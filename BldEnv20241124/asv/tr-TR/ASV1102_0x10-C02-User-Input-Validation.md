# C2 Kullanıcı Girişi Doğrulaması

## Kontrol Hedefi

Kullanıcı girdisinin sağlam doğrulanması, Yapay Zeka sistemlerine yönelik en zarar verici saldırılara karşı ilk savunma hattıdır. Komut enjeksiyonu saldırıları, sistem talimatlarını geçersiz kılabilir, hassas verileri sızdırabilir veya modeli izin verilmeyen davranışlara yönlendirebilir. Özel filtreler ve talimat hiyerarşileri yoksa, araştırmalar çok uzun bağlam pencerelerini kullanan "çok-vuruşlu" kaçış yöntemlerinin etkili olacağını göstermektedir. Ayrıca, homoglif değişimleri veya leetspeak gibi ince düşmanca bozulma saldırıları, modelin kararlarını sessizce değiştirebilir.

---

## C2.1 İstek Enjeksiyonu Savunması

İstek enjeksiyonu, yapay zeka sistemleri için en büyük risklerden biridir. Bu taktiğe karşı savunmalar, statik desen filtreleri, dinamik sınıflandırıcılar ve talimat hiyerarşisi uygulamasının bir kombinasyonunu kullanır.

|   #   | Description                                                                                                                                                                                                                                                | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 2.1.1 | Kullanıcı girdilerinin, sürekli güncellenen bilinen prompt enjeksiyonu desenleri kütüphanesine (jailbreak anahtar kelimeleri, "öndeki komutları yok say", rol yapma zincirleri, dolaylı HTML/URL saldırıları) karşı tarandığından emin olun.               |   1   | D/V  |
| 2.1.2 | Sistemin, bağlam penceresi genişletildikten sonra bile sistem veya geliştirici mesajlarının kullanıcı talimatlarının üzerine geçtiği bir talimat hiyerarşisini uyguladığını doğrulayın.                                                                    |   1   | D/V  |
| 2.1.3 | Her model veya prompt-şablon sürümü öncesinde, başarı oranı eşiklerine ve gerilemeler için otomatik engelleyicilere sahip olacak şekilde, düşman değerlendirme testlerinin (örneğin, Kırmızı Takım "çoklu deneme" promptları) çalıştırıldığını doğrulayın. |   2   | D/V  |
| 2.1.4 | Üçüncü taraf içeriklerinden (web sayfaları, PDF'ler, e-postalar) kaynaklanan istemlerin, ana istemle birleştirilmeden önce izole bir ayrıştırma bağlamında temizlendiğini doğrulayın.                                                                      |   2   |  D   |
| 2.1.5 | Tüm istemci-filtre kural güncellemelerinin, sınıflandırıcı model sürümlerinin ve engelleme listesi değişikliklerinin sürüm kontrollü ve denetlenebilir olduğunu doğrulayın.                                                                                |   3   | D/V  |

---

## C2.2 Karşıt Örnek Direnci

Doğal Dil İşleme (NLP) modelleri, insanların sıkça gözden kaçırdığı ancak modellerin yanlış sınıflandırmaya eğilimli olduğu ince karakter veya kelime düzeyindeki değişikliklere karşı hâlâ savunmasızdır.

|   #   | Description                                                                                                                                                                                                                | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 2.2.1 | Temel giriş normalizasyon adımlarının (Unicode NFC, homoglif eşleştirme, boşluk kırpma) tokenleştirme işleminden önce çalıştığını doğrulayın.                                                                              |   1   |  D   |
| 2.2.2 | İstatistiksel anomali tespitinin, dil normlarına alışılmadık derecede yüksek düzenleme mesafesine sahip girdileri, aşırı tekrarlanan tokenleri veya anormal gömme (embedding) mesafelerini işaretlediğini doğrulayın.      |   2   | D/V  |
| 2.2.3 | Çıkarım hattının, yüksek riskli uç noktalar için isteğe bağlı düşmanca eğitimle güçlendirilmiş model varyantlarını veya savunma katmanlarını (örneğin, rastgeleleştirme, savunmacı distilasyon) desteklediğini doğrulayın. |   2   |  D   |
| 2.2.4 | Şüphelenilen düşmanca girdilerin karantinaya alındığını, tam yükler ile (Kişisel Tanımlayıcı Bilgiler (PII) kırpması sonrası) kaydedildiğini doğrulayın.                                                                   |   2   |  V   |
| 2.2.5 | Dayanıklılık metriklerinin (bilinen saldırı setlerinin başarı oranı) zaman içinde izlendiğini ve gerilemelerin bir sürüm engelleyicisini tetiklediğini doğrulayın.                                                         |   3   | D/V  |

---

## C2.3 Şema, Tip ve Uzunluk Doğrulaması

Yanlış biçimlendirilmiş veya aşırı büyük girdiler içeren Yapay Zeka saldırıları, ayrıştırma hatalarına, alanlar arasında istem taşmasına ve kaynak tükenmesine neden olabilir. Belirleyici araç çağrıları gerçekleştirilirken sıkı şema (şematik yapı) denetimi de ön koşuldur.

|   #   | Description                                                                                                                                                                                                | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 2.3.1 | Her API veya fonksiyon çağrısı uç noktasının açık bir giriş şeması (JSON Şeması, Protobuf veya çok modlu eşdeğeri) tanımladığını ve girdi verilerinin istek oluşturulmadan önce doğrulandığını doğrulayın. |   1   |  D   |
| 2.3.2 | Girdiğin maksimum token veya byte sınırını aşan girişlerin güvenli bir hata ile reddedildiğini ve asla sessizce kısaltılmadığını doğrula.                                                                  |   1   | D/V  |
| 2.3.3 | Tür türü kontrollerinin (örneğin, sayısal aralıklar, enum değerleri, resim/ses için MIME türleri) yalnızca istemci kodunda değil, sunucu tarafında da uygulandığını doğrulayın.                            |   2   | D/V  |
| 2.3.4 | Semantik doğrulayıcıların (örneğin, JSON Şeması) algoritmik Hizmet Reddi (DoS) saldırılarını önlemek için sabit zamanda çalıştığını doğrulayın.                                                            |   2   |  D   |
| 2.3.5 | Doğrulama hatalarının, güvenlik üçlemesini kolaylaştırmak için sansürlenmiş yük kesitleri ve açık hata kodları ile kaydedildiğini doğrulayın.                                                              |   3   |  V   |

---

## C2.4 İçerik ve Politika Tarama

Geliştiriciler, yasaklanmış içerik talep eden (yasadışı talimatlar, nefret söylemi ve telif hakkıyla korunan metinler gibi) sözdizimsel olarak geçerli istemleri tespit edebilmeli ve bunların yayılmasını engellemelidir.

|   #   | Description                                                                                                                                                                                                           | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 2.4.1 | Bir içerik sınıflandırıcısının (sıfır atış veya ince ayar yapılmış) her girdiyi şiddet, öz zarar, nefret, cinsel içerik ve yasadışı talepler açısından, yapılandırılabilir eşik değerleriyle puanladığını doğrulayın. |   1   |  D   |
| 2.4.2 | Politikaları ihlal eden girdilerin, standart reddedilme mesajları veya güvenli tamamlama alacaklarını doğrulayın, böylece bunlar sonraki LLM çağrılarına yayılmayacaktır.                                             |   1   | D/V  |
| 2.4.3 | Tarama modelinin veya kural setinin, yeni gözlemlenen jailbreak veya politika atlama desenlerini de içerecek şekilde en az üç ayda bir yeniden eğitildiğini/güncellendiğini doğrulayın.                               |   2   |  D   |
| 2.4.4 | Ekranlamanın, kullanıcıya özgü politikalara (yaş, bölgesel yasal kısıtlamalar) isteğin yapıldığı anda çözülen öznitelik tabanlı kurallar aracılığıyla uyduğunu doğrulayın.                                            |   2   |  D   |
| 2.4.5 | Tarama günlüklerinin SOC korelasyonu ve gelecekteki kırmızı takım tekrarı için sınıflandırıcı güven puanları ve politika kategori etiketlerini içerdiğini doğrulayın.                                                 |   3   |  V   |

---

## C2.5 Girdi Hızı Sınırlaması ve Kötüye Kullanım Önleme

Geliştiriciler, giriş hızlarını sınırlayarak ve anormal kullanım kalıplarını tespit ederek AI sistemlerine yönelik kötüye kullanımı, kaynak tükenmesini ve otomatik saldırıları önlemelidir.

|   #   | Description                                                                                                                                         | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 2.5.1 | Tüm giriş uç noktalarında kullanıcı başına, IP başına ve API anahtarı başına hız sınırlarının uygulandığını doğrulayın.                             |   1   | D/V  |
| 2.5.2 | DoS ve kaba kuvvet saldırılarını önlemek için ani ve sürekli hız sınırlarının ayarlandığını doğrulayın.                                             |   2   | D/V  |
| 2.5.3 | Anormal kullanım kalıplarının (örneğin, hızlı ardı ardına istekler, giriş seli) otomatik engellemeleri veya yükseltmeleri tetiklediğini doğrulayın. |   2   | D/V  |
| 2.5.4 | Kötüye kullanım önleme günlüklerinin saklandığını ve ortaya çıkan saldırı desenleri için incelendiğini doğrulayın.                                  |   3   |  V   |

---

## C2.6 Çok Modlu Girdi Doğrulaması

Yapay zeka sistemleri, enjeksiyon, kaçınma veya kaynak kötüye kullanımını önlemek için metin dışı girdiler (görseller, ses, dosyalar) için sağlam doğrulama içermelidir.

|   #   | Description                                                                                                                             | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 2.6.1 | İşlemden önce tüm metin dışı girdilerin (görseller, ses dosyaları, dosyalar) tür, boyut ve biçim açısından doğrulandığını kontrol edin. |   1   |  D   |
| 2.6.2 | Dosyaların içeri alınmadan önce kötü amaçlı yazılım ve steganografik yükler açısından tarandığını doğrulayın.                           |   2   | D/V  |
| 2.6.3 | Görüntü/ses girdilerinin düşmanca değişiklikler veya bilinen saldırı desenleri açısından kontrol edildiğini doğrulayın.                 |   2   | D/V  |
| 2.6.4 | Çok modlu giriş doğrulama hatalarının kaydedildiğini ve araştırma için uyarılar tetiklediğini doğrulayın.                               |   3   |  V   |

---

## C2.7 Girdi Kaynağı ve Atıf

Yapay zeka sistemleri, tüm kullanıcı girdilerinin kaynaklarını izleyerek ve etiketleyerek denetim, kötüye kullanım takibi ve uyumluluğu desteklemelidir.

|   #   | Description                                                                                                                                        | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 2.7.1 | Tüm kullanıcı girişlerinin alım sırasında meta verilerle (kullanıcı kimliği, oturum, kaynak, zaman damgası, IP adresi) etiketlendiğini doğrulayın. |   1   | D/V  |
| 2.7.2 | İşlenen tüm girdiler için köken meta verilerinin korunduğunu ve denetlenebilir olduğunu doğrulayın.                                                |   2   | D/V  |
| 2.7.3 | Anormal veya güvenilmeyen giriş kaynaklarının işaretlendiğini ve artırılmış inceleme veya engelleme kapsamında olduğunu doğrulayın.                |   2   | D/V  |

---

## C2.8 Gerçek Zamanlı Uyarlanabilir Tehdit Tespiti

Geliştiriciler, yeni saldırı modellerine uyum sağlayan ve derlenmiş desen eşleştirme ile gerçek zamanlı koruma sağlayan gelişmiş tehdit algılama sistemlerini AI için kullanmalıdır.

|   #   | Description                                                                                                                                                                                              | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 2.8.1 | Tehdit tespit desenlerinin, minimum gecikme etkisiyle yüksek performanslı gerçek zamanlı filtreleme için optimize edilmiş regex motorlarına derlenip derlenmediğini doğrulayın.                          |   1   | D/V  |
| 2.8.2 | Tehdit algılama sistemlerinin farklı tehdit kategorileri için (komut enjeksiyonu, zararlı içerik, hassas veri, sistem komutları) ayrı desen kütüphaneleri tuttuğunu doğrulayın.                          |   1   | D/V  |
| 2.8.3 | Uyarlamalı tehdit algılamanın, saldırı sıklığı ve başarı oranlarına dayalı olarak tehdit hassasiyetini güncelleyen makine öğrenimi modellerini içerdiğini doğrulayın.                                    |   2   | D/V  |
| 2.8.4 | Gerçek zamanlı tehdit istihbaratı beslemelerinin, yeni saldırı imzaları ve Tespit Göstergeleri (Indicators of Compromise - IOC'lar) ile desen kütüphanelerini otomatik olarak güncellediğini doğrulayın. |   2   | D/V  |
| 2.8.5 | Tehdit algılama yanlış pozitif oranlarının sürekli olarak izlendiğini ve desen özgüllüğünün meşru kullanım senaryosu müdahalesini en aza indirmek için otomatik olarak ayarlandığını doğrulayın.         |   3   | D/V  |
| 2.8.6 | Bağlamsal tehdit analizinin algılama doğruluğunu artırmak için giriş kaynağı, kullanıcı davranış kalıpları ve oturum geçmişini dikkate aldığını doğrulayın.                                              |   3   | D/V  |
| 2.8.7 | Tehdit tespiti performans metriklerinin (tespit oranı, işleme gecikmesi, kaynak kullanımı) gerçek zamanlı olarak izlendiğini ve optimize edildiğini doğrulayın.                                          |   3   | D/V  |

---

## C2.9 Çok Modlu Güvenlik Doğrulama Boru Hattı

Geliştiriciler, metin, görüntü, ses ve diğer yapay zeka giriş modları için belirli türde tehdit tespiti ve kaynak izolasyonu ile güvenlik doğrulaması sağlamalıdır.

|   #   | Description                                                                                                                                                                                                                                                  | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 2.9.1 | Her girdi modülünün, belgelenmiş tehdit desenleri (metin: istem enjeksiyonu, görüntüler: steganografi, ses: spektrogram saldırıları) ve tespit eşik değerleri ile özel güvenlik doğrulayıcılarına sahip olduğunu doğrulayın.                                 |   1   | D/V  |
| 2.9.2 | Çok modlu girdilerin, her modalite türüne özgü tanımlanmış kaynak sınırları (bellek, CPU, işlem süresi) ile izole edilmiş kum havuzlarında işlendiğini ve bunun güvenlik politikalarında belgelenmiş olduğunu doğrulayın.                                    |   2   | D/V  |
| 2.9.3 | Çapraz modal saldırı tespitinin, birden çok girdi türünü kapsayan koordine saldırıları (örneğin, görüntülerde steganografik yükler ile metinde istem enjeksiyonu birlikte) ilişkilendirme kuralları ve uyarı üretimi ile tanımladığını doğrulayın.           |   2   | D/V  |
| 2.9.4 | Çok modlu doğrulama hatalarının, tüm giriş modlarını, doğrulama sonuçlarını, tehdit puanlarını ve korelasyon analizini içeren ayrıntılı günlük kaydını tetiklediğini ve SIEM entegrasyonu için yapılandırılmış günlük formatlarının sağlandığını doğrulayın. |   3   | D/V  |
| 2.9.5 | Modaliteye özgü içerik sınıflandırıcılarının, belgelenmiş programlara göre (en az üç ayda bir) yeni tehdit modelleri, düşmanca örnekler ve performans ölçütleriyle temel eşiklerin üzerinde olacak şekilde güncellendiğini doğrulayın.                       |   3   | D/V  |

---

## Kaynaklar

* [LLM01:2025 Prompt Injection – OWASP Top 10 for LLM & Generative AI Security](https://genai.owasp.org/llmrisk/llm01-prompt-injection/)
* [Generative AI's Biggest Security Flaw Is Not Easy to Fix](https://www.wired.com/story/generative-ai-prompt-injection-hacking)
* [Many-shot jailbreaking \ Anthropic](https://www.anthropic.com/research/many-shot-jailbreaking)
* [$PDF$ OpenAI GPT-4.5 System Card](https://cdn.openai.com/gpt-4-5-system-card-2272025.pdf)
* [Notebook for the CheckThat Lab at CLEF 2024](https://ceur-ws.org/Vol-3740/paper-53.pdf)
* [Mitigate jailbreaks and prompt injections – Anthropic](https://docs.anthropic.com/en/docs/test-and-evaluate/strengthen-guardrails/mitigate-jailbreaks)
* [Chapter 3 MITRE ATT\&CK – Adversarial Model Analysis](https://ama.drwhy.ai/mitre-attck.html)
* [OWASP Top 10 for LLM Applications 2025 – WorldTech IT](https://wtit.com/blog/2025/04/17/owasp-top-10-for-llm-applications-2025/)
* [OWASP Machine Learning Security Top Ten](https://owasp.org/www-project-machine-learning-security-top-10/)
* [Few words about AI Security – Jussi Metso](https://www.jussimetso.com/index.php/2024/09/28/few-words-about-ai-security/)
* [How To Ensure LLM Output Adheres to a JSON Schema | Modelmetry](https://modelmetry.com/blog/how-to-ensure-llm-output-adheres-to-a-json-schema)
* [Easily enforcing valid JSON schema following – API](https://community.openai.com/t/feature-request-function-calling-easily-enforcing-valid-json-schema-following/263515?utm_source)
* [AI Safety + Cybersecurity R\&D Tracker – Fairly AI](https://www.fairly.ai/blog/ai-cybersecurity-tracker)
* [Anthropic makes 'jailbreak' advance to stop AI models producing harmful results](https://www.ft.com/content/cf11ebd8-aa0b-4ed4-945b-a5d4401d186e)
* [Pattern matching filter rules - IBM](https://www.ibm.com/docs/ssw_aix_71/security/intrusion_pattern_matching_filter_rules.html)
* [Real-time Threat Detection](https://www.darktrace.com/cyber-ai-glossary/real-time-threat-detection)

