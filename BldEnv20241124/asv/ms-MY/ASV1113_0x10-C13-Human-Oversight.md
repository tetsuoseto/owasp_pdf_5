# C13 Pengawasan Manusia, Akauntabiliti & Tadbir Urus

## Objektif Kawalan

Bab ini menyediakan keperluan untuk mengekalkan pengawasan manusia dan rantai akauntabiliti yang jelas dalam sistem AI, memastikan keterjelasan, ketelusan, dan pengurusan etika sepanjang kitaran hayat AI.

---

## C13.1 Mekanisme Kill-Switch & Override

Sediakan laluan penutupan atau pemulihan apabila tingkah laku tidak selamat sistem AI diperhatikan.

|   #    | Description                                                                                                   | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 13.1.1 | Sahkan bahawa wujud mekanisme suis berhenti manual untuk segera menghentikan inferens model AI dan outputnya. |   1   | D/V  |
| 13.1.2 | Sahkan bahawa kawalan override hanya boleh diakses oleh kakitangan yang diberi kuasa.                         |   1   |  D   |
| 13.1.3 | Sahkan bahawa prosedur rollback boleh memulihkan versi model sebelumnya atau operasi mod selamat.             |   3   | D/V  |
| 13.1.4 | Sahkan bahawa mekanisme override diuji secara berkala.                                                        |   3   |  V   |

---

## C13.2 Titik Pemeriksaan Keputusan Manusia-Dalam-Lingkaran

Memerlukan kelulusan manusia apabila risiko melebihi ambang risiko yang telah ditetapkan.

|   #    | Description                                                                                                                                                      | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 13.2.1 | Sahkan bahawa keputusan AI berisiko tinggi memerlukan kelulusan manusia yang jelas sebelum pelaksanaan.                                                          |   1   | D/V  |
| 13.2.2 | Sahkan bahawa ambang risiko ditakrifkan dengan jelas dan secara automatik mencetuskan aliran kerja semakan manusia.                                              |   1   |  D   |
| 13.2.3 | Sahkan bahawa keputusan yang sensitif kepada masa mempunyai prosedur sandaran apabila kelulusan manusia tidak dapat diperoleh dalam jangka masa yang diperlukan. |   2   |  D   |
| 13.2.4 | Sahkan bahawa prosedur eskalasi menetapkan tahap kuasa yang jelas untuk jenis keputusan yang berbeza atau kategori risiko, jika berkenaan.                       |   3   | D/V  |

---

## C13.3 Rantaian Tanggungjawab & Kebolehcapaian Audit

Catat tindakan operator dan keputusan model.

|   #    | Description                                                                                                                              | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 13.3.1 | Sahkan bahawa semua keputusan sistem AI dan campur tangan manusia direkodkan dengan cap masa, identiti pengguna, dan rasional keputusan. |   1   | D/V  |
| 13.3.2 | Sahkan bahawa log audit tidak boleh diubah suai dan sertakan mekanisme pengesahan integriti.                                             |   2   |  D   |

---

## C13.4 Teknik Explainable-AI

Kepentingan ciri permukaan, kontra-faktual, dan penjelasan tempatan.

|   #    | Description                                                                                                                                                   | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 13.4.1 | Sahkan bahawa sistem AI memberikan penjelasan asas untuk keputusan mereka dalam format yang boleh dibaca oleh manusia.                                        |   1   | D/V  |
| 13.4.2 | Sahkan bahawa kualiti penjelasan disahkan melalui kajian penilaian manusia dan metrik.                                                                        |   2   |  V   |
| 13.4.3 | Sahkan bahawa skor kepentingan ciri atau kaedah atribusi (SHAP, LIME, dan lain-lain) tersedia untuk keputusan kritikal.                                       |   3   | D/V  |
| 13.4.4 | Sahkan bahawa penjelasan kontra-faktual menunjukkan bagaimana input boleh diubah untuk mengubah hasil, jika sesuai dengan kes penggunaan dan bidang tersebut. |   3   |  V   |

---

## Kad Model C13.5 & Pendedahan Penggunaan

Mengekalkan kad model untuk penggunaan yang dimaksudkan, metrik prestasi, dan pertimbangan etika.

|   #    | Description                                                                                                                                                                     | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 13.5.1 | Sahkan bahawa kad model mendokumentasikan kes penggunaan yang dimaksudkan, hadnya, dan mod kegagalan yang diketahui.                                                            |   1   |  D   |
| 13.5.2 | Sahkan bahawa metrik prestasi merentasi pelbagai kes penggunaan yang berkenaan telah didedahkan.                                                                                |   1   | D/V  |
| 13.5.3 | Sahkan bahawa pertimbangan etika, penilaian bias, penilaian keadilan, ciri-ciri data latihan, dan had data latihan yang diketahui didokumenkan dan dikemas kini secara berkala. |   2   |  D   |
| 13.5.4 | Sahkan bahawa kad model dikawal versi dan diselenggara sepanjang kitaran hayat model dengan penjejakan perubahan.                                                               |   2   | D/V  |

---

## C13.6 Pengukuran Ketidakpastian

Sebarkan skor keyakinan atau ukuran entropi dalam respons.

|   #    | Description                                                                                                   | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 13.6.1 | Sahkan bahawa sistem AI menyediakan skor keyakinan atau ukuran ketidakpastian bersama dengan keluaran mereka. |   1   |  D   |
| 13.6.2 | Sahkan bahawa ambang ketidakpastian mencetuskan semakan manusia tambahan atau laluan keputusan alternatif.    |   2   | D/V  |
| 13.6.3 | Sahkan bahawa kaedah pengukuran ketidaktentuan dikalibrasi dan disahkan terhadap data kebenaran asas.         |   2   |  V   |
| 13.6.4 | Sahkan bahawa pengembangan ketidakpastian dikekalkan melalui aliran kerja AI berbilang langkah.               |   3   | D/V  |

---

## C13.7 Laporan Ketelusan Berhadapan Pengguna

Memberikan pendedahan berkala mengenai kejadian, peralihan, dan penggunaan data.

|   #    | Description                                                                                                                               | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 13.7.1 | Sahkan bahawa dasar penggunaan data dan amalan pengurusan persetujuan pengguna disampaikan dengan jelas kepada para pemegang kepentingan. |   1   | D/V  |
| 13.7.2 | Sahkan bahawa penilaian impak AI dijalankan dan keputusan dimasukkan dalam laporan.                                                       |   2   | D/V  |
| 13.7.3 | Sahkan bahawa laporan ketelusan yang diterbitkan secara berkala mendedahkan insiden AI dan metrik operasi dengan butiran yang munasabah.  |   2   | D/V  |

### Rujukan

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

