# C5 Kawalan Akses & Identiti untuk Komponen & Pengguna AI

## Objektif Kawalan

Kawalan akses yang berkesan untuk sistem AI memerlukan pengurusan identiti yang kukuh, kebenaran yang sedar konteks, dan penguatkuasaan semasa berjalan mengikut prinsip kepercayaan sifar. Kawalan ini memastikan bahawa manusia, perkhidmatan, dan ejen autonomi hanya berinteraksi dengan model, data, dan sumber pengkomputeran dalam skop yang diberikan secara eksplisit, dengan keupayaan pengesahan berterusan dan audit.

---

## C5.1 Pengurusan Identiti & Pengesahan

Wujudkan identiti yang disokong secara kriptografi untuk semua entiti dengan pengesahan berbilang faktor bagi operasi berhak istimewa.

|   #   | Description                                                                                                                                                                                                                                       | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 5.1.1 | Sahkan bahawa semua pengguna manusia dan prinsipal perkhidmatan mengesahkan melalui penyedia identiti perusahaan berpusat (IdP) menggunakan protokol OIDC/SAML dengan pemetaan identiti-ke-token yang unik (tiada akaun atau kelayakan dikongsi). |   1   | D/V  |
| 5.1.2 | Sahkan bahawa operasi berisiko tinggi (penyebaran model, eksport berat, akses data latihan, perubahan konfigurasi produksi) memerlukan pengesahan pelbagai faktor atau pengesahan tahap lanjut dengan pengesahan semula sesi.                     |   1   | D/V  |
| 5.1.3 | Sahkan bahawa pengetua baru menjalani bukti identiti yang selaras dengan NIST 800-63-3 IAL-2 atau piawaian setara sebelum menerima akses sistem produksi.                                                                                         |   2   |  D   |
| 5.1.4 | Sahkan bahawa semakan akses dijalankan setiap suku tahun dengan pengesanan automatik akaun tidak aktif, penguatkuasaan putaran kelayakan, dan aliran kerja penamatan provisi.                                                                     |   2   |  V   |
| 5.1.5 | Sahkan bahawa ejen AI berpersekutuan mengesahkan melalui pernyataan JWT yang ditandatangani yang mempunyai hayat maksimum 24 jam dan termasuk bukti kriptografi asal.                                                                             |   3   | D/V  |

---

## C5.2 Kebenaran Sumber & Privilege Paling Minimum

Laksanakan kawalan akses terperinci untuk semua sumber AI dengan model kebenaran yang jelas dan jejak audit.

|   #   | Description                                                                                                                                                                                                                   | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 5.2.1 | Sahkan bahawa setiap sumber AI (set data, model, titik akhir, koleksi vektor, indeks embedding, instans pengkomputeran) menguatkuasakan kawalan akses berasaskan peranan dengan senarai benaran jelas dan polisi tolak lalai. |   1   | D/V  |
| 5.2.2 | Sahkan bahawa prinsip hak keistimewaan minimum dikuatkuasakan secara lalai dengan akaun perkhidmatan bermula dengan kebenaran baca sahaja dan justifikasi perniagaan yang didokumentasikan diperlukan untuk akses tulis.      |   1   | D/V  |
| 5.2.3 | Sahkan bahawa semua pengubahsuaian kawalan akses berkaitan dengan permintaan perubahan yang diluluskan dan direkodkan secara kekal dengan cap masa, identiti pelaku, pengecam sumber, dan perbezaan kebenaran.                |   1   |  V   |
| 5.2.4 | Sahkan bahawa label pengelasan data (PII, PHI, dikawal eksport, proprietari) secara automatik tersebar ke sumber terbitan (pembentukan petikan, cache arahan, output model) dengan penguatkuasaan polisi yang konsisten.      |   2   |  D   |
| 5.2.5 | Sahkan bahawa percubaan akses tanpa kebenaran dan kejadian peningkatan keistimewaan mencetuskan amaran masa nyata dengan metadata kontekstual kepada sistem SIEM dalam masa 5 minit.                                          |   2   | D/V  |

---

## C5.3 Penilaian Polisi Dinamik

Deploy enjin kawalan akses berasaskan atribut (ABAC) untuk keputusan kebenaran yang peka konteks dengan keupayaan audit.

|   #   | Description                                                                                                                                                                                           | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 5.3.1 | Sahkan bahawa keputusan kebenaran dialihkan ke enjin polisi khusus (OPA, Cedar, atau setaraf) yang boleh diakses melalui API yang diautentikasi dengan perlindungan integriti kriptografi.            |   1   | D/V  |
| 5.3.2 | Sahkan bahawa polisi menilai atribut dinamik semasa waktu pelaksanaan termasuk tahap kelulusan pengguna, klasifikasi kepekaan sumber, konteks permintaan, pengasingan penyewa, dan kekangan temporal. |   1   | D/V  |
| 5.3.3 | Sahkan bahawa definisi polisi dikawal versi, disemak oleh rakan sekerja, dan disahkan melalui ujian automatik dalam laluan CI/CD sebelum penyebaran ke produksi.                                      |   2   |  D   |
| 5.3.4 | Sahkan bahawa hasil penilaian dasar termasuk rasional keputusan berstruktur dan dihantar ke sistem SIEM untuk analisis korelasi dan pelaporan pematuhan.                                              |   2   |  V   |
| 5.3.5 | Sahkan bahawa nilai masa hidup (TTL) cache dasar tidak melebihi 5 minit untuk sumber berkepekaan tinggi dan 1 jam untuk sumber standard dengan keupayaan tidak sah cache.                             |   3   | D/V  |

---

## C5.4 Penguatkuasaan Keselamatan Masa Pertanyaan

Laksanakan kawalan keselamatan lapisan pangkalan data dengan penapisan wajib dan polisi keselamatan tahap baris.

|   #   | Description                                                                                                                                                                                                                       | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 5.4.1 | Sahkan bahawa semua pertanyaan pangkalan data vektor dan SQL termasuk penapis keselamatan wajib (ID penyewa, label sensitiviti, skop pengguna) yang dikuatkuasakan pada peringkat enjin pangkalan data, bukan kod aplikasi.       |   1   | D/V  |
| 5.4.2 | Sahkan bahawa dasar keselamatan tahap baris (RLS) dan pengecatan tahap medan diaktifkan dengan pewarisan dasar untuk semua pangkalan data vektor, indeks carian, dan set data latihan.                                            |   1   | D/V  |
| 5.4.3 | Sahkan bahawa penilaian kebenaran yang gagal akan menghalang "serangan pegawai yang keliru" dengan segera memberhentikan pertanyaan dan mengembalikan kod ralat kebenaran yang jelas daripada mengembalikan set keputusan kosong. |   2   |  D   |
| 5.4.4 | Sahkan bahawa latensi penilaian polisi dipantau secara berterusan dengan amaran automatik untuk keadaan tamat masa yang boleh membolehkan pengelakan kebenaran.                                                                   |   2   |  V   |
| 5.4.5 | Sahkan bahawa mekanisme cuba semula pertanyaan menilai semula dasar kebenaran untuk mengambil kira perubahan keizinan dinamik dalam sesi pengguna yang aktif.                                                                     |   3   | D/V  |

---

## Penapisan Output C5.5 & Pencegahan Kehilangan Data

Laksanakan kawalan pasca pemprosesan untuk mencegah pendedahan data tanpa kebenaran dalam kandungan yang dijana AI.

|   #   | Description                                                                                                                                                                                         | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 5.5.1 | Sahkan bahawa mekanisme penapisan selepas inferens mengimbas dan menyunting PII yang tidak dibenarkan, maklumat berklasifikasi, dan data proprietari sebelum menyampaikan kandungan kepada pemohon. |   1   | D/V  |
| 5.5.2 | Sahkan bahawa sitasi, rujukan, dan atribusi sumber dalam keluaran model disahkan mengikut kelayakan pemanggil dan dikeluarkan jika akses tanpa kebenaran dikesan.                                   |   1   | D/V  |
| 5.5.3 | Sahkan bahawa sekatan format output (PDF yang disanitasi, imej yang metadata telah dibuang, jenis fail yang diluluskan) dipatuhi berdasarkan tahap kebenaran pengguna dan klasifikasi data.         |   2   |  D   |
| 5.5.4 | Sahkan bahawa algoritma penyuntingan adalah deterministik, dikawal versi, dan mengekalkan log audit untuk menyokong siasatan pematuhan dan analisis forensik.                                       |   2   |  V   |
| 5.5.5 | Sahkan bahawa acara penapisan risiko tinggi menghasilkan log adaptif yang termasuk hash kriptografi kandungan asal untuk pengambilan forensik tanpa pendedahan data.                                |   3   |  V   |

---

## C5.6 Pengasingan Pelbagai Penyewa

Pastikan pengasingan kriptografi dan logik antara penyewa dalam infrastruktur AI bersama.

|   #   | Description                                                                                                                                                                                             | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 5.6.1 | Sahkan bahawa ruang memori, stor penanaman, entri cache, dan fail sementara diasingkan mengikut ruang nama bagi setiap penyewa dengan pembersihan selamat apabila penyewa dipadam atau sesi ditamatkan. |   1   | D/V  |
| 5.6.2 | Sahkan bahawa setiap permintaan API termasuk pengecam penyewa yang diautentikasi yang disahkan secara kriptografi terhadap konteks sesi dan hak pengguna.                                               |   1   | D/V  |
| 5.6.3 | Sahkan bahawa dasar rangkaian melaksanakan peraturan tolak-lalai untuk komunikasi antara penyewa dalam mesh perkhidmatan dan platform pengurusan kontena.                                               |   2   |  D   |
| 5.6.4 | Sahkan bahawa kunci penyulitan adalah unik bagi setiap penyewa dengan sokongan kunci yang diuruskan oleh pelanggan (CMK) dan pemisahan kriptografi antara stor data penyewa.                            |   3   |  D   |

---

## C5.7 Kebenaran Ejen Autonomi

Kawal kebenaran untuk ejen AI dan sistem autonomi melalui token keupayaan berskala dan kebenaran berterusan.

|   #   | Description                                                                                                                                                                                                                   | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 5.7.1 | Sahkan bahawa ejen autonomi menerima token keupayaan berskop yang secara eksplisit menyenaraikan tindakan yang dibenarkan, sumber yang boleh diakses, had masa, dan kekangan operasi.                                         |   1   | D/V  |
| 5.7.2 | Sahkan bahawa kebolehan berisiko tinggi (akses sistem fail, pelaksanaan kod, panggilan API luaran, transaksi kewangan) dimatikan secara lalai dan memerlukan kebenaran jelas untuk diaktifkan beserta justifikasi perniagaan. |   1   | D/V  |
| 5.7.3 | Sahkan bahawa token kapasiti diikat kepada sesi pengguna, termasuk perlindungan integriti kriptografi, dan pastikan ia tidak boleh disimpan atau digunakan semula dalam senario luar talian.                                  |   2   |  D   |
| 5.7.4 | Sahkan bahawa tindakan yang dimulakan oleh ejen melalui kebenaran sekunder menggunakan enjin polisi ABAC dengan penilaian konteks penuh dan pencatatan audit.                                                                 |   2   |  V   |
| 5.7.5 | Sahkan bahawa syarat ralat agen dan pengendalian pengecualian merangkumi maklumat skop keupayaan untuk menyokong analisis insiden dan penyiasatan forensik.                                                                   |   3   |  V   |

---

## Rujukan

### Standard & Rangka Kerja

* [NIST SP 800-63-3: Digital Identity Guidelines](https://pages.nist.gov/800-63-3/)
* [Zero Trust Architecture – NIST SP 800-207](https://nvlpubs.nist.gov/nistpubs/specialpublications/NIST.SP.800-207.pdf)
* [OWASP Application Security Verification Standard (AISVS)](https://owasp.org/www-project-application-security-verification-standard/)
  ​
### Panduan Pelaksanaan

* [Identity and Access Management in the AI Era: 2025 Guide – IDSA](https://www.idsalliance.org/blog/identity-and-access-management-in-the-ai-era-2025-guide/)
* [Attribute-Based Access Control with OPA – Permify](https://medium.com/permify-tech-blog/attribute-based-access-control-abac-implementation-with-open-policy-agent-opa-b47052248f29)
* [How We Designed Cedar to Be Intuitive, Fast, and Safe – AWS](https://aws.amazon.com/blogs/security/how-we-designed-cedar-to-be-intuitive-to-use-fast-and-safe/)
  ​
### Keselamatan Khusus AI

* [Row Level Security in Vector DBs for RAG – Bluetuple.ai](https://medium.com/bluetuple-ai/implementing-row-level-security-in-vector-dbs-for-rag-applications-fdbccb63d464)
* [Tenant Isolation in Multi-Tenant Systems – WorkOS](https://workos.com/blog/tenant-isolation-in-multi-tenant-systems)
* [Handling AI Agent Permissions – Stytch](https://stytch.com/blog/handling-ai-agent-permissions/)
* [OWASP Top 10 for Large Language Model Applications](https://owasp.org/www-project-top-10-for-large-language-model-applications/)

