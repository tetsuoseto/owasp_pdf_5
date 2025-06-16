# C7 Model Davranışı, Çıktı Kontrolü ve Güvenlik Güvencesi

## Kontrol Amacı

Model çıktıları yapılandırılmış, güvenilir, güvenli, açıklanabilir olmalı ve üretimde sürekli izlenmelidir. Bu, gerçek dışı içerikleri, gizlilik sızıntılarını, zararlı içerikleri ve kontrol dışı eylemleri azaltırken, kullanıcı güvenini ve düzenleyici uyumu artırır.

---

## C7.1 Çıktı Formatı Zorlaması

Sıkı şemalar, kısıtlı çözümleme ve sonraki doğrulama, bozuk veya kötü niyetli içeriğin yayılmasını engeller.

|   #   | Description                                                                                                                                                                        | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 7.1.1 | Yanıt şemalarının (örn., JSON Şeması) sistem isteminde sağlandığını ve her çıktının otomatik olarak doğrulandığını doğrulayın; uyumsuz çıktılar onarım veya reddedilmeyi tetikler. |   1   | D/V  |
| 7.1.2 | Taşma veya istem enjeksiyonu yan kanal saldırılarını önlemek için kısıtlı çözümlemenin (durdurma tokenları, regex, maksimum token sayısı) etkinleştirildiğini doğrulayın.          |   1   | D/V  |
| 7.1.3 | Aşağıdaki bileşenlerin çıktıları güvenilmez olarak ele aldığını ve bunları şemalar veya enjeksiyona karşı güvenli de-serializatörlere karşı doğruladığını kontrol edin.            |   2   | D/V  |
| 7.1.4 | Yanlış çıktı olaylarının kaydedildiğini, hız sınırlaması uygulandığını ve izlemeye yansıtıldığını doğrulayın.                                                                      |   3   |  V   |

---

## C7.2 Halüsinasyon Tespiti ve Azaltılması

Belirsizlik tahmini ve yedek stratejiler, uydurma yanıtları engeller.

|   #   | Description                                                                                                                                                                     | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 7.2.1 | Token düzeyinde log-olasılıkların, topluluk içi tutarlılığın veya ince ayarlı halüsinasyon tespitçilerinin her yanıta bir güven skoru atadığını doğrulayın.                     |   1   | D/V  |
| 7.2.2 | Yapılandırılabilir bir güven eşiğinin altındaki yanıtların, geri çekme iş akışlarını (ör. bilgiye dayalı üretim, ikincil model veya insan incelemesi) tetiklediğini doğrulayın. |   1   | D/V  |
| 7.2.3 | Halüsinasyon olaylarının kök neden meta verisi ile etiketlendiğini ve post-mortem ile ince ayar (finetuning) iş akışlarına aktarıldığını doğrulayın.                            |   2   | D/V  |
| 7.2.4 | Büyük model veya bilgi tabanı güncellemelerinden sonra eşik değerlerinin ve algılayıcıların tekrar kalibre edildiğini doğrulayın.                                               |   3   | D/V  |
| 7.2.5 | Gösterge paneli görselleştirmelerinin halüsinasyon oranlarını takip ettiğini doğrulayın.                                                                                        |   3   |  V   |

---

## C7.3 Çıktı Güvenliği ve Gizlilik Filtreleme

Politika filtreleri ve red-team kapsamı, kullanıcıları ve gizli verileri korur.

|   #   | Description                                                                                                                                                                | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 7.3.1 | Ön ve son üretim sınıflandırıcılarının, politika ile uyumlu nefret, taciz, kendine zarar verme, aşırılık yanlısı ve cinsel içerikli materyalleri engellediğini doğrulayın. |   1   | D/V  |
| 7.3.2 | Her yanıtta Kişisel Tanımlanabilir Bilgi (PII) / Ödeme Kartı Endüstrisi (PCI) tespiti ve otomatik sansürün çalıştığını doğrulayın; ihlaller gizlilik olayını tetikler.     |   1   | D/V  |
| 7.3.3 | Gizlilik etiketlerinin (örneğin, ticari sırlar) metin, resim veya kodda sızıntıyı önlemek için modlar arasında yayıldığını doğrulayın.                                     |   2   |  D   |
| 7.3.4 | Filtre atlama girişimlerinin veya yüksek riskli sınıflandırmaların ikincil onay veya kullanıcı tekrar kimlik doğrulaması gerektirdiğini doğrulayın.                        |   3   | D/V  |
| 7.3.5 | Filtreleme eşiklerinin yasal yargı alanları ve kullanıcı yaşı/rol bağlamını yansıttığını doğrulayın.                                                                       |   3   | D/V  |

---

## C7.4 Çıktı ve Eylem Kısıtlaması

Oran sınırları ve onay kapıları, kötüye kullanımı ve aşırı özerkliği önler.

|   #   | Description                                                                                                                                                                          | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 7.4.1 | 429 hatalarında üstel geri çekilme ile kullanıcı başına ve API anahtarı başına kota sınırlarının istekleri, tokenları ve maliyeti kısıtladığını doğrulayın.                          |   1   |  D   |
| 7.4.2 | Ayrıcalıklı işlemlerin (dosya yazımları, kod yürütme, ağ çağrıları) politika tabanlı onay veya insan müdahalesi gerektirdiğini doğrulayın.                                           |   1   | D/V  |
| 7.4.3 | Çapraz modlu tutarlılık kontrollerinin, aynı istek için oluşturulan görüntülerin, kodun ve metnin kötü amaçlı içerik gizlemek için kullanılamayacağından emin olunmasını doğrulayın. |   2   | D/V  |
| 7.4.4 | Ajan delege derinliği, özyineleme sınırları ve izin verilen araç listelerinin açıkça yapılandırıldığını doğrulayın.                                                                  |   2   |  D   |
| 7.4.5 | Limit ihlalinin SIEM alımı için yapılandırılmış güvenlik olayları yaydığını doğrulayın.                                                                                              |   3   |  V   |

---

## C7.5 Çıktı Açıklanabilirliği

Şeffaf sinyaller kullanıcı güvenini ve dahili hata ayıklamayı artırır.

|   #   | Description                                                                                                                          | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 7.5.1 | Risk değerlendirmesi uygun gördüğünde, kullanıcıya yönelik güven puanlarının veya kısa mantık özetlerinin gösterildiğini doğrulayın. |   2   | D/V  |
| 7.5.2 | Oluşturulan açıklamaların hassas sistem istemlerini veya tescilli verileri ifşa etmediğini doğrulayın.                               |   2   | D/V  |
| 7.5.3 | Sistemin, token düzeyinde olasılık günlüklerini veya dikkat haritalarını yakalayarak yetkili inceleme için depoladığını doğrulayın.  |   3   |  D   |
| 7.5.4 | Açıklanabilirlik artefaktlarının denetlenebilirlik için model sürümleriyle birlikte sürüm kontrolünün yapıldığını doğrulayın.        |   3   |  V   |

---

## C7.6 İzleme Entegrasyonu

Gerçek zamanlı gözlemlenebilirlik, geliştirme ile üretim arasındaki döngüyü kapatır.

|   #   | Description                                                                                                                                                    | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 7.6.1 | Metriklerin (şema ihlalleri, halüsinasyon oranı, toksisite, KİB sızıntıları, gecikme süresi, maliyet) merkezi bir izleme platformuna aktarıldığını doğrulayın. |   1   |  D   |
| 7.6.2 | Her güvenlik metriği için uyarı eşikleri tanımlandığını ve çağrı üzerine yükseltme yollarının bulunduğunu doğrulayın.                                          |   1   |  V   |
| 7.6.3 | Gösterge tablolarının çıktı anormalliklerini model/sürüm, özellik bayrağı ve yukarı akış veri değişiklikleri ile ilişkilendirdiğini doğrulayın.                |   2   |  V   |
| 7.6.4 | Belgelenmiş bir MLOps iş akışı içinde, izleme verilerinin yeniden eğitim, ince ayar veya kural güncellemelerine geri besleme yapmasını doğrulayın.             |   2   | D/V  |
| 7.6.5 | Hassas günlüklerin sızıntısını önlemek için izleme boru hatlarının penetrasyon testlerinin yapıldığını ve erişim kontrollerinin uygulandığını doğrulayın.      |   3   |  V   |

---

## 7.7 Üretken Medya Güvenlik Önlemleri

AI sistemlerinin yasa dışı, zararlı veya yetkisiz medya içeriği üretmemesini sağlamak için politika kısıtlamalarını, çıktı doğrulamasını ve izlenebilirliği uygulayın.

|   #   | Description                                                                                                                                                                                                                         | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 7.7.1 | Sistem istemlerinin ve kullanıcı talimatlarının yasa dışı, zararlı veya rızaya dayanmayan deepfake medya (örneğin, görüntü, video, ses) oluşturulmasını açıkça yasakladığını doğrulayın.                                            |   1   | D/V  |
| 7.7.2 | İsteklerin taklit oluşturma girişimleri, cinsel içerikli derin sahte videolar veya gerçek kişileri izinsiz gösteren medyalar için filtrelendiğini doğrulayın.                                                                       |   2   | D/V  |
| 7.7.3 | Sistemin, telif hakkıyla korunan medyanın yetkisiz çoğaltılmasını önlemek için algısal özetleme (perceptual hashing), filigran (watermark) tespiti veya parmak izi (fingerprinting) yöntemlerini kullandığını doğrulayın.           |   2   |  V   |
| 7.7.4 | Tüm oluşturulan medyanın, aşağı akıştaki izlenebilirlik için kriptografik olarak imzalanmış, filigranlı veya değiştirilemez köken meta verisi ile gömülü olduğunu doğrulayın.                                                       |   3   | D/V  |
| 7.7.5 | Atlatma girişimlerinin (örneğin, prompt karartma, argo, düşmanca ifadeler) tespit edildiğinden, kaydedildiğinden ve hız sınırlamasına tabi tutulduğundan emin olun; tekrarlayan kötüye kullanımlar izleme sistemlerine bildirilsin. |   3   |  V   |

## Referanslar

* [NIST AI Risk Management Framework](https://www.nist.gov/itl/ai-risk-management-framework)
* [ISO/IEC 42001:2023 – AI Management System](https://www.iso.org/obp/ui/en/)
* [OWASP Top-10 for Large Language Model Applications (2025)](https://owasp.org/www-project-top-10-for-large-language-model-applications/)
* [Improper Output Handling – OWASP LLM05:2025](https://genai.owasp.org/llmrisk/llm052025-improper-output-handling/)
* [Practical Techniques to Constrain LLM Output](https://mychen76.medium.com/practical-techniques-to-constraint-llm-output-in-json-format-e3e72396c670)
* [Dataiku – Structured Text Generation Guide](https://blog.dataiku.com/your-guide-to-structured-text-generation)
* [VL-Uncertainty: Detecting Hallucinations](https://arxiv.org/abs/2411.11919)
* [HaDeMiF: Hallucination Detection & Mitigation](https://openreview.net/forum?id=VwOYxPScxB)
* [Building Confidence in LLM Outputs](https://www.alkymi.io/data-science-room/building-confidence-in-llm-outputs)
* [Explainable AI & LLMs](https://duncsand.medium.com/explainable-ai-140912d31b3b)
* [LLM Red-Teaming Guide](https://www.confident-ai.com/blog/red-teaming-llms-a-step-by-step-guide)
* [Sensitive Information Disclosure in LLMs](https://virtualcyberlabs.com/llm-sensitive-information-disclosure/)
* [LangChain – Chat Model Rate Limiting](https://python.langchain.com/docs/how_to/chat_model_rate_limiting/)
* [OpenAI Rate-Limit & Exponential Back-off](https://hackernoon.com/openais-rate-limit-a-guide-to-exponential-backoff-for-llm-evaluation)
* [Arize AI – LLM Observability Platform](https://arize.com/)

