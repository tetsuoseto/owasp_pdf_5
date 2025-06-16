# Pengesahan Input Pengguna C2

## Objektif Kawalan

Pengesahan kukuh terhadap input pengguna adalah pertahanan barisan pertama terhadap beberapa serangan yang paling merosakkan pada sistem AI. Serangan suntikan prompt boleh menggantikan arahan sistem, membocorkan data sensitif, atau mengarahkan model ke tingkah laku yang tidak dibenarkan. Kecuali penapis khusus dan hierarki arahan disediakan, penyelidikan menunjukkan bahawa "multi-shot" jailbreak yang mengeksploitasi tetingkap konteks yang sangat panjang akan berkesan. Selain itu, serangan gangguan adversarial yang halus—seperti pertukaran homoglyph atau leetspeak—boleh diam-diam mengubah keputusan model.

---

## C2.1 Pertahanan Suntikan Prompt

Suntikan prompt adalah salah satu risiko utama untuk sistem AI. Pertahanan terhadap taktik ini menggunakan gabungan penapis corak statik, pengelasan dinamik dan penguatkuasaan hierarki arahan.

|   #   | Description                                                                                                                                                                                                                           | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 2.1.1 | Sahkan bahawa input pengguna disaring terhadap perpustakaan corak suntikan arahan yang diketahui yang sentiasa dikemas kini (kata kunci jailbreak, "abaikan sebelumnya", rantaian lakonan peranan, serangan HTML/URL tidak langsung). |   1   | D/V  |
| 2.1.2 | Sahkan bahawa sistem menguatkuasakan hierarki arahan di mana mesej sistem atau pemaju mengatasi arahan pengguna, walaupun selepas pengembangan tetingkap konteks.                                                                     |   1   | D/V  |
| 2.1.3 | Sahkan bahawa ujian penilaian adversarial (contohnya, arahan "banyak-senarai" Pasukan Merah) dijalankan sebelum setiap pelepasan model atau templat arahan, dengan ambang kadar kejayaan dan penghalang automatik untuk regresi.      |   2   | D/V  |
| 2.1.4 | Sahkan bahawa arahan yang berasal dari kandungan pihak ketiga (laman web, PDF, emel) disanitasi dalam konteks penguraian terpencil sebelum digabungkan ke dalam arahan utama.                                                         |   2   |  D   |
| 2.1.5 | Sahkan bahawa semua kemas kini peraturan penapis arahan, versi model pengelasan dan perubahan senarai blok adalah dikawal versi dan boleh diaudit.                                                                                    |   3   | D/V  |

---

## C2.2 Ketahanan Contoh Adversarial

Model Pemprosesan Bahasa Semulajadi (NLP) masih terdedah kepada gangguan halus pada tahap aksara atau perkataan yang sering terlepas pandang oleh manusia tetapi biasanya menyebabkan model salah klasifikasi.

|   #   | Description                                                                                                                                                                                                     | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 2.2.1 | Sahkan bahawa langkah normalisasi input asas (Unicode NFC, pemetaan homoglyph, pemangkasan ruang kosong) dijalankan sebelum tokenisasi.                                                                         |   1   |  D   |
| 2.2.2 | Sahkan bahawa pengesanan anomali statistik menandakan input dengan jarak suntingan yang luar biasa tinggi kepada norma bahasa, token berulang yang berlebihan, atau jarak embedding yang luar biasa.            |   2   | D/V  |
| 2.2.3 | Sahkan bahawa saluran inferens menyokong varian model yang diperkeras dengan latihan adversarial pilihan atau lapisan pertahanan (contohnya, pengacakan, distilasi defensif) untuk titik akhir berisiko tinggi. |   2   |  D   |
| 2.2.4 | Sahkan bahawa input bermusuhan yang disyaki diasingkan, direkodkan dengan muatan penuh (selepas penyuntingan PII).                                                                                              |   2   |  V   |
| 2.2.5 | Sahkan bahawa metrik ketahanan (kadar kejayaan set serangan yang diketahui) dipantau dari masa ke masa dan regresi mencetuskan penghalang pelepasan.                                                            |   3   | D/V  |

---

## C2.3 Validasi Skema, Jenis & Panjang

Serangan AI yang melibatkan input yang cacat atau terlalu besar boleh menyebabkan ralat penguraian, tumpahan arahan merentasi medan, dan keletihan sumber. Penguatkuasaan skema yang ketat juga merupakan prasyarat apabila melakukan panggilan alat deterministik.

|   #   | Description                                                                                                                                                                                     | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 2.3.1 | Sahkan bahawa setiap titik akhir panggilan API atau fungsi mempunyai skema input yang jelas (JSON Schema, Protobuf atau setara multimodal) dan bahawa input disahkan sebelum pemasangan prompt. |   1   |  D   |
| 2.3.2 | Sahkan bahawa input yang melebihi had token atau bait maksimum ditolak dengan ralat selamat dan tidak pernah dipotong secara senyap.                                                            |   1   | D/V  |
| 2.3.3 | Sahkan bahawa pemeriksaan jenis (contohnya, julat nombor, nilai enum, jenis MIME untuk imej/audio) dilaksanakan di sisi pelayan, bukan hanya dalam kod klien.                                   |   2   | D/V  |
| 2.3.4 | Sahkan bahawa validator semantik (contohnya, Skema JSON) berjalan dalam masa tetap untuk mengelakkan serangan DoS algoritma.                                                                    |   2   |  D   |
| 2.3.5 | Sahkan bahawa kegagalan pengesahan direkodkan dengan petikan muatan yang disunting dan kod ralat yang jelas untuk membantu triase keselamatan.                                                  |   3   |  V   |

---

## C2.4 Penapisan Kandungan & Polisi

Pembangun harus dapat mengesan arahan yang sah secara sintaksis yang meminta kandungan yang tidak dibenarkan (seperti arahan haram, ucapan kebencian, dan teks yang berhak cipta) kemudian menghalangnya daripada tersebar.

|   #   | Description                                                                                                                                                                                                                                          | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 2.4.1 | Sahkan bahawa pengelasan kandungan (tanpa latihan awal atau yang telah dilatih halus) menilai setiap input untuk keganasan, mencederakan diri sendiri, kebencian, kandungan seksual dan permintaan haram, dengan ambang yang boleh dikonfigurasikan. |   1   |  D   |
| 2.4.2 | Sahkan bahawa input yang melanggar polisi akan menerima penolakan standard atau penyelesaian selamat supaya ia tidak akan tersebar ke panggilan LLM hiliran.                                                                                         |   1   | D/V  |
| 2.4.3 | Sahkan bahawa model penapisan atau set peraturan dilatih semula/dikemas kini sekurang-kurangnya setiap suku tahun, dengan memasukkan corak jailbreak atau bypass polisi yang baru diperhatikan.                                                      |   2   |  D   |
| 2.4.4 | Sahkan bahawa saringan mematuhi dasar khusus pengguna (umur, kekangan undang-undang serantau) melalui peraturan berasaskan atribut yang diselesaikan pada waktu permintaan.                                                                          |   2   |  D   |
| 2.4.5 | Sahkan bahawa log penapisan mengandungi skor keyakinan pengklasifikasi dan tag kategori dasar untuk korelasi SOC dan main semula pasukan merah masa depan.                                                                                           |   3   |  V   |

---

## C2.5 Penghadang Kadar Input & Pencegahan Penyalahgunaan

Pembangun harus mencegah penyalahgunaan, kehabisan sumber, dan serangan automatik terhadap sistem AI dengan menghadkan kadar input dan mengesan corak penggunaan yang luar biasa.

|   #   | Description                                                                                                                                               | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 2.5.1 | Sahkan bahawa had kadar per pengguna, per IP, dan per kekunci API dikuatkuasakan untuk semua titik akhir input.                                           |   1   | D/V  |
| 2.5.2 | Sahkan bahawa had kadar ledakan dan berterusan telah disesuaikan untuk menghalang serangan DoS dan serangan paksa kasar.                                  |   2   | D/V  |
| 2.5.3 | Sahkan bahawa corak penggunaan yang ganjil (contohnya, permintaan berturut-turut dengan cepat, banjir input) mencetuskan sekatan automatik atau eskalasi. |   2   | D/V  |
| 2.5.4 | Sahkan bahawa log pencegahan penyalahgunaan disimpan dan disemak untuk corak serangan yang muncul.                                                        |   3   |  V   |

---

## C2.6 Pengesahan Input Multi-Modular

Sistem AI harus merangkumi pengesahan yang kukuh untuk input bukan teks (imej, audio, fail) bagi mencegah suntikan, pengelakan, atau penyalahgunaan sumber.

|   #   | Description                                                                                                       | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 2.6.1 | Sahkan bahawa semua input bukan teks (imej, audio, fail) disahkan untuk jenis, saiz, dan format sebelum diproses. |   1   |  D   |
| 2.6.2 | Sahkan bahawa fail telah diimbas untuk perisian hasad dan muatan steganografi sebelum pengambilan.                |   2   | D/V  |
| 2.6.3 | Sahkan bahawa input imej/audio diperiksa untuk gangguan adversarial atau corak serangan yang diketahui.           |   2   | D/V  |
| 2.6.4 | Sahkan bahawa kegagalan pengesahan input multi-modal direkodkan dan mencetuskan amaran untuk siasatan.            |   3   |  V   |

---

## C2.7 Asal-usul Input & Penentuan Atribusi

Sistem AI harus menyokong pengauditan, penjejakan penyalahgunaan, dan pematuhan dengan memantau serta menandakan asal-usul semua input pengguna.

|   #   | Description                                                                                                                         | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 2.7.1 | Sahkan bahawa semua input pengguna ditandai dengan metadata (ID pengguna, sesi, sumber, cap masa, alamat IP) semasa kemasukan data. |   1   | D/V  |
| 2.7.2 | Sahkan bahawa metadata asal-usul dikekalkan dan dapat diaudit untuk semua input yang diproses.                                      |   2   | D/V  |
| 2.7.3 | Sahkan bahawa sumber input yang luar biasa atau tidak dipercayai ditandakan dan dikenakan pemeriksaan yang diperketat atau disekat. |   2   | D/V  |

---

## C2.8 Pengesanan Ancaman Adaptif Masa Nyata

Pembangun harus menggunakan sistem pengesanan ancaman canggih untuk AI yang menyesuaikan diri dengan corak serangan baru dan menyediakan perlindungan masa nyata dengan padanan corak terkompilasi.

|   #   | Description                                                                                                                                                                                      | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 2.8.1 | Sahkan bahawa corak pengesanan ancaman disusun ke dalam enjin regex yang dioptimumkan untuk penapisan masa nyata berprestasi tinggi dengan impak latensi yang minimum.                           |   1   | D/V  |
| 2.8.2 | Sahkan bahawa sistem pengesanan ancaman mengekalkan perpustakaan corak yang berasingan untuk kategori ancaman yang berbeza (suntikan arahan, kandungan berbahaya, data sensitif, arahan sistem). |   1   | D/V  |
| 2.8.3 | Sahkan bahawa pengesanan ancaman adaptif menggabungkan model pembelajaran mesin yang mengemas kini sensitiviti ancaman berdasarkan kekerapan serangan dan kadar kejayaan.                        |   2   | D/V  |
| 2.8.4 | Sahkan bahawa suapan intelijen ancaman waktu nyata secara automatik mengemas kini perpustakaan corak dengan tandatangan serangan baru dan IOCs (Penunjuk Kompromi).                              |   2   | D/V  |
| 2.8.5 | Sahkan bahawa kadar positif palsu pengesanan ancaman dipantau secara berterusan dan kekhususan corak diselaraskan secara automatik untuk meminimumkan gangguan terhadap kes penggunaan yang sah. |   3   | D/V  |
| 2.8.6 | Sahkan bahawa analisis ancaman kontekstual mengambil kira sumber input, corak tingkah laku pengguna, dan sejarah sesi untuk meningkatkan ketepatan pengesanan.                                   |   3   | D/V  |
| 2.8.7 | Sahkan bahawa metrik prestasi pengesanan ancaman (kadar pengesanan, kelewatan pemprosesan, penggunaan sumber) dipantau dan dioptimumkan secara masa nyata.                                       |   3   | D/V  |

---

## C2.9 Saluran Pengesahan Keselamatan Pelbagai Mod

Pembangun harus menyediakan pengesahan keselamatan untuk teks, imej, audio, dan modaliti input AI lain dengan jenis pengesanan ancaman tertentu dan pengasingan sumber.

|   #   | Description                                                                                                                                                                                                                                                              | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 2.9.1 | Sahkan bahawa setiap modal input mempunyai validator keselamatan khusus dengan corak ancaman yang didokumenkan (teks: suntikan arahan, imej: steganografi, audio: serangan spektrogram) dan ambang pengesanan.                                                           |   1   | D/V  |
| 2.9.2 | Sahkan bahawa input multi-modal diproses dalam ruang pasir terpencil dengan had sumber yang ditentukan (memori, CPU, masa pemprosesan) khusus untuk setiap jenis modaliti dan didokumentasikan dalam dasar keselamatan.                                                  |   2   | D/V  |
| 2.9.3 | Sahkan bahawa pengesanan serangan rentas-modal mengenal pasti serangan berkoordinasi yang merangkumi pelbagai jenis input (contohnya, muatan steganografi dalam imej digabungkan dengan suntikan arahan dalam teks) menggunakan peraturan korelasi dan penjanaan amaran. |   2   | D/V  |
| 2.9.4 | Sahkan bahawa kegagalan pengesahan multi-modal mencetuskan pencatatan terperinci termasuk semua modaliti input, keputusan pengesahan, skor ancaman, dan analisis korelasi dengan format log berstruktur untuk integrasi SIEM.                                            |   3   | D/V  |
| 2.9.5 | Sahkan bahawa pengklasifikasi kandungan khusus modaliti dikemas kini mengikut jadual yang didokumentasikan (minimum suku tahunan) dengan corak ancaman baharu, contoh adversarial, dan penanda aras prestasi dikekalkan di atas ambang asas.                             |   3   | D/V  |

---

## Rujukan

* [LLM01:2025 Prompt Injection – OWASP Top 10 for LLM & Generative AI Security](https://genai.owasp.org/llmrisk/llm01-prompt-injection/)
* [Generative AI's Biggest Security Flaw Is Not Easy to Fix](https://www.wired.com/story/generative-ai-prompt-injection-hacking)
* [Many-shot jailbreaking \ Anthropic](https://www.anthropic.com/research/many-shot-jailbreaking)
* [$PDF$ OpenAI GPT-4.5 System Card](https://cdn.openai.com/gpt-4-5-system-card-2272025.pdf)
* [Notebook for the CheckThat Lab at CLEF 2024](https://ceur-ws.org/Vol-3740/paper-53.pdf)
* [Mitigate jailbreaks and prompt injections – Anthropic](https://docs.anthropic.com/en/docs/test-and-evaluate/strengthen-guardrails/mitigate-jailbreaks)
* [Chapter 3 MITRE ATT\&CK – Adversarial Model Analysis](https://ama.drwhy.ai/mitre-attck.html)
* [OWASP Top 10 for LLM Applications 2025 – WorldTech IT](https://wtit.com/blog/2025/04/17/owasp-top-10-for-llm-applications-2025/)
* [OWASP Machine Learning Security Top Ten](https://owasp.org/www-project-machine-learning-security-top-10/)
* [Few words about AI Security – Jussi Metso](https://www.jussimetso.com/index.php/2024/09/28/few-words-about-ai-security/)
* [How To Ensure LLM Output Adheres to a JSON Schema | Modelmetry](https://modelmetry.com/blog/how-to-ensure-llm-output-adheres-to-a-json-schema)
* [Easily enforcing valid JSON schema following – API](https://community.openai.com/t/feature-request-function-calling-easily-enforcing-valid-json-schema-following/263515?utm_source)
* [AI Safety + Cybersecurity R\&D Tracker – Fairly AI](https://www.fairly.ai/blog/ai-cybersecurity-tracker)
* [Anthropic makes 'jailbreak' advance to stop AI models producing harmful results](https://www.ft.com/content/cf11ebd8-aa0b-4ed4-945b-a5d4401d186e)
* [Pattern matching filter rules - IBM](https://www.ibm.com/docs/ssw_aix_71/security/intrusion_pattern_matching_filter_rules.html)
* [Real-time Threat Detection](https://www.darktrace.com/cyber-ai-glossary/real-time-threat-detection)

