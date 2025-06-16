# Modeller, Çerçeveler ve Veri için C6 Tedarik Zinciri Güvenliği

## Kontrol Hedefi

Yapay zeka tedarik zinciri saldırıları, arka kapılar, önyargılar veya sömürülebilir kod yerleştirmek için üçüncü taraf modelleri, çerçeveleri veya veri kümelerini kullanır. Bu kontroller, tüm model yaşam döngüsünü korumak için uçtan uca köken takibi, zafiyet yönetimi ve izleme sağlar.

---

## C6.1 Önceden Eğitilmiş Modelin Denetimi ve Kökeni

Herhangi bir ince ayar veya dağıtımdan önce üçüncü taraf model kökenlerini, lisanslarını ve gizli davranışlarını değerlendirin ve doğrulayın.

|   #   | Description                                                                                                                                                           | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 6.1.1 | Her üçüncü taraf model eserinin, kaynak deposunu ve commit hash'ini belirten imzalı bir köken kaydı içerdiğini doğrulayın.                                            |   1   | D/V  |
| 6.1.2 | Modellerin, içe aktarılmadan önce kötü amaçlı katmanlar veya Truva atı tetikleyicileri için otomatik araçlar kullanılarak tarandığından emin olun.                    |   1   | D/V  |
| 6.1.3 | Transfer öğrenimi ile ince ayar yapmanın, gizli davranışları tespit etmek için düşmanca değerlendirmeyi geçtiğini doğrulayın.                                         |   2   |  D   |
| 6.1.4 | Model lisanslarının, ihracat-kontrol etiketlerinin ve veri-kaynak beyanlarının bir ML-BOM girdisinde kaydedildiğini doğrulayın.                                       |   2   |  V   |
| 6.1.5 | Yüksek riskli modellerin (herkese açık yüklenmiş ağırlıklar, doğrulanmamış oluşturucular) insan incelemesi ve onayı sağlanana kadar karantinada kaldığını doğrulayın. |   3   | D/V  |

---

## C6.2 Çerçeve ve Kütüphane Taraması

Çalışma zamanı yığını güvenli tutmak için ML çerçeveleri ve kütüphanelerini CVE'ler ve kötü amaçlı kodlar açısından sürekli tarayın.

|   #   | Description                                                                                                                           | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 6.2.1 | CI boru hatlarının AI çerçeveleri ve kritik kütüphaneler üzerinde bağımlılık tarayıcıları çalıştırdığını doğrulayın.                  |   1   | D/V  |
| 6.2.2 | Kritik güvenlik açıklarının (CVSS ≥ 7.0) üretim imajlarına geçişi engellediğini doğrulayın.                                           |   1   | D/V  |
| 6.2.3 | Forklanmış veya tedarik edilmiş ML kütüphanelerinde statik kod analizinin çalıştığını doğrulayın.                                     |   2   |  D   |
| 6.2.4 | Çerçeve yükseltme önerilerinin, genel CVE beslemelerine referans veren bir güvenlik etki değerlendirmesi içerdiğini doğrulayın.       |   2   |  V   |
| 6.2.5 | Çalışma zamanı sensörlerinin, imzalı SBOM'dan sapma gösteren beklenmeyen dinamik kütüphane yüklemelerinde uyarı verdiğini doğrulayın. |   3   |  V   |

---

## C6.3 Bağımlılık Sabitleme ve Doğrulama

Her bağımlılığı değiştirilemez özetlere sabitleyin ve aynı, müdahale edilmemiş yapıtları garanti etmek için yapıları yeniden üretin.

|   #   | Description                                                                                                                           | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 6.3.1 | Tüm paket yöneticilerinin kilit dosyaları (lockfile) aracılığıyla sürüm sabitlemesini (version pinning) zorunlu kıldığını doğrulayın. |   1   | D/V  |
| 6.3.2 | Konteyner referanslarında değiştirilebilir etiketler yerine değiştirilemez özetlerin kullanıldığını doğrulayın.                       |   1   | D/V  |
| 6.3.3 | Tekrarlanabilir yapılar kontrollerinin, aynı çıktıları sağlamak için CI çalışmaları arasında hashleri karşılaştırdığını doğrulayın.   |   2   |  D   |
| 6.3.4 | İnceleme izlenebilirliği için yapı belgelerinin 18 ay boyunca saklandığını doğrulayın.                                                |   2   |  V   |
| 6.3.5 | Süresi dolmuş bağımlılıkların, sabitlenmiş sürümleri güncellemek veya çatallamak için otomatik PR'leri tetiklediğini doğrulayın.      |   3   |  D   |

---

## C6.4 Güvenilir Kaynak Uygulaması

Sadece kriptografik olarak doğrulanmış, kuruluş tarafından onaylanmış kaynaklardan artefakt indirmesine izin verin ve diğer her şeyi engelleyin.

|   #   | Description                                                                                                                                            | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 6.4.1 | Model ağırlıklarının, veri setlerinin ve konteynerlerin yalnızca onaylanmış alan adlarından veya dahili kayıt defterlerinden indirildiğini doğrulayın. |   1   | D/V  |
| 6.4.2 | Sigstore/Cosign imzalarının, artefaktlar yerel olarak önbelleğe alınmadan önce yayıncı kimliğini doğruladığını teyit edin.                             |   1   | D/V  |
| 6.4.3 | Eris çıkış vekillerinin, güvenilen kaynak politikası uygulamak için kimlik doğrulaması yapılmamış nesne indirmelerini engellediğini doğrulayın.        |   2   |  D   |
| 6.4.4 | Depo izin listelerinin her madde için iş gerekçesi kanıtı ile birlikte üç ayda bir gözden geçirildiğini doğrulayın.                                    |   2   |  V   |
| 6.4.5 | Politika ihlallerinin eserleri karantinaya almayı ve bağlı boru hattı çalıştırmalarının geri alınmasını tetiklediğini doğrulayın.                      |   3   |  V   |

---

## C6.5 Üçüncü Taraf Veri Kümesi Risk Değerlendirmesi

Dış veri setlerini zehirlenme, önyargı ve yasal uyumluluk açısından değerlendirin ve yaşam döngüleri boyunca izleyin.

|   #   | Description                                                                                                                                   | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 6.5.1 | Dış veri setlerinin zehirlenme risk puanlamasından geçtiğini doğrulayın (örneğin, veri parmak izi çıkarma, aykırı değer tespiti).             |   1   | D/V  |
| 6.5.2 | Veri seti onayından önce önyargı metriklerinin (demografik denklik, eşit fırsat) hesaplandığını doğrulayın.                                   |   1   |  D   |
| 6.5.3 | Veri kümeleri için kaynak ve lisans şartlarının ML-BOM kayıtlarında yakalandığını doğrulayın.                                                 |   2   |  V   |
| 6.5.4 | Barındırılan veri setlerindeki kayma veya bozulmanın periyodik izleme ile tespit edildiğini doğrulayın.                                       |   2   |  V   |
| 6.5.5 | Eğitim öncesinde yasaklanmış içeriğin (telif hakkı, kişisel tanımlanabilir bilgi - PII) otomatik temizleme yoluyla kaldırıldığını doğrulayın. |   3   |  D   |

---

## C6.6 Tedarik Zinciri Saldırısı İzleme

CVE beslemeleri, denetim kaydı analizleri ve kırmızı takım simülasyonları yoluyla tedarik zinciri tehditlerini erken tespit edin.

|   #   | Description                                                                                                                                                                   | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 6.6.1 | CI/CD denetim günlüklerinin, anormal paket çekme işlemleri veya değiştirilmiş derleme adımları için SIEM tespitlerine aktarıldığını doğrulayın.                               |   1   |  V   |
| 6.6.2 | Olay müdahale oyun kitaplarının, ihlal edilmiş modeller veya kütüphaneler için geri alma prosedürlerini içerdiğini doğrulayın.                                                |   2   |  D   |
| 6.6.3 | Tehdit istihbaratı zenginleştirme etiketlerinin, uyarı sınıflandırmasında makine öğrenimi özel göstergelerini (örneğin, model zehirleme IoC’leri) doğruladığını kontrol edin. |   3   |  V   |

---

## C6.7 Model Nesneleri için ML-BOM

Detaylı ML'ye özgü SBOM'lar (ML-BOM'lar) oluşturun ve imzalayın, böylece sonraki kullanıcılar dağıtım anında bileşen bütünlüğünü doğrulayabilir.

|   #   | Description                                                                                                                                 | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 6.7.1 | Her model artefaktının veri setleri, ağırlıklar, hiperparametreler ve lisansları listeleyen bir ML-BOM yayımladığını doğrulayın.            |   1   | D/V  |
| 6.7.2 | ML-BOM oluşturma ve Cosign imzalamanın CI içinde otomatikleştirildiğini ve birleştirme için gerekli olduğunu doğrulayın.                    |   1   | D/V  |
| 6.7.3 | ML‑BOM eksik bileşen meta verisi (hash, lisans) varsa derlemenin başarısız olduğunu doğrulayın.                                             |   2   |  D   |
| 6.7.4 | Aşağıdaki kullanıcıların ML-BOM'ları, dağıtım sırasında ithal edilen modelleri doğrulamak için API üzerinden sorgulayabildiğini doğrulayın. |   2   |  V   |
| 6.7.5 | ML-BOM'ların sürüm kontrolünün yapıldığını ve yetkisiz değişiklikleri tespit etmek için farklarının alındığını doğrulayın.                  |   3   |  V   |

---

## Referanslar

* [ML Supply Chain Compromise – MITRE ATLAS](https://misp-galaxy.org/mitre-atlas-attack-pattern/)
* [Supply‑chain Levels for Software Artifacts (SLSA)](https://slsa.dev/)
* [CycloneDX – Machine Learning Bill of Materials](https://cyclonedx.org/capabilities/mlbom/)
* [What is Data Poisoning? – SentinelOne](https://www.sentinelone.com/cybersecurity-101/cybersecurity/data-poisoning/)
* [Transfer Learning Attack – OWASP ML Security Top 10](https://owasp.org/www-project-machine-learning-security-top-10/docs/ML07_2023-Transfer_Learning_Attack)
* [AI Data Security Best Practices – CISA](https://www.cisa.gov/news-events/cybersecurity-advisories/aa25-142a)
* [Secure CI/CD Supply Chain – Sumo Logic](https://www.sumologic.com/blog/secure-azure-devops-github-supply-chain-attacks)
* [AI & Transparency: Protect ML Models – ReversingLabs](https://www.reversinglabs.com/blog/ai-and-transparency-how-ml-model-creators-can-protect-against-supply-chain-attacks)
* [SBOM Overview – CISA](https://www.cisa.gov/sbom)
* [Training Data Poisoning Guide – Lakera.ai](https://www.lakera.ai/blog/training-data-poisoning)
* [Dependency Pinning for Reproducible Python – Medium](https://medium.com/data-science-collective/guarantee-a-locked-reproducible-environment-with-every-python-run-c0e2bf19fb53)

