# C1 Eğitim Veri Yönetişimi ve Önyargı Yönetimi

## Kontrol Hedefi

Eğitim verileri, köken, güvenlik, kalite ve adaleti koruyacak şekilde temin edilmeli, işlenmeli ve muhafaza edilmelidir. Böyle yapmak, yasal yükümlülükleri yerine getirir ve yapay zeka yaşam döngüsü boyunca önyargı, zehirlenme veya gizlilik ihlali risklerini azaltır.

---

## C1.1 Eğitim Verisi Kökeni

Tüm veri setlerinin doğrulanabilir envanterini tutun, yalnızca güvenilir kaynakları kabul edin ve denetlenebilirlik için her değişikliği kaydedin.

|   #   | Description                                                                                                                                                                                                                                                                | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.1.1 | Her eğitim veri kaynağının (kaynak, sorumlu/sahip, lisans, toplama yöntemi, amaçlanan kullanım kısıtlamaları ve işleme geçmişi) güncel bir envanterinin tutulduğunu doğrulayın.                                                                                            |   1   | D/V  |
| 1.1.2 | Sadece kalite, temsil yeteneği, etik kaynak kullanımı ve lisans uyumluluğu açısından incelenmiş veri setlerinin kabul edildiğini doğrulayın; böylece zehirlenme, yerleşik önyargı ve fikri mülkiyet ihlali riskleri azaltılır.                                             |   1   | D/V  |
| 1.1.3 | Gereksiz veya hassas özniteliklerin hariç tutulduğundan emin olmak için veri minimizasyonunun uygulandığını doğrulayın.                                                                                                                                                    |   1   | D/V  |
| 1.1.4 | Tüm veri seti değişikliklerinin kaydedilen onay iş akışına tabi olduğunu doğrulayın.                                                                                                                                                                                       |   2   | D/V  |
| 1.1.5 | Etiketleme/yorumlama kalitesinin, değerlendirici çapraz kontrolleri veya uzlaşması yoluyla sağlandığını doğrulayın.                                                                                                                                                        |   2   | D/V  |
| 1.1.6 | Önemli eğitim veri setleri için "veri kartlarının" veya "veri setleri için veri sayfalarının" tutulduğunu doğrulayın; bu kartlarda özellikler, motivasyonlar, bileşim, toplama süreçleri, ön işleme ve önerilen/önerilmeyen kullanım şekilleri detaylandırılmış olmalıdır. |   2   | D/V  |

---

## C1.2 Eğitim Verisi Güvenliği ve Bütünlüğü

Erişimi kısıtlayın, verileri kalıcı ve aktarım sırasında şifreleyin ve bütünlüğü doğrulayarak müdahale veya hırsızlığı engelleyin.

|   #   | Description                                                                                                                                                                                                                                                                                                         | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.2.1 | Erişim kontrollerinin depolama ve veri boru hatlarını koruduğunu doğrulayın.                                                                                                                                                                                                                                        |   1   | D/V  |
| 1.2.2 | Veri setlerinin, tüm hassas veya kişisel olarak tanımlanabilir bilgiler (PII) için, endüstri standartlarındaki kriptografik algoritmalar ve anahtar yönetim uygulamaları kullanılarak, iletim sırasında ve dinlenirken şifrelenmiş olduğunu doğrulayın.                                                             |   2   | D/V  |
| 1.2.3 | Veri bütünlüğünün depolama ve transfer sırasında sağlanması için kriptografik özetlerin veya dijital imzaların kullanıldığını ve yetkisiz değişiklikler veya bozulmalar, özellikle hedeflenmiş veri zehirleme girişimlerine karşı korunmak amacıyla otomatik anomali tespit tekniklerinin uygulandığını doğrulayın. |   2   | D/V  |
| 1.2.4 | Veri kümesi sürümlerinin geri alma işlemini mümkün kılacak şekilde takip edildiğini doğrulayın.                                                                                                                                                                                                                     |   3   | D/V  |
| 1.2.5 | Veri saklama politikları, düzenleyici gereklilikler ile uyumlu olarak geçersiz verilerin güvenli bir şekilde silindiğini veya anonimleştirildiğini doğrulayın ve böylece saldırı yüzeyini azaltın.                                                                                                                  |   2   | D/V  |

---

## C1.3 Temsil Tamlığı ve Adalet

Demografik eğilimleri tespit edin ve modelin hata oranlarının gruplar arasında eşit olmasını sağlamak için düzeltme uygulayın.

|   #   | Description                                                                                                                                                                                                                                                                                                                                                              | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 1.3.1 | Veri setlerinin, temsil dengesizliği ve yasal olarak korunan özellikler (örneğin, ırk, cinsiyet, yaş) ile modelin uygulama alanına ilişkin diğer etik açıdan hassas özellikler (örneğin, sosyo-ekonomik durum, konum) bazında potansiyel önyargılar açısından incelendiğini doğrulayın.                                                                                  |   1   | D/V  |
| 1.3.2 | Belirlenen önyargıların, yeniden dengeleme, hedeflenmiş veri artırımı, algoritmik ayarlamalar (örneğin, ön işleme, işlem sırasında ve işlem sonrası teknikler) veya yeniden ağırlıklandırma gibi belgelenmiş stratejilerle giderildiğini doğrulayın ve giderme işleminin hem adalet hem de genel model performansı üzerindeki etkisinin değerlendirildiğinden emin olun. |   2   | D/V  |
| 1.3.3 | Eğitim sonrası adalet metriklerinin değerlendirildiğini ve belgelenmesini doğrulayın.                                                                                                                                                                                                                                                                                    |   2   | D/V  |
| 1.3.4 | Bir yaşam döngüsü yanlılık yönetimi politikasının sahipleri ve inceleme sıklığını atadığını doğrulayın.                                                                                                                                                                                                                                                                  |   3   | D/V  |

---

## C1.4 Eğitim Verisi Etiketleme Kalitesi, Bütünlüğü ve Güvenliği

Etiketleri şifreleme ile koruyun ve kritik sınıflar için çift inceleme gerektirin.

|   #   | Description                                                                                                                                                                                                                                                                                          | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.4.1 | Etiketleme/yorumlama kalitesinin, açık yönergeler, inceleyici çapraz kontrolleri, uzlaşma mekanizmaları (örneğin, anotatörler arası uyumun izlenmesi) ve uyuşmazlıkları çözmek için tanımlanmış süreçler aracılığıyla sağlandığını doğrulayın.                                                       |   2   | D/V  |
| 1.4.2 | Etiket artefaktlarına bütünlüklerini ve özgünlüklerini sağlamak amacıyla kriptografik özetlerin veya dijital imzaların uygulandığını doğrulayın.                                                                                                                                                     |   2   | D/V  |
| 1.4.3 | Etiketleme arayüzlerinin ve platformlarının güçlü erişim kontrolleri uyguladığını, tüm etiketleme faaliyetlerinin değiştirilemez denetim kayıtlarını tuttuğunu ve yetkisiz değişikliklere karşı koruma sağladığını doğrulayın.                                                                       |   2   | D/V  |
| 1.4.4 | Güvenlik, emniyet veya adalet açısından kritik olan etiketlerin (örneğin, toksik içeriğin tanımlanması, kritik tıbbi bulgular) zorunlu bağımsız çift inceleme veya eşdeğer sağlam doğrulamadan geçmesini sağlayın.                                                                                   |   3   | D/V  |
| 1.4.5 | Etiketlerde yanlışlıkla yakalanan veya zorunlu olarak bulunan hassas bilgilerin (kişisel tanımlayıcı bilgiler dahil) veri minimizasyonu prensiplerine uygun olarak, dinlenme halinde ve iletim sırasında sansürlendiği, takma ad kullanıldığı, anonimleştirildiği veya şifrelendiği doğrulanmalıdır. |   2   | D/V  |
| 1.4.6 | Etiketleme rehberlerinin ve talimatlarının kapsamlı, sürüm kontrolüne tabi ve meslektaş incelemesinden geçmiş olduğunu doğrulayın.                                                                                                                                                                   |   2   | D/V  |
| 1.4.7 | Veri şemalarının (etiketler dahil) net bir şekilde tanımlandığını ve sürüm kontrolünün yapıldığını doğrulayın.                                                                                                                                                                                       |   2   | D/V  |
| 1.8.2 | Dış kaynaklı veya kitle kaynaklı etiketleme iş akışlarının, veri gizliliği, bütünlüğü, etiket kalitesi sağlama ve veri sızıntısını önleme için teknik/prosedürel güvenlik önlemlerini içerdiğini doğrulayın.                                                                                         |   2   | D/V  |

---

## C1.5 Eğitim Verisi Kalite Güvencesi

Otomatik doğrulama, manuel rastgele kontroller ve kaydedilen iyileştirmeleri birleştirerek veri seti güvenilirliğini garanti altına alın.

|   #   | Description                                                                                                                                                                                                                                                                                             | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.5.1 | Otomatik testlerin, her veri alımında veya önemli bir dönüşümde format hatalarını, boş değerleri ve etiket kaymalarını yakaladığını doğrulayın.                                                                                                                                                         |   1   |  D   |
| 1.5.2 | Başarısız veri setlerinin denetim izleriyle karantinaya alındığını doğrulayın.                                                                                                                                                                                                                          |   1   | D/V  |
| 1.5.3 | Alan uzmanları tarafından yapılan manuel nokta kontrollerinin, otomasyon tarafından yakalanamayan ince kalite sorunlarını tespit etmek için istatistiksel olarak anlamlı bir örneklem (örneğin, ≥%1 veya 1.000 örnek, hangisi büyükse veya risk değerlendirmesi ile belirlenen) kapsadığını doğrulayın. |   2   |  V   |
| 1.5.4 | Düzeltme adımlarının kaynak kayıtlarına eklendiğini doğrulayın.                                                                                                                                                                                                                                         |   2   | D/V  |
| 1.5.5 | Kalite kapılarının, istisnalar onaylanmadıkça standart altı veri kümelerini engellediğini doğrulayın.                                                                                                                                                                                                   |   2   | D/V  |

---

## C1.6 Veri Zehirleme Tespiti

İstatistiksel anomali tespiti ve karantina iş akışlarını uygulayarak düşmanca eklemeleri durdurun.

|   #   | Description                                                                                                                                                                                                                                                                                       | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.6.1 | Anomali tespit tekniklerinin (örneğin, istatistiksel yöntemler, aykırı değer tespiti, gömme analizi) potansiyel zehirlenme saldırılarını veya istem dışı veri bozulmalarını belirlemek için veri alımı sırasında ve önemli eğitim çalışmaları öncesinde eğitim verisine uygulandığını doğrulayın. |   2   | D/V  |
| 1.6.2 | İşaretlenen örneklerin eğitimden önce manuel incelemeyi tetiklediğini doğrulayın.                                                                                                                                                                                                                 |   2   | D/V  |
| 1.6.3 | Sonuçların modelin güvenlik dosyasını beslediğini ve devam eden tehdit istihbaratını bilgilendirdiğini doğrulayın.                                                                                                                                                                                |   2   |  V   |
| 1.6.4 | Tespit mantığının yeni tehdit istihbaratı ile güncellendiğini doğrulayın.                                                                                                                                                                                                                         |   3   | D/V  |
| 1.6.5 | Çevrimiçi öğrenme boru hatlarının dağılım kaymasını izlediğini doğrulayın.                                                                                                                                                                                                                        |   3   | D/V  |
| 1.6.6 | Sistem risk profili ve veri kaynaklarına göre bilinen veri zehirleme saldırı türlerine (örneğin, etiket çevirme, arka kapı tetikleyici ekleme, etkili örnek saldırıları) karşı belirli savunmaların göz önünde bulundurulup uygulanmasını doğrulayın.                                             |   3   | D/V  |

---

## C1.7 Kullanıcı Verisi Silme ve Onay Uygulaması

Veri setleri, yedekler ve türetilmiş ürünler genelinde silme ve onay çekme taleplerine uyun.

|   #   | Description                                                                                                                                                                                                                                                                | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.7.1 | Silme iş akışlarının birincil ve türetilmiş verileri tamamen kaldırdığını doğrulayın ve model üzerindeki etkisini değerlendirin; etkilenen modeller üzerindeki etkinin gerektiğinde (örneğin, yeniden eğitim veya yeniden kalibrasyon yoluyla) ele alındığından emin olun. |   1   | D/V  |
| 1.7.2 | Kullanıcı onayının kapsamını ve durumunu (ve geri çekilmelerini) izlemek ve saygı göstermek için mekanizmaların mevcut olduğunu doğrulayın ve veriler yeni eğitim süreçlerine veya önemli model güncellemelerine dahil edilmeden önce onayın geçerli olduğunu teyit edin.  |   2   |  D   |
| 1.7.3 | İş akışlarının yıllık olarak test edildiğini ve kaydedildiğini doğrulayın.                                                                                                                                                                                                 |   2   |  V   |

---

## C1.8 Tedarik Zinciri Güvenliği

Harici veri sağlayıcılarını değerlendirin ve kimlik doğrulamalı, şifrelenmiş kanallar üzerinden bütünlüğünü doğrulayın.

|   #   | Description                                                                                                                                                                                                                                                                                                        | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 1.8.1 | Üçüncü taraf veri tedarikçilerinin, önceden eğitilmiş modeller ve dış veri setleri sağlayıcıları dahil olmak üzere, verileri veya modelleri entegre edilmeden önce güvenlik, gizlilik, etik kaynak sağlama ve veri kalitesi konularında titiz incelemeye tabi tutulduğunu doğrulayın.                              |   2   | D/V  |
| 1.8.2 | Dış transferlerin TLS/doğrulama ve bütünlük kontrolleri kullandığını doğrulayın.                                                                                                                                                                                                                                   |   1   |  D   |
| 1.8.3 | Yüksek riskli veri kaynaklarının (örneğin, kaynağı bilinmeyen açık kaynak veri setleri, denetlenmemiş tedarikçiler) hassas uygulamalarda kullanılmadan önce sızdırmaz ortamda analiz, kapsamlı kalite/önyargı kontrolleri ve hedeflenmiş zehirlenme tespiti gibi artırılmış denetime tabi tutulduğundan emin olun. |   2   | D/V  |
| 1.8.4 | Üçüncü taraflardan elde edilen önceden eğitilmiş modellerin, ince ayar yapılmadan veya dağıtıma alınmadan önce gömülü önyargılar, potansiyel arka kapılar, mimari bütünlüğü ve orijinal eğitim verilerinin kaynağı açısından değerlendirildiğini doğrulayın.                                                       |   3   | D/V  |

---

## C1.9 Adversarial Örnek Tespiti

Eğitim aşamasında, modelin rakip örneklere karşı dayanıklılığını artırmak için rakip eğitim gibi önlemler uygulayın.

|   #   | Description                                                                                                                                                                                                                                                                      | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.9.1 | İlgili modeller için risk değerlendirmesine dayanarak oluşturulan saldırgan örnekler kullanılarak yapılan saldırgan eğitim, bozulmuş girişlerle veri artırımı veya sağlam optimizasyon teknikleri gibi uygun savunmaların uygulanıp uygulanmadığını ve ayarlandığını doğrulayın. |   3   | D/V  |
| 1.9.2 | Eğer düşmanca eğitim kullanılıyorsa, düşmanca veri kümelerinin oluşturulması, yönetimi ve sürüm kontrolünün belgelenip kontrol edildiğini doğrulayın.                                                                                                                            |   2   | D/V  |
| 1.9.3 | Model performansı (hem temiz hem de saldırgan girişlere karşı) ve adalet metrikleri üzerindeki adversarial sağlamlık eğitiminin etkisinin değerlendirilmesini, belgelenmesini ve izlenmesini doğrulayın.                                                                         |   3   | D/V  |
| 1.9.4 | Evrimleşen düşmanca saldırı tekniklerine karşı koymak için düşmanca eğitim ve dayanıklılık stratejilerinin periyodik olarak gözden geçirilip güncellendiğini doğrulayın.                                                                                                         |   3   | D/V  |

---

## C1.10 Veri Soyu ve İzlenebilirlik

Denetim ve olay müdahalesi için her veri noktasının kaynaktan modele girişine kadar tüm yolculuğunu takip edin.

|   #    | Description                                                                                                                                               | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.10.1 | Her veri noktasının kökeninin, tüm dönüşümler, artırmalar ve birleştirmeler dahil olmak üzere, kaydedildiğini ve yeniden oluşturulabileceğini doğrulayın. |   2   | D/V  |
| 1.10.2 | Soy kütüğü kayıtlarının değiştirilemez, güvenli bir şekilde saklanmış ve denetimler veya soruşturmalar için erişilebilir olduğunu doğrulayın.             |   2   | D/V  |
| 1.10.3 | Soy takip sisteminin hem ham hem de sentetik veriyi kapsadığından emin olun.                                                                              |   2   | D/V  |

---

## C1.11 Sentetik Veri Yönetimi

Sentetik verilerin doğru şekilde yönetildiğinden, etiketlendiğinden ve risk değerlendirmesinin yapıldığından emin olun.

|   #    | Description                                                                                                                                              | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.11.1 | Tüm sentetik verilerin, boru hattı boyunca gerçek verilerden açıkça etiketlendiğini ve ayırt edilebilir olduğunu doğrulayın.                             |   2   | D/V  |
| 1.11.2 | Sentetik verinin oluşturulma sürecinin, parametrelerinin ve amaçlanan kullanımının belgelenmiş olduğunu doğrulayın.                                      |   2   | D/V  |
| 1.11.3 | Sentetik verilerin eğitimde kullanılmadan önce önyargı, gizlilik sızıntısı ve temsil sorunları açısından risk değerlendirmesinin yapıldığını doğrulayın. |   2   | D/V  |

---

## C1.12 Veri Erişim İzleme ve Anomali Tespiti

Eğitim verilerine olağandışı erişimi izleyin ve uyarı verin, iç tehditleri veya dışa aktarımı tespit etmek için.

|   #    | Description                                                                                                                                                | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.12.1 | Eğitim verilerine yapılan tüm erişimlerin, kullanıcı, zaman ve işlem dahil olmak üzere kaydedildiğinden emin olun.                                         |   2   | D/V  |
| 1.12.2 | Erişim günlüklerinin, büyük veri dışa aktarımları veya yeni konumlardan erişim gibi olağandışı kalıplar açısından düzenli olarak incelendiğini doğrulayın. |   2   | D/V  |
| 1.12.3 | Şüpheli erişim olayları için uyarıların oluşturulduğunu ve derhal araştırıldığını doğrulayın.                                                              |   2   | D/V  |

---

## C1.13 Veri Saklama ve Süre Sonu Politikaları

Gereksiz veri depolamayı en aza indirmek için veri saklama sürelerini tanımlayın ve uygulayın.

|   #    | Description                                                                                                                                  | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.13.1 | Tüm eğitim veri setleri için açık saklama sürelerinin tanımlandığını doğrulayın.                                                             |   1   | D/V  |
| 1.13.2 | Veri setlerinin yaşam döngülerinin sonunda otomatik olarak süresinin dolduğundan, silindiğinden veya silinme için incelendiğinden emin olun. |   2   | D/V  |
| 1.13.3 | Saklama ve silme işlemlerinin kaydedildiğini ve denetlenebilir olduğunu doğrulayın.                                                          |   2   | D/V  |

---

## C1.14 Düzenleyici ve Yargı Uyumu

Tüm eğitim verilerinin geçerli yasa ve yönetmeliklere uygun olduğundan emin olun.

|   #    | Description                                                                                                                 | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.14.1 | Tüm veri setleri için veri yerleşimi ve sınır ötesi transfer gereksinimlerinin belirlenip uygulanmasını doğrulayın.         |   2   | D/V  |
| 1.14.2 | Sektörlere özgü düzenlemelerin (örneğin, sağlık, finans) veri işleme sürecinde tanımlandığını ve ele alındığını doğrulayın. |   2   | D/V  |
| 1.14.3 | İlgili gizlilik yasalarına (ör. GDPR, CCPA) uyumun belgelendiğini ve düzenli olarak gözden geçirildiğini doğrulayın.        |   2   | D/V  |

---

## C1.15 Veri Filigranlama ve Parmak İzi Oluşturma

Yetkisiz yeniden kullanımını veya sahipli ya da hassas verilerin sızdırılmasını tespit edin.

|   #    | Description                                                                                                                               | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.15.1 | Veri kümelerinin veya alt kümelerin mümkün olan yerlerde dijital filigranla işaretlendiğini veya parmak iziyle tanımlandığını doğrulayın. |   3   | D/V  |
| 1.15.2 | Filigranlama/parmak izi yöntemlerinin önyargı veya gizlilik riski oluşturmadığını doğrulayın.                                             |   3   | D/V  |
| 1.15.3 | Filigranlı verinin yetkisiz yeniden kullanımı veya sızıntısını tespit etmek için düzenli kontrollerin yapıldığını doğrulayın.             |   3   | D/V  |

---

## C1.16 Veri Sahibi Hakları Yönetimi

Erişim, düzeltme, kısıtlama ve itiraz gibi veri sahiplerinin haklarını destekleyin.

|   #    | Description                                                                                                                     | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.16.1 | Veri sahibinin erişim, düzeltme, kısıtlama veya itiraz taleplerine yanıt vermek için mekanizmaların mevcut olduğunu doğrulayın. |   2   | D/V  |
| 1.16.2 | İsteklerin yasal olarak belirlenmiş zaman dilimleri içinde kaydedildiğini, izlendiğini ve yerine getirildiğini doğrulayın.      |   2   | D/V  |
| 1.16.3 | Veri konusu kişilerin hak süreçlerinin etkinliği için düzenli olarak test edildiğini ve gözden geçirilmesini doğrulayın.        |   2   | D/V  |

---

## C1.17 Veri Seti Sürümünün Etki Analizi

Sürümleri güncellemeden veya değiştirmeden önce veri kümesi değişikliklerinin etkisini değerlendirin.

|   #    | Description                                                                                                                                                    | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.17.1 | Bir veri kümesi sürümü güncellenmeden veya değiştirilmeden önce, model performansı, adillik ve uyumluluğu kapsayan bir etki analizinin yapıldığını doğrulayın. |   2   | D/V  |
| 1.17.2 | Etkileşim analizinin sonuçlarının ilgili paydaşlar tarafından belgelenip incelendiğini doğrulayın.                                                             |   2   | D/V  |
| 1.17.3 | Yeni sürümler kabul edilemez riskler veya gerilemeler getirdiğinde kullanılmak üzere geri alma planlarının var olduğunu doğrulayın.                            |   2   | D/V  |

---

## C1.18 Veri Etiketleme İşgücü Güvenliği

Veri anotasyonunda yer alan personelin güvenliğini ve bütünlüğünü sağlamak.

|   #    | Description                                                                                                                                      | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 1.18.1 | Veri açıklamasıyla ilgili tüm personelin geçmiş kontrollerinin yapıldığını ve veri güvenliği ile gizliliği konusunda eğitim aldığını doğrulayın. |   2   | D/V  |
| 1.18.2 | Tüm anotasyon personelinin gizlilik ve ifşa etmeme sözleşmelerini imzaladığını doğrulayın.                                                       |   2   | D/V  |
| 1.18.3 | Notasyon platformlarının erişim kontrollerini uyguladığını ve içeriden gelen tehditler için izleme yaptığını doğrulayın.                         |   2   | D/V  |

---

## Referanslar

* [NIST AI Risk Management Framework](https://www.nist.gov/itl/ai-risk-management-framework)
* [EU AI Act – Article 10: Data & Data Governance](https://artificialintelligenceact.eu/article/10/)
* [MITRE ATLAS: Adversary Tactics for AI](https://atlas.mitre.org/)
* [Survey of ML Bias Mitigation Techniques – MDPI](https://www.mdpi.com/2673-6470/4/1/1)
* [Data Provenance & Lineage Best Practices – Nightfall AI](https://www.nightfall.ai/ai-security-101/data-provenance-and-lineage)
* [Data Labeling Quality Standards – LabelYourData](https://labelyourdata.com/articles/data-labeling-quality-and-how-to-measure-it)
* [Training Data Poisoning Guide – Lakera.ai](https://www.lakera.ai/blog/training-data-poisoning)
* [CISA Advisory: Securing Data for AI Systems](https://www.cisa.gov/news-events/cybersecurity-advisories/aa25-142a)
* [ISO/IEC 23053: AI Management Systems Framework](https://www.iso.org/sectors/it-technologies/ai)
* [IBM: What is AI Governance?](https://www.ibm.com/think/topics/ai-governance)
* [Google AI Principles](https://ai.google/principles/)
* [GDPR & AI Training Data – DataProtectionReport](https://www.dataprotectionreport.com/2024/08/recent-regulatory-developments-in-training-artificial-intelligence-ai-models-under-the-gdpr/)
* [Supply-Chain Security for AI Data – AppSOC](https://www.appsoc.com/blog/ai-is-the-new-frontier-of-supply-chain-security)
* [OpenAI Privacy Center – Data Deletion Controls](https://privacy.openai.com/policies?modal=take-control)
* [Adversarial ML Dataset – Kaggle](https://www.kaggle.com/datasets/cnrieiit/adversarial-machine-learning-dataset)

