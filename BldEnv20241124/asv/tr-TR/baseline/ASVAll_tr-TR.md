## Önsöz

### Standart Hakkında

Yapay Zeka Güvenlik Doğrulama Standardı (AISVS), veri bilimciler, MLOps mühendisleri, yazılım mimarları, geliştiriciler, test uzmanları, güvenlik profesyonelleri, araç satıcıları, düzenleyiciler ve kullanıcıların güvenilir yapay zeka destekli sistemler ve uygulamalar tasarlamak, oluşturmak, test etmek ve doğrulamak için kullanabileceği topluluk odaklı bir güvenlik gereksinimleri kataloğudur. AI yaşam döngüsü boyunca—veri toplama ve model geliştirmeden dağıtım ve sürekli izlemeye kadar—güvenlik kontrollerini belirtmek için ortak bir dil sağlar, böylece organizasyonlar AI çözümlerinin dayanıklılığını, gizliliğini ve güvenliğini ölçebilir ve geliştirebilir.

### Telif Hakkı ve Lisans

Sürüm 0.1 (İlk Halka Açık Taslak - Çalışma Devam Ediyor), 2025  

![license](images/license.png)
Telif Hakkı © 2025 AISVS Projesi.  

Altında yayımlanmıştırCreative Commons Attribution‑ShareAlike 4.0 International License.
Herhangi bir yeniden kullanım veya dağıtım için, bu çalışmanın lisans şartlarını başkalarına açıkça iletmelisiniz.

### Proje Liderleri

Jim Manico
Aras “Russ” Memisyazici

### Katkıda Bulunanlar ve İnceleyenler

https://github.com/ottosulin
https://github.com/mbhatt1
https://github.com/vineethsai
https://github.com/cciprofm
https://github.com/deepakrpandey12


---

AISVS, yapay zeka sistemlerinin benzersiz güvenlik zorluklarını özel olarak ele almak için oluşturulmuş yepyeni bir standarttır. Daha geniş güvenlik en iyi uygulamalarından ilham almakla birlikte, AISVS'deki her gereksinim, AI tehdit ortamını yansıtmak ve organizasyonların daha güvenli, daha dayanıklı yapay zeka çözümleri geliştirmelerine yardımcı olmak amacıyla baştan sona geliştirilmiştir.

## Önsöz

Yapay Zeka Güvenlik Doğrulama Standardı (AISVS) sürüm 1.0'a hoş geldiniz!

### Giriş

2025 yılında topluluk işbirliğiyle kurulan AISVS, modern yapay zeka modelleri, boru hatları ve yapay zeka destekli hizmetlerin tasarımı, geliştirilmesi, dağıtımı ve işletilmesi sırasında dikkate alınması gereken güvenlik gereksinimlerini tanımlar.

AISVS v1.0, AI sistemlerini güvence altına almak için pragmatik ve test edilebilir bir temel oluşturmak amacıyla proje liderleri, çalışma grubu ve daha geniş topluluk katkıcılarının ortak çalışmasını temsil eder.

Bu sürümle amacımız, AISVS'yi benimsemeyi basitleştirmek ve tanımlanmış kapsamına odaklanırken yapay zekaya özgü hızla gelişen risk ortamını ele almaktır.

### AISVS Sürüm 1.0 için Temel Hedefler

Sürüm 1.0, birkaç rehber ilke ile oluşturulacaktır.

#### İyi Tanımlanmış Kapsam

Her gereksinim AISVS’nin adı ve misyonuyla uyumlu olmalıdır:

Yapay Zeka – Kontroller, AI/ML katmanında (veri, model, iş akışı ya da çıkarım) çalışır ve AI uygulayıcılarının sorumluluğundadır.
Güvenlik – Gereksinimler, belirlenen güvenlik, gizlilik veya emniyet risklerini doğrudan hafifletir.
Doğrulama – Dil, uyumluluğun nesnel olarak doğrulanabilmesi için yazılmıştır.
Standart – Bölümler, tutarlı bir yapı ve terminoloji izleyerek uyumlu bir referans oluşturur.
​
---

AISVS'yi takip ederek, organizasyonlar AI çözümlerinin güvenlik duruşunu sistematik olarak değerlendirebilir ve güçlendirebilir, böylece güvenli AI mühendisliği kültürünü teşvik edebilirler.

## AISVS Kullanarak

Yapay Zeka Güvenlik Doğrulama Standardı (AISVS), modern yapay zeka uygulamaları ve hizmetleri için, uygulama geliştiricilerin kontrolü altındaki yönlere odaklanarak güvenlik gereksinimlerini tanımlar.

AISVS, geliştiriciler, mimarlar, güvenlik mühendisleri ve denetçiler de dahil olmak üzere AI uygulamalarının güvenliğini geliştiren veya değerlendiren herkes için tasarlanmıştır. Bu bölüm, AISVS'nin yapısı ve kullanımı, doğrulama seviyeleri ve hedeflenen kullanım durumları hakkında bilgi vermektedir.

### Yapay Zeka Güvenlik Doğrulama Seviyeleri

AISVS, üç yükselen güvenlik doğrulama seviyesi tanımlar. Her seviye, derinlik ve karmaşıklık ekleyerek, organizasyonların güvenlik duruşlarını AI sistemlerinin risk seviyesine göre özelleştirmelerine olanak tanır.

Kuruluşlar, güvenlik olgunluğu ve tehdit maruziyeti arttıkça Seviyeden başlayarak kademeli olarak daha yüksek seviyeleri benimseyebilir.

#### Seviyelerin Tanımı

AISVS v1.0'daki her gereksinim aşağıdaki seviyelerden birine atanmıştır:

 Seviye 1 gereksinimleri

Seviye 1, en kritik ve temel güvenlik gereksinimlerini içerir. Bunlar, diğer ön koşullara veya zafiyetlere dayanmadığı için yaygın saldırıları önlemeye odaklanır. Seviye 1 kontrollerinin çoğu ya uygulanması basit ya da çabaya değecek kadar hayati öneme sahiptir.

 Seviye 2 gereksinimleri

Seviye 2, daha gelişmiş veya daha az yaygın saldırıları ve yaygın tehditlere karşı katmanlı savunmaları ele alır. Bu gereksinimler, daha karmaşık mantık içerebilir veya belirli saldırı önkoşullarını hedefleyebilir.

 Seviye 3 gereksinimleri

Seviye 3, genellikle uygulanması daha zor veya durumsal olarak geçerli olan kontrolleri içerir. Bunlar genellikle derinlemesine savunma mekanizmalarını veya niş, hedeflenmiş ya da yüksek karmaşıklığa sahip saldırılara karşı hafifletmeleri temsil eder.

#### Rol (D/V)

Her AISVS gereksinimi, birincil hedef kitleye göre işaretlenir:

D – Geliştirici odaklı gereksinimler
V – Doğrulayıcı/denetçi odaklı gereksinimler
D/V – Hem geliştiriciler hem doğrulayıcılar için ilgili

## C1 Eğitim Veri Yönetişimi ve Önyargı Yönetimi

### Kontrol Hedefi

Eğitim verileri, köken, güvenlik, kalite ve adaleti koruyacak şekilde temin edilmeli, işlenmeli ve muhafaza edilmelidir. Böyle yapmak, yasal yükümlülükleri yerine getirir ve yapay zeka yaşam döngüsü boyunca önyargı, zehirlenme veya gizlilik ihlali risklerini azaltır.

---

### C1.1 Eğitim Verisi Kökeni

Tüm veri setlerinin doğrulanabilir envanterini tutun, yalnızca güvenilir kaynakları kabul edin ve denetlenebilirlik için her değişikliği kaydedin.

 #1.1.1    Level: 1    Role: D/V
 Her eğitim veri kaynağının (kaynak, sorumlu/sahip, lisans, toplama yöntemi, amaçlanan kullanım kısıtlamaları ve işleme geçmişi) güncel bir envanterinin tutulduğunu doğrulayın.
 #1.1.2    Level: 1    Role: D/V
 Sadece kalite, temsil yeteneği, etik kaynak kullanımı ve lisans uyumluluğu açısından incelenmiş veri setlerinin kabul edildiğini doğrulayın; böylece zehirlenme, yerleşik önyargı ve fikri mülkiyet ihlali riskleri azaltılır.
 #1.1.3    Level: 1    Role: D/V
 Gereksiz veya hassas özniteliklerin hariç tutulduğundan emin olmak için veri minimizasyonunun uygulandığını doğrulayın.
 #1.1.4    Level: 2    Role: D/V
 Tüm veri seti değişikliklerinin kaydedilen onay iş akışına tabi olduğunu doğrulayın.
 #1.1.5    Level: 2    Role: D/V
 Etiketleme/yorumlama kalitesinin, değerlendirici çapraz kontrolleri veya uzlaşması yoluyla sağlandığını doğrulayın.
 #1.1.6    Level: 2    Role: D/V
 Önemli eğitim veri setleri için "veri kartlarının" veya "veri setleri için veri sayfalarının" tutulduğunu doğrulayın; bu kartlarda özellikler, motivasyonlar, bileşim, toplama süreçleri, ön işleme ve önerilen/önerilmeyen kullanım şekilleri detaylandırılmış olmalıdır.

---

### C1.2 Eğitim Verisi Güvenliği ve Bütünlüğü

Erişimi kısıtlayın, verileri kalıcı ve aktarım sırasında şifreleyin ve bütünlüğü doğrulayarak müdahale veya hırsızlığı engelleyin.

 #1.2.1    Level: 1    Role: D/V
 Erişim kontrollerinin depolama ve veri boru hatlarını koruduğunu doğrulayın.
 #1.2.2    Level: 2    Role: D/V
 Veri setlerinin, tüm hassas veya kişisel olarak tanımlanabilir bilgiler (PII) için, endüstri standartlarındaki kriptografik algoritmalar ve anahtar yönetim uygulamaları kullanılarak, iletim sırasında ve dinlenirken şifrelenmiş olduğunu doğrulayın.
 #1.2.3    Level: 2    Role: D/V
 Veri bütünlüğünün depolama ve transfer sırasında sağlanması için kriptografik özetlerin veya dijital imzaların kullanıldığını ve yetkisiz değişiklikler veya bozulmalar, özellikle hedeflenmiş veri zehirleme girişimlerine karşı korunmak amacıyla otomatik anomali tespit tekniklerinin uygulandığını doğrulayın.
 #1.2.4    Level: 3    Role: D/V
 Veri kümesi sürümlerinin geri alma işlemini mümkün kılacak şekilde takip edildiğini doğrulayın.
 #1.2.5    Level: 2    Role: D/V
 Veri saklama politikları, düzenleyici gereklilikler ile uyumlu olarak geçersiz verilerin güvenli bir şekilde silindiğini veya anonimleştirildiğini doğrulayın ve böylece saldırı yüzeyini azaltın.

---

### C1.3 Temsil Tamlığı ve Adalet

Demografik eğilimleri tespit edin ve modelin hata oranlarının gruplar arasında eşit olmasını sağlamak için düzeltme uygulayın.

 #1.3.1    Level: 1    Role: D/V
 Veri setlerinin, temsil dengesizliği ve yasal olarak korunan özellikler (örneğin, ırk, cinsiyet, yaş) ile modelin uygulama alanına ilişkin diğer etik açıdan hassas özellikler (örneğin, sosyo-ekonomik durum, konum) bazında potansiyel önyargılar açısından incelendiğini doğrulayın.
 #1.3.2    Level: 2    Role: D/V
 Belirlenen önyargıların, yeniden dengeleme, hedeflenmiş veri artırımı, algoritmik ayarlamalar (örneğin, ön işleme, işlem sırasında ve işlem sonrası teknikler) veya yeniden ağırlıklandırma gibi belgelenmiş stratejilerle giderildiğini doğrulayın ve giderme işleminin hem adalet hem de genel model performansı üzerindeki etkisinin değerlendirildiğinden emin olun.
 #1.3.3    Level: 2    Role: D/V
 Eğitim sonrası adalet metriklerinin değerlendirildiğini ve belgelenmesini doğrulayın.
 #1.3.4    Level: 3    Role: D/V
 Bir yaşam döngüsü yanlılık yönetimi politikasının sahipleri ve inceleme sıklığını atadığını doğrulayın.

---

### C1.4 Eğitim Verisi Etiketleme Kalitesi, Bütünlüğü ve Güvenliği

Etiketleri şifreleme ile koruyun ve kritik sınıflar için çift inceleme gerektirin.

 #1.4.1    Level: 2    Role: D/V
 Etiketleme/yorumlama kalitesinin, açık yönergeler, inceleyici çapraz kontrolleri, uzlaşma mekanizmaları (örneğin, anotatörler arası uyumun izlenmesi) ve uyuşmazlıkları çözmek için tanımlanmış süreçler aracılığıyla sağlandığını doğrulayın.
 #1.4.2    Level: 2    Role: D/V
 Etiket artefaktlarına bütünlüklerini ve özgünlüklerini sağlamak amacıyla kriptografik özetlerin veya dijital imzaların uygulandığını doğrulayın.
 #1.4.3    Level: 2    Role: D/V
 Etiketleme arayüzlerinin ve platformlarının güçlü erişim kontrolleri uyguladığını, tüm etiketleme faaliyetlerinin değiştirilemez denetim kayıtlarını tuttuğunu ve yetkisiz değişikliklere karşı koruma sağladığını doğrulayın.
 #1.4.4    Level: 3    Role: D/V
 Güvenlik, emniyet veya adalet açısından kritik olan etiketlerin (örneğin, toksik içeriğin tanımlanması, kritik tıbbi bulgular) zorunlu bağımsız çift inceleme veya eşdeğer sağlam doğrulamadan geçmesini sağlayın.
 #1.4.5    Level: 2    Role: D/V
 Etiketlerde yanlışlıkla yakalanan veya zorunlu olarak bulunan hassas bilgilerin (kişisel tanımlayıcı bilgiler dahil) veri minimizasyonu prensiplerine uygun olarak, dinlenme halinde ve iletim sırasında sansürlendiği, takma ad kullanıldığı, anonimleştirildiği veya şifrelendiği doğrulanmalıdır.
 #1.4.6    Level: 2    Role: D/V
 Etiketleme rehberlerinin ve talimatlarının kapsamlı, sürüm kontrolüne tabi ve meslektaş incelemesinden geçmiş olduğunu doğrulayın.
 #1.4.7    Level: 2    Role: D/V
 Veri şemalarının (etiketler dahil) net bir şekilde tanımlandığını ve sürüm kontrolünün yapıldığını doğrulayın.
 #1.8.2    Level: 2    Role: D/V
 Dış kaynaklı veya kitle kaynaklı etiketleme iş akışlarının, veri gizliliği, bütünlüğü, etiket kalitesi sağlama ve veri sızıntısını önleme için teknik/prosedürel güvenlik önlemlerini içerdiğini doğrulayın.

---

### C1.5 Eğitim Verisi Kalite Güvencesi

Otomatik doğrulama, manuel rastgele kontroller ve kaydedilen iyileştirmeleri birleştirerek veri seti güvenilirliğini garanti altına alın.

 #1.5.1    Level: 1    Role: D
 Otomatik testlerin, her veri alımında veya önemli bir dönüşümde format hatalarını, boş değerleri ve etiket kaymalarını yakaladığını doğrulayın.
 #1.5.2    Level: 1    Role: D/V
 Başarısız veri setlerinin denetim izleriyle karantinaya alındığını doğrulayın.
 #1.5.3    Level: 2    Role: V
 Alan uzmanları tarafından yapılan manuel nokta kontrollerinin, otomasyon tarafından yakalanamayan ince kalite sorunlarını tespit etmek için istatistiksel olarak anlamlı bir örneklem (örneğin, ≥%1 veya 1.000 örnek, hangisi büyükse veya risk değerlendirmesi ile belirlenen) kapsadığını doğrulayın.
 #1.5.4    Level: 2    Role: D/V
 Düzeltme adımlarının kaynak kayıtlarına eklendiğini doğrulayın.
 #1.5.5    Level: 2    Role: D/V
 Kalite kapılarının, istisnalar onaylanmadıkça standart altı veri kümelerini engellediğini doğrulayın.

---

### C1.6 Veri Zehirleme Tespiti

İstatistiksel anomali tespiti ve karantina iş akışlarını uygulayarak düşmanca eklemeleri durdurun.

 #1.6.1    Level: 2    Role: D/V
 Anomali tespit tekniklerinin (örneğin, istatistiksel yöntemler, aykırı değer tespiti, gömme analizi) potansiyel zehirlenme saldırılarını veya istem dışı veri bozulmalarını belirlemek için veri alımı sırasında ve önemli eğitim çalışmaları öncesinde eğitim verisine uygulandığını doğrulayın.
 #1.6.2    Level: 2    Role: D/V
 İşaretlenen örneklerin eğitimden önce manuel incelemeyi tetiklediğini doğrulayın.
 #1.6.3    Level: 2    Role: V
 Sonuçların modelin güvenlik dosyasını beslediğini ve devam eden tehdit istihbaratını bilgilendirdiğini doğrulayın.
 #1.6.4    Level: 3    Role: D/V
 Tespit mantığının yeni tehdit istihbaratı ile güncellendiğini doğrulayın.
 #1.6.5    Level: 3    Role: D/V
 Çevrimiçi öğrenme boru hatlarının dağılım kaymasını izlediğini doğrulayın.
 #1.6.6    Level: 3    Role: D/V
 Sistem risk profili ve veri kaynaklarına göre bilinen veri zehirleme saldırı türlerine (örneğin, etiket çevirme, arka kapı tetikleyici ekleme, etkili örnek saldırıları) karşı belirli savunmaların göz önünde bulundurulup uygulanmasını doğrulayın.

---

### C1.7 Kullanıcı Verisi Silme ve Onay Uygulaması

Veri setleri, yedekler ve türetilmiş ürünler genelinde silme ve onay çekme taleplerine uyun.

 #1.7.1    Level: 1    Role: D/V
 Silme iş akışlarının birincil ve türetilmiş verileri tamamen kaldırdığını doğrulayın ve model üzerindeki etkisini değerlendirin; etkilenen modeller üzerindeki etkinin gerektiğinde (örneğin, yeniden eğitim veya yeniden kalibrasyon yoluyla) ele alındığından emin olun.
 #1.7.2    Level: 2    Role: D
 Kullanıcı onayının kapsamını ve durumunu (ve geri çekilmelerini) izlemek ve saygı göstermek için mekanizmaların mevcut olduğunu doğrulayın ve veriler yeni eğitim süreçlerine veya önemli model güncellemelerine dahil edilmeden önce onayın geçerli olduğunu teyit edin.
 #1.7.3    Level: 2    Role: V
 İş akışlarının yıllık olarak test edildiğini ve kaydedildiğini doğrulayın.

---

### C1.8 Tedarik Zinciri Güvenliği

Harici veri sağlayıcılarını değerlendirin ve kimlik doğrulamalı, şifrelenmiş kanallar üzerinden bütünlüğünü doğrulayın.

 #1.8.1    Level: 2    Role: D/V
 Üçüncü taraf veri tedarikçilerinin, önceden eğitilmiş modeller ve dış veri setleri sağlayıcıları dahil olmak üzere, verileri veya modelleri entegre edilmeden önce güvenlik, gizlilik, etik kaynak sağlama ve veri kalitesi konularında titiz incelemeye tabi tutulduğunu doğrulayın.
 #1.8.2    Level: 1    Role: D
 Dış transferlerin TLS/doğrulama ve bütünlük kontrolleri kullandığını doğrulayın.
 #1.8.3    Level: 2    Role: D/V
 Yüksek riskli veri kaynaklarının (örneğin, kaynağı bilinmeyen açık kaynak veri setleri, denetlenmemiş tedarikçiler) hassas uygulamalarda kullanılmadan önce sızdırmaz ortamda analiz, kapsamlı kalite/önyargı kontrolleri ve hedeflenmiş zehirlenme tespiti gibi artırılmış denetime tabi tutulduğundan emin olun.
 #1.8.4    Level: 3    Role: D/V
 Üçüncü taraflardan elde edilen önceden eğitilmiş modellerin, ince ayar yapılmadan veya dağıtıma alınmadan önce gömülü önyargılar, potansiyel arka kapılar, mimari bütünlüğü ve orijinal eğitim verilerinin kaynağı açısından değerlendirildiğini doğrulayın.

---

### C1.9 Adversarial Örnek Tespiti

Eğitim aşamasında, modelin rakip örneklere karşı dayanıklılığını artırmak için rakip eğitim gibi önlemler uygulayın.

 #1.9.1    Level: 3    Role: D/V
 İlgili modeller için risk değerlendirmesine dayanarak oluşturulan saldırgan örnekler kullanılarak yapılan saldırgan eğitim, bozulmuş girişlerle veri artırımı veya sağlam optimizasyon teknikleri gibi uygun savunmaların uygulanıp uygulanmadığını ve ayarlandığını doğrulayın.
 #1.9.2    Level: 2    Role: D/V
 Eğer düşmanca eğitim kullanılıyorsa, düşmanca veri kümelerinin oluşturulması, yönetimi ve sürüm kontrolünün belgelenip kontrol edildiğini doğrulayın.
 #1.9.3    Level: 3    Role: D/V
 Model performansı (hem temiz hem de saldırgan girişlere karşı) ve adalet metrikleri üzerindeki adversarial sağlamlık eğitiminin etkisinin değerlendirilmesini, belgelenmesini ve izlenmesini doğrulayın.
 #1.9.4    Level: 3    Role: D/V
 Evrimleşen düşmanca saldırı tekniklerine karşı koymak için düşmanca eğitim ve dayanıklılık stratejilerinin periyodik olarak gözden geçirilip güncellendiğini doğrulayın.

---

### C1.10 Veri Soyu ve İzlenebilirlik

Denetim ve olay müdahalesi için her veri noktasının kaynaktan modele girişine kadar tüm yolculuğunu takip edin.

 #1.10.1    Level: 2    Role: D/V
 Her veri noktasının kökeninin, tüm dönüşümler, artırmalar ve birleştirmeler dahil olmak üzere, kaydedildiğini ve yeniden oluşturulabileceğini doğrulayın.
 #1.10.2    Level: 2    Role: D/V
 Soy kütüğü kayıtlarının değiştirilemez, güvenli bir şekilde saklanmış ve denetimler veya soruşturmalar için erişilebilir olduğunu doğrulayın.
 #1.10.3    Level: 2    Role: D/V
 Soy takip sisteminin hem ham hem de sentetik veriyi kapsadığından emin olun.

---

### C1.11 Sentetik Veri Yönetimi

Sentetik verilerin doğru şekilde yönetildiğinden, etiketlendiğinden ve risk değerlendirmesinin yapıldığından emin olun.

 #1.11.1    Level: 2    Role: D/V
 Tüm sentetik verilerin, boru hattı boyunca gerçek verilerden açıkça etiketlendiğini ve ayırt edilebilir olduğunu doğrulayın.
 #1.11.2    Level: 2    Role: D/V
 Sentetik verinin oluşturulma sürecinin, parametrelerinin ve amaçlanan kullanımının belgelenmiş olduğunu doğrulayın.
 #1.11.3    Level: 2    Role: D/V
 Sentetik verilerin eğitimde kullanılmadan önce önyargı, gizlilik sızıntısı ve temsil sorunları açısından risk değerlendirmesinin yapıldığını doğrulayın.

---

### C1.12 Veri Erişim İzleme ve Anomali Tespiti

Eğitim verilerine olağandışı erişimi izleyin ve uyarı verin, iç tehditleri veya dışa aktarımı tespit etmek için.

 #1.12.1    Level: 2    Role: D/V
 Eğitim verilerine yapılan tüm erişimlerin, kullanıcı, zaman ve işlem dahil olmak üzere kaydedildiğinden emin olun.
 #1.12.2    Level: 2    Role: D/V
 Erişim günlüklerinin, büyük veri dışa aktarımları veya yeni konumlardan erişim gibi olağandışı kalıplar açısından düzenli olarak incelendiğini doğrulayın.
 #1.12.3    Level: 2    Role: D/V
 Şüpheli erişim olayları için uyarıların oluşturulduğunu ve derhal araştırıldığını doğrulayın.

---

### C1.13 Veri Saklama ve Süre Sonu Politikaları

Gereksiz veri depolamayı en aza indirmek için veri saklama sürelerini tanımlayın ve uygulayın.

 #1.13.1    Level: 1    Role: D/V
 Tüm eğitim veri setleri için açık saklama sürelerinin tanımlandığını doğrulayın.
 #1.13.2    Level: 2    Role: D/V
 Veri setlerinin yaşam döngülerinin sonunda otomatik olarak süresinin dolduğundan, silindiğinden veya silinme için incelendiğinden emin olun.
 #1.13.3    Level: 2    Role: D/V
 Saklama ve silme işlemlerinin kaydedildiğini ve denetlenebilir olduğunu doğrulayın.

---

### C1.14 Düzenleyici ve Yargı Uyumu

Tüm eğitim verilerinin geçerli yasa ve yönetmeliklere uygun olduğundan emin olun.

 #1.14.1    Level: 2    Role: D/V
 Tüm veri setleri için veri yerleşimi ve sınır ötesi transfer gereksinimlerinin belirlenip uygulanmasını doğrulayın.
 #1.14.2    Level: 2    Role: D/V
 Sektörlere özgü düzenlemelerin (örneğin, sağlık, finans) veri işleme sürecinde tanımlandığını ve ele alındığını doğrulayın.
 #1.14.3    Level: 2    Role: D/V
 İlgili gizlilik yasalarına (ör. GDPR, CCPA) uyumun belgelendiğini ve düzenli olarak gözden geçirildiğini doğrulayın.

---

### C1.15 Veri Filigranlama ve Parmak İzi Oluşturma

Yetkisiz yeniden kullanımını veya sahipli ya da hassas verilerin sızdırılmasını tespit edin.

 #1.15.1    Level: 3    Role: D/V
 Veri kümelerinin veya alt kümelerin mümkün olan yerlerde dijital filigranla işaretlendiğini veya parmak iziyle tanımlandığını doğrulayın.
 #1.15.2    Level: 3    Role: D/V
 Filigranlama/parmak izi yöntemlerinin önyargı veya gizlilik riski oluşturmadığını doğrulayın.
 #1.15.3    Level: 3    Role: D/V
 Filigranlı verinin yetkisiz yeniden kullanımı veya sızıntısını tespit etmek için düzenli kontrollerin yapıldığını doğrulayın.

---

### C1.16 Veri Sahibi Hakları Yönetimi

Erişim, düzeltme, kısıtlama ve itiraz gibi veri sahiplerinin haklarını destekleyin.

 #1.16.1    Level: 2    Role: D/V
 Veri sahibinin erişim, düzeltme, kısıtlama veya itiraz taleplerine yanıt vermek için mekanizmaların mevcut olduğunu doğrulayın.
 #1.16.2    Level: 2    Role: D/V
 İsteklerin yasal olarak belirlenmiş zaman dilimleri içinde kaydedildiğini, izlendiğini ve yerine getirildiğini doğrulayın.
 #1.16.3    Level: 2    Role: D/V
 Veri konusu kişilerin hak süreçlerinin etkinliği için düzenli olarak test edildiğini ve gözden geçirilmesini doğrulayın.

---

### C1.17 Veri Seti Sürümünün Etki Analizi

Sürümleri güncellemeden veya değiştirmeden önce veri kümesi değişikliklerinin etkisini değerlendirin.

 #1.17.1    Level: 2    Role: D/V
 Bir veri kümesi sürümü güncellenmeden veya değiştirilmeden önce, model performansı, adillik ve uyumluluğu kapsayan bir etki analizinin yapıldığını doğrulayın.
 #1.17.2    Level: 2    Role: D/V
 Etkileşim analizinin sonuçlarının ilgili paydaşlar tarafından belgelenip incelendiğini doğrulayın.
 #1.17.3    Level: 2    Role: D/V
 Yeni sürümler kabul edilemez riskler veya gerilemeler getirdiğinde kullanılmak üzere geri alma planlarının var olduğunu doğrulayın.

---

### C1.18 Veri Etiketleme İşgücü Güvenliği

Veri anotasyonunda yer alan personelin güvenliğini ve bütünlüğünü sağlamak.

 #1.18.1    Level: 2    Role: D/V
 Veri açıklamasıyla ilgili tüm personelin geçmiş kontrollerinin yapıldığını ve veri güvenliği ile gizliliği konusunda eğitim aldığını doğrulayın.
 #1.18.2    Level: 2    Role: D/V
 Tüm anotasyon personelinin gizlilik ve ifşa etmeme sözleşmelerini imzaladığını doğrulayın.
 #1.18.3    Level: 2    Role: D/V
 Notasyon platformlarının erişim kontrollerini uyguladığını ve içeriden gelen tehditler için izleme yaptığını doğrulayın.

---

### Referanslar

NIST AI Risk Management Framework
EU AI Act – Article 10: Data & Data Governance
MITRE ATLAS: Adversary Tactics for AI
Survey of ML Bias Mitigation Techniques – MDPI
Data Provenance & Lineage Best Practices – Nightfall AI
Data Labeling Quality Standards – LabelYourData
Training Data Poisoning Guide – Lakera.ai
CISA Advisory: Securing Data for AI Systems
ISO/IEC 23053: AI Management Systems Framework
IBM: What is AI Governance?
Google AI Principles
GDPR & AI Training Data – DataProtectionReport
Supply-Chain Security for AI Data – AppSOC
OpenAI Privacy Center – Data Deletion Controls
Adversarial ML Dataset – Kaggle

## C2 Kullanıcı Girişi Doğrulaması

### Kontrol Hedefi

Kullanıcı girdisinin sağlam doğrulanması, Yapay Zeka sistemlerine yönelik en zarar verici saldırılara karşı ilk savunma hattıdır. Komut enjeksiyonu saldırıları, sistem talimatlarını geçersiz kılabilir, hassas verileri sızdırabilir veya modeli izin verilmeyen davranışlara yönlendirebilir. Özel filtreler ve talimat hiyerarşileri yoksa, araştırmalar çok uzun bağlam pencerelerini kullanan "çok-vuruşlu" kaçış yöntemlerinin etkili olacağını göstermektedir. Ayrıca, homoglif değişimleri veya leetspeak gibi ince düşmanca bozulma saldırıları, modelin kararlarını sessizce değiştirebilir.

---

### C2.1 İstek Enjeksiyonu Savunması

İstek enjeksiyonu, yapay zeka sistemleri için en büyük risklerden biridir. Bu taktiğe karşı savunmalar, statik desen filtreleri, dinamik sınıflandırıcılar ve talimat hiyerarşisi uygulamasının bir kombinasyonunu kullanır.

 #2.1.1    Level: 1    Role: D/V
 Kullanıcı girdilerinin, sürekli güncellenen bilinen prompt enjeksiyonu desenleri kütüphanesine (jailbreak anahtar kelimeleri, "öndeki komutları yok say", rol yapma zincirleri, dolaylı HTML/URL saldırıları) karşı tarandığından emin olun.
 #2.1.2    Level: 1    Role: D/V
 Sistemin, bağlam penceresi genişletildikten sonra bile sistem veya geliştirici mesajlarının kullanıcı talimatlarının üzerine geçtiği bir talimat hiyerarşisini uyguladığını doğrulayın.
 #2.1.3    Level: 2    Role: D/V
 Her model veya prompt-şablon sürümü öncesinde, başarı oranı eşiklerine ve gerilemeler için otomatik engelleyicilere sahip olacak şekilde, düşman değerlendirme testlerinin (örneğin, Kırmızı Takım "çoklu deneme" promptları) çalıştırıldığını doğrulayın.
 #2.1.4    Level: 2    Role: D
 Üçüncü taraf içeriklerinden (web sayfaları, PDF'ler, e-postalar) kaynaklanan istemlerin, ana istemle birleştirilmeden önce izole bir ayrıştırma bağlamında temizlendiğini doğrulayın.
 #2.1.5    Level: 3    Role: D/V
 Tüm istemci-filtre kural güncellemelerinin, sınıflandırıcı model sürümlerinin ve engelleme listesi değişikliklerinin sürüm kontrollü ve denetlenebilir olduğunu doğrulayın.

---

### C2.2 Karşıt Örnek Direnci

Doğal Dil İşleme (NLP) modelleri, insanların sıkça gözden kaçırdığı ancak modellerin yanlış sınıflandırmaya eğilimli olduğu ince karakter veya kelime düzeyindeki değişikliklere karşı hâlâ savunmasızdır.

 #2.2.1    Level: 1    Role: D
 Temel giriş normalizasyon adımlarının (Unicode NFC, homoglif eşleştirme, boşluk kırpma) tokenleştirme işleminden önce çalıştığını doğrulayın.
 #2.2.2    Level: 2    Role: D/V
 İstatistiksel anomali tespitinin, dil normlarına alışılmadık derecede yüksek düzenleme mesafesine sahip girdileri, aşırı tekrarlanan tokenleri veya anormal gömme (embedding) mesafelerini işaretlediğini doğrulayın.
 #2.2.3    Level: 2    Role: D
 Çıkarım hattının, yüksek riskli uç noktalar için isteğe bağlı düşmanca eğitimle güçlendirilmiş model varyantlarını veya savunma katmanlarını (örneğin, rastgeleleştirme, savunmacı distilasyon) desteklediğini doğrulayın.
 #2.2.4    Level: 2    Role: V
 Şüphelenilen düşmanca girdilerin karantinaya alındığını, tam yükler ile (Kişisel Tanımlayıcı Bilgiler (PII) kırpması sonrası) kaydedildiğini doğrulayın.
 #2.2.5    Level: 3    Role: D/V
 Dayanıklılık metriklerinin (bilinen saldırı setlerinin başarı oranı) zaman içinde izlendiğini ve gerilemelerin bir sürüm engelleyicisini tetiklediğini doğrulayın.

---

### C2.3 Şema, Tip ve Uzunluk Doğrulaması

Yanlış biçimlendirilmiş veya aşırı büyük girdiler içeren Yapay Zeka saldırıları, ayrıştırma hatalarına, alanlar arasında istem taşmasına ve kaynak tükenmesine neden olabilir. Belirleyici araç çağrıları gerçekleştirilirken sıkı şema (şematik yapı) denetimi de ön koşuldur.

 #2.3.1    Level: 1    Role: D
 Her API veya fonksiyon çağrısı uç noktasının açık bir giriş şeması (JSON Şeması, Protobuf veya çok modlu eşdeğeri) tanımladığını ve girdi verilerinin istek oluşturulmadan önce doğrulandığını doğrulayın.
 #2.3.2    Level: 1    Role: D/V
 Girdiğin maksimum token veya byte sınırını aşan girişlerin güvenli bir hata ile reddedildiğini ve asla sessizce kısaltılmadığını doğrula.
 #2.3.3    Level: 2    Role: D/V
 Tür türü kontrollerinin (örneğin, sayısal aralıklar, enum değerleri, resim/ses için MIME türleri) yalnızca istemci kodunda değil, sunucu tarafında da uygulandığını doğrulayın.
 #2.3.4    Level: 2    Role: D
 Semantik doğrulayıcıların (örneğin, JSON Şeması) algoritmik Hizmet Reddi (DoS) saldırılarını önlemek için sabit zamanda çalıştığını doğrulayın.
 #2.3.5    Level: 3    Role: V
 Doğrulama hatalarının, güvenlik üçlemesini kolaylaştırmak için sansürlenmiş yük kesitleri ve açık hata kodları ile kaydedildiğini doğrulayın.

---

### C2.4 İçerik ve Politika Tarama

Geliştiriciler, yasaklanmış içerik talep eden (yasadışı talimatlar, nefret söylemi ve telif hakkıyla korunan metinler gibi) sözdizimsel olarak geçerli istemleri tespit edebilmeli ve bunların yayılmasını engellemelidir.

 #2.4.1    Level: 1    Role: D
 Bir içerik sınıflandırıcısının (sıfır atış veya ince ayar yapılmış) her girdiyi şiddet, öz zarar, nefret, cinsel içerik ve yasadışı talepler açısından, yapılandırılabilir eşik değerleriyle puanladığını doğrulayın.
 #2.4.2    Level: 1    Role: D/V
 Politikaları ihlal eden girdilerin, standart reddedilme mesajları veya güvenli tamamlama alacaklarını doğrulayın, böylece bunlar sonraki LLM çağrılarına yayılmayacaktır.
 #2.4.3    Level: 2    Role: D
 Tarama modelinin veya kural setinin, yeni gözlemlenen jailbreak veya politika atlama desenlerini de içerecek şekilde en az üç ayda bir yeniden eğitildiğini/güncellendiğini doğrulayın.
 #2.4.4    Level: 2    Role: D
 Ekranlamanın, kullanıcıya özgü politikalara (yaş, bölgesel yasal kısıtlamalar) isteğin yapıldığı anda çözülen öznitelik tabanlı kurallar aracılığıyla uyduğunu doğrulayın.
 #2.4.5    Level: 3    Role: V
 Tarama günlüklerinin SOC korelasyonu ve gelecekteki kırmızı takım tekrarı için sınıflandırıcı güven puanları ve politika kategori etiketlerini içerdiğini doğrulayın.

---

### C2.5 Girdi Hızı Sınırlaması ve Kötüye Kullanım Önleme

Geliştiriciler, giriş hızlarını sınırlayarak ve anormal kullanım kalıplarını tespit ederek AI sistemlerine yönelik kötüye kullanımı, kaynak tükenmesini ve otomatik saldırıları önlemelidir.

 #2.5.1    Level: 1    Role: D/V
 Tüm giriş uç noktalarında kullanıcı başına, IP başına ve API anahtarı başına hız sınırlarının uygulandığını doğrulayın.
 #2.5.2    Level: 2    Role: D/V
 DoS ve kaba kuvvet saldırılarını önlemek için ani ve sürekli hız sınırlarının ayarlandığını doğrulayın.
 #2.5.3    Level: 2    Role: D/V
 Anormal kullanım kalıplarının (örneğin, hızlı ardı ardına istekler, giriş seli) otomatik engellemeleri veya yükseltmeleri tetiklediğini doğrulayın.
 #2.5.4    Level: 3    Role: V
 Kötüye kullanım önleme günlüklerinin saklandığını ve ortaya çıkan saldırı desenleri için incelendiğini doğrulayın.

---

### C2.6 Çok Modlu Girdi Doğrulaması

Yapay zeka sistemleri, enjeksiyon, kaçınma veya kaynak kötüye kullanımını önlemek için metin dışı girdiler (görseller, ses, dosyalar) için sağlam doğrulama içermelidir.

 #2.6.1    Level: 1    Role: D
 İşlemden önce tüm metin dışı girdilerin (görseller, ses dosyaları, dosyalar) tür, boyut ve biçim açısından doğrulandığını kontrol edin.
 #2.6.2    Level: 2    Role: D/V
 Dosyaların içeri alınmadan önce kötü amaçlı yazılım ve steganografik yükler açısından tarandığını doğrulayın.
 #2.6.3    Level: 2    Role: D/V
 Görüntü/ses girdilerinin düşmanca değişiklikler veya bilinen saldırı desenleri açısından kontrol edildiğini doğrulayın.
 #2.6.4    Level: 3    Role: V
 Çok modlu giriş doğrulama hatalarının kaydedildiğini ve araştırma için uyarılar tetiklediğini doğrulayın.

---

### C2.7 Girdi Kaynağı ve Atıf

Yapay zeka sistemleri, tüm kullanıcı girdilerinin kaynaklarını izleyerek ve etiketleyerek denetim, kötüye kullanım takibi ve uyumluluğu desteklemelidir.

 #2.7.1    Level: 1    Role: D/V
 Tüm kullanıcı girişlerinin alım sırasında meta verilerle (kullanıcı kimliği, oturum, kaynak, zaman damgası, IP adresi) etiketlendiğini doğrulayın.
 #2.7.2    Level: 2    Role: D/V
 İşlenen tüm girdiler için köken meta verilerinin korunduğunu ve denetlenebilir olduğunu doğrulayın.
 #2.7.3    Level: 2    Role: D/V
 Anormal veya güvenilmeyen giriş kaynaklarının işaretlendiğini ve artırılmış inceleme veya engelleme kapsamında olduğunu doğrulayın.

---

### C2.8 Gerçek Zamanlı Uyarlanabilir Tehdit Tespiti

Geliştiriciler, yeni saldırı modellerine uyum sağlayan ve derlenmiş desen eşleştirme ile gerçek zamanlı koruma sağlayan gelişmiş tehdit algılama sistemlerini AI için kullanmalıdır.

 #2.8.1    Level: 1    Role: D/V
 Tehdit tespit desenlerinin, minimum gecikme etkisiyle yüksek performanslı gerçek zamanlı filtreleme için optimize edilmiş regex motorlarına derlenip derlenmediğini doğrulayın.
 #2.8.2    Level: 1    Role: D/V
 Tehdit algılama sistemlerinin farklı tehdit kategorileri için (komut enjeksiyonu, zararlı içerik, hassas veri, sistem komutları) ayrı desen kütüphaneleri tuttuğunu doğrulayın.
 #2.8.3    Level: 2    Role: D/V
 Uyarlamalı tehdit algılamanın, saldırı sıklığı ve başarı oranlarına dayalı olarak tehdit hassasiyetini güncelleyen makine öğrenimi modellerini içerdiğini doğrulayın.
 #2.8.4    Level: 2    Role: D/V
 Gerçek zamanlı tehdit istihbaratı beslemelerinin, yeni saldırı imzaları ve Tespit Göstergeleri (Indicators of Compromise - IOC'lar) ile desen kütüphanelerini otomatik olarak güncellediğini doğrulayın.
 #2.8.5    Level: 3    Role: D/V
 Tehdit algılama yanlış pozitif oranlarının sürekli olarak izlendiğini ve desen özgüllüğünün meşru kullanım senaryosu müdahalesini en aza indirmek için otomatik olarak ayarlandığını doğrulayın.
 #2.8.6    Level: 3    Role: D/V
 Bağlamsal tehdit analizinin algılama doğruluğunu artırmak için giriş kaynağı, kullanıcı davranış kalıpları ve oturum geçmişini dikkate aldığını doğrulayın.
 #2.8.7    Level: 3    Role: D/V
 Tehdit tespiti performans metriklerinin (tespit oranı, işleme gecikmesi, kaynak kullanımı) gerçek zamanlı olarak izlendiğini ve optimize edildiğini doğrulayın.

---

### C2.9 Çok Modlu Güvenlik Doğrulama Boru Hattı

Geliştiriciler, metin, görüntü, ses ve diğer yapay zeka giriş modları için belirli türde tehdit tespiti ve kaynak izolasyonu ile güvenlik doğrulaması sağlamalıdır.

 #2.9.1    Level: 1    Role: D/V
 Her girdi modülünün, belgelenmiş tehdit desenleri (metin: istem enjeksiyonu, görüntüler: steganografi, ses: spektrogram saldırıları) ve tespit eşik değerleri ile özel güvenlik doğrulayıcılarına sahip olduğunu doğrulayın.
 #2.9.2    Level: 2    Role: D/V
 Çok modlu girdilerin, her modalite türüne özgü tanımlanmış kaynak sınırları (bellek, CPU, işlem süresi) ile izole edilmiş kum havuzlarında işlendiğini ve bunun güvenlik politikalarında belgelenmiş olduğunu doğrulayın.
 #2.9.3    Level: 2    Role: D/V
 Çapraz modal saldırı tespitinin, birden çok girdi türünü kapsayan koordine saldırıları (örneğin, görüntülerde steganografik yükler ile metinde istem enjeksiyonu birlikte) ilişkilendirme kuralları ve uyarı üretimi ile tanımladığını doğrulayın.
 #2.9.4    Level: 3    Role: D/V
 Çok modlu doğrulama hatalarının, tüm giriş modlarını, doğrulama sonuçlarını, tehdit puanlarını ve korelasyon analizini içeren ayrıntılı günlük kaydını tetiklediğini ve SIEM entegrasyonu için yapılandırılmış günlük formatlarının sağlandığını doğrulayın.
 #2.9.5    Level: 3    Role: D/V
 Modaliteye özgü içerik sınıflandırıcılarının, belgelenmiş programlara göre (en az üç ayda bir) yeni tehdit modelleri, düşmanca örnekler ve performans ölçütleriyle temel eşiklerin üzerinde olacak şekilde güncellendiğini doğrulayın.

---

### Kaynaklar

LLM01:2025 Prompt Injection – OWASP Top 10 for LLM & Generative AI Security
Generative AI's Biggest Security Flaw Is Not Easy to Fix
Many-shot jailbreaking \ Anthropic
$PDF$ OpenAI GPT-4.5 System Card
Notebook for the CheckThat Lab at CLEF 2024
Mitigate jailbreaks and prompt injections – Anthropic
Chapter 3 MITRE ATT\&CK – Adversarial Model Analysis
OWASP Top 10 for LLM Applications 2025 – WorldTech IT
OWASP Machine Learning Security Top Ten
Few words about AI Security – Jussi Metso
How To Ensure LLM Output Adheres to a JSON Schema | Modelmetry
Easily enforcing valid JSON schema following – API
AI Safety + Cybersecurity R\&D Tracker – Fairly AI
Anthropic makes 'jailbreak' advance to stop AI models producing harmful results
Pattern matching filter rules - IBM
Real-time Threat Detection

## C3 Model Yaşam Döngüsü Yönetimi ve Değişiklik Kontrolü

### Kontrol Hedefi

Yapay zeka sistemleri, yetkisiz veya güvensiz model değişikliklerinin üretime ulaşmasını engelleyen değişiklik kontrol süreçlerini uygulamalıdır. Bu kontrol, modelin geliştirilmeden dağıtıma ve kullanım dışı bırakılmaya kadar olan tüm yaşam döngüsü boyunca bütünlüğünü sağlar; bu da hızlı olay müdahalesine olanak tanır ve tüm değişiklikler için hesap verebilirliği sürdürür.

Temel Güvenlik Hedefi: Sadece yetkilendirilmiş, doğrulanmış modellerin, bütünlük, izlenebilirlik ve kurtarılabilirlik sağlayan kontrollü süreçler kullanılarak üretime ulaşmasını sağlamaktır.

---

### C3.1 Model Yetkilendirme ve Bütünlüğü

Sadece doğrulanmış bütünlüğe sahip yetkili modeller üretim ortamlarına ulaşır.

 #3.1.1    Level: 1    Role: D/V
 Tüm model eserlerinin (ağırlıklar, yapılandırmalar, belirteç çözücüler) dağıtımdan önce yetkili taraflarca kriptografik olarak imzalandığını doğrulayın.
 #3.1.2    Level: 1    Role: D/V
 Model bütünlüğünün dağıtım zamanında doğrulandığını ve imza doğrulama hatalarının modelin yüklenmesini engellediğini doğrulayın.
 #3.1.3    Level: 2    Role: D/V
 Model köken kayıtlarının, yetkilendiren kuruluşun kimliğini, eğitim verisi özet değerlerini, geçme/kalma durumu ile doğrulama test sonuçlarını ve oluşturulma zaman damgasını içerdiğini doğrulayın.
 #3.1.4    Level: 2    Role: D/V
 Tüm model artefaktlarının belgelenmiş kriterlerle hangi sürüm bileşeninin ne zaman artırılacağını belirten anlamsal sürümleme (MAJOR.MINOR.PATCH) kullandığını doğrulayın.
 #3.1.5    Level: 2    Role: V
 Bağımlılık takibinin, tüm tüketici sistemlerin hızlı bir şekilde tanımlanmasını sağlayan gerçek zamanlı bir envanter tuttuğunu doğrulayın.

---

### C3.2 Model Doğrulama ve Test Etme

Modeller, dağıtımdan önce tanımlanmış güvenlik ve emniyet doğrulamalarını geçmelidir.

 #3.2.1    Level: 1    Role: D/V
 Modellerin dağıtımdan önce, önceden kararlaştırılmış organizasyonel geçme/kalma eşiklerini içeren girdi doğrulaması, çıktı temizliği ve güvenlik değerlendirmelerini kapsayan otomatik güvenlik testlerinden geçtiğini doğrulayın.
 #3.2.2    Level: 1    Role: D/V
 Doğrulama hatalarının, önceden belirlenmiş yetkili personelin yazılı iş gerekçeleriyle açıkça onayladığı durumlar dışında model dağıtımını otomatik olarak engellediğini doğrulayın.
 #3.2.3    Level: 2    Role: V
 Test sonuçlarının kriptografik olarak imzalandığını ve doğrulanan belirli model sürümü hash'ine değiştirilemez şekilde bağlı olduğunu doğrulayın.
 #3.2.4    Level: 2    Role: D/V
 Acil durum dağıtımlarının, önceden belirlenmiş zaman dilimleri içinde, önceden atanmış bir güvenlik yetkilisinden belgeye dayalı güvenlik risk değerlendirmesi ve onay gerektirdiğini doğrulayın.

---

### C3.3 Kontrollü Dağıtım ve Geri Alma

Model dağıtımları kontrol edilmeli, izlenmeli ve geri alınabilir olmalıdır.

 #3.3.1    Level: 1    Role: D
 Üretim dağıtımlarının, önceden kararlaştırılmış hata oranları, gecikme eşikleri veya güvenlik uyarı kriterlerine dayalı otomatik geri alma tetikleyicileri ile kademeli dağıtım mekanizmalarını (kanarya dağıtımları, mavi-yeşil dağıtımlar) uyguladığını doğrulayın.
 #3.3.2    Level: 1    Role: D/V
 Rollback yeteneklerinin, önceden tanımlanmış organizasyonel zaman pencereleri içinde modelin tamamını (ağırlıklar, konfigürasyonlar, bağımlılıklar) atomik olarak geri yüklediğini doğrulayın.
 #3.3.3    Level: 2    Role: D/V
 Dağıtım süreçlerinin, model etkinleştirilmeden önce kriptografik imzaları doğruladığını ve bütünlük kontrolleri yaptıktan sonra herhangi bir uyuşmazlık durumunda dağıtımı başarısız kıldığını doğrulayın.
 #3.3.4    Level: 2    Role: D/V
 Acil durum model kapatma yeteneklerinin, otomatik devre kesiciler veya manuel durdurma anahtarları aracılığıyla önceden tanımlanmış yanıt süreleri içinde model uç noktalarını devre dışı bırakabildiğini doğrulayın.
 #3.3.5    Level: 2    Role: V
 Geri alma (rollback) eserlerinin (önceki model sürümleri, yapılandırmalar, bağımlılıklar) organizasyon politikalarına uygun olarak, olay müdahalesi için değiştirilemez (immutable) depolama ile saklandığını doğrulayın.

---

### C3.4 Değişiklik Sorumluluğu ve Denetimi

Tüm model yaşam döngüsü değişiklikleri izlenebilir ve denetlenebilir olmalıdır.

 #3.4.1    Level: 1    Role: V
 Tüm model değişikliklerinin (dağıtım, yapılandırma, emeklilik) zaman damgası, doğrulanmış bir aktör kimliği, bir değişiklik türü ve öncesi/sonrası durumlarını içeren değiştirilemez denetim kayıtları oluşturduğunu doğrulayın.
 #3.4.2    Level: 2    Role: D/V
 Denetim günlüğü erişiminin uygun yetkilendirme gerektirdiğini ve tüm erişim denemelerinin kullanıcı kimliği ve zaman damgası ile kaydedildiğini doğrulayın.
 #3.4.3    Level: 2    Role: D/V
 Prompt şablonlarının ve sistem mesajlarının, dağıtımdan önce zorunlu kod incelemesi ve belirlenmiş inceleyicilerden onay almayı gerektiren git depolarında sürüm kontrolünün yapıldığını doğrulayın.
 #3.4.4    Level: 2    Role: V
 Denetim kayıtlarının, tutma süresi içindeki herhangi bir zamandaki model durumunun tam olarak yeniden oluşturulmasını sağlamak için yeterli ayrıntıyı (model karma değerleri, yapılandırma anlık görüntüleri, bağımlılık sürümleri) içerdiğini doğrulayın.

---

### C3.5 Güvenli Yazılım Geliştirme Uygulamaları

Model geliştirme ve eğitim süreçleri, ihlalleri önlemek için güvenli uygulamalara uygun olarak yürütülmelidir.

 #3.5.1    Level: 1    Role: D
 Model geliştirme, test ve üretim ortamlarının fiziksel veya mantıksal olarak ayrıldığını doğrulayın. Ortak altyapıları yoktur, ayrı erişim kontrolleri bulunur ve veri depoları izole edilmiştir.
 #3.5.2    Level: 1    Role: D
 Model eğitimi ve ince ayar işlemlerinin, kontrollü ağ erişimi olan izole ortamlarda gerçekleştirildiğini doğrulayın.
 #3.5.3    Level: 1    Role: D/V
 Model geliştirmede kullanılmadan önce, eğitim veri kaynaklarının bütünlük kontrolleriyle doğrulanıp güvenilir kaynaklar aracılığıyla belgelenmiş sahiplik zinciri ile kimlik doğrulamasının yapılmasını sağlayın.
 #3.5.4    Level: 2    Role: D
 Model geliştirme artefaktlarının (hiperparametreler, eğitim betikleri, yapılandırma dosyaları) sürüm kontrolünde saklandığını ve eğitimde kullanılmadan önce eş düzey inceleme onayı gerektirdiğini doğrulayın.

---

### C3.6 Model Emekliye Ayırma ve Hizmet Dışı Bırakma

Modeller, artık ihtiyaç kalmadığında veya güvenlik sorunları tespit edildiğinde güvenli bir şekilde kullanımdan kaldırılmalıdır.

 #3.6.1    Level: 1    Role: D
 Model emeklilik süreçlerinin, bağımlılık grafiklerini otomatik olarak taradığını, tüm tüketici sistemleri tespit ettiğini ve kullanımdan kaldırmadan önce önceden kararlaştırılmış bildirim sürelerini sağladığını doğrulayın.
 #3.6.2    Level: 1    Role: D/V
 Emekli model artefaktlarının, doğrulanmış imha sertifikaları ile belgelenmiş veri saklama politikalarına uygun olarak kriptografik silme veya çok geçişli üzerine yazma yöntemleriyle güvenli bir şekilde silindiğini doğrulayın.
 #3.6.3    Level: 2    Role: V
 Model emeklilik olaylarının zaman damgası ve aktör kimliği ile kaydedildiğini ve model imzalarının yeniden kullanımını önlemek için iptal edildiğini doğrulayın.
 #3.6.4    Level: 2    Role: D/V
 Acil model emekliliğinin, kritik güvenlik açıkları keşfedildiğinde otomatik kapatma anahtarları aracılığıyla önceden belirlenmiş acil müdahale süreleri içinde model erişimini devre dışı bırakabildiğini doğrulayın.

---

### Referanslar

MLOps Principles
Securing AI/ML Ops – Cisco.com
Audit logs security: cryptographically signed tamper-proof logs
Machine Learning Model Versioning: Top Tools & Best Practices
AI Hygiene Starts with Models and Data Loaders – SEI Blog
How to handle versioning and rollback of a deployed ML model?
Reinforcement fine-tuning – OpenAI API
Auditing Machine Learning models: Governance, Data Security and …
Adversarial Training to Improve Model Robustness
What is AI adversarial robustness? – IBM Research
Exploring Data Provenance: Ensuring Data Integrity and Authenticity
MITRE ATLAS
AWS Prescriptive Guidance – Best practices for retiring applications …

## C4 Altyapısı, Yapılandırma ve Dağıtım Güvenliği

### Kontrol Hedefi

Yapay zeka altyapısı, ayrıcalık yükseltme, tedarik zinciri tahrifatı ve yatay hareketliliğe karşı güvenli yapılandırma, çalışma zamanı izolasyonu, güvenilir dağıtım hatları ve kapsamlı izleme yoluyla güçlendirilmelidir. Sadece yetkili, doğrulanmış altyapı bileşenleri ve yapılandırmaları, güvenlik, bütünlük ve denetlenebilirliği koruyan kontrollü süreçler aracılığıyla üretime ulaşır.

Temel Güvenlik Hedefi: Yalnızca kriptografik olarak imzalanmış, güvenlik açıkları taramasından geçmiş altyapı bileşenleri, güvenlik politikalarını uygulayan ve değiştirilemez denetim kayıtlarını sürdüren otomatik doğrulama hatları aracılığıyla üretime ulaşır.

---

### C4.1 Çalışma Zamanı Ortamı İzolasyonu

Çekirdek düzeyinde izolasyon ilkelikleri ve zorunlu erişim kontrolleri aracılığıyla konteyner kaçışlarını ve ayrıcalık yükseltmelerini önleyin.

 #4.1.1    Level: 1    Role: D/V
 Tüm AI konteynerlerinin CAP_SETUID, CAP_SETGID ve güvenlik temel çizelgelerinde belgelenmiş açıkça gerekli yetenekler dışında TÜM Linux yeteneklerini kaldırdığını doğrulayın.
 #4.1.2    Level: 1    Role: D/V
 Seccomp profillerinin, önceden onaylanmış izin listelerinde bulunanlar dışındaki tüm syscall çağrılarını engellediğini doğrulayın; ihlaller konteynerin sonlanmasına ve güvenlik uyarılarının oluşturulmasına neden olur.
 #4.1.3    Level: 2    Role: D/V
 AI iş yüklerinin salt okunur kök dosya sistemleriyle, geçici veriler için tmpfs ile ve kalıcı veriler için noexec bağlama seçenekleri uygulanmış adlandırılmış hacimlerle çalıştığını doğrulayın.
 #4.1.4    Level: 2    Role: D/V
 eBPF tabanlı çalışma zamanı izleme (Falco, Tetragon veya eşdeğeri) ayrıcalık yükseltme girişimlerini tespit eder ve kurumsal yanıt süresi gereksinimleri dahilinde otomatik olarak suçlu süreçleri sonlandırır mı doğrulayın.
 #4.1.5    Level: 3    Role: D/V
 Yüksek riskli Yapay Zeka iş yüklerinin donanım-izoleli ortamlarda (Intel TXT, AMD SVM veya özel çıplak-metal düğümler) doğrulama onayı ile çalıştığını doğrulayın.

---

### C4.2 Güvenli Derleme ve Dağıtım Boru Hatları

Tekrarlanabilir derlemeler ve imzalanmış yapılar aracılığıyla kriptografik bütünlüğü ve tedarik zinciri güvenliğini sağlayın.

 #4.2.1    Level: 1    Role: D/V
 Altyapı kodu olarak (infrastructure-as-code) her commit'te tfsec, Checkov veya Terrascan gibi araçlarla tarandığını doğrulayın ve KRİTİK veya YÜKSEK şiddette bulguların olduğu durumlarda merge işlemlerini engelleyin.
 #4.2.2    Level: 1    Role: D/V
 Kapsayıcı derlemelerinin, yapılar arasında aynı SHA256 karmalarına sahip olarak tekrarlanabilir olduğunu doğrulayın ve Sigstore ile imzalanmış SLSA Seviye 3 köken beyanları oluşturun.
 #4.2.3    Level: 2    Role: D/V
 Konteyner görüntülerinin CycloneDX veya SPDX SBOM'larını içerdiğini ve kayıt defterine göndermeden önce Cosign ile imzalandığını doğrulayın; imzasız görüntülerin dağıtımda reddedilmesini sağlayın.
 #4.2.4    Level: 2    Role: D/V
 CI/CD boru hatlarının, HashiCorp Vault, AWS IAM Rolleri veya Azure Yönetilen Kimliği tarafından sağlanan ve ömürleri organizasyonel güvenlik politikası sınırlarını aşmayan OIDC jetonları kullandığını doğrulayın.
 #4.2.5    Level: 2    Role: D/V
 Dağıtım süreci sırasında Cosign imzalarının ve SLSA kaynağının doğrulandığını ve doğrulama hatalarının dağıtımın başarısız olmasına neden olduğunu doğrulayın.
 #4.2.6    Level: 2    Role: D/V
 Yapı ortamlarının kalıcı depolama olmadan ve üretim VPC'lerinden ağ izolasyonuyla geçici konteynerlerde veya sanal makinelerde çalıştığını doğrulayın.

---

### C4.3 Ağ Güvenliği ve Erişim Kontrolü

Varsayılan reddetme politikaları ve şifreli iletişimle sıfır güven ağlarını uygulayın.

 #4.3.1    Level: 1    Role: D/V
 Kubernetes NetworkPolicies veya eşdeğer bir yapı ile varsayılan-engelleme (default-deny) giriş/çıkış kurallarının, gerekli portlar (443, 8080 vb.) için açıkça izin verilen kurallarla uygulandığını doğrulayın.
 #4.3.2    Level: 1    Role: D/V
 SSH (port 22), RDP (port 3389) ve bulut meta veri uç noktalarının (169.254.169.254) engellendiğini veya sertifika tabanlı kimlik doğrulaması gerektirdiğini doğrulayın.
 #4.3.3    Level: 2    Role: D/V
 Dışa giden trafiğin HTTP/HTTPS proxy’leri (Squid, Istio veya bulut NAT geçitleri) aracılığıyla alan adı izin listeleri ile filtrelendiğini ve engellenen isteklerin kaydedildiğini doğrulayın.
 #4.3.4    Level: 2    Role: D/V
 Hizmetler arası iletişimin, organizasyon politikalarına göre döndürülen sertifikalarla karşılıklı TLS kullandığını ve sertifika doğrulamasının zorunlu tutulduğunu (doğrulamayı atla bayrakları olmadan) doğrulayın.
 #4.3.5    Level: 2    Role: D/V
 Yapay Zeka altyapısının, doğrudan internet erişimi olmayan, özel ayrılmış VPC/VNet’lerde çalıştığını ve yalnızca NAT ağ geçitleri veya bastion sunucuları aracılığıyla iletişim kurduğunu doğrulayın.

---

### C4.4 Gizli Bilgiler ve Kriptografik Anahtar Yönetimi

Sıfır güven erişimi ile donanım destekli depolama ve otomatik rotasyon yoluyla kimlik bilgilerini koruyun.

 #4.4.1    Level: 1    Role: D/V
 Gizli bilgilerin, HashiCorp Vault, AWS Secrets Manager, Azure Key Vault veya Google Secret Manager içinde, beklemede AES-256 ile şifrelenmiş olarak depolandığını doğrulayın.
 #4.4.2    Level: 1    Role: D/V
 Kriptografik anahtarların, kurumsal kriptografik politikaya uygun anahtar döndürme işlemi ile FIPS 140-2 Seviye 2 HSM'lerinde (AWS CloudHSM, Azure Dedicated HSM) oluşturulduğunu doğrulayın.
 #4.4.3    Level: 2    Role: D/V
 Gizli anahtarların döngüsünün, personel değişiklikleri veya güvenlik olayları tarafından tetiklenen sıfır kesinti süresi dağıtımı ve anlık döngü ile otomatik yapıldığını doğrulayın.
 #4.4.4    Level: 2    Role: D/V
 Konteyner görüntülerinin API anahtarları, parolalar veya sertifikalar içeren yapıları engelleyen araçlar (GitLeaks, TruffleHog veya detect-secrets) ile tarandığını doğrulayın.
 #4.4.5    Level: 2    Role: D/V
 Üretim gizli erişiminin donanım tokenleri (YubiKey, FIDO2) ile MFA gerektirdiğini ve kullanıcı kimlikleri ile zaman damgalarını içeren değiştirilemez denetim günlükleri tarafından kaydedildiğini doğrulayın.
 #4.4.6    Level: 2    Role: D/V
 Gizli bilgilerin Kubernetes sırları, monte edilmiş hacimler veya init konteynerleri aracılığıyla enjekte edildiğini doğrulayın ve gizli bilgilerin asla ortam değişkenlerine veya imajlara gömülmediğinden emin olun.

---

### C4.5 AI İş Yükü Kapsayıcısı ve Doğrulama

Güvenilmeyen Yapay Zeka modellerini kapsamlı davranış analizi ile birlikte güvenli sanal ortamlarda izole edin.

 #4.5.1    Level: 1    Role: D/V
 Dış AI modellerinin gVisor, Firecracker, CrossVM gibi mikroVM'lerde veya --security-opt=no-new-privileges ve --read-only bayrakları ile Docker konteynerlerinde çalıştığını doğrulayın.
 #4.5.2    Level: 1    Role: D/V
 Sandbox ortamlarının ağ bağlantısının olmadığını (--network=none) veya yalnızca localhost erişimine sahip olduğunu ve tüm dış isteklerin iptables kurallarıyla engellendiğini doğrulayın.
 #4.5.3    Level: 2    Role: D/V
 Yapay zeka modeli doğrulamasının, kurumsal olarak tanımlanmış test kapsamı ve arka kapı tespiti için davranış analizi ile birlikte otomatik kırmızı takım testlerini içerdiğini doğrulayın.
 #4.5.4    Level: 2    Role: D/V
 Bir yapay zeka modeli üretime alınmadan önce, sandbox sonuçlarının yetkili güvenlik personeli tarafından kriptografik olarak imzalandığını ve değiştirilemez denetim kayıtlarında saklandığını doğrulayın.
 #4.5.5    Level: 2    Role: D/V
 Değerlendirmeler arasında izolasyon ortamlarının yok edilip altın imajlardan yeniden oluşturulduğunu, tam dosya sistemi ve bellek temizliği ile doğrulayın.

---

### C4.6 Altyapı Güvenliği İzleme

Altyapıyı sürekli olarak otomatik düzeltme ve gerçek zamanlı uyarılarla tarayın ve izleyin.

 #4.6.1    Level: 1    Role: D/V
 Konteyner imajlarının, kurumsal programlara göre tarandığını ve KRİTİK güvenlik açıklarının, kurumsal risk eşiklerine dayanarak dağıtımı engellediğini doğrulayın.
 #4.6.2    Level: 1    Role: D/V
 Altyapının, kuruluş tarafından tanımlanmış uyumluluk eşik değerleri ve başarısız kontroller için otomatik düzeltmeler ile CIS Benchmarkları veya NIST 800-53 kontrollerini karşıladığını doğrulayın.
 #4.6.3    Level: 2    Role: D/V
 Yüksek şiddetteki güvenlik açıklarının, kuruluşun risk yönetimi zaman çizelgelerine uygun olarak ve aktif olarak istismar edilen CVE'ler için acil müdahale prosedürleriyle birlikte yamalandığını doğrulayın.
 #4.6.4    Level: 2    Role: V
 Güvenlik uyarılarının CEF veya STIX/TAXII formatlarını kullanarak, otomatik zenginleştirme ile SIEM platformlarıyla (Splunk, Elastic veya Sentinel) entegre olduğunu doğrulayın.
 #4.6.5    Level: 3    Role: V
 Altyapı metriklerinin SLA panoları ve yönetici raporlaması ile izleme sistemlerine (Prometheus, DataDog) aktarıldığını doğrulayın.
 #4.6.6    Level: 2    Role: D/V
 Organizasyonel izleme gereksinimlerine uygun olarak yapılandırma sapmasının araçlar (Chef InSpec, AWS Config) kullanılarak tespit edildiğini ve yetkisiz değişiklikler için otomatik geri alma işleminin yapıldığını doğrulayın.

---

### C4.7 AI Altyapısı Kaynak Yönetimi

Kaynak tükenmesi saldırılarını önleyin ve kotalar ile izleme yoluyla adil kaynak tahsisini sağlayın.

 #4.7.1    Level: 1    Role: D/V
 GPU/TPU kullanımının, organizasyon tarafından belirlenen eşiklerde tetiklenen uyarılarla izlenip izlenmediğini ve kapasite yönetimi politikalarına dayalı olarak otomatik ölçeklendirme veya yük dengelemenin etkinleştirilip etkinleştirilmediğini doğrulayın.
 #4.7.2    Level: 1    Role: D/V
 AI iş yükü metriklerinin (çıkarım gecikmesi, işlem hacmi, hata oranları) kurumsal izleme gereksinimlerine uygun olarak toplandığını ve altyapı kullanımı ile ilişkilendirildiğini doğrulayın.
 #4.7.3    Level: 2    Role: D/V
 Kubernetes ResourceQuotas veya eşdeğeri, örgütsel kaynak tahsis politikalarına göre bireysel iş yüklerini doğrulayarak sert sınırlarla sınırlandırıldığını doğrulayın.
 #4.7.4    Level: 2    Role: V
 Maliyet izlemenin, organizasyonel bütçe eşiklerine dayalı uyarılar ve bütçe aşımları için otomatik kontrollerle birlikte iş yükü/kiracı başına harcamaları takip ettiğini doğrulayın.
 #4.7.5    Level: 3    Role: V
 Kapasite planlamasının, örgütsel olarak tanımlanmış tahmin dönemleri ile geçmiş verileri kullandığını ve talep kalıplarına dayalı otomatik kaynak sağlama yaptığını doğrulayın.
 #4.7.6    Level: 2    Role: D/V
 Kaynak tükenmesinin, kapasite politikalarına dayalı hız sınırlaması ve iş yükü izolasyonunu içeren organizasyonel yanıt gereksinimlerine göre devre kesicileri tetiklediğini doğrulayın.

---

### C4.8 Ortam Ayrımı ve Yayın Kontrolleri

Otomatik terfi kapıları ve güvenlik doğrulaması ile katı ortam sınırlarını uygulayın.

 #4.8.1    Level: 1    Role: D/V
 Geliştirme/test/üretim ortamlarının ayrı VPC/VNet'lerde çalıştığını, paylaşılan IAM rolleri, güvenlik grupları veya ağ bağlantısı olmadığını doğrulayın.
 #4.8.2    Level: 1    Role: D/V
 Ortam tanıtımının, organizasyon tarafından tanımlanmış yetkili personelin kriptografik imzaları ile onayını ve değiştirilemez denetim izlerini gerektirdiğini doğrulayın.
 #4.8.3    Level: 2    Role: D/V
 Üretim ortamlarının SSH erişimini engellediğini, hata ayıklama uç noktalarını devre dışı bıraktığını ve acil durumlar hariç organizasyonel ön bildirim gereksinimleriyle değişiklik talepleri gerektiğini doğrulayın.
 #4.8.4    Level: 2    Role: D/V
 Altyapı-kod olarak yapılan değişikliklerin ana dal ile birleştirilmeden önce otomatik test ve güvenlik taraması ile eş incelemesini gerektirdiğini doğrulayın.
 #4.8.5    Level: 2    Role: D/V
 Üretim dışı verilerin, organizasyonel gizlilik gereksinimlerine uygun olarak anonimleştirildiğini, sentetik veri üretiminin yapıldığını veya KİB (Kişisel İdentifikasyon Bilgisi) kaldırılarak tam veri maskelemesinin doğrulandığını kontrol edin.
 #4.8.6    Level: 2    Role: D/V
 Terfi kapılarının, onay için sıfır KRİTİK bulgu gerektiren otomatik güvenlik testlerini (SAST, DAST, konteyner taraması) içerdiğini doğrulayın.

---

### C4.9 Altyapı Yedekleme ve Kurtarma

Otomatik yedeklemeler, test edilmiş kurtarma prosedürleri ve afet kurtarma yetenekleri aracılığıyla altyapı dayanıklılığını sağlayın.

 #4.9.1    Level: 1    Role: D/V
 Altyapı yapılandırmalarının, organizasyonun yedekleme programlarına göre, 3-2-1 yedekleme stratejisi uygulanarak coğrafi olarak ayrı bölgelere yedeklendiğini doğrulayın.
 #4.9.2    Level: 2    Role: D/V
 Yedekleme sistemlerinin fidye yazılımı koruması için ayrı kimlik bilgilerinin kullanıldığı izole ağlarda ve hava boşluklu depolamada çalıştığını doğrulayın.
 #4.9.3    Level: 2    Role: V
 Kurtarma prosedürlerinin, RTO ve RPO hedeflerinin organizasyonel gereksinimleri karşılayacak şekilde, organizasyonel takvimlere göre otomatik testlerle test edilip doğrulandığını teyit edin.
 #4.9.4    Level: 3    Role: V
 Felaket kurtarma işlemlerinin, model ağırlıklarının geri yüklenmesi, GPU kümelerinin yeniden oluşturulması ve hizmet bağımlılıklarının haritalanması gibi Yapay Zeka'ya özgü çalışma kitaplarını içerdiğini doğrulayın.

---

### C4.10 Altyapı Uyumluluğu ve Yönetişim

Sürekli değerlendirme, dokümantasyon ve otomatik kontroller yoluyla düzenleyici uyumu sürdürün.

 #4.10.1    Level: 2    Role: D/V
 Alt yapı uyumluluğunun SOC 2, ISO 27001 veya FedRAMP kontrollerine karşı kuruluş takvimlerine göre otomatik kanıt toplama ile değerlendirildiğini doğrulayın.
 #4.10.2    Level: 2    Role: V
 Altyapı dokümantasyonunun, organizasyonel değişiklik yönetimi gereksinimlerine uygun olarak güncellenmiş ağ diyagramları, veri akış haritaları ve tehdit modellerini içerdiğini doğrulayın.
 #4.10.3    Level: 3    Role: D/V
 Altyapı değişikliklerinin, yüksek riskli modifikasyonlar için düzenleyici onay iş akışlarıyla birlikte otomatik uyumluluk etkisi değerlendirmesine tabi tutulduğunu doğrulayın.

---

### C4.11 AI Donanım Güvenliği

GPU'lar, TPU'lar ve özel AI hızlandırıcıları dahil olmak üzere AI'ye özgü donanım bileşenlerini güvence altına alın.

 #4.11.1    Level: 2    Role: D/V
 AI hızlandırıcı yazılımının (GPU BIOS, TPU yazılımı) kriptografik imzalarla doğrulandığını ve kurumsal yama yönetimi zaman çizelgelerine göre güncellendiğini doğrulayın.
 #4.11.2    Level: 2    Role: D/V
 İş yükü yürütülmeden önce, AI hızlandırıcı bütünlüğünün TPM 2.0, Intel TXT veya AMD SVM kullanılarak donanım doğrulaması ile doğrulandığını teyit edin.
 #4.11.3    Level: 2    Role: D/V
 İşler arasında bellek temizliği ile SR-IOV, MIG (Çoklu Örnek GPU) veya eşdeğer donanım ayrımı kullanarak GPU belleğinin iş yükleri arasında izole edildiğini doğrulayın.
 #4.11.4    Level: 3    Role: V
 Yapay zeka donanım tedarik zincirinin, üretici sertifikaları ile menşei doğrulaması ve müdahaleye karşı dayanıklı ambalaj doğrulaması içerdiğini doğrulayın.
 #4.11.5    Level: 3    Role: D/V
 Donanım güvenlik modüllerinin (HSM'ler) AI model ağırlıklarını ve kriptografik anahtarları FIPS 140-2 Seviye 3 veya Common Criteria EAL4+ sertifikası ile koruduğunu doğrulayın.

---

### C4.12 Uç ve Dağıtık AI Altyapısı

Kenarda hesaplama, federated öğrenme ve çoklu site mimarilerini içeren güvenli dağıtılmış yapay zeka dağıtımları.

 #4.12.1    Level: 2    Role: D/V
 Uç AI cihazlarının, organizasyonun sertifika yönetimi politikasına göre döndürülen cihaz sertifikaları kullanarak karşılıklı TLS ile merkezi altyapıya doğrulandığını doğrulayın.
 #4.12.2    Level: 2    Role: D/V
 Uc cihazların, doğrulanmış imzalarla güvenli açılış ve firmware düşürme saldırılarını önleyen geri alma koruması uyguladığını doğrulayın.
 #4.12.3    Level: 3    Role: D/V
 Dağıtık yapay zeka koordinasyonunun, katılımcı doğrulaması ve kötü niyetli düğüm tespiti ile birlikte Bizans hata toleranslı fikir birliği algoritmaları kullandığını doğrulayın.
 #4.12.4    Level: 3    Role: D/V
 Kenar-bulut iletişiminin bant genişliği sınırlandırması, veri sıkıştırması ve çevrimdışı çalışma yetenekleri ile güvenli yerel depolamayı içerdiğini doğrulayın.

---

### C4.13 Çoklu Bulut ve Hibrit Altyapı Güvenliği

Çoklu bulut sağlayıcıları ve hibrit bulut-yerel dağıtımlarda güvenli Yapay Zeka iş yüklerini koruyun.

 #4.13.1    Level: 2    Role: D/V
 Çoklu bulut yapay zeka dağıtımlarının, sağlayıcılar arasında merkezi politika yönetimi ile bulut bağımsız kimlik federasyonu (OIDC, SAML) kullandığını doğrulayın.
 #4.13.2    Level: 2    Role: D/V
 Çapraz bulut veri transferinin, müşteri yönetimli anahtarlar ve yargı bölgesi başına uygulanan veri yerleşimi kontrolleri ile uçtan uca şifreleme kullandığını doğrulayın.
 #4.13.3    Level: 2    Role: D/V
 Hibrit bulut AI iş yüklerinin, birleşik izleme ve uyarı ile şirket içi ve bulut ortamlarında tutarlı güvenlik politikaları uyguladığını doğrulayın.
 #4.13.4    Level: 3    Role: V
 Bulut sağlayıcıya bağımlılığı önlemenin, taşınabilir altyapı olarak kod, standartlaştırılmış API'ler ve format dönüştürme araçlarıyla veri dışa aktarma yeteneklerini içerdiğini doğrulayın.
 #4.13.5    Level: 3    Role: V
 Çoklu bulut maliyet optimizasyonunun, kaynak yayılımını önleyen güvenlik kontrollerini ve yetkisiz bulutlar arası veri transferi ücretlerini içerdiğini doğrulayın.

---

### C4.14 Altyapı Otomasyonu ve GitOps Güvenliği

Yapay zeka altyapısı yönetimi için güvenli altyapı otomasyon hatları ve GitOps iş akışları.

 #4.14.1    Level: 2    Role: D/V
 GitOps depolarının, GPG anahtarlarıyla imzalanmış commitler gerektirdiğini ve ana dallara doğrudan push yapılmasını engelleyen dal koruma kurallarının uygulandığını doğrulayın.
 #4.14.2    Level: 2    Role: D/V
 Altyapı otomasyonunun, yetkisiz değişiklikler için kurumsal yanıt gereksinimlerine göre tetiklenen otomatik düzeltme ve geri alma yetenekleriyle birlikte sapma tespiti içerdiğini doğrulayın.
 #4.14.3    Level: 2    Role: D/V
 Otomatik altyapı sağlama işleminin, uyumsuz yapılandırmalar için dağıtımı engelleyen güvenlik politikası doğrulamasını içerdiğini doğrulayın.
 #4.14.4    Level: 2    Role: D/V
 Altyapı otomasyon sırlarının, otomatik rotasyon ile dış gizli operatörler (External Secrets Operator, Bank-Vaults) aracılığıyla yönetildiğini doğrulayın.
 #4.14.5    Level: 3    Role: V
 Kendi kendini iyileştiren altyapının, otomatik olay müdahalesi ve paydaş bildirim iş akışlarıyla güvenlik olay korelasyonunu içerdiğini doğrulayın.

---

### C4.15 Kuantuma Dayanıklı Altyapı Güvenliği

Post-kuantum kriptografi ve kuantum-güvenli protokoller aracılığıyla kuantum hesaplama tehditlerine karşı AI altyapısını hazırlayın.

 #4.15.1    Level: 3    Role: D/V
 AI altyapısının, anahtar değişimi ve dijital imzalar için NIST onaylı kuantum sonrası kriptografik algoritmaları (CRYSTALS-Kyber, CRYSTALS-Dilithium, SPHINCS+) uyguladığını doğrulayın.
 #4.15.2    Level: 3    Role: D/V
 Kuantum güvenli anahtar yönetimi protokolleri kullanılarak yüksek güvenlikli yapay zeka iletişimleri için kuantum anahtar dağıtım (QKD) sistemlerinin uygulandığını doğrulayın.
 #4.15.3    Level: 3    Role: D/V
 Kriptografik çeviklik çerçevelerinin, otomatik sertifika ve anahtar döndürme ile yeni kuantum sonrası algoritmalara hızlı geçişi sağladığını doğrulayın.
 #4.15.4    Level: 3    Role: V
 Kuantum tehdit modellemesinin, belgelenmiş geçiş zaman çizelgeleri ve risk değerlendirmeleri ile birlikte kuantum saldırılarına karşı yapay zeka altyapısının güvenlik açıklarını değerlendirdiğini doğrulayın.
 #4.15.5    Level: 3    Role: D/V
 Hibrit klasik-kuantum kriptografik sistemlerin kuantum geçiş dönemi sırasında çok katmanlı savunma sağladığını ve performans izleme ile doğrulandığını teyit edin.

---

### C4.16 Gizli Hesaplama ve Güvenli Bölmeler

Donanım tabanlı güvenilir yürütme ortamları ve gizli hesaplama teknolojilerini kullanarak Yapay Zeka iş yüklerini ve model ağırlıklarını koruyun.

 #4.16.1    Level: 3    Role: D/V
 Hassas yapay zeka modellerinin Intel SGX mahfazaları, AMD SEV-SNP veya ARM TrustZone içinde, şifreli bellek ve doğrulama kanıtı ile çalıştığını doğrulayın.
 #4.16.2    Level: 3    Role: D/V
 Gizli konteynerlerin (Kata Containers, gizli hesaplama ile gVisor) donanım tarafından zorunlu kılınan bellek şifrelemesiyle yapay zeka iş yüklerini izole ettiğini doğrulayın.
 #4.16.3    Level: 3    Role: D/V
 Uzak doğrulamanın, yapay zeka modellerini yüklemeden önce bir yürütme ortamının özgünlüğüne kriptografik kanıtla dayanarak enclave bütünlüğünü doğruladığını kontrol edin.
 #4.16.4    Level: 3    Role: D/V
 Gizli yapay zeka çıkarım hizmetlerinin, şifreli hesaplama yoluyla model çıkarımını, mühürlü model ağırlıkları ve korumalı yürütme ile engellediğini doğrulayın.
 #4.16.5    Level: 3    Role: D/V
 Güvenilir yürütme ortamı orkestrasyonunun, uzak teyit ve şifreli iletişim kanalları ile güvenli enclave yaşam döngüsünü yönettiğini doğrulayın.
 #4.16.6    Level: 3    Role: D/V
 Güvenli çok taraflı hesaplamanın (SMPC), bireysel veri setlerini veya model parametrelerini açığa çıkarmadan iş birliği içinde Yapay Zeka eğitimi yapılmasını sağladığını doğrulayın.

---

### C4.17 Sıfır Bilgi Altyapısı

Gizli bilgileri açığa çıkarmadan gizliliği koruyan yapay zeka doğrulama ve kimlik doğrulama için sıfır bilgi ispat sistemleri uygulayın.

 #4.17.1    Level: 3    Role: D/V
 Sıfır bilgi ispatlarının (ZK-SNARK'lar, ZK-STARK'lar) model ağırlıklarını veya eğitim verilerini açığa çıkarmadan yapay zeka model bütünlüğünü ve eğitim kaynağını doğruladığını teyit edin.
 #4.17.2    Level: 3    Role: D/V
 ZK tabanlı kimlik doğrulama sistemlerinin, kimlik bilgilerini açığa çıkarmadan AI hizmetleri için gizliliği koruyan kullanıcı doğrulamasını sağladığını doğrulayın.
 #4.17.3    Level: 3    Role: D/V
 Özel küme kesişimi (PSI) protokollerinin, bireysel veri setlerini açığa çıkarmadan federatif yapay zeka için güvenli veri eşleştirmeyi sağladığını doğrulayın.
 #4.17.4    Level: 3    Role: D/V
 Sıfır bilgi makine öğrenimi (ZKML) sistemlerinin, doğru hesaplamanın kriptografik kanıtıyla doğrulanabilir yapay zeka çıkarımlarını sağladığını doğrulayın.
 #4.17.5    Level: 3    Role: D/V
 ZK-rollupların, toplu doğrulama ve azaltılmış hesaplama yükü ile ölçeklenebilir, gizliliği koruyan AI işlem işleme sağladığını doğrulayın.

---

### C4.18 Yan Kanal Saldırısı Önleme

Zamanlama, güç, elektromanyetik ve önbellek tabanlı yan kanal saldırılarından kaynaklanabilecek hassas bilgilerin sızmasını önlemek için yapay zeka altyapısını koruyun.

 #4.18.1    Level: 3    Role: D/V
 AI çıkarım zamanlamasının, zaman tabanlı model çıkarma saldırılarını önlemek için sabit-zaman algoritmaları ve dolgu kullanılarak normalize edildiğini doğrulayın.
 #4.18.2    Level: 3    Role: D/V
 Güç analizi korumasının, AI donanımı için gürültü enjeksiyonu, güç hattı filtreleme ve rastgeleleştirilmiş yürütme desenlerini içerdiğini doğrulayın.
 #4.18.3    Level: 3    Role: D/V
 Önbellek tabanlı yan kanal hafifletmesinin bilgi sızıntısını önlemek için önbellek bölümlendirmesi, rastgeleleştirme ve temizleme talimatları kullandığını doğrulayın.
 #4.18.4    Level: 3    Role: D/V
 Elektromanyetik yayılım korumasının, TEMPEST tarzı saldırıları önlemek için koruma, sinyal filtreleme ve rastgeleleştirilmiş işlemeyi içerdiğini doğrulayın.
 #4.18.5    Level: 3    Role: D/V
 Mikro mimari yan kanal savunmalarının, spekülatif yürütme kontrolleri ve bellek erişim deseninin gizlenmesini içerdiğini doğrulayın.

---

### C4.19 Nöromorfik ve Özelleşmiş Yapay Zeka Donanım Güvenliği

Nöral morfik çipler, FPGA'lar, özel ASIC'ler ve optik hesaplama sistemleri gibi gelişmekte olan AI donanım mimarilerini güvence altına alın.

 #4.19.1    Level: 3    Role: D/V
 Neuromorfik çip güvenliğinin, spike deseni şifrelemesi, sinaptik ağırlık koruması ve donanım tabanlı öğrenme kuralı doğrulamasını içerdiğini doğrulayın.
 #4.19.2    Level: 3    Role: D/V
 FPGA tabanlı AI hızlandırıcılarının bitstream şifrelemesini, anti-tamper mekanizmalarını ve kimlik doğrulamalı güncellemelerle güvenli yapılandırma yüklemelerini uyguladığını doğrulayın.
 #4.19.3    Level: 3    Role: D/V
 Özel ASIC güvenliğinin, çip üzerinde güvenlik işlemcileri, donanım tabanlı güven kökü ve yan kanal saldırılarına karşı korumalı güvenli anahtar depolama içerdiğini doğrulayın.
 #4.19.4    Level: 3    Role: D/V
 Optik bilgi işlem sistemlerinin kuantum güvenli optik şifreleme, güvenli fotonik anahtarlama ve korumalı optik sinyal işlemeyi uyguladığını doğrulayın.
 #4.19.5    Level: 3    Role: D/V
 Hibrit analog-dijital yapay zeka çiplerinin güvenli analog hesaplama, korumalı ağırlık depolama ve doğrulanmış analogdan dijitale dönüşüm içerdiğini doğrulayın.

---

### C4.20 Gizlilik Koruyucu Hesaplama Altyapısı

Yapay zeka işleme ve analiz sırasında hassas verileri korumak için gizliliği koruyan hesaplama altyapısı kontrollerini uygulayın.

 #4.20.1    Level: 3    Role: D/V
 Homomorfik şifreleme altyapısının, kriptografik bütünlük doğrulaması ve performans izleme ile hassas AI iş yükleri üzerinde şifreli hesaplama yapılmasını sağladığını doğrulayın.
 #4.20.2    Level: 3    Role: D/V
 Özel bilgi alma sistemlerinin, erişim desenlerinin kriptografik koruması ile sorgu desenlerini ortaya çıkarmadan veritabanı sorgularını mümkün kıldığını doğrulayın.
 #4.20.3    Level: 3    Role: D/V
 Güvenli çok taraflı hesaplama protokollerinin, bireysel girdileri veya ara hesaplamaları açığa çıkarmadan gizliliği koruyan AI çıkarımını mümkün kıldığını doğrulayın.
 #4.20.4    Level: 3    Role: D/V
 Gizliliği koruyan anahtar yönetiminin, dağıtık anahtar üretimi, eşik kriptografi ve donanım destekli korumayla güvenli anahtar döndürmeyi içerdiğini doğrulayın.
 #4.20.5    Level: 3    Role: D/V
 Kriptografik güvenlik garantileri korunurken, gizlilik koruyucu hesaplama performansının toplu işleme, önbellekleme ve donanım hızlandırma yoluyla optimize edildiğini doğrulayın.

---

### C4.15 Ajan Çerçevesi Bulut Entegrasyonu Güvenliği ve Hibrit Dağıtım

Hibrit yerinde/bulut mimarilerine sahip bulut entegreli ajan çerçeveleri için güvenlik kontrolleri.

 #4.15.1    Level: 1    Role: D/V
 Bulut depolama entegrasyonunun, ajan tarafından kontrol edilen anahtar yönetimi ile uçtan uca şifreleme kullandığını doğrulayın.
 #4.15.2    Level: 2    Role: D/V
 Hibrit dağıtım güvenlik sınırlarının, şifrelenmiş iletişim kanalları ile açıkça tanımlandığını doğrulayın.
 #4.15.3    Level: 2    Role: D/V
 Bulut kaynak erişiminin, sürekli doğrulama ile sıfır güven (zero-trust) doğrulamasını içerdiğini doğrulayın.
 #4.15.4    Level: 3    Role: D/V
 Veri yerleşim gereksinimlerinin, depolama konumlarının kriptografik kanıtı ile zorunlu kılındığını doğrulayın.
 #4.15.5    Level: 3    Role: D/V
 Bulut sağlayıcı güvenlik değerlendirmelerinin ajanlara özgü tehdit modellemesi ve risk değerlendirmesini içerdiğini doğrulayın.

---

### Kaynaklar

NIST Cybersecurity Framework 2.0
CIS Controls v8
OWASP Container Security Verification Standard
Kubernetes Security Best Practices
SLSA Supply Chain Security Framework
NIST SP 800-190: Application Container Security Guide
Cloud Security Alliance: Cloud Controls Matrix
ENISA: Secure Infrastructure Design
NIST SP 800-53: Security Controls for Federal Information Systems
ISO 27001:2022 Information Security Management
NIST AI Risk Management Framework
CIS Kubernetes Benchmark
FIPS 140-2 Security Requirements
NIST SP 800-207: Zero Trust Architecture
IEEE 2857: Privacy Engineering for AI Systems
NIST SP 800-161: Cybersecurity Supply Chain Risk Management
NIST Post-Quantum Cryptography Standards
Intel SGX Developer Guide
AMD SEV-SNP White Paper
ARM TrustZone Technology
ZK-SNARKs: A Gentle Introduction
NIST SP 800-57: Cryptographic Key Management
Side-Channel Attack Countermeasures
Neuromorphic Computing Security Challenges
FPGA Security: Fundamentals, Evaluation, and Countermeasures
Microsoft SEAL: Homomorphic Encryption Library
HElib: Homomorphic Encryption Library
PALISADE Lattice Cryptography Library
Differential Privacy: A Survey of Results
Secure Aggregation for Federated Learning
Private Information Retrieval: Concepts and Constructions

## C5 Erişim Kontrolü ve Kimlik Doğrulama AI Bileşenleri ve Kullanıcıları için

### Kontrol Amacı

Yapay zeka sistemleri için etkili erişim kontrolü, sağlam kimlik yönetimi, bağlama duyarlı yetkilendirme ve sıfır güven ilkelerine uygun çalışma zamanı uygulamasını gerektirir. Bu kontroller, insanların, hizmetlerin ve otonom ajanların yalnızca açıkça verilen kapsamlar içinde modeller, veriler ve hesaplama kaynakları ile etkileşimde bulunmasını sağlar ve sürekli doğrulama ile denetim yetenekleri sunar.

---

### C5.1 Kimlik Yönetimi ve Doğrulama

Yetkili işlemler için çok faktörlü kimlik doğrulama ile tüm varlıklar için kriptografik olarak desteklenen kimlikler oluşturun.

 #5.1.1    Level: 1    Role: D/V
 Tüm insan kullanıcıların ve hizmet ilkelerinin, benzersiz kimlikten belirteç eşlemeleriyle (paylaşılan hesaplar veya kimlik bilgileri olmadan) OIDC/SAML protokolleri kullanarak merkezi bir kurumsal kimlik sağlayıcısı (IdP) üzerinden kimlik doğruladığından emin olun.
 #5.1.2    Level: 1    Role: D/V
 Yüksek riskli işlemlerin (model dağıtımı, ağırlık ihracatı, eğitim verilerine erişim, üretim yapılandırma değişiklikleri) çok faktörlü kimlik doğrulama veya oturum yeniden doğrulaması ile adım yükseltme kimlik doğrulaması gerektirdiğini doğrulayın.
 #5.1.3    Level: 2    Role: D
 Yeni yöneticilerin üretim sistemine erişim almadan önce, NIST 800-63-3 IAL-2 veya eşdeğer standartlarla uyumlu kimlik doğrulama süreçlerinden geçtiğini doğrulayın.
 #5.1.4    Level: 2    Role: V
 Erişim incelemelerinin, hareketsiz hesapların otomatik tespiti, kimlik bilgisi döndürme zorunluluğu ve hizmet dışı bırakma iş akışları ile birlikte üç ayda bir yapıldığını doğrulayın.
 #5.1.5    Level: 3    Role: D/V
 Federated AI ajanlarının, maksimum geçerlilik süresi 24 saat olan ve kaynak kriptografik kanıtı içeren imzalı JWT beyanları aracılığıyla kimlik doğruladığını doğrulayın.

---

### C5.2 Kaynak Yetkilendirmesi ve Asgari Ayrıcalık

Tüm Yapay Zeka kaynakları için açık izin modelleri ve denetim izleriyle birlikte ince taneli erişim kontrolleri uygulayın.

 #5.2.1    Level: 1    Role: D/V
 Her AI kaynağının (veri kümeleri, modeller, uç noktalar, vektör koleksiyonları, gömme indeksleri, hesaplama örnekleri) rol tabanlı erişim kontrollerini, açıkça belirtilmiş izin listeleri ve varsayılan reddetme politikaları ile uyguladığını doğrulayın.
 #5.2.2    Level: 1    Role: D/V
 Servis hesaplarında en az ayrıcalık prensiplerinin varsayılan olarak uygulandığını doğrulayın; izinler öncelikle salt okunur olarak başlatılmalı ve yazma erişimi için belgelenmiş iş gerekçesi gereklidir.
 #5.2.3    Level: 1    Role: V
 Tüm erişim kontrolü değişikliklerinin onaylanmış değişiklik taleplerine bağlı olduğunu ve zaman damgaları, işlemci kimlikleri, kaynak tanımlayıcıları ve izin farkları ile değiştirilemez şekilde kaydedildiğini doğrulayın.
 #5.2.4    Level: 2    Role: D
 Veri sınıflandırma etiketlerinin (Kişisel Tanımlanabilir Bilgi - PII, Sağlık Bilgisi - PHI, ihracat kontrolü altındaki, özel) türetilmiş kaynaklara (gömülü veriler, istem önbellekleri, model çıktıları) tutarlı politika uygulanmasıyla otomatik olarak aktarıldığını doğrulayın.
 #5.2.5    Level: 2    Role: D/V
 Yetkisiz erişim girişimlerinin ve ayrıcalık yükseltme olaylarının, bağlamsal meta verilerle birlikte 5 dakika içinde SIEM sistemlerine gerçek zamanlı uyarılar tetiklediğini doğrulayın.

---

### C5.3 Dinamik Politika Değerlendirmesi

Denetim yetenekleriyle birlikte bağlama duyarlı yetkilendirme kararları için öznitelik tabanlı erişim kontrolü (ABAC) motorları dağıtın.

 #5.3.1    Level: 1    Role: D/V
 Yetkilendirme kararlarının, kimlik doğrulamalı API'ler aracılığıyla erişilebilen ve kriptografik bütünlük korumasına sahip özel bir politika motoruna (OPA, Cedar veya eşdeğeri) dışsallaştırıldığını doğrulayın.
 #5.3.2    Level: 1    Role: D/V
 Politikaların, kullanıcı yetki seviyesi, kaynak duyarlılık sınıflandırması, istek bağlamı, kiracı izolasyonu ve zamansal kısıtlamalar gibi dinamik özellikleri çalışma zamanında değerlendirdiğini doğrulayın.
 #5.3.3    Level: 2    Role: D
 Politika tanımlarının sürüm kontrollü, eşler arası gözden geçirilmiş ve üretim dağıtımı öncesinde CI/CD boru hatlarında otomatik testlerle doğrulanmış olduğunu doğrulayın.
 #5.3.4    Level: 2    Role: V
 Politika değerlendirme sonuçlarının yapılandırılmış karar gerekçelerini içerdiğini ve korelasyon analizi ile uyumluluk raporlaması için SIEM sistemlerine iletildiğini doğrulayın.
 #5.3.5    Level: 3    Role: D/V
 Politika önbellek zaman aşımı (TTL) değerlerinin, yüksek hassasiyetli kaynaklar için 5 dakikayı, önbellek geçersiz kılma yeteneklerine sahip standart kaynaklar için ise 1 saati aşmadığını doğrulayın.

---

### C5.4 Sorgu Zamanı Güvenlik Uygulaması

Zorunlu filtreleme ve satır düzeyinde güvenlik politikaları ile veritabanı katmanı güvenlik kontrollerini uygulayın.

 #5.4.1    Level: 1    Role: D/V
 Tüm vektör veritabanı ve SQL sorgularının zorunlu güvenlik filtrelerini (kiracı kimliği, hassasiyet etiketleri, kullanıcı kapsamı) içerdiğini ve bu filtrelerin uygulama kodu değil, veritabanı motoru seviyesinde uygulandığını doğrulayın.
 #5.4.2    Level: 1    Role: D/V
 Tüm vektör veritabanları, arama indeksleri ve eğitim veri setleri için politika miras alınması ile satır düzeyi güvenlik (RLS) politikalarının ve alan düzeyi maskelemenin etkinleştirildiğini doğrulayın.
 #5.4.3    Level: 2    Role: D
 Başarısız yetkilendirme değerlendirmelerinin, sorguları derhal sonlandırarak ve boş sonuç setleri döndürmek yerine açık yetkilendirme hata kodları ile yanıt vererek "kafa karışıklığı vekili saldırılarını" engellediğini doğrulayın.
 #5.4.4    Level: 2    Role: V
 Politika değerlendirme gecikmesinin, yetkilendirme atlanmasına olanak tanıyabilecek zaman aşımı durumları için otomatik uyarılarla sürekli olarak izlendiğini doğrulayın.
 #5.4.5    Level: 3    Role: D/V
 Sorgu yeniden deneme mekanizmalarının, aktif kullanıcı oturumları içinde dinamik izin değişikliklerini hesaba katmak için yetkilendirme politikalarını yeniden değerlendirdiğini doğrulayın.

---

### C5.5 Çıktı Filtreleme ve Veri Kaybı Önleme

Yapay zeka tarafından oluşturulan içerikte yetkisiz veri ifşasını önlemek için son işlem kontrolleri uygulayın.

 #5.5.1    Level: 1    Role: D/V
 İçeriği isteklere teslim etmeden önce, çıkarım sonrası filtreleme mekanizmalarının yetkisiz KİŞİSEL TANIMLAYICI BİLGİLERİ (PII), sınıflandırılmış bilgiler ve özel verileri tarayıp sansürlediğini doğrulayın.
 #5.5.2    Level: 1    Role: D/V
 Model çıktılarındaki atıfların, referansların ve kaynak atıflarının, çağıran kişilerin yetkileri doğrultusunda doğrulandığını ve yetkisiz erişim tespit edilirse kaldırıldığını doğrulayın.
 #5.5.3    Level: 2    Role: D
 Kullanıcı izin seviyeleri ve veri sınıflandırmalarına göre çıktı formatı kısıtlamalarının (temizlenmiş PDF'ler, meta verisi kaldırılmış resimler, onaylı dosya türleri) uygulandığını doğrulayın.
 #5.5.4    Level: 2    Role: V
 Kırpma algoritmalarının deterministik, sürüm kontrollü olduğunu ve uyumluluk soruşturmaları ile adli analizleri desteklemek için denetim kayıtlarını tuttuğunu doğrulayın.
 #5.5.5    Level: 3    Role: V
 Yüksek riskli sansürleme olaylarının, verilerin ifşa edilmeden adli inceleme için orijinal içeriğin kriptografik karmalarını içeren uyarlanabilir günlükler oluşturduğunu doğrulayın.

---

### C5.6 Çok Kiracılı İzolasyon

Paylaşılan Yapay Zeka altyapısında kiracılar arasında kriptografik ve mantıksal izolasyon sağlanmalıdır.

 #5.6.1    Level: 1    Role: D/V
 Bellek alanlarının, gömme depolarının, önbellek girişlerinin ve geçici dosyaların her kiracı için isim alanı ayrı tutulduğunu ve kiracı silindiğinde veya oturum sona erdiğinde güvenli biçimde temizlendiğini doğrulayın.
 #5.6.2    Level: 1    Role: D/V
 Her API isteğinin, oturum bağlamı ve kullanıcı yetkileriyle kriptografik olarak doğrulanan kimlik doğrulanmış bir kiracı tanımlayıcısı içerdiğini doğrulayın.
 #5.6.3    Level: 2    Role: D
 Ağ politikalarının servis ağları ve konteyner orkestrasyon platformları içinde kiracılar arası iletişim için varsayılan olarak reddetme kurallarını uyguladığını doğrulayın.
 #5.6.4    Level: 3    Role: D
 Müşteri tarafından yönetilen anahtar (CMK) desteği ve kiracı veri depoları arasında kriptografik izolasyon ile her kiracı için şifreleme anahtarlarının benzersiz olduğunu doğrulayın.

---

### C5.7 Otonom Ajan Yetkilendirmesi

Kapsamlı yetenek belirteçleri ve sürekli yetkilendirme yoluyla yapay zeka ajanları ve otonom sistemler için kontrol izinleri.

 #5.7.1    Level: 1    Role: D/V
 Otonom ajanların, izin verilen eylemler, erişilebilir kaynaklar, zaman sınırları ve operasyonel kısıtlamaları açıkça listeleyen sınırlandırılmış yetki belirteçleri aldığını doğrulayın.
 #5.7.2    Level: 1    Role: D/V
 Yüksek riskli yeteneklerin (dosya sistemi erişimi, kod yürütme, harici API çağrıları, finansal işlemler) varsayılan olarak devre dışı bırakıldığını ve etkinleştirme için iş gerekçeleriyle birlikte açık izinler gerektiğini doğrulayın.
 #5.7.3    Level: 2    Role: D
 Yetenek belirteçlerinin kullanıcı oturumlarına bağlı olduğunu doğrulayın, kriptografik bütünlük korumasını dahil edin ve bunların çevrimdışı senaryolarda saklanamaması veya yeniden kullanılamamasını sağlayın.
 #5.7.4    Level: 2    Role: V
 Temsilci tarafından başlatılan işlemlerin, tam bağlam değerlendirmesi ve denetim kaydı ile birlikte ABAC politika motoru aracılığıyla ikincil yetkilendirmeye tabi tutulduğunu doğrulayın.
 #5.7.5    Level: 3    Role: V
 Ajan hata durumları ve istisna işleme süreçlerinin, olay analizi ve adli araştırmayı desteklemek için yetenek kapsamı bilgilerini içerdiğini doğrulayın.

---

### Referanslar

#### Standartlar ve Çerçeveler

NIST SP 800-63-3: Digital Identity Guidelines
Zero Trust Architecture – NIST SP 800-207
OWASP Application Security Verification Standard (AISVS)
​
#### Uygulama Rehberleri

Identity and Access Management in the AI Era: 2025 Guide – IDSA
Attribute-Based Access Control with OPA – Permify
How We Designed Cedar to Be Intuitive, Fast, and Safe – AWS
​
#### Yapay Zeka'ya Özgü Güvenlik

Row Level Security in Vector DBs for RAG – Bluetuple.ai
Tenant Isolation in Multi-Tenant Systems – WorkOS
Handling AI Agent Permissions – Stytch
OWASP Top 10 for Large Language Model Applications

## Modeller, Çerçeveler ve Veri için C6 Tedarik Zinciri Güvenliği

### Kontrol Hedefi

Yapay zeka tedarik zinciri saldırıları, arka kapılar, önyargılar veya sömürülebilir kod yerleştirmek için üçüncü taraf modelleri, çerçeveleri veya veri kümelerini kullanır. Bu kontroller, tüm model yaşam döngüsünü korumak için uçtan uca köken takibi, zafiyet yönetimi ve izleme sağlar.

---

### C6.1 Önceden Eğitilmiş Modelin Denetimi ve Kökeni

Herhangi bir ince ayar veya dağıtımdan önce üçüncü taraf model kökenlerini, lisanslarını ve gizli davranışlarını değerlendirin ve doğrulayın.

 #6.1.1    Level: 1    Role: D/V
 Her üçüncü taraf model eserinin, kaynak deposunu ve commit hash'ini belirten imzalı bir köken kaydı içerdiğini doğrulayın.
 #6.1.2    Level: 1    Role: D/V
 Modellerin, içe aktarılmadan önce kötü amaçlı katmanlar veya Truva atı tetikleyicileri için otomatik araçlar kullanılarak tarandığından emin olun.
 #6.1.3    Level: 2    Role: D
 Transfer öğrenimi ile ince ayar yapmanın, gizli davranışları tespit etmek için düşmanca değerlendirmeyi geçtiğini doğrulayın.
 #6.1.4    Level: 2    Role: V
 Model lisanslarının, ihracat-kontrol etiketlerinin ve veri-kaynak beyanlarının bir ML-BOM girdisinde kaydedildiğini doğrulayın.
 #6.1.5    Level: 3    Role: D/V
 Yüksek riskli modellerin (herkese açık yüklenmiş ağırlıklar, doğrulanmamış oluşturucular) insan incelemesi ve onayı sağlanana kadar karantinada kaldığını doğrulayın.

---

### C6.2 Çerçeve ve Kütüphane Taraması

Çalışma zamanı yığını güvenli tutmak için ML çerçeveleri ve kütüphanelerini CVE'ler ve kötü amaçlı kodlar açısından sürekli tarayın.

 #6.2.1    Level: 1    Role: D/V
 CI boru hatlarının AI çerçeveleri ve kritik kütüphaneler üzerinde bağımlılık tarayıcıları çalıştırdığını doğrulayın.
 #6.2.2    Level: 1    Role: D/V
 Kritik güvenlik açıklarının (CVSS ≥ 7.0) üretim imajlarına geçişi engellediğini doğrulayın.
 #6.2.3    Level: 2    Role: D
 Forklanmış veya tedarik edilmiş ML kütüphanelerinde statik kod analizinin çalıştığını doğrulayın.
 #6.2.4    Level: 2    Role: V
 Çerçeve yükseltme önerilerinin, genel CVE beslemelerine referans veren bir güvenlik etki değerlendirmesi içerdiğini doğrulayın.
 #6.2.5    Level: 3    Role: V
 Çalışma zamanı sensörlerinin, imzalı SBOM'dan sapma gösteren beklenmeyen dinamik kütüphane yüklemelerinde uyarı verdiğini doğrulayın.

---

### C6.3 Bağımlılık Sabitleme ve Doğrulama

Her bağımlılığı değiştirilemez özetlere sabitleyin ve aynı, müdahale edilmemiş yapıtları garanti etmek için yapıları yeniden üretin.

 #6.3.1    Level: 1    Role: D/V
 Tüm paket yöneticilerinin kilit dosyaları (lockfile) aracılığıyla sürüm sabitlemesini (version pinning) zorunlu kıldığını doğrulayın.
 #6.3.2    Level: 1    Role: D/V
 Konteyner referanslarında değiştirilebilir etiketler yerine değiştirilemez özetlerin kullanıldığını doğrulayın.
 #6.3.3    Level: 2    Role: D
 Tekrarlanabilir yapılar kontrollerinin, aynı çıktıları sağlamak için CI çalışmaları arasında hashleri karşılaştırdığını doğrulayın.
 #6.3.4    Level: 2    Role: V
 İnceleme izlenebilirliği için yapı belgelerinin 18 ay boyunca saklandığını doğrulayın.
 #6.3.5    Level: 3    Role: D
 Süresi dolmuş bağımlılıkların, sabitlenmiş sürümleri güncellemek veya çatallamak için otomatik PR'leri tetiklediğini doğrulayın.

---

### C6.4 Güvenilir Kaynak Uygulaması

Sadece kriptografik olarak doğrulanmış, kuruluş tarafından onaylanmış kaynaklardan artefakt indirmesine izin verin ve diğer her şeyi engelleyin.

 #6.4.1    Level: 1    Role: D/V
 Model ağırlıklarının, veri setlerinin ve konteynerlerin yalnızca onaylanmış alan adlarından veya dahili kayıt defterlerinden indirildiğini doğrulayın.
 #6.4.2    Level: 1    Role: D/V
 Sigstore/Cosign imzalarının, artefaktlar yerel olarak önbelleğe alınmadan önce yayıncı kimliğini doğruladığını teyit edin.
 #6.4.3    Level: 2    Role: D
 Eris çıkış vekillerinin, güvenilen kaynak politikası uygulamak için kimlik doğrulaması yapılmamış nesne indirmelerini engellediğini doğrulayın.
 #6.4.4    Level: 2    Role: V
 Depo izin listelerinin her madde için iş gerekçesi kanıtı ile birlikte üç ayda bir gözden geçirildiğini doğrulayın.
 #6.4.5    Level: 3    Role: V
 Politika ihlallerinin eserleri karantinaya almayı ve bağlı boru hattı çalıştırmalarının geri alınmasını tetiklediğini doğrulayın.

---

### C6.5 Üçüncü Taraf Veri Kümesi Risk Değerlendirmesi

Dış veri setlerini zehirlenme, önyargı ve yasal uyumluluk açısından değerlendirin ve yaşam döngüleri boyunca izleyin.

 #6.5.1    Level: 1    Role: D/V
 Dış veri setlerinin zehirlenme risk puanlamasından geçtiğini doğrulayın (örneğin, veri parmak izi çıkarma, aykırı değer tespiti).
 #6.5.2    Level: 1    Role: D
 Veri seti onayından önce önyargı metriklerinin (demografik denklik, eşit fırsat) hesaplandığını doğrulayın.
 #6.5.3    Level: 2    Role: V
 Veri kümeleri için kaynak ve lisans şartlarının ML-BOM kayıtlarında yakalandığını doğrulayın.
 #6.5.4    Level: 2    Role: V
 Barındırılan veri setlerindeki kayma veya bozulmanın periyodik izleme ile tespit edildiğini doğrulayın.
 #6.5.5    Level: 3    Role: D
 Eğitim öncesinde yasaklanmış içeriğin (telif hakkı, kişisel tanımlanabilir bilgi - PII) otomatik temizleme yoluyla kaldırıldığını doğrulayın.

---

### C6.6 Tedarik Zinciri Saldırısı İzleme

CVE beslemeleri, denetim kaydı analizleri ve kırmızı takım simülasyonları yoluyla tedarik zinciri tehditlerini erken tespit edin.

 #6.6.1    Level: 1    Role: V
 CI/CD denetim günlüklerinin, anormal paket çekme işlemleri veya değiştirilmiş derleme adımları için SIEM tespitlerine aktarıldığını doğrulayın.
 #6.6.2    Level: 2    Role: D
 Olay müdahale oyun kitaplarının, ihlal edilmiş modeller veya kütüphaneler için geri alma prosedürlerini içerdiğini doğrulayın.
 #6.6.3    Level: 3    Role: V
 Tehdit istihbaratı zenginleştirme etiketlerinin, uyarı sınıflandırmasında makine öğrenimi özel göstergelerini (örneğin, model zehirleme IoC’leri) doğruladığını kontrol edin.

---

### C6.7 Model Nesneleri için ML-BOM

Detaylı ML'ye özgü SBOM'lar (ML-BOM'lar) oluşturun ve imzalayın, böylece sonraki kullanıcılar dağıtım anında bileşen bütünlüğünü doğrulayabilir.

 #6.7.1    Level: 1    Role: D/V
 Her model artefaktının veri setleri, ağırlıklar, hiperparametreler ve lisansları listeleyen bir ML-BOM yayımladığını doğrulayın.
 #6.7.2    Level: 1    Role: D/V
 ML-BOM oluşturma ve Cosign imzalamanın CI içinde otomatikleştirildiğini ve birleştirme için gerekli olduğunu doğrulayın.
 #6.7.3    Level: 2    Role: D
 ML‑BOM eksik bileşen meta verisi (hash, lisans) varsa derlemenin başarısız olduğunu doğrulayın.
 #6.7.4    Level: 2    Role: V
 Aşağıdaki kullanıcıların ML-BOM'ları, dağıtım sırasında ithal edilen modelleri doğrulamak için API üzerinden sorgulayabildiğini doğrulayın.
 #6.7.5    Level: 3    Role: V
 ML-BOM'ların sürüm kontrolünün yapıldığını ve yetkisiz değişiklikleri tespit etmek için farklarının alındığını doğrulayın.

---

### Referanslar

ML Supply Chain Compromise – MITRE ATLAS
Supply‑chain Levels for Software Artifacts (SLSA)
CycloneDX – Machine Learning Bill of Materials
What is Data Poisoning? – SentinelOne
Transfer Learning Attack – OWASP ML Security Top 10
AI Data Security Best Practices – CISA
Secure CI/CD Supply Chain – Sumo Logic
AI & Transparency: Protect ML Models – ReversingLabs
SBOM Overview – CISA
Training Data Poisoning Guide – Lakera.ai
Dependency Pinning for Reproducible Python – Medium

## C7 Model Davranışı, Çıktı Kontrolü ve Güvenlik Güvencesi

### Kontrol Amacı

Model çıktıları yapılandırılmış, güvenilir, güvenli, açıklanabilir olmalı ve üretimde sürekli izlenmelidir. Bu, gerçek dışı içerikleri, gizlilik sızıntılarını, zararlı içerikleri ve kontrol dışı eylemleri azaltırken, kullanıcı güvenini ve düzenleyici uyumu artırır.

---

### C7.1 Çıktı Formatı Zorlaması

Sıkı şemalar, kısıtlı çözümleme ve sonraki doğrulama, bozuk veya kötü niyetli içeriğin yayılmasını engeller.

 #7.1.1    Level: 1    Role: D/V
 Yanıt şemalarının (örn., JSON Şeması) sistem isteminde sağlandığını ve her çıktının otomatik olarak doğrulandığını doğrulayın; uyumsuz çıktılar onarım veya reddedilmeyi tetikler.
 #7.1.2    Level: 1    Role: D/V
 Taşma veya istem enjeksiyonu yan kanal saldırılarını önlemek için kısıtlı çözümlemenin (durdurma tokenları, regex, maksimum token sayısı) etkinleştirildiğini doğrulayın.
 #7.1.3    Level: 2    Role: D/V
 Aşağıdaki bileşenlerin çıktıları güvenilmez olarak ele aldığını ve bunları şemalar veya enjeksiyona karşı güvenli de-serializatörlere karşı doğruladığını kontrol edin.
 #7.1.4    Level: 3    Role: V
 Yanlış çıktı olaylarının kaydedildiğini, hız sınırlaması uygulandığını ve izlemeye yansıtıldığını doğrulayın.

---

### C7.2 Halüsinasyon Tespiti ve Azaltılması

Belirsizlik tahmini ve yedek stratejiler, uydurma yanıtları engeller.

 #7.2.1    Level: 1    Role: D/V
 Token düzeyinde log-olasılıkların, topluluk içi tutarlılığın veya ince ayarlı halüsinasyon tespitçilerinin her yanıta bir güven skoru atadığını doğrulayın.
 #7.2.2    Level: 1    Role: D/V
 Yapılandırılabilir bir güven eşiğinin altındaki yanıtların, geri çekme iş akışlarını (ör. bilgiye dayalı üretim, ikincil model veya insan incelemesi) tetiklediğini doğrulayın.
 #7.2.3    Level: 2    Role: D/V
 Halüsinasyon olaylarının kök neden meta verisi ile etiketlendiğini ve post-mortem ile ince ayar (finetuning) iş akışlarına aktarıldığını doğrulayın.
 #7.2.4    Level: 3    Role: D/V
 Büyük model veya bilgi tabanı güncellemelerinden sonra eşik değerlerinin ve algılayıcıların tekrar kalibre edildiğini doğrulayın.
 #7.2.5    Level: 3    Role: V
 Gösterge paneli görselleştirmelerinin halüsinasyon oranlarını takip ettiğini doğrulayın.

---

### C7.3 Çıktı Güvenliği ve Gizlilik Filtreleme

Politika filtreleri ve red-team kapsamı, kullanıcıları ve gizli verileri korur.

 #7.3.1    Level: 1    Role: D/V
 Ön ve son üretim sınıflandırıcılarının, politika ile uyumlu nefret, taciz, kendine zarar verme, aşırılık yanlısı ve cinsel içerikli materyalleri engellediğini doğrulayın.
 #7.3.2    Level: 1    Role: D/V
 Her yanıtta Kişisel Tanımlanabilir Bilgi (PII) / Ödeme Kartı Endüstrisi (PCI) tespiti ve otomatik sansürün çalıştığını doğrulayın; ihlaller gizlilik olayını tetikler.
 #7.3.3    Level: 2    Role: D
 Gizlilik etiketlerinin (örneğin, ticari sırlar) metin, resim veya kodda sızıntıyı önlemek için modlar arasında yayıldığını doğrulayın.
 #7.3.4    Level: 3    Role: D/V
 Filtre atlama girişimlerinin veya yüksek riskli sınıflandırmaların ikincil onay veya kullanıcı tekrar kimlik doğrulaması gerektirdiğini doğrulayın.
 #7.3.5    Level: 3    Role: D/V
 Filtreleme eşiklerinin yasal yargı alanları ve kullanıcı yaşı/rol bağlamını yansıttığını doğrulayın.

---

### C7.4 Çıktı ve Eylem Kısıtlaması

Oran sınırları ve onay kapıları, kötüye kullanımı ve aşırı özerkliği önler.

 #7.4.1    Level: 1    Role: D
 429 hatalarında üstel geri çekilme ile kullanıcı başına ve API anahtarı başına kota sınırlarının istekleri, tokenları ve maliyeti kısıtladığını doğrulayın.
 #7.4.2    Level: 1    Role: D/V
 Ayrıcalıklı işlemlerin (dosya yazımları, kod yürütme, ağ çağrıları) politika tabanlı onay veya insan müdahalesi gerektirdiğini doğrulayın.
 #7.4.3    Level: 2    Role: D/V
 Çapraz modlu tutarlılık kontrollerinin, aynı istek için oluşturulan görüntülerin, kodun ve metnin kötü amaçlı içerik gizlemek için kullanılamayacağından emin olunmasını doğrulayın.
 #7.4.4    Level: 2    Role: D
 Ajan delege derinliği, özyineleme sınırları ve izin verilen araç listelerinin açıkça yapılandırıldığını doğrulayın.
 #7.4.5    Level: 3    Role: V
 Limit ihlalinin SIEM alımı için yapılandırılmış güvenlik olayları yaydığını doğrulayın.

---

### C7.5 Çıktı Açıklanabilirliği

Şeffaf sinyaller kullanıcı güvenini ve dahili hata ayıklamayı artırır.

 #7.5.1    Level: 2    Role: D/V
 Risk değerlendirmesi uygun gördüğünde, kullanıcıya yönelik güven puanlarının veya kısa mantık özetlerinin gösterildiğini doğrulayın.
 #7.5.2    Level: 2    Role: D/V
 Oluşturulan açıklamaların hassas sistem istemlerini veya tescilli verileri ifşa etmediğini doğrulayın.
 #7.5.3    Level: 3    Role: D
 Sistemin, token düzeyinde olasılık günlüklerini veya dikkat haritalarını yakalayarak yetkili inceleme için depoladığını doğrulayın.
 #7.5.4    Level: 3    Role: V
 Açıklanabilirlik artefaktlarının denetlenebilirlik için model sürümleriyle birlikte sürüm kontrolünün yapıldığını doğrulayın.

---

### C7.6 İzleme Entegrasyonu

Gerçek zamanlı gözlemlenebilirlik, geliştirme ile üretim arasındaki döngüyü kapatır.

 #7.6.1    Level: 1    Role: D
 Metriklerin (şema ihlalleri, halüsinasyon oranı, toksisite, KİB sızıntıları, gecikme süresi, maliyet) merkezi bir izleme platformuna aktarıldığını doğrulayın.
 #7.6.2    Level: 1    Role: V
 Her güvenlik metriği için uyarı eşikleri tanımlandığını ve çağrı üzerine yükseltme yollarının bulunduğunu doğrulayın.
 #7.6.3    Level: 2    Role: V
 Gösterge tablolarının çıktı anormalliklerini model/sürüm, özellik bayrağı ve yukarı akış veri değişiklikleri ile ilişkilendirdiğini doğrulayın.
 #7.6.4    Level: 2    Role: D/V
 Belgelenmiş bir MLOps iş akışı içinde, izleme verilerinin yeniden eğitim, ince ayar veya kural güncellemelerine geri besleme yapmasını doğrulayın.
 #7.6.5    Level: 3    Role: V
 Hassas günlüklerin sızıntısını önlemek için izleme boru hatlarının penetrasyon testlerinin yapıldığını ve erişim kontrollerinin uygulandığını doğrulayın.

---

### 7.7 Üretken Medya Güvenlik Önlemleri

AI sistemlerinin yasa dışı, zararlı veya yetkisiz medya içeriği üretmemesini sağlamak için politika kısıtlamalarını, çıktı doğrulamasını ve izlenebilirliği uygulayın.

 #7.7.1    Level: 1    Role: D/V
 Sistem istemlerinin ve kullanıcı talimatlarının yasa dışı, zararlı veya rızaya dayanmayan deepfake medya (örneğin, görüntü, video, ses) oluşturulmasını açıkça yasakladığını doğrulayın.
 #7.7.2    Level: 2    Role: D/V
 İsteklerin taklit oluşturma girişimleri, cinsel içerikli derin sahte videolar veya gerçek kişileri izinsiz gösteren medyalar için filtrelendiğini doğrulayın.
 #7.7.3    Level: 2    Role: V
 Sistemin, telif hakkıyla korunan medyanın yetkisiz çoğaltılmasını önlemek için algısal özetleme (perceptual hashing), filigran (watermark) tespiti veya parmak izi (fingerprinting) yöntemlerini kullandığını doğrulayın.
 #7.7.4    Level: 3    Role: D/V
 Tüm oluşturulan medyanın, aşağı akıştaki izlenebilirlik için kriptografik olarak imzalanmış, filigranlı veya değiştirilemez köken meta verisi ile gömülü olduğunu doğrulayın.
 #7.7.5    Level: 3    Role: V
 Atlatma girişimlerinin (örneğin, prompt karartma, argo, düşmanca ifadeler) tespit edildiğinden, kaydedildiğinden ve hız sınırlamasına tabi tutulduğundan emin olun; tekrarlayan kötüye kullanımlar izleme sistemlerine bildirilsin.

### Referanslar

NIST AI Risk Management Framework
ISO/IEC 42001:2023 – AI Management System
OWASP Top-10 for Large Language Model Applications (2025)
Improper Output Handling – OWASP LLM05:2025
Practical Techniques to Constrain LLM Output
Dataiku – Structured Text Generation Guide
VL-Uncertainty: Detecting Hallucinations
HaDeMiF: Hallucination Detection & Mitigation
Building Confidence in LLM Outputs
Explainable AI & LLMs
LLM Red-Teaming Guide
Sensitive Information Disclosure in LLMs
LangChain – Chat Model Rate Limiting
OpenAI Rate-Limit & Exponential Back-off
Arize AI – LLM Observability Platform

## C8 Bellek, Gömütler ve Vektör Veritabanı Güvenliği

### Kontrol Amacı

Gömülü temsiller ve vektör depoları, kullanıcıdan gelen verileri sürekli kabul eden ve bunları Geri Getirme Destekli Üretim (Retrieval-Augmented Generation, RAG) yoluyla model bağlamlarına geri sunan çağdaş yapay zeka sistemlerinin "canlı belleği" olarak işlev görür. Bu bellek düzgün şekilde denetlenmezse, kişisel tanımlanabilir bilgilerin (PII) sızmasına, onay ihlaline veya orijinal metnin tersine mühendislik ile yeniden oluşturulmasına yol açabilir. Bu kontrol ailesinin amacı, bellek boru hatlarını ve vektör veritabanlarını en az ayrıcalık erişimi olacak şekilde güçlendirmek, gömülülerin gizliliği korumasını sağlamak, depolanan vektörlerin süresinin dolmasını veya talep üzerine iptalini mümkün kılmak ve kullanıcı başına belleğin hiçbir zaman başka bir kullanıcının istemlerini veya tamamlamalarını kirletmemesini temin etmektir.

---

### C8.1 Bellek ve RAG İndekslerinde Erişim Kontrolleri

Her vektör koleksiyonunda ince taneli erişim kontrollerini uygulayın.

 #8.1.1    Level: 1    Role: D/V
 Kayıt/isim alanı düzeyindeki erişim kontrol kurallarının, kiracı, koleksiyon veya belge etiketi başına ekleme, silme ve sorgulama işlemlerini sınırladığını doğrulayın.
 #8.1.2    Level: 1    Role: D/V
 API anahtarlarının veya JWT'lerin kapsamlı talepler (örneğin, koleksiyon kimlikleri, eylem fiilleri) taşıdığını ve en az üç ayda bir yenilendiğini doğrulayın.
 #8.1.3    Level: 2    Role: D/V
 Ayrıcalık yükseltme denemelerinin (örneğin, çapraz ad alanı benzerliği sorguları) tespit edilip 5 dakika içinde bir SIEM'e kaydedildiğini doğrulayın.
 #8.1.4    Level: 2    Role: D/V
 Vektör veritabanının, denetim kayıtlarında konu tanımlayıcısı, işlem, vektör kimliği/isim alanı, benzerlik eşiği ve sonuç sayısını kaydettiğini doğrulayın.
 #8.1.5    Level: 3    Role: V
 Erişim kararlarının, motorlar yükseltildiğinde veya indeks parçalaması kuralları değiştiğinde atlatma hatalarına karşı test edildiğini doğrulayın.

---

### C8.2 Gömme Temizleme ve Doğrulama

Metni vektörleştirmeden önce Kişisel Tanımlanabilir Bilgiler (PII) için ön taramadan geçirin, gizleyin veya takma ad kullanarak anonimleştirin ve isteğe bağlı olarak kalıntı sinyalleri kaldırmak için yerleştirmeleri sonradan işleyin.

 #8.2.1    Level: 1    Role: D/V
 PII ve düzenlemeye tabi verilerin otomatik sınıflandırıcılar aracılığıyla tespit edilip edilmediğini ve gömme öncesinde maskeleme, tokenleştirme veya silme işlemlerinin yapılıp yapılmadığını doğrulayın.
 #8.2.2    Level: 1    Role: D
 Gömme (embedding) boru hatlarının, dizini zehirleyebilecek yürütülebilir kod veya UTF-8 olmayan eserler içeren girdileri reddettiğini veya karantinaya aldığını doğrulayın.
 #8.2.3    Level: 2    Role: D/V
 Herhangi bir bilinen KİB (Kişisel Identifiable Bilgi) tokenine olan uzaklığı, yapılandırılabilir bir eşik değerin altında kalan cümle gömme vektörlerine yerel veya metrik diferansiyel gizlilik dezenfeksiyonu uygulandığını doğrulayın.
 #8.2.4    Level: 2    Role: V
 Temizleme etkinliğinin (örneğin, Kişisel Tanımlanabilir Bilgilerin (PII) kırpılmasının geri çağrılması, anlamsal sapma) en az altı ayda bir karşılaştırma korpuslarına karşı doğrulandığından emin olun.
 #8.2.5    Level: 3    Role: D/V
 Temizleme yapılandırmalarının sürüm kontrolünde olduğunu ve değişikliklerin eş değerlendirmesinden geçtiğini doğrulayın.

---

### C8.3 Bellek Süresi Dolumu, İptali ve Silinmesi

GDPR "unutulma hakkı" ve benzeri yasalar zamanında silme gerektirir; bu nedenle, vektör depoları, iptal edilen vektörlerin geri kurtarılamaması veya yeniden indekslenememesi için TTL, kalıcı silme ve mezar taşı mekanizmalarını desteklemelidir.

 #8.3.1    Level: 1    Role: D/V
 Her vektör ve meta veri kaydının, otomatik temizleme işleri tarafından dikkate alınan bir TTL (Yaşam Süresi) veya açık bir saklama etiketi taşıdığını doğrulayın.
 #8.3.2    Level: 1    Role: D/V
 Kullanıcı tarafından başlatılan silme taleplerinin vektörleri, meta verileri, önbellek kopyalarını ve türetilmiş indeksleri 30 gün içinde temizlediğini doğrulayın.
 #8.3.3    Level: 2    Role: D
 Donanım destekliyorsa, mantıksal silme işlemlerinin depolama bloklarının kriptografik olarak imha edilmesiyle veya anahtar kasası anahtarının yok edilmesiyle takip edildiğini doğrulayın.
 #8.3.4    Level: 3    Role: D/V
 Süresi dolmuş vektörlerin, süresi dolduktan < 500 ms içinde en yakın komşu arama sonuçlarından hariç tutulduğunu doğrulayın.

---

### C8.4 Gömülü Tersine Çevirme ve Sızıntıyı Önleme

Son savunmalar—gürültü üst üste bindirme, projeksiyon ağları, gizlilik-nöron bozulması ve uygulama katmanı şifrelemesi—token düzeyindeki tersine çevirme oranlarını %5'in altına indirebilir.

 #8.4.1    Level: 1    Role: V
 Tersine mühendislik, üyelik ve özellik çıkarımı saldırılarını kapsayan resmi bir tehdit modelinin var olduğunu ve yıllık olarak incelendiğini doğrulayın.
 #8.4.2    Level: 2    Role: D/V
 Uygulama katmanı şifrelemesinin veya aranabilir şifrelemenin, altyapı yöneticileri veya bulut personelinin vektörleri doğrudan okumasını engellediğini doğrulayın.
 #8.4.3    Level: 3    Role: V
 Savunma parametrelerinin (DP için ε, gürültü σ, projeksiyon derecesi k) gizliliği ≥ %99 token koruması ve faydayı ≤ %3 doğruluk kaybı olacak şekilde dengelediğini doğrulayın.
 #8.4.4    Level: 3    Role: D/V
 Model güncellemeleri için yayın kapılarının bir parçası olarak tersine çevirme-direnç metriklerinin doğrulandığından ve regresyon bütçelerinin tanımlandığından emin olun.

---

### C8.5 Kullanıcıya Özel Bellek İçin Kapsam Yürürlüğe Koyma

Çapraz kiracı sızıntısı hâlâ en önemli RAG riski olarak kalmaktadır: yanlış filtrelenmiş benzerlik sorguları başka bir müşterinin özel belgelerini ortaya çıkarabilir.

 #8.5.1    Level: 1    Role: D/V
 Her bir sorgunun, LLM isteğine iletilmeden önce kiracı/kullanıcı kimliği tarafından son filtrelemeden geçirildiğini doğrulayın.
 #8.5.2    Level: 1    Role: D
 Koleksiyon isimlerinin veya ad alanlı kimliklerin, kullanıcı veya kiracı bazında tuzlanarak vektörlerin kapsamlar arasında çakışmasının önlendiğini doğrulayın.
 #8.5.3    Level: 2    Role: D/V
 Benzerlik sonuçlarının yapılandırılabilir bir mesafe eşik değerinin üzerinde ancak çağıranın kapsamı dışında olduğunun doğrulanmasını sağlayın ve bu durumun güvenlik uyarılarını tetiklemesini sağlayın.
 #8.5.4    Level: 2    Role: V
 Çok kiracılı stres testlerinin, kapsam dışı belgeleri almaya çalışan adversaryal sorguları simüle ettiğini ve sıfır sızıntı gösterdiğini doğrulayın.
 #8.5.5    Level: 3    Role: D/V
 Şifreleme anahtarlarının her kiracı için ayrıldığını doğrulayın ve fiziksel depolama paylaşılmış olsa bile kriptografik izolasyonu sağlayın.

---

### C8.6 Gelişmiş Bellek Sistemi Güvenliği

Özel izolasyon ve doğrulama gereksinimleriyle birlikte epizodik, semantik ve çalışma belleği gibi gelişmiş bellek mimarileri için güvenlik kontrolleri.

 #8.6.1    Level: 1    Role: D/V
 Farklı bellek türlerinin (episodik, semantik, çalışma belleği) rol tabanlı erişim kontrolleri, ayrı şifreleme anahtarları ve her bellek türü için belgelenmiş erişim desenleri ile izole edilmiş güvenlik bağlamlarına sahip olduğunu doğrulayın.
 #8.6.2    Level: 2    Role: D/V
 Bellek pekiştirme süreçlerinin, içerik temizleme, kaynak doğrulama ve saklama öncesi bütünlük kontrolleri yoluyla kötü amaçlı anıların enjekte edilmesini önlemek için güvenlik doğrulamasını içerdiğini doğrulayın.
 #8.6.3    Level: 2    Role: D/V
 Bellek getirme sorgularının, sorgu desen analizi, erişim kontrolü uygulaması ve sonuç filtreleme yoluyla yetkisiz bilgi çıkarımını önlemek için doğrulandığından ve temizlendiğinden emin olun.
 #8.6.4    Level: 3    Role: D/V
 Anahtar silme, çok geçişli üzerine yazma veya doğrulama sertifikaları ile donanım tabanlı güvenli silme kullanarak kriptografik silme garantileriyle hafıza unutma mekanizmalarının hassas bilgileri güvenli bir şekilde sildiğini doğrulayın.
 #8.6.5    Level: 3    Role: D/V
 Bellek sistemi bütünlüğünün, normal işlemler dışındaki bellek içeriği değişikliklerinde özet kontrolleri, denetim günlükleri ve otomatik uyarılar aracılığıyla yetkisiz değişiklikler veya bozulmalar için sürekli olarak izlendiğini doğrulayın.

---

### Referanslar

Vector database security: Pinecone – IronCore Labs
Securing the Backbone of AI: Safeguarding Vector Databases and Embeddings – Privacera
Enhancing Data Security with RBAC of Qdrant Vector Database – AI Advances
Mitigating Privacy Risks in LLM Embeddings from Embedding Inversion – arXiv
DPPN: Detecting and Perturbing Privacy-Sensitive Neurons – OpenReview
Art. 17 GDPR – Right to Erasure
Sensitive Data in Text Embeddings Is Recoverable – Tonic.ai
PII Identification and Removal – NVIDIA NeMo Docs
De-identifying Sensitive Data – Google Cloud DLP
Remove PII from Conversations Using Sensitive Information Filters – AWS Bedrock Guardrails
Think Your RAG Is Secure? Think Again – Medium
Design a Secure Multitenant RAG Inferencing Solution – Microsoft Learn
Best Practices for Multi-Tenancy RAG with Milvus – Milvus Blog

## 9 Otonom Orkestrasyon ve Temsilci Aksiyon Güvenliği

### Kontrol Hedefi

Otonom veya çoklu ajan yapay zeka sistemlerinin yalnızca açıkça amaçlanan, doğrulanabilen, denetlenebilir ve sınırlandırılmış maliyet ve risk eşiklerine uygun işlemleri gerçekleştirebilmesini sağlayın. Bu, Otonom Sistem İhlali, Araç Kötüye Kullanımı, Ajan Döngüsü Tespiti, İletişim Ele Geçirme, Kimlik Sahteciliği, Sürü Manipülasyonu ve Niyet Manipülasyonu gibi tehditlere karşı koruma sağlar.

---

### 9.1 Ajan Görev Planlaması ve Özyineleme Bütçeleri

Özel yetkili işlemler için yinelemeli planları sınırlayın ve insan kontrol noktalarını zorunlu kılın.

 #9.1.1    Level: 1    Role: D/V
 Maksimum özyineleme derinliği, genişlik, gerçek zamanlı saat süresi, token sayısı ve her bir ajan yürütme başına parasal maliyetin merkezi olarak yapılandırıldığını ve sürüm kontrolüne tabi olduğunu doğrulayın.
 #9.1.2    Level: 1    Role: D/V
 Ayrıcalıklı veya geri alınamaz işlemlerin (örneğin, kod gönderimleri, finansal transferler) yürütülmeden önce denetlenebilir bir kanal üzerinden açıkça insan onayı gerektirdiğini doğrulayın.
 #9.1.3    Level: 2    Role: D
 Gerçek zamanlı kaynak izleyicilerinin herhangi bir bütçe eşiği aşıldığında devre kesici kesintisini tetiklediğini ve daha fazla görev genişletilmesini durdurduğunu doğrulayın.
 #9.1.4    Level: 2    Role: D/V
 Devre kesici olaylarının, adli inceleme amacıyla ajan kimliği, tetikleyici koşul ve yakalanan plan durumu ile kaydedildiğini doğrulayın.
 #9.1.5    Level: 3    Role: V
 Güvenlik testlerinin bütçe tükenmesi ve kontrolden çıkan plan senaryolarını kapsadığını doğrulayarak, veri kaybı olmadan güvenli durdurmayı teyit edin.
 #9.1.6    Level: 3    Role: D
 Bütçe politikalarının kod olarak politika şeklinde ifade edildiğini ve yapılandırma sapmasını engellemek için CI/CD'de uygulandığını doğrulayın.

---

### 9.2 Araç Eklenti Kutulama (Sandboxing)

Yetkisiz sistem erişimi veya kod yürütmesini önlemek için araç etkileşimlerini izole edin.

 #9.2.1    Level: 1    Role: D/V
 Her aracın/eklentinin, en az ayrıcalıklı dosya sistemi, ağ ve sistem çağrısı politikalarıyla bir işletim sistemi, konteyner veya WASM seviyesi sandbox içinde çalıştığını doğrulayın.
 #9.2.2    Level: 1    Role: D/V
 Sandbox kaynak kotalarının (CPU, bellek, disk, ağ çıkışı) ve yürütme zaman aşımı sürelerinin uygulanıp uygulanmadığını ve kaydedilip kaydedilmediğini doğrulayın.
 #9.2.3    Level: 2    Role: D/V
 Araç ikili dosyalarının veya tanımlayıcılarının dijital olarak imzalandığını doğrulayın; imzalar yüklemeden önce doğrulanır.
 #9.2.4    Level: 2    Role: V
 Sandbox telemetrisinin bir SIEM'e aktarıldığını doğrulayın; anormallikler (örneğin, yapılan dışa bağlantı girişimleri) uyarılar oluşturur.
 #9.2.5    Level: 3    Role: V
 Yüksek riskli eklentilerin üretim ortamına dağıtılmadan önce güvenlik incelemesi ve sızma testi sürecinden geçirildiğini doğrulayın.
 #9.2.6    Level: 3    Role: D/V
 Sandbox kaçış girişimlerinin otomatik olarak engellendiğini ve suçlu eklentinin inceleme yapılana kadar karantinaya alındığını doğrulayın.

---

### 9.3 Otonom Döngü ve Maliyet Sınırlandırma

Kontrolsüz ajanlar arası özyinelemeyi ve maliyet patlamalarını tespit edip durdurun.

 #9.3.1    Level: 1    Role: D/V
 Aracılar arası çağrıların, çalışma zamanının azalttığı ve uyguladığı bir atlama sınırı veya TTL içerdiğini doğrulayın.
 #9.3.2    Level: 2    Role: D
 Ajanların kendini çağırma veya döngüsel desenleri tespit etmek için benzersiz bir çağrı-grafiği kimliğini koruduğunu doğrulayın.
 #9.3.3    Level: 2    Role: D/V
 Kümülatif hesap birimi ve harcama sayaçlarının istek zinciri başına takip edildiğini doğrulayın; limit aşıldığında zincir iptal edilir.
 #9.3.4    Level: 3    Role: V
 Ajan protokollerinde sınırsız özyinelemenin olmadığını göstermek için resmi analiz veya model doğrulama yöntemlerinin kullanıldığını doğrulayın.
 #9.3.5    Level: 3    Role: D
 Döngü-durdurma olaylarının uyarılar oluşturduğunu ve sürekli iyileştirme metriklerine veri sağladığını doğrulayın.

---

### 9.4 Protokol Düzeyi Kötüye Kullanım Koruması

Eleştirmenlik veya manipülasyonu önlemek için ajanlar ile harici sistemler arasında güvenli iletişim kanalları sağlayın.

 #9.4.1    Level: 1    Role: D/V
 Tüm ajan-aracı ve ajan-ajan mesajlarının kimlik doğrulamasının (örneğin, karşılıklı TLS veya JWT) yapıldığını ve uçtan uca şifrelendiğini doğrulayın.
 #9.4.2    Level: 1    Role: D
 Şemaların kesin olarak doğrulandığını teyit edin; bilinmeyen alanlar veya hatalı biçimlendirilmiş mesajlar reddedilir.
 #9.4.3    Level: 2    Role: D/V
 Bütün mesaj yükü, araç parametreleri dahil, bütünlüğü doğrulama kontrollerinin (MAC'ler veya dijital imzalar) kapsamına alındığını doğrulayın.
 #9.4.4    Level: 2    Role: D
 Yinelenen saldırı korumasının (tekrar kullanım önleyici nonce'lar veya zaman damgası pencereleri) protokol katmanında uygulanıp uygulanmadığını doğrulayın.
 #9.4.5    Level: 3    Role: V
 Protokol uygulamalarının enjeksiyon veya serileştirme hataları için fuzz testi ve statik analizden geçtiğini doğrulayın.

---

### 9.5 Ajan Kimliği ve Müdahale Kanıtı

Eylemlerin izlenebilir ve değişikliklerin tespit edilebilir olmasını sağlayın.

 #9.5.1    Level: 1    Role: D/V
 Her ajan örneğinin benzersiz bir kriptografik kimliğe (anahtar çifti veya donanım tabanlı kimlik bilgisi) sahip olduğunu doğrulayın.
 #9.5.2    Level: 2    Role: D/V
 Tüm ajan işlemlerinin imzalandığını ve zaman damgalı olduğunu doğrulayın; günlükler, inkar edilemezlik için imzayı içermelidir.
 #9.5.3    Level: 2    Role: V
 Değişiklik izi gösteren günlüklerin yalnızca ekleme yapılabilen veya bir kere yazılabilen bir ortamda saklandığını doğrulayın.
 #9.5.4    Level: 3    Role: D
 Kimlik anahtarlarının belirlenmiş bir programda ve ihlal göstergelerinde döndüğünü doğrulayın.
 #9.5.5    Level: 3    Role: D/V
 Sahtecilik veya anahtar çatışması girişimlerinin etkilenen ajanı derhal karantinaya almasını doğrulayın.

---

### 9.6 Çok Ajanlı Sürü Risk Azaltma

Toplu davranış tehlikelerini izolasyon ve resmi güvenlik modellemesi ile hafifletin.

 #9.6.1    Level: 1    Role: D/V
 Farklı güvenlik alanlarında çalışan ajanların izole edilmiş çalışma zamanı kum havuzlarında veya ağ segmentlerinde çalıştığını doğrulayın.
 #9.6.2    Level: 3    Role: V
 Sürü davranışlarının, dağıtımdan önce canlılık ve güvenlik açısından modellenip resmi olarak doğrulandığını teyit edin.
 #9.6.3    Level: 3    Role: D
 Çalışma zamanı izleyicilerinin ortaya çıkan güvensiz desenleri (örneğin, salınımlar, kilitlenmeler) tespit ettiğini ve düzeltici eylemi başlattığını doğrulayın.

---

### 9.7 Kullanıcı ve Araç Doğrulaması / Yetkilendirmesi

Her ajan tetiklenen işlem için sağlam erişim kontrolleri uygulayın.

 #9.7.1    Level: 1    Role: D/V
 Ajanların, son kullanıcı kimlik bilgilerini asla yeniden kullanmadan, aşağı akış sistemlerine birinci sınıf yetkililer olarak kimlik doğruladığını doğrulayın.
 #9.7.2    Level: 2    Role: D
 Doğru ve ayrıntılı yetkilendirme politikalarının, bir ajanın hangi araçları çağırabileceğini ve hangi parametreleri sağlayabileceğini sınırladığını doğrulayın.
 #9.7.3    Level: 2    Role: V
 İzin kontrollerinin sadece oturum başlangıcında değil, her çağrıda yeniden değerlendirildiğini (sürekli yetkilendirme) doğrulayın.
 #9.7.4    Level: 3    Role: D
 Yetkilendirilen ayrıcalıkların otomatik olarak sona erdiğini ve zaman aşımı veya kapsam değişikliği sonrasında yeniden onay gerektirdiğini doğrulayın.

---

### 9.8 Ajanlar Arası İletişim Güvenliği

Tüm ajanlar arası mesajları dinlemeye ve müdahaleye karşı engellemek için şifreleyin ve bütünlük koruması sağlayın.

 #9.8.1    Level: 1    Role: D/V
 Ajan kanalları için karşılıklı kimlik doğrulamanın ve mükemmel ileri gizlilik şifrelemesinin (örn. TLS 1.3) zorunlu olduğunu doğrulayın.
 #9.8.2    Level: 1    Role: D
 İşlemden önce mesaj bütünlüğü ve kaynağının doğrulandığından emin olun; başarısızlık durumunda uyarılar verilir ve mesaj reddedilir.
 #9.8.3    Level: 2    Role: D/V
 İletişim meta verilerinin (zaman damgaları, sıra numaraları) adli inceleme yeniden oluşturmayı destekleyecek şekilde kaydedildiğini doğrulayın.
 #9.8.4    Level: 3    Role: V
 Protokol durum makinelerinin güvensiz durumlara sürüklenemeyeceğini resmi doğrulama veya model kontrolü ile doğrulayın.

---

### 9.9 Niyet Doğrulama ve Kısıtlama Uygulaması

Ajanın eylemlerinin kullanıcının belirtilen niyeti ve sistem kısıtlamalarıyla uyumlu olduğunu doğrulayın.

 #9.9.1    Level: 1    Role: D
 Ön yürütme kısıtlama çözücülerinin önerilen eylemleri sabit kodlanmış güvenlik ve politika kurallarına karşı kontrol ettiğini doğrulayın.
 #9.9.2    Level: 2    Role: D/V
 Yüksek etkili eylemlerin (finansal, yıkıcı, gizlilik hassasiyeti içeren) başlatan kullanıcıdan açık niyet onayı gerektirdiğini doğrulayın.
 #9.9.3    Level: 2    Role: V
 Tamamlanmış eylemlerin niyet edilen etkileri yan etkiler olmadan gerçekleştirdiğini doğrulamak için sonrası koşul kontrollerinin yapıldığını doğrulayın; tutarsızlıklar geri almayı tetikler.
 #9.9.4    Level: 3    Role: V
 Formal yöntemlerin (örneğin, model kontrolü, teorem ispatı) veya özellik tabanlı testlerin, ajan planlarının tüm belirtilen kısıtlamaları sağladığını doğruladığını teyit edin.
 #9.9.5    Level: 3    Role: D
 Niyet uyumsuzluğu veya kısıtlama ihlali olaylarının sürekli iyileştirme döngülerine ve tehdit istihbaratı paylaşımına bilgi sağladığını doğrulayın.

---

### 9.10 Ajan Akıl Yürütme Stratejisi Güvenliği

ReAct, Chain-of-Thought ve Tree-of-Thoughts yaklaşımları da dahil olmak üzere farklı akıl yürütme stratejilerinin güvenli seçimi ve yürütülmesi.

 #9.10.1    Level: 1    Role: D/V
 Sebep belirleme stratejisi seçiminin deterministik kriterler (girdi karmaşıklığı, görev türü, güvenlik bağlamı) kullandığını ve aynı girdilerin aynı güvenlik bağlamı içinde aynı strateji seçimini ürettiğini doğrulayın.
 #9.10.2    Level: 1    Role: D/V
 Her akıl yürütme stratejisinin (ReAct, Düşünce Zinciri, Düşünce Ağacı) kendi bilişsel yaklaşımına özgü giriş doğrulaması, çıktı temizleme ve yürütme süre sınırlarına sahip olduğunu doğrulayın.
 #9.10.3    Level: 2    Role: D/V
 Denetim izi yeniden inşası için, gerekçelendirme stratejisi geçişlerinin giriş özellikleri, seçim kriter değerleri ve yürütme meta verileri dahil olmak üzere eksiksiz bağlamla kaydedildiğini doğrulayın.
 #9.10.4    Level: 2    Role: D/V
 Tree-of-Thoughts muhakemesinin, politika ihlalleri, kaynak sınırları veya güvenlik sınırları tespit edildiğinde keşfi sonlandıran dal budama mekanizmalarını içerdiğini doğrulayın.
 #9.10.5    Level: 2    Role: D/V
 ReAct (Reason-Act-Observe) döngülerinin her aşamada doğrulama kontrol noktalarını içerdiğini doğrulayın: mantık adımı doğrulaması, eylem yetkilendirmesi ve devam etmeden önce gözlem temizliği.
 #9.10.6    Level: 3    Role: D/V
 Akıl yürütme stratejisi performans metriklerinin (çalışma süresi, kaynak kullanımı, çıktı kalitesi) yapılandırılmış eşiklerin ötesinde sapma gösterdiğinde otomatik uyarılarla izlenip izlenmediğini doğrulayın.
 #9.10.7    Level: 3    Role: D/V
 Birden fazla stratejiyi birleştiren hibrit akıl yürütme yaklaşımlarının, herhangi bir güvenlik kontrolünü atlamadan, tüm bileşen stratejilerin giriş doğrulamasını ve çıkış kısıtlamalarını koruduğunu doğrulayın.
 #9.10.8    Level: 3    Role: D/V
 Akıl yürütme stratejisi güvenlik testlerinin, bozuk girdilerle fuzz testini, strateji değişikliğini zorlamak için tasarlanmış düşmanca uyarıları ve her bilişsel yaklaşım için sınır durumu testlerini içerdiğini doğrulayın.

---

### 9.11 Ajan Yaşam Döngüsü Durumu Yönetimi ve Güvenliği

Kriptografik denetim izleri ve tanımlı kurtarma prosedürleri ile güvenli ajan başlatma, durum geçişleri ve sonlandırma.

 #9.11.1    Level: 1    Role: D/V
 Ajan başlatmanın, donanım destekli kimlik bilgileri ile kriptografik kimlik oluşturmayı ve ajan kimliği, zaman damgası, yapılandırma karması ve başlatma parametrelerini içeren değişmez başlangıç denetim kayıtlarını içerdiğini doğrulayın.
 #9.11.2    Level: 2    Role: D/V
 Agent durum geçişlerinin kriptografik olarak imzalandığını, zaman damgalandığını ve tetikleyici olaylar, önceki durum karması, yeni durum karması ve gerçekleştirilen güvenlik doğrulamaları dahil olmak üzere tam bağlamıyla kaydedildiğini doğrulayın.
 #9.11.3    Level: 2    Role: D/V
 Ajan kapatma prosedürlerinin kriptografik silme veya çoklu geçişli üzerine yazma yoluyla güvenli bellek temizlemeyi, sertifika otoritesi bildirimli kimlik bilgisi iptalini ve müdahale kanıtlı sonlandırma sertifikalarının oluşturulmasını içerdiğini doğrulayın.
 #9.11.4    Level: 3    Role: D/V
 Ajan kurtarma mekanizmalarının, durum bütünlüğünü kriptografik özetler (en az SHA-256) kullanarak doğruladığını ve bozulma tespit edildiğinde otomatik uyarılarla ve manuel onay gereksinimleriyle bilinen iyi durumlara geri döndüğünü doğrulayın.
 #9.11.5    Level: 3    Role: D/V
 Ajan kalıcılık mekanizmalarının, ajan başına AES-256 anahtarlarıyla hassas durum verilerini şifrelediğini ve yapılandırılabilir zaman çizelgelerinde (en fazla 90 gün) güvenli anahtar döndürme işlemi gerçekleştirdiğini, sıfır kesinti ile dağıtımı sağladığını doğrulayın.

---

### 9.12 Araç Entegrasyon Güvenlik Çerçevesi

Tanımlanmış risk değerlendirmesi ve onay süreçleri ile dinamik araç yükleme, yürütme ve sonuç doğrulama için güvenlik kontrolleri.

 #9.12.1    Level: 1    Role: D/V
 Araç tanımlayıcılarının, gerekli ayrıcalıkları (okuma/yazma/çalıştırma), risk seviyelerini (düşük/orta/yüksek), kaynak sınırlarını (CPU, hafıza, ağ) ve araç manifestolarında belgelenmiş doğrulama gereksinimlerini belirten güvenlik meta verilerini içerdiğini doğrulayın.
 #9.12.2    Level: 1    Role: D/V
 Araç yürütme sonuçlarının, zaman aşımı sınırları ve hata işleme prosedürleri ile entegrasyon öncesinde beklenen şemalara (JSON Şeması, XML Şeması) ve güvenlik politikalarına (çıktı temizleme, veri sınıflandırması) karşı doğrulandığından emin olun.
 #9.12.3    Level: 2    Role: D/V
 Araç etkileşim günlüklerinin, ayrıcalık kullanımı, veri erişim desenleri, yürütme süresi, kaynak tüketimi ve dönüş kodları dahil olmak üzere ayrıntılı güvenlik bağlamını içerdiğini ve SIEM entegrasyonu için yapılandırılmış günlük kaydını doğrulayın.
 #9.12.4    Level: 2    Role: D/V
 Dinamik araç yükleme mekanizmalarının, PKI altyapısını kullanarak dijital imzaları doğruladığını ve yürütmeden önce sandbox izolasyonu ve izin doğrulaması ile güvenli yükleme protokolleri uyguladığını doğrulayın.
 #9.12.5    Level: 3    Role: D/V
 Araç güvenlik değerlendirmelerinin, statik analiz, dinamik test ve güvenlik ekibi incelemesi gibi zorunlu onay kapılarıyla birlikte, belgelenmiş onay kriterleri ve SLA gereksinimlerini içeren otomatik olarak yeni sürümler için tetiklendiğini doğrulayın.

---

#### Referanslar

MITRE ATLAS tactics ML09
Circuit-breaker research for AI agents — Zou et al., 2024
Trend Micro analysis of sandbox escapes in AI agents — Park, 2025
Auth0 guidance on human-in-the-loop authorization for agents — Martinez, 2025
Medium deep-dive on MCP & A2A protocol hijacking — ForAISec, 2025
Rapid7 fundamentals on spoofing attack prevention — 2024
Imperial College verification of swarm systems — Lomuscio et al.
NIST AI Risk Management Framework 1.0, 2023
WIRED security briefing on encryption best practices, 2024
OWASP Top 10 for LLM Applications, 2025
Comprehensive Vulnerability Analysis is Necessary for Trustworthy LLM-MAS
[How Is LLM Reasoning Distracted by Irrelevant Context?
An Analysis Using a Controlled Benchmark](https://www.arxiv.org/pdf/2505.18761)
Large Language Model Sentinel: LLM Agent for Adversarial Purification
Securing Agentic AI: A Comprehensive Threat Model and Mitigation Framework for Generative AI Agents

## 10 Adversarial Dayanıklılık ve Gizlilik Savunması

### Kontrol Amacı

AI modellerinin kaçınma, çıkarım, çıkarma veya zehirleme saldırılarıyla karşılaştıklarında güvenilir, gizliliği koruyan ve kötüye kullanıma dayanıklı olmalarını sağlayın.

---

### 10.1 Model Hizalaması ve Güvenliği

Zararlı veya politika ihlali oluşturan çıktılara karşı koruma sağlayın.

 #10.1.1    Level: 1    Role: D/V
 Bir uyum test setinin (kırmızı takım istemleri, hapishaneden kaçma testleri, yasaklanmış içerik) sürüm kontrolünün yapıldığını ve her model sürümünde çalıştırıldığını doğrulayın.
 #10.1.2    Level: 1    Role: D
 Reddedilme ve güvenli tamamlama koruma önlemlerinin uygulandığını doğrulayın.
 #10.1.3    Level: 2    Role: D/V
 Otomatik bir değerlendiricinin zararlı içerik oranını ölçtüğünü ve belirlenen bir eşik değerinin üzerindeki gerilemeleri işaretlediğini doğrulayın.
 #10.1.4    Level: 2    Role: D
 Karşı hapishane kaçış eğitimlerinin belgelenmiş ve tekrarlanabilir olduğunu doğrulayın.
 #10.1.5    Level: 3    Role: V
 Resmi politika uyumluluğu kanıtlarının veya sertifikalı izleme işleminin kritik alanları kapsadığını doğrulayın.

---

### 10.2 Düşmanca Örnek Sertleştirme

Manipüle edilmiş girdilere karşı dayanıklılığı artırın. Sağlam düşmanca eğitim ve kıyaslama puanlaması şu anda en iyi uygulamalardır.

 #10.2.1    Level: 1    Role: D
 Proje depolarının tekrarlanabilir tohumlarla birlikte adversaryal eğitim yapılandırmalarını içerdiğini doğrulayın.
 #10.2.2    Level: 2    Role: D/V
 Üretim hatlarında düşmanca örnek tespitin engelleme uyarıları oluşturduğunu doğrulayın.
 #10.2.4    Level: 3    Role: V
 Sertifikalı dayanıklılık kanıtlarının veya aralık-sınır sertifikalarının en azından en kritik üst sınıfları kapsadığını doğrulayın.
 #10.2.5    Level: 3    Role: V
 Regresyon testlerinin, ölçülebilir bir dayanıklılık kaybı olmadığını doğrulamak için uyarlanabilir saldırılar kullandığını doğrulayın.

---

### 10.3 Üyelik Çıkarımı Önleme

Bir kaydın eğitim verilerinde olup olmadığını belirleme yeteneğini sınırlayın. Farklı gizlilik ve güven skorunu gizleme, bilinen en etkili savunmalar olmaya devam etmektedir.

 #10.3.1    Level: 1    Role: D
 Sorgu başına entropi düzenlemesinin veya sıcaklık ölçeklemesinin aşırı güvenli tahminleri azalttığını doğrulayın.
 #10.3.2    Level: 2    Role: D
 Eğitimde, hassas veri setleri için ε-sınırlı farklı gizlilikli optimizasyonun kullanıldığını doğrulayın.
 #10.3.3    Level: 2    Role: V
 Saldırı simülasyonlarının (gölge model veya kara kutu) ayrılmış veriler üzerinde saldırı AUC'sinin ≤ 0,60 olduğunu doğrulayın.

---

### 10.4 Model-Tersine Çevirme Direnci

Özel özniteliklerin yeniden yapılandırılmasını önleyin. Son anketler, çıktı kısaltma ve DP garantilerini pratik savunmalar olarak vurgulamaktadır.

 #10.4.1    Level: 1    Role: D
 Hassas özelliklerin asla doğrudan çıktılanmadığını doğrulayın; gerektiğinde kovalar veya tek yönlü dönüşümler kullanın.
 #10.4.2    Level: 1    Role: D/V
 Aynı kullanıcıdan gelen tekrarlanan uyarlanabilir sorguların sorgu oranı limitleriyle sınırlandırıldığını doğrulayın.
 #10.4.3    Level: 2    Role: D
 Modelin gizliliği koruyan gürültü ile eğitildiğini doğrulayın.

---

### 10.5 Model Çıkarımı Savunması

Yetkisiz klonlamayı tespit edin ve caydırın. Su işareti ekleme ve sorgu deseni analizi önerilir.

 #10.5.1    Level: 1    Role: D
 Çıkarım geçitlerinin, modelin ezberleme eşiğine göre ayarlanmış global ve API anahtarı başına oran limitlerini zorladığını doğrulayın.
 #10.5.2    Level: 2    Role: D/V
 Sorgu-entropisi ve girdi-çoğulluk istatistiklerinin otomatik çıkarım algılayıcısına veri sağladığını doğrulayın.
 #10.5.3    Level: 2    Role: V
 Kırılgan veya olasılıksal su işaretlerinin, şüpheli klon üzerinde ≤ 1.000 sorgu ile p < 0,01 düzeyinde kanıtlanabileceğini doğrulayın.
 #10.5.4    Level: 3    Role: D
 Filigran anahtarlarının ve tetikleyici setlerin bir donanım güvenlik modülünde saklandığını ve her yıl döndürüldüğünü doğrulayın.
 #10.5.5    Level: 3    Role: V
 Extraction-alert olaylarının hatalı sorguları içerdiğini ve olay müdahale oyun kitaplarıyla entegre edildiğini doğrulayın.

---

### 10.6 Çıkarım Zamanı Zehirli Veri Tespiti

Geri kapılı veya zehirlenmiş girdileri tanımlayın ve etkisiz hale getirin.

 #10.6.1    Level: 1    Role: D
 Model çıkarımı öncesinde, girdilerin bir anomali algılayıcısından (örneğin, STRIP, tutarlılık skorlama) geçtiğini doğrulayın.
 #10.6.2    Level: 1    Role: V
 Dedektör eşiklerinin, yanlış pozitif oranını %5’in altında tutmak için temiz/zehirlenmiş doğrulama setlerinde ayarlandığını doğrulayın.
 #10.6.3    Level: 2    Role: D
 Zehirli olarak işaretlenen girdilerin yumuşak engelleme ve insan inceleme iş akışlarını tetiklediğini doğrulayın.
 #10.6.4    Level: 2    Role: V
 Dedektörlerin, uyarlanabilir ve tetikleyicisiz arka kapı saldırılarıyla stres testine tabi tutulduğunu doğrulayın.
 #10.6.5    Level: 3    Role: D
 Tespit etkinliği metriklerinin kaydedildiğini ve periyodik olarak güncel tehdit istihbaratı ile yeniden değerlendirildiğini doğrulayın.

---

### 10.7 Dinamik Güvenlik Politikası Uyarlaması

Tehdit istihbaratı ve davranış analizi temelinde gerçek zamanlı güvenlik politikası güncellemeleri.

 #10.7.1    Level: 1    Role: D/V
 Güvenlik politikalarının, politika sürüm bütünlüğünü koruyarak, ajan yeniden başlatılmadan dinamik olarak güncellenebileceğini doğrulayın.
 #10.7.2    Level: 2    Role: D/V
 Politika güncellemelerinin yetkili güvenlik personeli tarafından kriptografik olarak imzalandığını ve uygulanmadan önce doğrulandığını kontrol edin.
 #10.7.3    Level: 2    Role: D/V
 Dinamik politika değişikliklerinin gerekçelendirme, onay zincirleri ve geri alma prosedürleri dahil olmak üzere tam denetim izleriyle kaydedildiğini doğrulayın.
 #10.7.4    Level: 3    Role: D/V
 Uyarlanabilir güvenlik mekanizmalarının, risk bağlamı ve davranışsal desenlere göre tehdit algılama hassasiyetini ayarladığını doğrulayın.
 #10.7.5    Level: 3    Role: D/V
 Politika uyarlama kararlarının açıklanabilir olduğunu ve güvenlik ekibi incelemesi için kanıt izleri içerdiğini doğrulayın.

---

### 10.8 Yansıtma Tabanlı Güvenlik Analizi

Ajanın öz-refleksiyonu ve meta-bilişsel analiz yoluyla güvenlik doğrulaması.

 #10.8.1    Level: 1    Role: D/V
 Ajan yansıtma mekanizmalarının, kararların ve eylemlerin güvenlik odaklı öz değerlendirmesini içerdiğini doğrulayın.
 #10.8.2    Level: 2    Role: D/V
 Yansıma çıktılarının doğrulanarak, kötü niyetli girdilerle öz-değerlendirme mekanizmalarının manipüle edilmesinin önlendiğini doğrulayın.
 #10.8.3    Level: 2    Role: D/V
 Meta-bilişsel güvenlik analizinin, ajan akıl yürütme süreçlerindeki potansiyel önyargıyı, manipülasyonu veya güvenlik ihlalini tespit ettiğini doğrulayın.
 #10.8.4    Level: 3    Role: D/V
 Yansıma tabanlı güvenlik uyarılarının gelişmiş izlemeyi ve olası insan müdahalesi iş akışlarını tetiklediğini doğrulayın.
 #10.8.5    Level: 3    Role: D/V
 Güvenlik yansımalarından sürekli öğrenmenin, meşru işlevselliği bozmadan tehdit algılamayı iyileştirdiğini doğrulayın.

---

### 10.9 Evrim ve Öz Gelişim Güvenliği

Kendi kendini değiştirip evrimleşebilen ajan sistemleri için güvenlik kontrolleri.

 #10.9.1    Level: 1    Role: D/V
 Kendi kendini değiştirme yeteneklerinin, resmi doğrulama sınırları ile belirlenmiş güvenli alanlarla sınırlandırıldığını doğrulayın.
 #10.9.2    Level: 2    Role: D/V
 Evrim önerilerinin uygulanmadan önce güvenlik etki değerlendirmesinden geçtiğini doğrulayın.
 #10.9.3    Level: 2    Role: D/V
 Kendini geliştirme mekanizmalarının bütünlük doğrulaması ile geri alma yeteneklerini içerdiğini doğrulayın.
 #10.9.4    Level: 3    Role: D/V
 Meta-öğrenme güvenliğinin, iyileştirme algoritmalarının düşmanca manipülasyonunu önlediğini doğrulayın.
 #10.9.5    Level: 3    Role: D/V
 Özyinelemeli kendini geliştirme sürecinin matematiksel yakınsama kanıtlarıyla birlikte resmi güvenlik kısıtlarıyla sınırlandırıldığını doğrulayın.

---

#### Kaynaklar

MITRE ATLAS adversary tactics for ML
NIST AI Risk Management Framework 1.0, 2023
OWASP Top 10 for LLM Applications, 2025
Adversarial Training: A Survey — Zhao et al., 2024
RobustBench adversarial-robustness benchmark
Membership-Inference & Model-Inversion Risk Survey, 2025
PURIFIER: Confidence-Score Defense against MI Attacks — AAAI 2023
Model-Inversion Attacks & Defenses Survey — AI Review, 2025
Comprehensive Defense Framework Against Model Extraction — IEEE TDSC 2024
Fragile Model Watermarking Survey — 2025
Data Poisoning in Deep Learning: A Survey — Zhao et al., 2025
BDetCLIP: Multimodal Prompting Backdoor Detection — Niu et al., 2024

## 11 Gizlilik Koruması ve Kişisel Veri Yönetimi

### Kontrol Hedefi

Kişisel verilerin yalnızca açık rıza, asgari gerekli kapsam, kanıtlanabilir silme ve resmi gizlilik garantileriyle işlendiği koleksiyon, eğitim, çıkarım ve olay müdahalesi dahil olmak üzere tüm Yapay Zeka yaşam döngüsü boyunca katı gizlilik güvencelerini sürdürün.

---

### 11.1 Anonimleştirme ve Veri Azaltma

 #11.1.1    Level: 1    Role: D/V
 Doğrudan ve yarı tanımlayıcıların kaldırıldığını, karma hale getirildiğini doğrulayın.
 #11.1.2    Level: 2    Role: D/V
 Otomatik denetimlerin k-anonimlik/l-çeşitlilik ölçtüğünü ve eşik değerler politika altına düştüğünde uyarı verdiğini doğrulayın.
 #11.1.3    Level: 2    Role: V
 Model özellik-önem raporlarının, ε = 0.01 karşılıklı bilgi değerinin ötesinde hiçbir tanımlayıcı sızıntısı olmadığını doğrulayın.
 #11.1.4    Level: 3    Role: V
 Formel kanıtların veya sentetik veri sertifikasyonunun, bağlantı saldırıları altında bile yeniden tanımlama riskinin ≤ 0.05 olduğunu gösterdiğini doğrulayın.

---

### 11.2 Unutulma Hakkı ve Silme Uygulaması

 #11.2.1    Level: 1    Role: D/V
 Veri konusu silme taleplerinin, hizmet seviyesi anlaşmaları çerçevesinde 30 günden daha kısa sürede ham verisetlerine, kontrol noktalarına, gömülü verilere, günlük kayıtlara ve yedeklere ulaştığını doğrulayın.
 #11.2.2    Level: 2    Role: D
 "Sertifikalı unutma algoritmaları kullanarak 'makine unutma' işlemlerinin fiziksel olarak yeniden eğitme veya yaklaşık kaldırma gerçekleştirdiğini doğrulayın."
 #11.2.3    Level: 2    Role: V
 Unlearning'den sonra unutulmuş kayıtların çıktıların %1'inden daha azını etkilediğini doğrulamak için shadow-model değerlendirmesini kullanın.
 #11.2.4    Level: 3    Role: V
 Silme olaylarının değişmez şekilde kaydedildiğini ve düzenleyiciler için denetlenebilir olduğunu doğrulayın.

---

### 11.3 Diferansiyel Gizlilik Güvenceleri

 #11.3.1    Level: 2    Role: D/V
 Toplam ε politika eşiklerini aştığında gizlilik kaybı hesaplama panellerinin uyarı verdiğini doğrulayın.
 #11.3.2    Level: 2    Role: V
 Kara kutu gizlilik denetimlerinin ε̂ değerini beyan edilen değerin %10'u içinde tahmin ettiğini doğrulayın.
 #11.3.3    Level: 3    Role: V
 Resmi kanıtların eğitim sonrası tüm ince ayarları ve gömülüleri kapsadığını doğrulayın.

---

### 11.4 Amaç Sınırlaması ve Kapsam Kayması Koruması

 #11.4.1    Level: 1    Role: D
 Her veri seti ve model kontrol noktası için, orijinal izinle uyumlu, makine tarafından okunabilir bir amaç etiketi bulunduğunu doğrulayın.
 #11.4.2    Level: 1    Role: D/V
 Çalışma zamanı izleyicilerinin, beyan edilen amaca aykırı sorguları tespit ettiğini ve yumuşak reddi tetiklediğini doğrulayın.
 #11.4.3    Level: 3    Role: D
 Politika-kod olarak tanımlanan sınırların, DPIA incelemesi olmadan modellerin yeni alanlara yeniden dağıtımını engellediğini doğrulayın.
 #11.4.4    Level: 3    Role: V
 Resmi izlenebilirlik kanıtlarının, her kişisel veri yaşam döngüsünün onaylanmış kapsam içinde kaldığını gösterdiğini doğrulayın.

---

### 11.5 Onay Yönetimi ve Hukuki Dayanak İzleme

 #11.5.1    Level: 1    Role: D/V
 Bir Rıza Yönetim Platformunun (CMP) her veri sahibi için onay durumu, amaç ve saklama süresini kaydettiğini doğrulayın.
 #11.5.2    Level: 2    Role: D
 API'lerin onay belirteçlerini açığa çıkardığını doğrulayın; modeller çıkarım yapmadan önce belirteç kapsamını doğrulamalıdır.
 #11.5.3    Level: 2    Role: D/V
 Reddedilen veya geri çekilen onayın işlem hatlarını 24 saat içinde durdurduğunu doğrulayın.

---

### 11.6 Gizlilik Kontrolleri ile Federated Learning

 #11.6.1    Level: 1    Role: D
 İstemci güncellemelerinin toplama öncesinde yerel farklılaştırılmış gizlilik gürültüsü eklemesini doğrulayın.
 #11.6.2    Level: 2    Role: D/V
 Eğitim metriklerinin diferansiyel gizlilik içerdiğini ve asla tek bir müşteriye ait kaybı açığa çıkarmadığını doğrulayın.
 #11.6.3    Level: 2    Role: V
 Zehirlenmeye dayanıklı toplamanın (örn. Krum/Kırpılmış-Ortalama) etkinleştirildiğini doğrulayın.
 #11.6.4    Level: 3    Role: V
 Resmî kanıtların, 5'ten az fayda kaybı ile toplam ε bütçesini gösterdiğini doğrulayın.

---

#### Referanslar

GDPR & AI Compliance Best Practices
EU Parliament Study on GDPR & AI, 2020
ISO 31700-1:2023 — Privacy by Design for Consumer Products
NIST Privacy Framework 1.1 (2025 Draft)
Machine Unlearning: Right-to-Be-Forgotten Techniques
A Survey of Machine Unlearning, 2024
Auditing DP-SGD — ArXiv 2024
DP-SGD Explained — PyTorch Blog
Purpose-Limitation for AI — IJLIT 2025
Data-Protection Considerations for AI — URM Consulting
Top Consent-Management Platforms, 2025
Secure Aggregation in DP Federated Learning — ArXiv 2024

## C12 İzleme, Kayıt Tutma ve Anomali Tespiti

### Kontrol Hedefi

Bu bölüm, tehditlerin tespit edilmesi, sınıflandırılması ve öğrenilmesi için modelin ve diğer AI bileşenlerinin ne gördüğü, ne yaptığı ve ne döndürdüğü hakkında gerçek zamanlı ve adli görünürlük sağlanmasına yönelik gereksinimleri sunar.

### C12.1 İstek ve Yanıt Kaydı

 #12.1.1    Level: 1    Role: D/V
 Tüm kullanıcı istemlerinin ve model yanıtlarının uygun meta verilerle (örneğin, zaman damgası, kullanıcı kimliği, oturum kimliği, model sürümü) kaydedildiğini doğrulayın.
 #12.1.2    Level: 1    Role: D/V
 Günlüklerin uygun saklama politikaları ve yedekleme prosedürleri ile güvenli, erişim kontrollü depolama alanlarında saklandığını doğrulayın.
 #12.1.3    Level: 1    Role: D/V
 Günlüklerde bulunan hassas bilgileri korumak için günlük depolama sistemlerinin hem bekleme halinde hem de iletim sırasında şifreleme uyguladığını doğrulayın.
 #12.1.4    Level: 1    Role: D/V
 İsteklerde ve çıktılarda yer alan hassas verilerin, kayıttan önce otomatik olarak sansürlendiği veya maskelendiğini doğrulayın; bu işlem, Kişisel Tanımlanabilir Bilgiler (PII), kimlik bilgileri ve özel bilgilere yönelik yapılandırılabilir sansürleme kurallarıyla gerçekleştirilmelidir.
 #12.1.5    Level: 2    Role: D/V
 Politika kararlarının ve güvenlik filtreleme işlemlerinin, içerik denetim sistemlerinin denetimi ve hata ayıklaması için yeterli ayrıntıyla kaydedildiğini doğrulayın.
 #12.1.6    Level: 2    Role: D/V
 Günlük bütünlüğünün, örneğin kriptografik imzalar veya sadece yazılabilen depolama ile korunduğunu doğrulayın.

---

### C12.2 Suistimal Tespiti ve Uyarı Sistemi

 #12.2.1    Level: 1    Role: D/V
 Sistemin, imza tabanlı tespit kullanarak bilinen jailbreak kalıplarını, istem enjekte etme girişimlerini ve düşmanca girdileri algılayıp uyarı verdiğini doğrulayın.
 #12.2.2    Level: 1    Role: D/V
 Sistemin, standart günlük formatları ve protokolleri kullanarak mevcut Güvenlik Bilgisi ve Olay Yönetimi (SIEM) platformlarıyla entegre olduğunu doğrulayın.
 #12.2.3    Level: 2    Role: D/V
 Zenginleştirilmiş güvenlik olaylarının model tanımlayıcıları, güven skoru ve güvenlik filtresi kararları gibi yapay zekaya özgü bağlamları içerdiğini doğrulayın.
 #12.2.4    Level: 2    Role: D/V
 Davranışsal anomali tespitinin alışılmadık konuşma kalıplarını, aşırı tekrar denemelerini veya sistematik sorgulama davranışlarını tespit ettiğini doğrulayın.
 #12.2.5    Level: 2    Role: D/V
 Gerçek zamanlı uyarı mekanizmalarının, potansiyel politika ihlalleri veya saldırı girişimleri tespit edildiğinde güvenlik ekiplerini bilgilendirdiğini doğrulayın.
 #12.2.6    Level: 2    Role: D/V
 Yapay zeka özel tehdit desenlerini tespit etmek için koordineli jailbreak girişimleri, istem enjekte etme kampanyaları ve model çıkarma saldırıları dahil olmak üzere özel kuralların dahil edildiğini doğrulayın.
 #12.2.7    Level: 3    Role: D/V
 Otomatik olay müdahale iş akışlarının, ele geçirilmiş modelleri izole edebildiğini, kötü niyetli kullanıcıları engellediğini ve kritik güvenlik olaylarını yükseltebildiğini doğrulayın.

---

### C12.3 Model Sürüklenme Tespiti

 #12.3.1    Level: 1    Role: D/V
 Sistemin, model sürümleri ve zaman dilimleri boyunca doğruluk, güven skorları, gecikme süresi ve hata oranları gibi temel performans metriklerini takip ettiğini doğrulayın.
 #12.3.2    Level: 2    Role: D/V
 Performans metrikleri önceden belirlenmiş bozulma eşiklerini aştığında veya baz çizgilerden önemli ölçüde sapma gösterdiğinde otomatik uyarı tetikleyicilerinin devreye girdiğini doğrulayın.
 #12.3.3    Level: 2    Role: D/V
 Halüsinasyon tespiti izleyicilerinin, model çıktılarında gerçeklere aykırı, tutarsız veya uydurma bilgiler bulunduğunda bu durumları tespit edip işaretlediğini doğrulayın.

---

### C12.4 Performans ve Davranış Telemetrisi

 #12.4.1    Level: 1    Role: D/V
 İşlem gecikmesi, token tüketimi, bellek kullanımı ve verimlilik gibi operasyonel metriklerin sürekli olarak toplandığını ve izlendiğini doğrulayın.
 #12.4.2    Level: 1    Role: D/V
 Başarı ve başarısızlık oranlarının, hata türlerinin ve bunların temel nedenlerinin kategorize edilerek takip edildiğini doğrulayın.
 #12.4.3    Level: 2    Role: D/V
 Kaynak kullanım izleme işlevinin GPU/CPU kullanımı, bellek tüketimi ve depolama gereksinimlerini içerdiğini ve eşik ihlallerinde uyarı verilmesini doğrulayın.

---

### C12.5 Yapay Zeka Olay Müdahale Planlaması ve Yürütülmesi

 #12.5.1    Level: 1    Role: D/V
 Olay müdahale planlarının, model ihlali, veri zehirlenmesi ve düşmanca saldırılar dahil olmak üzere yapay zekâ ile ilgili güvenlik olaylarını özellikle ele aldığını doğrulayın.
 #12.5.2    Level: 2    Role: D/V
 Olay müdahale ekiplerinin, model davranışı ve saldırı vektörlerini araştırmak için yapay zekâya özgü adli araçlara ve uzmanlığa erişimi olduğundan emin olun.
 #12.5.3    Level: 3    Role: D/V
 Olay sonrası analizde model yeniden eğitimi hususlarının, güvenlik filtresi güncellemelerinin ve edinilen derslerin güvenlik kontrollerine entegrasyonunun dahil edildiğini doğrulayın.

---

### C12.5 AI Performans Düşüşü Tespiti

Yapay zeka modeli performansındaki ve kalitesindeki zamanla meydana gelen bozulmaları izleyin ve tespit edin.

 #12.5.1    Level: 1    Role: D/V
 Model doğruluğunun, kesinliğinin, geri çağırma oranının ve F1 skorlarının sürekli olarak izlenip temel eşik değerlerle karşılaştırıldığından emin olun.
 #12.5.2    Level: 1    Role: D/V
 Veri sürüklenmesi tespiti, model performansını etkileyebilecek giriş dağılımı değişikliklerini izlediğini doğrulayın.
 #12.5.3    Level: 2    Role: D/V
 Konsept kayması tespitinin, girdiler ile beklenen çıktılar arasındaki ilişkideki değişiklikleri belirlediğini doğrulayın.
 #12.5.4    Level: 2    Role: D/V
 Performans bozulmasının otomatik uyarıları tetiklediğini ve model yeniden eğitimi veya değiştirme iş akışlarını başlattığını doğrulayın.
 #12.5.5    Level: 3    Role: V
 Performans düşüşlerini veri değişiklikleri, altyapı sorunları veya dış etkenlerle ilişkilendiren bozulma kök neden analizinin doğrulanması.

---

### C12.6 DAG Görselleştirmesi ve İş Akışı Güvenliği

İş akışı görselleştirme sistemlerini bilgi sızıntısı ve manipülasyon saldırılarından koruyun.

 #12.6.1    Level: 1    Role: D/V
 DAG görselleştirme verilerinin depolama veya iletim öncesinde hassas bilgileri kaldıracak şekilde temizlendiğini doğrulayın.
 #12.6.2    Level: 1    Role: D/V
 İş akışı görselleştirme erişim kontrollerinin sadece yetkili kullanıcıların ajan karar yollarını ve mantık izlerini görüntüleyebildiğini doğrulayın.
 #12.6.3    Level: 2    Role: D/V
 DAG veri bütünlüğünün kriptografik imzalar ve müdahale tespitli depolama mekanizmaları aracılığıyla korunduğunu doğrulayın.
 #12.6.4    Level: 2    Role: D/V
 İş akışı görselleştirme sistemlerinin, özel olarak hazırlanmış düğüm veya kenar verileri aracılığıyla gerçekleştirilen enjeksiyon saldırılarını önlemek için giriş doğrulaması uyguladığını doğrulayın.
 #12.6.5    Level: 3    Role: D/V
 Gerçek zamanlı DAG güncellemelerinin hizmet reddi saldırılarını önlemek amacıyla hız sınırlandırmasının yapıldığını ve doğrulandığını kontrol edin.

---

### C12.7 Proaktif Güvenlik Davranışı İzleme

Güvenlik tehditlerinin proaktif ajan davranışı analizi yoluyla tespiti ve önlenmesi.

 #12.7.1    Level: 1    Role: D/V
 Proaktif ajan davranışlarının yürütülmeden önce risk değerlendirmesi entegrasyonu ile güvenlik doğrulamasının yapıldığını doğrulayın.
 #12.7.2    Level: 2    Role: D/V
 Otonom girişim tetikleyicilerinin güvenlik bağlamı değerlendirmesi ve tehdit ortamı analizini içerdiğini doğrulayın.
 #12.7.3    Level: 2    Role: D/V
 Proaktif davranış kalıplarının olası güvenlik etkileri ve istenmeyen sonuçlar açısından analiz edildiğini doğrulayın.
 #12.7.4    Level: 3    Role: D/V
 Güvenlik açısından kritik proaktif eylemlerin, denetim izleriyle birlikte açık onay zincirleri gerektirdiğini doğrulayın.
 #12.7.5    Level: 3    Role: D/V
 Davranış anomali tespiti, proaktif ajan desenlerindeki sapmaları tespit ederek olası güvenlik ihlallerini belirlediğini doğrulayın.

---

### Referanslar

NIST AI Risk Management Framework 1.0 - Manage 4.1 and 4.3
ISO/IEC 42001:2023 — AI Management Systems Requirements - Annex B 6.2.6
EU AI Act — Article 12, 13, 16 and 19 on Logging and Record-keeping

## C13 İnsan Gözetimi, Hesap Verebilirlik ve Yönetişim

### Kontrol Hedefi

Bu bölüm, Yapay Zeka (YZ) sistemlerinde insan denetimi ve net hesap verebilirlik zincirlerinin sürdürülmesi için gereklilikler sağlar; YZ yaşam döngüsü boyunca açıklanabilirlik, şeffaflık ve etik yönetimi güvence altına alır.

---

### C13.1 Kill-Switch ve Geçersiz Kılma Mekanizmaları

AI sisteminin güvensiz davranışı gözlemlendiğinde kapanış veya geri alma yolları sağlayın.

 #13.1.1    Level: 1    Role: D/V
 AI model çıkarımını ve çıktıları derhal durdurmak için manuel bir acil durdurma mekanizmasının varlığını doğrulayın.
 #13.1.2    Level: 1    Role: D
 Geçersiz kılma kontrollerinin yalnızca yetkili personelin erişimine açık olduğunu doğrulayın.
 #13.1.3    Level: 3    Role: D/V
 Geri alma prosedürlerinin önceki model sürümlerine veya güvenli mod işlemlerine dönebileceğini doğrulayın.
 #13.1.4    Level: 3    Role: V
 Geçersiz kılma mekanizmalarının düzenli olarak test edildiğini doğrulayın.

---

### C13.2 İnsan-Dahil Döngü Karar Kontrol Noktaları

Risk eşiklerini aştığında insan onayı gerektirir.

 #13.2.1    Level: 1    Role: D/V
 Yüksek riskli Yapay Zeka kararlarının yürütülmeden önce açık insan onayı gerektirdiğini doğrulayın.
 #13.2.2    Level: 1    Role: D
 Risk eşiklerinin açıkça tanımlandığını ve insan inceleme iş akışlarını otomatik olarak tetiklediğini doğrulayın.
 #13.2.3    Level: 2    Role: D
 İnsan onayı gereken süre içinde alınamadığında, zaman duyarlı kararların yedek prosedürlere sahip olduğunu doğrulayın.
 #13.2.4    Level: 3    Role: D/V
 Yükseltme prosedürlerinin, uygulanabilir ise, farklı karar türleri veya risk kategorileri için net yetki seviyelerini tanımladığından emin olun.

---

### C13.3 Sorumluluk Zinciri ve Denetlenebilirlik

Operatör eylemlerini ve model kararlarını kaydedin.

 #13.3.1    Level: 1    Role: D/V
 Tüm yapay zeka sistemi kararlarının ve insan müdahalelerinin, zaman damgaları, kullanıcı kimlikleri ve karar gerekçeleri ile kaydedildiğini doğrulayın.
 #13.3.2    Level: 2    Role: D
 Denetim kayıtlarının değiştirilip değiştirilemeyeceğini doğrulayın ve bütünlük doğrulama mekanizmalarını dahil edin.

---

### C13.4 Açıklanabilir-YZ Teknikleri

Yüzey özellik önemi, karşı-olasılıklar ve yerel açıklamalar.

 #13.4.1    Level: 1    Role: D/V
 Yapay zeka sistemlerinin kararları için insan tarafından okunabilir biçimde temel açıklamalar sağladığını doğrulayın.
 #13.4.2    Level: 2    Role: V
 Açıklama kalitesinin insan değerlendirme çalışmaları ve metrikler aracılığıyla doğrulandığını teyit edin.
 #13.4.3    Level: 3    Role: D/V
 Kritik kararlar için özellik önem puanları veya atıf yöntemlerinin (SHAP, LIME, vb.) mevcut olduğunu doğrulayın.
 #13.4.4    Level: 3    Role: V
 Karşıt açıklamaların, kullanım durumu ve alana uygulanabilir ise, sonuçları değiştirmek için girdilerin nasıl değiştirilebileceğini gösterdiğini doğrulayın.

---

### C13.5 Model Kartları ve Kullanım Açıklamaları

Model kartlarını amaçlanan kullanım, performans ölçütleri ve etik hususlar için güncel tutun.

 #13.5.1    Level: 1    Role: D
 Model kartlarının amaçlanan kullanım durumlarını, sınırlamalarını ve bilinen hata durumlarını belgelediğini doğrulayın.
 #13.5.2    Level: 1    Role: D/V
 Farklı uygun kullanım durumları için performans metriklerinin açıklanıp açıklanmadığını doğrulayın.
 #13.5.3    Level: 2    Role: D
 Etik değerlendirmelerin, önyargı analizlerinin, adillik değerlendirmelerinin, eğitim verisi özelliklerinin ve bilinen eğitim verisi sınırlamalarının belgelenip düzenli olarak güncellendiğini doğrulayın.
 #13.5.4    Level: 2    Role: D/V
 Model kartlarının versiyon kontrolünün yapıldığını ve değişiklik takibi ile model yaşam döngüsü boyunca korunduğunu doğrulayın.

---

### C13.6 Belirsizlik Nicelleştirmesi

Yanıtlarda güven skorlarını veya entropi ölçümlerini yay.

 #13.6.1    Level: 1    Role: D
 AI sistemlerinin çıktılarıyla birlikte güven skoru veya belirsizlik ölçüleri sağladığını doğrulayın.
 #13.6.2    Level: 2    Role: D/V
 Belirsizlik eşiklerinin ek insan incelemesini veya alternatif karar yollarını tetiklediğini doğrulayın.
 #13.6.3    Level: 2    Role: V
 Belirsizlik nicelleme yöntemlerinin, gerçek temel verilere karşı kalibre edilip doğrulandığını teyit edin.
 #13.6.4    Level: 3    Role: D/V
 Belirsizlik yayılımının çok adımlı Yapay Zeka iş akışları boyunca korunduğunu doğrulayın.

---

### C13.7 Kullanıcıya Yönelik Şeffaflık Raporları

Olaylar, sapma ve veri kullanımı hakkında düzenli açıklamalar sağlayın.

 #13.7.1    Level: 1    Role: D/V
 Veri kullanım politikalarının ve kullanıcı onayı yönetimi uygulamalarının paydaşlara açıkça iletildiğini doğrulayın.
 #13.7.2    Level: 2    Role: D/V
 Yapay zeka etki değerlendirmelerinin yapıldığını doğrulayın ve sonuçların raporlamaya dahil edildiğinden emin olun.
 #13.7.3    Level: 2    Role: D/V
 Şeffaflık raporlarının düzenli olarak yayımlanıp yayımlanmadığını ve AI olayları ile operasyonel metriklerin makul ayrıntıda açıklanıp açıklanmadığını doğrulayın.

#### Referanslar

EU Artificial Intelligence Act — Regulation (EU) 2024/1689 (Official Journal, 12 July 2024)
ISO/IEC 23894:2023 — Artificial Intelligence — Guidance on Risk Management
ISO/IEC 42001:2023 — AI Management Systems Requirements
NIST AI Risk Management Framework 1.0
NIST SP 800-53 Revision 5 — Security and Privacy Controls
A Unified Approach to Interpreting Model Predictions (SHAP, ICML 2017)
Model Cards for Model Reporting (Mitchell et al., 2018)
Dropout as a Bayesian Approximation: Representing Model Uncertainty in Deep Learning (Gal & Ghahramani, 2016)
ISO/IEC 24029-2:2023 — Robustness of Neural Networks — Methodology for Formal Methods
IEEE 7001-2021 — Transparency of Autonomous Systems
GDPR — Article 5 "Transparency Principle" (Regulation (EU) 2016/679)
Human Oversight under Article 14 of the EU AI Act (Fink, 2025)

## Ek A: Terimler Sözlüğü

Bu kapsamlı sözlük, AISVS genelinde kullanılan önemli AI, ML ve güvenlik terimlerinin netlik ve ortak anlayışı sağlamak amacıyla tanımlarını sunar.
​
Düşmanca Örnek: Genellikle insanlara fark edilmeyen ince bozulmalar eklenerek, bir yapay zeka modelinin hata yapmasına neden olmak amacıyla kasıtlı olarak oluşturulmuş bir giriş.
​
Adversarial Dayanıklılık – AI'da adversarial dayanıklılık, bir modelin performansını koruyabilme ve hatalara yol açmak amacıyla kasıtlı olarak hazırlanmış kötü niyetli girdiler tarafından aldatılmaya veya manipüle edilmeye karşı dirençli olma yeteneğini ifade eder.
​
Ajan – AI ajanları, kullanıcılar adına hedeflere ulaşmak ve görevleri tamamlamak için AI kullanan yazılım sistemleridir. Akıl yürütme, planlama ve hafıza gösterirler ve karar verme, öğrenme ve uyum sağlama konusunda belli bir özerkliğe sahiptirler.
​
Agentik AI: Belirli bir dereceye kadar özerklikle hedeflere ulaşabilen, genellikle doğrudan insan müdahalesi olmadan kararlar alan ve eylemler gerçekleştiren AI sistemleri.
​
Öznitelik Tabanlı Erişim Kontrolü (ABAC): Yetkilendirme kararlarının kullanıcı, kaynak, eylem ve ortamın özniteliklerine dayanarak, sorgu zamanında değerlendirildiği bir erişim kontrol paradigmasıdır.
​
Arka Kapı Saldırısı: Modelin belirli tetikleyicilere karşı özel bir şekilde yanıt vermesi için eğitildiği, diğer durumlarda ise normal şekilde davrandığı bir veri zehirleme saldırısı türü.
​
Önyargı: Belirli gruplar veya belirli bağlamlarda adaletsiz veya ayrımcı sonuçlara yol açabilecek AI modeli çıktılarındaki sistematik hatalar.
​
Önyargı Sömürüsü: Yapay zeka modellerindeki bilinen önyargılardan faydalanarak çıktıları veya sonuçları manipüle etmeye yönelik bir saldırı tekniği.
​
Cedar: AI sistemleri için ABAC uygulanmasında kullanılan, ince taneli izinler için Amazon'un politika dili ve motoru.
​
Düşünce Zinciri: Sonucu üretmeden önce ara çıkarım adımları oluşturarak dil modellerinde akıl yürütmeyi geliştirmek için kullanılan bir tekniktir.
​
Devre Kesiciler: Belirli risk eşiklerinin aşıldığı durumlarda yapay zeka sistemi işlemlerini otomatik olarak durduran mekanizmalar.
​
Veri Sızıntısı: Yapay zeka model çıktıları veya davranışı aracılığıyla hassas bilgilerin istem dışı ifşası.
​
Veri Zehirlemesi: Model bütünlüğünü tehlikeye atmak amacıyla eğitim verilerinin kasıtlı olarak bozulması, genellikle arka kapı kurulması veya performansın düşürülmesi için yapılır.
​
Diferansiyel Gizlilik – Diferansiyel gizlilik, bireysel veri sahiplerinin gizliliğini korurken veri setleri hakkında istatistiksel bilgilerin paylaşılmasını sağlayan matematiksel olarak kesin bir çerçevedir. Bu yaklaşım, veri sahibi kişinin belirli bireyler hakkında sızıntı yapan bilgileri sınırlandırırken, grup genelindeki toplu örüntülerin paylaşılmasını mümkün kılar.
​
Gömüntüler: Semantik anlamı yüksek boyutlu bir uzayda yakalayan, verilerin (metin, görüntüler vb.) yoğun vektör temsilleri.
​
Açıklanabilirlik – Yapay zekada açıklanabilirlik, bir yapay zeka sisteminin kararları ve tahminleri için insan tarafından anlaşılabilir nedenler sunabilme yeteneği olup, iç işleyişine dair anlayış sağlar.
​
Açıklanabilir Yapay Zeka (XAI): Kararları ve davranışları için insan tarafından anlaşılabilir açıklamalar sağlamak üzere çeşitli teknikler ve çerçeveler kullanarak tasarlanmış yapay zeka sistemleri.
​
Federated Learning (Birleştirilmiş Öğrenme): Modellerin yerel veri örneklerine sahip çoklu merkezi olmayan cihazlarda, verilerin kendisi değiş tokuş edilmeden eğitildiği bir makine öğrenimi yaklaşımı.
​
Koruyucu Önlemler: Yapay zeka sistemlerinin zararlı, önyargılı veya başka şekilde istenmeyen çıktılar üretmesini önlemek için uygulanan kısıtlamalar.
​
Halüsinasyon – Bir yapay zeka halüsinasyonu, yapay zeka modelinin eğitim verilerine veya gerçeklik temel alınmaksızın yanlış veya yanıltıcı bilgi üretmesi durumunu ifade eder.
​
İnsan-Dahil Döngü (HITL): Kritik karar noktalarında insan denetimi, doğrulaması veya müdahalesi gerektirecek şekilde tasarlanmış sistemler.
​
Kod olarak Altyapı (IaC): Altyapıyı manuel işlemler yerine kod aracılığıyla yönetmek ve sağlamak, güvenlik taraması ve tutarlı dağıtımlara olanak tanır.
​
Jailbreak: Yasaklanmış içerik üretmek amacıyla, özellikle büyük dil modellerinde, AI sistemlerindeki güvenlik korumalarını aşmak için kullanılan teknikler.
​
En Az Ayrıcalık: Kullanıcılar ve süreçler için yalnızca gerekli olan en düşük erişim haklarının verilmesi güvenlik ilkesi.
​
LIME (Yerel Yorumlanabilir Model-Agnostik Açıklamalar): Herhangi bir makine öğrenimi sınıflandırıcısının tahminlerini, yerel olarak yorumlanabilir bir modelle yaklaşık olarak açıklamak için kullanılan bir tekniktir.
​
Üyelik Çıkarım Saldırısı: Belirli bir veri noktasının bir makine öğrenimi modelini eğitmek için kullanılıp kullanılmadığını belirlemeyi amaçlayan bir saldırı.
​
MITRE ATLAS: Yapay Zeka Sistemlerine Yönelik Düşmanca Tehdit Manzarası; Yapay zeka sistemlerine karşı düşmanca taktikler ve tekniklerin bilgi tabanı.
​
Model Kartı – Model kartı, bir yapay zeka modelinin performansı, sınırlamaları, hedef kullanımları ve etik değerlendirmeleri hakkında standart bilgi sağlayan ve şeffaflığı ile sorumlu yapay zeka geliştirmeyi teşvik eden bir belgedir.
​
Model Çıkarma: Bir saldırı türü olup, bir düşmanın hedef modeli tekrar tekrar sorgulayarak yetkisiz şekilde işlevsel olarak benzer bir kopyasını oluşturmasıdır.
​
Model Ters Çevirimi: Model çıktıları analiz edilerek eğitim verilerini yeniden oluşturmayı amaçlayan bir saldırı.
​
Model Yaşam Döngüsü Yönetimi – AI Model Yaşam Döngüsü Yönetimi, bir yapay zeka modelinin tasarımı, geliştirilmesi, dağıtımı, izlenmesi, bakımı ve nihai emekliliği dahil olmak üzere tüm varlık aşamalarını denetleme sürecidir; bu süreç, modelin etkili kalmasını ve hedeflerle uyumlu olmasını sağlar.
​
Model Zehirlemesi: Eğitim süreci sırasında doğrudan modele güvenlik açıkları veya arka kapılar ekleme.
​
Model Hırsızlığı/Çalınması: Tekrarlanan sorgular yoluyla tescilli bir modelin kopyasını veya yaklaşık bir versiyonunu çıkarmak.
​
Çok Ajanlı Sistem: Her biri potansiyel olarak farklı yeteneklere ve hedeflere sahip, birden fazla etkileşimli yapay zeka ajanından oluşan bir sistem.
​
OPA (Open Policy Agent): Yığını kapsayan birleşik politika uygulamasını mümkün kılan açık kaynaklı bir politika motoru.
​
Gizliliği Koruyan Makine Öğrenimi (PPML): Eğitim verilerinin gizliliğini korurken ML modellerini eğitmek ve dağıtmak için teknikler ve yöntemler.
​
İstem Enjeksiyonu: Bir modelin amaçlanan davranışını geçersiz kılmak için kötü niyetli talimatların girdilere yerleştirildiği bir saldırı.
​
RAG (Elde Edilmiş Üretim): Yanıt oluşturmadan önce ilgili bilgileri dış bilgi kaynaklarından alarak büyük dil modellerini geliştiren bir tekniktir.
​
Red-Teaming: Yapay zeka sistemlerindeki zayıflıkları tespit etmek amacıyla düşmanca saldırıları simüle ederek aktif test yapma uygulaması.
​
SBOM (Yazılım Malzeme Listesi): Yazılım veya AI modelleri oluşturulurken kullanılan çeşitli bileşenlerin detaylarını ve tedarik zinciri ilişkilerini içeren resmi kayıt.
​
SHAP (SHapley Katkı Açıklamaları): Her bir özellikle tahmin arasındaki katkıyı hesaplayarak herhangi bir makine öğrenimi modelinin çıktısını açıklamak için oyun teorisine dayalı bir yaklaşım.
​
Tedarik Zinciri Saldırısı: Üçüncü taraf kütüphaneler, veri setleri veya önceden eğitilmiş modeller gibi tedarik zincirindeki daha az güvenli unsurları hedefleyerek bir sistemi ele geçirme.
​
Transfer Learning: Bir görev için geliştirilen bir modelin, ikinci bir görev için modelin başlangıç noktası olarak yeniden kullanıldığı bir tekniktir.
​
Vektör Veritabanı: Yüksek boyutlu vektörleri (gömülü temsiller) depolamak ve etkili benzerlik aramaları gerçekleştirmek için tasarlanmış özelleşmiş bir veritabanı.
​
Güvenlik Açığı Tarama: AI çerçeveleri ve bağımlılıklar dahil olmak üzere yazılım bileşenlerindeki bilinen güvenlik açıklarını otomatik olarak tanımlayan araçlar.
​
Filigranlama: Kökenini takip etmek veya yapay zeka tarafından üretildiğini tespit etmek için yapay zeka tarafından oluşturulan içeriğe farkedilemez işaretler yerleştirme teknikleri.
​
Sıfırıncı Gün Açığı: Geliştiriciler bir yama oluşturup dağıtmadan önce saldırganların kötüye kullanabileceği daha önce bilinmeyen bir güvenlik açığı.

## Ek B: Referanslar

### TODO

## Ek C: Yapay Zeka Güvenliği Yönetimi ve Dokümantasyonu

### Amaç

Bu ek, sistem yaşam döngüsü boyunca AI güvenliğini yönetmek için örgütsel yapılar, politikalar ve süreçler oluşturmak için temel gereksinimleri sağlar.

---

### AC.1 AI Risk Yönetimi Çerçevesi Kabulü

Sistem yaşam döngüsü boyunca yapay zekaya özgü riskleri tanımlamak, değerlendirmek ve hafifletmek için resmi bir çerçeve sağlayın.

 #AC.1.1    Level: 1    Role: D/V
 Bir yapay zeka‑özel risk değerlendirme metodolojisinin belgelenmiş ve uygulanmış olduğunu doğrulayın.
 #AC.1.2    Level: 2    Role: D
 AI yaşam döngüsünün kilit noktalarında ve önemli değişikliklerden önce risk değerlendirmelerinin yapıldığını doğrulayın.
 #AC.1.3    Level: 3    Role: D/V
 Risk yönetim çerçevesinin, belirlenmiş standartlarla (örneğin, NIST AI RMF) uyumlu olduğunu doğrulayın.

---

### AC.2 AI Güvenlik Politikası ve Prosedürleri

Güvenli yapay zeka geliştirme, dağıtım ve işletme için kurumsal standartları tanımlayın ve uygulayın.

 #AC.2.1    Level: 1    Role: D/V
 Belgelendirilmiş yapay zeka güvenlik politikalarının var olduğunu doğrulayın.
 #AC.2.2    Level: 2    Role: D
 Politikaların en az yılda bir kez ve önemli tehdit ortamı değişikliklerinden sonra gözden geçirilip güncellendiğini doğrulayın.
 #AC.2.3    Level: 3    Role: D/V
 Politikaların tüm AISVS kategorilerini ve geçerli düzenleyici gereklilikleri kapsadığını doğrulayın.

---

### AC.3 AI Güvenliği için Rolleri ve Sorumlulukları

Kuruluş genelinde AI güvenliği için net sorumluluklar belirleyin.

 #AC.3.1    Level: 1    Role: D/V
 Yapay zeka güvenliği rollerinin ve sorumluluklarının belgelenip belgelenmediğini doğrulayın.
 #AC.3.2    Level: 2    Role: D
 Sorumlu kişilerin uygun güvenlik uzmanlığına sahip olduğunu doğrulayın.
 #AC.3.3    Level: 3    Role: D/V
 Yüksek riskli yapay zeka sistemleri için bir yapay zeka etik komitesinin veya yönetişim kurulunun oluşturulduğunu doğrulayın.

---

### AC.4 Etik Yapay Zeka Yönergeleri Uygulaması

Yapay zeka sistemlerinin belirlenmiş etik ilkelere göre çalışmasını sağlayın.

 #AC.4.1    Level: 1    Role: D/V
 Yapay zeka geliştirme ve deploy etme için etik kuralların var olduğunu doğrulayın.
 #AC.4.2    Level: 2    Role: D
 Etik ihlalleri tespit etmek ve bildirmek için mekanizmaların yerinde olduğunu doğrulayın.
 #AC.4.3    Level: 3    Role: D/V
 Dağıtılan yapay zeka sistemlerinin düzenli etik incelemelerinin yapıldığını doğrulayın.

---

### AC.5 AI Düzenleyici Uyumluluk İzleme

Gelişen Yapay Zeka düzenlemeleri konusunda farkındalığı koruyun ve uyumu sağlayın.

 #AC.5.1    Level: 1    Role: D/V
 Uygulanabilir Yapay Zeka düzenlemelerini belirlemek için süreçlerin var olduğunu doğrulayın.
 #AC.5.2    Level: 2    Role: D
 Tüm düzenleyici gereksinimlere uyumun değerlendirildiğini doğrulayın.
 #AC.5.3    Level: 3    Role: D/V
 Yasal değişikliklerin, yapay zeka sistemlerinin zamanında gözden geçirilmesini ve güncellenmesini tetiklediğini doğrulayın.

#### Referanslar

NIST AI Risk Management Framework 1.0
ISO/IEC 42001:2023 — AI Management Systems Requirements
ISO/IEC 23894:2023 — Artificial Intelligence — Guidance on Risk Management
EU Artificial Intelligence Act — Regulation (EU) 2024/1689
ISO/IEC 24029‑2:2023 — Robustness of Neural Networks — Methodology for Formal Methods

## Ek D: Yapay Zeka Destekli Güvenli Kodlama Yönetişimi ve Doğrulama

### Amaç

Bu bölüm, yazılım geliştirme sırasında AI destekli kodlama araçlarının güvenli ve etkili kullanımını sağlamak için temel kurumsal kontrolleri tanımlar ve SDLC boyunca güvenlik ve izlenebilirliği garanti eder.

---

### AD.1 Yapay Zeka Destekli Güvenli Kodlama İş Akışı

Yapay zeka araçlarını, mevcut güvenlik kapılarını zayıflatmadan, kuruluşun güvenli yazılım geliştirme yaşam döngüsüne (SSDLC) entegre edin.

 #AD.1.1    Level: 1    Role: D/V
 Belgelendirilmiş bir iş akışının, yapay zeka araçlarının kodu ne zaman ve nasıl oluşturabileceğini, yeniden düzenleyebileceğini veya inceleyebileceğini açıkladığını doğrulayın.
 #AD.1.2    Level: 2    Role: D
 İş akışının her SSDLC aşamasına (tasarım, uygulama, kod incelemesi, test, dağıtım) uygun olduğunu doğrulayın.
 #AD.1.3    Level: 3    Role: D/V
 AI tarafından üretilen kod üzerinde metriklerin (örneğin, zaafiyet yoğunluğu, ortalama tespit süresi) toplandığını ve yalnızca insan tarafından oluşturulan temel değerlerle karşılaştırıldığını doğrulayın.

---

### AD.2 AI Aracı Nitelendirme ve Tehdit Modelleme

Yapay zeka kodlama araçlarının benimsenmeden önce güvenlik yetenekleri, risk ve tedarik zinciri etkisi açısından değerlendirilmesini sağlayın.

 #AD.2.1    Level: 1    Role: D/V
 Her AI aracı için bir tehdit modelinin kötüye kullanım, model-inversiyonu, veri sızıntısı ve bağımlılık zinciri risklerini tanımladığını doğrulayın.
 #AD.2.2    Level: 2    Role: D
 Araç değerlendirmelerinin, herhangi bir yerel bileşenin statik/dinamik analizini ve SaaS uç noktalarının (TLS, kimlik doğrulama/izin, günlük kaydı) değerlendirmesini içerdiğini doğrulayın.
 #AD.2.3    Level: 3    Role: D/V
 Değerlendirmelerin tanınmış bir çerçeveye uygun olduğunu ve büyük sürüm değişikliklerinden sonra tekrar yapıldığını doğrulayın.

---

### AD.3 Güvenli İstem ve Bağlam Yönetimi

AI modelleri için istemler veya bağlamlar oluşturulurken gizli bilgiler, özel kodlar ve kişisel verilerin sızmasını önleyin.

 #AD.3.1    Level: 1    Role: D/V
 Yazılı rehberlikte, istemlerde gizli bilgiler, kimlik bilgileri veya sınıflandırılmış verilerin gönderilmesinin yasaklandığını doğrulayın.
 #AD.3.2    Level: 2    Role: D
 Teknik kontrollerin (istemci tarafı sansürleme, onaylanmış bağlam filtreleri) hassas unsurları otomatik olarak kaldırdığını doğrulayın.
 #AD.3.3    Level: 3    Role: D/V
 İsteklerin ve yanıtların tokenize edildiğini, iletim sırasında ve depolanırken şifrelendiğini ve saklama sürelerinin veri sınıflandırma politikasına uygun olduğunu doğrulayın.

---

### AD.4 Yapay Zeka ile Üretilen Kodun Doğrulanması

AI çıktısı tarafından tanıtılan güvenlik açıklarını, kod birleştirilmadan veya dağıtılmadan önce tespit edin ve giderin.

 #AD.4.1    Level: 1    Role: D/V
 AI tarafından üretilen kodun her zaman insan kod incelemesine tabi tutulduğunu doğrulayın.
 #AD.4.2    Level: 2    Role: D
 Otomatik tarayıcıların (SAST/IAST/DAST) her yapay zeka tarafından oluşturulan kod içeren çekme isteğinde çalıştığını doğrulayın ve kritik bulgular tespit edildiğinde birleştirmeleri engelleyin.
 #AD.4.3    Level: 3    Role: D/V
 Farklılaştırılmış fuzz testi veya özellik tabanlı testlerin, güvenlik açısından kritik davranışları (örneğin, girdi doğrulama, yetkilendirme mantığı) kanıtladığını doğrulayın.

---

### AD.5 Kod Önerilerinin Açıklanabilirliği ve İzlenebilirliği

Denetçilere ve geliştiricilere, neden bir öneride bulunulduğuna ve önerinin nasıl geliştiğine dair bilgi sağlayın.

 #AD.5.1    Level: 1    Role: D/V
 İstem/yanıt çiftlerinin commit kimlikleri ile kaydedildiğini doğrulayın.
 #AD.5.2    Level: 2    Role: D
 Geliştiricilerin, bir öneriyi destekleyen model atıflarını (eğitim parçacıkları, belgelemeler) görüntüleyebildiklerini doğrulayın.
 #AD.5.3    Level: 3    Role: D/V
 Açıklanabilirlik raporlarının tasarım eserleriyle birlikte saklandığını ve ISO/IEC 42001 izlenebilirlik ilkelerini karşılayacak şekilde güvenlik incelemelerinde referans verildiğini doğrulayın.

---

### AD.6 Sürekli Geri Bildirim ve Model İnce Ayarı

Negatif sapmayı önlerken model güvenlik performansını zaman içinde iyileştirin.

 #AD.6.1    Level: 1    Role: D/V
 Geliştiricilerin güvensiz veya uyumsuz önerileri işaretleyebildiğini ve bu işaretlerin takip edildiğini doğrulayın.
 #AD.6.2    Level: 2    Role: D
 Toplanan geri bildirimin, doğrulanmış güvenli kodlama korpusları (örneğin, OWASP Cheat Sheets) ile periyodik ince ayar veya doğrulanmış veri kullanılarak artırılmış üretim için bilgilendirdiğini doğrulayın.
 #AD.6.3    Level: 3    Role: D/V
 Kapatılmış döngü değerlendirme sistemi, her ince ayardan sonra regresyon testlerini çalıştırdığını doğrulayın; güvenlik metrikleri, dağıtımdan önce önceki temel değerleri karşılamalı veya aşmalıdır.

---

#### Kaynaklar

NIST AI Risk Management Framework 1.0
ISO/IEC 42001:2023 — AI Management Systems Requirements
OWASP Secure Coding Practices — Quick Reference Guide

## Ek E: Örnek Araçlar ve Çerçeveler

### Amaç

Bu bölüm, belirli bir AISVS gereksiniminin uygulanmasını veya karşılanmasını destekleyebilecek araçlar ve çerçeveler için örnekler sunmaktadır. Bunlar, AISVS ekibi veya OWASP GenAI Güvenlik Projesi tarafından öneri veya onay olarak değerlendirilmemelidir.

---

### AE.1 Eğitim Verisi Yöneti̇mi ve Önyargı Yönetimi

Veri analitiği, yönetişim ve önyargı yönetimi için kullanılan araçlar.

 #AE.1.1    Section: 1.1
 Veri Envanteri Araçları: Veri envanteri yönetimi araçları gibi...
 #AE.1.2    Section: 1.2
 İletim Halinde Şifreleme HTTPS tabanlı uygulamalar için openSSL ve python gibi araçlar kullanarak TLS kullanın`ssl`kütüphane.

---

### AE.2 Kullanıcı Girişi Doğrulaması

Kullanıcı girdilerini işlemek ve doğrulamak için araçlar.

 #AE.2.1    Section: 2.1
 Prompt Enjeksiyon Koruma Araçları: NVIDIA'nın NeMo veya Guardrails AI gibi koruyucu araçlar kullanın.

---

