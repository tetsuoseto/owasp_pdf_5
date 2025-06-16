# 10 Ketahanan Advèrsarial & Perlindungan Privasi

## Objektif Kawalan

Pastikan model AI kekal boleh dipercayai, melindungi privasi, dan tahan terhadap penyalahgunaan apabila berdepan serangan pengelakan, inferens, ekstraksi, atau pencemaran.

---

## 10.1 Penjajaran Model & Keselamatan

Lindungi daripada output yang berbahaya atau melanggar polisi.

|   #    | Description                                                                                                                                                             | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 10.1.1 | Sahkan bahawa set ujian penjajaran (prompts pasukan merah, sondaj jailbreak, kandungan yang tidak dibenarkan) dikawal versi dan dijalankan pada setiap pelepasan model. |   1   | D/V  |
| 10.1.2 | Sahkan bahawa penguatkuasaan penolakan dan pengawal selamat-penyelesaian dilaksanakan.                                                                                  |   1   |  D   |
| 10.1.3 | Sahkan bahawa penilai automatik mengukur kadar kandungan berbahaya dan menandakan regresi yang melebihi ambang yang ditetapkan.                                         |   2   | D/V  |
| 10.1.4 | Sahkan bahawa latihan penentangan jailbreak didokumentasikan dan boleh dihasilkan semula.                                                                               |   2   |  D   |
| 10.1.5 | Sahkan bahawa bukti pematuhan dasar formal atau pemantauan yang disahkan merangkumi domain kritikal.                                                                    |   3   |  V   |

---

## 10.2 Pengukuhan Contoh Adversarial

Meningkatkan ketahanan terhadap input yang dimanipulasi. Latihan adversarial yang kukuh dan penilaian penanda aras adalah amalan terbaik semasa.

|   #    | Description                                                                                                              | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 10.2.1 | Sahkan bahawa repositori projek termasuk konfigurasi latihan adversarial dengan benih yang boleh dihasilkan semula.      |   1   |  D   |
| 10.2.2 | Sahkan bahawa pengesanan contoh-adversarial mengeluarkan amaran penyekatan dalam aliran pengeluaran.                     |   2   | D/V  |
| 10.2.4 | Sahkan bahawa bukti ketahanan bersijil atau sijil had selang meliputi sekurang-kurangnya kelas kritikal teratas.         |   3   |  V   |
| 10.2.5 | Sahkan bahawa ujian regresi menggunakan serangan adaptif untuk mengesahkan tiada kehilangan ketahanan yang dapat diukur. |   3   |  V   |

---

## 10.3 Mitigasi Inferens Keanggotaan

Hadkan keupayaan untuk menentukan sama ada rekod tersebut terdapat dalam data latihan. Privasi berbeza dan penyamaran skor keyakinan kekal sebagai pertahanan paling berkesan yang diketahui.

|   #    | Description                                                                                                                            | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 10.3.1 | Sahkan bahawa pengawalan entropi setiap pertanyaan atau penskalaan suhu mengurangkan ramalan yang terlalu yakin.                       |   1   |  D   |
| 10.3.2 | Sahkan bahawa latihan menggunakan pengoptimuman privasi-diferensial terhad ε untuk set data sensitif.                                  |   2   |  D   |
| 10.3.3 | Sahkan bahawa simulasi serangan (model bayangan atau kotak hitam) menunjukkan AUC serangan ≤ 0.60 pada data yang disimpan untuk ujian. |   2   |  V   |

---

## 10.4 Ketahanan Terhadap Penukaran Model

Menghalang pembinaan semula atribut peribadi. Kajian terkini menekankan pemotongan output dan jaminan DP sebagai pertahanan praktikal.

|   #    | Description                                                                                                                       | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 10.4.1 | Sahkan bahawa atribut sensitif tidak pernah dipaparkan secara langsung; jika perlu, gunakan kumpulan atau transformasi satu-arah. |   1   |  D   |
| 10.4.2 | Sahkan bahawa had kadar pertanyaan menghadkan pertanyaan adaptif berulang dari pihak utama yang sama.                             |   1   | D/V  |
| 10.4.3 | Sahkan bahawa model dilatih dengan bunyi pemeliharaan privasi.                                                                    |   2   |  D   |

---

## 10.5 Pertahanan Ekstraksi Model

Mengesan dan menghalang penyalinan tanpa kebenaran. Penandaan air dan analisis corak pertanyaan disyorkan.

|   #    | Description                                                                                                                                 | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 10.5.1 | Sahkan bahawa pintu masuk inferens menegakkan had kadar global dan setiap kekunci API yang disesuaikan dengan ambang pengingatan model.     |   1   |  D   |
| 10.5.2 | Sahkan bahawa statistik entropi pertanyaan dan pluraliti input memberi isyarat kepada pengesan ekstraksi automatik.                         |   2   | D/V  |
| 10.5.3 | Sahkan bahawa tanda air yang rapuh atau probabilistik boleh dibuktikan dengan p < 0.01 dalam ≤ 1 000 pertanyaan terhadap klon yang disyaki. |   2   |  V   |
| 10.5.4 | Sahkan bahawa kekunci tanda air dan set pencetus disimpan dalam modul keselamatan perkakasan dan dipusingkan setiap tahun.                  |   3   |  D   |
| 10.5.5 | Sahkan bahawa acara extraction-alert termasuk pertanyaan yang melanggar dan diintegrasikan dengan buku panduan tindak balas insiden.        |   3   |  V   |

---

## 10.6 Pengesanan Data Beracun Masa Inferens

Kenal pasti dan neutralisasi input yang telah dipasangkan pintu belakang atau diracun.

|   #    | Description                                                                                                                | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 10.6.1 | Sahkan bahawa input melalui pengesan anomali (contoh, STRIP, penilaian konsistensi) sebelum inferens model.                |   1   |  D   |
| 10.6.2 | Sahkan bahawa ambang pengesan diselaraskan pada set pengesahan bersih/beracun untuk mencapai kurang dari 5% positif palsu. |   1   |  V   |
| 10.6.3 | Sahkan bahawa input yang ditandakan sebagai tercemar mencetuskan pemblokiran lembut dan aliran kerja semakan manusia.      |   2   |  D   |
| 10.6.4 | Sahkan bahawa pengesan diuji tekanan dengan serangan pintu belakang adaptif tanpa pencetus.                                |   2   |  V   |
| 10.6.5 | Sahkan bahawa metrik keberkesanan pengesanan direkodkan dan dinilai semula secara berkala dengan intel ancaman terkini.    |   3   |  D   |

---

## 10.7 Penyesuaian Dasar Keselamatan Dinamik

Kemas kini dasar keselamatan masa nyata berdasarkan maklumat ancaman dan analisis tingkah laku.

|   #    | Description                                                                                                                                     | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 10.7.1 | Sahkan bahawa polisi keselamatan boleh dikemas kini secara dinamik tanpa perlu memulakan semula ejen sambil mengekalkan integriti versi polisi. |   1   | D/V  |
| 10.7.2 | Sahkan bahawa kemas kini dasar ditandatangani secara kriptografi oleh kakitangan keselamatan yang diberi kuasa dan disahkan sebelum diterapkan. |   2   | D/V  |
| 10.7.3 | Sahkan bahawa perubahan dasar dinamik direkodkan dengan jejak audit penuh termasuk justifikasi, rantai kelulusan, dan prosedur pemulihan.       |   2   | D/V  |
| 10.7.4 | Sahkan bahawa mekanisme keselamatan adaptif menyesuaikan kepekaan pengesanan ancaman berdasarkan konteks risiko dan corak tingkah laku.         |   3   | D/V  |
| 10.7.5 | Sahkan bahawa keputusan penyesuaian polisi boleh diterangkan dan disertakan dengan jejak bukti untuk semakan pasukan keselamatan.               |   3   | D/V  |

---

## 10.8 Analisis Keselamatan Berdasarkan Refleksi

Pengesahan keselamatan melalui refleksi diri agen dan analisis meta-kognitif.

|   #    | Description                                                                                                                                     | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 10.8.1 | Sahkan bahawa mekanisme refleksi agen termasuk penilaian kendiri berfokus keselamatan terhadap keputusan dan tindakan.                          |   1   | D/V  |
| 10.8.2 | Sahkan bahawa output pantulan disahkan untuk mengelakkan manipulasi mekanisme penilaian kendiri oleh input musuh.                               |   2   | D/V  |
| 10.8.3 | Sahkan bahawa analisis keselamatan meta-kognitif mengenal pasti potensi bias, manipulasi, atau kompromi dalam proses penaakulan agen.           |   2   | D/V  |
| 10.8.4 | Sahkan bahawa amaran keselamatan berasaskan pantulan mencetuskan pemantauan dipertingkatkan dan kemungkinan aliran kerja campur tangan manusia. |   3   | D/V  |
| 10.8.5 | Sahkan bahawa pembelajaran berterusan daripada refleksi keselamatan meningkatkan pengesanan ancaman tanpa menjejaskan fungsi sah.               |   3   | D/V  |

---

## 10.9 Keselamatan Evolusi & Penambahbaikan Diri

Kawalan keselamatan untuk sistem ejen yang mampu mengubah suai diri dan evolusi.

|   #    | Description                                                                                                                       | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 10.9.1 | Sahkan bahawa keupayaan pengubahsuaian sendiri dihadkan kepada kawasan selamat yang ditetapkan dengan sempadan pengesahan formal. |   1   | D/V  |
| 10.9.2 | Sahkan bahawa cadangan evolusi menjalani penilaian impak keselamatan sebelum pelaksanaan.                                         |   2   | D/V  |
| 10.9.3 | Sahkan bahawa mekanisme peningkatan kendiri termasuk keupayaan pengembalian dengan pengesahan integriti.                          |   2   | D/V  |
| 10.9.4 | Sahkan bahawa keselamatan meta-pembelajaran menghalang manipulasi adversarial terhadap algoritma peningkatan.                     |   3   | D/V  |
| 10.9.5 | Sahkan bahawa peningkatan kendiri rekursif dibatasi oleh kekangan keselamatan formal dengan bukti matematik tentang konvergensi.  |   3   | D/V  |

---

### Rujukan

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

