# C13 İnsan Gözetimi, Hesap Verebilirlik ve Yönetişim

## Kontrol Hedefi

Bu bölüm, Yapay Zeka (YZ) sistemlerinde insan denetimi ve net hesap verebilirlik zincirlerinin sürdürülmesi için gereklilikler sağlar; YZ yaşam döngüsü boyunca açıklanabilirlik, şeffaflık ve etik yönetimi güvence altına alır.

---

## C13.1 Kill-Switch ve Geçersiz Kılma Mekanizmaları

AI sisteminin güvensiz davranışı gözlemlendiğinde kapanış veya geri alma yolları sağlayın.

|   #    | Description                                                                                                          | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 13.1.1 | AI model çıkarımını ve çıktıları derhal durdurmak için manuel bir acil durdurma mekanizmasının varlığını doğrulayın. |   1   | D/V  |
| 13.1.2 | Geçersiz kılma kontrollerinin yalnızca yetkili personelin erişimine açık olduğunu doğrulayın.                        |   1   |  D   |
| 13.1.3 | Geri alma prosedürlerinin önceki model sürümlerine veya güvenli mod işlemlerine dönebileceğini doğrulayın.           |   3   | D/V  |
| 13.1.4 | Geçersiz kılma mekanizmalarının düzenli olarak test edildiğini doğrulayın.                                           |   3   |  V   |

---

## C13.2 İnsan-Dahil Döngü Karar Kontrol Noktaları

Risk eşiklerini aştığında insan onayı gerektirir.

|   #    | Description                                                                                                                                      | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 13.2.1 | Yüksek riskli Yapay Zeka kararlarının yürütülmeden önce açık insan onayı gerektirdiğini doğrulayın.                                              |   1   | D/V  |
| 13.2.2 | Risk eşiklerinin açıkça tanımlandığını ve insan inceleme iş akışlarını otomatik olarak tetiklediğini doğrulayın.                                 |   1   |  D   |
| 13.2.3 | İnsan onayı gereken süre içinde alınamadığında, zaman duyarlı kararların yedek prosedürlere sahip olduğunu doğrulayın.                           |   2   |  D   |
| 13.2.4 | Yükseltme prosedürlerinin, uygulanabilir ise, farklı karar türleri veya risk kategorileri için net yetki seviyelerini tanımladığından emin olun. |   3   | D/V  |

---

## C13.3 Sorumluluk Zinciri ve Denetlenebilirlik

Operatör eylemlerini ve model kararlarını kaydedin.

|   #    | Description                                                                                                                                             | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 13.3.1 | Tüm yapay zeka sistemi kararlarının ve insan müdahalelerinin, zaman damgaları, kullanıcı kimlikleri ve karar gerekçeleri ile kaydedildiğini doğrulayın. |   1   | D/V  |
| 13.3.2 | Denetim kayıtlarının değiştirilip değiştirilemeyeceğini doğrulayın ve bütünlük doğrulama mekanizmalarını dahil edin.                                    |   2   |  D   |

---

## C13.4 Açıklanabilir-YZ Teknikleri

Yüzey özellik önemi, karşı-olasılıklar ve yerel açıklamalar.

|   #    | Description                                                                                                                                                  | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 13.4.1 | Yapay zeka sistemlerinin kararları için insan tarafından okunabilir biçimde temel açıklamalar sağladığını doğrulayın.                                        |   1   | D/V  |
| 13.4.2 | Açıklama kalitesinin insan değerlendirme çalışmaları ve metrikler aracılığıyla doğrulandığını teyit edin.                                                    |   2   |  V   |
| 13.4.3 | Kritik kararlar için özellik önem puanları veya atıf yöntemlerinin (SHAP, LIME, vb.) mevcut olduğunu doğrulayın.                                             |   3   | D/V  |
| 13.4.4 | Karşıt açıklamaların, kullanım durumu ve alana uygulanabilir ise, sonuçları değiştirmek için girdilerin nasıl değiştirilebileceğini gösterdiğini doğrulayın. |   3   |  V   |

---

## C13.5 Model Kartları ve Kullanım Açıklamaları

Model kartlarını amaçlanan kullanım, performans ölçütleri ve etik hususlar için güncel tutun.

|   #    | Description                                                                                                                                                                                                | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 13.5.1 | Model kartlarının amaçlanan kullanım durumlarını, sınırlamalarını ve bilinen hata durumlarını belgelediğini doğrulayın.                                                                                    |   1   |  D   |
| 13.5.2 | Farklı uygun kullanım durumları için performans metriklerinin açıklanıp açıklanmadığını doğrulayın.                                                                                                        |   1   | D/V  |
| 13.5.3 | Etik değerlendirmelerin, önyargı analizlerinin, adillik değerlendirmelerinin, eğitim verisi özelliklerinin ve bilinen eğitim verisi sınırlamalarının belgelenip düzenli olarak güncellendiğini doğrulayın. |   2   |  D   |
| 13.5.4 | Model kartlarının versiyon kontrolünün yapıldığını ve değişiklik takibi ile model yaşam döngüsü boyunca korunduğunu doğrulayın.                                                                            |   2   | D/V  |

---

## C13.6 Belirsizlik Nicelleştirmesi

Yanıtlarda güven skorlarını veya entropi ölçümlerini yay.

|   #    | Description                                                                                                | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 13.6.1 | AI sistemlerinin çıktılarıyla birlikte güven skoru veya belirsizlik ölçüleri sağladığını doğrulayın.       |   1   |  D   |
| 13.6.2 | Belirsizlik eşiklerinin ek insan incelemesini veya alternatif karar yollarını tetiklediğini doğrulayın.    |   2   | D/V  |
| 13.6.3 | Belirsizlik nicelleme yöntemlerinin, gerçek temel verilere karşı kalibre edilip doğrulandığını teyit edin. |   2   |  V   |
| 13.6.4 | Belirsizlik yayılımının çok adımlı Yapay Zeka iş akışları boyunca korunduğunu doğrulayın.                  |   3   | D/V  |

---

## C13.7 Kullanıcıya Yönelik Şeffaflık Raporları

Olaylar, sapma ve veri kullanımı hakkında düzenli açıklamalar sağlayın.

|   #    | Description                                                                                                                                                        | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 13.7.1 | Veri kullanım politikalarının ve kullanıcı onayı yönetimi uygulamalarının paydaşlara açıkça iletildiğini doğrulayın.                                               |   1   | D/V  |
| 13.7.2 | Yapay zeka etki değerlendirmelerinin yapıldığını doğrulayın ve sonuçların raporlamaya dahil edildiğinden emin olun.                                                |   2   | D/V  |
| 13.7.3 | Şeffaflık raporlarının düzenli olarak yayımlanıp yayımlanmadığını ve AI olayları ile operasyonel metriklerin makul ayrıntıda açıklanıp açıklanmadığını doğrulayın. |   2   | D/V  |

### Referanslar

* [EU Artificial Intelligence Act — Regulation (EU) 2024/1689 (Official Journal, 12 July 2024)](https://eur-lex.europa.eu/eli/reg/2024/1689/oj)
* [ISO/IEC 23894:2023 — Artificial Intelligence — Guidance on Risk Management](https://www.iso.org/standard/77304.html)
* [ISO/IEC 42001:2023 — AI Management Systems Requirements](https://www.iso.org/standard/81230.html)
* [NIST AI Risk Management Framework 1.0](https://nvlpubs.nist.gov/nistpubs/ai/nist.ai.100-1.pdf)
* [NIST SP 800-53 Revision 5 — Security and Privacy Controls](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-53r5.pdf)
* [A Unified Approach to Interpreting Model Predictions (SHAP, ICML 2017)](https://arxiv.org/abs/1705.07874)
* [Model Cards for Model Reporting (Mitchell et al., 2018)](https://arxiv.org/abs/1810.03993)
* [Dropout as a Bayesian Approximation: Representing Model Uncertainty in Deep Learning (Gal & Ghahramani, 2016)](https://arxiv.org/abs/1506.02142)
* [ISO/IEC 24029-2:2023 — Robustness of Neural Networks — Methodology for Formal Methods](https://www.iso.org/standard/79804.html)
* [IEEE 7001-2021 — Transparency of Autonomous Systems](https://standards.ieee.org/ieee/7001/6929/)
* [GDPR — Article 5 "Transparency Principle" (Regulation (EU) 2016/679)](https://eur-lex.europa.eu/legal-content/EN/TXT/PDF/?uri=CELEX%3A32016R0679)
* [Human Oversight under Article 14 of the EU AI Act (Fink, 2025)](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=5147196)

