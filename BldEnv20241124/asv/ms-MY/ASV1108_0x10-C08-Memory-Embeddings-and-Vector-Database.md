# Keselamatan Memori C8, Embedding & Pangkalan Data Vektor

## Objektif Kawalan

Embedding dan penyimpanan vektor berfungsi sebagai "memori langsung" sistem AI kontemporari, sentiasa menerima data yang disediakan pengguna dan memaparkannya kembali ke dalam konteks model melalui Penjanaan Dipertingkatkan Pengambilan (RAG). Jika tidak dikawal, memori ini boleh membocorkan Maklumat Peribadi yang Boleh Dikenal Pasti (PII), melanggar persetujuan, atau dibalikkan untuk membina semula teks asal. Objektif keluarga kawalan ini adalah untuk mengukuhkan saluran memori dan pangkalan data vektor supaya akses adalah berdasarkan keistimewaan minimum, embedding menjaga privasi, vektor yang disimpan tamat tempoh atau boleh dibatalkan mengikut permintaan, dan memori per pengguna tidak pernah mencemari prompt atau penyelesaian pengguna lain.

---

## C8.1 Kawalan Akses pada Memori & Indeks RAG

Laksanakan kawalan akses terperinci pada setiap koleksi vektor.

|   #   | Description                                                                                                                                                     | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 8.1.1 | Sahkan bahawa peraturan kawalan akses pada tahap baris/ruang nama mengehadkan operasi sisip, padam, dan pertanyaan mengikut penyewa, koleksi, atau tag dokumen. |   1   | D/V  |
| 8.1.2 | Sahkan bahawa kunci API atau JWT membawa tuntutan berfokus (contohnya, ID koleksi, kata kerja tindakan) dan diputar sekurang-kurangnya setiap suku tahun.       |   1   | D/V  |
| 8.1.3 | Sahkan bahawa cubaan peningkatan keistimewaan (contohnya, pertanyaan kesamaan rentas-ruang nama) dikesan dan direkodkan ke dalam SIEM dalam masa 5 minit.       |   2   | D/V  |
| 8.1.4 | Sahkan bahawa pangkalan data vektor merekod log pengecam subjek, operasi, ID vektor/nama ruang, ambang kesamaan, dan kiraan keputusan.                          |   2   | D/V  |
| 8.1.5 | Sahkan bahawa keputusan akses diuji untuk kelemahan pengelakan setiap kali enjin dinaik taraf atau peraturan pemecahan indeks berubah.                          |   3   |  V   |

---

## C8.2 Penyahcemaran dan Pengesahan Penanaman

Prakata teks untuk PII, sembunyikan atau pseudonimkan sebelum pektorasi, dan secara pilihan proses selepas embeding untuk membuang isyarat residu.

|   #   | Description                                                                                                                                                                                      | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 8.2.1 | Sahkan bahawa PII dan data terkawal dikesan melalui pengelasan automatik dan disembunyikan, ditokenkan, atau dibuang sebelum penempatan.                                                         |   1   | D/V  |
| 8.2.2 | Sahkan bahawa saluran alur sesaran menolak atau mengasingkan input yang mengandungi kod boleh laksana atau artifak bukan UTF-8 yang berpotensi mencemarkan indeks.                               |   1   |  D   |
| 8.2.3 | Sahkan bahawa sanitasi privasi-diferensial tempatan atau metrik digunakan pada pengewangan ayat yang jaraknya kepada mana-mana token PII yang diketahui jatuh di bawah ambang boleh konfigurasi. |   2   | D/V  |
| 8.2.4 | Sahkan bahawa keberkesanan sanitasi (contohnya, pengesanan semula penyuntingan PII, pergeseran semantik) disahkan sekurang-kurangnya dua kali setahun menggunakan korpora penanda aras.          |   2   |  V   |
| 8.2.5 | Sahkan bahawa konfigurasi sanitasi dikawal versi dan perubahan menjalani semakan rakan sebaya.                                                                                                   |   3   | D/V  |

---

## C8.3 Luput Memori, Pembatalan & Pemadaman

GDPR "hak untuk dilupakan" dan undang-undang serupa memerlukan pemadaman yang tepat pada masanya; stor vektor oleh itu mesti menyokong TTL, pemadaman keras, dan sistem penanda kubur supaya vektor yang dibatalkan tidak boleh dipulihkan atau diindeks semula.

|   #   | Description                                                                                                                                              | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 8.3.1 | Sahkan bahawa setiap vektor dan rekod metadata membawa TTL atau label pengekalan eksplisit yang dihormati oleh tugas pembersihan automatik.              |   1   | D/V  |
| 8.3.2 | Sahkan bahawa permintaan penghapusan yang dimulakan pengguna membersihkan vektor, metadata, salinan cache, dan indeks turunan dalam masa 30 hari.        |   1   | D/V  |
| 8.3.3 | Sahkan bahawa penghapusan logik diikuti dengan pemusnahan kriptografi blok storan jika perkakasan menyokongnya, atau dengan pemusnahan kunci peti kunci. |   2   |  D   |
| 8.3.4 | Sahkan bahawa vektor yang telah tamat tempoh dikecualikan daripada keputusan carian jiran terdekat dalam masa < 500 ms selepas tamat tempoh.             |   3   | D/V  |

---

## C8.4 Mencegah Pembalikan & Kebocoran Embedding

Pertahanan terkini—superposisi bunyi, rangkaian proyeksi, gangguan neuron privasi, dan penyulitan lapisan aplikasi—boleh mengurangkan kadar terbalik tahap token ke bawah 5%.

|   #   | Description                                                                                                                                                                 | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 8.4.1 | Sahkan bahawa model ancaman formal yang merangkumi serangan pembalikan, keahlian dan inferens atribut wujud dan disemak setiap tahun.                                       |   1   |  V   |
| 8.4.2 | Sahkan bahawa penyulitan lapisan aplikasi atau penyulitan boleh dicari melindungi vektor daripada dibaca secara langsung oleh pentadbir infrastruktur atau kakitangan awan. |   2   | D/V  |
| 8.4.3 | Sahkan bahawa parameter pertahanan (ε untuk DP, bunyi σ, pangkat unjuran k) mengimbangi privasi ≥ 99% perlindungan token dan kebolehgunaan ≤ 3% kehilangan ketepatan.       |   3   |  V   |
| 8.4.4 | Sahkan bahawa metrik ketahanan songsang merupakan sebahagian daripada pintu pelepasan untuk kemas kini model, dengan belanjawan regresi yang ditetapkan.                    |   3   | D/V  |

---

## C8.5 Penguatkuasaan Skop untuk Memori Spesifik Pengguna

Kebocoran merentas penyewa kekal sebagai risiko RAG utama: pertanyaan keserupaan yang disaring dengan tidak betul boleh mendedahkan dokumen peribadi pelanggan lain.

|   #   | Description                                                                                                                                                     | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 8.5.1 | Sahkan bahawa setiap pertanyaan pengambilan disaring selepas oleh ID penyewa/pengguna sebelum diserahkan kepada arahan LLM.                                     |   1   | D/V  |
| 8.5.2 | Sahkan bahawa nama koleksi atau ID berjenama diberi garam mengikut pengguna atau penyewa supaya vektor tidak boleh bertindih merentas skop.                     |   1   |  D   |
| 8.5.3 | Sahkan bahawa keputusan keserupaan di atas ambang jarak yang boleh dikonfigurasi tetapi di luar skop pemanggil akan dibuang dan mencetuskan amaran keselamatan. |   2   | D/V  |
| 8.5.4 | Sahkan bahawa ujian tekanan pelbagai penyewa mensimulasikan pertanyaan adversarial yang cuba mendapatkan dokumen di luar skop dan menunjukkan tiada kebocoran.  |   2   |  V   |
| 8.5.5 | Sahkan bahawa kekunci penyulitan dipisahkan untuk setiap penyewa, memastikan pengasingan kriptografi walaupun storan fizikal dikongsi.                          |   3   | D/V  |

---

## C8.6 Keselamatan Sistem Memori Lanjutan

Kawalan keselamatan untuk seni bina memori yang canggih termasuk memori episodik, semantik, dan kerja dengan keperluan pengasingan dan pengesahan khusus.

|   #   | Description                                                                                                                                                                                                                                                   | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 8.6.1 | Sahkan bahawa jenis-jenis memori yang berbeza (episodik, semantik, kerja) mempunyai konteks keselamatan yang terasing dengan kawalan akses berasaskan peranan, kunci penyulitan yang berasingan, dan corak akses yang didokumenkan untuk setiap jenis memori. |   1   | D/V  |
| 8.6.2 | Sahkan bahawa proses pemadatan memori termasuk pengesahan keselamatan untuk mengelakkan penyisipan memori berniat jahat melalui pensanitasi kandungan, pengesahan sumber, dan pemeriksaan integriti sebelum penyimpanan.                                      |   2   | D/V  |
| 8.6.3 | Sahkan bahawa pertanyaan pengambilan memori disahkan dan disanitasi untuk mengelakkan pengekstrakan maklumat yang tidak dibenarkan melalui analisis corak pertanyaan, penguatkuasaan kawalan akses, dan penapisan keputusan.                                  |   2   | D/V  |
| 8.6.4 | Sahkan bahawa mekanisme pelupusan memori memadam maklumat sensitif dengan selamat menggunakan jaminan pemadaman kriptografi melalui penghapusan kunci, penimpaan berbilang laluan, atau pemadaman selamat berasaskan perkakasan dengan sijil pengesahan.      |   3   | D/V  |
| 8.6.5 | Sahkan bahawa integriti sistem memori sentiasa dipantau untuk pengubahsuaian atau kerosakan yang tidak dibenarkan melalui checksum, log audit, dan amaran automatik apabila kandungan memori berubah di luar operasi biasa.                                   |   3   | D/V  |

---

## Rujukan

* [Vector database security: Pinecone – IronCore Labs](https://ironcorelabs.com/vectordbs/pinecone-security/)
* [Securing the Backbone of AI: Safeguarding Vector Databases and Embeddings – Privacera](https://privacera.com/blog/securing-the-backbone-of-ai-safeguarding-vector-databases-and-embeddings/)
* [Enhancing Data Security with RBAC of Qdrant Vector Database – AI Advances](https://ai.gopubby.com/enhancing-data-security-with-role-based-access-control-of-qdrant-vector-database-3878769bec83)
* [Mitigating Privacy Risks in LLM Embeddings from Embedding Inversion – arXiv](https://arxiv.org/html/2411.05034v1)
* [DPPN: Detecting and Perturbing Privacy-Sensitive Neurons – OpenReview](https://openreview.net/forum?id=DF5TVzpTW0)
* [Art. 17 GDPR – Right to Erasure](https://gdpr-info.eu/art-17-gdpr/)
* [Sensitive Data in Text Embeddings Is Recoverable – Tonic.ai](https://www.tonic.ai/blog/sensitive-data-in-text-embeddings-is-recoverable)
* [PII Identification and Removal – NVIDIA NeMo Docs](https://docs.nvidia.com/nemo-framework/user-guide/latest/datacuration/personalidentifiableinformationidentificationandremoval.html)
* [De-identifying Sensitive Data – Google Cloud DLP](https://cloud.google.com/sensitive-data-protection/docs/deidentify-sensitive-data)
* [Remove PII from Conversations Using Sensitive Information Filters – AWS Bedrock Guardrails](https://docs.aws.amazon.com/bedrock/latest/userguide/guardrails-sensitive-filters.html)
* [Think Your RAG Is Secure? Think Again – Medium](https://medium.com/%40vijay.poudel1/think-your-rag-is-secure-think-again-heres-how-to-actually-lock-it-down-c4c30e3864e7)
* [Design a Secure Multitenant RAG Inferencing Solution – Microsoft Learn](https://learn.microsoft.com/en-us/azure/architecture/ai-ml/guide/secure-multitenant-rag)
* [Best Practices for Multi-Tenancy RAG with Milvus – Milvus Blog](https://milvus.io/blog/build-multi-tenancy-rag-with-milvus-best-practices-part-one.md)

