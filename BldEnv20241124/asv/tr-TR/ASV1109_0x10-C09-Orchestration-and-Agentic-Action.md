# 9 Otonom Orkestrasyon ve Temsilci Aksiyon Güvenliği

## Kontrol Hedefi

Otonom veya çoklu ajan yapay zeka sistemlerinin yalnızca açıkça amaçlanan, doğrulanabilen, denetlenebilir ve sınırlandırılmış maliyet ve risk eşiklerine uygun işlemleri gerçekleştirebilmesini sağlayın. Bu, Otonom Sistem İhlali, Araç Kötüye Kullanımı, Ajan Döngüsü Tespiti, İletişim Ele Geçirme, Kimlik Sahteciliği, Sürü Manipülasyonu ve Niyet Manipülasyonu gibi tehditlere karşı koruma sağlar.

---

## 9.1 Ajan Görev Planlaması ve Özyineleme Bütçeleri

Özel yetkili işlemler için yinelemeli planları sınırlayın ve insan kontrol noktalarını zorunlu kılın.

|   #   | Description                                                                                                                                                                                                        | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 9.1.1 | Maksimum özyineleme derinliği, genişlik, gerçek zamanlı saat süresi, token sayısı ve her bir ajan yürütme başına parasal maliyetin merkezi olarak yapılandırıldığını ve sürüm kontrolüne tabi olduğunu doğrulayın. |   1   | D/V  |
| 9.1.2 | Ayrıcalıklı veya geri alınamaz işlemlerin (örneğin, kod gönderimleri, finansal transferler) yürütülmeden önce denetlenebilir bir kanal üzerinden açıkça insan onayı gerektirdiğini doğrulayın.                     |   1   | D/V  |
| 9.1.3 | Gerçek zamanlı kaynak izleyicilerinin herhangi bir bütçe eşiği aşıldığında devre kesici kesintisini tetiklediğini ve daha fazla görev genişletilmesini durdurduğunu doğrulayın.                                    |   2   |  D   |
| 9.1.4 | Devre kesici olaylarının, adli inceleme amacıyla ajan kimliği, tetikleyici koşul ve yakalanan plan durumu ile kaydedildiğini doğrulayın.                                                                           |   2   | D/V  |
| 9.1.5 | Güvenlik testlerinin bütçe tükenmesi ve kontrolden çıkan plan senaryolarını kapsadığını doğrulayarak, veri kaybı olmadan güvenli durdurmayı teyit edin.                                                            |   3   |  V   |
| 9.1.6 | Bütçe politikalarının kod olarak politika şeklinde ifade edildiğini ve yapılandırma sapmasını engellemek için CI/CD'de uygulandığını doğrulayın.                                                                   |   3   |  D   |

---

## 9.2 Araç Eklenti Kutulama (Sandboxing)

Yetkisiz sistem erişimi veya kod yürütmesini önlemek için araç etkileşimlerini izole edin.

|   #   | Description                                                                                                                                                                           | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.2.1 | Her aracın/eklentinin, en az ayrıcalıklı dosya sistemi, ağ ve sistem çağrısı politikalarıyla bir işletim sistemi, konteyner veya WASM seviyesi sandbox içinde çalıştığını doğrulayın. |   1   | D/V  |
| 9.2.2 | Sandbox kaynak kotalarının (CPU, bellek, disk, ağ çıkışı) ve yürütme zaman aşımı sürelerinin uygulanıp uygulanmadığını ve kaydedilip kaydedilmediğini doğrulayın.                     |   1   | D/V  |
| 9.2.3 | Araç ikili dosyalarının veya tanımlayıcılarının dijital olarak imzalandığını doğrulayın; imzalar yüklemeden önce doğrulanır.                                                          |   2   | D/V  |
| 9.2.4 | Sandbox telemetrisinin bir SIEM'e aktarıldığını doğrulayın; anormallikler (örneğin, yapılan dışa bağlantı girişimleri) uyarılar oluşturur.                                            |   2   |  V   |
| 9.2.5 | Yüksek riskli eklentilerin üretim ortamına dağıtılmadan önce güvenlik incelemesi ve sızma testi sürecinden geçirildiğini doğrulayın.                                                  |   3   |  V   |
| 9.2.6 | Sandbox kaçış girişimlerinin otomatik olarak engellendiğini ve suçlu eklentinin inceleme yapılana kadar karantinaya alındığını doğrulayın.                                            |   3   | D/V  |

---

## 9.3 Otonom Döngü ve Maliyet Sınırlandırma

Kontrolsüz ajanlar arası özyinelemeyi ve maliyet patlamalarını tespit edip durdurun.

|   #   | Description                                                                                                                                      | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 9.3.1 | Aracılar arası çağrıların, çalışma zamanının azalttığı ve uyguladığı bir atlama sınırı veya TTL içerdiğini doğrulayın.                           |   1   | D/V  |
| 9.3.2 | Ajanların kendini çağırma veya döngüsel desenleri tespit etmek için benzersiz bir çağrı-grafiği kimliğini koruduğunu doğrulayın.                 |   2   |  D   |
| 9.3.3 | Kümülatif hesap birimi ve harcama sayaçlarının istek zinciri başına takip edildiğini doğrulayın; limit aşıldığında zincir iptal edilir.          |   2   | D/V  |
| 9.3.4 | Ajan protokollerinde sınırsız özyinelemenin olmadığını göstermek için resmi analiz veya model doğrulama yöntemlerinin kullanıldığını doğrulayın. |   3   |  V   |
| 9.3.5 | Döngü-durdurma olaylarının uyarılar oluşturduğunu ve sürekli iyileştirme metriklerine veri sağladığını doğrulayın.                               |   3   |  D   |

---

## 9.4 Protokol Düzeyi Kötüye Kullanım Koruması

Eleştirmenlik veya manipülasyonu önlemek için ajanlar ile harici sistemler arasında güvenli iletişim kanalları sağlayın.

|   #   | Description                                                                                                                                                 | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.4.1 | Tüm ajan-aracı ve ajan-ajan mesajlarının kimlik doğrulamasının (örneğin, karşılıklı TLS veya JWT) yapıldığını ve uçtan uca şifrelendiğini doğrulayın.       |   1   | D/V  |
| 9.4.2 | Şemaların kesin olarak doğrulandığını teyit edin; bilinmeyen alanlar veya hatalı biçimlendirilmiş mesajlar reddedilir.                                      |   1   |  D   |
| 9.4.3 | Bütün mesaj yükü, araç parametreleri dahil, bütünlüğü doğrulama kontrollerinin (MAC'ler veya dijital imzalar) kapsamına alındığını doğrulayın.              |   2   | D/V  |
| 9.4.4 | Yinelenen saldırı korumasının (tekrar kullanım önleyici nonce'lar veya zaman damgası pencereleri) protokol katmanında uygulanıp uygulanmadığını doğrulayın. |   2   |  D   |
| 9.4.5 | Protokol uygulamalarının enjeksiyon veya serileştirme hataları için fuzz testi ve statik analizden geçtiğini doğrulayın.                                    |   3   |  V   |

---

## 9.5 Ajan Kimliği ve Müdahale Kanıtı

Eylemlerin izlenebilir ve değişikliklerin tespit edilebilir olmasını sağlayın.

|   #   | Description                                                                                                                          | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 9.5.1 | Her ajan örneğinin benzersiz bir kriptografik kimliğe (anahtar çifti veya donanım tabanlı kimlik bilgisi) sahip olduğunu doğrulayın. |   1   | D/V  |
| 9.5.2 | Tüm ajan işlemlerinin imzalandığını ve zaman damgalı olduğunu doğrulayın; günlükler, inkar edilemezlik için imzayı içermelidir.      |   2   | D/V  |
| 9.5.3 | Değişiklik izi gösteren günlüklerin yalnızca ekleme yapılabilen veya bir kere yazılabilen bir ortamda saklandığını doğrulayın.       |   2   |  V   |
| 9.5.4 | Kimlik anahtarlarının belirlenmiş bir programda ve ihlal göstergelerinde döndüğünü doğrulayın.                                       |   3   |  D   |
| 9.5.5 | Sahtecilik veya anahtar çatışması girişimlerinin etkilenen ajanı derhal karantinaya almasını doğrulayın.                             |   3   | D/V  |

---

## 9.6 Çok Ajanlı Sürü Risk Azaltma

Toplu davranış tehlikelerini izolasyon ve resmi güvenlik modellemesi ile hafifletin.

|   #   | Description                                                                                                                                                      | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.6.1 | Farklı güvenlik alanlarında çalışan ajanların izole edilmiş çalışma zamanı kum havuzlarında veya ağ segmentlerinde çalıştığını doğrulayın.                       |   1   | D/V  |
| 9.6.2 | Sürü davranışlarının, dağıtımdan önce canlılık ve güvenlik açısından modellenip resmi olarak doğrulandığını teyit edin.                                          |   3   |  V   |
| 9.6.3 | Çalışma zamanı izleyicilerinin ortaya çıkan güvensiz desenleri (örneğin, salınımlar, kilitlenmeler) tespit ettiğini ve düzeltici eylemi başlattığını doğrulayın. |   3   |  D   |

---

## 9.7 Kullanıcı ve Araç Doğrulaması / Yetkilendirmesi

Her ajan tetiklenen işlem için sağlam erişim kontrolleri uygulayın.

|   #   | Description                                                                                                                                                     | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.7.1 | Ajanların, son kullanıcı kimlik bilgilerini asla yeniden kullanmadan, aşağı akış sistemlerine birinci sınıf yetkililer olarak kimlik doğruladığını doğrulayın.  |   1   | D/V  |
| 9.7.2 | Doğru ve ayrıntılı yetkilendirme politikalarının, bir ajanın hangi araçları çağırabileceğini ve hangi parametreleri sağlayabileceğini sınırladığını doğrulayın. |   2   |  D   |
| 9.7.3 | İzin kontrollerinin sadece oturum başlangıcında değil, her çağrıda yeniden değerlendirildiğini (sürekli yetkilendirme) doğrulayın.                              |   2   |  V   |
| 9.7.4 | Yetkilendirilen ayrıcalıkların otomatik olarak sona erdiğini ve zaman aşımı veya kapsam değişikliği sonrasında yeniden onay gerektirdiğini doğrulayın.          |   3   |  D   |

---

## 9.8 Ajanlar Arası İletişim Güvenliği

Tüm ajanlar arası mesajları dinlemeye ve müdahaleye karşı engellemek için şifreleyin ve bütünlük koruması sağlayın.

|   #   | Description                                                                                                                                     | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.8.1 | Ajan kanalları için karşılıklı kimlik doğrulamanın ve mükemmel ileri gizlilik şifrelemesinin (örn. TLS 1.3) zorunlu olduğunu doğrulayın.        |   1   | D/V  |
| 9.8.2 | İşlemden önce mesaj bütünlüğü ve kaynağının doğrulandığından emin olun; başarısızlık durumunda uyarılar verilir ve mesaj reddedilir.            |   1   |  D   |
| 9.8.3 | İletişim meta verilerinin (zaman damgaları, sıra numaraları) adli inceleme yeniden oluşturmayı destekleyecek şekilde kaydedildiğini doğrulayın. |   2   | D/V  |
| 9.8.4 | Protokol durum makinelerinin güvensiz durumlara sürüklenemeyeceğini resmi doğrulama veya model kontrolü ile doğrulayın.                         |   3   |  V   |

---

## 9.9 Niyet Doğrulama ve Kısıtlama Uygulaması

Ajanın eylemlerinin kullanıcının belirtilen niyeti ve sistem kısıtlamalarıyla uyumlu olduğunu doğrulayın.

|   #   | Description                                                                                                                                                                                   | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.9.1 | Ön yürütme kısıtlama çözücülerinin önerilen eylemleri sabit kodlanmış güvenlik ve politika kurallarına karşı kontrol ettiğini doğrulayın.                                                     |   1   |  D   |
| 9.9.2 | Yüksek etkili eylemlerin (finansal, yıkıcı, gizlilik hassasiyeti içeren) başlatan kullanıcıdan açık niyet onayı gerektirdiğini doğrulayın.                                                    |   2   | D/V  |
| 9.9.3 | Tamamlanmış eylemlerin niyet edilen etkileri yan etkiler olmadan gerçekleştirdiğini doğrulamak için sonrası koşul kontrollerinin yapıldığını doğrulayın; tutarsızlıklar geri almayı tetikler. |   2   |  V   |
| 9.9.4 | Formal yöntemlerin (örneğin, model kontrolü, teorem ispatı) veya özellik tabanlı testlerin, ajan planlarının tüm belirtilen kısıtlamaları sağladığını doğruladığını teyit edin.               |   3   |  V   |
| 9.9.5 | Niyet uyumsuzluğu veya kısıtlama ihlali olaylarının sürekli iyileştirme döngülerine ve tehdit istihbaratı paylaşımına bilgi sağladığını doğrulayın.                                           |   3   |  D   |

---

## 9.10 Ajan Akıl Yürütme Stratejisi Güvenliği

ReAct, Chain-of-Thought ve Tree-of-Thoughts yaklaşımları da dahil olmak üzere farklı akıl yürütme stratejilerinin güvenli seçimi ve yürütülmesi.

|   #    | Description                                                                                                                                                                                                                   | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.10.1 | Sebep belirleme stratejisi seçiminin deterministik kriterler (girdi karmaşıklığı, görev türü, güvenlik bağlamı) kullandığını ve aynı girdilerin aynı güvenlik bağlamı içinde aynı strateji seçimini ürettiğini doğrulayın.    |   1   | D/V  |
| 9.10.2 | Her akıl yürütme stratejisinin (ReAct, Düşünce Zinciri, Düşünce Ağacı) kendi bilişsel yaklaşımına özgü giriş doğrulaması, çıktı temizleme ve yürütme süre sınırlarına sahip olduğunu doğrulayın.                              |   1   | D/V  |
| 9.10.3 | Denetim izi yeniden inşası için, gerekçelendirme stratejisi geçişlerinin giriş özellikleri, seçim kriter değerleri ve yürütme meta verileri dahil olmak üzere eksiksiz bağlamla kaydedildiğini doğrulayın.                    |   2   | D/V  |
| 9.10.4 | Tree-of-Thoughts muhakemesinin, politika ihlalleri, kaynak sınırları veya güvenlik sınırları tespit edildiğinde keşfi sonlandıran dal budama mekanizmalarını içerdiğini doğrulayın.                                           |   2   | D/V  |
| 9.10.5 | ReAct (Reason-Act-Observe) döngülerinin her aşamada doğrulama kontrol noktalarını içerdiğini doğrulayın: mantık adımı doğrulaması, eylem yetkilendirmesi ve devam etmeden önce gözlem temizliği.                              |   2   | D/V  |
| 9.10.6 | Akıl yürütme stratejisi performans metriklerinin (çalışma süresi, kaynak kullanımı, çıktı kalitesi) yapılandırılmış eşiklerin ötesinde sapma gösterdiğinde otomatik uyarılarla izlenip izlenmediğini doğrulayın.              |   3   | D/V  |
| 9.10.7 | Birden fazla stratejiyi birleştiren hibrit akıl yürütme yaklaşımlarının, herhangi bir güvenlik kontrolünü atlamadan, tüm bileşen stratejilerin giriş doğrulamasını ve çıkış kısıtlamalarını koruduğunu doğrulayın.            |   3   | D/V  |
| 9.10.8 | Akıl yürütme stratejisi güvenlik testlerinin, bozuk girdilerle fuzz testini, strateji değişikliğini zorlamak için tasarlanmış düşmanca uyarıları ve her bilişsel yaklaşım için sınır durumu testlerini içerdiğini doğrulayın. |   3   | D/V  |

---

## 9.11 Ajan Yaşam Döngüsü Durumu Yönetimi ve Güvenliği

Kriptografik denetim izleri ve tanımlı kurtarma prosedürleri ile güvenli ajan başlatma, durum geçişleri ve sonlandırma.

|   #    | Description                                                                                                                                                                                                                                                                   | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.11.1 | Ajan başlatmanın, donanım destekli kimlik bilgileri ile kriptografik kimlik oluşturmayı ve ajan kimliği, zaman damgası, yapılandırma karması ve başlatma parametrelerini içeren değişmez başlangıç denetim kayıtlarını içerdiğini doğrulayın.                                 |   1   | D/V  |
| 9.11.2 | Agent durum geçişlerinin kriptografik olarak imzalandığını, zaman damgalandığını ve tetikleyici olaylar, önceki durum karması, yeni durum karması ve gerçekleştirilen güvenlik doğrulamaları dahil olmak üzere tam bağlamıyla kaydedildiğini doğrulayın.                      |   2   | D/V  |
| 9.11.3 | Ajan kapatma prosedürlerinin kriptografik silme veya çoklu geçişli üzerine yazma yoluyla güvenli bellek temizlemeyi, sertifika otoritesi bildirimli kimlik bilgisi iptalini ve müdahale kanıtlı sonlandırma sertifikalarının oluşturulmasını içerdiğini doğrulayın.           |   2   | D/V  |
| 9.11.4 | Ajan kurtarma mekanizmalarının, durum bütünlüğünü kriptografik özetler (en az SHA-256) kullanarak doğruladığını ve bozulma tespit edildiğinde otomatik uyarılarla ve manuel onay gereksinimleriyle bilinen iyi durumlara geri döndüğünü doğrulayın.                           |   3   | D/V  |
| 9.11.5 | Ajan kalıcılık mekanizmalarının, ajan başına AES-256 anahtarlarıyla hassas durum verilerini şifrelediğini ve yapılandırılabilir zaman çizelgelerinde (en fazla 90 gün) güvenli anahtar döndürme işlemi gerçekleştirdiğini, sıfır kesinti ile dağıtımı sağladığını doğrulayın. |   3   | D/V  |

---

## 9.12 Araç Entegrasyon Güvenlik Çerçevesi

Tanımlanmış risk değerlendirmesi ve onay süreçleri ile dinamik araç yükleme, yürütme ve sonuç doğrulama için güvenlik kontrolleri.

|   #    | Description                                                                                                                                                                                                                                                                   | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.12.1 | Araç tanımlayıcılarının, gerekli ayrıcalıkları (okuma/yazma/çalıştırma), risk seviyelerini (düşük/orta/yüksek), kaynak sınırlarını (CPU, hafıza, ağ) ve araç manifestolarında belgelenmiş doğrulama gereksinimlerini belirten güvenlik meta verilerini içerdiğini doğrulayın. |   1   | D/V  |
| 9.12.2 | Araç yürütme sonuçlarının, zaman aşımı sınırları ve hata işleme prosedürleri ile entegrasyon öncesinde beklenen şemalara (JSON Şeması, XML Şeması) ve güvenlik politikalarına (çıktı temizleme, veri sınıflandırması) karşı doğrulandığından emin olun.                       |   1   | D/V  |
| 9.12.3 | Araç etkileşim günlüklerinin, ayrıcalık kullanımı, veri erişim desenleri, yürütme süresi, kaynak tüketimi ve dönüş kodları dahil olmak üzere ayrıntılı güvenlik bağlamını içerdiğini ve SIEM entegrasyonu için yapılandırılmış günlük kaydını doğrulayın.                     |   2   | D/V  |
| 9.12.4 | Dinamik araç yükleme mekanizmalarının, PKI altyapısını kullanarak dijital imzaları doğruladığını ve yürütmeden önce sandbox izolasyonu ve izin doğrulaması ile güvenli yükleme protokolleri uyguladığını doğrulayın.                                                          |   2   | D/V  |
| 9.12.5 | Araç güvenlik değerlendirmelerinin, statik analiz, dinamik test ve güvenlik ekibi incelemesi gibi zorunlu onay kapılarıyla birlikte, belgelenmiş onay kriterleri ve SLA gereksinimlerini içeren otomatik olarak yeni sürümler için tetiklendiğini doğrulayın.                 |   3   | D/V  |

---

### Referanslar

* [MITRE ATLAS tactics ML09](https://atlas.mitre.org/)
* [Circuit-breaker research for AI agents — Zou et al., 2024](https://arxiv.org/abs/2406.04313)
* [Trend Micro analysis of sandbox escapes in AI agents — Park, 2025](https://www.trendmicro.com/vinfo/us/security/news/cybercrime-and-digital-threats/unveiling-ai-agent-vulnerabilities-code-execution)
* [Auth0 guidance on human-in-the-loop authorization for agents — Martinez, 2025](https://auth0.com/blog/secure-human-in-the-loop-interactions-for-ai-agents/)
* [Medium deep-dive on MCP & A2A protocol hijacking — ForAISec, 2025](https://medium.com/%40foraisec/security-analysis-potential-ai-agent-hijacking-via-mcp-and-a2a-protocol-insights-cd1ec5e6045f)
* [Rapid7 fundamentals on spoofing attack prevention — 2024](https://www.rapid7.com/fundamentals/spoofing-attacks/)
* [Imperial College verification of swarm systems — Lomuscio et al.](https://sail.doc.ic.ac.uk/projects/swarms/)
* [NIST AI Risk Management Framework 1.0, 2023](https://nvlpubs.nist.gov/nistpubs/ai/nist.ai.100-1.pdf)
* [WIRED security briefing on encryption best practices, 2024](https://www.wired.com/story/encryption-apps-chinese-telecom-hacking-hydra-russia-exxon)
* [OWASP Top 10 for LLM Applications, 2025](https://owasp.org/www-project-top-10-for-large-language-model-applications/)
* [Comprehensive Vulnerability Analysis is Necessary for Trustworthy LLM-MAS](https://arxiv.org/html/2506.01245v1)
* [How Is LLM Reasoning Distracted by Irrelevant Context?
  An Analysis Using a Controlled Benchmark](https://www.arxiv.org/pdf/2505.18761)
* [Large Language Model Sentinel: LLM Agent for Adversarial Purification](https://arxiv.org/pdf/2405.20770)
* [Securing Agentic AI: A Comprehensive Threat Model and Mitigation Framework for Generative AI Agents](https://arxiv.org/html/2504.19956v2)

