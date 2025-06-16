# Ek D: Yapay Zeka Destekli Güvenli Kodlama Yönetişimi ve Doğrulama

## Amaç

Bu bölüm, yazılım geliştirme sırasında AI destekli kodlama araçlarının güvenli ve etkili kullanımını sağlamak için temel kurumsal kontrolleri tanımlar ve SDLC boyunca güvenlik ve izlenebilirliği garanti eder.

---

## AD.1 Yapay Zeka Destekli Güvenli Kodlama İş Akışı

Yapay zeka araçlarını, mevcut güvenlik kapılarını zayıflatmadan, kuruluşun güvenli yazılım geliştirme yaşam döngüsüne (SSDLC) entegre edin.

|   #    | Description                                                                                                                                                                                                  | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| AD.1.1 | Belgelendirilmiş bir iş akışının, yapay zeka araçlarının kodu ne zaman ve nasıl oluşturabileceğini, yeniden düzenleyebileceğini veya inceleyebileceğini açıkladığını doğrulayın.                             |   1   | D/V  |
| AD.1.2 | İş akışının her SSDLC aşamasına (tasarım, uygulama, kod incelemesi, test, dağıtım) uygun olduğunu doğrulayın.                                                                                                |   2   |  D   |
| AD.1.3 | AI tarafından üretilen kod üzerinde metriklerin (örneğin, zaafiyet yoğunluğu, ortalama tespit süresi) toplandığını ve yalnızca insan tarafından oluşturulan temel değerlerle karşılaştırıldığını doğrulayın. |   3   | D/V  |

---

## AD.2 AI Aracı Nitelendirme ve Tehdit Modelleme

Yapay zeka kodlama araçlarının benimsenmeden önce güvenlik yetenekleri, risk ve tedarik zinciri etkisi açısından değerlendirilmesini sağlayın.

|   #    | Description                                                                                                                                                                                  | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| AD.2.1 | Her AI aracı için bir tehdit modelinin kötüye kullanım, model-inversiyonu, veri sızıntısı ve bağımlılık zinciri risklerini tanımladığını doğrulayın.                                         |   1   | D/V  |
| AD.2.2 | Araç değerlendirmelerinin, herhangi bir yerel bileşenin statik/dinamik analizini ve SaaS uç noktalarının (TLS, kimlik doğrulama/izin, günlük kaydı) değerlendirmesini içerdiğini doğrulayın. |   2   |  D   |
| AD.2.3 | Değerlendirmelerin tanınmış bir çerçeveye uygun olduğunu ve büyük sürüm değişikliklerinden sonra tekrar yapıldığını doğrulayın.                                                              |   3   | D/V  |

---

## AD.3 Güvenli İstem ve Bağlam Yönetimi

AI modelleri için istemler veya bağlamlar oluşturulurken gizli bilgiler, özel kodlar ve kişisel verilerin sızmasını önleyin.

|   #    | Description                                                                                                                                                                     | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| AD.3.1 | Yazılı rehberlikte, istemlerde gizli bilgiler, kimlik bilgileri veya sınıflandırılmış verilerin gönderilmesinin yasaklandığını doğrulayın.                                      |   1   | D/V  |
| AD.3.2 | Teknik kontrollerin (istemci tarafı sansürleme, onaylanmış bağlam filtreleri) hassas unsurları otomatik olarak kaldırdığını doğrulayın.                                         |   2   |  D   |
| AD.3.3 | İsteklerin ve yanıtların tokenize edildiğini, iletim sırasında ve depolanırken şifrelendiğini ve saklama sürelerinin veri sınıflandırma politikasına uygun olduğunu doğrulayın. |   3   | D/V  |

---

## AD.4 Yapay Zeka ile Üretilen Kodun Doğrulanması

AI çıktısı tarafından tanıtılan güvenlik açıklarını, kod birleştirilmadan veya dağıtılmadan önce tespit edin ve giderin.

|   #    | Description                                                                                                                                                                                       | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| AD.4.1 | AI tarafından üretilen kodun her zaman insan kod incelemesine tabi tutulduğunu doğrulayın.                                                                                                        |   1   | D/V  |
| AD.4.2 | Otomatik tarayıcıların (SAST/IAST/DAST) her yapay zeka tarafından oluşturulan kod içeren çekme isteğinde çalıştığını doğrulayın ve kritik bulgular tespit edildiğinde birleştirmeleri engelleyin. |   2   |  D   |
| AD.4.3 | Farklılaştırılmış fuzz testi veya özellik tabanlı testlerin, güvenlik açısından kritik davranışları (örneğin, girdi doğrulama, yetkilendirme mantığı) kanıtladığını doğrulayın.                   |   3   | D/V  |

---

## AD.5 Kod Önerilerinin Açıklanabilirliği ve İzlenebilirliği

Denetçilere ve geliştiricilere, neden bir öneride bulunulduğuna ve önerinin nasıl geliştiğine dair bilgi sağlayın.

|   #    | Description                                                                                                                                                                                       | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| AD.5.1 | İstem/yanıt çiftlerinin commit kimlikleri ile kaydedildiğini doğrulayın.                                                                                                                          |   1   | D/V  |
| AD.5.2 | Geliştiricilerin, bir öneriyi destekleyen model atıflarını (eğitim parçacıkları, belgelemeler) görüntüleyebildiklerini doğrulayın.                                                                |   2   |  D   |
| AD.5.3 | Açıklanabilirlik raporlarının tasarım eserleriyle birlikte saklandığını ve ISO/IEC 42001 izlenebilirlik ilkelerini karşılayacak şekilde güvenlik incelemelerinde referans verildiğini doğrulayın. |   3   | D/V  |

---

## AD.6 Sürekli Geri Bildirim ve Model İnce Ayarı

Negatif sapmayı önlerken model güvenlik performansını zaman içinde iyileştirin.

|   #    | Description                                                                                                                                                                                                    | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| AD.6.1 | Geliştiricilerin güvensiz veya uyumsuz önerileri işaretleyebildiğini ve bu işaretlerin takip edildiğini doğrulayın.                                                                                            |   1   | D/V  |
| AD.6.2 | Toplanan geri bildirimin, doğrulanmış güvenli kodlama korpusları (örneğin, OWASP Cheat Sheets) ile periyodik ince ayar veya doğrulanmış veri kullanılarak artırılmış üretim için bilgilendirdiğini doğrulayın. |   2   |  D   |
| AD.6.3 | Kapatılmış döngü değerlendirme sistemi, her ince ayardan sonra regresyon testlerini çalıştırdığını doğrulayın; güvenlik metrikleri, dağıtımdan önce önceki temel değerleri karşılamalı veya aşmalıdır.         |   3   | D/V  |

---

### Kaynaklar

* [NIST AI Risk Management Framework 1.0](https://nvlpubs.nist.gov/nistpubs/ai/nist.ai.100-1.pdf)
* [ISO/IEC 42001:2023 — AI Management Systems Requirements](https://www.iso.org/standard/81230.html)
* [OWASP Secure Coding Practices — Quick Reference Guide](https://owasp.org/www-project-secure-coding-practices-quick-reference-guide/)

