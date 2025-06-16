# Pengurusan Data Latihan C1 & Pengurusan Bias

## Objektif Kawalan

Data latihan mesti diperoleh, diurus, dan diselenggara dengan cara yang mengekalkan asal usul, keselamatan, kualiti, dan keadilan. Melakukan demikian memenuhi tanggungjawab undang-undang dan mengurangkan risiko berat sebelah, pencemaran, atau pelanggaran privasi sepanjang kitaran hayat AI.

---

## C1.1 Asal Usul Data Latihan

Kekalkan inventori yang boleh disahkan bagi semua set data, terima hanya sumber yang dipercayai, dan rekod setiap perubahan untuk keupayaan audit.

|   #   | Description                                                                                                                                                                                                                                | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 1.1.1 | Sahkan bahawa inventori terkini bagi setiap sumber data latihan (asal, penjaga/pemilik, lesen, kaedah pengumpulan, kekangan penggunaan yang dimaksudkan, dan sejarah pemprosesan) dikekalkan.                                              |   1   | D/V  |
| 1.1.2 | Sahkan bahawa hanya set data yang disemak untuk kualiti, keterwakilan, punca etika, dan kepatuhan lesen dibenarkan, mengurangkan risiko pencemaran data, bias tersirat, dan pelanggaran harta intelek.                                     |   1   | D/V  |
| 1.1.3 | Sahkan bahawa peminimuman data dikuatkuasakan supaya atribut yang tidak perlu atau sensitif dikecualikan.                                                                                                                                  |   1   | D/V  |
| 1.1.4 | Sahkan bahawa semua perubahan dataset tertakluk kepada aliran kerja kelulusan yang dicatat.                                                                                                                                                |   2   | D/V  |
| 1.1.5 | Sahkan bahawa kualiti pelabelan/anotasi dijamin melalui semakan silang oleh penilai atau konsensus.                                                                                                                                        |   2   | D/V  |
| 1.1.6 | Sahkan bahawa "kad data" atau "lembaran data untuk set data" dikekalkan untuk set data latihan yang penting, yang menerangkan ciri-ciri, motivasi, komposisi, proses pengumpulan, pra-pemprosesan, serta kegunaan yang disyorkan/dilarang. |   2   | D/V  |

---

## C1.2 Keselamatan dan Integriti Data Latihan

Hadkan akses, enkripsi semasa disimpan dan semasa penghantaran, dan sahkan integriti untuk menghalang pengubahsuaian atau kecurian.

|   #   | Description                                                                                                                                                                                                                                                                                                                   | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.2.1 | Sahkan bahawa kawalan akses melindungi storan dan saluran pengaliran.                                                                                                                                                                                                                                                         |   1   | D/V  |
| 1.2.2 | Sahkan bahawa set data disulitkan semasa penghantaran dan, untuk semua maklumat sensitif atau yang boleh dikenal pasti secara peribadi (PII), semasa penyimpanan, dengan menggunakan algoritma kriptografi standard industri dan amalan pengurusan kekunci.                                                                   |   2   | D/V  |
| 1.2.3 | Sahkan bahawa hash kriptografi atau tandatangan digital digunakan untuk memastikan integriti data semasa penyimpanan dan pemindahan, dan bahawa teknik pengesanan anomali automatik digunakan untuk melindungi daripada pengubahsuaian atau kerosakan yang tidak dibenarkan, termasuk cubaan pencemaran data yang disasarkan. |   2   | D/V  |
| 1.2.4 | Sahkan bahawa versi set data dipantau untuk membolehkan pemulihan semula.                                                                                                                                                                                                                                                     |   3   | D/V  |
| 1.2.5 | Sahkan bahawa data lapuk dibersihkan dengan selamat atau dianonimkan mengikut polisi pengekalan data, keperluan peraturan, dan untuk mengurangkan permukaan serangan.                                                                                                                                                         |   2   | D/V  |

---

## C1.3 Kesempurnaan & Keadilan Perwakilan

Mengesan ketidakseimbangan demografi dan melaksanakan langkah mitigasi supaya kadar ralat model adalah setara di kalangan kumpulan.

|   #   | Description                                                                                                                                                                                                                                                                                                                                                                           | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.3.1 | Sahkan bahawa set data telah dianalisis untuk ketidakseimbangan perwakilan dan potensi bias merentas atribut yang dilindungi oleh undang-undang (contoh: kaum, jantina, umur) serta ciri-ciri sensitif dari segi etika yang lain yang berkaitan dengan bidang aplikasi model tersebut (contoh: status sosio-ekonomi, lokasi).                                                         |   1   | D/V  |
| 1.3.2 | Sahkan bahawa bias yang dikenalpasti telah diatasi melalui strategi yang didokumentasikan seperti penyesuaian semula imbangan, peningkatan data bersasarkan sasaran, penyesuaian algoritma (contoh: teknik pra-pemprosesan, pemprosesan dalam, pasca-pemprosesan), atau penyesuaian semula pemberatan, serta kesan mitigasi terhadap keadilan dan prestasi keseluruhan model dinilai. |   2   | D/V  |
| 1.3.3 | Sahkan bahawa metrik keadilan selepas latihan telah dinilai dan didokumentasikan.                                                                                                                                                                                                                                                                                                     |   2   | D/V  |
| 1.3.4 | Sahkan bahawa polisi pengurusan bias kitaran hayat menetapkan pemilik dan kekerapan semakan.                                                                                                                                                                                                                                                                                          |   3   | D/V  |

---

## C1.4 Kualiti, Integriti, dan Keselamatan Pelabelan Data Latihan

Lindungi label dengan penyulitan dan perlukan semakan berganda untuk kelas kritikal.

|   #   | Description                                                                                                                                                                                                                                              | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.4.1 | Sahkan bahawa kualiti pelabelan/penandaan dijamin melalui garis panduan yang jelas, semakan silang oleh penilai, mekanisme konsensus (contohnya, pemantauan persetujuan antara penanda), dan proses yang ditetapkan untuk menyelesaikan pertikaian.      |   2   | D/V  |
| 1.4.2 | Sahkan bahawa hash kriptografi atau tandatangan digital digunakan pada artifak label untuk memastikan integriti dan keasliannya.                                                                                                                         |   2   | D/V  |
| 1.4.3 | Sahkan bahawa antara muka dan platform pelabelan menguatkuasakan kawalan akses yang kukuh, mengekalkan log audit yang bukti pengubahsuaian bagi semua aktiviti pelabelan, dan melindungi terhadap pengubahsuaian tanpa kebenaran.                        |   2   | D/V  |
| 1.4.4 | Sahkan bahawa label yang kritikal kepada keselamatan, sekuriti, atau keadilan (contohnya, mengenal pasti kandungan toksik, penemuan perubatan kritikal) menerima semakan berganda bebas wajib atau pengesahan kukuh yang setara.                         |   3   | D/V  |
| 1.4.5 | Sahkan bahawa maklumat sensitif (termasuk PII) yang secara tidak sengaja ditangkap atau semestinya hadir dalam label telah disekat, dipseudonimkan, dianonimkan, atau disulitkan semasa penyimpanan dan penghantaran, mengikut prinsip pengurangan data. |   2   | D/V  |
| 1.4.6 | Sahkan bahawa panduan pelabelan dan arahan adalah komprehensif, terkawal versi, dan disemak oleh rakan sebaya.                                                                                                                                           |   2   | D/V  |
| 1.4.7 | Sahkan bahawa skema data (termasuk untuk label) ditakrifkan dengan jelas, dan dikawal versi.                                                                                                                                                             |   2   | D/V  |
| 1.8.2 | Sahkan bahawa aliran kerja pelabelan yang dialih keluar atau dikumpulkan secara ramai mempunyai langkah-langkah keselamatan teknikal/prosedural untuk memastikan kerahsiaan data, integriti, kualiti label, dan mengelakkan kebocoran data.              |   2   | D/V  |

---

## C1.5 Jaminan Kualiti Data Latihan

Gabungkan pengesahan automatik, pemeriksaan manual secara rawak, dan pembaikan yang direkodkan untuk menjamin kebolehpercayaan set data.

|   #   | Description                                                                                                                                                                                                                                                                                           | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.5.1 | Sahkan bahawa ujian automatik mengesan ralat format, nilai null, dan ketidaksejajaran label pada setiap pemprosesan data atau transformasi yang signifikan.                                                                                                                                           |   1   |  D   |
| 1.5.2 | Sahkan bahawa set data yang gagal dikarantin dengan jejak audit.                                                                                                                                                                                                                                      |   1   | D/V  |
| 1.5.3 | Sahkan bahawa pemeriksaan spot manual oleh pakar domain merangkumi sampel yang signifikan secara statistik (contohnya, ≥1% atau 1,000 sampel, mana-mana yang lebih besar, atau sebagaimana ditentukan oleh penilaian risiko) untuk mengenal pasti isu kualiti halus yang tidak dikesan oleh automasi. |   2   |  V   |
| 1.5.4 | Sahkan bahawa langkah-langkah pembetulan ditambahkan ke rekod provokasi.                                                                                                                                                                                                                              |   2   | D/V  |
| 1.5.5 | Sahkan bahawa pintu kualiti menyekat set data yang kurang memuaskan kecuali pengecualian diluluskan.                                                                                                                                                                                                  |   2   | D/V  |

---

## C1.6 Pengesanan Peracunan Data

Terapkan pengesanan anomali statistik dan aliran kerja kuarantin untuk menghentikan penyisipan musuh.

|   #   | Description                                                                                                                                                                                                                                                                                | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 1.6.1 | Sahkan bahawa teknik pengesanan anomali (contohnya, kaedah statistik, pengesanan outlier, analisis embedding) digunakan pada data latihan semasa pengambilan dan sebelum latihan utama dijalankan untuk mengenal pasti potensi serangan pencemaran atau kerosakan data yang tidak sengaja. |   2   | D/V  |
| 1.6.2 | Sahkan bahawa sampel yang ditandakan mencetuskan semakan manual sebelum latihan.                                                                                                                                                                                                           |   2   | D/V  |
| 1.6.3 | Sahkan bahawa keputusan memberi maklumat kepada dosier keselamatan model dan memaklumkan perisikan ancaman yang sedang berlangsung.                                                                                                                                                        |   2   |  V   |
| 1.6.4 | Sahkan bahawa logik pengesanan dikemas kini dengan maklumat ancaman baru.                                                                                                                                                                                                                  |   3   | D/V  |
| 1.6.5 | Sahkan bahawa rangkaian pembelajaran dalam talian memantau pergeseran taburan.                                                                                                                                                                                                             |   3   | D/V  |
| 1.6.6 | Sahkan bahawa pertahanan khusus terhadap jenis serangan pencemaran data yang diketahui (contohnya, pembalikan label, penyisipan pencetus pintu belakang, serangan contoh berpengaruh) telah dipertimbangkan dan dilaksanakan berdasarkan profil risiko sistem dan sumber data.             |   3   | D/V  |

---

## C1.7 Pemadaman Data Pengguna & Penguatkuasaan Persetujuan

Hormati permintaan pemadaman dan penarikan persetujuan merentasi set data, sandaran, dan artifak terbitan.

|   #   | Description                                                                                                                                                                                                                                                                                                   | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.7.1 | Sahkan bahawa aliran kerja pemadaman membersihkan data utama dan data terbitan serta menilai impak model, dan bahawa impak terhadap model yang terjejas dinilai dan, jika perlu, ditangani (contohnya, melalui latihan semula atau penyesuaian semula).                                                       |   1   | D/V  |
| 1.7.2 | Sahkan bahawa mekanisme telah disediakan untuk menjejak dan menghormati skop serta status persetujuan pengguna (dan penarikan balik) untuk data yang digunakan dalam latihan, serta persetujuan tersebut disahkan sebelum data dimasukkan ke dalam proses latihan baru atau kemas kini model yang signifikan. |   2   |  D   |
| 1.7.3 | Sahkan bahawa aliran kerja diuji setiap tahun dan direkodkan.                                                                                                                                                                                                                                                 |   2   |  V   |

---

## C1.8 Keselamatan Rantaian Bekalan

Sahkan penyedia data luaran dan pastikan integriti melalui saluran yang diautentikasi dan disulitkan.

|   #   | Description                                                                                                                                                                                                                                                                                                                                                                | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.8.1 | Sahkan bahawa pembekal data pihak ketiga, termasuk penyedia model yang telah dilatih dan set data luaran, menjalani pemeriksaan wajar dari segi keselamatan, privasi, sumber etika, dan kualiti data sebelum data atau model mereka disepadukan.                                                                                                                           |   2   | D/V  |
| 1.8.2 | Sahkan bahawa pemindahan luaran menggunakan TLS/pengesahan dan pemeriksaan integriti.                                                                                                                                                                                                                                                                                      |   1   |  D   |
| 1.8.3 | Sahkan bahawa sumber data berisiko tinggi (contohnya, set data sumber terbuka dengan asal-usul tidak diketahui, pembekal yang tidak disemak) menerima pemeriksaan yang dipertingkatkan, seperti analisis dalam persekitaran terasing, pemeriksaan kualiti/berat sebelah yang meluas, dan pengesanan pencemaran yang disasarkan, sebelum digunakan dalam aplikasi sensitif. |   2   | D/V  |
| 1.8.4 | Sahkan bahawa model pra-latih yang diperoleh daripada pihak ketiga dinilai untuk kecenderungan terbenam, potensi pintu belakang, integriti seni bina mereka, dan asal-usul data latihan asal mereka sebelum penalaan halus atau penggunaan.                                                                                                                                |   3   | D/V  |

---

## C1.9 Pengesanan Sampel Adversarial

Melaksanakan langkah-langkah semasa fasa latihan, seperti latihan bertentangan, untuk meningkatkan ketahanan model terhadap contoh bertentangan.

|   #   | Description                                                                                                                                                                                                                                                                          | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 1.9.1 | Sahkan bahawa pertahanan yang sesuai, seperti latihan adversarial (menggunakan contoh adversarial yang dijana), penggandaan data dengan input yang terganggu, atau teknik pengoptimuman kukuh, dilaksanakan dan disesuaikan untuk model yang berkaitan berdasarkan penilaian risiko. |   3   | D/V  |
| 1.9.2 | Sahkan bahawa jika latihan adversarial digunakan, penjanaan, pengurusan, dan penversian set data adversarial didokumentasikan dan dikawal.                                                                                                                                           |   2   | D/V  |
| 1.9.3 | Sahkan bahawa impak latihan ketahanan adversarial terhadap prestasi model (terhadap kedua-dua input bersih dan adversarial) serta metrik keadilan dinilai, didokumenkan, dan dipantau.                                                                                               |   3   | D/V  |
| 1.9.4 | Sahkan bahawa strategi untuk latihan adversarial dan ketahanan dikaji semula dan dikemas kini secara berkala untuk menangani teknik serangan adversarial yang berkembang.                                                                                                            |   3   | D/V  |

---

## C1.10 Penelusuran dan Keterlacakan Data

Jejaki perjalanan penuh setiap titik data dari sumber ke input model untuk kebolehperiksa dan tindak balas insiden.

|   #    | Description                                                                                                                           | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.10.1 | Sahkan bahawa keturunan setiap titik data, termasuk semua transformasi, augmentasi, dan gabungan, direkodkan dan boleh dibina semula. |   2   | D/V  |
| 1.10.2 | Sahkan bahawa rekod keturunan tidak boleh diubah, disimpan dengan selamat, dan boleh diakses untuk audit atau siasatan.               |   2   | D/V  |
| 1.10.3 | Sahkan bahawa penjejakan keturunan merangkumi kedua-dua data mentah dan data sintetik.                                                |   2   | D/V  |

---

## C1.11 Pengurusan Data Sintetik

Pastikan data sintetik diurus dengan betul, dilabelkan, dan dinilai risikonya.

|   #    | Description                                                                                                                                       | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.11.1 | Sahkan bahawa semua data sintetik dilabel dengan jelas dan boleh dibezakan daripada data sebenar sepanjang saluran data.                          |   2   | D/V  |
| 1.11.2 | Sahkan bahawa proses penjanaan, parameter, dan kegunaan yang dimaksudkan bagi data sintetik telah didokumentasikan.                               |   2   | D/V  |
| 1.11.3 | Sahkan bahawa data sintetik telah dinilai risikonya untuk berat sebelah, kebocoran privasi, dan isu representasi sebelum digunakan dalam latihan. |   2   | D/V  |

---

## C1.12 Pemantauan Akses Data & Pengesanan Anomali

Pantau dan beri amaran mengenai akses luar biasa kepada data latihan untuk mengesan ancaman dalaman atau pencerobohan data.

|   #    | Description                                                                                                               | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.12.1 | Sahkan bahawa semua akses kepada data latihan direkodkan, termasuk pengguna, masa, dan tindakan.                          |   2   | D/V  |
| 1.12.2 | Sahkan bahawa log akses disemak secara berkala untuk corak luar biasa, seperti eksport besar atau akses dari lokasi baru. |   2   | D/V  |
| 1.12.3 | Sahkan bahawa amaran dijana untuk acara akses yang mencurigakan dan disiasat dengan segera.                               |   2   | D/V  |

---

## C1.13 Polisi Penahanan & Tamat Tempoh Data

Tentukan dan laksanakan tempoh penyimpanan data untuk mengurangkan penyimpanan data yang tidak perlu.

|   #    | Description                                                                                                                      | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.13.1 | Sahkan bahawa tempoh pengekalan eksplisit ditetapkan untuk semua set data latihan.                                               |   1   | D/V  |
| 1.13.2 | Sahkan bahawa set data secara automatik tamat tempoh, dipadamkan, atau disemak untuk dipadamkan pada akhir kitaran hayat mereka. |   2   | D/V  |
| 1.13.3 | Sahkan bahawa tindakan pengekalan dan pemadaman direkod dan boleh diaudit.                                                       |   2   | D/V  |

---

## C1.14 Pematuhan Peraturan & Bidang Kuasa

Pastikan semua data latihan mematuhi undang-undang dan peraturan yang berkuat kuasa.

|   #    | Description                                                                                                                              | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.14.1 | Sahkan bahawa keperluan kediaman data dan pemindahan rentas sempadan dikenalpasti dan dikuatkuasakan untuk semua set data.               |   2   | D/V  |
| 1.14.2 | Sahkan bahawa peraturan khusus sektor (contohnya, penjagaan kesihatan, kewangan) dikenalpasti dan ditangani dalam pengendalian data.     |   2   | D/V  |
| 1.14.3 | Sahkan bahawa pematuhan dengan undang-undang privasi yang berkaitan (contohnya, GDPR, CCPA) didokumentasikan dan disemak secara berkala. |   2   | D/V  |

---

## C1.15 Penandaan Air Data & Penjejakan Cap Jari

Mengesan penggunaan semula tanpa kebenaran atau kebocoran data proprietari atau sensitif.

|   #    | Description                                                                                                                  | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.15.1 | Sahkan bahawa set data atau subset telah ditanda air atau dicap jari di mana boleh dilakukan.                                |   3   | D/V  |
| 1.15.2 | Sahkan bahawa kaedah penandaan air/cap jari tidak memperkenalkan bias atau risiko privasi.                                   |   3   | D/V  |
| 1.15.3 | Sahkan bahawa pemeriksaan berkala dilakukan untuk mengesan penggunaan semula tanpa kebenaran atau kebocoran data berwmakana. |   3   | D/V  |

---

## C1.16 Pengurusan Hak Subjek Data

Menyokong hak subjek data seperti akses, pembetulan, sekatan, dan bantahan.

|   #    | Description                                                                                                            | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.16.1 | Sahkan bahawa mekanisme wujud untuk menanggapi permintaan subjek data untuk akses, pembetulan, sekatan, atau bantahan. |   2   | D/V  |
| 1.16.2 | Sahkan bahawa permintaan direkod, dikesan, dan dipenuhi dalam tempoh masa yang ditetapkan secara undang-undang.        |   2   | D/V  |
| 1.16.3 | Sahkan bahawa proses hak subjek data diuji dan dikaji semula secara berkala untuk keberkesanannya.                     |   2   | D/V  |

---

## C1.17 Analisis Impak Versi Set Data

Nilailah kesan perubahan set data sebelum mengemas kini atau menggantikan versi.

|   #    | Description                                                                                                                                        | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.17.1 | Sahkan bahawa analisis impak dilakukan sebelum mengemas kini atau menggantikan versi set data, merangkumi prestasi model, keadilan, dan pematuhan. |   2   | D/V  |
| 1.17.2 | Sahkan bahawa hasil analisis impak didokumentasikan dan disemak oleh pihak berkepentingan yang relevan.                                            |   2   | D/V  |
| 1.17.3 | Sahkan bahawa pelan pemulangan wujud sekiranya versi baru memperkenalkan risiko yang tidak boleh diterima atau kemunduran.                         |   2   | D/V  |

---

## C1.18 Keselamatan Tenaga Kerja Anotasi Data

Pastikan keselamatan dan integriti kakitangan yang terlibat dalam anotasi data.

|   #    | Description                                                                                                                                         | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.18.1 | Sahkan bahawa semua kakitangan yang terlibat dalam anotasi data telah disemak latar belakang mereka dan dilatih dalam keselamatan dan privasi data. |   2   | D/V  |
| 1.18.2 | Sahkan bahawa semua kakitangan anotasi menandatangani perjanjian kerahsiaan dan bukan pendedahan.                                                   |   2   | D/V  |
| 1.18.3 | Sahkan bahawa platform anotasi menguatkuasakan kawalan akses dan memantau ancaman dalaman.                                                          |   2   | D/V  |

---

## Rujukan

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

