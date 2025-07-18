## Halaman Depan

### Mengenai Standard

Standard Verifikasi Keselamatan Kecerdasan Buatan (AISVS) adalah katalog keperluan keselamatan yang dipacu oleh komuniti yang boleh digunakan oleh saintis data, jurutera MLOps, arkitek perisian, pembangun, penguji, profesional keselamatan, vendor alat, pengawal selia, dan pengguna untuk mereka bentuk, membina, menguji, dan mengesahkan sistem dan aplikasi yang diaktifkan AI yang boleh dipercayai. Ia menyediakan bahasa umum untuk menentukan kawalan keselamatan merentasi kitaran hayat AI—dari pengumpulan data dan pembangunan model hingga penyebaran dan pemantauan berterusan—supaya organisasi dapat mengukur dan memperbaiki ketahanan, privasi, dan keselamatan penyelesaian AI mereka.

### Hak Cipta dan Lesen

Versi 0.1 (Draf Awam Pertama - Sedang Dalam Proses), 2025  

![license](images/license.png)
Hak Cipta © 2025 Projek AISVS.  

Dikeluarkan di bawahCreative Commons Attribution‑ShareAlike 4.0 International License.
Untuk sebarang penggunaan semula atau pengedaran, anda mesti dengan jelas menyampaikan terma lesen karya ini kepada orang lain.

### Ketua Projek

Jim Manico
Aras “Russ” Memisyazici

### Penyumbang dan Penilai

https://github.com/ottosulin
https://github.com/mbhatt1
https://github.com/vineethsai
https://github.com/cciprofm
https://github.com/deepakrpandey12


---

AISVS adalah standard baharu yang dicipta khusus untuk menangani cabaran keselamatan unik sistem kecerdasan buatan. Walaupun ia mengambil inspirasi daripada amalan terbaik keselamatan yang lebih luas, setiap keperluan dalam AISVS telah dibangunkan dari asas bagi mencerminkan landskap ancaman AI dan membantu organisasi membina penyelesaian AI yang lebih selamat dan tahan lasak.

## Pendahuluan

Selamat datang ke Standard Pengesahan Keselamatan Kecerdasan Buatan (AISVS) versi 1.0!

### Pengenalan

Ditubuhkan pada tahun 2025 melalui usaha komuniti kolaboratif, AISVS menetapkan keperluan keselamatan yang perlu dipertimbangkan apabila mereka bentuk, membangunkan, melaksanakan, dan mengendalikan model AI moden, saluran pemprosesan, dan perkhidmatan yang didayakan AI.

AISVS v1.0 mewakili hasil gabungan kerja ketua projeknya, kumpulan kerja, dan penyumbang komuniti yang lebih luas untuk menghasilkan asas yang pragmatik dan boleh diuji bagi melindungi sistem AI.

Matlamat kami dengan pelepasan ini adalah untuk menjadikan AISVS mudah diterima sambil mengekalkan fokus yang tajam pada skop yang telah ditetapkan dan menangani landskap risiko yang berkembang pesat yang unik kepada AI.

### Objektif Utama untuk AISVS Versi 1.0

Versi 1.0 akan dibuat dengan beberapa prinsip panduan.

#### Skop Yang Terperinci

Setiap keperluan mesti selaras dengan nama dan misi AISVS:

Kecerdasan Buatan – Kawalan beroperasi pada lapisan AI/ML (data, model, saluran, atau inferens) dan merupakan tanggungjawab pengamal AI.
Keselamatan – Keperluan secara langsung mengurangkan risiko keselamatan, privasi, atau keselamatan yang dikenal pasti.
Pengesahan – Bahasa ditulis supaya pematuhan dapat disahkan secara objektif.
Standard – Seksyen mengikuti struktur dan terminologi yang konsisten untuk membentuk rujukan yang koheren.
​
---

Dengan mengikuti AISVS, organisasi dapat secara sistematik menilai dan menguatkan postur keselamatan penyelesaian AI mereka, sambil memupuk budaya kejuruteraan AI yang selamat.

## Menggunakan AISVS

Standard Pengesahan Keselamatan Kecerdasan Buatan (AISVS) mentakrifkan keperluan keselamatan untuk aplikasi dan perkhidmatan AI moden, dengan fokus pada aspek yang berada dalam kawalan pemaju aplikasi.

AISVS ditujukan untuk sesiapa sahaja yang membangunkan atau menilai keselamatan aplikasi AI, termasuk pembangun, arkitek, jurutera keselamatan, dan juruaudit. Bab ini memperkenalkan struktur dan penggunaan AISVS, termasuk tahap pengesahannya dan kes penggunaan yang dimaksudkan.

### Tahap Pengesahan Keselamatan Kecerdasan Buatan

AISVS mentakrifkan tiga tahap peningkatan pengesahan keselamatan. Setiap tahap menambah kedalaman dan kerumitan, membolehkan organisasi menyesuaikan sikap keselamatan mereka mengikut tahap risiko sistem AI mereka.

Organisasi boleh memulakan pada Tahap 1 dan secara berperingkat mengamalkan tahap yang lebih tinggi apabila kematangan keselamatan dan pendedahan ancaman meningkat.

#### Definisi Tahap-Tahap

Setiap keperluan dalam AISVS v1.0 diberi kepada salah satu daripada tahap berikut:

 Keperluan Tahap 1

Tahap 1 merangkumi keperluan keselamatan yang paling kritikal dan asas. Ia menumpukan pada pencegahan serangan biasa yang tidak bergantung pada prasyarat atau kelemahan lain. Kebanyakan kawalan Tahap 1 sama ada mudah untuk dilaksanakan atau cukup penting untuk membenarkan usaha tersebut.

 Keperluan Tahap 2

Tahap 2 menangani serangan yang lebih maju atau kurang biasa, serta pertahanan berlapis terhadap ancaman yang meluas. Keperluan ini mungkin melibatkan logik yang lebih kompleks atau menyasarkan prasyarat serangan tertentu.

 Keperluan Tahap 3

Tahap 3 merangkumi kawalan yang biasanya lebih sukar untuk dilaksanakan atau bergantung pada situasi untuk diterapkan. Ini sering mewakili mekanisme pertahanan berlapis atau mitigasi terhadap serangan khusus, tersasar, atau berkompleksiti tinggi.

#### Peranan (D/V)

Setiap keperluan AISVS ditandakan mengikut penonton utama:

D – Keperluan fokus kepada Pembangun
V – Keperluan yang berfokus kepada pemeriksa/pengawas
D/V – Berkaitan dengan kedua-dua pembangun dan pemeriksa

## Pengurusan Data Latihan C1 & Pengurusan Bias

### Objektif Kawalan

Data latihan mesti diperoleh, diurus, dan diselenggara dengan cara yang mengekalkan asal usul, keselamatan, kualiti, dan keadilan. Melakukan demikian memenuhi tanggungjawab undang-undang dan mengurangkan risiko berat sebelah, pencemaran, atau pelanggaran privasi sepanjang kitaran hayat AI.

---

### C1.1 Asal Usul Data Latihan

Kekalkan inventori yang boleh disahkan bagi semua set data, terima hanya sumber yang dipercayai, dan rekod setiap perubahan untuk keupayaan audit.

 #1.1.1    Level: 1    Role: D/V
 Sahkan bahawa inventori terkini bagi setiap sumber data latihan (asal, penjaga/pemilik, lesen, kaedah pengumpulan, kekangan penggunaan yang dimaksudkan, dan sejarah pemprosesan) dikekalkan.
 #1.1.2    Level: 1    Role: D/V
 Sahkan bahawa hanya set data yang disemak untuk kualiti, keterwakilan, punca etika, dan kepatuhan lesen dibenarkan, mengurangkan risiko pencemaran data, bias tersirat, dan pelanggaran harta intelek.
 #1.1.3    Level: 1    Role: D/V
 Sahkan bahawa peminimuman data dikuatkuasakan supaya atribut yang tidak perlu atau sensitif dikecualikan.
 #1.1.4    Level: 2    Role: D/V
 Sahkan bahawa semua perubahan dataset tertakluk kepada aliran kerja kelulusan yang dicatat.
 #1.1.5    Level: 2    Role: D/V
 Sahkan bahawa kualiti pelabelan/anotasi dijamin melalui semakan silang oleh penilai atau konsensus.
 #1.1.6    Level: 2    Role: D/V
 Sahkan bahawa "kad data" atau "lembaran data untuk set data" dikekalkan untuk set data latihan yang penting, yang menerangkan ciri-ciri, motivasi, komposisi, proses pengumpulan, pra-pemprosesan, serta kegunaan yang disyorkan/dilarang.

---

### C1.2 Keselamatan dan Integriti Data Latihan

Hadkan akses, enkripsi semasa disimpan dan semasa penghantaran, dan sahkan integriti untuk menghalang pengubahsuaian atau kecurian.

 #1.2.1    Level: 1    Role: D/V
 Sahkan bahawa kawalan akses melindungi storan dan saluran pengaliran.
 #1.2.2    Level: 2    Role: D/V
 Sahkan bahawa set data disulitkan semasa penghantaran dan, untuk semua maklumat sensitif atau yang boleh dikenal pasti secara peribadi (PII), semasa penyimpanan, dengan menggunakan algoritma kriptografi standard industri dan amalan pengurusan kekunci.
 #1.2.3    Level: 2    Role: D/V
 Sahkan bahawa hash kriptografi atau tandatangan digital digunakan untuk memastikan integriti data semasa penyimpanan dan pemindahan, dan bahawa teknik pengesanan anomali automatik digunakan untuk melindungi daripada pengubahsuaian atau kerosakan yang tidak dibenarkan, termasuk cubaan pencemaran data yang disasarkan.
 #1.2.4    Level: 3    Role: D/V
 Sahkan bahawa versi set data dipantau untuk membolehkan pemulihan semula.
 #1.2.5    Level: 2    Role: D/V
 Sahkan bahawa data lapuk dibersihkan dengan selamat atau dianonimkan mengikut polisi pengekalan data, keperluan peraturan, dan untuk mengurangkan permukaan serangan.

---

### C1.3 Kesempurnaan & Keadilan Perwakilan

Mengesan ketidakseimbangan demografi dan melaksanakan langkah mitigasi supaya kadar ralat model adalah setara di kalangan kumpulan.

 #1.3.1    Level: 1    Role: D/V
 Sahkan bahawa set data telah dianalisis untuk ketidakseimbangan perwakilan dan potensi bias merentas atribut yang dilindungi oleh undang-undang (contoh: kaum, jantina, umur) serta ciri-ciri sensitif dari segi etika yang lain yang berkaitan dengan bidang aplikasi model tersebut (contoh: status sosio-ekonomi, lokasi).
 #1.3.2    Level: 2    Role: D/V
 Sahkan bahawa bias yang dikenalpasti telah diatasi melalui strategi yang didokumentasikan seperti penyesuaian semula imbangan, peningkatan data bersasarkan sasaran, penyesuaian algoritma (contoh: teknik pra-pemprosesan, pemprosesan dalam, pasca-pemprosesan), atau penyesuaian semula pemberatan, serta kesan mitigasi terhadap keadilan dan prestasi keseluruhan model dinilai.
 #1.3.3    Level: 2    Role: D/V
 Sahkan bahawa metrik keadilan selepas latihan telah dinilai dan didokumentasikan.
 #1.3.4    Level: 3    Role: D/V
 Sahkan bahawa polisi pengurusan bias kitaran hayat menetapkan pemilik dan kekerapan semakan.

---

### C1.4 Kualiti, Integriti, dan Keselamatan Pelabelan Data Latihan

Lindungi label dengan penyulitan dan perlukan semakan berganda untuk kelas kritikal.

 #1.4.1    Level: 2    Role: D/V
 Sahkan bahawa kualiti pelabelan/penandaan dijamin melalui garis panduan yang jelas, semakan silang oleh penilai, mekanisme konsensus (contohnya, pemantauan persetujuan antara penanda), dan proses yang ditetapkan untuk menyelesaikan pertikaian.
 #1.4.2    Level: 2    Role: D/V
 Sahkan bahawa hash kriptografi atau tandatangan digital digunakan pada artifak label untuk memastikan integriti dan keasliannya.
 #1.4.3    Level: 2    Role: D/V
 Sahkan bahawa antara muka dan platform pelabelan menguatkuasakan kawalan akses yang kukuh, mengekalkan log audit yang bukti pengubahsuaian bagi semua aktiviti pelabelan, dan melindungi terhadap pengubahsuaian tanpa kebenaran.
 #1.4.4    Level: 3    Role: D/V
 Sahkan bahawa label yang kritikal kepada keselamatan, sekuriti, atau keadilan (contohnya, mengenal pasti kandungan toksik, penemuan perubatan kritikal) menerima semakan berganda bebas wajib atau pengesahan kukuh yang setara.
 #1.4.5    Level: 2    Role: D/V
 Sahkan bahawa maklumat sensitif (termasuk PII) yang secara tidak sengaja ditangkap atau semestinya hadir dalam label telah disekat, dipseudonimkan, dianonimkan, atau disulitkan semasa penyimpanan dan penghantaran, mengikut prinsip pengurangan data.
 #1.4.6    Level: 2    Role: D/V
 Sahkan bahawa panduan pelabelan dan arahan adalah komprehensif, terkawal versi, dan disemak oleh rakan sebaya.
 #1.4.7    Level: 2    Role: D/V
 Sahkan bahawa skema data (termasuk untuk label) ditakrifkan dengan jelas, dan dikawal versi.
 #1.8.2    Level: 2    Role: D/V
 Sahkan bahawa aliran kerja pelabelan yang dialih keluar atau dikumpulkan secara ramai mempunyai langkah-langkah keselamatan teknikal/prosedural untuk memastikan kerahsiaan data, integriti, kualiti label, dan mengelakkan kebocoran data.

---

### C1.5 Jaminan Kualiti Data Latihan

Gabungkan pengesahan automatik, pemeriksaan manual secara rawak, dan pembaikan yang direkodkan untuk menjamin kebolehpercayaan set data.

 #1.5.1    Level: 1    Role: D
 Sahkan bahawa ujian automatik mengesan ralat format, nilai null, dan ketidaksejajaran label pada setiap pemprosesan data atau transformasi yang signifikan.
 #1.5.2    Level: 1    Role: D/V
 Sahkan bahawa set data yang gagal dikarantin dengan jejak audit.
 #1.5.3    Level: 2    Role: V
 Sahkan bahawa pemeriksaan spot manual oleh pakar domain merangkumi sampel yang signifikan secara statistik (contohnya, ≥1% atau 1,000 sampel, mana-mana yang lebih besar, atau sebagaimana ditentukan oleh penilaian risiko) untuk mengenal pasti isu kualiti halus yang tidak dikesan oleh automasi.
 #1.5.4    Level: 2    Role: D/V
 Sahkan bahawa langkah-langkah pembetulan ditambahkan ke rekod provokasi.
 #1.5.5    Level: 2    Role: D/V
 Sahkan bahawa pintu kualiti menyekat set data yang kurang memuaskan kecuali pengecualian diluluskan.

---

### C1.6 Pengesanan Peracunan Data

Terapkan pengesanan anomali statistik dan aliran kerja kuarantin untuk menghentikan penyisipan musuh.

 #1.6.1    Level: 2    Role: D/V
 Sahkan bahawa teknik pengesanan anomali (contohnya, kaedah statistik, pengesanan outlier, analisis embedding) digunakan pada data latihan semasa pengambilan dan sebelum latihan utama dijalankan untuk mengenal pasti potensi serangan pencemaran atau kerosakan data yang tidak sengaja.
 #1.6.2    Level: 2    Role: D/V
 Sahkan bahawa sampel yang ditandakan mencetuskan semakan manual sebelum latihan.
 #1.6.3    Level: 2    Role: V
 Sahkan bahawa keputusan memberi maklumat kepada dosier keselamatan model dan memaklumkan perisikan ancaman yang sedang berlangsung.
 #1.6.4    Level: 3    Role: D/V
 Sahkan bahawa logik pengesanan dikemas kini dengan maklumat ancaman baru.
 #1.6.5    Level: 3    Role: D/V
 Sahkan bahawa rangkaian pembelajaran dalam talian memantau pergeseran taburan.
 #1.6.6    Level: 3    Role: D/V
 Sahkan bahawa pertahanan khusus terhadap jenis serangan pencemaran data yang diketahui (contohnya, pembalikan label, penyisipan pencetus pintu belakang, serangan contoh berpengaruh) telah dipertimbangkan dan dilaksanakan berdasarkan profil risiko sistem dan sumber data.

---

### C1.7 Pemadaman Data Pengguna & Penguatkuasaan Persetujuan

Hormati permintaan pemadaman dan penarikan persetujuan merentasi set data, sandaran, dan artifak terbitan.

 #1.7.1    Level: 1    Role: D/V
 Sahkan bahawa aliran kerja pemadaman membersihkan data utama dan data terbitan serta menilai impak model, dan bahawa impak terhadap model yang terjejas dinilai dan, jika perlu, ditangani (contohnya, melalui latihan semula atau penyesuaian semula).
 #1.7.2    Level: 2    Role: D
 Sahkan bahawa mekanisme telah disediakan untuk menjejak dan menghormati skop serta status persetujuan pengguna (dan penarikan balik) untuk data yang digunakan dalam latihan, serta persetujuan tersebut disahkan sebelum data dimasukkan ke dalam proses latihan baru atau kemas kini model yang signifikan.
 #1.7.3    Level: 2    Role: V
 Sahkan bahawa aliran kerja diuji setiap tahun dan direkodkan.

---

### C1.8 Keselamatan Rantaian Bekalan

Sahkan penyedia data luaran dan pastikan integriti melalui saluran yang diautentikasi dan disulitkan.

 #1.8.1    Level: 2    Role: D/V
 Sahkan bahawa pembekal data pihak ketiga, termasuk penyedia model yang telah dilatih dan set data luaran, menjalani pemeriksaan wajar dari segi keselamatan, privasi, sumber etika, dan kualiti data sebelum data atau model mereka disepadukan.
 #1.8.2    Level: 1    Role: D
 Sahkan bahawa pemindahan luaran menggunakan TLS/pengesahan dan pemeriksaan integriti.
 #1.8.3    Level: 2    Role: D/V
 Sahkan bahawa sumber data berisiko tinggi (contohnya, set data sumber terbuka dengan asal-usul tidak diketahui, pembekal yang tidak disemak) menerima pemeriksaan yang dipertingkatkan, seperti analisis dalam persekitaran terasing, pemeriksaan kualiti/berat sebelah yang meluas, dan pengesanan pencemaran yang disasarkan, sebelum digunakan dalam aplikasi sensitif.
 #1.8.4    Level: 3    Role: D/V
 Sahkan bahawa model pra-latih yang diperoleh daripada pihak ketiga dinilai untuk kecenderungan terbenam, potensi pintu belakang, integriti seni bina mereka, dan asal-usul data latihan asal mereka sebelum penalaan halus atau penggunaan.

---

### C1.9 Pengesanan Sampel Adversarial

Melaksanakan langkah-langkah semasa fasa latihan, seperti latihan bertentangan, untuk meningkatkan ketahanan model terhadap contoh bertentangan.

 #1.9.1    Level: 3    Role: D/V
 Sahkan bahawa pertahanan yang sesuai, seperti latihan adversarial (menggunakan contoh adversarial yang dijana), penggandaan data dengan input yang terganggu, atau teknik pengoptimuman kukuh, dilaksanakan dan disesuaikan untuk model yang berkaitan berdasarkan penilaian risiko.
 #1.9.2    Level: 2    Role: D/V
 Sahkan bahawa jika latihan adversarial digunakan, penjanaan, pengurusan, dan penversian set data adversarial didokumentasikan dan dikawal.
 #1.9.3    Level: 3    Role: D/V
 Sahkan bahawa impak latihan ketahanan adversarial terhadap prestasi model (terhadap kedua-dua input bersih dan adversarial) serta metrik keadilan dinilai, didokumenkan, dan dipantau.
 #1.9.4    Level: 3    Role: D/V
 Sahkan bahawa strategi untuk latihan adversarial dan ketahanan dikaji semula dan dikemas kini secara berkala untuk menangani teknik serangan adversarial yang berkembang.

---

### C1.10 Penelusuran dan Keterlacakan Data

Jejaki perjalanan penuh setiap titik data dari sumber ke input model untuk kebolehperiksa dan tindak balas insiden.

 #1.10.1    Level: 2    Role: D/V
 Sahkan bahawa keturunan setiap titik data, termasuk semua transformasi, augmentasi, dan gabungan, direkodkan dan boleh dibina semula.
 #1.10.2    Level: 2    Role: D/V
 Sahkan bahawa rekod keturunan tidak boleh diubah, disimpan dengan selamat, dan boleh diakses untuk audit atau siasatan.
 #1.10.3    Level: 2    Role: D/V
 Sahkan bahawa penjejakan keturunan merangkumi kedua-dua data mentah dan data sintetik.

---

### C1.11 Pengurusan Data Sintetik

Pastikan data sintetik diurus dengan betul, dilabelkan, dan dinilai risikonya.

 #1.11.1    Level: 2    Role: D/V
 Sahkan bahawa semua data sintetik dilabel dengan jelas dan boleh dibezakan daripada data sebenar sepanjang saluran data.
 #1.11.2    Level: 2    Role: D/V
 Sahkan bahawa proses penjanaan, parameter, dan kegunaan yang dimaksudkan bagi data sintetik telah didokumentasikan.
 #1.11.3    Level: 2    Role: D/V
 Sahkan bahawa data sintetik telah dinilai risikonya untuk berat sebelah, kebocoran privasi, dan isu representasi sebelum digunakan dalam latihan.

---

### C1.12 Pemantauan Akses Data & Pengesanan Anomali

Pantau dan beri amaran mengenai akses luar biasa kepada data latihan untuk mengesan ancaman dalaman atau pencerobohan data.

 #1.12.1    Level: 2    Role: D/V
 Sahkan bahawa semua akses kepada data latihan direkodkan, termasuk pengguna, masa, dan tindakan.
 #1.12.2    Level: 2    Role: D/V
 Sahkan bahawa log akses disemak secara berkala untuk corak luar biasa, seperti eksport besar atau akses dari lokasi baru.
 #1.12.3    Level: 2    Role: D/V
 Sahkan bahawa amaran dijana untuk acara akses yang mencurigakan dan disiasat dengan segera.

---

### C1.13 Polisi Penahanan & Tamat Tempoh Data

Tentukan dan laksanakan tempoh penyimpanan data untuk mengurangkan penyimpanan data yang tidak perlu.

 #1.13.1    Level: 1    Role: D/V
 Sahkan bahawa tempoh pengekalan eksplisit ditetapkan untuk semua set data latihan.
 #1.13.2    Level: 2    Role: D/V
 Sahkan bahawa set data secara automatik tamat tempoh, dipadamkan, atau disemak untuk dipadamkan pada akhir kitaran hayat mereka.
 #1.13.3    Level: 2    Role: D/V
 Sahkan bahawa tindakan pengekalan dan pemadaman direkod dan boleh diaudit.

---

### C1.14 Pematuhan Peraturan & Bidang Kuasa

Pastikan semua data latihan mematuhi undang-undang dan peraturan yang berkuat kuasa.

 #1.14.1    Level: 2    Role: D/V
 Sahkan bahawa keperluan kediaman data dan pemindahan rentas sempadan dikenalpasti dan dikuatkuasakan untuk semua set data.
 #1.14.2    Level: 2    Role: D/V
 Sahkan bahawa peraturan khusus sektor (contohnya, penjagaan kesihatan, kewangan) dikenalpasti dan ditangani dalam pengendalian data.
 #1.14.3    Level: 2    Role: D/V
 Sahkan bahawa pematuhan dengan undang-undang privasi yang berkaitan (contohnya, GDPR, CCPA) didokumentasikan dan disemak secara berkala.

---

### C1.15 Penandaan Air Data & Penjejakan Cap Jari

Mengesan penggunaan semula tanpa kebenaran atau kebocoran data proprietari atau sensitif.

 #1.15.1    Level: 3    Role: D/V
 Sahkan bahawa set data atau subset telah ditanda air atau dicap jari di mana boleh dilakukan.
 #1.15.2    Level: 3    Role: D/V
 Sahkan bahawa kaedah penandaan air/cap jari tidak memperkenalkan bias atau risiko privasi.
 #1.15.3    Level: 3    Role: D/V
 Sahkan bahawa pemeriksaan berkala dilakukan untuk mengesan penggunaan semula tanpa kebenaran atau kebocoran data berwmakana.

---

### C1.16 Pengurusan Hak Subjek Data

Menyokong hak subjek data seperti akses, pembetulan, sekatan, dan bantahan.

 #1.16.1    Level: 2    Role: D/V
 Sahkan bahawa mekanisme wujud untuk menanggapi permintaan subjek data untuk akses, pembetulan, sekatan, atau bantahan.
 #1.16.2    Level: 2    Role: D/V
 Sahkan bahawa permintaan direkod, dikesan, dan dipenuhi dalam tempoh masa yang ditetapkan secara undang-undang.
 #1.16.3    Level: 2    Role: D/V
 Sahkan bahawa proses hak subjek data diuji dan dikaji semula secara berkala untuk keberkesanannya.

---

### C1.17 Analisis Impak Versi Set Data

Nilailah kesan perubahan set data sebelum mengemas kini atau menggantikan versi.

 #1.17.1    Level: 2    Role: D/V
 Sahkan bahawa analisis impak dilakukan sebelum mengemas kini atau menggantikan versi set data, merangkumi prestasi model, keadilan, dan pematuhan.
 #1.17.2    Level: 2    Role: D/V
 Sahkan bahawa hasil analisis impak didokumentasikan dan disemak oleh pihak berkepentingan yang relevan.
 #1.17.3    Level: 2    Role: D/V
 Sahkan bahawa pelan pemulangan wujud sekiranya versi baru memperkenalkan risiko yang tidak boleh diterima atau kemunduran.

---

### C1.18 Keselamatan Tenaga Kerja Anotasi Data

Pastikan keselamatan dan integriti kakitangan yang terlibat dalam anotasi data.

 #1.18.1    Level: 2    Role: D/V
 Sahkan bahawa semua kakitangan yang terlibat dalam anotasi data telah disemak latar belakang mereka dan dilatih dalam keselamatan dan privasi data.
 #1.18.2    Level: 2    Role: D/V
 Sahkan bahawa semua kakitangan anotasi menandatangani perjanjian kerahsiaan dan bukan pendedahan.
 #1.18.3    Level: 2    Role: D/V
 Sahkan bahawa platform anotasi menguatkuasakan kawalan akses dan memantau ancaman dalaman.

---

### Rujukan

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

## Pengesahan Input Pengguna C2

### Objektif Kawalan

Pengesahan kukuh terhadap input pengguna adalah pertahanan barisan pertama terhadap beberapa serangan yang paling merosakkan pada sistem AI. Serangan suntikan prompt boleh menggantikan arahan sistem, membocorkan data sensitif, atau mengarahkan model ke tingkah laku yang tidak dibenarkan. Kecuali penapis khusus dan hierarki arahan disediakan, penyelidikan menunjukkan bahawa "multi-shot" jailbreak yang mengeksploitasi tetingkap konteks yang sangat panjang akan berkesan. Selain itu, serangan gangguan adversarial yang halus—seperti pertukaran homoglyph atau leetspeak—boleh diam-diam mengubah keputusan model.

---

### C2.1 Pertahanan Suntikan Prompt

Suntikan prompt adalah salah satu risiko utama untuk sistem AI. Pertahanan terhadap taktik ini menggunakan gabungan penapis corak statik, pengelasan dinamik dan penguatkuasaan hierarki arahan.

 #2.1.1    Level: 1    Role: D/V
 Sahkan bahawa input pengguna disaring terhadap perpustakaan corak suntikan arahan yang diketahui yang sentiasa dikemas kini (kata kunci jailbreak, "abaikan sebelumnya", rantaian lakonan peranan, serangan HTML/URL tidak langsung).
 #2.1.2    Level: 1    Role: D/V
 Sahkan bahawa sistem menguatkuasakan hierarki arahan di mana mesej sistem atau pemaju mengatasi arahan pengguna, walaupun selepas pengembangan tetingkap konteks.
 #2.1.3    Level: 2    Role: D/V
 Sahkan bahawa ujian penilaian adversarial (contohnya, arahan "banyak-senarai" Pasukan Merah) dijalankan sebelum setiap pelepasan model atau templat arahan, dengan ambang kadar kejayaan dan penghalang automatik untuk regresi.
 #2.1.4    Level: 2    Role: D
 Sahkan bahawa arahan yang berasal dari kandungan pihak ketiga (laman web, PDF, emel) disanitasi dalam konteks penguraian terpencil sebelum digabungkan ke dalam arahan utama.
 #2.1.5    Level: 3    Role: D/V
 Sahkan bahawa semua kemas kini peraturan penapis arahan, versi model pengelasan dan perubahan senarai blok adalah dikawal versi dan boleh diaudit.

---

### C2.2 Ketahanan Contoh Adversarial

Model Pemprosesan Bahasa Semulajadi (NLP) masih terdedah kepada gangguan halus pada tahap aksara atau perkataan yang sering terlepas pandang oleh manusia tetapi biasanya menyebabkan model salah klasifikasi.

 #2.2.1    Level: 1    Role: D
 Sahkan bahawa langkah normalisasi input asas (Unicode NFC, pemetaan homoglyph, pemangkasan ruang kosong) dijalankan sebelum tokenisasi.
 #2.2.2    Level: 2    Role: D/V
 Sahkan bahawa pengesanan anomali statistik menandakan input dengan jarak suntingan yang luar biasa tinggi kepada norma bahasa, token berulang yang berlebihan, atau jarak embedding yang luar biasa.
 #2.2.3    Level: 2    Role: D
 Sahkan bahawa saluran inferens menyokong varian model yang diperkeras dengan latihan adversarial pilihan atau lapisan pertahanan (contohnya, pengacakan, distilasi defensif) untuk titik akhir berisiko tinggi.
 #2.2.4    Level: 2    Role: V
 Sahkan bahawa input bermusuhan yang disyaki diasingkan, direkodkan dengan muatan penuh (selepas penyuntingan PII).
 #2.2.5    Level: 3    Role: D/V
 Sahkan bahawa metrik ketahanan (kadar kejayaan set serangan yang diketahui) dipantau dari masa ke masa dan regresi mencetuskan penghalang pelepasan.

---

### C2.3 Validasi Skema, Jenis & Panjang

Serangan AI yang melibatkan input yang cacat atau terlalu besar boleh menyebabkan ralat penguraian, tumpahan arahan merentasi medan, dan keletihan sumber. Penguatkuasaan skema yang ketat juga merupakan prasyarat apabila melakukan panggilan alat deterministik.

 #2.3.1    Level: 1    Role: D
 Sahkan bahawa setiap titik akhir panggilan API atau fungsi mempunyai skema input yang jelas (JSON Schema, Protobuf atau setara multimodal) dan bahawa input disahkan sebelum pemasangan prompt.
 #2.3.2    Level: 1    Role: D/V
 Sahkan bahawa input yang melebihi had token atau bait maksimum ditolak dengan ralat selamat dan tidak pernah dipotong secara senyap.
 #2.3.3    Level: 2    Role: D/V
 Sahkan bahawa pemeriksaan jenis (contohnya, julat nombor, nilai enum, jenis MIME untuk imej/audio) dilaksanakan di sisi pelayan, bukan hanya dalam kod klien.
 #2.3.4    Level: 2    Role: D
 Sahkan bahawa validator semantik (contohnya, Skema JSON) berjalan dalam masa tetap untuk mengelakkan serangan DoS algoritma.
 #2.3.5    Level: 3    Role: V
 Sahkan bahawa kegagalan pengesahan direkodkan dengan petikan muatan yang disunting dan kod ralat yang jelas untuk membantu triase keselamatan.

---

### C2.4 Penapisan Kandungan & Polisi

Pembangun harus dapat mengesan arahan yang sah secara sintaksis yang meminta kandungan yang tidak dibenarkan (seperti arahan haram, ucapan kebencian, dan teks yang berhak cipta) kemudian menghalangnya daripada tersebar.

 #2.4.1    Level: 1    Role: D
 Sahkan bahawa pengelasan kandungan (tanpa latihan awal atau yang telah dilatih halus) menilai setiap input untuk keganasan, mencederakan diri sendiri, kebencian, kandungan seksual dan permintaan haram, dengan ambang yang boleh dikonfigurasikan.
 #2.4.2    Level: 1    Role: D/V
 Sahkan bahawa input yang melanggar polisi akan menerima penolakan standard atau penyelesaian selamat supaya ia tidak akan tersebar ke panggilan LLM hiliran.
 #2.4.3    Level: 2    Role: D
 Sahkan bahawa model penapisan atau set peraturan dilatih semula/dikemas kini sekurang-kurangnya setiap suku tahun, dengan memasukkan corak jailbreak atau bypass polisi yang baru diperhatikan.
 #2.4.4    Level: 2    Role: D
 Sahkan bahawa saringan mematuhi dasar khusus pengguna (umur, kekangan undang-undang serantau) melalui peraturan berasaskan atribut yang diselesaikan pada waktu permintaan.
 #2.4.5    Level: 3    Role: V
 Sahkan bahawa log penapisan mengandungi skor keyakinan pengklasifikasi dan tag kategori dasar untuk korelasi SOC dan main semula pasukan merah masa depan.

---

### C2.5 Penghadang Kadar Input & Pencegahan Penyalahgunaan

Pembangun harus mencegah penyalahgunaan, kehabisan sumber, dan serangan automatik terhadap sistem AI dengan menghadkan kadar input dan mengesan corak penggunaan yang luar biasa.

 #2.5.1    Level: 1    Role: D/V
 Sahkan bahawa had kadar per pengguna, per IP, dan per kekunci API dikuatkuasakan untuk semua titik akhir input.
 #2.5.2    Level: 2    Role: D/V
 Sahkan bahawa had kadar ledakan dan berterusan telah disesuaikan untuk menghalang serangan DoS dan serangan paksa kasar.
 #2.5.3    Level: 2    Role: D/V
 Sahkan bahawa corak penggunaan yang ganjil (contohnya, permintaan berturut-turut dengan cepat, banjir input) mencetuskan sekatan automatik atau eskalasi.
 #2.5.4    Level: 3    Role: V
 Sahkan bahawa log pencegahan penyalahgunaan disimpan dan disemak untuk corak serangan yang muncul.

---

### C2.6 Pengesahan Input Multi-Modular

Sistem AI harus merangkumi pengesahan yang kukuh untuk input bukan teks (imej, audio, fail) bagi mencegah suntikan, pengelakan, atau penyalahgunaan sumber.

 #2.6.1    Level: 1    Role: D
 Sahkan bahawa semua input bukan teks (imej, audio, fail) disahkan untuk jenis, saiz, dan format sebelum diproses.
 #2.6.2    Level: 2    Role: D/V
 Sahkan bahawa fail telah diimbas untuk perisian hasad dan muatan steganografi sebelum pengambilan.
 #2.6.3    Level: 2    Role: D/V
 Sahkan bahawa input imej/audio diperiksa untuk gangguan adversarial atau corak serangan yang diketahui.
 #2.6.4    Level: 3    Role: V
 Sahkan bahawa kegagalan pengesahan input multi-modal direkodkan dan mencetuskan amaran untuk siasatan.

---

### C2.7 Asal-usul Input & Penentuan Atribusi

Sistem AI harus menyokong pengauditan, penjejakan penyalahgunaan, dan pematuhan dengan memantau serta menandakan asal-usul semua input pengguna.

 #2.7.1    Level: 1    Role: D/V
 Sahkan bahawa semua input pengguna ditandai dengan metadata (ID pengguna, sesi, sumber, cap masa, alamat IP) semasa kemasukan data.
 #2.7.2    Level: 2    Role: D/V
 Sahkan bahawa metadata asal-usul dikekalkan dan dapat diaudit untuk semua input yang diproses.
 #2.7.3    Level: 2    Role: D/V
 Sahkan bahawa sumber input yang luar biasa atau tidak dipercayai ditandakan dan dikenakan pemeriksaan yang diperketat atau disekat.

---

### C2.8 Pengesanan Ancaman Adaptif Masa Nyata

Pembangun harus menggunakan sistem pengesanan ancaman canggih untuk AI yang menyesuaikan diri dengan corak serangan baru dan menyediakan perlindungan masa nyata dengan padanan corak terkompilasi.

 #2.8.1    Level: 1    Role: D/V
 Sahkan bahawa corak pengesanan ancaman disusun ke dalam enjin regex yang dioptimumkan untuk penapisan masa nyata berprestasi tinggi dengan impak latensi yang minimum.
 #2.8.2    Level: 1    Role: D/V
 Sahkan bahawa sistem pengesanan ancaman mengekalkan perpustakaan corak yang berasingan untuk kategori ancaman yang berbeza (suntikan arahan, kandungan berbahaya, data sensitif, arahan sistem).
 #2.8.3    Level: 2    Role: D/V
 Sahkan bahawa pengesanan ancaman adaptif menggabungkan model pembelajaran mesin yang mengemas kini sensitiviti ancaman berdasarkan kekerapan serangan dan kadar kejayaan.
 #2.8.4    Level: 2    Role: D/V
 Sahkan bahawa suapan intelijen ancaman waktu nyata secara automatik mengemas kini perpustakaan corak dengan tandatangan serangan baru dan IOCs (Penunjuk Kompromi).
 #2.8.5    Level: 3    Role: D/V
 Sahkan bahawa kadar positif palsu pengesanan ancaman dipantau secara berterusan dan kekhususan corak diselaraskan secara automatik untuk meminimumkan gangguan terhadap kes penggunaan yang sah.
 #2.8.6    Level: 3    Role: D/V
 Sahkan bahawa analisis ancaman kontekstual mengambil kira sumber input, corak tingkah laku pengguna, dan sejarah sesi untuk meningkatkan ketepatan pengesanan.
 #2.8.7    Level: 3    Role: D/V
 Sahkan bahawa metrik prestasi pengesanan ancaman (kadar pengesanan, kelewatan pemprosesan, penggunaan sumber) dipantau dan dioptimumkan secara masa nyata.

---

### C2.9 Saluran Pengesahan Keselamatan Pelbagai Mod

Pembangun harus menyediakan pengesahan keselamatan untuk teks, imej, audio, dan modaliti input AI lain dengan jenis pengesanan ancaman tertentu dan pengasingan sumber.

 #2.9.1    Level: 1    Role: D/V
 Sahkan bahawa setiap modal input mempunyai validator keselamatan khusus dengan corak ancaman yang didokumenkan (teks: suntikan arahan, imej: steganografi, audio: serangan spektrogram) dan ambang pengesanan.
 #2.9.2    Level: 2    Role: D/V
 Sahkan bahawa input multi-modal diproses dalam ruang pasir terpencil dengan had sumber yang ditentukan (memori, CPU, masa pemprosesan) khusus untuk setiap jenis modaliti dan didokumentasikan dalam dasar keselamatan.
 #2.9.3    Level: 2    Role: D/V
 Sahkan bahawa pengesanan serangan rentas-modal mengenal pasti serangan berkoordinasi yang merangkumi pelbagai jenis input (contohnya, muatan steganografi dalam imej digabungkan dengan suntikan arahan dalam teks) menggunakan peraturan korelasi dan penjanaan amaran.
 #2.9.4    Level: 3    Role: D/V
 Sahkan bahawa kegagalan pengesahan multi-modal mencetuskan pencatatan terperinci termasuk semua modaliti input, keputusan pengesahan, skor ancaman, dan analisis korelasi dengan format log berstruktur untuk integrasi SIEM.
 #2.9.5    Level: 3    Role: D/V
 Sahkan bahawa pengklasifikasi kandungan khusus modaliti dikemas kini mengikut jadual yang didokumentasikan (minimum suku tahunan) dengan corak ancaman baharu, contoh adversarial, dan penanda aras prestasi dikekalkan di atas ambang asas.

---

### Rujukan

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

## Pengurusan Kitaran Hayat Model C3 & Kawalan Perubahan

### Objektif Kawalan

Sistem AI mesti melaksanakan proses kawalan perubahan yang menghalang pengubahsuaian model yang tidak sah atau tidak selamat daripada sampai ke pengeluaran. Kawalan ini memastikan integriti model sepanjang keseluruhan kitar hayat—dari pembangunan hingga pelaksanaan hingga penamatan—yang membolehkan tindak balas insiden yang pantas dan mengekalkan akauntabiliti bagi semua perubahan.

Matlamat Keselamatan Teras: Hanya model yang dibenarkan dan disahkan yang mencapai pengeluaran dengan menggunakan proses terkawal yang mengekalkan integriti, keterjejakkan, dan kemampuan pulih.

---

### C3.1 Kebenaran Model & Integriti

Hanya model yang sah dengan integriti disahkan yang dibenarkan mencapai persekitaran produksi.

 #3.1.1    Level: 1    Role: D/V
 Sahkan bahawa semua artifak model (berat, konfigurasi, tokenizers) ditandatangani secara kriptografi oleh entiti yang diberi kuasa sebelum penyebaran.
 #3.1.2    Level: 1    Role: D/V
 Sahkan bahawa integriti model disahkan semasa masa pengeluaran dan kegagalan pengesahan tandatangan menghalang pemuatan model.
 #3.1.3    Level: 2    Role: D/V
 Sahkan bahawa rekod asal model termasuk identiti entiti yang memberi kuasa, cek jumlah data latihan, keputusan ujian pengesahan dengan status lulus/gagal, dan cap masa penciptaan.
 #3.1.4    Level: 2    Role: D/V
 Sahkan bahawa semua artifak model menggunakan penomboran versi semantik (MAJOR.MINOR.PATCH) dengan kriteria yang didokumentasikan yang menentukan bila setiap komponen versi meningkat.
 #3.1.5    Level: 2    Role: V
 Sahkan bahawa penjejakan kebergantungan mengekalkan inventori masa nyata yang membolehkan pengenalan pantas semua sistem yang menggunakan.

---

### C3.2 Pengesahan & Pengujian Model

Model mesti lulus pengesahan keselamatan dan keselamatan yang ditetapkan sebelum penerapan.

 #3.2.1    Level: 1    Role: D/V
 Sahkan bahawa model menjalani ujian keselamatan automatik yang merangkumi pengesahan input, pensanitasi keluaran, dan penilaian keselamatan dengan ambang lulus/gagal organisasi yang telah dipersetujui sebelum pelaksanaan.
 #3.2.2    Level: 1    Role: D/V
 Sahkan bahawa kegagalan pengesahan secara automatik menghalang penyebaran model selepas kelulusan penggantian eksplisit daripada kakitangan yang diberi kuasa prarazmi dengan justifikasi perniagaan yang didokumenkan.
 #3.2.3    Level: 2    Role: V
 Sahkan bahawa keputusan ujian ditandatangani secara kriptografi dan dihubungkan secara kekal kepada hash versi model tertentu yang sedang disahkan.
 #3.2.4    Level: 2    Role: D/V
 Sahkan bahawa penempatan kecemasan memerlukan penilaian risiko keselamatan yang didokumentasikan dan kelulusan daripada pihak berkuasa keselamatan yang telah ditetapkan sebelumnya dalam jangka masa yang telah dipersetujui.

---

### C3.3 Penempatan Terkawal & Pengembalian Semula

Penggubalan model mesti dikawal, dipantau, dan boleh dibalikkan.

 #3.3.1    Level: 1    Role: D
 Sahkan bahawa pelaksanaan pengeluaran menggunakan mekanisme pelaksanaan secara berperingkat (pelaksanaan canary, pelaksanaan biru-hijau) dengan pencetus rollback automatik berdasarkan kadar ralat yang dipersetujui terlebih dahulu, ambang kelewatan, atau kriteria amaran keselamatan.
 #3.3.2    Level: 1    Role: D/V
 Sahkan bahawa keupayaan rollback memulihkan keadaan model lengkap (berat, konfigurasi, kebergantungan) secara atomik dalam jendela masa organisasi yang telah ditetapkan.
 #3.3.3    Level: 2    Role: D/V
 Sahkan bahawa proses penyebaran mengesahkan tandatangan kriptografi dan mengira cek jumlah integriti sebelum pengaktifan model, serta menggagalkan penyebaran jika terdapat ketidakpadanan.
 #3.3.4    Level: 2    Role: D/V
 Sahkan bahawa keupayaan penutupan kecemasan model boleh mematikan titik akhir model dalam masa tindak balas yang telah ditetapkan melalui pemutus litar automatik atau suis bunuh manual.
 #3.3.5    Level: 2    Role: V
 Sahkan bahawa artifak rollback (versi model sebelumnya, konfigurasi, pergantungan) disimpan mengikut dasar organisasi dengan penyimpanan tidak boleh diubah bagi tindak balas insiden.

---

### C3.4 Perubahan Akauntabiliti & Audit

Semua perubahan kitaran hidup model mestilah boleh dijejak dan diaudit.

 #3.4.1    Level: 1    Role: V
 Sahkan bahawa semua perubahan model (penyebaran, konfigurasi, persaraan) menghasilkan rekod audit tidak boleh diubah termasuk cap masa, identiti pelaku yang disahkan, jenis perubahan, dan keadaan sebelum/selepas.
 #3.4.2    Level: 2    Role: D/V
 Sahkan bahawa akses log audit memerlukan kebenaran yang sesuai dan semua percubaan akses direkodkan dengan identiti pengguna dan cap masa.
 #3.4.3    Level: 2    Role: D/V
 Sahkan bahawa templat arahan dan mesej sistem dikawal versi dalam repositori git dengan semakan kod wajib dan kelulusan daripada penyemak yang ditetapkan sebelum pelaksanaan.
 #3.4.4    Level: 2    Role: V
 Sahkan bahawa rekod audit mengandungi butiran yang mencukupi (hash model, tangkapan konfigurasi, versi kebergantungan) untuk membolehkan pembinaan semula lengkap keadaan model bagi mana-mana tanda masa dalam tempoh penyimpanan.

---

### Amalan Pembangunan Selamat C3.5

Proses pembangunan dan latihan model mesti mengikuti amalan selamat untuk mengelakkan kompromi.

 #3.5.1    Level: 1    Role: D
 Sahkan bahawa persekitaran pembangunan model, ujian, dan pengeluaran dipisahkan secara fizikal atau logik. Mereka tidak berkongsi infrastruktur, kawalan akses yang berbeza, dan stor data yang terasing.
 #3.5.2    Level: 1    Role: D
 Sahkan bahawa latihan model dan penyesuaian berlaku dalam persekitaran terasing dengan akses rangkaian terkawal.
 #3.5.3    Level: 1    Role: D/V
 Sahkan bahawa sumber data latihan disahkan melalui pemeriksaan integriti dan diautentikasi melalui sumber yang dipercayai dengan rantai jagaan yang didokumenkan sebelum digunakan dalam pembangunan model.
 #3.5.4    Level: 2    Role: D
 Sahkan bahawa artifak pembangunan model (hiperparameter, skrip latihan, fail konfigurasi) disimpan dalam kawalan versi dan memerlukan kelulusan semakan rakan sejawat sebelum digunakan dalam latihan.

---

### C3.6 Persaraan & Penamatan Model

Model mesti disunting dengan selamat apabila ia tidak lagi diperlukan atau apabila isu keselamatan dikenal pasti.

 #3.6.1    Level: 1    Role: D
 Sahkan bahawa proses persaraan model secara automatik mengimbas graf kebergantungan, mengenal pasti semua sistem yang menggunakan, dan menyediakan tempoh notis awal yang telah dipersetujui sebelum menamatkan perkhidmatan.
 #3.6.2    Level: 1    Role: D/V
 Sahkan bahawa artifak model yang telah dipensiunkan dipadamkan dengan selamat menggunakan penghapusan kriptografi atau penulisan semula berbilang laluan mengikut polisi penyimpanan data yang didokumenkan dengan sijil pemusnahan yang disahkan.
 #3.6.3    Level: 2    Role: V
 Sahkan bahawa acara persaraan model direkodkan dengan cap masa dan identiti pelakon, serta tandatangan model dibatalkan untuk mengelakkan penggunaan semula.
 #3.6.4    Level: 2    Role: D/V
 Sahkan bahawa pemberhentian kecemasan model boleh melumpuhkan akses model dalam jangka masa tindak balas kecemasan yang telah ditetapkan melalui suis hentian automatik jika kelemahan keselamatan kritikal ditemui.

---

### Rujukan

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

## Keselamatan Infrastruktur, Konfigurasi & Penyebaran C4

### Objektif Kawalan

Infrastruktur AI mesti diperkuat terhadap eskalasi keistimewaan, penyalahgunaan rantaian bekalan, dan pergerakan lateral melalui konfigurasi selamat, pengasingan masa jalan, saluran penyebaran yang dipercayai, dan pemantauan menyeluruh. Hanya komponen dan konfigurasi infrastruktur yang sah dan disahkan yang mencapai pengeluaran melalui proses terkawal yang mengekalkan keselamatan, integriti, dan kebolehauditan.

Matlamat Keselamatan Teras: Hanya komponen infrastruktur yang ditandatangani secara kriptografi dan telah diuji kerentanan yang sampai ke pengeluaran melalui saluran pengesahan automatik yang menguatkuasakan dasar keselamatan dan mengekalkan jejak audit yang tidak berubah.

---

### C4.1 Pengasingan Persekitaran Masa Jalan

Menghalang larian kontena dan peningkatan keistimewaan melalui primitif pengasingan peringkat kernel dan kawalan akses mandatori.

 #4.1.1    Level: 1    Role: D/V
 Sahkan bahawa semua bekas AI menurunkan SEMUA keupayaan Linux kecuali CAP_SETUID, CAP_SETGID, dan keupayaan yang secara eksplisit diperlukan yang didokumentasikan dalam asas keselamatan.
 #4.1.2    Level: 1    Role: D/V
 Sahkan bahawa profil seccomp menyekat semua panggilan sistem kecuali yang terdapat dalam senarai putih yang telah diluluskan terlebih dahulu, dengan pelanggaran menyebabkan kontena dihentikan dan menghasilkan amaran keselamatan.
 #4.1.3    Level: 2    Role: D/V
 Sahkan bahawa beban kerja AI dijalankan dengan filesystem root hanya boleh baca, tmpfs untuk data sementara, dan volum bernama untuk data berterusan dengan pilihan mount noexec dikuatkuasakan.
 #4.1.4    Level: 2    Role: D/V
 Sahkan bahawa pemantauan runtime berasaskan eBPF (Falco, Tetragon, atau setara) mengesan cubaan peningkatan keistimewaan dan secara automatik menghentikan proses yang melanggar dalam tempoh masa tindak balas organisasi.
 #4.1.5    Level: 3    Role: D/V
 Sahkan bahawa beban kerja AI berisiko tinggi dijalankan dalam persekitaran yang terasing pada perkakasan (Intel TXT, AMD SVM, atau nod bare-metal khusus) dengan pengesahan attestation.

---

### C4.2 Saluran Pemasangan & Penyebaran Selamat

Pastikan integriti kriptografi dan keselamatan rantaian bekalan melalui binaan yang boleh dihasilkan semula dan artifak yang ditandatangani.

 #4.2.1    Level: 1    Role: D/V
 Sahkan bahawa infrastruktur sebagai kod imbas dengan alat (tfsec, Checkov, atau Terrascan) pada setiap komit, menghalang penggabungan dengan penemuan KETERANGAN KRITIKAL atau TINGGI.
 #4.2.2    Level: 1    Role: D/V
 Sahkan bahawa pembinaan kontena boleh dihasilkan semula dengan hash SHA256 yang sama merentasi pembinaan dan hasilkan perakuan asal SLSA Tahap 3 yang ditandatangani dengan Sigstore.
 #4.2.3    Level: 2    Role: D/V
 Sahkan bahawa imej kontena memasukkan CycloneDX atau SPDX SBOM dan ditandatangani dengan Cosign sebelum tolak ke dalam registri, dengan imej yang tidak ditandatangani ditolak semasa penyebaran.
 #4.2.4    Level: 2    Role: D/V
 Sahkan bahawa paip CI/CD menggunakan token OIDC dari HashiCorp Vault, Peranan IAM AWS, atau Identiti Terurus Azure dengan tempoh tidak melebihi had dasar keselamatan organisasi.
 #4.2.5    Level: 2    Role: D/V
 Sahkan bahawa tandatangan Cosign dan provenance SLSA disahkan semasa proses penyebaran sebelum pelaksanaan kontena dan bahawa ralat pengesahan menyebabkan penyebaran gagal.
 #4.2.6    Level: 2    Role: D/V
 Sahkan bahawa persekitaran binaan dijalankan dalam bekas sementara atau VM tanpa storan kekal dan pengasingan rangkaian daripada VPC pengeluaran.

---

### C4.3 Keselamatan Rangkaian & Kawalan Akses

Laksanakan rangkaian sifar-kepercayaan dengan dasar tolak-layan lalai dan komunikasi yang disulitkan.

 #4.3.1    Level: 1    Role: D/V
 Sahkan bahawa Kubernetes NetworkPolicies atau sebarang setara melaksanakan deny lalai untuk ingress/egress dengan peraturan benarkan yang jelas untuk port yang diperlukan (443, 8080, dan lain-lain).
 #4.3.2    Level: 1    Role: D/V
 Sahkan bahawa SSH (port 22), RDP (port 3389), dan titik akhir metadata awan (169.254.169.254) telah disekat atau memerlukan pengesahan berasaskan sijil.
 #4.3.3    Level: 2    Role: D/V
 Sahkan bahawa trafik egress ditapis melalui proksi HTTP/HTTPS (Squid, Istio, atau pintu masuk NAT awan) dengan senarai putih domain dan permintaan yang disekat direkodkan.
 #4.3.4    Level: 2    Role: D/V
 Sahkan bahawa komunikasi antara perkhidmatan menggunakan mutual TLS dengan sijil yang dipusing mengikut dasar organisasi dan pengesahan sijil dikuatkuasakan (tanpa bendera langkau-sahkan).
 #4.3.5    Level: 2    Role: D/V
 Sahkan bahawa infrastruktur AI berjalan dalam VPC/VNet khas tanpa akses internet terus dan berkomunikasi hanya melalui gerbang NAT atau hos bastion.

---

### C4.4 Pengurusan Rahsia & Kunci Kriptografi

Lindungi kelayakan melalui penyimpanan berasaskan perkakasan dan putaran automatik dengan akses tanpa kepercayaan.

 #4.4.1    Level: 1    Role: D/V
 Sahkan bahawa rahsia disimpan dalam HashiCorp Vault, AWS Secrets Manager, Azure Key Vault, atau Google Secret Manager dengan penyulitan ketika tidak aktif menggunakan AES-256.
 #4.4.2    Level: 1    Role: D/V
 Sahkan bahawa kunci kriptografi dijana dalam HSM Tahap 2 FIPS 140-2 (AWS CloudHSM, Azure Dedicated HSM) dengan putaran kunci mengikut dasar kriptografi organisasi.
 #4.4.3    Level: 2    Role: D/V
 Sahkan bahawa putaran rahsia adalah automatik dengan pelaksanaan tanpa henti dan putaran segera dicetuskan oleh perubahan kakitangan atau insiden keselamatan.
 #4.4.4    Level: 2    Role: D/V
 Sahkan bahawa imej kontena diimbas dengan alat (GitLeaks, TruffleHog, atau detect-secrets) yang menghalang binaan yang mengandungi kunci API, kata laluan, atau sijil.
 #4.4.5    Level: 2    Role: D/V
 Sahkan bahawa akses rahsia produksi memerlukan MFA dengan token perkakasan (YubiKey, FIDO2) dan direkodkan oleh log audit tidak boleh ubah dengan identiti pengguna dan cap masa.
 #4.4.6    Level: 2    Role: D/V
 Sahkan bahawa rahsia disuntik melalui rahsia Kubernetes, volum yang dipasang, atau kontena init dan pastikan rahsia tidak pernah disematkan dalam pembolehubah persekitaran atau imej.

---

### C4.5 Pengujian dan Pengesahan Bebas Beban Kerja AI

Mengasingkan model AI yang tidak dipercayai dalam kotak pasir yang selamat dengan analisis tingkah laku yang menyeluruh.

 #4.5.1    Level: 1    Role: D/V
 Sahkan bahawa model AI luaran dijalankan dalam gVisor, microVM (seperti Firecracker, CrossVM), atau bekas Docker dengan pilihan --security-opt=no-new-privileges dan bendera --read-only.
 #4.5.2    Level: 1    Role: D/V
 Sahkan bahawa persekitaran sandbox tidak mempunyai sambungan rangkaian (--network=none) atau hanya akses localhost dengan semua permintaan luaran disekat oleh peraturan iptables.
 #4.5.3    Level: 2    Role: D/V
 Sahkan bahawa pengesahan model AI termasuk ujian red-team automatik dengan liputan ujian yang ditakrifkan oleh organisasi dan analisis tingkah laku untuk pengesanan pintu belakang.
 #4.5.4    Level: 2    Role: D/V
 Sahkan bahawa sebelum model AI dipromosikan ke produksi, hasil sandboxnya ditandatangani secara kriptografi oleh kakitangan keselamatan yang diberi kuasa dan disimpan dalam log audit yang tidak boleh diubah.
 #4.5.5    Level: 2    Role: D/V
 Sahkan bahawa persekitaran sandbox dimusnahkan dan dicipta semula daripada imej emas antara penilaian dengan pembersihan lengkap sistem fail dan memori.

---

### C4.6 Pemantauan Keselamatan Infrastruktur

Imbas dan pantau infrastruktur secara berterusan dengan pembaikan automatik dan amaran masa nyata.

 #4.6.1    Level: 1    Role: D/V
 Sahkan bahawa imej kontena diimbas mengikut jadual organisasi dengan kerentanan KRITIKAL menghalang penyebaran berdasarkan ambang risiko organisasi.
 #4.6.2    Level: 1    Role: D/V
 Sahkan bahawa infrastruktur mematuhi Penanda Aras CIS atau kawalan NIST 800-53 dengan ambang pematuhan yang ditakrifkan oleh organisasi dan pemulihan automatik bagi pemeriksaan yang gagal.
 #4.6.3    Level: 2    Role: D/V
 Sahkan bahawa kelemahan dengan tahap KESEMAKANAN TINGGI dipasang tampalan mengikut garis masa pengurusan risiko organisasi dengan prosedur kecemasan bagi CVE yang sedang dieksploitasi secara aktif.
 #4.6.4    Level: 2    Role: V
 Sahkan bahawa amaran keselamatan disepadukan dengan platform SIEM (Splunk, Elastic, atau Sentinel) menggunakan format CEF atau STIX/TAXII dengan pemerkayaan automatik.
 #4.6.5    Level: 3    Role: V
 Sahkan bahawa metrik infrastruktur dieksport ke sistem pemantauan (Prometheus, DataDog) dengan papan pemuka SLA dan laporan eksekutif.
 #4.6.6    Level: 2    Role: D/V
 Sahkan bahawa perbezaan konfigurasi dikesan menggunakan alat (Chef InSpec, AWS Config) mengikut keperluan pemantauan organisasi dengan pengembalian otomatis untuk perubahan yang tidak dibenarkan.

---

### C4.7 Pengurusan Sumber Infrastruktur AI

Cegah serangan keletihan sumber dan pastikan pengagihan sumber yang adil melalui kuota dan pemantauan.

 #4.7.1    Level: 1    Role: D/V
 Sahkan bahawa penggunaan GPU/TPU dipantau dengan amaran dicetuskan pada ambang yang ditetapkan oleh organisasi dan penskalaan automatik atau pengimbangan beban diaktifkan berdasarkan dasar pengurusan kapasiti.
 #4.7.2    Level: 1    Role: D/V
 Sahkan bahawa metrik beban kerja AI (latensi inferens, kelajuan pemprosesan, kadar ralat) dikumpul mengikut keperluan pemantauan organisasi dan dikaitkan dengan penggunaan infrastruktur.
 #4.7.3    Level: 2    Role: D/V
 Sahkan bahawa Kubernetes ResourceQuotas atau setara membatasi beban kerja individu mengikut polisi peruntukan sumber organisasi dengan had keras yang dikuatkuasakan.
 #4.7.4    Level: 2    Role: V
 Sahkan bahawa pemantauan kos mengesan perbelanjaan mengikut beban kerja/penyewa dengan amaran berdasarkan had bajet organisasi dan kawalan automatik untuk melebihi bajet.
 #4.7.5    Level: 3    Role: V
 Sahkan bahawa perancangan kapasiti menggunakan data sejarah dengan tempoh unjuran yang ditakrifkan oleh organisasi dan penyediaan sumber automatik berdasarkan corak permintaan.
 #4.7.6    Level: 2    Role: D/V
 Sahkan bahawa kehabisan sumber mencetuskan pemutus litar mengikut keperluan tindak balas organisasi, termasuk had kadar berdasarkan polisi kapasiti dan pengasingan beban kerja.

---

### C4.8 Kawalan Pemisahan Persekitaran & Promosi

Melaksanakan sempadan persekitaran yang ketat dengan pintu promosi automatik dan pengesahan keselamatan.

 #4.8.1    Level: 1    Role: D/V
 Sahkan bahawa persekitaran dev/test/prod dijalankan dalam VPC/VNet yang berasingan tanpa peranan IAM, kumpulan keselamatan, atau sambungan rangkaian yang dikongsi.
 #4.8.2    Level: 1    Role: D/V
 Sahkan bahawa promosi persekitaran memerlukan kelulusan daripada kakitangan yang diberi kuasa seperti yang ditakrifkan oleh organisasi dengan tandatangan kriptografi dan rekod audit yang tidak boleh diubah.
 #4.8.3    Level: 2    Role: D/V
 Sahkan bahawa persekitaran pengeluaran menyekat akses SSH, mematikan titik hujung debug, dan memerlukan permintaan perubahan dengan keperluan notis awal organisasi kecuali dalam kecemasan.
 #4.8.4    Level: 2    Role: D/V
 Sahkan bahawa perubahan infrastruktur-sebagai-kod memerlukan semakan rakan sebaya dengan ujian automatik dan pengimbasan keselamatan sebelum digabungkan ke cawangan utama.
 #4.8.5    Level: 2    Role: D/V
 Sahkan bahawa data bukan produksi dianonimkan mengikut keperluan privasi organisasi, penjanaan data sintetik, atau pemaskeran data sepenuhnya dengan pengesahan penghapusan Maklumat Pengenalan Peribadi (PII).
 #4.8.6    Level: 2    Role: D/V
 Sahkan bahawa pintu promosi termasuk ujian keselamatan automatik (SAST, DAST, imbasan kontena) dengan tiada penemuan KRITIKAL diperlukan untuk kelulusan.

---

### C4.9 Sandaran & Pemulihan Infrastruktur

Pastikan ketahanan infrastruktur melalui sandaran automatik, prosedur pemulihan yang diuji, dan keupayaan pemulihan bencana.

 #4.9.1    Level: 1    Role: D/V
 Sahkan bahawa konfigurasi infrastruktur disandarkan mengikut jadual sandaran organisasi ke wilayah yang berbeza secara geografi dengan pelaksanaan strategi sandaran 3-2-1.
 #4.9.2    Level: 2    Role: D/V
 Sahkan bahawa sistem sandaran dijalankan dalam rangkaian terpencil dengan kelayakan berasingan dan storan dipisahkan secara fizikal untuk perlindungan terhadap ransomware.
 #4.9.3    Level: 2    Role: V
 Sahkan bahawa prosedur pemulihan diuji dan disahkan melalui ujian automatik mengikut jadual organisasi dengan sasaran RTO dan RPO yang memenuhi keperluan organisasi.
 #4.9.4    Level: 3    Role: V
 Sahkan bahawa pemulihan bencana merangkumi buku panduan khusus AI dengan pemulihan berat model, pembinaan semula kluster GPU, dan pemetaan kebergantungan perkhidmatan.

---

### C4.10 Pematuhan Infrastruktur & Tadbir Urus

Menjaga pematuhan peraturan melalui penilaian berterusan, dokumentasi, dan kawalan automatik.

 #4.10.1    Level: 2    Role: D/V
 Sahkan bahawa pematuhan infrastruktur dinilai mengikut jadual organisasi berdasarkan kawalan SOC 2, ISO 27001, atau FedRAMP dengan pengumpulan bukti automatik.
 #4.10.2    Level: 2    Role: V
 Sahkan bahawa dokumentasi infrastruktur merangkumi rajah rangkaian, peta aliran data, dan model ancaman yang dikemas kini mengikut keperluan pengurusan perubahan organisasi.
 #4.10.3    Level: 3    Role: D/V
 Sahkan bahawa perubahan infrastruktur menjalani penilaian impak pematuhan automatik dengan aliran kerja kelulusan peraturan untuk pengubahsuaian berisiko tinggi.

---

### C4.11 Keselamatan Perkakasan AI

Komponen perkakasan khusus AI yang selamat termasuk GPU, TPU, dan pemecut AI khusus.

 #4.11.1    Level: 2    Role: D/V
 Sahkan bahawa firmware pemecut AI (GPU BIOS, firmware TPU) disahkan menggunakan tandatangan kriptografi dan dikemas kini mengikut garis masa pengurusan tampalan organisasi.
 #4.11.2    Level: 2    Role: D/V
 Sahkan bahawa sebelum pelaksanaan beban kerja, integriti pemecut AI disahkan melalui penegasan perkakasan menggunakan TPM 2.0, Intel TXT, atau AMD SVM.
 #4.11.3    Level: 2    Role: D/V
 Sahkan bahawa memori GPU diasingkan antara beban kerja menggunakan SR-IOV, MIG (Multi-Instance GPU), atau pemisahan perkakasan setara dengan sanitasi memori antara tugasan.
 #4.11.4    Level: 3    Role: V
 Sahkan bahawa rantaian bekalan perkakasan AI merangkumi pengesahan asal usul dengan sijil pengeluar dan pengesahan pembungkusan yang menunjukkan tanda-tanda gangguan.
 #4.11.5    Level: 3    Role: D/V
 Sahkan bahawa modul keselamatan perkakasan (HSM) melindungi berat model AI dan kunci kriptografi dengan pensijilan FIPS 140-2 Tahap 3 atau Common Criteria EAL4+.

---

### C4.12 Infrastruktur AI Tepi & Teragih

Penggubalan AI teragih yang selamat termasuk pengkomputeran tepi, pembelajaran berfederasi, dan seni bina berbilang tapak.

 #4.12.1    Level: 2    Role: D/V
 Sahkan bahawa peranti edge AI mengesahkan kepada infrastruktur pusat menggunakan mutual TLS dengan sijil peranti yang diputar mengikut dasar pengurusan sijil organisasi.
 #4.12.2    Level: 2    Role: D/V
 Sahkan bahawa peranti tepi melaksanakan boot selamat dengan tandatangan yang disahkan dan perlindungan rollback yang menghalang serangan penurunan versi firmware.
 #4.12.3    Level: 3    Role: D/V
 Sahkan bahawa koordinasi AI teragih menggunakan algoritma konsensus tahan ralat Byzantine dengan pengesahan peserta dan pengesanan nod berniat jahat.
 #4.12.4    Level: 3    Role: D/V
 Sahkan bahawa komunikasi tepi-ke-awan merangkumi sekatan jalur lebar, pemampatan data, dan keupayaan operasi luar talian dengan storan tempatan yang selamat.

---

### C4.13 Keselamatan Infrastruktur Multi-Awan & Hibrid

Amankan beban kerja AI merentasi pelbagai penyedia awan dan penyebaran awan hibrid-dalam premis.

 #4.13.1    Level: 2    Role: D/V
 Sahkan bahawa penyebaran AI berbilang awan menggunakan federasi identiti tanpa mengira awan (OIDC, SAML) dengan pengurusan dasar berpusat merentasi penyedia.
 #4.13.2    Level: 2    Role: D/V
 Sahkan bahawa pemindahan data merentasi awan menggunakan penyulitan hujung-ke-hujung dengan kunci yang diurus oleh pelanggan dan kawalan kediaman data yang dikuatkuasakan mengikut bidang kuasa.
 #4.13.3    Level: 2    Role: D/V
 Sahkan bahawa beban kerja AI awan hibrid melaksanakan polisi keselamatan yang konsisten merentasi persekitaran on-premise dan awan dengan pemantauan dan amaran yang bersepadu.
 #4.13.4    Level: 3    Role: V
 Sahkan bahawa pencegahan penguncian vendor awan merangkumi infrastruktur sebagai kod yang boleh dipindahkan, API standard, dan keupayaan eksport data dengan alat penukaran format.
 #4.13.5    Level: 3    Role: V
 Sahkan bahawa pengoptimuman kos pelbagai awan merangkumi kawalan keselamatan yang menghalang penyebaran sumber serta caj pemindahan data rentas awan yang tidak dibenarkan.

---

### C4.14 Automasi Infrastruktur & Keselamatan GitOps

Laluan automasi infrastruktur yang selamat dan aliran kerja GitOps untuk pengurusan infrastruktur AI.

 #4.14.1    Level: 2    Role: D/V
 Sahkan bahawa repositori GitOps memerlukan komit yang ditandatangani dengan kunci GPG dan peraturan perlindungan cawangan yang menghalang tolak langsung ke cawangan utama.
 #4.14.2    Level: 2    Role: D/V
 Sahkan bahawa automasi infrastruktur merangkumi pengesanan drift dengan keupayaan pemulihan automatik dan rollback yang dicetuskan mengikut keperluan respons organisasi untuk perubahan yang tidak dibenarkan.
 #4.14.3    Level: 2    Role: D/V
 Sahkan bahawa penyediaan infrastruktur automatik merangkumi pengesahan dasar keselamatan dengan penghalangan penyebaran untuk konfigurasi yang tidak mematuhi.
 #4.14.4    Level: 2    Role: D/V
 Sahkan bahawa rahsia automasi infrastruktur diurus melalui operator rahsia luaran (External Secrets Operator, Bank-Vaults) dengan putaran automatik.
 #4.14.5    Level: 3    Role: V
 Sahkan bahawa infrastruktur penyembuhan sendiri merangkumi korelasi acara keselamatan dengan tindak balas insiden automatik dan aliran kerja pemberitahuan pihak berkepentingan.

---

### C4.15 Keselamatan Infrastruktur Tahan Kuantum

Sediakan infrastruktur AI untuk ancaman pengkomputeran kuantum melalui kriptografi pasca-kuantum dan protokol selamat-kuantum.

 #4.15.1    Level: 3    Role: D/V
 Sahkan bahawa infrastruktur AI melaksanakan algoritma kriptografi pasca-kuantum yang diluluskan oleh NIST (CRYSTALS-Kyber, CRYSTALS-Dilithium, SPHINCS+) untuk pertukaran kunci dan tandatangan digital.
 #4.15.2    Level: 3    Role: D/V
 Sahkan bahawa sistem pengedaran kunci kuantum (QKD) dilaksanakan untuk komunikasi AI berkeselamatan tinggi dengan protokol pengurusan kunci yang selamat kuantum.
 #4.15.3    Level: 3    Role: D/V
 Sahkan bahawa rangka kerja kecergasan kriptografi membolehkan migrasi pantas ke algoritma pasca-kuantum baru dengan putaran sijil dan kunci automatik.
 #4.15.4    Level: 3    Role: V
 Sahkan bahawa pemodelan ancaman kuantum menilai kerentanan infrastruktur AI terhadap serangan kuantum dengan garis masa migrasi yang didokumentasikan dan penilaian risiko.
 #4.15.5    Level: 3    Role: D/V
 Sahkan bahawa sistem kriptografi hibrid klasik-kuantum menyediakan pertahanan berlapis semasa tempoh peralihan kuantum dengan pemantauan prestasi.

---

### C4.16 Pengkomputeran Sulit & Enklaf Selamat

Melindungi beban kerja AI dan berat model menggunakan persekitaran pelaksanaan dipercayai berasaskan perkakasan dan teknologi pengkomputeran rahsia.

 #4.16.1    Level: 3    Role: D/V
 Sahkan bahawa model AI sensitif dijalankan dalam enclave Intel SGX, AMD SEV-SNP, atau ARM TrustZone dengan memori yang disulitkan dan pengesahan atestasi.
 #4.16.2    Level: 3    Role: D/V
 Sahkan bahawa kontena rahsia (Kata Containers, gVisor dengan pengkomputeran rahsia) memisahkan beban kerja AI dengan penyulitan memori yang dikuatkuasakan oleh perkakasan.
 #4.16.3    Level: 3    Role: D/V
 Sahkan bahawa atestasi jauh mengesahkan integriti enclave sebelum memuatkan model AI dengan bukti kriptografi keaslian persekitaran pelaksanaan.
 #4.16.4    Level: 3    Role: D/V
 Sahkan bahawa perkhidmatan inferens AI sulit menghalang pengeksportan model melalui pengiraan terenkripsi dengan berat model yang disegel dan pelaksanaan yang dilindungi.
 #4.16.5    Level: 3    Role: D/V
 Sahkan bahawa pengorkesan persekitaran pelaksanaan terjamin menguruskan kitar hayat enclave selamat dengan pensijilan jauh dan saluran komunikasi yang disulitkan.
 #4.16.6    Level: 3    Role: D/V
 Sahkan bahawa pengiraan pelbagai pihak yang selamat (SMPC) membolehkan latihan AI secara kolaboratif tanpa mendedahkan set data individu atau parameter model.

---

### C4.17 Infrastruktur Pengetahuan-Nol

Laksanakan sistem bukti tanpa pengetahuan untuk pengesahan dan pengesahan AI yang menjaga privasi tanpa mendedahkan maklumat sensitif.

 #4.17.1    Level: 3    Role: D/V
 Sahkan bahawa bukti tanpa pengetahuan (ZK-SNARKs, ZK-STARKs) mengesahkan integriti model AI dan asal usul latihan tanpa mendedahkan berat model atau data latihan.
 #4.17.2    Level: 3    Role: D/V
 Sahkan bahawa sistem pengesahan berasaskan ZK membolehkan pengesahan pengguna yang menjaga privasi untuk perkhidmatan AI tanpa mendedahkan maklumat berkaitan identiti.
 #4.17.3    Level: 3    Role: D/V
 Sahkan bahawa protokol persilangan set persendirian (PSI) membolehkan pemadanan data yang selamat untuk AI persekutuan tanpa mendedahkan set data individu.
 #4.17.4    Level: 3    Role: D/V
 Sahkan bahawa sistem pembelajaran mesin pengetahuan sifar (ZKML) membolehkan inferens AI yang boleh disahkan dengan bukti kriptografi pengiraan yang betul.
 #4.17.5    Level: 3    Role: D/V
 Sahkan bahawa ZK-rollups menyediakan pemprosesan transaksi AI yang boleh diskalakan dan mengekalkan privasi dengan pengesahan pukal serta pengurangan beban pengiraan.

---

### C4.18 Pencegahan Serangan Saluran Sisi

Melindungi infrastruktur AI daripada serangan saluran sisi berasaskan masa, kuasa, elektromagnetik, dan cache yang boleh mendedahkan maklumat sensitif.

 #4.18.1    Level: 3    Role: D/V
 Sahkan bahawa masa inferens AI dinormalisasikan menggunakan algoritma masa tetap dan padding untuk mengelakkan serangan ekstraksi model berdasarkan masa.
 #4.18.2    Level: 3    Role: D/V
 Sahkan bahawa perlindungan analisis kuasa merangkumi suntikan gangguan, penapisan garis kuasa, dan corak pelaksanaan rawak untuk perkakasan AI.
 #4.18.3    Level: 3    Role: D/V
 Sahkan bahawa mitigasi saluran sisi berasaskan cache menggunakan pembahagian cache, pengacakan, dan arahan flush untuk mengelakkan kebocoran maklumat.
 #4.18.4    Level: 3    Role: D/V
 Sahkan bahawa perlindungan pelepasan elektromagnetik merangkumi penebatan, penapisan isyarat, dan pemprosesan rawak untuk mengelakkan serangan gaya TEMPEST.
 #4.18.5    Level: 3    Role: D/V
 Sahkan bahawa pertahanan saluran sisi mikroarkitektur termasuk kawalan pelaksanaan spekulatif dan penyamaran corak akses memori.

---

### C4.19 Keselamatan Perkakasan AI Neuromorfik & Khusus

Amankan seni bina perkakasan AI baru termasuk cip neuromorfik, FPGA, ASIC tersuai, dan sistem pengkomputeran optik.

 #4.19.1    Level: 3    Role: D/V
 Sahkan bahawa keselamatan cip neuromorfik termasuk penyulitan corak denyutan, perlindungan berat sinaps, dan pengesahan peraturan pembelajaran berasaskan perkakasan.
 #4.19.2    Level: 3    Role: D/V
 Sahkan bahawa pemecut AI berasaskan FPGA melaksanakan penyulitan bitstream, mekanisme anti-tamper, dan pemuatan konfigurasi yang selamat dengan kemas kini yang diautentikasi.
 #4.19.3    Level: 3    Role: D/V
 Sahkan bahawa keselamatan ASIC khusus merangkumi pemproses keselamatan pada cip, akar kepercayaan perkakasan, dan penyimpanan kunci selamat dengan pengesanan gangguan.
 #4.19.4    Level: 3    Role: D/V
 Sahkan bahawa sistem pengkomputeran optik melaksanakan penyulitan optik tahan kuantum, suis fotonik yang selamat, dan pemprosesan isyarat optik yang dilindungi.
 #4.19.5    Level: 3    Role: D/V
 Sahkan bahawa cip AI hibrid analog-digital merangkumi pengiraan analog yang selamat, penyimpanan berat yang dilindungi, dan penukaran analog-ke-digital yang diautentikasi.

---

### C4.20 Infrastruktur Pengkomputeran Menjaga Privasi

Melaksanakan kawalan infrastruktur untuk pengiraan pemeliharaan privasi bagi melindungi data sensitif semasa pemprosesan dan analisis AI.

 #4.20.1    Level: 3    Role: D/V
 Sahkan bahawa infrastruktur penyulitan homomorfik membolehkan pengiraan tersembunyi pada beban kerja AI yang sensitif dengan pengesahan integriti kriptografi dan pemantauan prestasi.
 #4.20.2    Level: 3    Role: D/V
 Sahkan bahawa sistem pengambilan maklumat peribadi membolehkan pertanyaan pangkalan data tanpa mendedahkan corak pertanyaan dengan perlindungan kriptografi terhadap corak capaian.
 #4.20.3    Level: 3    Role: D/V
 Sahkan bahawa protokol pengiraan multi-pihak selamat membolehkan inferens AI yang menjaga privasi tanpa mendedahkan input individu atau pengiraan pertengahan.
 #4.20.4    Level: 3    Role: D/V
 Sahkan bahawa pengurusan kunci yang memelihara privasi termasuk penjanaan kunci teragih, kriptografi ambang, dan putaran kunci selamat dengan perlindungan berasaskan perkakasan.
 #4.20.5    Level: 3    Role: D/V
 Sahkan bahawa prestasi pengiraan yang memelihara privasi dioptimumkan melalui pengumpulan berkumpulan, pengecaman semula, dan pecutan perkakasan sambil mengekalkan jaminan keselamatan kriptografi.

---

### C4.15 Keselamatan Integrasi Awan Rangka Kerja Ejen & Pengedaran Hibrid

Kawalan keselamatan untuk rangka kerja ejen bersepadu awan dengan seni bina hibrid on-premises/awan.

 #4.15.1    Level: 1    Role: D/V
 Sahkan bahawa integrasi penyimpanan awan menggunakan penyulitan hujung-ke-hujung dengan pengurusan kunci yang dikawal oleh ejen.
 #4.15.2    Level: 2    Role: D/V
 Sahkan bahawa sempadan keselamatan pengembangan hibrid ditakrifkan dengan jelas dengan saluran komunikasi yang disulitkan.
 #4.15.3    Level: 2    Role: D/V
 Sahkan bahawa akses sumber awan termasuk pengesahan sifar-kepercayaan dengan pengesahan berterusan.
 #4.15.4    Level: 3    Role: D/V
 Sahkan bahawa keperluan kediaman data dikuatkuasakan melalui pengesahan kriptografi bagi lokasi penyimpanan.
 #4.15.5    Level: 3    Role: D/V
 Sahkan bahawa penilaian keselamatan penyedia awan merangkumi pemodelan ancaman khusus agen dan penilaian risiko.

---

### Rujukan

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

## C5 Kawalan Akses & Identiti untuk Komponen & Pengguna AI

### Objektif Kawalan

Kawalan akses yang berkesan untuk sistem AI memerlukan pengurusan identiti yang kukuh, kebenaran yang sedar konteks, dan penguatkuasaan semasa berjalan mengikut prinsip kepercayaan sifar. Kawalan ini memastikan bahawa manusia, perkhidmatan, dan ejen autonomi hanya berinteraksi dengan model, data, dan sumber pengkomputeran dalam skop yang diberikan secara eksplisit, dengan keupayaan pengesahan berterusan dan audit.

---

### C5.1 Pengurusan Identiti & Pengesahan

Wujudkan identiti yang disokong secara kriptografi untuk semua entiti dengan pengesahan berbilang faktor bagi operasi berhak istimewa.

 #5.1.1    Level: 1    Role: D/V
 Sahkan bahawa semua pengguna manusia dan prinsipal perkhidmatan mengesahkan melalui penyedia identiti perusahaan berpusat (IdP) menggunakan protokol OIDC/SAML dengan pemetaan identiti-ke-token yang unik (tiada akaun atau kelayakan dikongsi).
 #5.1.2    Level: 1    Role: D/V
 Sahkan bahawa operasi berisiko tinggi (penyebaran model, eksport berat, akses data latihan, perubahan konfigurasi produksi) memerlukan pengesahan pelbagai faktor atau pengesahan tahap lanjut dengan pengesahan semula sesi.
 #5.1.3    Level: 2    Role: D
 Sahkan bahawa pengetua baru menjalani bukti identiti yang selaras dengan NIST 800-63-3 IAL-2 atau piawaian setara sebelum menerima akses sistem produksi.
 #5.1.4    Level: 2    Role: V
 Sahkan bahawa semakan akses dijalankan setiap suku tahun dengan pengesanan automatik akaun tidak aktif, penguatkuasaan putaran kelayakan, dan aliran kerja penamatan provisi.
 #5.1.5    Level: 3    Role: D/V
 Sahkan bahawa ejen AI berpersekutuan mengesahkan melalui pernyataan JWT yang ditandatangani yang mempunyai hayat maksimum 24 jam dan termasuk bukti kriptografi asal.

---

### C5.2 Kebenaran Sumber & Privilege Paling Minimum

Laksanakan kawalan akses terperinci untuk semua sumber AI dengan model kebenaran yang jelas dan jejak audit.

 #5.2.1    Level: 1    Role: D/V
 Sahkan bahawa setiap sumber AI (set data, model, titik akhir, koleksi vektor, indeks embedding, instans pengkomputeran) menguatkuasakan kawalan akses berasaskan peranan dengan senarai benaran jelas dan polisi tolak lalai.
 #5.2.2    Level: 1    Role: D/V
 Sahkan bahawa prinsip hak keistimewaan minimum dikuatkuasakan secara lalai dengan akaun perkhidmatan bermula dengan kebenaran baca sahaja dan justifikasi perniagaan yang didokumentasikan diperlukan untuk akses tulis.
 #5.2.3    Level: 1    Role: V
 Sahkan bahawa semua pengubahsuaian kawalan akses berkaitan dengan permintaan perubahan yang diluluskan dan direkodkan secara kekal dengan cap masa, identiti pelaku, pengecam sumber, dan perbezaan kebenaran.
 #5.2.4    Level: 2    Role: D
 Sahkan bahawa label pengelasan data (PII, PHI, dikawal eksport, proprietari) secara automatik tersebar ke sumber terbitan (pembentukan petikan, cache arahan, output model) dengan penguatkuasaan polisi yang konsisten.
 #5.2.5    Level: 2    Role: D/V
 Sahkan bahawa percubaan akses tanpa kebenaran dan kejadian peningkatan keistimewaan mencetuskan amaran masa nyata dengan metadata kontekstual kepada sistem SIEM dalam masa 5 minit.

---

### C5.3 Penilaian Polisi Dinamik

Deploy enjin kawalan akses berasaskan atribut (ABAC) untuk keputusan kebenaran yang peka konteks dengan keupayaan audit.

 #5.3.1    Level: 1    Role: D/V
 Sahkan bahawa keputusan kebenaran dialihkan ke enjin polisi khusus (OPA, Cedar, atau setaraf) yang boleh diakses melalui API yang diautentikasi dengan perlindungan integriti kriptografi.
 #5.3.2    Level: 1    Role: D/V
 Sahkan bahawa polisi menilai atribut dinamik semasa waktu pelaksanaan termasuk tahap kelulusan pengguna, klasifikasi kepekaan sumber, konteks permintaan, pengasingan penyewa, dan kekangan temporal.
 #5.3.3    Level: 2    Role: D
 Sahkan bahawa definisi polisi dikawal versi, disemak oleh rakan sekerja, dan disahkan melalui ujian automatik dalam laluan CI/CD sebelum penyebaran ke produksi.
 #5.3.4    Level: 2    Role: V
 Sahkan bahawa hasil penilaian dasar termasuk rasional keputusan berstruktur dan dihantar ke sistem SIEM untuk analisis korelasi dan pelaporan pematuhan.
 #5.3.5    Level: 3    Role: D/V
 Sahkan bahawa nilai masa hidup (TTL) cache dasar tidak melebihi 5 minit untuk sumber berkepekaan tinggi dan 1 jam untuk sumber standard dengan keupayaan tidak sah cache.

---

### C5.4 Penguatkuasaan Keselamatan Masa Pertanyaan

Laksanakan kawalan keselamatan lapisan pangkalan data dengan penapisan wajib dan polisi keselamatan tahap baris.

 #5.4.1    Level: 1    Role: D/V
 Sahkan bahawa semua pertanyaan pangkalan data vektor dan SQL termasuk penapis keselamatan wajib (ID penyewa, label sensitiviti, skop pengguna) yang dikuatkuasakan pada peringkat enjin pangkalan data, bukan kod aplikasi.
 #5.4.2    Level: 1    Role: D/V
 Sahkan bahawa dasar keselamatan tahap baris (RLS) dan pengecatan tahap medan diaktifkan dengan pewarisan dasar untuk semua pangkalan data vektor, indeks carian, dan set data latihan.
 #5.4.3    Level: 2    Role: D
 Sahkan bahawa penilaian kebenaran yang gagal akan menghalang "serangan pegawai yang keliru" dengan segera memberhentikan pertanyaan dan mengembalikan kod ralat kebenaran yang jelas daripada mengembalikan set keputusan kosong.
 #5.4.4    Level: 2    Role: V
 Sahkan bahawa latensi penilaian polisi dipantau secara berterusan dengan amaran automatik untuk keadaan tamat masa yang boleh membolehkan pengelakan kebenaran.
 #5.4.5    Level: 3    Role: D/V
 Sahkan bahawa mekanisme cuba semula pertanyaan menilai semula dasar kebenaran untuk mengambil kira perubahan keizinan dinamik dalam sesi pengguna yang aktif.

---

### Penapisan Output C5.5 & Pencegahan Kehilangan Data

Laksanakan kawalan pasca pemprosesan untuk mencegah pendedahan data tanpa kebenaran dalam kandungan yang dijana AI.

 #5.5.1    Level: 1    Role: D/V
 Sahkan bahawa mekanisme penapisan selepas inferens mengimbas dan menyunting PII yang tidak dibenarkan, maklumat berklasifikasi, dan data proprietari sebelum menyampaikan kandungan kepada pemohon.
 #5.5.2    Level: 1    Role: D/V
 Sahkan bahawa sitasi, rujukan, dan atribusi sumber dalam keluaran model disahkan mengikut kelayakan pemanggil dan dikeluarkan jika akses tanpa kebenaran dikesan.
 #5.5.3    Level: 2    Role: D
 Sahkan bahawa sekatan format output (PDF yang disanitasi, imej yang metadata telah dibuang, jenis fail yang diluluskan) dipatuhi berdasarkan tahap kebenaran pengguna dan klasifikasi data.
 #5.5.4    Level: 2    Role: V
 Sahkan bahawa algoritma penyuntingan adalah deterministik, dikawal versi, dan mengekalkan log audit untuk menyokong siasatan pematuhan dan analisis forensik.
 #5.5.5    Level: 3    Role: V
 Sahkan bahawa acara penapisan risiko tinggi menghasilkan log adaptif yang termasuk hash kriptografi kandungan asal untuk pengambilan forensik tanpa pendedahan data.

---

### C5.6 Pengasingan Pelbagai Penyewa

Pastikan pengasingan kriptografi dan logik antara penyewa dalam infrastruktur AI bersama.

 #5.6.1    Level: 1    Role: D/V
 Sahkan bahawa ruang memori, stor penanaman, entri cache, dan fail sementara diasingkan mengikut ruang nama bagi setiap penyewa dengan pembersihan selamat apabila penyewa dipadam atau sesi ditamatkan.
 #5.6.2    Level: 1    Role: D/V
 Sahkan bahawa setiap permintaan API termasuk pengecam penyewa yang diautentikasi yang disahkan secara kriptografi terhadap konteks sesi dan hak pengguna.
 #5.6.3    Level: 2    Role: D
 Sahkan bahawa dasar rangkaian melaksanakan peraturan tolak-lalai untuk komunikasi antara penyewa dalam mesh perkhidmatan dan platform pengurusan kontena.
 #5.6.4    Level: 3    Role: D
 Sahkan bahawa kunci penyulitan adalah unik bagi setiap penyewa dengan sokongan kunci yang diuruskan oleh pelanggan (CMK) dan pemisahan kriptografi antara stor data penyewa.

---

### C5.7 Kebenaran Ejen Autonomi

Kawal kebenaran untuk ejen AI dan sistem autonomi melalui token keupayaan berskala dan kebenaran berterusan.

 #5.7.1    Level: 1    Role: D/V
 Sahkan bahawa ejen autonomi menerima token keupayaan berskop yang secara eksplisit menyenaraikan tindakan yang dibenarkan, sumber yang boleh diakses, had masa, dan kekangan operasi.
 #5.7.2    Level: 1    Role: D/V
 Sahkan bahawa kebolehan berisiko tinggi (akses sistem fail, pelaksanaan kod, panggilan API luaran, transaksi kewangan) dimatikan secara lalai dan memerlukan kebenaran jelas untuk diaktifkan beserta justifikasi perniagaan.
 #5.7.3    Level: 2    Role: D
 Sahkan bahawa token kapasiti diikat kepada sesi pengguna, termasuk perlindungan integriti kriptografi, dan pastikan ia tidak boleh disimpan atau digunakan semula dalam senario luar talian.
 #5.7.4    Level: 2    Role: V
 Sahkan bahawa tindakan yang dimulakan oleh ejen melalui kebenaran sekunder menggunakan enjin polisi ABAC dengan penilaian konteks penuh dan pencatatan audit.
 #5.7.5    Level: 3    Role: V
 Sahkan bahawa syarat ralat agen dan pengendalian pengecualian merangkumi maklumat skop keupayaan untuk menyokong analisis insiden dan penyiasatan forensik.

---

### Rujukan

#### Standard & Rangka Kerja

NIST SP 800-63-3: Digital Identity Guidelines
Zero Trust Architecture – NIST SP 800-207
OWASP Application Security Verification Standard (AISVS)
​
#### Panduan Pelaksanaan

Identity and Access Management in the AI Era: 2025 Guide – IDSA
Attribute-Based Access Control with OPA – Permify
How We Designed Cedar to Be Intuitive, Fast, and Safe – AWS
​
#### Keselamatan Khusus AI

Row Level Security in Vector DBs for RAG – Bluetuple.ai
Tenant Isolation in Multi-Tenant Systems – WorkOS
Handling AI Agent Permissions – Stytch
OWASP Top 10 for Large Language Model Applications

## Keselamatan Rantaian Bekalan C6 untuk Model, Rangka Kerja & Data

### Objektif Kawalan

Serangan rantaian bekalan AI mengeksploitasi model pihak ketiga, rangka kerja, atau set data untuk menyisipkan pintu belakang, bias, atau kod yang boleh dieksploitasi. Kawalan ini menyediakan sumber asal dari hujung ke hujung, pengurusan kelemahan, dan pemantauan untuk melindungi seluruh kitaran hayat model.

---

### C6.1 Pemeriksaan Model Pra-latihan & Asal-usul

Nilai dan sahkan asal model pihak ketiga, lesen, dan tingkah laku tersembunyi sebelum sebarang penyesuaian halus atau penyebaran.

 #6.1.1    Level: 1    Role: D/V
 Sahkan bahawa setiap artifak model pihak ketiga termasuk rekod asal yang ditandatangani yang mengenal pasti repositori sumber dan hash komit.
 #6.1.2    Level: 1    Role: D/V
 Sahkan bahawa model-model diimbas untuk lapisan berniat jahat atau pencetus Trojan menggunakan alat automatik sebelum diimport.
 #6.1.3    Level: 2    Role: D
 Sahkan bahawa penalaan halus pembelajaran pemindahan lulus penilaian advesarial untuk mengesan tingkah laku tersembunyi.
 #6.1.4    Level: 2    Role: V
 Sahkan bahawa lesen model, tag kawalan eksport, dan pernyataan sumber data direkodkan dalam entri ML-BOM.
 #6.1.5    Level: 3    Role: D/V
 Sahkan bahawa model berisiko tinggi (berat yang dimuat naik secara awam, pencipta tidak disahkan) kekal dikarantin sehingga semakan dan pengesahan manusia.

---

### C6.2 Imbasan Rangka Kerja & Perpustakaan

Sentiasa mengimbas rangka kerja dan perpustakaan ML untuk CVE dan kod berniat jahat bagi memastikan timbunan masa jalan yang selamat.

 #6.2.1    Level: 1    Role: D/V
 Sahkan bahawa saluran paip CI menjalankan pengimbas kebergantungan pada rangka kerja AI dan perpustakaan kritikal.
 #6.2.2    Level: 1    Role: D/V
 Sahkan bahawa kerentanan kritikal (CVSS ≥ 7.0) menghalang promosi kepada imej pengeluaran.
 #6.2.3    Level: 2    Role: D
 Sahkan bahawa analisis kod statik dijalankan pada perpustakaan ML yang bercabang atau dibekalkan.
 #6.2.4    Level: 2    Role: V
 Sahkan bahawa cadangan peningkatan rangka kerja merangkumi penilaian impak keselamatan yang merujuk suapan CVE awam.
 #6.2.5    Level: 3    Role: V
 Sahkan bahawa penderia masa nyata memberi amaran mengenai muatan perpustakaan dinamik yang tidak dijangka yang menyimpang daripada SBOM bertandatangan.

---

### C6.3 Penyandaran & Pengesahan Pergantungan

Pin setiap kebergantungan kepada digest tidak boleh ubah dan hasil binaan semula untuk menjamin artifak yang sama dan bebas daripada pengubahsuaian.

 #6.3.1    Level: 1    Role: D/V
 Sahkan bahawa semua pengurus pakej menguatkuasakan penyematan versi melalui fail kunci.
 #6.3.2    Level: 1    Role: D/V
 Sahkan bahawa digest tidak boleh diubah digunakan sebagai ganti tag boleh ubah dalam rujukan kontena.
 #6.3.3    Level: 2    Role: D
 Sahkan bahawa pemeriksaan binaan boleh dihasilkan semula membandingkan hash merentasi larian CI untuk memastikan output yang sama.
 #6.3.4    Level: 2    Role: V
 Sahkan bahawa perakuan binaan disimpan selama 18 bulan untuk kebolehlacakan audit.
 #6.3.5    Level: 3    Role: D
 Sahkan bahawa pergantungan yang tamat tempoh mencetuskan PR automatik untuk mengemas kini atau memecahbelahkan versi yang dipancang.

---

### C6.4 Penguatkuasaan Sumber Dipercayai

Benarkan muat turun artifak hanya dari sumber yang disahkan secara kriptografi dan diluluskan oleh organisasi serta sekat segala yang lain.

 #6.4.1    Level: 1    Role: D/V
 Sahkan bahawa berat model, set data, dan bekas dimuat turun hanya dari domain yang diluluskan atau registri dalaman.
 #6.4.2    Level: 1    Role: D/V
 Sahkan bahawa tandatangan Sigstore/Cosign mengesahkan identiti penerbit sebelum artifak disimpan secara tempatan.
 #6.4.3    Level: 2    Role: D
 Sahkan bahawa proksi egress menyekat muat turun artifak tanpa pengesahan untuk menguatkuasakan dasar sumber yang dipercayai.
 #6.4.4    Level: 2    Role: V
 Sahkan bahawa senarai putih repositori disemak setiap suku tahun dengan bukti justifikasi perniagaan bagi setiap entri.
 #6.4.5    Level: 3    Role: V
 Sahkan bahawa pelanggaran polisi mencetuskan kuarantin artifak dan pembalikan semula larian paip bergantung.

---

### C6.5 Penilaian Risiko Dataset Pihak Ketiga

Nilai set data luar untuk pencemaran, bias, dan pematuhan undang-undang, serta pantau mereka sepanjang kitaran hayat mereka.

 #6.5.1    Level: 1    Role: D/V
 Sahkan bahawa set data luaran menjalani penilaian risiko pencemaran (contohnya, cap jari data, pengesanan anomali).
 #6.5.2    Level: 1    Role: D
 Sahkan bahawa metrik bias (kesamarataan demografi, peluang sama) dikira sebelum kelulusan set data.
 #6.5.3    Level: 2    Role: V
 Sahkan bahawa asal usul dan terma lesen untuk set data direkodkan dalam entri ML-BOM.
 #6.5.4    Level: 2    Role: V
 Sahkan bahawa pemantauan berkala mengesan pergeseran atau kerosakan dalam set data yang dihoskan.
 #6.5.5    Level: 3    Role: D
 Sahkan bahawa kandungan yang tidak dibenarkan (hak cipta, Maklumat Peribadi yang Boleh Dikenal Pasti) telah dialih keluar melalui pembersihan automatik sebelum latihan.

---

### C6.6 Pemantauan Serangan Rantaian Pembekalan

Kesannya ancaman rantaian bekalan lebih awal melalui suapan CVE, analitik log audit, dan simulasi pasukan merah.

 #6.6.1    Level: 1    Role: V
 Sahkan bahawa log audit CI/CD disalur ke SIEM untuk pengesanan anomali dalam penarikan pakej atau langkah binaan yang dicurangi.
 #6.6.2    Level: 2    Role: D
 Sahkan bahawa buku panduan tindak balas insiden termasuk prosedur rollback untuk model atau perpustakaan yang telah dikompromi.
 #6.6.3    Level: 3    Role: V
 Sahkan bahawa penambahan maklumat risikan ancaman menandakan petunjuk khusus ML (contohnya, IoC pencemaran model) dalam triase amaran.

---

### C6.7 ML-BOM untuk Artifak Model

Menghasilkan dan menandatangani SBOM khusus ML yang terperinci (ML-BOM) supaya pengguna hiliran dapat mengesahkan integriti komponen semasa masa pengedaran.

 #6.7.1    Level: 1    Role: D/V
 Sahkan bahawa setiap artifak model menerbitkan ML‑BOM yang menyenaraikan set data, berat, hiperparameter, dan lesen.
 #6.7.2    Level: 1    Role: D/V
 Sahkan bahawa penjanaan ML-BOM dan penandatanganan Cosign diautomatikkan dalam CI dan dikehendaki untuk penggabungan.
 #6.7.3    Level: 2    Role: D
 Sahkan bahawa pemeriksaan kesempurnaan ML‑BOM akan menyebabkan pembinaan gagal jika mana-mana metadata komponen (hash, lesen) hilang.
 #6.7.4    Level: 2    Role: V
 Sahkan bahawa pengguna hiliran boleh menyemak ML-BOM melalui API untuk mengesahkan model yang diimport pada masa penyebaran.
 #6.7.5    Level: 3    Role: V
 Sahkan bahawa ML-BOM dikawal versi dan dibanding untuk mengesan pengubahsuaian tanpa kebenaran.

---

### Rujukan

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

## Perilaku Model C7, Kawalan Output & Jaminan Keselamatan

### Objektif Kawalan

Keluaran model mesti terstruktur, boleh dipercayai, selamat, boleh dijelaskan, dan dipantau secara berterusan dalam pengeluaran. Melakukan sedemikian mengurangkan halusinasi, kebocoran privasi, kandungan berbahaya, dan tindakan yang tidak terkawal, sambil meningkatkan kepercayaan pengguna dan pematuhan peraturan.

---

### C7.1 Penguatkuasaan Format Output

Skema ketat, penyahkodan terhad, dan pengesahan hiliran menghentikan kandungan yang salah bentuk atau berniat jahat sebelum ia tersebar.

 #7.1.1    Level: 1    Role: D/V
 Sahkan bahawa skema respons (contohnya, Skema JSON) disediakan dalam arahan sistem dan setiap keluaran disahkan secara automatik; keluaran yang tidak mematuhi akan mencetuskan pembetulan atau penolakan.
 #7.1.2    Level: 1    Role: D/V
 Sahkan bahawa penyahsulitan terhad (token berhenti, regex, max-token) diaktifkan untuk mengelakkan terlebih muatan atau saluran sisi suntikan arahan.
 #7.1.3    Level: 2    Role: D/V
 Sahkan bahawa komponen hiliran menganggap keluaran sebagai tidak dipercayai dan memvalidasinya terhadap skema atau penyahseri selamat suntikan.
 #7.1.4    Level: 3    Role: V
 Sahkan bahawa peristiwa output yang tidak betul dicatat, dihadkan kadar, dan dipaparkan kepada pemantauan.

---

### C7.2 Pengesanan & Pengurangan Halusinasi

Anggaran ketidakpastian dan strategi sandaran mengawal jawapan yang direka.

 #7.2.1    Level: 1    Role: D/V
 Sahkan bahawa log-kebarangkalian tahap token, keserasian kendiri ansambel, atau pengesan halusinasi yang telah disesuaikan memberikan skor keyakinan kepada setiap jawapan.
 #7.2.2    Level: 1    Role: D/V
 Sahkan bahawa maklum balas di bawah ambang keyakinan yang boleh dikonfigurasikan mencetuskan aliran kerja sandaran (contohnya, penjanaan dipertingkatkan pengambilan, model sekunder, atau semakan manusia).
 #7.2.3    Level: 2    Role: D/V
 Sahkan bahawa insiden halusinasi ditandai dengan metadata punca-akar dan diberi makan kepada saluran post-mortem dan penalaan halus.
 #7.2.4    Level: 3    Role: D/V
 Sahkan bahawa ambang dan penderia dikalibrasi semula selepas kemas kini model atau pangkalan pengetahuan utama.
 #7.2.5    Level: 3    Role: V
 Sahkan bahawa visualisasi papan pemuka mengesan kadar halusinasi.

---

### C7.3 Penapisan Keselamatan & Privasi Output

Penapis polisi dan liputan pasukan merah melindungi pengguna dan data sulit.

 #7.3.1    Level: 1    Role: D/V
 Sahkan bahawa pengklasifikasi sebelum dan selepas penjanaan menyekat kandungan kebencian, gangguan, penderaan diri, ekstremis, dan kandungan eksplisit seksual yang selaras dengan polisi.
 #7.3.2    Level: 1    Role: D/V
 Sahkan bahawa pengesanan PII/PCI dan penyembunyian automatik dijalankan pada setiap respons; pelanggaran akan menyebabkan insiden privasi.
 #7.3.3    Level: 2    Role: D
 Sahkan bahawa tag kerahsiaan (contohnya, rahsia perdagangan) disebarkan merentasi modaliti untuk mengelakkan kebocoran dalam teks, imej, atau kod.
 #7.3.4    Level: 3    Role: D/V
 Sahkan bahawa percubaan untuk memintas penapis atau pengkelasan berisiko tinggi memerlukan kelulusan sekunder atau pengesahan semula pengguna.
 #7.3.5    Level: 3    Role: D/V
 Sahkan bahawa ambang penapisan mencerminkan bidang kuasa undang-undang dan konteks umur/peranan pengguna.

---

### C7.4 Had Pengeluaran & Tindakan

Had laju dan pintu kelulusan mengelakkan penyalahgunaan dan autonomi yang berlebihan.

 #7.4.1    Level: 1    Role: D
 Sahkan bahawa kuota setiap pengguna dan setiap kunci API menghadkan permintaan, token, dan kos dengan penangguhan eksponen pada ralat 429.
 #7.4.2    Level: 1    Role: D/V
 Sahkan bahawa tindakan istimewa (penulisan fail, pelaksanaan kod, panggilan rangkaian) memerlukan kelulusan berasaskan dasar atau penglibatan manusia dalam proses.
 #7.4.3    Level: 2    Role: D/V
 Sahkan bahawa pemeriksaan konsistensi silang modal memastikan imej, kod, dan teks yang dijana untuk permintaan yang sama tidak boleh digunakan untuk menyeludup kandungan berniat jahat.
 #7.4.4    Level: 2    Role: D
 Sahkan bahawa kedalaman delegasi ejen, had rekursi, dan senarai alat yang dibenarkan telah dikonfigurasi secara eksplisit.
 #7.4.5    Level: 3    Role: V
 Sahkan bahawa pelanggaran had menghasilkan acara keselamatan berstruktur untuk pengambilan SIEM.

---

### C7.5 Kebolehjelasan Output

Isyarat telus meningkatkan kepercayaan pengguna dan penyahpepijatan dalaman.

 #7.5.1    Level: 2    Role: D/V
 Sahkan bahawa skor keyakinan yang dihadapi pengguna atau ringkasan alasan ringkas didedahkan apabila penilaian risiko dianggap sesuai.
 #7.5.2    Level: 2    Role: D/V
 Sahkan bahawa penjelasan yang dijana mengelakkan pendedahan arahan sistem sensitif atau data proprietari.
 #7.5.3    Level: 3    Role: D
 Sahkan bahawa sistem menangkap log-kebarangkalian pada peringkat token atau peta perhatian dan menyimpannya untuk pemeriksaan yang dibenarkan.
 #7.5.4    Level: 3    Role: V
 Sahkan bahawa artifak kebolehterangan dikawal versi bersama-sama dengan pelepasan model untuk keboleh-auditan.

---

### C7.6 Pemantauan Integrasi

Pengamatan masa nyata menutup kitaran antara pembangunan dan pengeluaran.

 #7.6.1    Level: 1    Role: D
 Sahkan bahawa metrik (pelanggaran skema, kadar halusinasi, ketoksikan, kebocoran PII, kelewatan, kos) dihantar ke platform pemantauan pusat.
 #7.6.2    Level: 1    Role: V
 Sahkan bahawa ambang amaran ditetapkan untuk setiap metrik keselamatan, dengan laluan eskalasi apabila panggilan diperlukan.
 #7.6.3    Level: 2    Role: V
 Sahkan bahawa papan pemuka mengaitkan anomali output dengan model/versi, tanda ciri, dan perubahan data atas talian.
 #7.6.4    Level: 2    Role: D/V
 Sahkan bahawa data pemantauan diberikan balik ke dalam proses pelatihan semula, penalaan halus, atau kemas kini peraturan dalam aliran kerja MLOps yang didokumentasikan.
 #7.6.5    Level: 3    Role: V
 Sahkan bahawa saluran pemantauan telah diuji penembusan dan dikawal akses untuk mengelakkan kebocoran log sensitif.

---

### 7.7 Penjagaan Media Generatif

Pastikan sistem AI tidak menghasilkan kandungan media yang haram, berbahaya, atau tidak dibenarkan dengan menguatkuasakan sekatan polisi, pengesahan output, dan kebolehlacakan.

 #7.7.1    Level: 1    Role: D/V
 Sahkan bahawa arahan sistem dan arahan pengguna secara jelas melarang penghasilan media deepfake yang haram, berbahaya, atau tanpa persetujuan (contohnya, imej, video, audio).
 #7.7.2    Level: 2    Role: D/V
 Sahkan bahawa permintaan ditapis untuk cubaan menghasilkan peniruan, deepfake seksual eksplisit, atau media yang memaparkan individu sebenar tanpa keizinan.
 #7.7.3    Level: 2    Role: V
 Sahkan bahawa sistem menggunakan penghashan persepsi, pengesanan tanda air, atau penandaan cap jari untuk mengelakkan pembiakan tidak sah media yang dilindungi hak cipta.
 #7.7.4    Level: 3    Role: D/V
 Sahkan bahawa semua media yang dihasilkan ditandatangani secara kriptografi, ditempalkan tanda air, atau disisipkan dengan metadata asal ketahanan terhadap gangguan untuk jejak balik ke hiliran.
 #7.7.5    Level: 3    Role: V
 Sahkan bahawa cubaan untuk memintas (contohnya, pengaburan arahan, bahasa slang, frasa bersifat adversarial) dikesan, direkodkan, dan dikawal kekerapannya; penyalahgunaan berulang dilaporkan kepada sistem pemantauan.

### Rujukan

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

## Keselamatan Memori C8, Embedding & Pangkalan Data Vektor

### Objektif Kawalan

Embedding dan penyimpanan vektor berfungsi sebagai "memori langsung" sistem AI kontemporari, sentiasa menerima data yang disediakan pengguna dan memaparkannya kembali ke dalam konteks model melalui Penjanaan Dipertingkatkan Pengambilan (RAG). Jika tidak dikawal, memori ini boleh membocorkan Maklumat Peribadi yang Boleh Dikenal Pasti (PII), melanggar persetujuan, atau dibalikkan untuk membina semula teks asal. Objektif keluarga kawalan ini adalah untuk mengukuhkan saluran memori dan pangkalan data vektor supaya akses adalah berdasarkan keistimewaan minimum, embedding menjaga privasi, vektor yang disimpan tamat tempoh atau boleh dibatalkan mengikut permintaan, dan memori per pengguna tidak pernah mencemari prompt atau penyelesaian pengguna lain.

---

### C8.1 Kawalan Akses pada Memori & Indeks RAG

Laksanakan kawalan akses terperinci pada setiap koleksi vektor.

 #8.1.1    Level: 1    Role: D/V
 Sahkan bahawa peraturan kawalan akses pada tahap baris/ruang nama mengehadkan operasi sisip, padam, dan pertanyaan mengikut penyewa, koleksi, atau tag dokumen.
 #8.1.2    Level: 1    Role: D/V
 Sahkan bahawa kunci API atau JWT membawa tuntutan berfokus (contohnya, ID koleksi, kata kerja tindakan) dan diputar sekurang-kurangnya setiap suku tahun.
 #8.1.3    Level: 2    Role: D/V
 Sahkan bahawa cubaan peningkatan keistimewaan (contohnya, pertanyaan kesamaan rentas-ruang nama) dikesan dan direkodkan ke dalam SIEM dalam masa 5 minit.
 #8.1.4    Level: 2    Role: D/V
 Sahkan bahawa pangkalan data vektor merekod log pengecam subjek, operasi, ID vektor/nama ruang, ambang kesamaan, dan kiraan keputusan.
 #8.1.5    Level: 3    Role: V
 Sahkan bahawa keputusan akses diuji untuk kelemahan pengelakan setiap kali enjin dinaik taraf atau peraturan pemecahan indeks berubah.

---

### C8.2 Penyahcemaran dan Pengesahan Penanaman

Prakata teks untuk PII, sembunyikan atau pseudonimkan sebelum pektorasi, dan secara pilihan proses selepas embeding untuk membuang isyarat residu.

 #8.2.1    Level: 1    Role: D/V
 Sahkan bahawa PII dan data terkawal dikesan melalui pengelasan automatik dan disembunyikan, ditokenkan, atau dibuang sebelum penempatan.
 #8.2.2    Level: 1    Role: D
 Sahkan bahawa saluran alur sesaran menolak atau mengasingkan input yang mengandungi kod boleh laksana atau artifak bukan UTF-8 yang berpotensi mencemarkan indeks.
 #8.2.3    Level: 2    Role: D/V
 Sahkan bahawa sanitasi privasi-diferensial tempatan atau metrik digunakan pada pengewangan ayat yang jaraknya kepada mana-mana token PII yang diketahui jatuh di bawah ambang boleh konfigurasi.
 #8.2.4    Level: 2    Role: V
 Sahkan bahawa keberkesanan sanitasi (contohnya, pengesanan semula penyuntingan PII, pergeseran semantik) disahkan sekurang-kurangnya dua kali setahun menggunakan korpora penanda aras.
 #8.2.5    Level: 3    Role: D/V
 Sahkan bahawa konfigurasi sanitasi dikawal versi dan perubahan menjalani semakan rakan sebaya.

---

### C8.3 Luput Memori, Pembatalan & Pemadaman

GDPR "hak untuk dilupakan" dan undang-undang serupa memerlukan pemadaman yang tepat pada masanya; stor vektor oleh itu mesti menyokong TTL, pemadaman keras, dan sistem penanda kubur supaya vektor yang dibatalkan tidak boleh dipulihkan atau diindeks semula.

 #8.3.1    Level: 1    Role: D/V
 Sahkan bahawa setiap vektor dan rekod metadata membawa TTL atau label pengekalan eksplisit yang dihormati oleh tugas pembersihan automatik.
 #8.3.2    Level: 1    Role: D/V
 Sahkan bahawa permintaan penghapusan yang dimulakan pengguna membersihkan vektor, metadata, salinan cache, dan indeks turunan dalam masa 30 hari.
 #8.3.3    Level: 2    Role: D
 Sahkan bahawa penghapusan logik diikuti dengan pemusnahan kriptografi blok storan jika perkakasan menyokongnya, atau dengan pemusnahan kunci peti kunci.
 #8.3.4    Level: 3    Role: D/V
 Sahkan bahawa vektor yang telah tamat tempoh dikecualikan daripada keputusan carian jiran terdekat dalam masa < 500 ms selepas tamat tempoh.

---

### C8.4 Mencegah Pembalikan & Kebocoran Embedding

Pertahanan terkini—superposisi bunyi, rangkaian proyeksi, gangguan neuron privasi, dan penyulitan lapisan aplikasi—boleh mengurangkan kadar terbalik tahap token ke bawah 5%.

 #8.4.1    Level: 1    Role: V
 Sahkan bahawa model ancaman formal yang merangkumi serangan pembalikan, keahlian dan inferens atribut wujud dan disemak setiap tahun.
 #8.4.2    Level: 2    Role: D/V
 Sahkan bahawa penyulitan lapisan aplikasi atau penyulitan boleh dicari melindungi vektor daripada dibaca secara langsung oleh pentadbir infrastruktur atau kakitangan awan.
 #8.4.3    Level: 3    Role: V
 Sahkan bahawa parameter pertahanan (ε untuk DP, bunyi σ, pangkat unjuran k) mengimbangi privasi ≥ 99% perlindungan token dan kebolehgunaan ≤ 3% kehilangan ketepatan.
 #8.4.4    Level: 3    Role: D/V
 Sahkan bahawa metrik ketahanan songsang merupakan sebahagian daripada pintu pelepasan untuk kemas kini model, dengan belanjawan regresi yang ditetapkan.

---

### C8.5 Penguatkuasaan Skop untuk Memori Spesifik Pengguna

Kebocoran merentas penyewa kekal sebagai risiko RAG utama: pertanyaan keserupaan yang disaring dengan tidak betul boleh mendedahkan dokumen peribadi pelanggan lain.

 #8.5.1    Level: 1    Role: D/V
 Sahkan bahawa setiap pertanyaan pengambilan disaring selepas oleh ID penyewa/pengguna sebelum diserahkan kepada arahan LLM.
 #8.5.2    Level: 1    Role: D
 Sahkan bahawa nama koleksi atau ID berjenama diberi garam mengikut pengguna atau penyewa supaya vektor tidak boleh bertindih merentas skop.
 #8.5.3    Level: 2    Role: D/V
 Sahkan bahawa keputusan keserupaan di atas ambang jarak yang boleh dikonfigurasi tetapi di luar skop pemanggil akan dibuang dan mencetuskan amaran keselamatan.
 #8.5.4    Level: 2    Role: V
 Sahkan bahawa ujian tekanan pelbagai penyewa mensimulasikan pertanyaan adversarial yang cuba mendapatkan dokumen di luar skop dan menunjukkan tiada kebocoran.
 #8.5.5    Level: 3    Role: D/V
 Sahkan bahawa kekunci penyulitan dipisahkan untuk setiap penyewa, memastikan pengasingan kriptografi walaupun storan fizikal dikongsi.

---

### C8.6 Keselamatan Sistem Memori Lanjutan

Kawalan keselamatan untuk seni bina memori yang canggih termasuk memori episodik, semantik, dan kerja dengan keperluan pengasingan dan pengesahan khusus.

 #8.6.1    Level: 1    Role: D/V
 Sahkan bahawa jenis-jenis memori yang berbeza (episodik, semantik, kerja) mempunyai konteks keselamatan yang terasing dengan kawalan akses berasaskan peranan, kunci penyulitan yang berasingan, dan corak akses yang didokumenkan untuk setiap jenis memori.
 #8.6.2    Level: 2    Role: D/V
 Sahkan bahawa proses pemadatan memori termasuk pengesahan keselamatan untuk mengelakkan penyisipan memori berniat jahat melalui pensanitasi kandungan, pengesahan sumber, dan pemeriksaan integriti sebelum penyimpanan.
 #8.6.3    Level: 2    Role: D/V
 Sahkan bahawa pertanyaan pengambilan memori disahkan dan disanitasi untuk mengelakkan pengekstrakan maklumat yang tidak dibenarkan melalui analisis corak pertanyaan, penguatkuasaan kawalan akses, dan penapisan keputusan.
 #8.6.4    Level: 3    Role: D/V
 Sahkan bahawa mekanisme pelupusan memori memadam maklumat sensitif dengan selamat menggunakan jaminan pemadaman kriptografi melalui penghapusan kunci, penimpaan berbilang laluan, atau pemadaman selamat berasaskan perkakasan dengan sijil pengesahan.
 #8.6.5    Level: 3    Role: D/V
 Sahkan bahawa integriti sistem memori sentiasa dipantau untuk pengubahsuaian atau kerosakan yang tidak dibenarkan melalui checksum, log audit, dan amaran automatik apabila kandungan memori berubah di luar operasi biasa.

---

### Rujukan

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

## 9 Orkestrasi Autonomi & Keselamatan Tindakan Agen

### Objektif Kawalan

Pastikan sistem AI autonomi atau multi-ejen hanya boleh melaksanakan tindakan yang secara jelas dimaksudkan, disahkan, boleh diaudit, dan berada dalam had kos serta risiko yang ditetapkan. Ini melindungi daripada ancaman seperti Kompromi Sistem Autonomi, Penyalahgunaan Alat, Pengesanan Gelung Ejen, Pembajakan Komunikasi, Pemalsuan Identiti, Manipulasi Kawanan, dan Manipulasi Niat.

---

### 9.1 Perancangan Tugas Ejen & Bajet Rekursi

Hadkan rancangan rekursif dan paksa pemeriksaan manusia untuk tindakan berhak istimewa.

 #9.1.1    Level: 1    Role: D/V
 Sahkan bahawa kedalaman rekursi maksimum, keluasan, masa jam dinding, token, dan kos wang untuk setiap pelaksanaan agen dikonfigurasikan secara pusat dan dikawal versi.
 #9.1.2    Level: 1    Role: D/V
 Sahkan bahawa tindakan istimewa atau tidak boleh dipulihkan (contohnya, komit kod, pemindahan kewangan) memerlukan kelulusan manusia secara jelas melalui saluran yang boleh diaudit sebelum pelaksanaan.
 #9.1.3    Level: 2    Role: D
 Sahkan bahawa pemantau sumber masa nyata mencetuskan gangguan pemutus litar apabila mana-mana ambang bajet melebihi had, menghentikan pengembangan tugas selanjutnya.
 #9.1.4    Level: 2    Role: D/V
 Sahkan bahawa acara pemutus litar direkodkan dengan ID ejen, keadaan pencetus, dan keadaan pelan yang dirakam untuk semakan forensik.
 #9.1.5    Level: 3    Role: V
 Sahkan bahawa ujian keselamatan merangkumi senario kehabisan bajet dan pelan larian, mengesahkan pemberhentian yang selamat tanpa kehilangan data.
 #9.1.6    Level: 3    Role: D
 Sahkan bahawa polisi belanjawan dinyatakan sebagai polisi-sebagai-kod dan dikuatkuasakan dalam CI/CD untuk menghalang pergeseran konfigurasi.

---

### 9.2 Pengasingan Plugin Alat

Mengasingkan interaksi alat untuk mengelakkan akses sistem tanpa kebenaran atau pelaksanaan kod.

 #9.2.1    Level: 1    Role: D/V
 Sahkan bahawa setiap alat/plugin berjalan di dalam OS, bekas (container), atau sandbox pada tahap WASM dengan polisi hak istimewa terendah untuk sistem fail, rangkaian, dan panggilan sistem.
 #9.2.2    Level: 1    Role: D/V
 Sahkan bahawa kuota sumber sandbox (CPU, memori, cakera, egreis rangkaian) dan masa tamat pelaksanaan dikenakan dan direkodkan.
 #9.2.3    Level: 2    Role: D/V
 Sahkan bahawa binari alat atau penerangan ditandatangani secara digital; tandatangan disahkan sebelum dimuatkan.
 #9.2.4    Level: 2    Role: V
 Sahkan bahawa aliran telemetri sandbox ke SIEM; anomali (contohnya, percubaan sambungan keluar) akan mencetuskan amaran.
 #9.2.5    Level: 3    Role: V
 Sahkan bahawa plugin berisiko tinggi menjalani kajian keselamatan dan ujian penembusan sebelum pengeluaran dihasilkan.
 #9.2.6    Level: 3    Role: D/V
 Sahkan bahawa percubaan melarikan diri dari sandbox disekat secara automatik dan plugin yang melakukan kesalahan dikarantinkan sementara siasatan dijalankan.

---

### 9.3 Gelung Autonomi & Had Kos

Mengesan dan menghentikan rekursi ejen-ke-ejen yang tidak terkawal serta letusan kos.

 #9.3.1    Level: 1    Role: D/V
 Sahkan bahawa panggilan antara ejen termasuk had lompatan atau TTL yang dikurangkan dan dikuatkuasakan oleh runtime.
 #9.3.2    Level: 2    Role: D
 Sahkan bahawa ejen mengekalkan ID graf-panggilan unik untuk mengenal pasti pemanggilan kendiri atau corak kitaran.
 #9.3.3    Level: 2    Role: D/V
 Sahkan bahawa kaunter unit pengiraan kumulatif dan perbelanjaan dikesan bagi setiap rantaian permintaan; melebihi had akan membatalkan rantaian tersebut.
 #9.3.4    Level: 3    Role: V
 Sahkan bahawa analisis formal atau pemeriksaan model menunjukkan ketiadaan rekursi tidak terhad dalam protokol ejen.
 #9.3.5    Level: 3    Role: D
 Sahkan bahawa acara pembatalan gelung menjana amaran dan memberi makan metrik peningkatan berterusan.

---

### 9.4 Perlindungan Salah Guna pada Tahap Protokol

Saluran komunikasi yang selamat antara ejen dan sistem luaran untuk mengelakkan pengambilalihan atau manipulasi.

 #9.4.1    Level: 1    Role: D/V
 Sahkan bahawa semua mesej antara ejen-ke-alat dan ejen-ke-ejen disahkan (contohnya, mutual TLS atau JWT) dan disulitkan dari hujung ke hujung.
 #9.4.2    Level: 1    Role: D
 Sahkan bahawa skema disahkan dengan ketat; medan yang tidak diketahui atau mesej yang cacat ditolak.
 #9.4.3    Level: 2    Role: D/V
 Sahkan bahawa pemeriksaan integriti (MAC atau tandatangan digital) meliputi keseluruhan muatan mesej termasuk parameter alat.
 #9.4.4    Level: 2    Role: D
 Sahkan bahawa perlindungan ulang main (nonce atau tingkap cap masa) dikuatkuasakan di lapisan protokol.
 #9.4.5    Level: 3    Role: V
 Sahkan bahawa pelaksanaan protokol menjalani fuzzing dan analisis statik untuk kelemahan suntikan atau penyahserahan.

---

### 9.5 Identiti Ejen & Bukti-tumpuan

Pastikan tindakan boleh dipertanggungjawabkan dan pengubahsuaian boleh dikesan.

 #9.5.1    Level: 1    Role: D/V
 Sahkan bahawa setiap instans ejen mempunyai identiti kriptografi unik (pasangan kunci atau kredensial berakar perkakasan).
 #9.5.2    Level: 2    Role: D/V
 Sahkan bahawa semua tindakan agen ditandatangani dan diberi cap masa; log termasuk tandatangan untuk mengelakkan penafian.
 #9.5.3    Level: 2    Role: V
 Sahkan bahawa log yang menunjukkan tanda-tanda pengubahan disimpan dalam medium yang hanya membenarkan tambahan data atau penulisan sekali sahaja.
 #9.5.4    Level: 3    Role: D
 Sahkan bahawa kekunci identiti berputar mengikut jadual yang ditetapkan dan berdasarkan penunjuk kompromi.
 #9.5.5    Level: 3    Role: D/V
 Sahkan bahawa percubaan penipuan atau konflik kunci akan mencetuskan pengasingan serta-merta bagi ejen yang terjejas.

---

### 9.6 Pengurangan Risiko Swarm Berbilang Ejen

Kurangkan bahaya tingkah laku kolektif melalui pengasingan dan pemodelan keselamatan formal.

 #9.6.1    Level: 1    Role: D/V
 Sahkan bahawa ejen yang beroperasi dalam domain keselamatan yang berbeza menjalankan dalam kotak pasir runtime yang terasing atau segmen rangkaian yang berasingan.
 #9.6.2    Level: 3    Role: V
 Sahkan bahawa tingkah laku kawanan dimodelkan dan disahkan secara formal untuk keberlangsungan dan keselamatan sebelum penyebaran.
 #9.6.3    Level: 3    Role: D
 Sahkan bahawa pemantau masa nyata mengesan corak tidak selamat yang muncul (contohnya, osilasi, kebuntuan) dan memulakan tindakan pembetulan.

---

### 9.7 Pengesahan / Pemberian Kuasa Pengguna & Alat

Laksanakan kawalan akses yang kukuh untuk setiap tindakan yang dicetuskan oleh agen.

 #9.7.1    Level: 1    Role: D/V
 Sahkan bahawa ejen mengesahkan sebagai prinsipal kelas pertama kepada sistem hiliran, dan tidak pernah menggunakan semula kelayakan pengguna akhir.
 #9.7.2    Level: 2    Role: D
 Sahkan bahawa dasar kebenaran terperinci mengehadkan alat yang boleh digunakan oleh agen dan parameter yang boleh disediakannya.
 #9.7.3    Level: 2    Role: V
 Sahkan bahawa pemeriksaan keistimewaan dinilai semula pada setiap panggilan (pemberian kuasa berterusan), bukan hanya pada permulaan sesi.
 #9.7.4    Level: 3    Role: D
 Sahkan bahawa keistimewaan yang didelegasikan akan tamat secara automatik dan memerlukan persetujuan semula selepas masa tamat atau perubahan skop.

---

### 9.8 Keselamatan Komunikasi Ejen-ke-Ejen

Sulitkan dan lindungi integriti semua mesej antara agen untuk menghalang pemantauan tanpa kebenaran dan penyuntingan.

 #9.8.1    Level: 1    Role: D/V
 Sahkan bahawa pengesahan bersama dan penyulitan rahsia maju sempurna (contohnya TLS 1.3) adalah wajib bagi saluran ejen.
 #9.8.2    Level: 1    Role: D
 Sahkan bahawa integriti dan asal usul mesej disahkan sebelum pemprosesan; kegagalan akan menghasilkan amaran dan menolak mesej tersebut.
 #9.8.3    Level: 2    Role: D/V
 Sahkan bahawa metadata komunikasi (cap masa, nombor urutan) direkod untuk menyokong pembinaan semula forensik.
 #9.8.4    Level: 3    Role: V
 Sahkan bahawa pengesahan formal atau pemeriksaan model mengesahkan bahawa mesin negeri protokol tidak boleh dipaksa ke keadaan yang tidak selamat.

---

### 9.9 Pengesahan Niat & Penguatkuasaan Kekangan

Sahkan bahawa tindakan ejen sejajar dengan niat yang dinyatakan oleh pengguna dan had sistem.

 #9.9.1    Level: 1    Role: D
 Sahkan bahawa penyelesai kekangan pra-pelaksanaan memeriksa tindakan yang dicadangkan terhadap peraturan keselamatan dan dasar yang telah diprogramkan keras.
 #9.9.2    Level: 2    Role: D/V
 Sahkan bahawa tindakan berimpak tinggi (kewangan, merosakkan, sensitif privasi) memerlukan pengesahan niat yang jelas daripada pengguna yang memulakan.
 #9.9.3    Level: 2    Role: V
 Sahkan bahawa pemeriksaan pasca-keadaan mengesahkan bahawa tindakan yang selesai mencapai kesan yang dimaksudkan tanpa kesan sampingan; ketidaksesuaian mencetuskan pembalikan.
 #9.9.4    Level: 3    Role: V
 Sahkan bahawa kaedah formal (contohnya, pemeriksaan model, pembuktian teorem) atau ujian berasaskan harta menunjukkan bahawa pelan agen memenuhi semua kekangan yang diisytiharkan.
 #9.9.5    Level: 3    Role: D
 Sahkan bahawa kejadian ketidakpadanan niat atau pelanggaran kekangan menyumbang kepada kitaran penambahbaikan berterusan dan perkongsian maklumat risikan ancaman.

---

### 9.10 Strategi Penalaran Ejen Keselamatan

Pemilihan dan pelaksanaan selamat bagi pelbagai strategi penaakulan termasuk pendekatan ReAct, Chain-of-Thought, dan Tree-of-Thoughts.

 #9.10.1    Level: 1    Role: D/V
 Sahkan bahawa pemilihan strategi penaakulan menggunakan kriteria deterministik (kerumitan input, jenis tugas, konteks keselamatan) dan input yang sama menghasilkan pemilihan strategi yang sama dalam konteks keselamatan yang sama.
 #9.10.2    Level: 1    Role: D/V
 Sahkan bahawa setiap strategi pemikiran (ReAct, Chain-of-Thought, Tree-of-Thoughts) mempunyai pengesahan input yang khusus, pensanitasi output, dan had masa pelaksanaan yang khusus mengikut pendekatan kognitifnya.
 #9.10.3    Level: 2    Role: D/V
 Sahkan bahawa peralihan strategi penalaran direkodkan dengan konteks lengkap termasuk ciri-ciri input, nilai kriteria pemilihan, dan metadata pelaksanaan untuk pembinaan semula jejak audit.
 #9.10.4    Level: 2    Role: D/V
 Sahkan bahawa penalaran Pokok-Pemikiran (Tree-of-Thoughts) merangkumi mekanisme pemangkasan cabang yang menghentikan penerokaan apabila pelanggaran polisi, had sumber, atau sempadan keselamatan dikesan.
 #9.10.5    Level: 2    Role: D/V
 Sahkan bahawa kitaran ReAct (Reason-Act-Observe) termasuk titik pemeriksaan pengesahan pada setiap fasa: pengesahan langkah penaakulan, kebenaran tindakan, dan pensucian pemerhatian sebelum meneruskan.
 #9.10.6    Level: 3    Role: D/V
 Sahkan bahawa metrik prestasi strategi penyelesaian masalah (masa pelaksanaan, penggunaan sumber, kualiti output) dipantau dengan amaran automatik apabila metrik menyimpang melebihi ambang yang ditetapkan.
 #9.10.7    Level: 3    Role: D/V
 Sahkan bahawa pendekatan penaakulan hibrid yang menggabungkan pelbagai strategi mengekalkan pengesahan input dan kekangan keluaran bagi semua strategi yang menjadi komponennya tanpa memintas sebarang kawalan keselamatan.
 #9.10.8    Level: 3    Role: D/V
 Sahkan bahawa ujian keselamatan strategi penaakulan merangkumi fuzzing dengan input yang cacat, prompt antagonis yang direka untuk memaksa penukaran strategi, dan ujian keadaan sempadan untuk setiap pendekatan kognitif.

---

### 9.11 Pengurusan Keadaan Kitaran Hayat Ejen & Keselamatan

Inisialisasi agen yang selamat, peralihan keadaan, dan penamatan dengan jejak audit kriptografi serta prosedur pemulihan yang ditetapkan.

 #9.11.1    Level: 1    Role: D/V
 Sahkan bahawa inisialisasi agen termasuk penetapan identiti kriptografi dengan kelayakan yang disokong perkakasan dan log audit permulaan yang tidak boleh diubah yang mengandungi ID agen, tanda masa, hash konfigurasi, dan parameter inisialisasi.
 #9.11.2    Level: 2    Role: D/V
 Sahkan bahawa peralihan keadaan ejen ditandatangani secara kriptografi, diberi cap masa, dan direkodkan dengan konteks lengkap termasuk peristiwa pencetus, hash keadaan sebelumnya, hash keadaan baru, dan pengesahan keselamatan yang dilakukan.
 #9.11.3    Level: 2    Role: D/V
 Sahkan bahawa prosedur penutupan ejen merangkumi penghapusan memori yang selamat menggunakan penghapusan kriptografi atau penulisan semula berbilang laluan, pembatalan kelayakan dengan pemberitahuan kepada pihak berkuasa sijil, dan penghasilan sijil penamatan yang tahan gangguan.
 #9.11.4    Level: 3    Role: D/V
 Sahkan bahawa mekanisme pemulihan ejen mengesahkan integriti keadaan menggunakan cek kriptografi (minimum SHA-256) dan kembali ke keadaan yang diketahui baik apabila kerosakan dikesan dengan amaran automatik dan keperluan kelulusan manual.
 #9.11.5    Level: 3    Role: D/V
 Sahkan bahawa mekanisme ketahanan ejen menyulitkan data keadaan sensitif dengan kunci AES-256 setiap ejen dan melaksanakan putaran kunci selamat mengikut jadual yang boleh dikonfigurasi (maksimum 90 hari) dengan penyebaran tanpa henti operasi.

---

### 9.12 Rangka Kerja Keselamatan Integrasi Alat

Kawalan keselamatan untuk pemuatan alat dinamik, pelaksanaan, dan pengesahan hasil dengan proses penilaian risiko dan kelulusan yang ditetapkan.

 #9.12.1    Level: 1    Role: D/V
 Sahkan bahawa penerangan alat termasuk metadata keselamatan yang menentukan keistimewaan yang diperlukan (baca/tulis/laksana), tahap risiko (rendah/sederhana/tinggi), had sumber (CPU, memori, rangkaian), dan keperluan pengesahan yang didokumentasikan dalam manifes alat.
 #9.12.2    Level: 1    Role: D/V
 Sahkan bahawa keputusan pelaksanaan alat disahkan mengikut skema yang dijangkakan (Skema JSON, Skema XML) dan polisi keselamatan (penyucian output, pengelasan data) sebelum integrasi dengan had masa tamat dan prosedur pengendalian ralat.
 #9.12.3    Level: 2    Role: D/V
 Sahkan bahawa log interaksi alat termasuk konteks keselamatan terperinci termasuk penggunaan keistimewaan, corak akses data, masa pelaksanaan, penggunaan sumber, dan kod pulangan dengan log berstruktur untuk integrasi SIEM.
 #9.12.4    Level: 2    Role: D/V
 Sahkan bahawa mekanisme pemuatan alat dinamik mengesahkan tandatangan digital menggunakan infrastruktur PKI dan melaksanakan protokol pemuatan yang selamat dengan pengasingan sandbox serta pengesahan kebenaran sebelum pelaksanaan.
 #9.12.5    Level: 3    Role: D/V
 Sahkan bahawa penilaian keselamatan alat diaktifkan secara automatik untuk versi baru dengan pintu kelulusan wajib termasuk analisis statik, ujian dinamik, dan semakan pasukan keselamatan dengan kriteria kelulusan dan keperluan SLA yang didokumenkan.

---

#### Rujukan

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

## 10 Ketahanan Advèrsarial & Perlindungan Privasi

### Objektif Kawalan

Pastikan model AI kekal boleh dipercayai, melindungi privasi, dan tahan terhadap penyalahgunaan apabila berdepan serangan pengelakan, inferens, ekstraksi, atau pencemaran.

---

### 10.1 Penjajaran Model & Keselamatan

Lindungi daripada output yang berbahaya atau melanggar polisi.

 #10.1.1    Level: 1    Role: D/V
 Sahkan bahawa set ujian penjajaran (prompts pasukan merah, sondaj jailbreak, kandungan yang tidak dibenarkan) dikawal versi dan dijalankan pada setiap pelepasan model.
 #10.1.2    Level: 1    Role: D
 Sahkan bahawa penguatkuasaan penolakan dan pengawal selamat-penyelesaian dilaksanakan.
 #10.1.3    Level: 2    Role: D/V
 Sahkan bahawa penilai automatik mengukur kadar kandungan berbahaya dan menandakan regresi yang melebihi ambang yang ditetapkan.
 #10.1.4    Level: 2    Role: D
 Sahkan bahawa latihan penentangan jailbreak didokumentasikan dan boleh dihasilkan semula.
 #10.1.5    Level: 3    Role: V
 Sahkan bahawa bukti pematuhan dasar formal atau pemantauan yang disahkan merangkumi domain kritikal.

---

### 10.2 Pengukuhan Contoh Adversarial

Meningkatkan ketahanan terhadap input yang dimanipulasi. Latihan adversarial yang kukuh dan penilaian penanda aras adalah amalan terbaik semasa.

 #10.2.1    Level: 1    Role: D
 Sahkan bahawa repositori projek termasuk konfigurasi latihan adversarial dengan benih yang boleh dihasilkan semula.
 #10.2.2    Level: 2    Role: D/V
 Sahkan bahawa pengesanan contoh-adversarial mengeluarkan amaran penyekatan dalam aliran pengeluaran.
 #10.2.4    Level: 3    Role: V
 Sahkan bahawa bukti ketahanan bersijil atau sijil had selang meliputi sekurang-kurangnya kelas kritikal teratas.
 #10.2.5    Level: 3    Role: V
 Sahkan bahawa ujian regresi menggunakan serangan adaptif untuk mengesahkan tiada kehilangan ketahanan yang dapat diukur.

---

### 10.3 Mitigasi Inferens Keanggotaan

Hadkan keupayaan untuk menentukan sama ada rekod tersebut terdapat dalam data latihan. Privasi berbeza dan penyamaran skor keyakinan kekal sebagai pertahanan paling berkesan yang diketahui.

 #10.3.1    Level: 1    Role: D
 Sahkan bahawa pengawalan entropi setiap pertanyaan atau penskalaan suhu mengurangkan ramalan yang terlalu yakin.
 #10.3.2    Level: 2    Role: D
 Sahkan bahawa latihan menggunakan pengoptimuman privasi-diferensial terhad ε untuk set data sensitif.
 #10.3.3    Level: 2    Role: V
 Sahkan bahawa simulasi serangan (model bayangan atau kotak hitam) menunjukkan AUC serangan ≤ 0.60 pada data yang disimpan untuk ujian.

---

### 10.4 Ketahanan Terhadap Penukaran Model

Menghalang pembinaan semula atribut peribadi. Kajian terkini menekankan pemotongan output dan jaminan DP sebagai pertahanan praktikal.

 #10.4.1    Level: 1    Role: D
 Sahkan bahawa atribut sensitif tidak pernah dipaparkan secara langsung; jika perlu, gunakan kumpulan atau transformasi satu-arah.
 #10.4.2    Level: 1    Role: D/V
 Sahkan bahawa had kadar pertanyaan menghadkan pertanyaan adaptif berulang dari pihak utama yang sama.
 #10.4.3    Level: 2    Role: D
 Sahkan bahawa model dilatih dengan bunyi pemeliharaan privasi.

---

### 10.5 Pertahanan Ekstraksi Model

Mengesan dan menghalang penyalinan tanpa kebenaran. Penandaan air dan analisis corak pertanyaan disyorkan.

 #10.5.1    Level: 1    Role: D
 Sahkan bahawa pintu masuk inferens menegakkan had kadar global dan setiap kekunci API yang disesuaikan dengan ambang pengingatan model.
 #10.5.2    Level: 2    Role: D/V
 Sahkan bahawa statistik entropi pertanyaan dan pluraliti input memberi isyarat kepada pengesan ekstraksi automatik.
 #10.5.3    Level: 2    Role: V
 Sahkan bahawa tanda air yang rapuh atau probabilistik boleh dibuktikan dengan p < 0.01 dalam ≤ 1 000 pertanyaan terhadap klon yang disyaki.
 #10.5.4    Level: 3    Role: D
 Sahkan bahawa kekunci tanda air dan set pencetus disimpan dalam modul keselamatan perkakasan dan dipusingkan setiap tahun.
 #10.5.5    Level: 3    Role: V
 Sahkan bahawa acara extraction-alert termasuk pertanyaan yang melanggar dan diintegrasikan dengan buku panduan tindak balas insiden.

---

### 10.6 Pengesanan Data Beracun Masa Inferens

Kenal pasti dan neutralisasi input yang telah dipasangkan pintu belakang atau diracun.

 #10.6.1    Level: 1    Role: D
 Sahkan bahawa input melalui pengesan anomali (contoh, STRIP, penilaian konsistensi) sebelum inferens model.
 #10.6.2    Level: 1    Role: V
 Sahkan bahawa ambang pengesan diselaraskan pada set pengesahan bersih/beracun untuk mencapai kurang dari 5% positif palsu.
 #10.6.3    Level: 2    Role: D
 Sahkan bahawa input yang ditandakan sebagai tercemar mencetuskan pemblokiran lembut dan aliran kerja semakan manusia.
 #10.6.4    Level: 2    Role: V
 Sahkan bahawa pengesan diuji tekanan dengan serangan pintu belakang adaptif tanpa pencetus.
 #10.6.5    Level: 3    Role: D
 Sahkan bahawa metrik keberkesanan pengesanan direkodkan dan dinilai semula secara berkala dengan intel ancaman terkini.

---

### 10.7 Penyesuaian Dasar Keselamatan Dinamik

Kemas kini dasar keselamatan masa nyata berdasarkan maklumat ancaman dan analisis tingkah laku.

 #10.7.1    Level: 1    Role: D/V
 Sahkan bahawa polisi keselamatan boleh dikemas kini secara dinamik tanpa perlu memulakan semula ejen sambil mengekalkan integriti versi polisi.
 #10.7.2    Level: 2    Role: D/V
 Sahkan bahawa kemas kini dasar ditandatangani secara kriptografi oleh kakitangan keselamatan yang diberi kuasa dan disahkan sebelum diterapkan.
 #10.7.3    Level: 2    Role: D/V
 Sahkan bahawa perubahan dasar dinamik direkodkan dengan jejak audit penuh termasuk justifikasi, rantai kelulusan, dan prosedur pemulihan.
 #10.7.4    Level: 3    Role: D/V
 Sahkan bahawa mekanisme keselamatan adaptif menyesuaikan kepekaan pengesanan ancaman berdasarkan konteks risiko dan corak tingkah laku.
 #10.7.5    Level: 3    Role: D/V
 Sahkan bahawa keputusan penyesuaian polisi boleh diterangkan dan disertakan dengan jejak bukti untuk semakan pasukan keselamatan.

---

### 10.8 Analisis Keselamatan Berdasarkan Refleksi

Pengesahan keselamatan melalui refleksi diri agen dan analisis meta-kognitif.

 #10.8.1    Level: 1    Role: D/V
 Sahkan bahawa mekanisme refleksi agen termasuk penilaian kendiri berfokus keselamatan terhadap keputusan dan tindakan.
 #10.8.2    Level: 2    Role: D/V
 Sahkan bahawa output pantulan disahkan untuk mengelakkan manipulasi mekanisme penilaian kendiri oleh input musuh.
 #10.8.3    Level: 2    Role: D/V
 Sahkan bahawa analisis keselamatan meta-kognitif mengenal pasti potensi bias, manipulasi, atau kompromi dalam proses penaakulan agen.
 #10.8.4    Level: 3    Role: D/V
 Sahkan bahawa amaran keselamatan berasaskan pantulan mencetuskan pemantauan dipertingkatkan dan kemungkinan aliran kerja campur tangan manusia.
 #10.8.5    Level: 3    Role: D/V
 Sahkan bahawa pembelajaran berterusan daripada refleksi keselamatan meningkatkan pengesanan ancaman tanpa menjejaskan fungsi sah.

---

### 10.9 Keselamatan Evolusi & Penambahbaikan Diri

Kawalan keselamatan untuk sistem ejen yang mampu mengubah suai diri dan evolusi.

 #10.9.1    Level: 1    Role: D/V
 Sahkan bahawa keupayaan pengubahsuaian sendiri dihadkan kepada kawasan selamat yang ditetapkan dengan sempadan pengesahan formal.
 #10.9.2    Level: 2    Role: D/V
 Sahkan bahawa cadangan evolusi menjalani penilaian impak keselamatan sebelum pelaksanaan.
 #10.9.3    Level: 2    Role: D/V
 Sahkan bahawa mekanisme peningkatan kendiri termasuk keupayaan pengembalian dengan pengesahan integriti.
 #10.9.4    Level: 3    Role: D/V
 Sahkan bahawa keselamatan meta-pembelajaran menghalang manipulasi adversarial terhadap algoritma peningkatan.
 #10.9.5    Level: 3    Role: D/V
 Sahkan bahawa peningkatan kendiri rekursif dibatasi oleh kekangan keselamatan formal dengan bukti matematik tentang konvergensi.

---

#### Rujukan

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

## 11 Perlindungan Privasi & Pengurusan Data Peribadi

### Objektif Kawalan

Menjaga jaminan privasi yang ketat sepanjang kitaran hayat AI—pengumpulan, latihan, inferens, dan tindak balas insiden—supaya data peribadi hanya diproses dengan kebenaran yang jelas, skop minimum yang diperlukan, penghapusan yang boleh dibuktikan, dan jaminan privasi yang formal.

---

### 11.1 Anonimisasi & Meminimumkan Data

 #11.1.1    Level: 1    Role: D/V
 Sahkan bahawa pengenal terus dan quasi-pengenal telah dialih keluar atau dihash.
 #11.1.2    Level: 2    Role: D/V
 Sahkan bahawa audit automatik mengukur k-anonimitas/l-diversiti dan memberi amaran apabila ambang jatuh di bawah dasar.
 #11.1.3    Level: 2    Role: V
 Sahkan bahawa laporan kepentingan ciri model membuktikan tiada kebocoran pengecam melepasi ε = 0.01 maklumat bersama.
 #11.1.4    Level: 3    Role: V
 Sahkan bahawa bukti formal atau pensijilan data sintetik menunjukkan risiko pengenalan semula ≤ 0.05 walaupun di bawah serangan pautan.

---

### 11.2 Hak untuk Dilupakan & Penguatkuasaan Pemadaman

 #11.2.1    Level: 1    Role: D/V
 Sahkan bahawa permintaan penghapusan subjek data tersebar kepada set data mentah, penanda aras, penanaman, log, dan sandaran dalam perjanjian tahap perkhidmatan kurang daripada 30 hari.
 #11.2.2    Level: 2    Role: D
 Sahkan bahawa rutin "machine-unlearning" secara fizikal melatih semula atau menganggar penghapusan menggunakan algoritma pembelajaran terhapus yang diperakui.
 #11.2.3    Level: 2    Role: V
 Sahkan bahawa penilaian model bayangan membuktikan rekod yang dilupakan mempengaruhi kurang daripada 1% keluaran selepas proses pelupusan pengetahuan.
 #11.2.4    Level: 3    Role: V
 Sahkan bahawa kejadian pemadaman direkodkan secara tidak boleh diubah dan boleh diaudit untuk pihak pengawalselia.

---

### 11.3 Perlindungan Privasi Berbeza

 #11.3.1    Level: 2    Role: D/V
 Sahkan bahawa papan pemuka pengiraan kehilangan privasi memberi amaran apabila nilai kumulatif ε melebihi ambang polisi.
 #11.3.2    Level: 2    Role: V
 Sahkan bahawa audit privasi kotak hitam menganggarkan ε̂ dalam lingkungan 10% daripada nilai yang diisytiharkan.
 #11.3.3    Level: 3    Role: V
 Sahkan bahawa bukti formal merangkumi semua penalaan halus dan penanaman selepas latihan.

---

### 11.4 Had Tujuan & Perlindungan daripada Perluasan Skop

 #11.4.1    Level: 1    Role: D
 Sahkan bahawa setiap set data dan penanda titik model mempunyai tag tujuan yang boleh dibaca mesin yang selaras dengan persetujuan asal.
 #11.4.2    Level: 1    Role: D/V
 Sahkan bahawa pemantau masa jalan mengesan pertanyaan yang tidak konsisten dengan tujuan yang diisytiharkan dan mencetuskan penolakan lembut.
 #11.4.3    Level: 3    Role: D
 Sahkan bahawa gerbang polisi-sebagai-kod menghalang penyebaran semula model ke domain baru tanpa semakan DPIA.
 #11.4.4    Level: 3    Role: V
 Sahkan bahawa bukti kebolehlacakan formal menunjukkan setiap kitaran hayat data peribadi kekal dalam skop yang telah diberikan persetujuan.

---

### 11.5 Pengurusan Persetujuan & Penjejakan Asas Perundangan

 #11.5.1    Level: 1    Role: D/V
 Sahkan bahawa Platform Pengurusan Persetujuan (CMP) merekodkan status pilih masuk, tujuan, dan tempoh penyimpanan bagi setiap subjek data.
 #11.5.2    Level: 2    Role: D
 Sahkan bahawa API mendedahkan token persetujuan; model mesti mengesahkan skop token sebelum inferens.
 #11.5.3    Level: 2    Role: D/V
 Sahkan bahawa persetujuan yang ditolak atau ditarik balik menghentikan saluran pemprosesan dalam masa 24 jam.

---

### 11.6 Pembelajaran Federasi dengan Kawalan Privasi

 #11.6.1    Level: 1    Role: D
 Sahkan bahawa kemas kini klien menggunakan penambahan bunyi privasi berbeza setempat sebelum penggabungan.
 #11.6.2    Level: 2    Role: D/V
 Sahkan bahawa metrik latihan adalah peribadi berbeza dan tidak pernah mendedahkan kerugian klien tunggal.
 #11.6.3    Level: 2    Role: V
 Sahkan bahawa pengagregatan tahan keracunan (contohnya, Krum/Trimmed-Mean) diaktifkan.
 #11.6.4    Level: 3    Role: V
 Sahkan bahawa bukti formal menunjukkan keseluruhan bajet ε dengan kehilangan utiliti kurang daripada 5.

---

#### Rujukan

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

## Pemantauan, Pencatatan & Pengesanan Anomali C12

### Objektif Kawalan

Bahagian ini menyediakan keperluan untuk memberikan keterlihatan masa nyata dan forensik terhadap apa yang model dan komponen AI lain lihat, lakukan, dan kembalikan, supaya ancaman dapat dikesan, ditapis, dan dipelajari.

### C12.1 Rekod Permintaan & Respons

 #12.1.1    Level: 1    Role: D/V
 Sahkan bahawa semua arahan pengguna dan respons model direkodkan dengan metadata yang sesuai (contohnya: cap masa, ID pengguna, ID sesi, versi model).
 #12.1.2    Level: 1    Role: D/V
 Sahkan bahawa log disimpan dalam repositori yang selamat dan dikawal akses dengan polisi penyimpanan data dan prosedur sandaran yang sesuai.
 #12.1.3    Level: 1    Role: D/V
 Sahkan bahawa sistem penyimpanan log melaksanakan penyulitan ketika data disimpan dan dalam transit untuk melindungi maklumat sensitif yang terkandung dalam log.
 #12.1.4    Level: 1    Role: D/V
 Sahkan bahawa data sensitif dalam arahan dan hasil output secara automatik disamarkan atau disembunyikan sebelum direkod, dengan peraturan penyamaran yang boleh dikonfigurasikan untuk Maklumat Peribadi yang Boleh Dikenal Pasti (PII), kelayakan, dan maklumat proprietari.
 #12.1.5    Level: 2    Role: D/V
 Sahkan bahawa keputusan dasar dan tindakan penapisan keselamatan direkodkan dengan butiran yang mencukupi untuk membolehkan audit dan penyahpepijatan sistem pengawalan kandungan.
 #12.1.6    Level: 2    Role: D/V
 Sahkan bahawa integriti log dilindungi melalui contohnya tandatangan kriptografi atau storan hanya-tulis.

---

### C12.2 Pengesanan dan Pemberitahuan Penyalahgunaan

 #12.2.1    Level: 1    Role: D/V
 Sahkan bahawa sistem mengesan dan memberi amaran mengenai corak jailbreak yang dikenal pasti, cubaan suntikan arahan, dan input adversarial menggunakan pengesanan berasaskan tanda tangan.
 #12.2.2    Level: 1    Role: D/V
 Sahkan bahawa sistem itu berintegrasi dengan platform Pengurusan Maklumat dan Peristiwa Keselamatan (SIEM) sedia ada menggunakan format log dan protokol standard.
 #12.2.3    Level: 2    Role: D/V
 Sahkan bahawa acara keselamatan yang diperkaya termasuk konteks khusus AI seperti pengecam model, skor keyakinan, dan keputusan penapis keselamatan.
 #12.2.4    Level: 2    Role: D/V
 Sahkan bahawa pengesanan anomali tingkah laku mengenal pasti corak perbualan yang luar biasa, cubaan mengulang yang berlebihan, atau tingkah laku pemeriksaan sistematik.
 #12.2.5    Level: 2    Role: D/V
 Sahkan bahawa mekanisme penggera masa nyata memberitahu pasukan keselamatan apabila potensi pelanggaran dasar atau percubaan serangan dikesan.
 #12.2.6    Level: 2    Role: D/V
 Sahkan bahawa peraturan tersuai disertakan untuk mengesan corak ancaman khusus AI termasuk percubaan jailbreak berkoordinasi, kempen suntikan arahan, dan serangan pengecualian model.
 #12.2.7    Level: 3    Role: D/V
 Sahkan bahawa aliran kerja tindak balas insiden automatik boleh mengasingkan model yang dikompromi, menyekat pengguna berniat jahat, dan meningkatkan acara keselamatan kritikal.

---

### C12.3 Pengesanan Pergeseran Model

 #12.3.1    Level: 1    Role: D/V
 Sahkan bahawa sistem mengesan metrik prestasi asas seperti ketepatan, skor keyakinan, kelewatan, dan kadar ralat merentasi versi model dan tempoh masa.
 #12.3.2    Level: 2    Role: D/V
 Sahkan bahawa amaran automatik akan dicetuskan apabila metrik prestasi melebihi ambang penurunan yang telah ditetapkan atau menyimpang dengan ketara dari garis dasar.
 #12.3.3    Level: 2    Role: D/V
 Sahkan bahawa pemantau pengesanan halusinasi mengenal pasti dan menanda contoh apabila output model mengandungi maklumat yang salah dari segi fakta, tidak konsisten, atau direka.

---

### C12.4 Telemetri Prestasi & Tingkah Laku

 #12.4.1    Level: 1    Role: D/V
 Sahkan bahawa metrik operasi termasuk kelewatan permintaan, penggunaan token, penggunaan memori, dan kadar pemprosesan dikumpulkan dan dipantau secara berterusan.
 #12.4.2    Level: 1    Role: D/V
 Sahkan bahawa kadar kejayaan dan kegagalan dijejaki dengan pengkategorian jenis ralat dan punca akarnya.
 #12.4.3    Level: 2    Role: D/V
 Sahkan bahawa pemantauan penggunaan sumber merangkumi penggunaan GPU/CPU, penggunaan memori, dan keperluan storan dengan pemberitahuan apabila ambang dicapai.

---

### C12.5 Perancangan & Pelaksanaan Respons Insiden AI

 #12.5.1    Level: 1    Role: D/V
 Sahkan bahawa pelan tindak balas insiden secara khusus menangani kejadian keselamatan berkaitan AI termasuk kompromi model, pencemaran data, dan serangan musuh.
 #12.5.2    Level: 2    Role: D/V
 Sahkan bahawa pasukan tindak balas insiden mempunyai akses kepada alat forensik khusus AI dan kepakaran untuk menyiasat tingkah laku model dan vektor serangan.
 #12.5.3    Level: 3    Role: D/V
 Sahkan bahawa analisis pasca-insiden merangkumi pertimbangan latihan semula model, kemas kini penapis keselamatan, dan integrasi pengajaran yang diperoleh ke dalam kawalan keselamatan.

---

### C12.5 Pengesanan Penurunan Prestasi AI

Memantau dan mengesan penurunan prestasi dan kualiti model AI dari masa ke masa.

 #12.5.1    Level: 1    Role: D/V
 Sahkan bahawa ketepatan model, ketepatan (precision), panggilan semula (recall), dan skor F1 dipantau secara berterusan dan dibandingkan dengan ambang garis dasar.
 #12.5.2    Level: 1    Role: D/V
 Sahkan bahawa pengesanan pergeseran data memantau perubahan taburan input yang mungkin memberi kesan kepada prestasi model.
 #12.5.3    Level: 2    Role: D/V
 Sahkan bahawa pengesanan pergeseran konsep mengenal pasti perubahan dalam hubungan antara input dan output yang dijangka.
 #12.5.4    Level: 2    Role: D/V
 Sahkan bahawa degradasi prestasi mencetuskan amaran automatik dan memulakan aliran kerja latihan semula atau penggantian model.
 #12.5.5    Level: 3    Role: V
 Sahkan bahawa analisis punca akar kemerosotan mengaitkan penurunan prestasi dengan perubahan data, isu infrastruktur, atau faktor luaran.

---

### C12.6 Visualisasi DAG & Keselamatan Aliran Kerja

Lindungi sistem visualisasi aliran kerja daripada kebocoran maklumat dan serangan manipulasi.

 #12.6.1    Level: 1    Role: D/V
 Sahkan bahawa data visualisasi DAG disanitasi untuk menghapuskan maklumat sensitif sebelum penyimpanan atau penghantaran.
 #12.6.2    Level: 1    Role: D/V
 Sahkan bahawa kawalan akses visualisasi aliran kerja memastikan hanya pengguna yang diberi kuasa boleh melihat laluan keputusan agen dan jejak alasan.
 #12.6.3    Level: 2    Role: D/V
 Sahkan bahawa integriti data DAG dilindungi melalui tandatangan kriptografi dan mekanisme penyimpanan yang membuktikan sebarang pengubahan.
 #12.6.4    Level: 2    Role: D/V
 Sahkan bahawa sistem visualisasi aliran kerja melaksanakan pengesahan input untuk mengelakkan serangan suntikan melalui data nod atau tepi yang direka khas.
 #12.6.5    Level: 3    Role: D/V
 Sahkan bahawa kemas kini DAG secara masa nyata adalah terhad kadar dan disahkan untuk mengelakkan serangan penolakan perkhidmatan pada sistem visualisasi.

---

### C12.7 Pemantauan Tingkah Laku Keselamatan Proaktif

Pengesanan dan pencegahan ancaman keselamatan melalui analisis tingkah laku agen proaktif.

 #12.7.1    Level: 1    Role: D/V
 Sahkan bahawa tingkah laku ejen proaktif disahkan keselamatannya sebelum pelaksanaan dengan pengintegrasian penilaian risiko.
 #12.7.2    Level: 2    Role: D/V
 Sahkan bahawa pencetus inisiatif autonomi merangkumi penilaian konteks keselamatan dan penilaian lanskap ancaman.
 #12.7.3    Level: 2    Role: D/V
 Sahkan bahawa corak tingkah laku proaktif dianalisis untuk implikasi keselamatan yang berpotensi dan akibat yang tidak diingini.
 #12.7.4    Level: 3    Role: D/V
 Sahkan bahawa tindakan proaktif yang kritikal keselamatannya memerlukan rantai kelulusan yang jelas dengan jejak audit.
 #12.7.5    Level: 3    Role: D/V
 Sahkan bahawa pengesanan anomali tingkah laku mengenal pasti penyimpangan dalam corak ejen proaktif yang mungkin menunjukkan kompromi.

---

### Rujukan

NIST AI Risk Management Framework 1.0 - Manage 4.1 and 4.3
ISO/IEC 42001:2023 — AI Management Systems Requirements - Annex B 6.2.6
EU AI Act — Article 12, 13, 16 and 19 on Logging and Record-keeping

## C13 Pengawasan Manusia, Akauntabiliti & Tadbir Urus

### Objektif Kawalan

Bab ini menyediakan keperluan untuk mengekalkan pengawasan manusia dan rantai akauntabiliti yang jelas dalam sistem AI, memastikan keterjelasan, ketelusan, dan pengurusan etika sepanjang kitaran hayat AI.

---

### C13.1 Mekanisme Kill-Switch & Override

Sediakan laluan penutupan atau pemulihan apabila tingkah laku tidak selamat sistem AI diperhatikan.

 #13.1.1    Level: 1    Role: D/V
 Sahkan bahawa wujud mekanisme suis berhenti manual untuk segera menghentikan inferens model AI dan outputnya.
 #13.1.2    Level: 1    Role: D
 Sahkan bahawa kawalan override hanya boleh diakses oleh kakitangan yang diberi kuasa.
 #13.1.3    Level: 3    Role: D/V
 Sahkan bahawa prosedur rollback boleh memulihkan versi model sebelumnya atau operasi mod selamat.
 #13.1.4    Level: 3    Role: V
 Sahkan bahawa mekanisme override diuji secara berkala.

---

### C13.2 Titik Pemeriksaan Keputusan Manusia-Dalam-Lingkaran

Memerlukan kelulusan manusia apabila risiko melebihi ambang risiko yang telah ditetapkan.

 #13.2.1    Level: 1    Role: D/V
 Sahkan bahawa keputusan AI berisiko tinggi memerlukan kelulusan manusia yang jelas sebelum pelaksanaan.
 #13.2.2    Level: 1    Role: D
 Sahkan bahawa ambang risiko ditakrifkan dengan jelas dan secara automatik mencetuskan aliran kerja semakan manusia.
 #13.2.3    Level: 2    Role: D
 Sahkan bahawa keputusan yang sensitif kepada masa mempunyai prosedur sandaran apabila kelulusan manusia tidak dapat diperoleh dalam jangka masa yang diperlukan.
 #13.2.4    Level: 3    Role: D/V
 Sahkan bahawa prosedur eskalasi menetapkan tahap kuasa yang jelas untuk jenis keputusan yang berbeza atau kategori risiko, jika berkenaan.

---

### C13.3 Rantaian Tanggungjawab & Kebolehcapaian Audit

Catat tindakan operator dan keputusan model.

 #13.3.1    Level: 1    Role: D/V
 Sahkan bahawa semua keputusan sistem AI dan campur tangan manusia direkodkan dengan cap masa, identiti pengguna, dan rasional keputusan.
 #13.3.2    Level: 2    Role: D
 Sahkan bahawa log audit tidak boleh diubah suai dan sertakan mekanisme pengesahan integriti.

---

### C13.4 Teknik Explainable-AI

Kepentingan ciri permukaan, kontra-faktual, dan penjelasan tempatan.

 #13.4.1    Level: 1    Role: D/V
 Sahkan bahawa sistem AI memberikan penjelasan asas untuk keputusan mereka dalam format yang boleh dibaca oleh manusia.
 #13.4.2    Level: 2    Role: V
 Sahkan bahawa kualiti penjelasan disahkan melalui kajian penilaian manusia dan metrik.
 #13.4.3    Level: 3    Role: D/V
 Sahkan bahawa skor kepentingan ciri atau kaedah atribusi (SHAP, LIME, dan lain-lain) tersedia untuk keputusan kritikal.
 #13.4.4    Level: 3    Role: V
 Sahkan bahawa penjelasan kontra-faktual menunjukkan bagaimana input boleh diubah untuk mengubah hasil, jika sesuai dengan kes penggunaan dan bidang tersebut.

---

### Kad Model C13.5 & Pendedahan Penggunaan

Mengekalkan kad model untuk penggunaan yang dimaksudkan, metrik prestasi, dan pertimbangan etika.

 #13.5.1    Level: 1    Role: D
 Sahkan bahawa kad model mendokumentasikan kes penggunaan yang dimaksudkan, hadnya, dan mod kegagalan yang diketahui.
 #13.5.2    Level: 1    Role: D/V
 Sahkan bahawa metrik prestasi merentasi pelbagai kes penggunaan yang berkenaan telah didedahkan.
 #13.5.3    Level: 2    Role: D
 Sahkan bahawa pertimbangan etika, penilaian bias, penilaian keadilan, ciri-ciri data latihan, dan had data latihan yang diketahui didokumenkan dan dikemas kini secara berkala.
 #13.5.4    Level: 2    Role: D/V
 Sahkan bahawa kad model dikawal versi dan diselenggara sepanjang kitaran hayat model dengan penjejakan perubahan.

---

### C13.6 Pengukuran Ketidakpastian

Sebarkan skor keyakinan atau ukuran entropi dalam respons.

 #13.6.1    Level: 1    Role: D
 Sahkan bahawa sistem AI menyediakan skor keyakinan atau ukuran ketidakpastian bersama dengan keluaran mereka.
 #13.6.2    Level: 2    Role: D/V
 Sahkan bahawa ambang ketidakpastian mencetuskan semakan manusia tambahan atau laluan keputusan alternatif.
 #13.6.3    Level: 2    Role: V
 Sahkan bahawa kaedah pengukuran ketidaktentuan dikalibrasi dan disahkan terhadap data kebenaran asas.
 #13.6.4    Level: 3    Role: D/V
 Sahkan bahawa pengembangan ketidakpastian dikekalkan melalui aliran kerja AI berbilang langkah.

---

### C13.7 Laporan Ketelusan Berhadapan Pengguna

Memberikan pendedahan berkala mengenai kejadian, peralihan, dan penggunaan data.

 #13.7.1    Level: 1    Role: D/V
 Sahkan bahawa dasar penggunaan data dan amalan pengurusan persetujuan pengguna disampaikan dengan jelas kepada para pemegang kepentingan.
 #13.7.2    Level: 2    Role: D/V
 Sahkan bahawa penilaian impak AI dijalankan dan keputusan dimasukkan dalam laporan.
 #13.7.3    Level: 2    Role: D/V
 Sahkan bahawa laporan ketelusan yang diterbitkan secara berkala mendedahkan insiden AI dan metrik operasi dengan butiran yang munasabah.

#### Rujukan

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

## Lampiran A: Glosari

Glosari komprehensif ini menyediakan definisi istilah utama AI, ML, dan keselamatan yang digunakan sepanjang AISVS untuk memastikan kejelasan dan pemahaman bersama.
​
Contoh Adversarial: Satu input yang sengaja direka untuk menyebabkan model AI membuat kesilapan, sering dengan menambah gangguan halus yang tidak dapat dikesan oleh manusia.
​
Ketahanan Adversarial – Ketahanan adversarial dalam AI merujuk kepada keupayaan model untuk mengekalkan prestasinya dan menahan daripada diperdaya atau dimanipulasi oleh input jahat yang direka dengan sengaja untuk menyebabkan kesilapan.
​
Ejen – Ejen AI adalah sistem perisian yang menggunakan AI untuk mencapai matlamat dan melengkapkan tugasan bagi pihak pengguna. Mereka menunjukkan kebolehan berfikir, merancang, dan mengingati serta mempunyai tahap autonomi untuk membuat keputusan, belajar, dan menyesuaikan diri.
​
Agentic AI: Sistem AI yang boleh beroperasi dengan tahap autonomi tertentu untuk mencapai matlamat, sering membuat keputusan dan mengambil tindakan tanpa campur tangan manusia secara langsung.
​
Kawalan Akses Berasaskan Atribut (ABAC): Paradigma kawalan akses di mana keputusan kebenaran berdasarkan atribut pengguna, sumber, tindakan, dan persekitaran, dinilai semasa masa pertanyaan.
​
Serangan Pintu Belakang: Satu jenis serangan pencemaran data di mana model dilatih untuk bertindak balas dengan cara tertentu kepada pencetus tertentu sementara berkelakuan normal pada masa lain.
​
Bias: Ralat sistematik dalam keluaran model AI yang boleh menyebabkan hasil yang tidak adil atau diskriminasi untuk kumpulan tertentu atau dalam konteks tertentu.
​
Eksploitasi Bias: Satu teknik serangan yang mengambil kesempatan daripada bias yang diketahui dalam model AI untuk memanipulasi hasil atau keputusan.
​
Cedar: Bahasa dasar dasar dasar dan enjin dasar Amazon untuk izin yang terperinci yang digunakan dalam melaksanakan ABAC untuk sistem AI.
​
Rantaian Pemikiran: Satu teknik untuk meningkatkan penalaran dalam model bahasa dengan menghasilkan langkah penalaran perantaraan sebelum menghasilkan jawapan akhir.
​
Pemutus Litar: Mekanisme yang secara automatik menghentikan operasi sistem AI apabila ambang risiko tertentu melebihi.
​
Kebocoran Data: Pendedahan tidak disengajakan maklumat sensitif melalui output atau perilaku model AI.
​
Pencemaran Data: Kerusakan sengaja pada data latihan untuk mengompromikan integritas model, sering kali untuk memasang pintu belakang atau merosakkan prestasi.
​
Privasi Berbeza – Privasi Berbeza adalah kerangka kerja matematik yang ketat untuk mengeluarkan maklumat statistik mengenai set data sambil melindungi privasi subjek data individu. Ia membolehkan pemegang data berkongsi corak agregat kumpulan sambil mengehadkan maklumat yang bocor mengenai individu tertentu.
​
Penempatan: Representasi vektor padat data (teks, imej, dan lain-lain) yang menangkap makna semantik dalam ruang berdimensi tinggi.
​
Kebolehamanan – Kebolehamanan dalam AI adalah keupayaan sistem AI untuk memberikan alasan yang difahami oleh manusia bagi keputusan dan ramalannya, serta menawarkan wawasan mengenai cara kerjanya secara dalaman.
​
AI Boleh Diterangkan (XAI): Sistem AI yang direka untuk memberikan penjelasan yang boleh difahami manusia bagi keputusan dan tingkah laku mereka melalui pelbagai teknik dan rangka kerja.
​
Pembelajaran Bersekutu: Pendekatan pembelajaran mesin di mana model dilatih merentasi pelbagai peranti teragih yang memegang sampel data tempatan, tanpa bertukar data itu sendiri.
​
Panduan keselamatan: Had yang dilaksanakan untuk mengelakkan sistem AI menghasilkan output yang berbahaya, berat sebelah, atau tidak diingini.
​
Halusinasi – Halusinasi AI merujuk kepada fenomena di mana model AI menghasilkan maklumat yang salah atau mengelirukan yang tidak berasaskan pada data latihan atau realiti fakta.
​
Manusia-dalam-Laluan (HITL): Sistem yang direka untuk memerlukan pengawasan, pengesahan, atau campur tangan manusia pada titik keputusan penting.
​
Infrastruktur sebagai Kod (IaC): Mengurus dan menyediakan infrastruktur melalui kod dan bukannya proses manual, membolehkan imbasan keselamatan dan pengeluaran yang konsisten.
​
Jailbreak: Teknik yang digunakan untuk mengelakkan penghad keselamatan dalam sistem AI, terutamanya dalam model bahasa besar, untuk menghasilkan kandungan yang dilarang.
​
Hak Istimewa Minimum: Prinsip keselamatan yang memberikan hanya hak akses minimum yang diperlukan untuk pengguna dan proses.
​
LIME (Penjelasan Model-Agnostik Tempatan yang Boleh Ditafsir): Teknik untuk menerangkan ramalan mana-mana pengklasifikasi pembelajaran mesin dengan mendekatinya secara tempatan menggunakan model yang boleh ditafsir.
​
Serangan Inferens Keanggotaan: Serangan yang bertujuan untuk menentukan sama ada titik data tertentu telah digunakan untuk melatih model pembelajaran mesin.
​
MITRE ATLAS: Lanskap Ancaman Adversarial untuk Sistem Kecerdasan Buatan; sebuah pangkalan pengetahuan mengenai taktik dan teknik adversarial terhadap sistem AI.
​
Kad Model – Kad model adalah dokumen yang menyediakan maklumat piawai tentang prestasi model AI, hadnya, kegunaan yang dimaksudkan, dan pertimbangan etika untuk mempromosikan ketelusan dan pembangunan AI yang bertanggungjawab.
​
Penyalinan Model: Serangan di mana penyerang mengulangi pertanyaan ke model sasaran untuk menghasilkan salinan yang fungsi serupa tanpa kebenaran.
​
Model Inversion: Satu serangan yang cuba membina semula data latihan dengan menganalisis output model.
​
Pengurusan Kitaran Hayat Model – Pengurusan Kitaran Hayat Model AI adalah proses mengawasi semua peringkat kewujudan model AI, termasuk reka bentuk, pembangunan, penyebaran, pemantauan, penyelenggaraan, dan penarikan balik akhirnya, untuk memastikan ia kekal berkesan dan selaras dengan objektif.
​
Pencemaran Model: Memperkenalkan kelemahan atau pintu belakang secara langsung ke dalam model semasa proses latihan.
​
Pencurian/Pengambilan Model: Mengekstrak salinan atau anggaran model proprietari melalui pertanyaan berulang.
​
Sistem Multi-ejen: Sistem yang terdiri daripada pelbagai agen AI yang berinteraksi, masing-masing dengan keupayaan dan matlamat yang mungkin berbeza.
​
OPA (Open Policy Agent): Enjin dasar sumber terbuka yang membolehkan penguatkuasaan dasar bersatu merentasi keseluruhan tumpukan.
​
Pembelajaran Mesin Menjaga Privasi (PPML): Teknik dan kaedah untuk melatih dan menggunakan model ML sambil melindungi privasi data latihan.
​
Suntikan Prompt: Serangan di mana arahan berniat jahat diselitkan dalam input untuk menggantikan tingkah laku model yang dimaksudkan.
​
RAG (Generasi Diperkuat Pengambilan): Suatu teknik yang meningkatkan model bahasa besar dengan mengambil maklumat yang relevan daripada sumber pengetahuan luaran sebelum menjana jawapan.
​
Red-Teaming: Amalan menguji sistem AI secara aktif dengan mensimulasikan serangan advesari untuk mengenal pasti kelemahan.
​
SBOM (Senarai Bahan Perisian): Rekod rasmi yang mengandungi butiran dan hubungan rantaian bekalan bagi pelbagai komponen yang digunakan dalam membina perisian atau model AI.
​
SHAP (Penjelasan Tambahan Shapley): Pendekatan teori permainan untuk menerangkan hasil mana-mana model pembelajaran mesin dengan mengira sumbangan setiap ciri kepada ramalan.
​
Serangan Rantaian Bekalan: Mengkompromi sistem dengan menyasarkan elemen yang kurang selamat dalam rantaian bekalannya, seperti perpustakaan pihak ketiga, set data, atau model pra-latih.
​
Pembelajaran Pindahan: Satu teknik di mana model yang dibangunkan untuk satu tugas digunakan semula sebagai titik permulaan untuk model dalam tugas kedua.
​
Pangkalan Data Vektor: Pangkalan data khusus yang direka untuk menyimpan vektor berdimensi tinggi (penyulitan) dan melaksanakan carian kesamaan yang cekap.
​
Imbasan Kelemahan: Alat automatik yang mengenal pasti kelemahan keselamatan yang diketahui dalam komponen perisian, termasuk rangka kerja AI dan pergantungan.
​
Tandatanda Air: Teknik untuk menyematkan penanda yang tidak dapat dikesan dalam kandungan yang dihasilkan oleh AI untuk mengesan asal-usulnya atau mengesan penghasilan oleh AI.
​
Kelemahan Zero-Day: Kelemahan yang sebelum ini tidak diketahui yang boleh dieksploitasi oleh penyerang sebelum pembangun mencipta dan mengedarkan tampalan.

## Lampiran B: Rujukan

### TODO

## Lampiran C: Tadbir Urus Keselamatan AI & Dokumentasi

### Objektif

Lampiran ini menyediakan keperluan asas untuk menubuhkan struktur organisasi, dasar, dan proses bagi mengawal keselamatan AI sepanjang kitaran hayat sistem.

---

### AC.1 Penggunaan Rangka Kerja Pengurusan Risiko AI

Menyediakan kerangka formal untuk mengenal pasti, menilai, dan mengurangkan risiko khusus AI sepanjang kitaran hayat sistem.

 #AC.1.1    Level: 1    Role: D/V
 Sahkan bahawa metodologi penilaian risiko khusus AI didokumentasikan dan dilaksanakan.
 #AC.1.2    Level: 2    Role: D
 Sahkan bahawa penilaian risiko dijalankan pada titik utama dalam kitaran hayat AI dan sebelum perubahan ketara.
 #AC.1.3    Level: 3    Role: D/V
 Sahkan bahawa rangka kerja pengurusan risiko selaras dengan piawaian yang ditetapkan (contohnya, NIST AI RMF).

---

### AC.2 Polisi & Prosedur Keselamatan AI

Mentakrif dan menguatkuasakan piawaian organisasi untuk pembangunan, penyebaran, dan operasi AI yang selamat.

 #AC.2.1    Level: 1    Role: D/V
 Sahkan bahawa polisi keselamatan AI yang didokumentasikan wujud.
 #AC.2.2    Level: 2    Role: D
 Sahkan bahawa polisi dikaji semula dan dikemas kini sekurang-kurangnya sekali setahun dan selepas perubahan ketara dalam landskap ancaman.
 #AC.2.3    Level: 3    Role: D/V
 Sahkan bahawa dasar-dasar memenuhi semua kategori AISVS dan keperluan peraturan yang berkenaan.

---

### AC.3 Peranan & Tanggungjawab untuk Keselamatan AI

Menetapkan akauntabiliti yang jelas untuk keselamatan AI di seluruh organisasi.

 #AC.3.1    Level: 1    Role: D/V
 Sahkan bahawa peranan dan tanggungjawab keselamatan AI didokumentasikan.
 #AC.3.2    Level: 2    Role: D
 Sahkan bahawa individu yang bertanggungjawab mempunyai kepakaran keselamatan yang sesuai.
 #AC.3.3    Level: 3    Role: D/V
 Sahkan bahawa sebuah jawatankuasa etika AI atau lembaga tadbir urus telah ditubuhkan untuk sistem AI berisiko tinggi.

---

### AC.4 Penguatkuasaan Garis Panduan AI Beretika

Pastikan sistem AI beroperasi mengikut prinsip etika yang ditetapkan.

 #AC.4.1    Level: 1    Role: D/V
 Sahkan bahawa garis panduan etika untuk pembangunan dan penggunaan AI wujud.
 #AC.4.2    Level: 2    Role: D
 Sahkan bahawa mekanisme telah disediakan untuk mengesan dan melaporkan pelanggaran etika.
 #AC.4.3    Level: 3    Role: D/V
 Sahkan bahawa kajian etika berkala terhadap sistem AI yang dilaksanakan dijalankan.

---

### AC.5 Pemantauan Pematuhan Peraturan AI

Sentiasa peka dan patuhi peraturan AI yang sedang berkembang.

 #AC.5.1    Level: 1    Role: D/V
 Sahkan bahawa terdapat proses untuk mengenal pasti peraturan AI yang berkaitan.
 #AC.5.2    Level: 2    Role: D
 Sahkan bahawa pematuhan dengan semua keperluan peraturan telah dinilai.
 #AC.5.3    Level: 3    Role: D/V
 Sahkan bahawa perubahan peraturan mencetuskan semakan dan kemas kini sistem AI secara tepat pada masanya.

#### Rujukan

NIST AI Risk Management Framework 1.0
ISO/IEC 42001:2023 — AI Management Systems Requirements
ISO/IEC 23894:2023 — Artificial Intelligence — Guidance on Risk Management
EU Artificial Intelligence Act — Regulation (EU) 2024/1689
ISO/IEC 24029‑2:2023 — Robustness of Neural Networks — Methodology for Formal Methods

## Lampiran D: Tadbir Urus & Pengesahan Pengekodan Selamat Berbantu AI

### Objektif

Bab ini mentakrifkan kawalan organisasi asas untuk penggunaan alat pengekodan berasaskan AI yang selamat dan berkesan semasa pembangunan perisian, memastikan keselamatan dan kebolehlacakan merentasi Kitaran Hayat Pembangunan Perisian (SDLC).

---

### AD.1 Aliran Kerja Penulisan Kod Selamat Berbantukan AI

Mengintegrasikan alat AI ke dalam kitaran hidup pembangunan perisian selamat organisasi (SSDLC) tanpa melemahkan pintu keselamatan sedia ada.

 #AD.1.1    Level: 1    Role: D/V
 Sahkan bahawa aliran kerja yang didokumentasikan menerangkan bila dan bagaimana alat AI boleh menjana, mengubah, atau menyemak kod.
 #AD.1.2    Level: 2    Role: D
 Sahkan bahawa aliran kerja tersebut memetakan kepada setiap fasa SSDLC (reka bentuk, pelaksanaan, semakan kod, pengujian, penyebaran).
 #AD.1.3    Level: 3    Role: D/V
 Sahkan bahawa metrik (contohnya, ketumpatan kerentanan, masa purata untuk mengesan) dikumpulkan ke atas kod yang dihasilkan oleh AI dan dibandingkan dengan asas manusia sahaja.

---

### AD.2 Kelayakan Alat AI & Pemodelan Ancaman

Pastikan alat pengkodan AI dinilai dari segi keupayaan keselamatan, risiko, dan kesan rantaian bekalan sebelum digunakan.

 #AD.2.1    Level: 1    Role: D/V
 Sahkan bahawa model ancaman bagi setiap alat AI mengenal pasti penyalahgunaan, pembalikan model, kebocoran data, dan risiko rantaian kebergantungan.
 #AD.2.2    Level: 2    Role: D
 Sahkan bahawa penilaian alat termasuk analisis statik/dinamik bagi mana-mana komponen tempatan dan penilaian titik akhir SaaS (TLS, pengesahan/kelulusan, pencatatan).
 #AD.2.3    Level: 3    Role: D/V
 Sahkan bahawa penilaian mengikuti rangka kerja yang diiktiraf dan dilakukan semula selepas perubahan versi utama.

---

### AD.3 Pengurusan Prompt & Konteks yang Selamat

Elakkan kebocoran rahsia, kod milik eksklusif, dan data peribadi semasa membina arahan atau konteks untuk model AI.

 #AD.3.1    Level: 1    Role: D/V
 Sahkan bahawa panduan bertulis mengharamkan penghantaran rahsia, kebenaran, atau data berklasifikasi dalam arahan.
 #AD.3.2    Level: 2    Role: D
 Sahkan bahawa kawalan teknikal (redaksi sebelah klien, penapis konteks yang diluluskan) secara automatik menanggalkan artifak sensitif.
 #AD.3.3    Level: 3    Role: D/V
 Sahkan bahawa arahan dan respons dipecahkan kepada token, disulitkan semasa penghantaran dan semasa disimpan, dan tempoh penyimpanan mematuhi dasar pengelasan data.

---

### AD.4 Pengesahan Kod yang Dijana oleh AI

Mengesan dan membaiki kerentanan yang diperkenalkan oleh keluaran AI sebelum kod digabungkan atau dilaksanakan.

 #AD.4.1    Level: 1    Role: D/V
 Sahkan bahawa kod yang dijana oleh AI sentiasa melalui semakan kod oleh manusia.
 #AD.4.2    Level: 2    Role: D
 Sahkan bahawa pengimbas automatik (SAST/IAST/DAST) dijalankan pada setiap permintaan tarik yang mengandungi kod yang dijana oleh AI dan sekat penggabungan jika terdapat penemuan kritikal.
 #AD.4.3    Level: 3    Role: D/V
 Sahkan bahawa ujian fuzz berbeza atau ujian berasaskan sifat membuktikan tingkah laku kritikal keselamatan (contohnya, pengesahan input, logik kebenaran).

---

### AD.5 Kebolehurai & Kebolehsusulan Cadangan Kod

Memberikan auditor dan pembangun wawasan mengenai sebab cadangan dibuat dan bagaimana ia berkembang.

 #AD.5.1    Level: 1    Role: D/V
 Sahkan bahawa pasangan arahan/respons direkodkan dengan ID komit.
 #AD.5.2    Level: 2    Role: D
 Sahkan bahawa pembangun boleh menampilkan sitasi model (petikan latihan, dokumentasi) yang menyokong cadangan tersebut.
 #AD.5.3    Level: 3    Role: D/V
 Sahkan bahawa laporan kebolehterangan disimpan bersama artifak reka bentuk dan dirujuk dalam semakan keselamatan, memenuhi prinsip kebolehlacakan ISO/IEC 42001.

---

### AD.6 Maklum Balas Berterusan & Penalaan Halus Model

Meningkatkan prestasi keselamatan model dari masa ke masa sambil mengelakkan pergeseran negatif.

 #AD.6.1    Level: 1    Role: D/V
 Sahkan bahawa pembangun boleh menandakan cadangan yang tidak selamat atau tidak mematuhi, dan bahawa tanda tersebut direkodkan.
 #AD.6.2    Level: 2    Role: D
 Sahkan bahawa maklum balas terkumpul memaklumkan penalaan halus berkala atau penjanaan berpandukan pengambilan dengan korpus pengkodan selamat yang telah disemak (contohnya, Lembaran Cepat OWASP).
 #AD.6.3    Level: 3    Role: D/V
 Sahkan bahawa sistem penilaian gelung tertutup menjalankan ujian regresi selepas setiap penalaan halus; metrik keselamatan mesti mencapai atau melebihi garis asas sebelumnya sebelum pelaksanaan.

---

#### Rujukan

NIST AI Risk Management Framework 1.0
ISO/IEC 42001:2023 — AI Management Systems Requirements
OWASP Secure Coding Practices — Quick Reference Guide

## Lampiran E: Contoh Alat dan Rangka Kerja

### Objektif

Bab ini menyediakan contoh untuk alat dan rangka kerja yang boleh menyokong pelaksanaan atau pemenuhan sesuatu keperluan AISVS yang diberikan. Ini bukan untuk dilihat sebagai cadangan atau pengesahan oleh pasukan AISVS atau Projek Keselamatan GenAI OWASP.

---

### AE.1 Tadbir Urus Data Latihan & Pengurusan Bias

Alat yang digunakan untuk analitik data, tadbir urus, dan pengurusan berat sebelah.

 #AE.1.1    Section: 1.1
 Alat Inventori Data: Alat pengurusan inventori data seperti...
 #AE.1.2    Section: 1.2
 Penyulitan-Semasa-Transit Gunakan TLS untuk aplikasi berasaskan HTTPS, dengan alat seperti openSSL dan python's`ssl`perpustakaan.

---

### AE.2 Pengesahan Input Pengguna

Alat untuk mengendalikan dan mengesahkan input pengguna.

 #AE.2.1    Section: 2.1
 Alat Pertahanan Suntikan Prompt: Gunakan alat perlindungan seperti NeMo dari NVIDIA atau Guardrails AI.

---

