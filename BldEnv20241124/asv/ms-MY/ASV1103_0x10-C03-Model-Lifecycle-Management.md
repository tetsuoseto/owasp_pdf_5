# Pengurusan Kitaran Hayat Model C3 & Kawalan Perubahan

## Objektif Kawalan

Sistem AI mesti melaksanakan proses kawalan perubahan yang menghalang pengubahsuaian model yang tidak sah atau tidak selamat daripada sampai ke pengeluaran. Kawalan ini memastikan integriti model sepanjang keseluruhan kitar hayat—dari pembangunan hingga pelaksanaan hingga penamatan—yang membolehkan tindak balas insiden yang pantas dan mengekalkan akauntabiliti bagi semua perubahan.

Matlamat Keselamatan Teras: Hanya model yang dibenarkan dan disahkan yang mencapai pengeluaran dengan menggunakan proses terkawal yang mengekalkan integriti, keterjejakkan, dan kemampuan pulih.

---

## C3.1 Kebenaran Model & Integriti

Hanya model yang sah dengan integriti disahkan yang dibenarkan mencapai persekitaran produksi.

|   #   | Description                                                                                                                                                                             | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 3.1.1 | Sahkan bahawa semua artifak model (berat, konfigurasi, tokenizers) ditandatangani secara kriptografi oleh entiti yang diberi kuasa sebelum penyebaran.                                  |   1   | D/V  |
| 3.1.2 | Sahkan bahawa integriti model disahkan semasa masa pengeluaran dan kegagalan pengesahan tandatangan menghalang pemuatan model.                                                          |   1   | D/V  |
| 3.1.3 | Sahkan bahawa rekod asal model termasuk identiti entiti yang memberi kuasa, cek jumlah data latihan, keputusan ujian pengesahan dengan status lulus/gagal, dan cap masa penciptaan.     |   2   | D/V  |
| 3.1.4 | Sahkan bahawa semua artifak model menggunakan penomboran versi semantik (MAJOR.MINOR.PATCH) dengan kriteria yang didokumentasikan yang menentukan bila setiap komponen versi meningkat. |   2   | D/V  |
| 3.1.5 | Sahkan bahawa penjejakan kebergantungan mengekalkan inventori masa nyata yang membolehkan pengenalan pantas semua sistem yang menggunakan.                                              |   2   |  V   |

---

## C3.2 Pengesahan & Pengujian Model

Model mesti lulus pengesahan keselamatan dan keselamatan yang ditetapkan sebelum penerapan.

|   #   | Description                                                                                                                                                                                                                    | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 3.2.1 | Sahkan bahawa model menjalani ujian keselamatan automatik yang merangkumi pengesahan input, pensanitasi keluaran, dan penilaian keselamatan dengan ambang lulus/gagal organisasi yang telah dipersetujui sebelum pelaksanaan.  |   1   | D/V  |
| 3.2.2 | Sahkan bahawa kegagalan pengesahan secara automatik menghalang penyebaran model selepas kelulusan penggantian eksplisit daripada kakitangan yang diberi kuasa prarazmi dengan justifikasi perniagaan yang didokumenkan.        |   1   | D/V  |
| 3.2.3 | Sahkan bahawa keputusan ujian ditandatangani secara kriptografi dan dihubungkan secara kekal kepada hash versi model tertentu yang sedang disahkan.                                                                            |   2   |  V   |
| 3.2.4 | Sahkan bahawa penempatan kecemasan memerlukan penilaian risiko keselamatan yang didokumentasikan dan kelulusan daripada pihak berkuasa keselamatan yang telah ditetapkan sebelumnya dalam jangka masa yang telah dipersetujui. |   2   | D/V  |

---

## C3.3 Penempatan Terkawal & Pengembalian Semula

Penggubalan model mesti dikawal, dipantau, dan boleh dibalikkan.

|   #   | Description                                                                                                                                                                                                                                                                                | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 3.3.1 | Sahkan bahawa pelaksanaan pengeluaran menggunakan mekanisme pelaksanaan secara berperingkat (pelaksanaan canary, pelaksanaan biru-hijau) dengan pencetus rollback automatik berdasarkan kadar ralat yang dipersetujui terlebih dahulu, ambang kelewatan, atau kriteria amaran keselamatan. |   1   |  D   |
| 3.3.2 | Sahkan bahawa keupayaan rollback memulihkan keadaan model lengkap (berat, konfigurasi, kebergantungan) secara atomik dalam jendela masa organisasi yang telah ditetapkan.                                                                                                                  |   1   | D/V  |
| 3.3.3 | Sahkan bahawa proses penyebaran mengesahkan tandatangan kriptografi dan mengira cek jumlah integriti sebelum pengaktifan model, serta menggagalkan penyebaran jika terdapat ketidakpadanan.                                                                                                |   2   | D/V  |
| 3.3.4 | Sahkan bahawa keupayaan penutupan kecemasan model boleh mematikan titik akhir model dalam masa tindak balas yang telah ditetapkan melalui pemutus litar automatik atau suis bunuh manual.                                                                                                  |   2   | D/V  |
| 3.3.5 | Sahkan bahawa artifak rollback (versi model sebelumnya, konfigurasi, pergantungan) disimpan mengikut dasar organisasi dengan penyimpanan tidak boleh diubah bagi tindak balas insiden.                                                                                                     |   2   |  V   |

---

## C3.4 Perubahan Akauntabiliti & Audit

Semua perubahan kitaran hidup model mestilah boleh dijejak dan diaudit.

|   #   | Description                                                                                                                                                                                                                         | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 3.4.1 | Sahkan bahawa semua perubahan model (penyebaran, konfigurasi, persaraan) menghasilkan rekod audit tidak boleh diubah termasuk cap masa, identiti pelaku yang disahkan, jenis perubahan, dan keadaan sebelum/selepas.                |   1   |  V   |
| 3.4.2 | Sahkan bahawa akses log audit memerlukan kebenaran yang sesuai dan semua percubaan akses direkodkan dengan identiti pengguna dan cap masa.                                                                                          |   2   | D/V  |
| 3.4.3 | Sahkan bahawa templat arahan dan mesej sistem dikawal versi dalam repositori git dengan semakan kod wajib dan kelulusan daripada penyemak yang ditetapkan sebelum pelaksanaan.                                                      |   2   | D/V  |
| 3.4.4 | Sahkan bahawa rekod audit mengandungi butiran yang mencukupi (hash model, tangkapan konfigurasi, versi kebergantungan) untuk membolehkan pembinaan semula lengkap keadaan model bagi mana-mana tanda masa dalam tempoh penyimpanan. |   2   |  V   |

---

## Amalan Pembangunan Selamat C3.5

Proses pembangunan dan latihan model mesti mengikuti amalan selamat untuk mengelakkan kompromi.

|   #   | Description                                                                                                                                                                                                 | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 3.5.1 | Sahkan bahawa persekitaran pembangunan model, ujian, dan pengeluaran dipisahkan secara fizikal atau logik. Mereka tidak berkongsi infrastruktur, kawalan akses yang berbeza, dan stor data yang terasing.   |   1   |  D   |
| 3.5.2 | Sahkan bahawa latihan model dan penyesuaian berlaku dalam persekitaran terasing dengan akses rangkaian terkawal.                                                                                            |   1   |  D   |
| 3.5.3 | Sahkan bahawa sumber data latihan disahkan melalui pemeriksaan integriti dan diautentikasi melalui sumber yang dipercayai dengan rantai jagaan yang didokumenkan sebelum digunakan dalam pembangunan model. |   1   | D/V  |
| 3.5.4 | Sahkan bahawa artifak pembangunan model (hiperparameter, skrip latihan, fail konfigurasi) disimpan dalam kawalan versi dan memerlukan kelulusan semakan rakan sejawat sebelum digunakan dalam latihan.      |   2   |  D   |

---

## C3.6 Persaraan & Penamatan Model

Model mesti disunting dengan selamat apabila ia tidak lagi diperlukan atau apabila isu keselamatan dikenal pasti.

|   #   | Description                                                                                                                                                                                                                                        | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 3.6.1 | Sahkan bahawa proses persaraan model secara automatik mengimbas graf kebergantungan, mengenal pasti semua sistem yang menggunakan, dan menyediakan tempoh notis awal yang telah dipersetujui sebelum menamatkan perkhidmatan.                      |   1   |  D   |
| 3.6.2 | Sahkan bahawa artifak model yang telah dipensiunkan dipadamkan dengan selamat menggunakan penghapusan kriptografi atau penulisan semula berbilang laluan mengikut polisi penyimpanan data yang didokumenkan dengan sijil pemusnahan yang disahkan. |   1   | D/V  |
| 3.6.3 | Sahkan bahawa acara persaraan model direkodkan dengan cap masa dan identiti pelakon, serta tandatangan model dibatalkan untuk mengelakkan penggunaan semula.                                                                                       |   2   |  V   |
| 3.6.4 | Sahkan bahawa pemberhentian kecemasan model boleh melumpuhkan akses model dalam jangka masa tindak balas kecemasan yang telah ditetapkan melalui suis hentian automatik jika kelemahan keselamatan kritikal ditemui.                               |   2   | D/V  |

---

## Rujukan

* [MLOps Principles](https://ml-ops.org/content/mlops-principles)
* [Securing AI/ML Ops – Cisco.com](https://sec.cloudapps.cisco.com/security/center/resources/SecuringAIMLOps)
* [Audit logs security: cryptographically signed tamper-proof logs](https://www.cossacklabs.com/blog/audit-logs-security/)
* [Machine Learning Model Versioning: Top Tools & Best Practices](https://lakefs.io/blog/model-versioning/)
* [AI Hygiene Starts with Models and Data Loaders – SEI Blog](https://insights.sei.cmu.edu/documents/6190/AI-Hygiene-Starts-with-Models-and-Data-Loaders_1G0KTRh.pdf)
* [How to handle versioning and rollback of a deployed ML model?](https://learn.microsoft.com/en-au/answers/questions/1845378/how-to-handle-versioning-and-rollback-of-a-deploye)
* [Reinforcement fine-tuning – OpenAI API](https://platform.openai.com/docs/guides/reinforcement-fine-tuning)
* [Auditing Machine Learning models: Governance, Data Security and …](https://www.linkedin.com/pulse/auditing-machine-learning-models-governance-data-security-negrete-yn81f)
* [Adversarial Training to Improve Model Robustness](https://medium.com/%40amit25173/adversarial-training-to-improve-model-robustness-5e285b516713)
* [What is AI adversarial robustness? – IBM Research](https://research.ibm.com/blog/securing-ai-workflows-with-adversarial-robustness)
* [Exploring Data Provenance: Ensuring Data Integrity and Authenticity](https://www.astera.com/type/blog/data-provenance/)
* [MITRE ATLAS](https://atlas.mitre.org/)
* [AWS Prescriptive Guidance – Best practices for retiring applications …](https://docs.aws.amazon.com/pdfs/prescriptive-guidance/latest/migration-app-retirement-best-practices/migration-app-retirement-best-practices.pdf)

