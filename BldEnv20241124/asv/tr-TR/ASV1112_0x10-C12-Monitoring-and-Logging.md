# C12 İzleme, Kayıt Tutma ve Anomali Tespiti

## Kontrol Hedefi

Bu bölüm, tehditlerin tespit edilmesi, sınıflandırılması ve öğrenilmesi için modelin ve diğer AI bileşenlerinin ne gördüğü, ne yaptığı ve ne döndürdüğü hakkında gerçek zamanlı ve adli görünürlük sağlanmasına yönelik gereksinimleri sunar.

## C12.1 İstek ve Yanıt Kaydı

|   #    | Description                                                                                                                                                                                                                                                                                   | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 12.1.1 | Tüm kullanıcı istemlerinin ve model yanıtlarının uygun meta verilerle (örneğin, zaman damgası, kullanıcı kimliği, oturum kimliği, model sürümü) kaydedildiğini doğrulayın.                                                                                                                    |   1   | D/V  |
| 12.1.2 | Günlüklerin uygun saklama politikaları ve yedekleme prosedürleri ile güvenli, erişim kontrollü depolama alanlarında saklandığını doğrulayın.                                                                                                                                                  |   1   | D/V  |
| 12.1.3 | Günlüklerde bulunan hassas bilgileri korumak için günlük depolama sistemlerinin hem bekleme halinde hem de iletim sırasında şifreleme uyguladığını doğrulayın.                                                                                                                                |   1   | D/V  |
| 12.1.4 | İsteklerde ve çıktılarda yer alan hassas verilerin, kayıttan önce otomatik olarak sansürlendiği veya maskelendiğini doğrulayın; bu işlem, Kişisel Tanımlanabilir Bilgiler (PII), kimlik bilgileri ve özel bilgilere yönelik yapılandırılabilir sansürleme kurallarıyla gerçekleştirilmelidir. |   1   | D/V  |
| 12.1.5 | Politika kararlarının ve güvenlik filtreleme işlemlerinin, içerik denetim sistemlerinin denetimi ve hata ayıklaması için yeterli ayrıntıyla kaydedildiğini doğrulayın.                                                                                                                        |   2   | D/V  |
| 12.1.6 | Günlük bütünlüğünün, örneğin kriptografik imzalar veya sadece yazılabilen depolama ile korunduğunu doğrulayın.                                                                                                                                                                                |   2   | D/V  |

---

## C12.2 Suistimal Tespiti ve Uyarı Sistemi

|   #    | Description                                                                                                                                                                                                        | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 12.2.1 | Sistemin, imza tabanlı tespit kullanarak bilinen jailbreak kalıplarını, istem enjekte etme girişimlerini ve düşmanca girdileri algılayıp uyarı verdiğini doğrulayın.                                               |   1   | D/V  |
| 12.2.2 | Sistemin, standart günlük formatları ve protokolleri kullanarak mevcut Güvenlik Bilgisi ve Olay Yönetimi (SIEM) platformlarıyla entegre olduğunu doğrulayın.                                                       |   1   | D/V  |
| 12.2.3 | Zenginleştirilmiş güvenlik olaylarının model tanımlayıcıları, güven skoru ve güvenlik filtresi kararları gibi yapay zekaya özgü bağlamları içerdiğini doğrulayın.                                                  |   2   | D/V  |
| 12.2.4 | Davranışsal anomali tespitinin alışılmadık konuşma kalıplarını, aşırı tekrar denemelerini veya sistematik sorgulama davranışlarını tespit ettiğini doğrulayın.                                                     |   2   | D/V  |
| 12.2.5 | Gerçek zamanlı uyarı mekanizmalarının, potansiyel politika ihlalleri veya saldırı girişimleri tespit edildiğinde güvenlik ekiplerini bilgilendirdiğini doğrulayın.                                                 |   2   | D/V  |
| 12.2.6 | Yapay zeka özel tehdit desenlerini tespit etmek için koordineli jailbreak girişimleri, istem enjekte etme kampanyaları ve model çıkarma saldırıları dahil olmak üzere özel kuralların dahil edildiğini doğrulayın. |   2   | D/V  |
| 12.2.7 | Otomatik olay müdahale iş akışlarının, ele geçirilmiş modelleri izole edebildiğini, kötü niyetli kullanıcıları engellediğini ve kritik güvenlik olaylarını yükseltebildiğini doğrulayın.                           |   3   | D/V  |

---

## C12.3 Model Sürüklenme Tespiti

|   #    | Description                                                                                                                                                                                   | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 12.3.1 | Sistemin, model sürümleri ve zaman dilimleri boyunca doğruluk, güven skorları, gecikme süresi ve hata oranları gibi temel performans metriklerini takip ettiğini doğrulayın.                  |   1   | D/V  |
| 12.3.2 | Performans metrikleri önceden belirlenmiş bozulma eşiklerini aştığında veya baz çizgilerden önemli ölçüde sapma gösterdiğinde otomatik uyarı tetikleyicilerinin devreye girdiğini doğrulayın. |   2   | D/V  |
| 12.3.3 | Halüsinasyon tespiti izleyicilerinin, model çıktılarında gerçeklere aykırı, tutarsız veya uydurma bilgiler bulunduğunda bu durumları tespit edip işaretlediğini doğrulayın.                   |   2   | D/V  |

---

## C12.4 Performans ve Davranış Telemetrisi

|   #    | Description                                                                                                                                                    | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 12.4.1 | İşlem gecikmesi, token tüketimi, bellek kullanımı ve verimlilik gibi operasyonel metriklerin sürekli olarak toplandığını ve izlendiğini doğrulayın.            |   1   | D/V  |
| 12.4.2 | Başarı ve başarısızlık oranlarının, hata türlerinin ve bunların temel nedenlerinin kategorize edilerek takip edildiğini doğrulayın.                            |   1   | D/V  |
| 12.4.3 | Kaynak kullanım izleme işlevinin GPU/CPU kullanımı, bellek tüketimi ve depolama gereksinimlerini içerdiğini ve eşik ihlallerinde uyarı verilmesini doğrulayın. |   2   | D/V  |

---

## C12.5 Yapay Zeka Olay Müdahale Planlaması ve Yürütülmesi

|   #    | Description                                                                                                                                                                             | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 12.5.1 | Olay müdahale planlarının, model ihlali, veri zehirlenmesi ve düşmanca saldırılar dahil olmak üzere yapay zekâ ile ilgili güvenlik olaylarını özellikle ele aldığını doğrulayın.        |   1   | D/V  |
| 12.5.2 | Olay müdahale ekiplerinin, model davranışı ve saldırı vektörlerini araştırmak için yapay zekâya özgü adli araçlara ve uzmanlığa erişimi olduğundan emin olun.                           |   2   | D/V  |
| 12.5.3 | Olay sonrası analizde model yeniden eğitimi hususlarının, güvenlik filtresi güncellemelerinin ve edinilen derslerin güvenlik kontrollerine entegrasyonunun dahil edildiğini doğrulayın. |   3   | D/V  |

---

## C12.5 AI Performans Düşüşü Tespiti

Yapay zeka modeli performansındaki ve kalitesindeki zamanla meydana gelen bozulmaları izleyin ve tespit edin.

|   #    | Description                                                                                                                                             | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 12.5.1 | Model doğruluğunun, kesinliğinin, geri çağırma oranının ve F1 skorlarının sürekli olarak izlenip temel eşik değerlerle karşılaştırıldığından emin olun. |   1   | D/V  |
| 12.5.2 | Veri sürüklenmesi tespiti, model performansını etkileyebilecek giriş dağılımı değişikliklerini izlediğini doğrulayın.                                   |   1   | D/V  |
| 12.5.3 | Konsept kayması tespitinin, girdiler ile beklenen çıktılar arasındaki ilişkideki değişiklikleri belirlediğini doğrulayın.                               |   2   | D/V  |
| 12.5.4 | Performans bozulmasının otomatik uyarıları tetiklediğini ve model yeniden eğitimi veya değiştirme iş akışlarını başlattığını doğrulayın.                |   2   | D/V  |
| 12.5.5 | Performans düşüşlerini veri değişiklikleri, altyapı sorunları veya dış etkenlerle ilişkilendiren bozulma kök neden analizinin doğrulanması.             |   3   |  V   |

---

## C12.6 DAG Görselleştirmesi ve İş Akışı Güvenliği

İş akışı görselleştirme sistemlerini bilgi sızıntısı ve manipülasyon saldırılarından koruyun.

|   #    | Description                                                                                                                                                                                             | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 12.6.1 | DAG görselleştirme verilerinin depolama veya iletim öncesinde hassas bilgileri kaldıracak şekilde temizlendiğini doğrulayın.                                                                            |   1   | D/V  |
| 12.6.2 | İş akışı görselleştirme erişim kontrollerinin sadece yetkili kullanıcıların ajan karar yollarını ve mantık izlerini görüntüleyebildiğini doğrulayın.                                                    |   1   | D/V  |
| 12.6.3 | DAG veri bütünlüğünün kriptografik imzalar ve müdahale tespitli depolama mekanizmaları aracılığıyla korunduğunu doğrulayın.                                                                             |   2   | D/V  |
| 12.6.4 | İş akışı görselleştirme sistemlerinin, özel olarak hazırlanmış düğüm veya kenar verileri aracılığıyla gerçekleştirilen enjeksiyon saldırılarını önlemek için giriş doğrulaması uyguladığını doğrulayın. |   2   | D/V  |
| 12.6.5 | Gerçek zamanlı DAG güncellemelerinin hizmet reddi saldırılarını önlemek amacıyla hız sınırlandırmasının yapıldığını ve doğrulandığını kontrol edin.                                                     |   3   | D/V  |

---

## C12.7 Proaktif Güvenlik Davranışı İzleme

Güvenlik tehditlerinin proaktif ajan davranışı analizi yoluyla tespiti ve önlenmesi.

|   #    | Description                                                                                                                           | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 12.7.1 | Proaktif ajan davranışlarının yürütülmeden önce risk değerlendirmesi entegrasyonu ile güvenlik doğrulamasının yapıldığını doğrulayın. |   1   | D/V  |
| 12.7.2 | Otonom girişim tetikleyicilerinin güvenlik bağlamı değerlendirmesi ve tehdit ortamı analizini içerdiğini doğrulayın.                  |   2   | D/V  |
| 12.7.3 | Proaktif davranış kalıplarının olası güvenlik etkileri ve istenmeyen sonuçlar açısından analiz edildiğini doğrulayın.                 |   2   | D/V  |
| 12.7.4 | Güvenlik açısından kritik proaktif eylemlerin, denetim izleriyle birlikte açık onay zincirleri gerektirdiğini doğrulayın.             |   3   | D/V  |
| 12.7.5 | Davranış anomali tespiti, proaktif ajan desenlerindeki sapmaları tespit ederek olası güvenlik ihlallerini belirlediğini doğrulayın.   |   3   | D/V  |

---

## Referanslar

* [NIST AI Risk Management Framework 1.0 - Manage 4.1 and 4.3](https://nvlpubs.nist.gov/nistpubs/ai/nist.ai.100-1.pdf)
* [ISO/IEC 42001:2023 — AI Management Systems Requirements - Annex B 6.2.6](https://www.iso.org/standard/81230.html)
* [EU AI Act — Article 12, 13, 16 and 19 on Logging and Record-keeping](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX%3A32024R1689)

