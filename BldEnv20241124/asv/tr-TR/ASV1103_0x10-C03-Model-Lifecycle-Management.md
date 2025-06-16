# C3 Model Yaşam Döngüsü Yönetimi ve Değişiklik Kontrolü

## Kontrol Hedefi

Yapay zeka sistemleri, yetkisiz veya güvensiz model değişikliklerinin üretime ulaşmasını engelleyen değişiklik kontrol süreçlerini uygulamalıdır. Bu kontrol, modelin geliştirilmeden dağıtıma ve kullanım dışı bırakılmaya kadar olan tüm yaşam döngüsü boyunca bütünlüğünü sağlar; bu da hızlı olay müdahalesine olanak tanır ve tüm değişiklikler için hesap verebilirliği sürdürür.

Temel Güvenlik Hedefi: Sadece yetkilendirilmiş, doğrulanmış modellerin, bütünlük, izlenebilirlik ve kurtarılabilirlik sağlayan kontrollü süreçler kullanılarak üretime ulaşmasını sağlamaktır.

---

## C3.1 Model Yetkilendirme ve Bütünlüğü

Sadece doğrulanmış bütünlüğe sahip yetkili modeller üretim ortamlarına ulaşır.

|   #   | Description                                                                                                                                                                                          | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 3.1.1 | Tüm model eserlerinin (ağırlıklar, yapılandırmalar, belirteç çözücüler) dağıtımdan önce yetkili taraflarca kriptografik olarak imzalandığını doğrulayın.                                             |   1   | D/V  |
| 3.1.2 | Model bütünlüğünün dağıtım zamanında doğrulandığını ve imza doğrulama hatalarının modelin yüklenmesini engellediğini doğrulayın.                                                                     |   1   | D/V  |
| 3.1.3 | Model köken kayıtlarının, yetkilendiren kuruluşun kimliğini, eğitim verisi özet değerlerini, geçme/kalma durumu ile doğrulama test sonuçlarını ve oluşturulma zaman damgasını içerdiğini doğrulayın. |   2   | D/V  |
| 3.1.4 | Tüm model artefaktlarının belgelenmiş kriterlerle hangi sürüm bileşeninin ne zaman artırılacağını belirten anlamsal sürümleme (MAJOR.MINOR.PATCH) kullandığını doğrulayın.                           |   2   | D/V  |
| 3.1.5 | Bağımlılık takibinin, tüm tüketici sistemlerin hızlı bir şekilde tanımlanmasını sağlayan gerçek zamanlı bir envanter tuttuğunu doğrulayın.                                                           |   2   |  V   |

---

## C3.2 Model Doğrulama ve Test Etme

Modeller, dağıtımdan önce tanımlanmış güvenlik ve emniyet doğrulamalarını geçmelidir.

|   #   | Description                                                                                                                                                                                                                        | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 3.2.1 | Modellerin dağıtımdan önce, önceden kararlaştırılmış organizasyonel geçme/kalma eşiklerini içeren girdi doğrulaması, çıktı temizliği ve güvenlik değerlendirmelerini kapsayan otomatik güvenlik testlerinden geçtiğini doğrulayın. |   1   | D/V  |
| 3.2.2 | Doğrulama hatalarının, önceden belirlenmiş yetkili personelin yazılı iş gerekçeleriyle açıkça onayladığı durumlar dışında model dağıtımını otomatik olarak engellediğini doğrulayın.                                               |   1   | D/V  |
| 3.2.3 | Test sonuçlarının kriptografik olarak imzalandığını ve doğrulanan belirli model sürümü hash'ine değiştirilemez şekilde bağlı olduğunu doğrulayın.                                                                                  |   2   |  V   |
| 3.2.4 | Acil durum dağıtımlarının, önceden belirlenmiş zaman dilimleri içinde, önceden atanmış bir güvenlik yetkilisinden belgeye dayalı güvenlik risk değerlendirmesi ve onay gerektirdiğini doğrulayın.                                  |   2   | D/V  |

---

## C3.3 Kontrollü Dağıtım ve Geri Alma

Model dağıtımları kontrol edilmeli, izlenmeli ve geri alınabilir olmalıdır.

|   #   | Description                                                                                                                                                                                                                                                           | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 3.3.1 | Üretim dağıtımlarının, önceden kararlaştırılmış hata oranları, gecikme eşikleri veya güvenlik uyarı kriterlerine dayalı otomatik geri alma tetikleyicileri ile kademeli dağıtım mekanizmalarını (kanarya dağıtımları, mavi-yeşil dağıtımlar) uyguladığını doğrulayın. |   1   |  D   |
| 3.3.2 | Rollback yeteneklerinin, önceden tanımlanmış organizasyonel zaman pencereleri içinde modelin tamamını (ağırlıklar, konfigürasyonlar, bağımlılıklar) atomik olarak geri yüklediğini doğrulayın.                                                                        |   1   | D/V  |
| 3.3.3 | Dağıtım süreçlerinin, model etkinleştirilmeden önce kriptografik imzaları doğruladığını ve bütünlük kontrolleri yaptıktan sonra herhangi bir uyuşmazlık durumunda dağıtımı başarısız kıldığını doğrulayın.                                                            |   2   | D/V  |
| 3.3.4 | Acil durum model kapatma yeteneklerinin, otomatik devre kesiciler veya manuel durdurma anahtarları aracılığıyla önceden tanımlanmış yanıt süreleri içinde model uç noktalarını devre dışı bırakabildiğini doğrulayın.                                                 |   2   | D/V  |
| 3.3.5 | Geri alma (rollback) eserlerinin (önceki model sürümleri, yapılandırmalar, bağımlılıklar) organizasyon politikalarına uygun olarak, olay müdahalesi için değiştirilemez (immutable) depolama ile saklandığını doğrulayın.                                             |   2   |  V   |

---

## C3.4 Değişiklik Sorumluluğu ve Denetimi

Tüm model yaşam döngüsü değişiklikleri izlenebilir ve denetlenebilir olmalıdır.

|   #   | Description                                                                                                                                                                                                                                                | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 3.4.1 | Tüm model değişikliklerinin (dağıtım, yapılandırma, emeklilik) zaman damgası, doğrulanmış bir aktör kimliği, bir değişiklik türü ve öncesi/sonrası durumlarını içeren değiştirilemez denetim kayıtları oluşturduğunu doğrulayın.                           |   1   |  V   |
| 3.4.2 | Denetim günlüğü erişiminin uygun yetkilendirme gerektirdiğini ve tüm erişim denemelerinin kullanıcı kimliği ve zaman damgası ile kaydedildiğini doğrulayın.                                                                                                |   2   | D/V  |
| 3.4.3 | Prompt şablonlarının ve sistem mesajlarının, dağıtımdan önce zorunlu kod incelemesi ve belirlenmiş inceleyicilerden onay almayı gerektiren git depolarında sürüm kontrolünün yapıldığını doğrulayın.                                                       |   2   | D/V  |
| 3.4.4 | Denetim kayıtlarının, tutma süresi içindeki herhangi bir zamandaki model durumunun tam olarak yeniden oluşturulmasını sağlamak için yeterli ayrıntıyı (model karma değerleri, yapılandırma anlık görüntüleri, bağımlılık sürümleri) içerdiğini doğrulayın. |   2   |  V   |

---

## C3.5 Güvenli Yazılım Geliştirme Uygulamaları

Model geliştirme ve eğitim süreçleri, ihlalleri önlemek için güvenli uygulamalara uygun olarak yürütülmelidir.

|   #   | Description                                                                                                                                                                                                       | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 3.5.1 | Model geliştirme, test ve üretim ortamlarının fiziksel veya mantıksal olarak ayrıldığını doğrulayın. Ortak altyapıları yoktur, ayrı erişim kontrolleri bulunur ve veri depoları izole edilmiştir.                 |   1   |  D   |
| 3.5.2 | Model eğitimi ve ince ayar işlemlerinin, kontrollü ağ erişimi olan izole ortamlarda gerçekleştirildiğini doğrulayın.                                                                                              |   1   |  D   |
| 3.5.3 | Model geliştirmede kullanılmadan önce, eğitim veri kaynaklarının bütünlük kontrolleriyle doğrulanıp güvenilir kaynaklar aracılığıyla belgelenmiş sahiplik zinciri ile kimlik doğrulamasının yapılmasını sağlayın. |   1   | D/V  |
| 3.5.4 | Model geliştirme artefaktlarının (hiperparametreler, eğitim betikleri, yapılandırma dosyaları) sürüm kontrolünde saklandığını ve eğitimde kullanılmadan önce eş düzey inceleme onayı gerektirdiğini doğrulayın.   |   2   |  D   |

---

## C3.6 Model Emekliye Ayırma ve Hizmet Dışı Bırakma

Modeller, artık ihtiyaç kalmadığında veya güvenlik sorunları tespit edildiğinde güvenli bir şekilde kullanımdan kaldırılmalıdır.

|   #   | Description                                                                                                                                                                                                                       | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 3.6.1 | Model emeklilik süreçlerinin, bağımlılık grafiklerini otomatik olarak taradığını, tüm tüketici sistemleri tespit ettiğini ve kullanımdan kaldırmadan önce önceden kararlaştırılmış bildirim sürelerini sağladığını doğrulayın.    |   1   |  D   |
| 3.6.2 | Emekli model artefaktlarının, doğrulanmış imha sertifikaları ile belgelenmiş veri saklama politikalarına uygun olarak kriptografik silme veya çok geçişli üzerine yazma yöntemleriyle güvenli bir şekilde silindiğini doğrulayın. |   1   | D/V  |
| 3.6.3 | Model emeklilik olaylarının zaman damgası ve aktör kimliği ile kaydedildiğini ve model imzalarının yeniden kullanımını önlemek için iptal edildiğini doğrulayın.                                                                  |   2   |  V   |
| 3.6.4 | Acil model emekliliğinin, kritik güvenlik açıkları keşfedildiğinde otomatik kapatma anahtarları aracılığıyla önceden belirlenmiş acil müdahale süreleri içinde model erişimini devre dışı bırakabildiğini doğrulayın.             |   2   | D/V  |

---

## Referanslar

* [MLOps Principles](https://ml-ops.org/content/mlops-principles)
* [Securing AI/ML Ops – Cisco.com](https://sec.cloudapps.cisco.com/security/center/resources/SecuringAIMLOps)
* [Audit logs security: cryptographically signed tamper-proof logs](https://www.cossacklabs.com/blog/audit-logs-security/)
* [Machine Learning Model Versioning: Top Tools & Best Practices](https://lakefs.io/blog/model-versioning/)
* [AI Hygiene Starts with Models and Data Loaders – SEI Blog](https://insights.sei.cmu.edu/documents/6190/AI-Hygiene-Starts-with-Models-and-Data-Loaders_1G0KTRh.pdf)
* [How to handle versioning and rollback of a deployed ML model?](https://learn.microsoft.com/en-au/answers/questions/1845378/how-to-handle-versioning-and-rollback-of-a-deploye)
* [Reinforcement fine-tuning – OpenAI API](https://platform.openai.com/docs/guides/reinforcement-fine-tuning)
* [Auditing Machine Learning models: Governance, Data Security and …](https://www.linkedin.com/pulse/auditing-machine-learning-models-governance-data-security-negrete-yn81f)
* [Adversarial Training to Improve Model Robustness](https://medium.com/%40amit25173/adversarial-training-to-improve-model-robustness-5e285b516713)
* [What is AI adversarial robustness? – IBM Research](https://research.ibm.com/blog/securing-ai-workflows-with-adversarial-robustness)
* [Exploring Data Provenance: Ensuring Data Integrity and Authenticity](https://www.astera.com/type/blog/data-provenance/)
* [MITRE ATLAS](https://atlas.mitre.org/)
* [AWS Prescriptive Guidance – Best practices for retiring applications …](https://docs.aws.amazon.com/pdfs/prescriptive-guidance/latest/migration-app-retirement-best-practices/migration-app-retirement-best-practices.pdf)

