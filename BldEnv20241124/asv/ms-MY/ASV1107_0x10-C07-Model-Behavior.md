# Perilaku Model C7, Kawalan Output & Jaminan Keselamatan

## Objektif Kawalan

Keluaran model mesti terstruktur, boleh dipercayai, selamat, boleh dijelaskan, dan dipantau secara berterusan dalam pengeluaran. Melakukan sedemikian mengurangkan halusinasi, kebocoran privasi, kandungan berbahaya, dan tindakan yang tidak terkawal, sambil meningkatkan kepercayaan pengguna dan pematuhan peraturan.

---

## C7.1 Penguatkuasaan Format Output

Skema ketat, penyahkodan terhad, dan pengesahan hiliran menghentikan kandungan yang salah bentuk atau berniat jahat sebelum ia tersebar.

|   #   | Description                                                                                                                                                                                                | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 7.1.1 | Sahkan bahawa skema respons (contohnya, Skema JSON) disediakan dalam arahan sistem dan setiap keluaran disahkan secara automatik; keluaran yang tidak mematuhi akan mencetuskan pembetulan atau penolakan. |   1   | D/V  |
| 7.1.2 | Sahkan bahawa penyahsulitan terhad (token berhenti, regex, max-token) diaktifkan untuk mengelakkan terlebih muatan atau saluran sisi suntikan arahan.                                                      |   1   | D/V  |
| 7.1.3 | Sahkan bahawa komponen hiliran menganggap keluaran sebagai tidak dipercayai dan memvalidasinya terhadap skema atau penyahseri selamat suntikan.                                                            |   2   | D/V  |
| 7.1.4 | Sahkan bahawa peristiwa output yang tidak betul dicatat, dihadkan kadar, dan dipaparkan kepada pemantauan.                                                                                                 |   3   |  V   |

---

## C7.2 Pengesanan & Pengurangan Halusinasi

Anggaran ketidakpastian dan strategi sandaran mengawal jawapan yang direka.

|   #   | Description                                                                                                                                                                                                  | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 7.2.1 | Sahkan bahawa log-kebarangkalian tahap token, keserasian kendiri ansambel, atau pengesan halusinasi yang telah disesuaikan memberikan skor keyakinan kepada setiap jawapan.                                  |   1   | D/V  |
| 7.2.2 | Sahkan bahawa maklum balas di bawah ambang keyakinan yang boleh dikonfigurasikan mencetuskan aliran kerja sandaran (contohnya, penjanaan dipertingkatkan pengambilan, model sekunder, atau semakan manusia). |   1   | D/V  |
| 7.2.3 | Sahkan bahawa insiden halusinasi ditandai dengan metadata punca-akar dan diberi makan kepada saluran post-mortem dan penalaan halus.                                                                         |   2   | D/V  |
| 7.2.4 | Sahkan bahawa ambang dan penderia dikalibrasi semula selepas kemas kini model atau pangkalan pengetahuan utama.                                                                                              |   3   | D/V  |
| 7.2.5 | Sahkan bahawa visualisasi papan pemuka mengesan kadar halusinasi.                                                                                                                                            |   3   |  V   |

---

## C7.3 Penapisan Keselamatan & Privasi Output

Penapis polisi dan liputan pasukan merah melindungi pengguna dan data sulit.

|   #   | Description                                                                                                                                                                                | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 7.3.1 | Sahkan bahawa pengklasifikasi sebelum dan selepas penjanaan menyekat kandungan kebencian, gangguan, penderaan diri, ekstremis, dan kandungan eksplisit seksual yang selaras dengan polisi. |   1   | D/V  |
| 7.3.2 | Sahkan bahawa pengesanan PII/PCI dan penyembunyian automatik dijalankan pada setiap respons; pelanggaran akan menyebabkan insiden privasi.                                                 |   1   | D/V  |
| 7.3.3 | Sahkan bahawa tag kerahsiaan (contohnya, rahsia perdagangan) disebarkan merentasi modaliti untuk mengelakkan kebocoran dalam teks, imej, atau kod.                                         |   2   |  D   |
| 7.3.4 | Sahkan bahawa percubaan untuk memintas penapis atau pengkelasan berisiko tinggi memerlukan kelulusan sekunder atau pengesahan semula pengguna.                                             |   3   | D/V  |
| 7.3.5 | Sahkan bahawa ambang penapisan mencerminkan bidang kuasa undang-undang dan konteks umur/peranan pengguna.                                                                                  |   3   | D/V  |

---

## C7.4 Had Pengeluaran & Tindakan

Had laju dan pintu kelulusan mengelakkan penyalahgunaan dan autonomi yang berlebihan.

|   #   | Description                                                                                                                                                                              | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 7.4.1 | Sahkan bahawa kuota setiap pengguna dan setiap kunci API menghadkan permintaan, token, dan kos dengan penangguhan eksponen pada ralat 429.                                               |   1   |  D   |
| 7.4.2 | Sahkan bahawa tindakan istimewa (penulisan fail, pelaksanaan kod, panggilan rangkaian) memerlukan kelulusan berasaskan dasar atau penglibatan manusia dalam proses.                      |   1   | D/V  |
| 7.4.3 | Sahkan bahawa pemeriksaan konsistensi silang modal memastikan imej, kod, dan teks yang dijana untuk permintaan yang sama tidak boleh digunakan untuk menyeludup kandungan berniat jahat. |   2   | D/V  |
| 7.4.4 | Sahkan bahawa kedalaman delegasi ejen, had rekursi, dan senarai alat yang dibenarkan telah dikonfigurasi secara eksplisit.                                                               |   2   |  D   |
| 7.4.5 | Sahkan bahawa pelanggaran had menghasilkan acara keselamatan berstruktur untuk pengambilan SIEM.                                                                                         |   3   |  V   |

---

## C7.5 Kebolehjelasan Output

Isyarat telus meningkatkan kepercayaan pengguna dan penyahpepijatan dalaman.

|   #   | Description                                                                                                                                    | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 7.5.1 | Sahkan bahawa skor keyakinan yang dihadapi pengguna atau ringkasan alasan ringkas didedahkan apabila penilaian risiko dianggap sesuai.         |   2   | D/V  |
| 7.5.2 | Sahkan bahawa penjelasan yang dijana mengelakkan pendedahan arahan sistem sensitif atau data proprietari.                                      |   2   | D/V  |
| 7.5.3 | Sahkan bahawa sistem menangkap log-kebarangkalian pada peringkat token atau peta perhatian dan menyimpannya untuk pemeriksaan yang dibenarkan. |   3   |  D   |
| 7.5.4 | Sahkan bahawa artifak kebolehterangan dikawal versi bersama-sama dengan pelepasan model untuk keboleh-auditan.                                 |   3   |  V   |

---

## C7.6 Pemantauan Integrasi

Pengamatan masa nyata menutup kitaran antara pembangunan dan pengeluaran.

|   #   | Description                                                                                                                                                               | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 7.6.1 | Sahkan bahawa metrik (pelanggaran skema, kadar halusinasi, ketoksikan, kebocoran PII, kelewatan, kos) dihantar ke platform pemantauan pusat.                              |   1   |  D   |
| 7.6.2 | Sahkan bahawa ambang amaran ditetapkan untuk setiap metrik keselamatan, dengan laluan eskalasi apabila panggilan diperlukan.                                              |   1   |  V   |
| 7.6.3 | Sahkan bahawa papan pemuka mengaitkan anomali output dengan model/versi, tanda ciri, dan perubahan data atas talian.                                                      |   2   |  V   |
| 7.6.4 | Sahkan bahawa data pemantauan diberikan balik ke dalam proses pelatihan semula, penalaan halus, atau kemas kini peraturan dalam aliran kerja MLOps yang didokumentasikan. |   2   | D/V  |
| 7.6.5 | Sahkan bahawa saluran pemantauan telah diuji penembusan dan dikawal akses untuk mengelakkan kebocoran log sensitif.                                                       |   3   |  V   |

---

## 7.7 Penjagaan Media Generatif

Pastikan sistem AI tidak menghasilkan kandungan media yang haram, berbahaya, atau tidak dibenarkan dengan menguatkuasakan sekatan polisi, pengesahan output, dan kebolehlacakan.

|   #   | Description                                                                                                                                                                                                              | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 7.7.1 | Sahkan bahawa arahan sistem dan arahan pengguna secara jelas melarang penghasilan media deepfake yang haram, berbahaya, atau tanpa persetujuan (contohnya, imej, video, audio).                                          |   1   | D/V  |
| 7.7.2 | Sahkan bahawa permintaan ditapis untuk cubaan menghasilkan peniruan, deepfake seksual eksplisit, atau media yang memaparkan individu sebenar tanpa keizinan.                                                             |   2   | D/V  |
| 7.7.3 | Sahkan bahawa sistem menggunakan penghashan persepsi, pengesanan tanda air, atau penandaan cap jari untuk mengelakkan pembiakan tidak sah media yang dilindungi hak cipta.                                               |   2   |  V   |
| 7.7.4 | Sahkan bahawa semua media yang dihasilkan ditandatangani secara kriptografi, ditempalkan tanda air, atau disisipkan dengan metadata asal ketahanan terhadap gangguan untuk jejak balik ke hiliran.                       |   3   | D/V  |
| 7.7.5 | Sahkan bahawa cubaan untuk memintas (contohnya, pengaburan arahan, bahasa slang, frasa bersifat adversarial) dikesan, direkodkan, dan dikawal kekerapannya; penyalahgunaan berulang dilaporkan kepada sistem pemantauan. |   3   |  V   |

## Rujukan

* [NIST AI Risk Management Framework](https://www.nist.gov/itl/ai-risk-management-framework)
* [ISO/IEC 42001:2023 – AI Management System](https://www.iso.org/obp/ui/en/)
* [OWASP Top-10 for Large Language Model Applications (2025)](https://owasp.org/www-project-top-10-for-large-language-model-applications/)
* [Improper Output Handling – OWASP LLM05:2025](https://genai.owasp.org/llmrisk/llm052025-improper-output-handling/)
* [Practical Techniques to Constrain LLM Output](https://mychen76.medium.com/practical-techniques-to-constraint-llm-output-in-json-format-e3e72396c670)
* [Dataiku – Structured Text Generation Guide](https://blog.dataiku.com/your-guide-to-structured-text-generation)
* [VL-Uncertainty: Detecting Hallucinations](https://arxiv.org/abs/2411.11919)
* [HaDeMiF: Hallucination Detection & Mitigation](https://openreview.net/forum?id=VwOYxPScxB)
* [Building Confidence in LLM Outputs](https://www.alkymi.io/data-science-room/building-confidence-in-llm-outputs)
* [Explainable AI & LLMs](https://duncsand.medium.com/explainable-ai-140912d31b3b)
* [LLM Red-Teaming Guide](https://www.confident-ai.com/blog/red-teaming-llms-a-step-by-step-guide)
* [Sensitive Information Disclosure in LLMs](https://virtualcyberlabs.com/llm-sensitive-information-disclosure/)
* [LangChain – Chat Model Rate Limiting](https://python.langchain.com/docs/how_to/chat_model_rate_limiting/)
* [OpenAI Rate-Limit & Exponential Back-off](https://hackernoon.com/openais-rate-limit-a-guide-to-exponential-backoff-for-llm-evaluation)
* [Arize AI – LLM Observability Platform](https://arize.com/)

