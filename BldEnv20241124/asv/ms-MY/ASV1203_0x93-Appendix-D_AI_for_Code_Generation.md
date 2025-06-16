# Lampiran D: Tadbir Urus & Pengesahan Pengekodan Selamat Berbantu AI

## Objektif

Bab ini mentakrifkan kawalan organisasi asas untuk penggunaan alat pengekodan berasaskan AI yang selamat dan berkesan semasa pembangunan perisian, memastikan keselamatan dan kebolehlacakan merentasi Kitaran Hayat Pembangunan Perisian (SDLC).

---

## AD.1 Aliran Kerja Penulisan Kod Selamat Berbantukan AI

Mengintegrasikan alat AI ke dalam kitaran hidup pembangunan perisian selamat organisasi (SSDLC) tanpa melemahkan pintu keselamatan sedia ada.

|   #    | Description                                                                                                                                                                      | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| AD.1.1 | Sahkan bahawa aliran kerja yang didokumentasikan menerangkan bila dan bagaimana alat AI boleh menjana, mengubah, atau menyemak kod.                                              |   1   | D/V  |
| AD.1.2 | Sahkan bahawa aliran kerja tersebut memetakan kepada setiap fasa SSDLC (reka bentuk, pelaksanaan, semakan kod, pengujian, penyebaran).                                           |   2   |  D   |
| AD.1.3 | Sahkan bahawa metrik (contohnya, ketumpatan kerentanan, masa purata untuk mengesan) dikumpulkan ke atas kod yang dihasilkan oleh AI dan dibandingkan dengan asas manusia sahaja. |   3   | D/V  |

---

## AD.2 Kelayakan Alat AI & Pemodelan Ancaman

Pastikan alat pengkodan AI dinilai dari segi keupayaan keselamatan, risiko, dan kesan rantaian bekalan sebelum digunakan.

|   #    | Description                                                                                                                                                            | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| AD.2.1 | Sahkan bahawa model ancaman bagi setiap alat AI mengenal pasti penyalahgunaan, pembalikan model, kebocoran data, dan risiko rantaian kebergantungan.                   |   1   | D/V  |
| AD.2.2 | Sahkan bahawa penilaian alat termasuk analisis statik/dinamik bagi mana-mana komponen tempatan dan penilaian titik akhir SaaS (TLS, pengesahan/kelulusan, pencatatan). |   2   |  D   |
| AD.2.3 | Sahkan bahawa penilaian mengikuti rangka kerja yang diiktiraf dan dilakukan semula selepas perubahan versi utama.                                                      |   3   | D/V  |

---

## AD.3 Pengurusan Prompt & Konteks yang Selamat

Elakkan kebocoran rahsia, kod milik eksklusif, dan data peribadi semasa membina arahan atau konteks untuk model AI.

|   #    | Description                                                                                                                                                          | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| AD.3.1 | Sahkan bahawa panduan bertulis mengharamkan penghantaran rahsia, kebenaran, atau data berklasifikasi dalam arahan.                                                   |   1   | D/V  |
| AD.3.2 | Sahkan bahawa kawalan teknikal (redaksi sebelah klien, penapis konteks yang diluluskan) secara automatik menanggalkan artifak sensitif.                              |   2   |  D   |
| AD.3.3 | Sahkan bahawa arahan dan respons dipecahkan kepada token, disulitkan semasa penghantaran dan semasa disimpan, dan tempoh penyimpanan mematuhi dasar pengelasan data. |   3   | D/V  |

---

## AD.4 Pengesahan Kod yang Dijana oleh AI

Mengesan dan membaiki kerentanan yang diperkenalkan oleh keluaran AI sebelum kod digabungkan atau dilaksanakan.

|   #    | Description                                                                                                                                                                                 | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| AD.4.1 | Sahkan bahawa kod yang dijana oleh AI sentiasa melalui semakan kod oleh manusia.                                                                                                            |   1   | D/V  |
| AD.4.2 | Sahkan bahawa pengimbas automatik (SAST/IAST/DAST) dijalankan pada setiap permintaan tarik yang mengandungi kod yang dijana oleh AI dan sekat penggabungan jika terdapat penemuan kritikal. |   2   |  D   |
| AD.4.3 | Sahkan bahawa ujian fuzz berbeza atau ujian berasaskan sifat membuktikan tingkah laku kritikal keselamatan (contohnya, pengesahan input, logik kebenaran).                                  |   3   | D/V  |

---

## AD.5 Kebolehurai & Kebolehsusulan Cadangan Kod

Memberikan auditor dan pembangun wawasan mengenai sebab cadangan dibuat dan bagaimana ia berkembang.

|   #    | Description                                                                                                                                                      | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| AD.5.1 | Sahkan bahawa pasangan arahan/respons direkodkan dengan ID komit.                                                                                                |   1   | D/V  |
| AD.5.2 | Sahkan bahawa pembangun boleh menampilkan sitasi model (petikan latihan, dokumentasi) yang menyokong cadangan tersebut.                                          |   2   |  D   |
| AD.5.3 | Sahkan bahawa laporan kebolehterangan disimpan bersama artifak reka bentuk dan dirujuk dalam semakan keselamatan, memenuhi prinsip kebolehlacakan ISO/IEC 42001. |   3   | D/V  |

---

## AD.6 Maklum Balas Berterusan & Penalaan Halus Model

Meningkatkan prestasi keselamatan model dari masa ke masa sambil mengelakkan pergeseran negatif.

|   #    | Description                                                                                                                                                                                          | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| AD.6.1 | Sahkan bahawa pembangun boleh menandakan cadangan yang tidak selamat atau tidak mematuhi, dan bahawa tanda tersebut direkodkan.                                                                      |   1   | D/V  |
| AD.6.2 | Sahkan bahawa maklum balas terkumpul memaklumkan penalaan halus berkala atau penjanaan berpandukan pengambilan dengan korpus pengkodan selamat yang telah disemak (contohnya, Lembaran Cepat OWASP). |   2   |  D   |
| AD.6.3 | Sahkan bahawa sistem penilaian gelung tertutup menjalankan ujian regresi selepas setiap penalaan halus; metrik keselamatan mesti mencapai atau melebihi garis asas sebelumnya sebelum pelaksanaan.   |   3   | D/V  |

---

### Rujukan

* [NIST AI Risk Management Framework 1.0](https://nvlpubs.nist.gov/nistpubs/ai/nist.ai.100-1.pdf)
* [ISO/IEC 42001:2023 — AI Management Systems Requirements](https://www.iso.org/standard/81230.html)
* [OWASP Secure Coding Practices — Quick Reference Guide](https://owasp.org/www-project-secure-coding-practices-quick-reference-guide/)

