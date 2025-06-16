# Pemantauan, Pencatatan & Pengesanan Anomali C12

## Objektif Kawalan

Bahagian ini menyediakan keperluan untuk memberikan keterlihatan masa nyata dan forensik terhadap apa yang model dan komponen AI lain lihat, lakukan, dan kembalikan, supaya ancaman dapat dikesan, ditapis, dan dipelajari.

## C12.1 Rekod Permintaan & Respons

|   #    | Description                                                                                                                                                                                                                                                                    | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 12.1.1 | Sahkan bahawa semua arahan pengguna dan respons model direkodkan dengan metadata yang sesuai (contohnya: cap masa, ID pengguna, ID sesi, versi model).                                                                                                                         |   1   | D/V  |
| 12.1.2 | Sahkan bahawa log disimpan dalam repositori yang selamat dan dikawal akses dengan polisi penyimpanan data dan prosedur sandaran yang sesuai.                                                                                                                                   |   1   | D/V  |
| 12.1.3 | Sahkan bahawa sistem penyimpanan log melaksanakan penyulitan ketika data disimpan dan dalam transit untuk melindungi maklumat sensitif yang terkandung dalam log.                                                                                                              |   1   | D/V  |
| 12.1.4 | Sahkan bahawa data sensitif dalam arahan dan hasil output secara automatik disamarkan atau disembunyikan sebelum direkod, dengan peraturan penyamaran yang boleh dikonfigurasikan untuk Maklumat Peribadi yang Boleh Dikenal Pasti (PII), kelayakan, dan maklumat proprietari. |   1   | D/V  |
| 12.1.5 | Sahkan bahawa keputusan dasar dan tindakan penapisan keselamatan direkodkan dengan butiran yang mencukupi untuk membolehkan audit dan penyahpepijatan sistem pengawalan kandungan.                                                                                             |   2   | D/V  |
| 12.1.6 | Sahkan bahawa integriti log dilindungi melalui contohnya tandatangan kriptografi atau storan hanya-tulis.                                                                                                                                                                      |   2   | D/V  |

---

## C12.2 Pengesanan dan Pemberitahuan Penyalahgunaan

|   #    | Description                                                                                                                                                                                 | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 12.2.1 | Sahkan bahawa sistem mengesan dan memberi amaran mengenai corak jailbreak yang dikenal pasti, cubaan suntikan arahan, dan input adversarial menggunakan pengesanan berasaskan tanda tangan. |   1   | D/V  |
| 12.2.2 | Sahkan bahawa sistem itu berintegrasi dengan platform Pengurusan Maklumat dan Peristiwa Keselamatan (SIEM) sedia ada menggunakan format log dan protokol standard.                          |   1   | D/V  |
| 12.2.3 | Sahkan bahawa acara keselamatan yang diperkaya termasuk konteks khusus AI seperti pengecam model, skor keyakinan, dan keputusan penapis keselamatan.                                        |   2   | D/V  |
| 12.2.4 | Sahkan bahawa pengesanan anomali tingkah laku mengenal pasti corak perbualan yang luar biasa, cubaan mengulang yang berlebihan, atau tingkah laku pemeriksaan sistematik.                   |   2   | D/V  |
| 12.2.5 | Sahkan bahawa mekanisme penggera masa nyata memberitahu pasukan keselamatan apabila potensi pelanggaran dasar atau percubaan serangan dikesan.                                              |   2   | D/V  |
| 12.2.6 | Sahkan bahawa peraturan tersuai disertakan untuk mengesan corak ancaman khusus AI termasuk percubaan jailbreak berkoordinasi, kempen suntikan arahan, dan serangan pengecualian model.      |   2   | D/V  |
| 12.2.7 | Sahkan bahawa aliran kerja tindak balas insiden automatik boleh mengasingkan model yang dikompromi, menyekat pengguna berniat jahat, dan meningkatkan acara keselamatan kritikal.           |   3   | D/V  |

---

## C12.3 Pengesanan Pergeseran Model

|   #    | Description                                                                                                                                                                        | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 12.3.1 | Sahkan bahawa sistem mengesan metrik prestasi asas seperti ketepatan, skor keyakinan, kelewatan, dan kadar ralat merentasi versi model dan tempoh masa.                            |   1   | D/V  |
| 12.3.2 | Sahkan bahawa amaran automatik akan dicetuskan apabila metrik prestasi melebihi ambang penurunan yang telah ditetapkan atau menyimpang dengan ketara dari garis dasar.             |   2   | D/V  |
| 12.3.3 | Sahkan bahawa pemantau pengesanan halusinasi mengenal pasti dan menanda contoh apabila output model mengandungi maklumat yang salah dari segi fakta, tidak konsisten, atau direka. |   2   | D/V  |

---

## C12.4 Telemetri Prestasi & Tingkah Laku

|   #    | Description                                                                                                                                                        | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 12.4.1 | Sahkan bahawa metrik operasi termasuk kelewatan permintaan, penggunaan token, penggunaan memori, dan kadar pemprosesan dikumpulkan dan dipantau secara berterusan. |   1   | D/V  |
| 12.4.2 | Sahkan bahawa kadar kejayaan dan kegagalan dijejaki dengan pengkategorian jenis ralat dan punca akarnya.                                                           |   1   | D/V  |
| 12.4.3 | Sahkan bahawa pemantauan penggunaan sumber merangkumi penggunaan GPU/CPU, penggunaan memori, dan keperluan storan dengan pemberitahuan apabila ambang dicapai.     |   2   | D/V  |

---

## C12.5 Perancangan & Pelaksanaan Respons Insiden AI

|   #    | Description                                                                                                                                                                              | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 12.5.1 | Sahkan bahawa pelan tindak balas insiden secara khusus menangani kejadian keselamatan berkaitan AI termasuk kompromi model, pencemaran data, dan serangan musuh.                         |   1   | D/V  |
| 12.5.2 | Sahkan bahawa pasukan tindak balas insiden mempunyai akses kepada alat forensik khusus AI dan kepakaran untuk menyiasat tingkah laku model dan vektor serangan.                          |   2   | D/V  |
| 12.5.3 | Sahkan bahawa analisis pasca-insiden merangkumi pertimbangan latihan semula model, kemas kini penapis keselamatan, dan integrasi pengajaran yang diperoleh ke dalam kawalan keselamatan. |   3   | D/V  |

---

## C12.5 Pengesanan Penurunan Prestasi AI

Memantau dan mengesan penurunan prestasi dan kualiti model AI dari masa ke masa.

|   #    | Description                                                                                                                                                         | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 12.5.1 | Sahkan bahawa ketepatan model, ketepatan (precision), panggilan semula (recall), dan skor F1 dipantau secara berterusan dan dibandingkan dengan ambang garis dasar. |   1   | D/V  |
| 12.5.2 | Sahkan bahawa pengesanan pergeseran data memantau perubahan taburan input yang mungkin memberi kesan kepada prestasi model.                                         |   1   | D/V  |
| 12.5.3 | Sahkan bahawa pengesanan pergeseran konsep mengenal pasti perubahan dalam hubungan antara input dan output yang dijangka.                                           |   2   | D/V  |
| 12.5.4 | Sahkan bahawa degradasi prestasi mencetuskan amaran automatik dan memulakan aliran kerja latihan semula atau penggantian model.                                     |   2   | D/V  |
| 12.5.5 | Sahkan bahawa analisis punca akar kemerosotan mengaitkan penurunan prestasi dengan perubahan data, isu infrastruktur, atau faktor luaran.                           |   3   |  V   |

---

## C12.6 Visualisasi DAG & Keselamatan Aliran Kerja

Lindungi sistem visualisasi aliran kerja daripada kebocoran maklumat dan serangan manipulasi.

|   #    | Description                                                                                                                                                  | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 12.6.1 | Sahkan bahawa data visualisasi DAG disanitasi untuk menghapuskan maklumat sensitif sebelum penyimpanan atau penghantaran.                                    |   1   | D/V  |
| 12.6.2 | Sahkan bahawa kawalan akses visualisasi aliran kerja memastikan hanya pengguna yang diberi kuasa boleh melihat laluan keputusan agen dan jejak alasan.       |   1   | D/V  |
| 12.6.3 | Sahkan bahawa integriti data DAG dilindungi melalui tandatangan kriptografi dan mekanisme penyimpanan yang membuktikan sebarang pengubahan.                  |   2   | D/V  |
| 12.6.4 | Sahkan bahawa sistem visualisasi aliran kerja melaksanakan pengesahan input untuk mengelakkan serangan suntikan melalui data nod atau tepi yang direka khas. |   2   | D/V  |
| 12.6.5 | Sahkan bahawa kemas kini DAG secara masa nyata adalah terhad kadar dan disahkan untuk mengelakkan serangan penolakan perkhidmatan pada sistem visualisasi.   |   3   | D/V  |

---

## C12.7 Pemantauan Tingkah Laku Keselamatan Proaktif

Pengesanan dan pencegahan ancaman keselamatan melalui analisis tingkah laku agen proaktif.

|   #    | Description                                                                                                                            | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 12.7.1 | Sahkan bahawa tingkah laku ejen proaktif disahkan keselamatannya sebelum pelaksanaan dengan pengintegrasian penilaian risiko.          |   1   | D/V  |
| 12.7.2 | Sahkan bahawa pencetus inisiatif autonomi merangkumi penilaian konteks keselamatan dan penilaian lanskap ancaman.                      |   2   | D/V  |
| 12.7.3 | Sahkan bahawa corak tingkah laku proaktif dianalisis untuk implikasi keselamatan yang berpotensi dan akibat yang tidak diingini.       |   2   | D/V  |
| 12.7.4 | Sahkan bahawa tindakan proaktif yang kritikal keselamatannya memerlukan rantai kelulusan yang jelas dengan jejak audit.                |   3   | D/V  |
| 12.7.5 | Sahkan bahawa pengesanan anomali tingkah laku mengenal pasti penyimpangan dalam corak ejen proaktif yang mungkin menunjukkan kompromi. |   3   | D/V  |

---

## Rujukan

* [NIST AI Risk Management Framework 1.0 - Manage 4.1 and 4.3](https://nvlpubs.nist.gov/nistpubs/ai/nist.ai.100-1.pdf)
* [ISO/IEC 42001:2023 — AI Management Systems Requirements - Annex B 6.2.6](https://www.iso.org/standard/81230.html)
* [EU AI Act — Article 12, 13, 16 and 19 on Logging and Record-keeping](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX%3A32024R1689)

