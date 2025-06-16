# 10 Adversarial Dayanıklılık ve Gizlilik Savunması

## Kontrol Amacı

AI modellerinin kaçınma, çıkarım, çıkarma veya zehirleme saldırılarıyla karşılaştıklarında güvenilir, gizliliği koruyan ve kötüye kullanıma dayanıklı olmalarını sağlayın.

---

## 10.1 Model Hizalaması ve Güvenliği

Zararlı veya politika ihlali oluşturan çıktılara karşı koruma sağlayın.

|   #    | Description                                                                                                                                                                        | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 10.1.1 | Bir uyum test setinin (kırmızı takım istemleri, hapishaneden kaçma testleri, yasaklanmış içerik) sürüm kontrolünün yapıldığını ve her model sürümünde çalıştırıldığını doğrulayın. |   1   | D/V  |
| 10.1.2 | Reddedilme ve güvenli tamamlama koruma önlemlerinin uygulandığını doğrulayın.                                                                                                      |   1   |  D   |
| 10.1.3 | Otomatik bir değerlendiricinin zararlı içerik oranını ölçtüğünü ve belirlenen bir eşik değerinin üzerindeki gerilemeleri işaretlediğini doğrulayın.                                |   2   | D/V  |
| 10.1.4 | Karşı hapishane kaçış eğitimlerinin belgelenmiş ve tekrarlanabilir olduğunu doğrulayın.                                                                                            |   2   |  D   |
| 10.1.5 | Resmi politika uyumluluğu kanıtlarının veya sertifikalı izleme işleminin kritik alanları kapsadığını doğrulayın.                                                                   |   3   |  V   |

---

## 10.2 Düşmanca Örnek Sertleştirme

Manipüle edilmiş girdilere karşı dayanıklılığı artırın. Sağlam düşmanca eğitim ve kıyaslama puanlaması şu anda en iyi uygulamalardır.

|   #    | Description                                                                                                                            | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 10.2.1 | Proje depolarının tekrarlanabilir tohumlarla birlikte adversaryal eğitim yapılandırmalarını içerdiğini doğrulayın.                     |   1   |  D   |
| 10.2.2 | Üretim hatlarında düşmanca örnek tespitin engelleme uyarıları oluşturduğunu doğrulayın.                                                |   2   | D/V  |
| 10.2.4 | Sertifikalı dayanıklılık kanıtlarının veya aralık-sınır sertifikalarının en azından en kritik üst sınıfları kapsadığını doğrulayın.    |   3   |  V   |
| 10.2.5 | Regresyon testlerinin, ölçülebilir bir dayanıklılık kaybı olmadığını doğrulamak için uyarlanabilir saldırılar kullandığını doğrulayın. |   3   |  V   |

---

## 10.3 Üyelik Çıkarımı Önleme

Bir kaydın eğitim verilerinde olup olmadığını belirleme yeteneğini sınırlayın. Farklı gizlilik ve güven skorunu gizleme, bilinen en etkili savunmalar olmaya devam etmektedir.

|   #    | Description                                                                                                                    | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 10.3.1 | Sorgu başına entropi düzenlemesinin veya sıcaklık ölçeklemesinin aşırı güvenli tahminleri azalttığını doğrulayın.              |   1   |  D   |
| 10.3.2 | Eğitimde, hassas veri setleri için ε-sınırlı farklı gizlilikli optimizasyonun kullanıldığını doğrulayın.                       |   2   |  D   |
| 10.3.3 | Saldırı simülasyonlarının (gölge model veya kara kutu) ayrılmış veriler üzerinde saldırı AUC'sinin ≤ 0,60 olduğunu doğrulayın. |   2   |  V   |

---

## 10.4 Model-Tersine Çevirme Direnci

Özel özniteliklerin yeniden yapılandırılmasını önleyin. Son anketler, çıktı kısaltma ve DP garantilerini pratik savunmalar olarak vurgulamaktadır.

|   #    | Description                                                                                                             | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 10.4.1 | Hassas özelliklerin asla doğrudan çıktılanmadığını doğrulayın; gerektiğinde kovalar veya tek yönlü dönüşümler kullanın. |   1   |  D   |
| 10.4.2 | Aynı kullanıcıdan gelen tekrarlanan uyarlanabilir sorguların sorgu oranı limitleriyle sınırlandırıldığını doğrulayın.   |   1   | D/V  |
| 10.4.3 | Modelin gizliliği koruyan gürültü ile eğitildiğini doğrulayın.                                                          |   2   |  D   |

---

## 10.5 Model Çıkarımı Savunması

Yetkisiz klonlamayı tespit edin ve caydırın. Su işareti ekleme ve sorgu deseni analizi önerilir.

|   #    | Description                                                                                                                            | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 10.5.1 | Çıkarım geçitlerinin, modelin ezberleme eşiğine göre ayarlanmış global ve API anahtarı başına oran limitlerini zorladığını doğrulayın. |   1   |  D   |
| 10.5.2 | Sorgu-entropisi ve girdi-çoğulluk istatistiklerinin otomatik çıkarım algılayıcısına veri sağladığını doğrulayın.                       |   2   | D/V  |
| 10.5.3 | Kırılgan veya olasılıksal su işaretlerinin, şüpheli klon üzerinde ≤ 1.000 sorgu ile p < 0,01 düzeyinde kanıtlanabileceğini doğrulayın. |   2   |  V   |
| 10.5.4 | Filigran anahtarlarının ve tetikleyici setlerin bir donanım güvenlik modülünde saklandığını ve her yıl döndürüldüğünü doğrulayın.      |   3   |  D   |
| 10.5.5 | Extraction-alert olaylarının hatalı sorguları içerdiğini ve olay müdahale oyun kitaplarıyla entegre edildiğini doğrulayın.             |   3   |  V   |

---

## 10.6 Çıkarım Zamanı Zehirli Veri Tespiti

Geri kapılı veya zehirlenmiş girdileri tanımlayın ve etkisiz hale getirin.

|   #    | Description                                                                                                                             | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 10.6.1 | Model çıkarımı öncesinde, girdilerin bir anomali algılayıcısından (örneğin, STRIP, tutarlılık skorlama) geçtiğini doğrulayın.           |   1   |  D   |
| 10.6.2 | Dedektör eşiklerinin, yanlış pozitif oranını %5’in altında tutmak için temiz/zehirlenmiş doğrulama setlerinde ayarlandığını doğrulayın. |   1   |  V   |
| 10.6.3 | Zehirli olarak işaretlenen girdilerin yumuşak engelleme ve insan inceleme iş akışlarını tetiklediğini doğrulayın.                       |   2   |  D   |
| 10.6.4 | Dedektörlerin, uyarlanabilir ve tetikleyicisiz arka kapı saldırılarıyla stres testine tabi tutulduğunu doğrulayın.                      |   2   |  V   |
| 10.6.5 | Tespit etkinliği metriklerinin kaydedildiğini ve periyodik olarak güncel tehdit istihbaratı ile yeniden değerlendirildiğini doğrulayın. |   3   |  D   |

---

## 10.7 Dinamik Güvenlik Politikası Uyarlaması

Tehdit istihbaratı ve davranış analizi temelinde gerçek zamanlı güvenlik politikası güncellemeleri.

|   #    | Description                                                                                                                                                      | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 10.7.1 | Güvenlik politikalarının, politika sürüm bütünlüğünü koruyarak, ajan yeniden başlatılmadan dinamik olarak güncellenebileceğini doğrulayın.                       |   1   | D/V  |
| 10.7.2 | Politika güncellemelerinin yetkili güvenlik personeli tarafından kriptografik olarak imzalandığını ve uygulanmadan önce doğrulandığını kontrol edin.             |   2   | D/V  |
| 10.7.3 | Dinamik politika değişikliklerinin gerekçelendirme, onay zincirleri ve geri alma prosedürleri dahil olmak üzere tam denetim izleriyle kaydedildiğini doğrulayın. |   2   | D/V  |
| 10.7.4 | Uyarlanabilir güvenlik mekanizmalarının, risk bağlamı ve davranışsal desenlere göre tehdit algılama hassasiyetini ayarladığını doğrulayın.                       |   3   | D/V  |
| 10.7.5 | Politika uyarlama kararlarının açıklanabilir olduğunu ve güvenlik ekibi incelemesi için kanıt izleri içerdiğini doğrulayın.                                      |   3   | D/V  |

---

## 10.8 Yansıtma Tabanlı Güvenlik Analizi

Ajanın öz-refleksiyonu ve meta-bilişsel analiz yoluyla güvenlik doğrulaması.

|   #    | Description                                                                                                                                                | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 10.8.1 | Ajan yansıtma mekanizmalarının, kararların ve eylemlerin güvenlik odaklı öz değerlendirmesini içerdiğini doğrulayın.                                       |   1   | D/V  |
| 10.8.2 | Yansıma çıktılarının doğrulanarak, kötü niyetli girdilerle öz-değerlendirme mekanizmalarının manipüle edilmesinin önlendiğini doğrulayın.                  |   2   | D/V  |
| 10.8.3 | Meta-bilişsel güvenlik analizinin, ajan akıl yürütme süreçlerindeki potansiyel önyargıyı, manipülasyonu veya güvenlik ihlalini tespit ettiğini doğrulayın. |   2   | D/V  |
| 10.8.4 | Yansıma tabanlı güvenlik uyarılarının gelişmiş izlemeyi ve olası insan müdahalesi iş akışlarını tetiklediğini doğrulayın.                                  |   3   | D/V  |
| 10.8.5 | Güvenlik yansımalarından sürekli öğrenmenin, meşru işlevselliği bozmadan tehdit algılamayı iyileştirdiğini doğrulayın.                                     |   3   | D/V  |

---

## 10.9 Evrim ve Öz Gelişim Güvenliği

Kendi kendini değiştirip evrimleşebilen ajan sistemleri için güvenlik kontrolleri.

|   #    | Description                                                                                                                                        | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 10.9.1 | Kendi kendini değiştirme yeteneklerinin, resmi doğrulama sınırları ile belirlenmiş güvenli alanlarla sınırlandırıldığını doğrulayın.               |   1   | D/V  |
| 10.9.2 | Evrim önerilerinin uygulanmadan önce güvenlik etki değerlendirmesinden geçtiğini doğrulayın.                                                       |   2   | D/V  |
| 10.9.3 | Kendini geliştirme mekanizmalarının bütünlük doğrulaması ile geri alma yeteneklerini içerdiğini doğrulayın.                                        |   2   | D/V  |
| 10.9.4 | Meta-öğrenme güvenliğinin, iyileştirme algoritmalarının düşmanca manipülasyonunu önlediğini doğrulayın.                                            |   3   | D/V  |
| 10.9.5 | Özyinelemeli kendini geliştirme sürecinin matematiksel yakınsama kanıtlarıyla birlikte resmi güvenlik kısıtlarıyla sınırlandırıldığını doğrulayın. |   3   | D/V  |

---

### Kaynaklar

* [MITRE ATLAS adversary tactics for ML](https://atlas.mitre.org/)
* [NIST AI Risk Management Framework 1.0, 2023](https://nvlpubs.nist.gov/nistpubs/ai/nist.ai.100-1.pdf)
* [OWASP Top 10 for LLM Applications, 2025](https://owasp.org/www-project-top-10-for-large-language-model-applications/)
* [Adversarial Training: A Survey — Zhao et al., 2024](https://arxiv.org/abs/2410.15042)
* [RobustBench adversarial-robustness benchmark](https://robustbench.github.io/)
* [Membership-Inference & Model-Inversion Risk Survey, 2025](https://www.sciencedirect.com/science/article/abs/pii/S0950705125003867)
* [PURIFIER: Confidence-Score Defense against MI Attacks — AAAI 2023](https://ojs.aaai.org/index.php/AAAI/article/view/26289)
* [Model-Inversion Attacks & Defenses Survey — AI Review, 2025](https://link.springer.com/article/10.1007/s10462-025-11248-0)
* [Comprehensive Defense Framework Against Model Extraction — IEEE TDSC 2024](https://doi.org/10.1109/TDSC.2023.3261327)
* [Fragile Model Watermarking Survey — 2025](https://www.sciencedirect.com/science/article/abs/pii/S0165168425002026)
* [Data Poisoning in Deep Learning: A Survey — Zhao et al., 2025](https://arxiv.org/abs/2503.22759)
* [BDetCLIP: Multimodal Prompting Backdoor Detection — Niu et al., 2024](https://arxiv.org/abs/2405.15269)

