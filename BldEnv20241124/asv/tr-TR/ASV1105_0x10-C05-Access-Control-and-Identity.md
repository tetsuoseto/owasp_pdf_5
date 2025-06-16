# C5 Erişim Kontrolü ve Kimlik Doğrulama AI Bileşenleri ve Kullanıcıları için

## Kontrol Amacı

Yapay zeka sistemleri için etkili erişim kontrolü, sağlam kimlik yönetimi, bağlama duyarlı yetkilendirme ve sıfır güven ilkelerine uygun çalışma zamanı uygulamasını gerektirir. Bu kontroller, insanların, hizmetlerin ve otonom ajanların yalnızca açıkça verilen kapsamlar içinde modeller, veriler ve hesaplama kaynakları ile etkileşimde bulunmasını sağlar ve sürekli doğrulama ile denetim yetenekleri sunar.

---

## C5.1 Kimlik Yönetimi ve Doğrulama

Yetkili işlemler için çok faktörlü kimlik doğrulama ile tüm varlıklar için kriptografik olarak desteklenen kimlikler oluşturun.

|   #   | Description                                                                                                                                                                                                                                                                | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 5.1.1 | Tüm insan kullanıcıların ve hizmet ilkelerinin, benzersiz kimlikten belirteç eşlemeleriyle (paylaşılan hesaplar veya kimlik bilgileri olmadan) OIDC/SAML protokolleri kullanarak merkezi bir kurumsal kimlik sağlayıcısı (IdP) üzerinden kimlik doğruladığından emin olun. |   1   | D/V  |
| 5.1.2 | Yüksek riskli işlemlerin (model dağıtımı, ağırlık ihracatı, eğitim verilerine erişim, üretim yapılandırma değişiklikleri) çok faktörlü kimlik doğrulama veya oturum yeniden doğrulaması ile adım yükseltme kimlik doğrulaması gerektirdiğini doğrulayın.                   |   1   | D/V  |
| 5.1.3 | Yeni yöneticilerin üretim sistemine erişim almadan önce, NIST 800-63-3 IAL-2 veya eşdeğer standartlarla uyumlu kimlik doğrulama süreçlerinden geçtiğini doğrulayın.                                                                                                        |   2   |  D   |
| 5.1.4 | Erişim incelemelerinin, hareketsiz hesapların otomatik tespiti, kimlik bilgisi döndürme zorunluluğu ve hizmet dışı bırakma iş akışları ile birlikte üç ayda bir yapıldığını doğrulayın.                                                                                    |   2   |  V   |
| 5.1.5 | Federated AI ajanlarının, maksimum geçerlilik süresi 24 saat olan ve kaynak kriptografik kanıtı içeren imzalı JWT beyanları aracılığıyla kimlik doğruladığını doğrulayın.                                                                                                  |   3   | D/V  |

---

## C5.2 Kaynak Yetkilendirmesi ve Asgari Ayrıcalık

Tüm Yapay Zeka kaynakları için açık izin modelleri ve denetim izleriyle birlikte ince taneli erişim kontrolleri uygulayın.

|   #   | Description                                                                                                                                                                                                                                                                         | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 5.2.1 | Her AI kaynağının (veri kümeleri, modeller, uç noktalar, vektör koleksiyonları, gömme indeksleri, hesaplama örnekleri) rol tabanlı erişim kontrollerini, açıkça belirtilmiş izin listeleri ve varsayılan reddetme politikaları ile uyguladığını doğrulayın.                         |   1   | D/V  |
| 5.2.2 | Servis hesaplarında en az ayrıcalık prensiplerinin varsayılan olarak uygulandığını doğrulayın; izinler öncelikle salt okunur olarak başlatılmalı ve yazma erişimi için belgelenmiş iş gerekçesi gereklidir.                                                                         |   1   | D/V  |
| 5.2.3 | Tüm erişim kontrolü değişikliklerinin onaylanmış değişiklik taleplerine bağlı olduğunu ve zaman damgaları, işlemci kimlikleri, kaynak tanımlayıcıları ve izin farkları ile değiştirilemez şekilde kaydedildiğini doğrulayın.                                                        |   1   |  V   |
| 5.2.4 | Veri sınıflandırma etiketlerinin (Kişisel Tanımlanabilir Bilgi - PII, Sağlık Bilgisi - PHI, ihracat kontrolü altındaki, özel) türetilmiş kaynaklara (gömülü veriler, istem önbellekleri, model çıktıları) tutarlı politika uygulanmasıyla otomatik olarak aktarıldığını doğrulayın. |   2   |  D   |
| 5.2.5 | Yetkisiz erişim girişimlerinin ve ayrıcalık yükseltme olaylarının, bağlamsal meta verilerle birlikte 5 dakika içinde SIEM sistemlerine gerçek zamanlı uyarılar tetiklediğini doğrulayın.                                                                                            |   2   | D/V  |

---

## C5.3 Dinamik Politika Değerlendirmesi

Denetim yetenekleriyle birlikte bağlama duyarlı yetkilendirme kararları için öznitelik tabanlı erişim kontrolü (ABAC) motorları dağıtın.

|   #   | Description                                                                                                                                                                                                       | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 5.3.1 | Yetkilendirme kararlarının, kimlik doğrulamalı API'ler aracılığıyla erişilebilen ve kriptografik bütünlük korumasına sahip özel bir politika motoruna (OPA, Cedar veya eşdeğeri) dışsallaştırıldığını doğrulayın. |   1   | D/V  |
| 5.3.2 | Politikaların, kullanıcı yetki seviyesi, kaynak duyarlılık sınıflandırması, istek bağlamı, kiracı izolasyonu ve zamansal kısıtlamalar gibi dinamik özellikleri çalışma zamanında değerlendirdiğini doğrulayın.    |   1   | D/V  |
| 5.3.3 | Politika tanımlarının sürüm kontrollü, eşler arası gözden geçirilmiş ve üretim dağıtımı öncesinde CI/CD boru hatlarında otomatik testlerle doğrulanmış olduğunu doğrulayın.                                       |   2   |  D   |
| 5.3.4 | Politika değerlendirme sonuçlarının yapılandırılmış karar gerekçelerini içerdiğini ve korelasyon analizi ile uyumluluk raporlaması için SIEM sistemlerine iletildiğini doğrulayın.                                |   2   |  V   |
| 5.3.5 | Politika önbellek zaman aşımı (TTL) değerlerinin, yüksek hassasiyetli kaynaklar için 5 dakikayı, önbellek geçersiz kılma yeteneklerine sahip standart kaynaklar için ise 1 saati aşmadığını doğrulayın.           |   3   | D/V  |

---

## C5.4 Sorgu Zamanı Güvenlik Uygulaması

Zorunlu filtreleme ve satır düzeyinde güvenlik politikaları ile veritabanı katmanı güvenlik kontrollerini uygulayın.

|   #   | Description                                                                                                                                                                                                                                  | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 5.4.1 | Tüm vektör veritabanı ve SQL sorgularının zorunlu güvenlik filtrelerini (kiracı kimliği, hassasiyet etiketleri, kullanıcı kapsamı) içerdiğini ve bu filtrelerin uygulama kodu değil, veritabanı motoru seviyesinde uygulandığını doğrulayın. |   1   | D/V  |
| 5.4.2 | Tüm vektör veritabanları, arama indeksleri ve eğitim veri setleri için politika miras alınması ile satır düzeyi güvenlik (RLS) politikalarının ve alan düzeyi maskelemenin etkinleştirildiğini doğrulayın.                                   |   1   | D/V  |
| 5.4.3 | Başarısız yetkilendirme değerlendirmelerinin, sorguları derhal sonlandırarak ve boş sonuç setleri döndürmek yerine açık yetkilendirme hata kodları ile yanıt vererek "kafa karışıklığı vekili saldırılarını" engellediğini doğrulayın.       |   2   |  D   |
| 5.4.4 | Politika değerlendirme gecikmesinin, yetkilendirme atlanmasına olanak tanıyabilecek zaman aşımı durumları için otomatik uyarılarla sürekli olarak izlendiğini doğrulayın.                                                                    |   2   |  V   |
| 5.4.5 | Sorgu yeniden deneme mekanizmalarının, aktif kullanıcı oturumları içinde dinamik izin değişikliklerini hesaba katmak için yetkilendirme politikalarını yeniden değerlendirdiğini doğrulayın.                                                 |   3   | D/V  |

---

## C5.5 Çıktı Filtreleme ve Veri Kaybı Önleme

Yapay zeka tarafından oluşturulan içerikte yetkisiz veri ifşasını önlemek için son işlem kontrolleri uygulayın.

|   #   | Description                                                                                                                                                                                                    | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 5.5.1 | İçeriği isteklere teslim etmeden önce, çıkarım sonrası filtreleme mekanizmalarının yetkisiz KİŞİSEL TANIMLAYICI BİLGİLERİ (PII), sınıflandırılmış bilgiler ve özel verileri tarayıp sansürlediğini doğrulayın. |   1   | D/V  |
| 5.5.2 | Model çıktılarındaki atıfların, referansların ve kaynak atıflarının, çağıran kişilerin yetkileri doğrultusunda doğrulandığını ve yetkisiz erişim tespit edilirse kaldırıldığını doğrulayın.                    |   1   | D/V  |
| 5.5.3 | Kullanıcı izin seviyeleri ve veri sınıflandırmalarına göre çıktı formatı kısıtlamalarının (temizlenmiş PDF'ler, meta verisi kaldırılmış resimler, onaylı dosya türleri) uygulandığını doğrulayın.              |   2   |  D   |
| 5.5.4 | Kırpma algoritmalarının deterministik, sürüm kontrollü olduğunu ve uyumluluk soruşturmaları ile adli analizleri desteklemek için denetim kayıtlarını tuttuğunu doğrulayın.                                     |   2   |  V   |
| 5.5.5 | Yüksek riskli sansürleme olaylarının, verilerin ifşa edilmeden adli inceleme için orijinal içeriğin kriptografik karmalarını içeren uyarlanabilir günlükler oluşturduğunu doğrulayın.                          |   3   |  V   |

---

## C5.6 Çok Kiracılı İzolasyon

Paylaşılan Yapay Zeka altyapısında kiracılar arasında kriptografik ve mantıksal izolasyon sağlanmalıdır.

|   #   | Description                                                                                                                                                                                                                | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 5.6.1 | Bellek alanlarının, gömme depolarının, önbellek girişlerinin ve geçici dosyaların her kiracı için isim alanı ayrı tutulduğunu ve kiracı silindiğinde veya oturum sona erdiğinde güvenli biçimde temizlendiğini doğrulayın. |   1   | D/V  |
| 5.6.2 | Her API isteğinin, oturum bağlamı ve kullanıcı yetkileriyle kriptografik olarak doğrulanan kimlik doğrulanmış bir kiracı tanımlayıcısı içerdiğini doğrulayın.                                                              |   1   | D/V  |
| 5.6.3 | Ağ politikalarının servis ağları ve konteyner orkestrasyon platformları içinde kiracılar arası iletişim için varsayılan olarak reddetme kurallarını uyguladığını doğrulayın.                                               |   2   |  D   |
| 5.6.4 | Müşteri tarafından yönetilen anahtar (CMK) desteği ve kiracı veri depoları arasında kriptografik izolasyon ile her kiracı için şifreleme anahtarlarının benzersiz olduğunu doğrulayın.                                     |   3   |  D   |

---

## C5.7 Otonom Ajan Yetkilendirmesi

Kapsamlı yetenek belirteçleri ve sürekli yetkilendirme yoluyla yapay zeka ajanları ve otonom sistemler için kontrol izinleri.

|   #   | Description                                                                                                                                                                                                                               | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 5.7.1 | Otonom ajanların, izin verilen eylemler, erişilebilir kaynaklar, zaman sınırları ve operasyonel kısıtlamaları açıkça listeleyen sınırlandırılmış yetki belirteçleri aldığını doğrulayın.                                                  |   1   | D/V  |
| 5.7.2 | Yüksek riskli yeteneklerin (dosya sistemi erişimi, kod yürütme, harici API çağrıları, finansal işlemler) varsayılan olarak devre dışı bırakıldığını ve etkinleştirme için iş gerekçeleriyle birlikte açık izinler gerektiğini doğrulayın. |   1   | D/V  |
| 5.7.3 | Yetenek belirteçlerinin kullanıcı oturumlarına bağlı olduğunu doğrulayın, kriptografik bütünlük korumasını dahil edin ve bunların çevrimdışı senaryolarda saklanamaması veya yeniden kullanılamamasını sağlayın.                          |   2   |  D   |
| 5.7.4 | Temsilci tarafından başlatılan işlemlerin, tam bağlam değerlendirmesi ve denetim kaydı ile birlikte ABAC politika motoru aracılığıyla ikincil yetkilendirmeye tabi tutulduğunu doğrulayın.                                                |   2   |  V   |
| 5.7.5 | Ajan hata durumları ve istisna işleme süreçlerinin, olay analizi ve adli araştırmayı desteklemek için yetenek kapsamı bilgilerini içerdiğini doğrulayın.                                                                                  |   3   |  V   |

---

## Referanslar

### Standartlar ve Çerçeveler

* [NIST SP 800-63-3: Digital Identity Guidelines](https://pages.nist.gov/800-63-3/)
* [Zero Trust Architecture – NIST SP 800-207](https://nvlpubs.nist.gov/nistpubs/specialpublications/NIST.SP.800-207.pdf)
* [OWASP Application Security Verification Standard (AISVS)](https://owasp.org/www-project-application-security-verification-standard/)
  ​
### Uygulama Rehberleri

* [Identity and Access Management in the AI Era: 2025 Guide – IDSA](https://www.idsalliance.org/blog/identity-and-access-management-in-the-ai-era-2025-guide/)
* [Attribute-Based Access Control with OPA – Permify](https://medium.com/permify-tech-blog/attribute-based-access-control-abac-implementation-with-open-policy-agent-opa-b47052248f29)
* [How We Designed Cedar to Be Intuitive, Fast, and Safe – AWS](https://aws.amazon.com/blogs/security/how-we-designed-cedar-to-be-intuitive-to-use-fast-and-safe/)
  ​
### Yapay Zeka'ya Özgü Güvenlik

* [Row Level Security in Vector DBs for RAG – Bluetuple.ai](https://medium.com/bluetuple-ai/implementing-row-level-security-in-vector-dbs-for-rag-applications-fdbccb63d464)
* [Tenant Isolation in Multi-Tenant Systems – WorkOS](https://workos.com/blog/tenant-isolation-in-multi-tenant-systems)
* [Handling AI Agent Permissions – Stytch](https://stytch.com/blog/handling-ai-agent-permissions/)
* [OWASP Top 10 for Large Language Model Applications](https://owasp.org/www-project-top-10-for-large-language-model-applications/)

