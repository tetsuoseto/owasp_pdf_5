# C8 Bellek, Gömütler ve Vektör Veritabanı Güvenliği

## Kontrol Amacı

Gömülü temsiller ve vektör depoları, kullanıcıdan gelen verileri sürekli kabul eden ve bunları Geri Getirme Destekli Üretim (Retrieval-Augmented Generation, RAG) yoluyla model bağlamlarına geri sunan çağdaş yapay zeka sistemlerinin "canlı belleği" olarak işlev görür. Bu bellek düzgün şekilde denetlenmezse, kişisel tanımlanabilir bilgilerin (PII) sızmasına, onay ihlaline veya orijinal metnin tersine mühendislik ile yeniden oluşturulmasına yol açabilir. Bu kontrol ailesinin amacı, bellek boru hatlarını ve vektör veritabanlarını en az ayrıcalık erişimi olacak şekilde güçlendirmek, gömülülerin gizliliği korumasını sağlamak, depolanan vektörlerin süresinin dolmasını veya talep üzerine iptalini mümkün kılmak ve kullanıcı başına belleğin hiçbir zaman başka bir kullanıcının istemlerini veya tamamlamalarını kirletmemesini temin etmektir.

---

## C8.1 Bellek ve RAG İndekslerinde Erişim Kontrolleri

Her vektör koleksiyonunda ince taneli erişim kontrollerini uygulayın.

|   #   | Description                                                                                                                                                             | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 8.1.1 | Kayıt/isim alanı düzeyindeki erişim kontrol kurallarının, kiracı, koleksiyon veya belge etiketi başına ekleme, silme ve sorgulama işlemlerini sınırladığını doğrulayın. |   1   | D/V  |
| 8.1.2 | API anahtarlarının veya JWT'lerin kapsamlı talepler (örneğin, koleksiyon kimlikleri, eylem fiilleri) taşıdığını ve en az üç ayda bir yenilendiğini doğrulayın.          |   1   | D/V  |
| 8.1.3 | Ayrıcalık yükseltme denemelerinin (örneğin, çapraz ad alanı benzerliği sorguları) tespit edilip 5 dakika içinde bir SIEM'e kaydedildiğini doğrulayın.                   |   2   | D/V  |
| 8.1.4 | Vektör veritabanının, denetim kayıtlarında konu tanımlayıcısı, işlem, vektör kimliği/isim alanı, benzerlik eşiği ve sonuç sayısını kaydettiğini doğrulayın.             |   2   | D/V  |
| 8.1.5 | Erişim kararlarının, motorlar yükseltildiğinde veya indeks parçalaması kuralları değiştiğinde atlatma hatalarına karşı test edildiğini doğrulayın.                      |   3   |  V   |

---

## C8.2 Gömme Temizleme ve Doğrulama

Metni vektörleştirmeden önce Kişisel Tanımlanabilir Bilgiler (PII) için ön taramadan geçirin, gizleyin veya takma ad kullanarak anonimleştirin ve isteğe bağlı olarak kalıntı sinyalleri kaldırmak için yerleştirmeleri sonradan işleyin.

|   #   | Description                                                                                                                                                                                                                               | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 8.2.1 | PII ve düzenlemeye tabi verilerin otomatik sınıflandırıcılar aracılığıyla tespit edilip edilmediğini ve gömme öncesinde maskeleme, tokenleştirme veya silme işlemlerinin yapılıp yapılmadığını doğrulayın.                                |   1   | D/V  |
| 8.2.2 | Gömme (embedding) boru hatlarının, dizini zehirleyebilecek yürütülebilir kod veya UTF-8 olmayan eserler içeren girdileri reddettiğini veya karantinaya aldığını doğrulayın.                                                               |   1   |  D   |
| 8.2.3 | Herhangi bir bilinen KİB (Kişisel Identifiable Bilgi) tokenine olan uzaklığı, yapılandırılabilir bir eşik değerin altında kalan cümle gömme vektörlerine yerel veya metrik diferansiyel gizlilik dezenfeksiyonu uygulandığını doğrulayın. |   2   | D/V  |
| 8.2.4 | Temizleme etkinliğinin (örneğin, Kişisel Tanımlanabilir Bilgilerin (PII) kırpılmasının geri çağrılması, anlamsal sapma) en az altı ayda bir karşılaştırma korpuslarına karşı doğrulandığından emin olun.                                  |   2   |  V   |
| 8.2.5 | Temizleme yapılandırmalarının sürüm kontrolünde olduğunu ve değişikliklerin eş değerlendirmesinden geçtiğini doğrulayın.                                                                                                                  |   3   | D/V  |

---

## C8.3 Bellek Süresi Dolumu, İptali ve Silinmesi

GDPR "unutulma hakkı" ve benzeri yasalar zamanında silme gerektirir; bu nedenle, vektör depoları, iptal edilen vektörlerin geri kurtarılamaması veya yeniden indekslenememesi için TTL, kalıcı silme ve mezar taşı mekanizmalarını desteklemelidir.

|   #   | Description                                                                                                                                                                                | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 8.3.1 | Her vektör ve meta veri kaydının, otomatik temizleme işleri tarafından dikkate alınan bir TTL (Yaşam Süresi) veya açık bir saklama etiketi taşıdığını doğrulayın.                          |   1   | D/V  |
| 8.3.2 | Kullanıcı tarafından başlatılan silme taleplerinin vektörleri, meta verileri, önbellek kopyalarını ve türetilmiş indeksleri 30 gün içinde temizlediğini doğrulayın.                        |   1   | D/V  |
| 8.3.3 | Donanım destekliyorsa, mantıksal silme işlemlerinin depolama bloklarının kriptografik olarak imha edilmesiyle veya anahtar kasası anahtarının yok edilmesiyle takip edildiğini doğrulayın. |   2   |  D   |
| 8.3.4 | Süresi dolmuş vektörlerin, süresi dolduktan < 500 ms içinde en yakın komşu arama sonuçlarından hariç tutulduğunu doğrulayın.                                                               |   3   | D/V  |

---

## C8.4 Gömülü Tersine Çevirme ve Sızıntıyı Önleme

Son savunmalar—gürültü üst üste bindirme, projeksiyon ağları, gizlilik-nöron bozulması ve uygulama katmanı şifrelemesi—token düzeyindeki tersine çevirme oranlarını %5'in altına indirebilir.

|   #   | Description                                                                                                                                                                    | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 8.4.1 | Tersine mühendislik, üyelik ve özellik çıkarımı saldırılarını kapsayan resmi bir tehdit modelinin var olduğunu ve yıllık olarak incelendiğini doğrulayın.                      |   1   |  V   |
| 8.4.2 | Uygulama katmanı şifrelemesinin veya aranabilir şifrelemenin, altyapı yöneticileri veya bulut personelinin vektörleri doğrudan okumasını engellediğini doğrulayın.             |   2   | D/V  |
| 8.4.3 | Savunma parametrelerinin (DP için ε, gürültü σ, projeksiyon derecesi k) gizliliği ≥ %99 token koruması ve faydayı ≤ %3 doğruluk kaybı olacak şekilde dengelediğini doğrulayın. |   3   |  V   |
| 8.4.4 | Model güncellemeleri için yayın kapılarının bir parçası olarak tersine çevirme-direnç metriklerinin doğrulandığından ve regresyon bütçelerinin tanımlandığından emin olun.     |   3   | D/V  |

---

## C8.5 Kullanıcıya Özel Bellek İçin Kapsam Yürürlüğe Koyma

Çapraz kiracı sızıntısı hâlâ en önemli RAG riski olarak kalmaktadır: yanlış filtrelenmiş benzerlik sorguları başka bir müşterinin özel belgelerini ortaya çıkarabilir.

|   #   | Description                                                                                                                                                                                               | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 8.5.1 | Her bir sorgunun, LLM isteğine iletilmeden önce kiracı/kullanıcı kimliği tarafından son filtrelemeden geçirildiğini doğrulayın.                                                                           |   1   | D/V  |
| 8.5.2 | Koleksiyon isimlerinin veya ad alanlı kimliklerin, kullanıcı veya kiracı bazında tuzlanarak vektörlerin kapsamlar arasında çakışmasının önlendiğini doğrulayın.                                           |   1   |  D   |
| 8.5.3 | Benzerlik sonuçlarının yapılandırılabilir bir mesafe eşik değerinin üzerinde ancak çağıranın kapsamı dışında olduğunun doğrulanmasını sağlayın ve bu durumun güvenlik uyarılarını tetiklemesini sağlayın. |   2   | D/V  |
| 8.5.4 | Çok kiracılı stres testlerinin, kapsam dışı belgeleri almaya çalışan adversaryal sorguları simüle ettiğini ve sıfır sızıntı gösterdiğini doğrulayın.                                                      |   2   |  V   |
| 8.5.5 | Şifreleme anahtarlarının her kiracı için ayrıldığını doğrulayın ve fiziksel depolama paylaşılmış olsa bile kriptografik izolasyonu sağlayın.                                                              |   3   | D/V  |

---

## C8.6 Gelişmiş Bellek Sistemi Güvenliği

Özel izolasyon ve doğrulama gereksinimleriyle birlikte epizodik, semantik ve çalışma belleği gibi gelişmiş bellek mimarileri için güvenlik kontrolleri.

|   #   | Description                                                                                                                                                                                                                                       | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 8.6.1 | Farklı bellek türlerinin (episodik, semantik, çalışma belleği) rol tabanlı erişim kontrolleri, ayrı şifreleme anahtarları ve her bellek türü için belgelenmiş erişim desenleri ile izole edilmiş güvenlik bağlamlarına sahip olduğunu doğrulayın. |   1   | D/V  |
| 8.6.2 | Bellek pekiştirme süreçlerinin, içerik temizleme, kaynak doğrulama ve saklama öncesi bütünlük kontrolleri yoluyla kötü amaçlı anıların enjekte edilmesini önlemek için güvenlik doğrulamasını içerdiğini doğrulayın.                              |   2   | D/V  |
| 8.6.3 | Bellek getirme sorgularının, sorgu desen analizi, erişim kontrolü uygulaması ve sonuç filtreleme yoluyla yetkisiz bilgi çıkarımını önlemek için doğrulandığından ve temizlendiğinden emin olun.                                                   |   2   | D/V  |
| 8.6.4 | Anahtar silme, çok geçişli üzerine yazma veya doğrulama sertifikaları ile donanım tabanlı güvenli silme kullanarak kriptografik silme garantileriyle hafıza unutma mekanizmalarının hassas bilgileri güvenli bir şekilde sildiğini doğrulayın.    |   3   | D/V  |
| 8.6.5 | Bellek sistemi bütünlüğünün, normal işlemler dışındaki bellek içeriği değişikliklerinde özet kontrolleri, denetim günlükleri ve otomatik uyarılar aracılığıyla yetkisiz değişiklikler veya bozulmalar için sürekli olarak izlendiğini doğrulayın. |   3   | D/V  |

---

## Referanslar

* [Vector database security: Pinecone – IronCore Labs](https://ironcorelabs.com/vectordbs/pinecone-security/)
* [Securing the Backbone of AI: Safeguarding Vector Databases and Embeddings – Privacera](https://privacera.com/blog/securing-the-backbone-of-ai-safeguarding-vector-databases-and-embeddings/)
* [Enhancing Data Security with RBAC of Qdrant Vector Database – AI Advances](https://ai.gopubby.com/enhancing-data-security-with-role-based-access-control-of-qdrant-vector-database-3878769bec83)
* [Mitigating Privacy Risks in LLM Embeddings from Embedding Inversion – arXiv](https://arxiv.org/html/2411.05034v1)
* [DPPN: Detecting and Perturbing Privacy-Sensitive Neurons – OpenReview](https://openreview.net/forum?id=DF5TVzpTW0)
* [Art. 17 GDPR – Right to Erasure](https://gdpr-info.eu/art-17-gdpr/)
* [Sensitive Data in Text Embeddings Is Recoverable – Tonic.ai](https://www.tonic.ai/blog/sensitive-data-in-text-embeddings-is-recoverable)
* [PII Identification and Removal – NVIDIA NeMo Docs](https://docs.nvidia.com/nemo-framework/user-guide/latest/datacuration/personalidentifiableinformationidentificationandremoval.html)
* [De-identifying Sensitive Data – Google Cloud DLP](https://cloud.google.com/sensitive-data-protection/docs/deidentify-sensitive-data)
* [Remove PII from Conversations Using Sensitive Information Filters – AWS Bedrock Guardrails](https://docs.aws.amazon.com/bedrock/latest/userguide/guardrails-sensitive-filters.html)
* [Think Your RAG Is Secure? Think Again – Medium](https://medium.com/%40vijay.poudel1/think-your-rag-is-secure-think-again-heres-how-to-actually-lock-it-down-c4c30e3864e7)
* [Design a Secure Multitenant RAG Inferencing Solution – Microsoft Learn](https://learn.microsoft.com/en-us/azure/architecture/ai-ml/guide/secure-multitenant-rag)
* [Best Practices for Multi-Tenancy RAG with Milvus – Milvus Blog](https://milvus.io/blog/build-multi-tenancy-rag-with-milvus-best-practices-part-one.md)

