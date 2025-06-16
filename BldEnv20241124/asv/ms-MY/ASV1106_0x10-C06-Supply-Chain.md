# Keselamatan Rantaian Bekalan C6 untuk Model, Rangka Kerja & Data

## Objektif Kawalan

Serangan rantaian bekalan AI mengeksploitasi model pihak ketiga, rangka kerja, atau set data untuk menyisipkan pintu belakang, bias, atau kod yang boleh dieksploitasi. Kawalan ini menyediakan sumber asal dari hujung ke hujung, pengurusan kelemahan, dan pemantauan untuk melindungi seluruh kitaran hayat model.

---

## C6.1 Pemeriksaan Model Pra-latihan & Asal-usul

Nilai dan sahkan asal model pihak ketiga, lesen, dan tingkah laku tersembunyi sebelum sebarang penyesuaian halus atau penyebaran.

|   #   | Description                                                                                                                                                 | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 6.1.1 | Sahkan bahawa setiap artifak model pihak ketiga termasuk rekod asal yang ditandatangani yang mengenal pasti repositori sumber dan hash komit.               |   1   | D/V  |
| 6.1.2 | Sahkan bahawa model-model diimbas untuk lapisan berniat jahat atau pencetus Trojan menggunakan alat automatik sebelum diimport.                             |   1   | D/V  |
| 6.1.3 | Sahkan bahawa penalaan halus pembelajaran pemindahan lulus penilaian advesarial untuk mengesan tingkah laku tersembunyi.                                    |   2   |  D   |
| 6.1.4 | Sahkan bahawa lesen model, tag kawalan eksport, dan pernyataan sumber data direkodkan dalam entri ML-BOM.                                                   |   2   |  V   |
| 6.1.5 | Sahkan bahawa model berisiko tinggi (berat yang dimuat naik secara awam, pencipta tidak disahkan) kekal dikarantin sehingga semakan dan pengesahan manusia. |   3   | D/V  |

---

## C6.2 Imbasan Rangka Kerja & Perpustakaan

Sentiasa mengimbas rangka kerja dan perpustakaan ML untuk CVE dan kod berniat jahat bagi memastikan timbunan masa jalan yang selamat.

|   #   | Description                                                                                                                                             | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 6.2.1 | Sahkan bahawa saluran paip CI menjalankan pengimbas kebergantungan pada rangka kerja AI dan perpustakaan kritikal.                                      |   1   | D/V  |
| 6.2.2 | Sahkan bahawa kerentanan kritikal (CVSS ≥ 7.0) menghalang promosi kepada imej pengeluaran.                                                              |   1   | D/V  |
| 6.2.3 | Sahkan bahawa analisis kod statik dijalankan pada perpustakaan ML yang bercabang atau dibekalkan.                                                       |   2   |  D   |
| 6.2.4 | Sahkan bahawa cadangan peningkatan rangka kerja merangkumi penilaian impak keselamatan yang merujuk suapan CVE awam.                                    |   2   |  V   |
| 6.2.5 | Sahkan bahawa penderia masa nyata memberi amaran mengenai muatan perpustakaan dinamik yang tidak dijangka yang menyimpang daripada SBOM bertandatangan. |   3   |  V   |

---

## C6.3 Penyandaran & Pengesahan Pergantungan

Pin setiap kebergantungan kepada digest tidak boleh ubah dan hasil binaan semula untuk menjamin artifak yang sama dan bebas daripada pengubahsuaian.

|   #   | Description                                                                                                                          | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 6.3.1 | Sahkan bahawa semua pengurus pakej menguatkuasakan penyematan versi melalui fail kunci.                                              |   1   | D/V  |
| 6.3.2 | Sahkan bahawa digest tidak boleh diubah digunakan sebagai ganti tag boleh ubah dalam rujukan kontena.                                |   1   | D/V  |
| 6.3.3 | Sahkan bahawa pemeriksaan binaan boleh dihasilkan semula membandingkan hash merentasi larian CI untuk memastikan output yang sama.   |   2   |  D   |
| 6.3.4 | Sahkan bahawa perakuan binaan disimpan selama 18 bulan untuk kebolehlacakan audit.                                                   |   2   |  V   |
| 6.3.5 | Sahkan bahawa pergantungan yang tamat tempoh mencetuskan PR automatik untuk mengemas kini atau memecahbelahkan versi yang dipancang. |   3   |  D   |

---

## C6.4 Penguatkuasaan Sumber Dipercayai

Benarkan muat turun artifak hanya dari sumber yang disahkan secara kriptografi dan diluluskan oleh organisasi serta sekat segala yang lain.

|   #   | Description                                                                                                                  | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 6.4.1 | Sahkan bahawa berat model, set data, dan bekas dimuat turun hanya dari domain yang diluluskan atau registri dalaman.         |   1   | D/V  |
| 6.4.2 | Sahkan bahawa tandatangan Sigstore/Cosign mengesahkan identiti penerbit sebelum artifak disimpan secara tempatan.            |   1   | D/V  |
| 6.4.3 | Sahkan bahawa proksi egress menyekat muat turun artifak tanpa pengesahan untuk menguatkuasakan dasar sumber yang dipercayai. |   2   |  D   |
| 6.4.4 | Sahkan bahawa senarai putih repositori disemak setiap suku tahun dengan bukti justifikasi perniagaan bagi setiap entri.      |   2   |  V   |
| 6.4.5 | Sahkan bahawa pelanggaran polisi mencetuskan kuarantin artifak dan pembalikan semula larian paip bergantung.                 |   3   |  V   |

---

## C6.5 Penilaian Risiko Dataset Pihak Ketiga

Nilai set data luar untuk pencemaran, bias, dan pematuhan undang-undang, serta pantau mereka sepanjang kitaran hayat mereka.

|   #   | Description                                                                                                                                                              | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 6.5.1 | Sahkan bahawa set data luaran menjalani penilaian risiko pencemaran (contohnya, cap jari data, pengesanan anomali).                                                      |   1   | D/V  |
| 6.5.2 | Sahkan bahawa metrik bias (kesamarataan demografi, peluang sama) dikira sebelum kelulusan set data.                                                                      |   1   |  D   |
| 6.5.3 | Sahkan bahawa asal usul dan terma lesen untuk set data direkodkan dalam entri ML-BOM.                                                                                    |   2   |  V   |
| 6.5.4 | Sahkan bahawa pemantauan berkala mengesan pergeseran atau kerosakan dalam set data yang dihoskan.                                                                        |   2   |  V   |
| 6.5.5 | Sahkan bahawa kandungan yang tidak dibenarkan (hak cipta, Maklumat Peribadi yang Boleh Dikenal Pasti) telah dialih keluar melalui pembersihan automatik sebelum latihan. |   3   |  D   |

---

## C6.6 Pemantauan Serangan Rantaian Pembekalan

Kesannya ancaman rantaian bekalan lebih awal melalui suapan CVE, analitik log audit, dan simulasi pasukan merah.

|   #   | Description                                                                                                                            | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 6.6.1 | Sahkan bahawa log audit CI/CD disalur ke SIEM untuk pengesanan anomali dalam penarikan pakej atau langkah binaan yang dicurangi.       |   1   |  V   |
| 6.6.2 | Sahkan bahawa buku panduan tindak balas insiden termasuk prosedur rollback untuk model atau perpustakaan yang telah dikompromi.        |   2   |  D   |
| 6.6.3 | Sahkan bahawa penambahan maklumat risikan ancaman menandakan petunjuk khusus ML (contohnya, IoC pencemaran model) dalam triase amaran. |   3   |  V   |

---

## C6.7 ML-BOM untuk Artifak Model

Menghasilkan dan menandatangani SBOM khusus ML yang terperinci (ML-BOM) supaya pengguna hiliran dapat mengesahkan integriti komponen semasa masa pengedaran.

|   #   | Description                                                                                                                           | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 6.7.1 | Sahkan bahawa setiap artifak model menerbitkan ML‑BOM yang menyenaraikan set data, berat, hiperparameter, dan lesen.                  |   1   | D/V  |
| 6.7.2 | Sahkan bahawa penjanaan ML-BOM dan penandatanganan Cosign diautomatikkan dalam CI dan dikehendaki untuk penggabungan.                 |   1   | D/V  |
| 6.7.3 | Sahkan bahawa pemeriksaan kesempurnaan ML‑BOM akan menyebabkan pembinaan gagal jika mana-mana metadata komponen (hash, lesen) hilang. |   2   |  D   |
| 6.7.4 | Sahkan bahawa pengguna hiliran boleh menyemak ML-BOM melalui API untuk mengesahkan model yang diimport pada masa penyebaran.          |   2   |  V   |
| 6.7.5 | Sahkan bahawa ML-BOM dikawal versi dan dibanding untuk mengesan pengubahsuaian tanpa kebenaran.                                       |   3   |  V   |

---

## Rujukan

* [ML Supply Chain Compromise – MITRE ATLAS](https://misp-galaxy.org/mitre-atlas-attack-pattern/)
* [Supply‑chain Levels for Software Artifacts (SLSA)](https://slsa.dev/)
* [CycloneDX – Machine Learning Bill of Materials](https://cyclonedx.org/capabilities/mlbom/)
* [What is Data Poisoning? – SentinelOne](https://www.sentinelone.com/cybersecurity-101/cybersecurity/data-poisoning/)
* [Transfer Learning Attack – OWASP ML Security Top 10](https://owasp.org/www-project-machine-learning-security-top-10/docs/ML07_2023-Transfer_Learning_Attack)
* [AI Data Security Best Practices – CISA](https://www.cisa.gov/news-events/cybersecurity-advisories/aa25-142a)
* [Secure CI/CD Supply Chain – Sumo Logic](https://www.sumologic.com/blog/secure-azure-devops-github-supply-chain-attacks)
* [AI & Transparency: Protect ML Models – ReversingLabs](https://www.reversinglabs.com/blog/ai-and-transparency-how-ml-model-creators-can-protect-against-supply-chain-attacks)
* [SBOM Overview – CISA](https://www.cisa.gov/sbom)
* [Training Data Poisoning Guide – Lakera.ai](https://www.lakera.ai/blog/training-data-poisoning)
* [Dependency Pinning for Reproducible Python – Medium](https://medium.com/data-science-collective/guarantee-a-locked-reproducible-environment-with-every-python-run-c0e2bf19fb53)

