# 11 Perlindungan Privasi & Pengurusan Data Peribadi

## Objektif Kawalan

Menjaga jaminan privasi yang ketat sepanjang kitaran hayat AI—pengumpulan, latihan, inferens, dan tindak balas insiden—supaya data peribadi hanya diproses dengan kebenaran yang jelas, skop minimum yang diperlukan, penghapusan yang boleh dibuktikan, dan jaminan privasi yang formal.

---

## 11.1 Anonimisasi & Meminimumkan Data

|   #    | Description                                                                                                                             | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 11.1.1 | Sahkan bahawa pengenal terus dan quasi-pengenal telah dialih keluar atau dihash.                                                        |   1   | D/V  |
| 11.1.2 | Sahkan bahawa audit automatik mengukur k-anonimitas/l-diversiti dan memberi amaran apabila ambang jatuh di bawah dasar.                 |   2   | D/V  |
| 11.1.3 | Sahkan bahawa laporan kepentingan ciri model membuktikan tiada kebocoran pengecam melepasi ε = 0.01 maklumat bersama.                   |   2   |  V   |
| 11.1.4 | Sahkan bahawa bukti formal atau pensijilan data sintetik menunjukkan risiko pengenalan semula ≤ 0.05 walaupun di bawah serangan pautan. |   3   |  V   |

---

## 11.2 Hak untuk Dilupakan & Penguatkuasaan Pemadaman

|   #    | Description                                                                                                                                                                               | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 11.2.1 | Sahkan bahawa permintaan penghapusan subjek data tersebar kepada set data mentah, penanda aras, penanaman, log, dan sandaran dalam perjanjian tahap perkhidmatan kurang daripada 30 hari. |   1   | D/V  |
| 11.2.2 | Sahkan bahawa rutin "machine-unlearning" secara fizikal melatih semula atau menganggar penghapusan menggunakan algoritma pembelajaran terhapus yang diperakui.                            |   2   |  D   |
| 11.2.3 | Sahkan bahawa penilaian model bayangan membuktikan rekod yang dilupakan mempengaruhi kurang daripada 1% keluaran selepas proses pelupusan pengetahuan.                                    |   2   |  V   |
| 11.2.4 | Sahkan bahawa kejadian pemadaman direkodkan secara tidak boleh diubah dan boleh diaudit untuk pihak pengawalselia.                                                                        |   3   |  V   |

---

## 11.3 Perlindungan Privasi Berbeza

|   #    | Description                                                                                                              | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 11.3.1 | Sahkan bahawa papan pemuka pengiraan kehilangan privasi memberi amaran apabila nilai kumulatif ε melebihi ambang polisi. |   2   | D/V  |
| 11.3.2 | Sahkan bahawa audit privasi kotak hitam menganggarkan ε̂ dalam lingkungan 10% daripada nilai yang diisytiharkan.         |   2   |  V   |
| 11.3.3 | Sahkan bahawa bukti formal merangkumi semua penalaan halus dan penanaman selepas latihan.                                |   3   |  V   |

---

## 11.4 Had Tujuan & Perlindungan daripada Perluasan Skop

|   #    | Description                                                                                                                                   | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 11.4.1 | Sahkan bahawa setiap set data dan penanda titik model mempunyai tag tujuan yang boleh dibaca mesin yang selaras dengan persetujuan asal.      |   1   |  D   |
| 11.4.2 | Sahkan bahawa pemantau masa jalan mengesan pertanyaan yang tidak konsisten dengan tujuan yang diisytiharkan dan mencetuskan penolakan lembut. |   1   | D/V  |
| 11.4.3 | Sahkan bahawa gerbang polisi-sebagai-kod menghalang penyebaran semula model ke domain baru tanpa semakan DPIA.                                |   3   |  D   |
| 11.4.4 | Sahkan bahawa bukti kebolehlacakan formal menunjukkan setiap kitaran hayat data peribadi kekal dalam skop yang telah diberikan persetujuan.   |   3   |  V   |

---

## 11.5 Pengurusan Persetujuan & Penjejakan Asas Perundangan

|   #    | Description                                                                                                                                | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 11.5.1 | Sahkan bahawa Platform Pengurusan Persetujuan (CMP) merekodkan status pilih masuk, tujuan, dan tempoh penyimpanan bagi setiap subjek data. |   1   | D/V  |
| 11.5.2 | Sahkan bahawa API mendedahkan token persetujuan; model mesti mengesahkan skop token sebelum inferens.                                      |   2   |  D   |
| 11.5.3 | Sahkan bahawa persetujuan yang ditolak atau ditarik balik menghentikan saluran pemprosesan dalam masa 24 jam.                              |   2   | D/V  |

---

## 11.6 Pembelajaran Federasi dengan Kawalan Privasi

|   #    | Description                                                                                                | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 11.6.1 | Sahkan bahawa kemas kini klien menggunakan penambahan bunyi privasi berbeza setempat sebelum penggabungan. |   1   |  D   |
| 11.6.2 | Sahkan bahawa metrik latihan adalah peribadi berbeza dan tidak pernah mendedahkan kerugian klien tunggal.  |   2   | D/V  |
| 11.6.3 | Sahkan bahawa pengagregatan tahan keracunan (contohnya, Krum/Trimmed-Mean) diaktifkan.                     |   2   |  V   |
| 11.6.4 | Sahkan bahawa bukti formal menunjukkan keseluruhan bajet ε dengan kehilangan utiliti kurang daripada 5.    |   3   |  V   |

---

### Rujukan

* [GDPR & AI Compliance Best Practices](https://www.exabeam.com/explainers/gdpr-compliance/the-intersection-of-gdpr-and-ai-and-6-compliance-best-practices/)
* [EU Parliament Study on GDPR & AI, 2020](https://www.europarl.europa.eu/RegData/etudes/STUD/2020/641530/EPRS_STU%282020%29641530_EN.pdf)
* [ISO 31700-1:2023 — Privacy by Design for Consumer Products](https://www.iso.org/standard/84977.html)
* [NIST Privacy Framework 1.1 (2025 Draft)](https://www.nist.gov/privacy-framework)
* [Machine Unlearning: Right-to-Be-Forgotten Techniques](https://www.kaggle.com/code/tamlhp/machine-unlearning-the-right-to-be-forgotten)
* [A Survey of Machine Unlearning, 2024](https://arxiv.org/html/2209.02299v6)
* [Auditing DP-SGD — ArXiv 2024](https://arxiv.org/html/2405.14106v4)
* [DP-SGD Explained — PyTorch Blog](https://medium.com/pytorch/differential-privacy-series-part-1-dp-sgd-algorithm-explained-12512c3959a3)
* [Purpose-Limitation for AI — IJLIT 2025](https://academic.oup.com/ijlit/article/doi/10.1093/ijlit/eaaf003/8121663)
* [Data-Protection Considerations for AI — URM Consulting](https://www.urmconsulting.com/blog/data-protection-considerations-for-artificial-intelligence-ai)
* [Top Consent-Management Platforms, 2025](https://www.enzuzo.com/blog/best-consent-management-platforms)
* [Secure Aggregation in DP Federated Learning — ArXiv 2024](https://arxiv.org/abs/2407.19286)

