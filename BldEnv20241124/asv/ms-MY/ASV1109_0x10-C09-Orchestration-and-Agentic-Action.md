# 9 Orkestrasi Autonomi & Keselamatan Tindakan Agen

## Objektif Kawalan

Pastikan sistem AI autonomi atau multi-ejen hanya boleh melaksanakan tindakan yang secara jelas dimaksudkan, disahkan, boleh diaudit, dan berada dalam had kos serta risiko yang ditetapkan. Ini melindungi daripada ancaman seperti Kompromi Sistem Autonomi, Penyalahgunaan Alat, Pengesanan Gelung Ejen, Pembajakan Komunikasi, Pemalsuan Identiti, Manipulasi Kawanan, dan Manipulasi Niat.

---

## 9.1 Perancangan Tugas Ejen & Bajet Rekursi

Hadkan rancangan rekursif dan paksa pemeriksaan manusia untuk tindakan berhak istimewa.

|   #   | Description                                                                                                                                                                                               | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.1.1 | Sahkan bahawa kedalaman rekursi maksimum, keluasan, masa jam dinding, token, dan kos wang untuk setiap pelaksanaan agen dikonfigurasikan secara pusat dan dikawal versi.                                  |   1   | D/V  |
| 9.1.2 | Sahkan bahawa tindakan istimewa atau tidak boleh dipulihkan (contohnya, komit kod, pemindahan kewangan) memerlukan kelulusan manusia secara jelas melalui saluran yang boleh diaudit sebelum pelaksanaan. |   1   | D/V  |
| 9.1.3 | Sahkan bahawa pemantau sumber masa nyata mencetuskan gangguan pemutus litar apabila mana-mana ambang bajet melebihi had, menghentikan pengembangan tugas selanjutnya.                                     |   2   |  D   |
| 9.1.4 | Sahkan bahawa acara pemutus litar direkodkan dengan ID ejen, keadaan pencetus, dan keadaan pelan yang dirakam untuk semakan forensik.                                                                     |   2   | D/V  |
| 9.1.5 | Sahkan bahawa ujian keselamatan merangkumi senario kehabisan bajet dan pelan larian, mengesahkan pemberhentian yang selamat tanpa kehilangan data.                                                        |   3   |  V   |
| 9.1.6 | Sahkan bahawa polisi belanjawan dinyatakan sebagai polisi-sebagai-kod dan dikuatkuasakan dalam CI/CD untuk menghalang pergeseran konfigurasi.                                                             |   3   |  D   |

---

## 9.2 Pengasingan Plugin Alat

Mengasingkan interaksi alat untuk mengelakkan akses sistem tanpa kebenaran atau pelaksanaan kod.

|   #   | Description                                                                                                                                                                                    | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.2.1 | Sahkan bahawa setiap alat/plugin berjalan di dalam OS, bekas (container), atau sandbox pada tahap WASM dengan polisi hak istimewa terendah untuk sistem fail, rangkaian, dan panggilan sistem. |   1   | D/V  |
| 9.2.2 | Sahkan bahawa kuota sumber sandbox (CPU, memori, cakera, egreis rangkaian) dan masa tamat pelaksanaan dikenakan dan direkodkan.                                                                |   1   | D/V  |
| 9.2.3 | Sahkan bahawa binari alat atau penerangan ditandatangani secara digital; tandatangan disahkan sebelum dimuatkan.                                                                               |   2   | D/V  |
| 9.2.4 | Sahkan bahawa aliran telemetri sandbox ke SIEM; anomali (contohnya, percubaan sambungan keluar) akan mencetuskan amaran.                                                                       |   2   |  V   |
| 9.2.5 | Sahkan bahawa plugin berisiko tinggi menjalani kajian keselamatan dan ujian penembusan sebelum pengeluaran dihasilkan.                                                                         |   3   |  V   |
| 9.2.6 | Sahkan bahawa percubaan melarikan diri dari sandbox disekat secara automatik dan plugin yang melakukan kesalahan dikarantinkan sementara siasatan dijalankan.                                  |   3   | D/V  |

---

## 9.3 Gelung Autonomi & Had Kos

Mengesan dan menghentikan rekursi ejen-ke-ejen yang tidak terkawal serta letusan kos.

|   #   | Description                                                                                                                                               | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.3.1 | Sahkan bahawa panggilan antara ejen termasuk had lompatan atau TTL yang dikurangkan dan dikuatkuasakan oleh runtime.                                      |   1   | D/V  |
| 9.3.2 | Sahkan bahawa ejen mengekalkan ID graf-panggilan unik untuk mengenal pasti pemanggilan kendiri atau corak kitaran.                                        |   2   |  D   |
| 9.3.3 | Sahkan bahawa kaunter unit pengiraan kumulatif dan perbelanjaan dikesan bagi setiap rantaian permintaan; melebihi had akan membatalkan rantaian tersebut. |   2   | D/V  |
| 9.3.4 | Sahkan bahawa analisis formal atau pemeriksaan model menunjukkan ketiadaan rekursi tidak terhad dalam protokol ejen.                                      |   3   |  V   |
| 9.3.5 | Sahkan bahawa acara pembatalan gelung menjana amaran dan memberi makan metrik peningkatan berterusan.                                                     |   3   |  D   |

---

## 9.4 Perlindungan Salah Guna pada Tahap Protokol

Saluran komunikasi yang selamat antara ejen dan sistem luaran untuk mengelakkan pengambilalihan atau manipulasi.

|   #   | Description                                                                                                                                    | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.4.1 | Sahkan bahawa semua mesej antara ejen-ke-alat dan ejen-ke-ejen disahkan (contohnya, mutual TLS atau JWT) dan disulitkan dari hujung ke hujung. |   1   | D/V  |
| 9.4.2 | Sahkan bahawa skema disahkan dengan ketat; medan yang tidak diketahui atau mesej yang cacat ditolak.                                           |   1   |  D   |
| 9.4.3 | Sahkan bahawa pemeriksaan integriti (MAC atau tandatangan digital) meliputi keseluruhan muatan mesej termasuk parameter alat.                  |   2   | D/V  |
| 9.4.4 | Sahkan bahawa perlindungan ulang main (nonce atau tingkap cap masa) dikuatkuasakan di lapisan protokol.                                        |   2   |  D   |
| 9.4.5 | Sahkan bahawa pelaksanaan protokol menjalani fuzzing dan analisis statik untuk kelemahan suntikan atau penyahserahan.                          |   3   |  V   |

---

## 9.5 Identiti Ejen & Bukti-tumpuan

Pastikan tindakan boleh dipertanggungjawabkan dan pengubahsuaian boleh dikesan.

|   #   | Description                                                                                                                                        | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.5.1 | Sahkan bahawa setiap instans ejen mempunyai identiti kriptografi unik (pasangan kunci atau kredensial berakar perkakasan).                         |   1   | D/V  |
| 9.5.2 | Sahkan bahawa semua tindakan agen ditandatangani dan diberi cap masa; log termasuk tandatangan untuk mengelakkan penafian.                         |   2   | D/V  |
| 9.5.3 | Sahkan bahawa log yang menunjukkan tanda-tanda pengubahan disimpan dalam medium yang hanya membenarkan tambahan data atau penulisan sekali sahaja. |   2   |  V   |
| 9.5.4 | Sahkan bahawa kekunci identiti berputar mengikut jadual yang ditetapkan dan berdasarkan penunjuk kompromi.                                         |   3   |  D   |
| 9.5.5 | Sahkan bahawa percubaan penipuan atau konflik kunci akan mencetuskan pengasingan serta-merta bagi ejen yang terjejas.                              |   3   | D/V  |

---

## 9.6 Pengurangan Risiko Swarm Berbilang Ejen

Kurangkan bahaya tingkah laku kolektif melalui pengasingan dan pemodelan keselamatan formal.

|   #   | Description                                                                                                                                                         | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.6.1 | Sahkan bahawa ejen yang beroperasi dalam domain keselamatan yang berbeza menjalankan dalam kotak pasir runtime yang terasing atau segmen rangkaian yang berasingan. |   1   | D/V  |
| 9.6.2 | Sahkan bahawa tingkah laku kawanan dimodelkan dan disahkan secara formal untuk keberlangsungan dan keselamatan sebelum penyebaran.                                  |   3   |  V   |
| 9.6.3 | Sahkan bahawa pemantau masa nyata mengesan corak tidak selamat yang muncul (contohnya, osilasi, kebuntuan) dan memulakan tindakan pembetulan.                       |   3   |  D   |

---

## 9.7 Pengesahan / Pemberian Kuasa Pengguna & Alat

Laksanakan kawalan akses yang kukuh untuk setiap tindakan yang dicetuskan oleh agen.

|   #   | Description                                                                                                                                         | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.7.1 | Sahkan bahawa ejen mengesahkan sebagai prinsipal kelas pertama kepada sistem hiliran, dan tidak pernah menggunakan semula kelayakan pengguna akhir. |   1   | D/V  |
| 9.7.2 | Sahkan bahawa dasar kebenaran terperinci mengehadkan alat yang boleh digunakan oleh agen dan parameter yang boleh disediakannya.                    |   2   |  D   |
| 9.7.3 | Sahkan bahawa pemeriksaan keistimewaan dinilai semula pada setiap panggilan (pemberian kuasa berterusan), bukan hanya pada permulaan sesi.          |   2   |  V   |
| 9.7.4 | Sahkan bahawa keistimewaan yang didelegasikan akan tamat secara automatik dan memerlukan persetujuan semula selepas masa tamat atau perubahan skop. |   3   |  D   |

---

## 9.8 Keselamatan Komunikasi Ejen-ke-Ejen

Sulitkan dan lindungi integriti semua mesej antara agen untuk menghalang pemantauan tanpa kebenaran dan penyuntingan.

|   #   | Description                                                                                                                                        | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.8.1 | Sahkan bahawa pengesahan bersama dan penyulitan rahsia maju sempurna (contohnya TLS 1.3) adalah wajib bagi saluran ejen.                           |   1   | D/V  |
| 9.8.2 | Sahkan bahawa integriti dan asal usul mesej disahkan sebelum pemprosesan; kegagalan akan menghasilkan amaran dan menolak mesej tersebut.           |   1   |  D   |
| 9.8.3 | Sahkan bahawa metadata komunikasi (cap masa, nombor urutan) direkod untuk menyokong pembinaan semula forensik.                                     |   2   | D/V  |
| 9.8.4 | Sahkan bahawa pengesahan formal atau pemeriksaan model mengesahkan bahawa mesin negeri protokol tidak boleh dipaksa ke keadaan yang tidak selamat. |   3   |  V   |

---

## 9.9 Pengesahan Niat & Penguatkuasaan Kekangan

Sahkan bahawa tindakan ejen sejajar dengan niat yang dinyatakan oleh pengguna dan had sistem.

|   #   | Description                                                                                                                                                                         | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.9.1 | Sahkan bahawa penyelesai kekangan pra-pelaksanaan memeriksa tindakan yang dicadangkan terhadap peraturan keselamatan dan dasar yang telah diprogramkan keras.                       |   1   |  D   |
| 9.9.2 | Sahkan bahawa tindakan berimpak tinggi (kewangan, merosakkan, sensitif privasi) memerlukan pengesahan niat yang jelas daripada pengguna yang memulakan.                             |   2   | D/V  |
| 9.9.3 | Sahkan bahawa pemeriksaan pasca-keadaan mengesahkan bahawa tindakan yang selesai mencapai kesan yang dimaksudkan tanpa kesan sampingan; ketidaksesuaian mencetuskan pembalikan.     |   2   |  V   |
| 9.9.4 | Sahkan bahawa kaedah formal (contohnya, pemeriksaan model, pembuktian teorem) atau ujian berasaskan harta menunjukkan bahawa pelan agen memenuhi semua kekangan yang diisytiharkan. |   3   |  V   |
| 9.9.5 | Sahkan bahawa kejadian ketidakpadanan niat atau pelanggaran kekangan menyumbang kepada kitaran penambahbaikan berterusan dan perkongsian maklumat risikan ancaman.                  |   3   |  D   |

---

## 9.10 Strategi Penalaran Ejen Keselamatan

Pemilihan dan pelaksanaan selamat bagi pelbagai strategi penaakulan termasuk pendekatan ReAct, Chain-of-Thought, dan Tree-of-Thoughts.

|   #    | Description                                                                                                                                                                                                                           | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.10.1 | Sahkan bahawa pemilihan strategi penaakulan menggunakan kriteria deterministik (kerumitan input, jenis tugas, konteks keselamatan) dan input yang sama menghasilkan pemilihan strategi yang sama dalam konteks keselamatan yang sama. |   1   | D/V  |
| 9.10.2 | Sahkan bahawa setiap strategi pemikiran (ReAct, Chain-of-Thought, Tree-of-Thoughts) mempunyai pengesahan input yang khusus, pensanitasi output, dan had masa pelaksanaan yang khusus mengikut pendekatan kognitifnya.                 |   1   | D/V  |
| 9.10.3 | Sahkan bahawa peralihan strategi penalaran direkodkan dengan konteks lengkap termasuk ciri-ciri input, nilai kriteria pemilihan, dan metadata pelaksanaan untuk pembinaan semula jejak audit.                                         |   2   | D/V  |
| 9.10.4 | Sahkan bahawa penalaran Pokok-Pemikiran (Tree-of-Thoughts) merangkumi mekanisme pemangkasan cabang yang menghentikan penerokaan apabila pelanggaran polisi, had sumber, atau sempadan keselamatan dikesan.                            |   2   | D/V  |
| 9.10.5 | Sahkan bahawa kitaran ReAct (Reason-Act-Observe) termasuk titik pemeriksaan pengesahan pada setiap fasa: pengesahan langkah penaakulan, kebenaran tindakan, dan pensucian pemerhatian sebelum meneruskan.                             |   2   | D/V  |
| 9.10.6 | Sahkan bahawa metrik prestasi strategi penyelesaian masalah (masa pelaksanaan, penggunaan sumber, kualiti output) dipantau dengan amaran automatik apabila metrik menyimpang melebihi ambang yang ditetapkan.                         |   3   | D/V  |
| 9.10.7 | Sahkan bahawa pendekatan penaakulan hibrid yang menggabungkan pelbagai strategi mengekalkan pengesahan input dan kekangan keluaran bagi semua strategi yang menjadi komponennya tanpa memintas sebarang kawalan keselamatan.          |   3   | D/V  |
| 9.10.8 | Sahkan bahawa ujian keselamatan strategi penaakulan merangkumi fuzzing dengan input yang cacat, prompt antagonis yang direka untuk memaksa penukaran strategi, dan ujian keadaan sempadan untuk setiap pendekatan kognitif.           |   3   | D/V  |

---

## 9.11 Pengurusan Keadaan Kitaran Hayat Ejen & Keselamatan

Inisialisasi agen yang selamat, peralihan keadaan, dan penamatan dengan jejak audit kriptografi serta prosedur pemulihan yang ditetapkan.

|   #    | Description                                                                                                                                                                                                                                                                              | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.11.1 | Sahkan bahawa inisialisasi agen termasuk penetapan identiti kriptografi dengan kelayakan yang disokong perkakasan dan log audit permulaan yang tidak boleh diubah yang mengandungi ID agen, tanda masa, hash konfigurasi, dan parameter inisialisasi.                                    |   1   | D/V  |
| 9.11.2 | Sahkan bahawa peralihan keadaan ejen ditandatangani secara kriptografi, diberi cap masa, dan direkodkan dengan konteks lengkap termasuk peristiwa pencetus, hash keadaan sebelumnya, hash keadaan baru, dan pengesahan keselamatan yang dilakukan.                                       |   2   | D/V  |
| 9.11.3 | Sahkan bahawa prosedur penutupan ejen merangkumi penghapusan memori yang selamat menggunakan penghapusan kriptografi atau penulisan semula berbilang laluan, pembatalan kelayakan dengan pemberitahuan kepada pihak berkuasa sijil, dan penghasilan sijil penamatan yang tahan gangguan. |   2   | D/V  |
| 9.11.4 | Sahkan bahawa mekanisme pemulihan ejen mengesahkan integriti keadaan menggunakan cek kriptografi (minimum SHA-256) dan kembali ke keadaan yang diketahui baik apabila kerosakan dikesan dengan amaran automatik dan keperluan kelulusan manual.                                          |   3   | D/V  |
| 9.11.5 | Sahkan bahawa mekanisme ketahanan ejen menyulitkan data keadaan sensitif dengan kunci AES-256 setiap ejen dan melaksanakan putaran kunci selamat mengikut jadual yang boleh dikonfigurasi (maksimum 90 hari) dengan penyebaran tanpa henti operasi.                                      |   3   | D/V  |

---

## 9.12 Rangka Kerja Keselamatan Integrasi Alat

Kawalan keselamatan untuk pemuatan alat dinamik, pelaksanaan, dan pengesahan hasil dengan proses penilaian risiko dan kelulusan yang ditetapkan.

|   #    | Description                                                                                                                                                                                                                                                                    | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 9.12.1 | Sahkan bahawa penerangan alat termasuk metadata keselamatan yang menentukan keistimewaan yang diperlukan (baca/tulis/laksana), tahap risiko (rendah/sederhana/tinggi), had sumber (CPU, memori, rangkaian), dan keperluan pengesahan yang didokumentasikan dalam manifes alat. |   1   | D/V  |
| 9.12.2 | Sahkan bahawa keputusan pelaksanaan alat disahkan mengikut skema yang dijangkakan (Skema JSON, Skema XML) dan polisi keselamatan (penyucian output, pengelasan data) sebelum integrasi dengan had masa tamat dan prosedur pengendalian ralat.                                  |   1   | D/V  |
| 9.12.3 | Sahkan bahawa log interaksi alat termasuk konteks keselamatan terperinci termasuk penggunaan keistimewaan, corak akses data, masa pelaksanaan, penggunaan sumber, dan kod pulangan dengan log berstruktur untuk integrasi SIEM.                                                |   2   | D/V  |
| 9.12.4 | Sahkan bahawa mekanisme pemuatan alat dinamik mengesahkan tandatangan digital menggunakan infrastruktur PKI dan melaksanakan protokol pemuatan yang selamat dengan pengasingan sandbox serta pengesahan kebenaran sebelum pelaksanaan.                                         |   2   | D/V  |
| 9.12.5 | Sahkan bahawa penilaian keselamatan alat diaktifkan secara automatik untuk versi baru dengan pintu kelulusan wajib termasuk analisis statik, ujian dinamik, dan semakan pasukan keselamatan dengan kriteria kelulusan dan keperluan SLA yang didokumenkan.                     |   3   | D/V  |

---

### Rujukan

* [MITRE ATLAS tactics ML09](https://atlas.mitre.org/)
* [Circuit-breaker research for AI agents — Zou et al., 2024](https://arxiv.org/abs/2406.04313)
* [Trend Micro analysis of sandbox escapes in AI agents — Park, 2025](https://www.trendmicro.com/vinfo/us/security/news/cybercrime-and-digital-threats/unveiling-ai-agent-vulnerabilities-code-execution)
* [Auth0 guidance on human-in-the-loop authorization for agents — Martinez, 2025](https://auth0.com/blog/secure-human-in-the-loop-interactions-for-ai-agents/)
* [Medium deep-dive on MCP & A2A protocol hijacking — ForAISec, 2025](https://medium.com/%40foraisec/security-analysis-potential-ai-agent-hijacking-via-mcp-and-a2a-protocol-insights-cd1ec5e6045f)
* [Rapid7 fundamentals on spoofing attack prevention — 2024](https://www.rapid7.com/fundamentals/spoofing-attacks/)
* [Imperial College verification of swarm systems — Lomuscio et al.](https://sail.doc.ic.ac.uk/projects/swarms/)
* [NIST AI Risk Management Framework 1.0, 2023](https://nvlpubs.nist.gov/nistpubs/ai/nist.ai.100-1.pdf)
* [WIRED security briefing on encryption best practices, 2024](https://www.wired.com/story/encryption-apps-chinese-telecom-hacking-hydra-russia-exxon)
* [OWASP Top 10 for LLM Applications, 2025](https://owasp.org/www-project-top-10-for-large-language-model-applications/)
* [Comprehensive Vulnerability Analysis is Necessary for Trustworthy LLM-MAS](https://arxiv.org/html/2506.01245v1)
* [How Is LLM Reasoning Distracted by Irrelevant Context?
  An Analysis Using a Controlled Benchmark](https://www.arxiv.org/pdf/2505.18761)
* [Large Language Model Sentinel: LLM Agent for Adversarial Purification](https://arxiv.org/pdf/2405.20770)
* [Securing Agentic AI: A Comprehensive Threat Model and Mitigation Framework for Generative AI Agents](https://arxiv.org/html/2504.19956v2)

