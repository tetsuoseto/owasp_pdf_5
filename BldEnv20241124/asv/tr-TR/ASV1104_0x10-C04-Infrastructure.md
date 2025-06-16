# C4 Altyapısı, Yapılandırma ve Dağıtım Güvenliği

## Kontrol Hedefi

Yapay zeka altyapısı, ayrıcalık yükseltme, tedarik zinciri tahrifatı ve yatay hareketliliğe karşı güvenli yapılandırma, çalışma zamanı izolasyonu, güvenilir dağıtım hatları ve kapsamlı izleme yoluyla güçlendirilmelidir. Sadece yetkili, doğrulanmış altyapı bileşenleri ve yapılandırmaları, güvenlik, bütünlük ve denetlenebilirliği koruyan kontrollü süreçler aracılığıyla üretime ulaşır.

Temel Güvenlik Hedefi: Yalnızca kriptografik olarak imzalanmış, güvenlik açıkları taramasından geçmiş altyapı bileşenleri, güvenlik politikalarını uygulayan ve değiştirilemez denetim kayıtlarını sürdüren otomatik doğrulama hatları aracılığıyla üretime ulaşır.

---

## C4.1 Çalışma Zamanı Ortamı İzolasyonu

Çekirdek düzeyinde izolasyon ilkelikleri ve zorunlu erişim kontrolleri aracılığıyla konteyner kaçışlarını ve ayrıcalık yükseltmelerini önleyin.

|   #   | Description                                                                                                                                                                                                                   | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.1.1 | Tüm AI konteynerlerinin CAP_SETUID, CAP_SETGID ve güvenlik temel çizelgelerinde belgelenmiş açıkça gerekli yetenekler dışında TÜM Linux yeteneklerini kaldırdığını doğrulayın.                                                |   1   | D/V  |
| 4.1.2 | Seccomp profillerinin, önceden onaylanmış izin listelerinde bulunanlar dışındaki tüm syscall çağrılarını engellediğini doğrulayın; ihlaller konteynerin sonlanmasına ve güvenlik uyarılarının oluşturulmasına neden olur.     |   1   | D/V  |
| 4.1.3 | AI iş yüklerinin salt okunur kök dosya sistemleriyle, geçici veriler için tmpfs ile ve kalıcı veriler için noexec bağlama seçenekleri uygulanmış adlandırılmış hacimlerle çalıştığını doğrulayın.                             |   2   | D/V  |
| 4.1.4 | eBPF tabanlı çalışma zamanı izleme (Falco, Tetragon veya eşdeğeri) ayrıcalık yükseltme girişimlerini tespit eder ve kurumsal yanıt süresi gereksinimleri dahilinde otomatik olarak suçlu süreçleri sonlandırır mı doğrulayın. |   2   | D/V  |
| 4.1.5 | Yüksek riskli Yapay Zeka iş yüklerinin donanım-izoleli ortamlarda (Intel TXT, AMD SVM veya özel çıplak-metal düğümler) doğrulama onayı ile çalıştığını doğrulayın.                                                            |   3   | D/V  |

---

## C4.2 Güvenli Derleme ve Dağıtım Boru Hatları

Tekrarlanabilir derlemeler ve imzalanmış yapılar aracılığıyla kriptografik bütünlüğü ve tedarik zinciri güvenliğini sağlayın.

|   #   | Description                                                                                                                                                                                                              | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 4.2.1 | Altyapı kodu olarak (infrastructure-as-code) her commit'te tfsec, Checkov veya Terrascan gibi araçlarla tarandığını doğrulayın ve KRİTİK veya YÜKSEK şiddette bulguların olduğu durumlarda merge işlemlerini engelleyin. |   1   | D/V  |
| 4.2.2 | Kapsayıcı derlemelerinin, yapılar arasında aynı SHA256 karmalarına sahip olarak tekrarlanabilir olduğunu doğrulayın ve Sigstore ile imzalanmış SLSA Seviye 3 köken beyanları oluşturun.                                  |   1   | D/V  |
| 4.2.3 | Konteyner görüntülerinin CycloneDX veya SPDX SBOM'larını içerdiğini ve kayıt defterine göndermeden önce Cosign ile imzalandığını doğrulayın; imzasız görüntülerin dağıtımda reddedilmesini sağlayın.                     |   2   | D/V  |
| 4.2.4 | CI/CD boru hatlarının, HashiCorp Vault, AWS IAM Rolleri veya Azure Yönetilen Kimliği tarafından sağlanan ve ömürleri organizasyonel güvenlik politikası sınırlarını aşmayan OIDC jetonları kullandığını doğrulayın.      |   2   | D/V  |
| 4.2.5 | Dağıtım süreci sırasında Cosign imzalarının ve SLSA kaynağının doğrulandığını ve doğrulama hatalarının dağıtımın başarısız olmasına neden olduğunu doğrulayın.                                                           |   2   | D/V  |
| 4.2.6 | Yapı ortamlarının kalıcı depolama olmadan ve üretim VPC'lerinden ağ izolasyonuyla geçici konteynerlerde veya sanal makinelerde çalıştığını doğrulayın.                                                                   |   2   | D/V  |

---

## C4.3 Ağ Güvenliği ve Erişim Kontrolü

Varsayılan reddetme politikaları ve şifreli iletişimle sıfır güven ağlarını uygulayın.

|   #   | Description                                                                                                                                                                                                          | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.3.1 | Kubernetes NetworkPolicies veya eşdeğer bir yapı ile varsayılan-engelleme (default-deny) giriş/çıkış kurallarının, gerekli portlar (443, 8080 vb.) için açıkça izin verilen kurallarla uygulandığını doğrulayın.     |   1   | D/V  |
| 4.3.2 | SSH (port 22), RDP (port 3389) ve bulut meta veri uç noktalarının (169.254.169.254) engellendiğini veya sertifika tabanlı kimlik doğrulaması gerektirdiğini doğrulayın.                                              |   1   | D/V  |
| 4.3.3 | Dışa giden trafiğin HTTP/HTTPS proxy’leri (Squid, Istio veya bulut NAT geçitleri) aracılığıyla alan adı izin listeleri ile filtrelendiğini ve engellenen isteklerin kaydedildiğini doğrulayın.                       |   2   | D/V  |
| 4.3.4 | Hizmetler arası iletişimin, organizasyon politikalarına göre döndürülen sertifikalarla karşılıklı TLS kullandığını ve sertifika doğrulamasının zorunlu tutulduğunu (doğrulamayı atla bayrakları olmadan) doğrulayın. |   2   | D/V  |
| 4.3.5 | Yapay Zeka altyapısının, doğrudan internet erişimi olmayan, özel ayrılmış VPC/VNet’lerde çalıştığını ve yalnızca NAT ağ geçitleri veya bastion sunucuları aracılığıyla iletişim kurduğunu doğrulayın.                |   2   | D/V  |

---

## C4.4 Gizli Bilgiler ve Kriptografik Anahtar Yönetimi

Sıfır güven erişimi ile donanım destekli depolama ve otomatik rotasyon yoluyla kimlik bilgilerini koruyun.

|   #   | Description                                                                                                                                                                                                           | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.4.1 | Gizli bilgilerin, HashiCorp Vault, AWS Secrets Manager, Azure Key Vault veya Google Secret Manager içinde, beklemede AES-256 ile şifrelenmiş olarak depolandığını doğrulayın.                                         |   1   | D/V  |
| 4.4.2 | Kriptografik anahtarların, kurumsal kriptografik politikaya uygun anahtar döndürme işlemi ile FIPS 140-2 Seviye 2 HSM'lerinde (AWS CloudHSM, Azure Dedicated HSM) oluşturulduğunu doğrulayın.                         |   1   | D/V  |
| 4.4.3 | Gizli anahtarların döngüsünün, personel değişiklikleri veya güvenlik olayları tarafından tetiklenen sıfır kesinti süresi dağıtımı ve anlık döngü ile otomatik yapıldığını doğrulayın.                                 |   2   | D/V  |
| 4.4.4 | Konteyner görüntülerinin API anahtarları, parolalar veya sertifikalar içeren yapıları engelleyen araçlar (GitLeaks, TruffleHog veya detect-secrets) ile tarandığını doğrulayın.                                       |   2   | D/V  |
| 4.4.5 | Üretim gizli erişiminin donanım tokenleri (YubiKey, FIDO2) ile MFA gerektirdiğini ve kullanıcı kimlikleri ile zaman damgalarını içeren değiştirilemez denetim günlükleri tarafından kaydedildiğini doğrulayın.        |   2   | D/V  |
| 4.4.6 | Gizli bilgilerin Kubernetes sırları, monte edilmiş hacimler veya init konteynerleri aracılığıyla enjekte edildiğini doğrulayın ve gizli bilgilerin asla ortam değişkenlerine veya imajlara gömülmediğinden emin olun. |   2   | D/V  |

---

## C4.5 AI İş Yükü Kapsayıcısı ve Doğrulama

Güvenilmeyen Yapay Zeka modellerini kapsamlı davranış analizi ile birlikte güvenli sanal ortamlarda izole edin.

|   #   | Description                                                                                                                                                                                                | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.5.1 | Dış AI modellerinin gVisor, Firecracker, CrossVM gibi mikroVM'lerde veya --security-opt=no-new-privileges ve --read-only bayrakları ile Docker konteynerlerinde çalıştığını doğrulayın.                    |   1   | D/V  |
| 4.5.2 | Sandbox ortamlarının ağ bağlantısının olmadığını (--network=none) veya yalnızca localhost erişimine sahip olduğunu ve tüm dış isteklerin iptables kurallarıyla engellendiğini doğrulayın.                  |   1   | D/V  |
| 4.5.3 | Yapay zeka modeli doğrulamasının, kurumsal olarak tanımlanmış test kapsamı ve arka kapı tespiti için davranış analizi ile birlikte otomatik kırmızı takım testlerini içerdiğini doğrulayın.                |   2   | D/V  |
| 4.5.4 | Bir yapay zeka modeli üretime alınmadan önce, sandbox sonuçlarının yetkili güvenlik personeli tarafından kriptografik olarak imzalandığını ve değiştirilemez denetim kayıtlarında saklandığını doğrulayın. |   2   | D/V  |
| 4.5.5 | Değerlendirmeler arasında izolasyon ortamlarının yok edilip altın imajlardan yeniden oluşturulduğunu, tam dosya sistemi ve bellek temizliği ile doğrulayın.                                                |   2   | D/V  |

---

## C4.6 Altyapı Güvenliği İzleme

Altyapıyı sürekli olarak otomatik düzeltme ve gerçek zamanlı uyarılarla tarayın ve izleyin.

|   #   | Description                                                                                                                                                                                                                      | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.6.1 | Konteyner imajlarının, kurumsal programlara göre tarandığını ve KRİTİK güvenlik açıklarının, kurumsal risk eşiklerine dayanarak dağıtımı engellediğini doğrulayın.                                                               |   1   | D/V  |
| 4.6.2 | Altyapının, kuruluş tarafından tanımlanmış uyumluluk eşik değerleri ve başarısız kontroller için otomatik düzeltmeler ile CIS Benchmarkları veya NIST 800-53 kontrollerini karşıladığını doğrulayın.                             |   1   | D/V  |
| 4.6.3 | Yüksek şiddetteki güvenlik açıklarının, kuruluşun risk yönetimi zaman çizelgelerine uygun olarak ve aktif olarak istismar edilen CVE'ler için acil müdahale prosedürleriyle birlikte yamalandığını doğrulayın.                   |   2   | D/V  |
| 4.6.4 | Güvenlik uyarılarının CEF veya STIX/TAXII formatlarını kullanarak, otomatik zenginleştirme ile SIEM platformlarıyla (Splunk, Elastic veya Sentinel) entegre olduğunu doğrulayın.                                                 |   2   |  V   |
| 4.6.5 | Altyapı metriklerinin SLA panoları ve yönetici raporlaması ile izleme sistemlerine (Prometheus, DataDog) aktarıldığını doğrulayın.                                                                                               |   3   |  V   |
| 4.6.6 | Organizasyonel izleme gereksinimlerine uygun olarak yapılandırma sapmasının araçlar (Chef InSpec, AWS Config) kullanılarak tespit edildiğini ve yetkisiz değişiklikler için otomatik geri alma işleminin yapıldığını doğrulayın. |   2   | D/V  |

---

## C4.7 AI Altyapısı Kaynak Yönetimi

Kaynak tükenmesi saldırılarını önleyin ve kotalar ile izleme yoluyla adil kaynak tahsisini sağlayın.

|   #   | Description                                                                                                                                                                                                                                                     | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.7.1 | GPU/TPU kullanımının, organizasyon tarafından belirlenen eşiklerde tetiklenen uyarılarla izlenip izlenmediğini ve kapasite yönetimi politikalarına dayalı olarak otomatik ölçeklendirme veya yük dengelemenin etkinleştirilip etkinleştirilmediğini doğrulayın. |   1   | D/V  |
| 4.7.2 | AI iş yükü metriklerinin (çıkarım gecikmesi, işlem hacmi, hata oranları) kurumsal izleme gereksinimlerine uygun olarak toplandığını ve altyapı kullanımı ile ilişkilendirildiğini doğrulayın.                                                                   |   1   | D/V  |
| 4.7.3 | Kubernetes ResourceQuotas veya eşdeğeri, örgütsel kaynak tahsis politikalarına göre bireysel iş yüklerini doğrulayarak sert sınırlarla sınırlandırıldığını doğrulayın.                                                                                          |   2   | D/V  |
| 4.7.4 | Maliyet izlemenin, organizasyonel bütçe eşiklerine dayalı uyarılar ve bütçe aşımları için otomatik kontrollerle birlikte iş yükü/kiracı başına harcamaları takip ettiğini doğrulayın.                                                                           |   2   |  V   |
| 4.7.5 | Kapasite planlamasının, örgütsel olarak tanımlanmış tahmin dönemleri ile geçmiş verileri kullandığını ve talep kalıplarına dayalı otomatik kaynak sağlama yaptığını doğrulayın.                                                                                 |   3   |  V   |
| 4.7.6 | Kaynak tükenmesinin, kapasite politikalarına dayalı hız sınırlaması ve iş yükü izolasyonunu içeren organizasyonel yanıt gereksinimlerine göre devre kesicileri tetiklediğini doğrulayın.                                                                        |   2   | D/V  |

---

## C4.8 Ortam Ayrımı ve Yayın Kontrolleri

Otomatik terfi kapıları ve güvenlik doğrulaması ile katı ortam sınırlarını uygulayın.

|   #   | Description                                                                                                                                                                                                                                         | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.8.1 | Geliştirme/test/üretim ortamlarının ayrı VPC/VNet'lerde çalıştığını, paylaşılan IAM rolleri, güvenlik grupları veya ağ bağlantısı olmadığını doğrulayın.                                                                                            |   1   | D/V  |
| 4.8.2 | Ortam tanıtımının, organizasyon tarafından tanımlanmış yetkili personelin kriptografik imzaları ile onayını ve değiştirilemez denetim izlerini gerektirdiğini doğrulayın.                                                                           |   1   | D/V  |
| 4.8.3 | Üretim ortamlarının SSH erişimini engellediğini, hata ayıklama uç noktalarını devre dışı bıraktığını ve acil durumlar hariç organizasyonel ön bildirim gereksinimleriyle değişiklik talepleri gerektiğini doğrulayın.                               |   2   | D/V  |
| 4.8.4 | Altyapı-kod olarak yapılan değişikliklerin ana dal ile birleştirilmeden önce otomatik test ve güvenlik taraması ile eş incelemesini gerektirdiğini doğrulayın.                                                                                      |   2   | D/V  |
| 4.8.5 | Üretim dışı verilerin, organizasyonel gizlilik gereksinimlerine uygun olarak anonimleştirildiğini, sentetik veri üretiminin yapıldığını veya KİB (Kişisel İdentifikasyon Bilgisi) kaldırılarak tam veri maskelemesinin doğrulandığını kontrol edin. |   2   | D/V  |
| 4.8.6 | Terfi kapılarının, onay için sıfır KRİTİK bulgu gerektiren otomatik güvenlik testlerini (SAST, DAST, konteyner taraması) içerdiğini doğrulayın.                                                                                                     |   2   | D/V  |

---

## C4.9 Altyapı Yedekleme ve Kurtarma

Otomatik yedeklemeler, test edilmiş kurtarma prosedürleri ve afet kurtarma yetenekleri aracılığıyla altyapı dayanıklılığını sağlayın.

|   #   | Description                                                                                                                                                                                                             | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.9.1 | Altyapı yapılandırmalarının, organizasyonun yedekleme programlarına göre, 3-2-1 yedekleme stratejisi uygulanarak coğrafi olarak ayrı bölgelere yedeklendiğini doğrulayın.                                               |   1   | D/V  |
| 4.9.2 | Yedekleme sistemlerinin fidye yazılımı koruması için ayrı kimlik bilgilerinin kullanıldığı izole ağlarda ve hava boşluklu depolamada çalıştığını doğrulayın.                                                            |   2   | D/V  |
| 4.9.3 | Kurtarma prosedürlerinin, RTO ve RPO hedeflerinin organizasyonel gereksinimleri karşılayacak şekilde, organizasyonel takvimlere göre otomatik testlerle test edilip doğrulandığını teyit edin.                          |   2   |  V   |
| 4.9.4 | Felaket kurtarma işlemlerinin, model ağırlıklarının geri yüklenmesi, GPU kümelerinin yeniden oluşturulması ve hizmet bağımlılıklarının haritalanması gibi Yapay Zeka'ya özgü çalışma kitaplarını içerdiğini doğrulayın. |   3   |  V   |

---

## C4.10 Altyapı Uyumluluğu ve Yönetişim

Sürekli değerlendirme, dokümantasyon ve otomatik kontroller yoluyla düzenleyici uyumu sürdürün.

|   #    | Description                                                                                                                                                                                 | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.10.1 | Alt yapı uyumluluğunun SOC 2, ISO 27001 veya FedRAMP kontrollerine karşı kuruluş takvimlerine göre otomatik kanıt toplama ile değerlendirildiğini doğrulayın.                               |   2   | D/V  |
| 4.10.2 | Altyapı dokümantasyonunun, organizasyonel değişiklik yönetimi gereksinimlerine uygun olarak güncellenmiş ağ diyagramları, veri akış haritaları ve tehdit modellerini içerdiğini doğrulayın. |   2   |  V   |
| 4.10.3 | Altyapı değişikliklerinin, yüksek riskli modifikasyonlar için düzenleyici onay iş akışlarıyla birlikte otomatik uyumluluk etkisi değerlendirmesine tabi tutulduğunu doğrulayın.             |   3   | D/V  |

---

## C4.11 AI Donanım Güvenliği

GPU'lar, TPU'lar ve özel AI hızlandırıcıları dahil olmak üzere AI'ye özgü donanım bileşenlerini güvence altına alın.

|   #    | Description                                                                                                                                                                      | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.11.1 | AI hızlandırıcı yazılımının (GPU BIOS, TPU yazılımı) kriptografik imzalarla doğrulandığını ve kurumsal yama yönetimi zaman çizelgelerine göre güncellendiğini doğrulayın.        |   2   | D/V  |
| 4.11.2 | İş yükü yürütülmeden önce, AI hızlandırıcı bütünlüğünün TPM 2.0, Intel TXT veya AMD SVM kullanılarak donanım doğrulaması ile doğrulandığını teyit edin.                          |   2   | D/V  |
| 4.11.3 | İşler arasında bellek temizliği ile SR-IOV, MIG (Çoklu Örnek GPU) veya eşdeğer donanım ayrımı kullanarak GPU belleğinin iş yükleri arasında izole edildiğini doğrulayın.         |   2   | D/V  |
| 4.11.4 | Yapay zeka donanım tedarik zincirinin, üretici sertifikaları ile menşei doğrulaması ve müdahaleye karşı dayanıklı ambalaj doğrulaması içerdiğini doğrulayın.                     |   3   |  V   |
| 4.11.5 | Donanım güvenlik modüllerinin (HSM'ler) AI model ağırlıklarını ve kriptografik anahtarları FIPS 140-2 Seviye 3 veya Common Criteria EAL4+ sertifikası ile koruduğunu doğrulayın. |   3   | D/V  |

---

## C4.12 Uç ve Dağıtık AI Altyapısı

Kenarda hesaplama, federated öğrenme ve çoklu site mimarilerini içeren güvenli dağıtılmış yapay zeka dağıtımları.

|   #    | Description                                                                                                                                                                       | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.12.1 | Uç AI cihazlarının, organizasyonun sertifika yönetimi politikasına göre döndürülen cihaz sertifikaları kullanarak karşılıklı TLS ile merkezi altyapıya doğrulandığını doğrulayın. |   2   | D/V  |
| 4.12.2 | Uc cihazların, doğrulanmış imzalarla güvenli açılış ve firmware düşürme saldırılarını önleyen geri alma koruması uyguladığını doğrulayın.                                         |   2   | D/V  |
| 4.12.3 | Dağıtık yapay zeka koordinasyonunun, katılımcı doğrulaması ve kötü niyetli düğüm tespiti ile birlikte Bizans hata toleranslı fikir birliği algoritmaları kullandığını doğrulayın. |   3   | D/V  |
| 4.12.4 | Kenar-bulut iletişiminin bant genişliği sınırlandırması, veri sıkıştırması ve çevrimdışı çalışma yetenekleri ile güvenli yerel depolamayı içerdiğini doğrulayın.                  |   3   | D/V  |

---

## C4.13 Çoklu Bulut ve Hibrit Altyapı Güvenliği

Çoklu bulut sağlayıcıları ve hibrit bulut-yerel dağıtımlarda güvenli Yapay Zeka iş yüklerini koruyun.

|   #    | Description                                                                                                                                                                                  | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.13.1 | Çoklu bulut yapay zeka dağıtımlarının, sağlayıcılar arasında merkezi politika yönetimi ile bulut bağımsız kimlik federasyonu (OIDC, SAML) kullandığını doğrulayın.                           |   2   | D/V  |
| 4.13.2 | Çapraz bulut veri transferinin, müşteri yönetimli anahtarlar ve yargı bölgesi başına uygulanan veri yerleşimi kontrolleri ile uçtan uca şifreleme kullandığını doğrulayın.                   |   2   | D/V  |
| 4.13.3 | Hibrit bulut AI iş yüklerinin, birleşik izleme ve uyarı ile şirket içi ve bulut ortamlarında tutarlı güvenlik politikaları uyguladığını doğrulayın.                                          |   2   | D/V  |
| 4.13.4 | Bulut sağlayıcıya bağımlılığı önlemenin, taşınabilir altyapı olarak kod, standartlaştırılmış API'ler ve format dönüştürme araçlarıyla veri dışa aktarma yeteneklerini içerdiğini doğrulayın. |   3   |  V   |
| 4.13.5 | Çoklu bulut maliyet optimizasyonunun, kaynak yayılımını önleyen güvenlik kontrollerini ve yetkisiz bulutlar arası veri transferi ücretlerini içerdiğini doğrulayın.                          |   3   |  V   |

---

## C4.14 Altyapı Otomasyonu ve GitOps Güvenliği

Yapay zeka altyapısı yönetimi için güvenli altyapı otomasyon hatları ve GitOps iş akışları.

|   #    | Description                                                                                                                                                                                    | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.14.1 | GitOps depolarının, GPG anahtarlarıyla imzalanmış commitler gerektirdiğini ve ana dallara doğrudan push yapılmasını engelleyen dal koruma kurallarının uygulandığını doğrulayın.               |   2   | D/V  |
| 4.14.2 | Altyapı otomasyonunun, yetkisiz değişiklikler için kurumsal yanıt gereksinimlerine göre tetiklenen otomatik düzeltme ve geri alma yetenekleriyle birlikte sapma tespiti içerdiğini doğrulayın. |   2   | D/V  |
| 4.14.3 | Otomatik altyapı sağlama işleminin, uyumsuz yapılandırmalar için dağıtımı engelleyen güvenlik politikası doğrulamasını içerdiğini doğrulayın.                                                  |   2   | D/V  |
| 4.14.4 | Altyapı otomasyon sırlarının, otomatik rotasyon ile dış gizli operatörler (External Secrets Operator, Bank-Vaults) aracılığıyla yönetildiğini doğrulayın.                                      |   2   | D/V  |
| 4.14.5 | Kendi kendini iyileştiren altyapının, otomatik olay müdahalesi ve paydaş bildirim iş akışlarıyla güvenlik olay korelasyonunu içerdiğini doğrulayın.                                            |   3   |  V   |

---

## C4.15 Kuantuma Dayanıklı Altyapı Güvenliği

Post-kuantum kriptografi ve kuantum-güvenli protokoller aracılığıyla kuantum hesaplama tehditlerine karşı AI altyapısını hazırlayın.

|   #    | Description                                                                                                                                                                                                     | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.15.1 | AI altyapısının, anahtar değişimi ve dijital imzalar için NIST onaylı kuantum sonrası kriptografik algoritmaları (CRYSTALS-Kyber, CRYSTALS-Dilithium, SPHINCS+) uyguladığını doğrulayın.                        |   3   | D/V  |
| 4.15.2 | Kuantum güvenli anahtar yönetimi protokolleri kullanılarak yüksek güvenlikli yapay zeka iletişimleri için kuantum anahtar dağıtım (QKD) sistemlerinin uygulandığını doğrulayın.                                 |   3   | D/V  |
| 4.15.3 | Kriptografik çeviklik çerçevelerinin, otomatik sertifika ve anahtar döndürme ile yeni kuantum sonrası algoritmalara hızlı geçişi sağladığını doğrulayın.                                                        |   3   | D/V  |
| 4.15.4 | Kuantum tehdit modellemesinin, belgelenmiş geçiş zaman çizelgeleri ve risk değerlendirmeleri ile birlikte kuantum saldırılarına karşı yapay zeka altyapısının güvenlik açıklarını değerlendirdiğini doğrulayın. |   3   |  V   |
| 4.15.5 | Hibrit klasik-kuantum kriptografik sistemlerin kuantum geçiş dönemi sırasında çok katmanlı savunma sağladığını ve performans izleme ile doğrulandığını teyit edin.                                              |   3   | D/V  |

---

## C4.16 Gizli Hesaplama ve Güvenli Bölmeler

Donanım tabanlı güvenilir yürütme ortamları ve gizli hesaplama teknolojilerini kullanarak Yapay Zeka iş yüklerini ve model ağırlıklarını koruyun.

|   #    | Description                                                                                                                                                                           | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.16.1 | Hassas yapay zeka modellerinin Intel SGX mahfazaları, AMD SEV-SNP veya ARM TrustZone içinde, şifreli bellek ve doğrulama kanıtı ile çalıştığını doğrulayın.                           |   3   | D/V  |
| 4.16.2 | Gizli konteynerlerin (Kata Containers, gizli hesaplama ile gVisor) donanım tarafından zorunlu kılınan bellek şifrelemesiyle yapay zeka iş yüklerini izole ettiğini doğrulayın.        |   3   | D/V  |
| 4.16.3 | Uzak doğrulamanın, yapay zeka modellerini yüklemeden önce bir yürütme ortamının özgünlüğüne kriptografik kanıtla dayanarak enclave bütünlüğünü doğruladığını kontrol edin.            |   3   | D/V  |
| 4.16.4 | Gizli yapay zeka çıkarım hizmetlerinin, şifreli hesaplama yoluyla model çıkarımını, mühürlü model ağırlıkları ve korumalı yürütme ile engellediğini doğrulayın.                       |   3   | D/V  |
| 4.16.5 | Güvenilir yürütme ortamı orkestrasyonunun, uzak teyit ve şifreli iletişim kanalları ile güvenli enclave yaşam döngüsünü yönettiğini doğrulayın.                                       |   3   | D/V  |
| 4.16.6 | Güvenli çok taraflı hesaplamanın (SMPC), bireysel veri setlerini veya model parametrelerini açığa çıkarmadan iş birliği içinde Yapay Zeka eğitimi yapılmasını sağladığını doğrulayın. |   3   | D/V  |

---

## C4.17 Sıfır Bilgi Altyapısı

Gizli bilgileri açığa çıkarmadan gizliliği koruyan yapay zeka doğrulama ve kimlik doğrulama için sıfır bilgi ispat sistemleri uygulayın.

|   #    | Description                                                                                                                                                                                  | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.17.1 | Sıfır bilgi ispatlarının (ZK-SNARK'lar, ZK-STARK'lar) model ağırlıklarını veya eğitim verilerini açığa çıkarmadan yapay zeka model bütünlüğünü ve eğitim kaynağını doğruladığını teyit edin. |   3   | D/V  |
| 4.17.2 | ZK tabanlı kimlik doğrulama sistemlerinin, kimlik bilgilerini açığa çıkarmadan AI hizmetleri için gizliliği koruyan kullanıcı doğrulamasını sağladığını doğrulayın.                          |   3   | D/V  |
| 4.17.3 | Özel küme kesişimi (PSI) protokollerinin, bireysel veri setlerini açığa çıkarmadan federatif yapay zeka için güvenli veri eşleştirmeyi sağladığını doğrulayın.                               |   3   | D/V  |
| 4.17.4 | Sıfır bilgi makine öğrenimi (ZKML) sistemlerinin, doğru hesaplamanın kriptografik kanıtıyla doğrulanabilir yapay zeka çıkarımlarını sağladığını doğrulayın.                                  |   3   | D/V  |
| 4.17.5 | ZK-rollupların, toplu doğrulama ve azaltılmış hesaplama yükü ile ölçeklenebilir, gizliliği koruyan AI işlem işleme sağladığını doğrulayın.                                                   |   3   | D/V  |

---

## C4.18 Yan Kanal Saldırısı Önleme

Zamanlama, güç, elektromanyetik ve önbellek tabanlı yan kanal saldırılarından kaynaklanabilecek hassas bilgilerin sızmasını önlemek için yapay zeka altyapısını koruyun.

|   #    | Description                                                                                                                                                            | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.18.1 | AI çıkarım zamanlamasının, zaman tabanlı model çıkarma saldırılarını önlemek için sabit-zaman algoritmaları ve dolgu kullanılarak normalize edildiğini doğrulayın.     |   3   | D/V  |
| 4.18.2 | Güç analizi korumasının, AI donanımı için gürültü enjeksiyonu, güç hattı filtreleme ve rastgeleleştirilmiş yürütme desenlerini içerdiğini doğrulayın.                  |   3   | D/V  |
| 4.18.3 | Önbellek tabanlı yan kanal hafifletmesinin bilgi sızıntısını önlemek için önbellek bölümlendirmesi, rastgeleleştirme ve temizleme talimatları kullandığını doğrulayın. |   3   | D/V  |
| 4.18.4 | Elektromanyetik yayılım korumasının, TEMPEST tarzı saldırıları önlemek için koruma, sinyal filtreleme ve rastgeleleştirilmiş işlemeyi içerdiğini doğrulayın.           |   3   | D/V  |
| 4.18.5 | Mikro mimari yan kanal savunmalarının, spekülatif yürütme kontrolleri ve bellek erişim deseninin gizlenmesini içerdiğini doğrulayın.                                   |   3   | D/V  |

---

## C4.19 Nöromorfik ve Özelleşmiş Yapay Zeka Donanım Güvenliği

Nöral morfik çipler, FPGA'lar, özel ASIC'ler ve optik hesaplama sistemleri gibi gelişmekte olan AI donanım mimarilerini güvence altına alın.

|   #    | Description                                                                                                                                                                                | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 4.19.1 | Neuromorfik çip güvenliğinin, spike deseni şifrelemesi, sinaptik ağırlık koruması ve donanım tabanlı öğrenme kuralı doğrulamasını içerdiğini doğrulayın.                                   |   3   | D/V  |
| 4.19.2 | FPGA tabanlı AI hızlandırıcılarının bitstream şifrelemesini, anti-tamper mekanizmalarını ve kimlik doğrulamalı güncellemelerle güvenli yapılandırma yüklemelerini uyguladığını doğrulayın. |   3   | D/V  |
| 4.19.3 | Özel ASIC güvenliğinin, çip üzerinde güvenlik işlemcileri, donanım tabanlı güven kökü ve yan kanal saldırılarına karşı korumalı güvenli anahtar depolama içerdiğini doğrulayın.            |   3   | D/V  |
| 4.19.4 | Optik bilgi işlem sistemlerinin kuantum güvenli optik şifreleme, güvenli fotonik anahtarlama ve korumalı optik sinyal işlemeyi uyguladığını doğrulayın.                                    |   3   | D/V  |
| 4.19.5 | Hibrit analog-dijital yapay zeka çiplerinin güvenli analog hesaplama, korumalı ağırlık depolama ve doğrulanmış analogdan dijitale dönüşüm içerdiğini doğrulayın.                           |   3   | D/V  |

---

## C4.20 Gizlilik Koruyucu Hesaplama Altyapısı

Yapay zeka işleme ve analiz sırasında hassas verileri korumak için gizliliği koruyan hesaplama altyapısı kontrollerini uygulayın.

|   #    | Description                                                                                                                                                                        | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.20.1 | Homomorfik şifreleme altyapısının, kriptografik bütünlük doğrulaması ve performans izleme ile hassas AI iş yükleri üzerinde şifreli hesaplama yapılmasını sağladığını doğrulayın.  |   3   | D/V  |
| 4.20.2 | Özel bilgi alma sistemlerinin, erişim desenlerinin kriptografik koruması ile sorgu desenlerini ortaya çıkarmadan veritabanı sorgularını mümkün kıldığını doğrulayın.               |   3   | D/V  |
| 4.20.3 | Güvenli çok taraflı hesaplama protokollerinin, bireysel girdileri veya ara hesaplamaları açığa çıkarmadan gizliliği koruyan AI çıkarımını mümkün kıldığını doğrulayın.             |   3   | D/V  |
| 4.20.4 | Gizliliği koruyan anahtar yönetiminin, dağıtık anahtar üretimi, eşik kriptografi ve donanım destekli korumayla güvenli anahtar döndürmeyi içerdiğini doğrulayın.                   |   3   | D/V  |
| 4.20.5 | Kriptografik güvenlik garantileri korunurken, gizlilik koruyucu hesaplama performansının toplu işleme, önbellekleme ve donanım hızlandırma yoluyla optimize edildiğini doğrulayın. |   3   | D/V  |

---

## C4.15 Ajan Çerçevesi Bulut Entegrasyonu Güvenliği ve Hibrit Dağıtım

Hibrit yerinde/bulut mimarilerine sahip bulut entegreli ajan çerçeveleri için güvenlik kontrolleri.

|   #    | Description                                                                                                                      | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.15.1 | Bulut depolama entegrasyonunun, ajan tarafından kontrol edilen anahtar yönetimi ile uçtan uca şifreleme kullandığını doğrulayın. |   1   | D/V  |
| 4.15.2 | Hibrit dağıtım güvenlik sınırlarının, şifrelenmiş iletişim kanalları ile açıkça tanımlandığını doğrulayın.                       |   2   | D/V  |
| 4.15.3 | Bulut kaynak erişiminin, sürekli doğrulama ile sıfır güven (zero-trust) doğrulamasını içerdiğini doğrulayın.                     |   2   | D/V  |
| 4.15.4 | Veri yerleşim gereksinimlerinin, depolama konumlarının kriptografik kanıtı ile zorunlu kılındığını doğrulayın.                   |   3   | D/V  |
| 4.15.5 | Bulut sağlayıcı güvenlik değerlendirmelerinin ajanlara özgü tehdit modellemesi ve risk değerlendirmesini içerdiğini doğrulayın.  |   3   | D/V  |

---

## Kaynaklar

* [NIST Cybersecurity Framework 2.0](https://www.nist.gov/cyberframework)
* [CIS Controls v8](https://www.cisecurity.org/controls/v8)
* [OWASP Container Security Verification Standard](https://github.com/OWASP/Container-Security-Verification-Standard)
* [Kubernetes Security Best Practices](https://kubernetes.io/docs/concepts/security/)
* [SLSA Supply Chain Security Framework](https://slsa.dev/)
* [NIST SP 800-190: Application Container Security Guide](https://csrc.nist.gov/publications/detail/sp/800-190/final)
* [Cloud Security Alliance: Cloud Controls Matrix](https://cloudsecurityalliance.org/research/cloud-controls-matrix/)
* [ENISA: Secure Infrastructure Design](https://www.enisa.europa.eu/topics/critical-information-infrastructures-and-services)
* [NIST SP 800-53: Security Controls for Federal Information Systems](https://csrc.nist.gov/publications/detail/sp/800-53/rev-5/final)
* [ISO 27001:2022 Information Security Management](https://www.iso.org/standard/27001)
* [NIST AI Risk Management Framework](https://www.nist.gov/itl/ai-risk-management-framework)
* [CIS Kubernetes Benchmark](https://www.cisecurity.org/benchmark/kubernetes)
* [FIPS 140-2 Security Requirements](https://csrc.nist.gov/publications/detail/fips/140/2/final)
* [NIST SP 800-207: Zero Trust Architecture](https://csrc.nist.gov/publications/detail/sp/800-207/final)
* [IEEE 2857: Privacy Engineering for AI Systems](https://standards.ieee.org/ieee/2857/7273/)
* [NIST SP 800-161: Cybersecurity Supply Chain Risk Management](https://csrc.nist.gov/publications/detail/sp/800-161/rev-1/final)
* [NIST Post-Quantum Cryptography Standards](https://csrc.nist.gov/Projects/post-quantum-cryptography)
* [Intel SGX Developer Guide](https://www.intel.com/content/www/us/en/developer/tools/software-guard-extensions/overview.html)
* [AMD SEV-SNP White Paper](https://www.amd.com/system/files/TechDocs/SEV-SNP-strengthening-vm-isolation-with-integrity-protection-and-more.pdf)
* [ARM TrustZone Technology](https://developer.arm.com/ip-products/security-ip/trustzone)
* [ZK-SNARKs: A Gentle Introduction](https://blog.ethereum.org/2016/12/05/zksnarks-in-a-nutshell/)
* [NIST SP 800-57: Cryptographic Key Management](https://csrc.nist.gov/publications/detail/sp/800-57-part-1/rev-5/final)
* [Side-Channel Attack Countermeasures](https://link.springer.com/book/10.1007/978-3-319-75268-6)
* [Neuromorphic Computing Security Challenges](https://ieeexplore.ieee.org/document/9458103)
* [FPGA Security: Fundamentals, Evaluation, and Countermeasures](https://link.springer.com/book/10.1007/978-3-319-90385-9)
* [Microsoft SEAL: Homomorphic Encryption Library](https://github.com/Microsoft/SEAL)
* [HElib: Homomorphic Encryption Library](https://github.com/homenc/HElib)
* [PALISADE Lattice Cryptography Library](https://palisade-crypto.org/)
* [Differential Privacy: A Survey of Results](https://link.springer.com/chapter/10.1007/978-3-540-79228-4_1)
* [Secure Aggregation for Federated Learning](https://eprint.iacr.org/2017/281.pdf)
* [Private Information Retrieval: Concepts and Constructions](https://link.springer.com/book/10.1007/978-3-030-16234-8)

