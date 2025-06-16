# Keselamatan Infrastruktur, Konfigurasi & Penyebaran C4

## Objektif Kawalan

Infrastruktur AI mesti diperkuat terhadap eskalasi keistimewaan, penyalahgunaan rantaian bekalan, dan pergerakan lateral melalui konfigurasi selamat, pengasingan masa jalan, saluran penyebaran yang dipercayai, dan pemantauan menyeluruh. Hanya komponen dan konfigurasi infrastruktur yang sah dan disahkan yang mencapai pengeluaran melalui proses terkawal yang mengekalkan keselamatan, integriti, dan kebolehauditan.

Matlamat Keselamatan Teras: Hanya komponen infrastruktur yang ditandatangani secara kriptografi dan telah diuji kerentanan yang sampai ke pengeluaran melalui saluran pengesahan automatik yang menguatkuasakan dasar keselamatan dan mengekalkan jejak audit yang tidak berubah.

---

## C4.1 Pengasingan Persekitaran Masa Jalan

Menghalang larian kontena dan peningkatan keistimewaan melalui primitif pengasingan peringkat kernel dan kawalan akses mandatori.

|   #   | Description                                                                                                                                                                                                                          | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 4.1.1 | Sahkan bahawa semua bekas AI menurunkan SEMUA keupayaan Linux kecuali CAP_SETUID, CAP_SETGID, dan keupayaan yang secara eksplisit diperlukan yang didokumentasikan dalam asas keselamatan.                                           |   1   | D/V  |
| 4.1.2 | Sahkan bahawa profil seccomp menyekat semua panggilan sistem kecuali yang terdapat dalam senarai putih yang telah diluluskan terlebih dahulu, dengan pelanggaran menyebabkan kontena dihentikan dan menghasilkan amaran keselamatan. |   1   | D/V  |
| 4.1.3 | Sahkan bahawa beban kerja AI dijalankan dengan filesystem root hanya boleh baca, tmpfs untuk data sementara, dan volum bernama untuk data berterusan dengan pilihan mount noexec dikuatkuasakan.                                     |   2   | D/V  |
| 4.1.4 | Sahkan bahawa pemantauan runtime berasaskan eBPF (Falco, Tetragon, atau setara) mengesan cubaan peningkatan keistimewaan dan secara automatik menghentikan proses yang melanggar dalam tempoh masa tindak balas organisasi.          |   2   | D/V  |
| 4.1.5 | Sahkan bahawa beban kerja AI berisiko tinggi dijalankan dalam persekitaran yang terasing pada perkakasan (Intel TXT, AMD SVM, atau nod bare-metal khusus) dengan pengesahan attestation.                                             |   3   | D/V  |

---

## C4.2 Saluran Pemasangan & Penyebaran Selamat

Pastikan integriti kriptografi dan keselamatan rantaian bekalan melalui binaan yang boleh dihasilkan semula dan artifak yang ditandatangani.

|   #   | Description                                                                                                                                                                                       | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.2.1 | Sahkan bahawa infrastruktur sebagai kod imbas dengan alat (tfsec, Checkov, atau Terrascan) pada setiap komit, menghalang penggabungan dengan penemuan KETERANGAN KRITIKAL atau TINGGI.            |   1   | D/V  |
| 4.2.2 | Sahkan bahawa pembinaan kontena boleh dihasilkan semula dengan hash SHA256 yang sama merentasi pembinaan dan hasilkan perakuan asal SLSA Tahap 3 yang ditandatangani dengan Sigstore.             |   1   | D/V  |
| 4.2.3 | Sahkan bahawa imej kontena memasukkan CycloneDX atau SPDX SBOM dan ditandatangani dengan Cosign sebelum tolak ke dalam registri, dengan imej yang tidak ditandatangani ditolak semasa penyebaran. |   2   | D/V  |
| 4.2.4 | Sahkan bahawa paip CI/CD menggunakan token OIDC dari HashiCorp Vault, Peranan IAM AWS, atau Identiti Terurus Azure dengan tempoh tidak melebihi had dasar keselamatan organisasi.                 |   2   | D/V  |
| 4.2.5 | Sahkan bahawa tandatangan Cosign dan provenance SLSA disahkan semasa proses penyebaran sebelum pelaksanaan kontena dan bahawa ralat pengesahan menyebabkan penyebaran gagal.                      |   2   | D/V  |
| 4.2.6 | Sahkan bahawa persekitaran binaan dijalankan dalam bekas sementara atau VM tanpa storan kekal dan pengasingan rangkaian daripada VPC pengeluaran.                                                 |   2   | D/V  |

---

## C4.3 Keselamatan Rangkaian & Kawalan Akses

Laksanakan rangkaian sifar-kepercayaan dengan dasar tolak-layan lalai dan komunikasi yang disulitkan.

|   #   | Description                                                                                                                                                                                            | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 4.3.1 | Sahkan bahawa Kubernetes NetworkPolicies atau sebarang setara melaksanakan deny lalai untuk ingress/egress dengan peraturan benarkan yang jelas untuk port yang diperlukan (443, 8080, dan lain-lain). |   1   | D/V  |
| 4.3.2 | Sahkan bahawa SSH (port 22), RDP (port 3389), dan titik akhir metadata awan (169.254.169.254) telah disekat atau memerlukan pengesahan berasaskan sijil.                                               |   1   | D/V  |
| 4.3.3 | Sahkan bahawa trafik egress ditapis melalui proksi HTTP/HTTPS (Squid, Istio, atau pintu masuk NAT awan) dengan senarai putih domain dan permintaan yang disekat direkodkan.                            |   2   | D/V  |
| 4.3.4 | Sahkan bahawa komunikasi antara perkhidmatan menggunakan mutual TLS dengan sijil yang dipusing mengikut dasar organisasi dan pengesahan sijil dikuatkuasakan (tanpa bendera langkau-sahkan).           |   2   | D/V  |
| 4.3.5 | Sahkan bahawa infrastruktur AI berjalan dalam VPC/VNet khas tanpa akses internet terus dan berkomunikasi hanya melalui gerbang NAT atau hos bastion.                                                   |   2   | D/V  |

---

## C4.4 Pengurusan Rahsia & Kunci Kriptografi

Lindungi kelayakan melalui penyimpanan berasaskan perkakasan dan putaran automatik dengan akses tanpa kepercayaan.

|   #   | Description                                                                                                                                                                            | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.4.1 | Sahkan bahawa rahsia disimpan dalam HashiCorp Vault, AWS Secrets Manager, Azure Key Vault, atau Google Secret Manager dengan penyulitan ketika tidak aktif menggunakan AES-256.        |   1   | D/V  |
| 4.4.2 | Sahkan bahawa kunci kriptografi dijana dalam HSM Tahap 2 FIPS 140-2 (AWS CloudHSM, Azure Dedicated HSM) dengan putaran kunci mengikut dasar kriptografi organisasi.                    |   1   | D/V  |
| 4.4.3 | Sahkan bahawa putaran rahsia adalah automatik dengan pelaksanaan tanpa henti dan putaran segera dicetuskan oleh perubahan kakitangan atau insiden keselamatan.                         |   2   | D/V  |
| 4.4.4 | Sahkan bahawa imej kontena diimbas dengan alat (GitLeaks, TruffleHog, atau detect-secrets) yang menghalang binaan yang mengandungi kunci API, kata laluan, atau sijil.                 |   2   | D/V  |
| 4.4.5 | Sahkan bahawa akses rahsia produksi memerlukan MFA dengan token perkakasan (YubiKey, FIDO2) dan direkodkan oleh log audit tidak boleh ubah dengan identiti pengguna dan cap masa.      |   2   | D/V  |
| 4.4.6 | Sahkan bahawa rahsia disuntik melalui rahsia Kubernetes, volum yang dipasang, atau kontena init dan pastikan rahsia tidak pernah disematkan dalam pembolehubah persekitaran atau imej. |   2   | D/V  |

---

## C4.5 Pengujian dan Pengesahan Bebas Beban Kerja AI

Mengasingkan model AI yang tidak dipercayai dalam kotak pasir yang selamat dengan analisis tingkah laku yang menyeluruh.

|   #   | Description                                                                                                                                                                                                     | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.5.1 | Sahkan bahawa model AI luaran dijalankan dalam gVisor, microVM (seperti Firecracker, CrossVM), atau bekas Docker dengan pilihan --security-opt=no-new-privileges dan bendera --read-only.                       |   1   | D/V  |
| 4.5.2 | Sahkan bahawa persekitaran sandbox tidak mempunyai sambungan rangkaian (--network=none) atau hanya akses localhost dengan semua permintaan luaran disekat oleh peraturan iptables.                              |   1   | D/V  |
| 4.5.3 | Sahkan bahawa pengesahan model AI termasuk ujian red-team automatik dengan liputan ujian yang ditakrifkan oleh organisasi dan analisis tingkah laku untuk pengesanan pintu belakang.                            |   2   | D/V  |
| 4.5.4 | Sahkan bahawa sebelum model AI dipromosikan ke produksi, hasil sandboxnya ditandatangani secara kriptografi oleh kakitangan keselamatan yang diberi kuasa dan disimpan dalam log audit yang tidak boleh diubah. |   2   | D/V  |
| 4.5.5 | Sahkan bahawa persekitaran sandbox dimusnahkan dan dicipta semula daripada imej emas antara penilaian dengan pembersihan lengkap sistem fail dan memori.                                                        |   2   | D/V  |

---

## C4.6 Pemantauan Keselamatan Infrastruktur

Imbas dan pantau infrastruktur secara berterusan dengan pembaikan automatik dan amaran masa nyata.

|   #   | Description                                                                                                                                                                                           | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.6.1 | Sahkan bahawa imej kontena diimbas mengikut jadual organisasi dengan kerentanan KRITIKAL menghalang penyebaran berdasarkan ambang risiko organisasi.                                                  |   1   | D/V  |
| 4.6.2 | Sahkan bahawa infrastruktur mematuhi Penanda Aras CIS atau kawalan NIST 800-53 dengan ambang pematuhan yang ditakrifkan oleh organisasi dan pemulihan automatik bagi pemeriksaan yang gagal.          |   1   | D/V  |
| 4.6.3 | Sahkan bahawa kelemahan dengan tahap KESEMAKANAN TINGGI dipasang tampalan mengikut garis masa pengurusan risiko organisasi dengan prosedur kecemasan bagi CVE yang sedang dieksploitasi secara aktif. |   2   | D/V  |
| 4.6.4 | Sahkan bahawa amaran keselamatan disepadukan dengan platform SIEM (Splunk, Elastic, atau Sentinel) menggunakan format CEF atau STIX/TAXII dengan pemerkayaan automatik.                               |   2   |  V   |
| 4.6.5 | Sahkan bahawa metrik infrastruktur dieksport ke sistem pemantauan (Prometheus, DataDog) dengan papan pemuka SLA dan laporan eksekutif.                                                                |   3   |  V   |
| 4.6.6 | Sahkan bahawa perbezaan konfigurasi dikesan menggunakan alat (Chef InSpec, AWS Config) mengikut keperluan pemantauan organisasi dengan pengembalian otomatis untuk perubahan yang tidak dibenarkan.   |   2   | D/V  |

---

## C4.7 Pengurusan Sumber Infrastruktur AI

Cegah serangan keletihan sumber dan pastikan pengagihan sumber yang adil melalui kuota dan pemantauan.

|   #   | Description                                                                                                                                                                                                       | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.7.1 | Sahkan bahawa penggunaan GPU/TPU dipantau dengan amaran dicetuskan pada ambang yang ditetapkan oleh organisasi dan penskalaan automatik atau pengimbangan beban diaktifkan berdasarkan dasar pengurusan kapasiti. |   1   | D/V  |
| 4.7.2 | Sahkan bahawa metrik beban kerja AI (latensi inferens, kelajuan pemprosesan, kadar ralat) dikumpul mengikut keperluan pemantauan organisasi dan dikaitkan dengan penggunaan infrastruktur.                        |   1   | D/V  |
| 4.7.3 | Sahkan bahawa Kubernetes ResourceQuotas atau setara membatasi beban kerja individu mengikut polisi peruntukan sumber organisasi dengan had keras yang dikuatkuasakan.                                             |   2   | D/V  |
| 4.7.4 | Sahkan bahawa pemantauan kos mengesan perbelanjaan mengikut beban kerja/penyewa dengan amaran berdasarkan had bajet organisasi dan kawalan automatik untuk melebihi bajet.                                        |   2   |  V   |
| 4.7.5 | Sahkan bahawa perancangan kapasiti menggunakan data sejarah dengan tempoh unjuran yang ditakrifkan oleh organisasi dan penyediaan sumber automatik berdasarkan corak permintaan.                                  |   3   |  V   |
| 4.7.6 | Sahkan bahawa kehabisan sumber mencetuskan pemutus litar mengikut keperluan tindak balas organisasi, termasuk had kadar berdasarkan polisi kapasiti dan pengasingan beban kerja.                                  |   2   | D/V  |

---

## C4.8 Kawalan Pemisahan Persekitaran & Promosi

Melaksanakan sempadan persekitaran yang ketat dengan pintu promosi automatik dan pengesahan keselamatan.

|   #   | Description                                                                                                                                                                                                     | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.8.1 | Sahkan bahawa persekitaran dev/test/prod dijalankan dalam VPC/VNet yang berasingan tanpa peranan IAM, kumpulan keselamatan, atau sambungan rangkaian yang dikongsi.                                             |   1   | D/V  |
| 4.8.2 | Sahkan bahawa promosi persekitaran memerlukan kelulusan daripada kakitangan yang diberi kuasa seperti yang ditakrifkan oleh organisasi dengan tandatangan kriptografi dan rekod audit yang tidak boleh diubah.  |   1   | D/V  |
| 4.8.3 | Sahkan bahawa persekitaran pengeluaran menyekat akses SSH, mematikan titik hujung debug, dan memerlukan permintaan perubahan dengan keperluan notis awal organisasi kecuali dalam kecemasan.                    |   2   | D/V  |
| 4.8.4 | Sahkan bahawa perubahan infrastruktur-sebagai-kod memerlukan semakan rakan sebaya dengan ujian automatik dan pengimbasan keselamatan sebelum digabungkan ke cawangan utama.                                     |   2   | D/V  |
| 4.8.5 | Sahkan bahawa data bukan produksi dianonimkan mengikut keperluan privasi organisasi, penjanaan data sintetik, atau pemaskeran data sepenuhnya dengan pengesahan penghapusan Maklumat Pengenalan Peribadi (PII). |   2   | D/V  |
| 4.8.6 | Sahkan bahawa pintu promosi termasuk ujian keselamatan automatik (SAST, DAST, imbasan kontena) dengan tiada penemuan KRITIKAL diperlukan untuk kelulusan.                                                       |   2   | D/V  |

---

## C4.9 Sandaran & Pemulihan Infrastruktur

Pastikan ketahanan infrastruktur melalui sandaran automatik, prosedur pemulihan yang diuji, dan keupayaan pemulihan bencana.

|   #   | Description                                                                                                                                                                 | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.9.1 | Sahkan bahawa konfigurasi infrastruktur disandarkan mengikut jadual sandaran organisasi ke wilayah yang berbeza secara geografi dengan pelaksanaan strategi sandaran 3-2-1. |   1   | D/V  |
| 4.9.2 | Sahkan bahawa sistem sandaran dijalankan dalam rangkaian terpencil dengan kelayakan berasingan dan storan dipisahkan secara fizikal untuk perlindungan terhadap ransomware. |   2   | D/V  |
| 4.9.3 | Sahkan bahawa prosedur pemulihan diuji dan disahkan melalui ujian automatik mengikut jadual organisasi dengan sasaran RTO dan RPO yang memenuhi keperluan organisasi.       |   2   |  V   |
| 4.9.4 | Sahkan bahawa pemulihan bencana merangkumi buku panduan khusus AI dengan pemulihan berat model, pembinaan semula kluster GPU, dan pemetaan kebergantungan perkhidmatan.     |   3   |  V   |

---

## C4.10 Pematuhan Infrastruktur & Tadbir Urus

Menjaga pematuhan peraturan melalui penilaian berterusan, dokumentasi, dan kawalan automatik.

|   #    | Description                                                                                                                                                                   | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.10.1 | Sahkan bahawa pematuhan infrastruktur dinilai mengikut jadual organisasi berdasarkan kawalan SOC 2, ISO 27001, atau FedRAMP dengan pengumpulan bukti automatik.               |   2   | D/V  |
| 4.10.2 | Sahkan bahawa dokumentasi infrastruktur merangkumi rajah rangkaian, peta aliran data, dan model ancaman yang dikemas kini mengikut keperluan pengurusan perubahan organisasi. |   2   |  V   |
| 4.10.3 | Sahkan bahawa perubahan infrastruktur menjalani penilaian impak pematuhan automatik dengan aliran kerja kelulusan peraturan untuk pengubahsuaian berisiko tinggi.             |   3   | D/V  |

---

## C4.11 Keselamatan Perkakasan AI

Komponen perkakasan khusus AI yang selamat termasuk GPU, TPU, dan pemecut AI khusus.

|   #    | Description                                                                                                                                                                  | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.11.1 | Sahkan bahawa firmware pemecut AI (GPU BIOS, firmware TPU) disahkan menggunakan tandatangan kriptografi dan dikemas kini mengikut garis masa pengurusan tampalan organisasi. |   2   | D/V  |
| 4.11.2 | Sahkan bahawa sebelum pelaksanaan beban kerja, integriti pemecut AI disahkan melalui penegasan perkakasan menggunakan TPM 2.0, Intel TXT, atau AMD SVM.                      |   2   | D/V  |
| 4.11.3 | Sahkan bahawa memori GPU diasingkan antara beban kerja menggunakan SR-IOV, MIG (Multi-Instance GPU), atau pemisahan perkakasan setara dengan sanitasi memori antara tugasan. |   2   | D/V  |
| 4.11.4 | Sahkan bahawa rantaian bekalan perkakasan AI merangkumi pengesahan asal usul dengan sijil pengeluar dan pengesahan pembungkusan yang menunjukkan tanda-tanda gangguan.       |   3   |  V   |
| 4.11.5 | Sahkan bahawa modul keselamatan perkakasan (HSM) melindungi berat model AI dan kunci kriptografi dengan pensijilan FIPS 140-2 Tahap 3 atau Common Criteria EAL4+.            |   3   | D/V  |

---

## C4.12 Infrastruktur AI Tepi & Teragih

Penggubalan AI teragih yang selamat termasuk pengkomputeran tepi, pembelajaran berfederasi, dan seni bina berbilang tapak.

|   #    | Description                                                                                                                                                               | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.12.1 | Sahkan bahawa peranti edge AI mengesahkan kepada infrastruktur pusat menggunakan mutual TLS dengan sijil peranti yang diputar mengikut dasar pengurusan sijil organisasi. |   2   | D/V  |
| 4.12.2 | Sahkan bahawa peranti tepi melaksanakan boot selamat dengan tandatangan yang disahkan dan perlindungan rollback yang menghalang serangan penurunan versi firmware.        |   2   | D/V  |
| 4.12.3 | Sahkan bahawa koordinasi AI teragih menggunakan algoritma konsensus tahan ralat Byzantine dengan pengesahan peserta dan pengesanan nod berniat jahat.                     |   3   | D/V  |
| 4.12.4 | Sahkan bahawa komunikasi tepi-ke-awan merangkumi sekatan jalur lebar, pemampatan data, dan keupayaan operasi luar talian dengan storan tempatan yang selamat.             |   3   | D/V  |

---

## C4.13 Keselamatan Infrastruktur Multi-Awan & Hibrid

Amankan beban kerja AI merentasi pelbagai penyedia awan dan penyebaran awan hibrid-dalam premis.

|   #    | Description                                                                                                                                                                                       | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.13.1 | Sahkan bahawa penyebaran AI berbilang awan menggunakan federasi identiti tanpa mengira awan (OIDC, SAML) dengan pengurusan dasar berpusat merentasi penyedia.                                     |   2   | D/V  |
| 4.13.2 | Sahkan bahawa pemindahan data merentasi awan menggunakan penyulitan hujung-ke-hujung dengan kunci yang diurus oleh pelanggan dan kawalan kediaman data yang dikuatkuasakan mengikut bidang kuasa. |   2   | D/V  |
| 4.13.3 | Sahkan bahawa beban kerja AI awan hibrid melaksanakan polisi keselamatan yang konsisten merentasi persekitaran on-premise dan awan dengan pemantauan dan amaran yang bersepadu.                   |   2   | D/V  |
| 4.13.4 | Sahkan bahawa pencegahan penguncian vendor awan merangkumi infrastruktur sebagai kod yang boleh dipindahkan, API standard, dan keupayaan eksport data dengan alat penukaran format.               |   3   |  V   |
| 4.13.5 | Sahkan bahawa pengoptimuman kos pelbagai awan merangkumi kawalan keselamatan yang menghalang penyebaran sumber serta caj pemindahan data rentas awan yang tidak dibenarkan.                       |   3   |  V   |

---

## C4.14 Automasi Infrastruktur & Keselamatan GitOps

Laluan automasi infrastruktur yang selamat dan aliran kerja GitOps untuk pengurusan infrastruktur AI.

|   #    | Description                                                                                                                                                                                                     | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.14.1 | Sahkan bahawa repositori GitOps memerlukan komit yang ditandatangani dengan kunci GPG dan peraturan perlindungan cawangan yang menghalang tolak langsung ke cawangan utama.                                     |   2   | D/V  |
| 4.14.2 | Sahkan bahawa automasi infrastruktur merangkumi pengesanan drift dengan keupayaan pemulihan automatik dan rollback yang dicetuskan mengikut keperluan respons organisasi untuk perubahan yang tidak dibenarkan. |   2   | D/V  |
| 4.14.3 | Sahkan bahawa penyediaan infrastruktur automatik merangkumi pengesahan dasar keselamatan dengan penghalangan penyebaran untuk konfigurasi yang tidak mematuhi.                                                  |   2   | D/V  |
| 4.14.4 | Sahkan bahawa rahsia automasi infrastruktur diurus melalui operator rahsia luaran (External Secrets Operator, Bank-Vaults) dengan putaran automatik.                                                            |   2   | D/V  |
| 4.14.5 | Sahkan bahawa infrastruktur penyembuhan sendiri merangkumi korelasi acara keselamatan dengan tindak balas insiden automatik dan aliran kerja pemberitahuan pihak berkepentingan.                                |   3   |  V   |

---

## C4.15 Keselamatan Infrastruktur Tahan Kuantum

Sediakan infrastruktur AI untuk ancaman pengkomputeran kuantum melalui kriptografi pasca-kuantum dan protokol selamat-kuantum.

|   #    | Description                                                                                                                                                                                              | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.15.1 | Sahkan bahawa infrastruktur AI melaksanakan algoritma kriptografi pasca-kuantum yang diluluskan oleh NIST (CRYSTALS-Kyber, CRYSTALS-Dilithium, SPHINCS+) untuk pertukaran kunci dan tandatangan digital. |   3   | D/V  |
| 4.15.2 | Sahkan bahawa sistem pengedaran kunci kuantum (QKD) dilaksanakan untuk komunikasi AI berkeselamatan tinggi dengan protokol pengurusan kunci yang selamat kuantum.                                        |   3   | D/V  |
| 4.15.3 | Sahkan bahawa rangka kerja kecergasan kriptografi membolehkan migrasi pantas ke algoritma pasca-kuantum baru dengan putaran sijil dan kunci automatik.                                                   |   3   | D/V  |
| 4.15.4 | Sahkan bahawa pemodelan ancaman kuantum menilai kerentanan infrastruktur AI terhadap serangan kuantum dengan garis masa migrasi yang didokumentasikan dan penilaian risiko.                              |   3   |  V   |
| 4.15.5 | Sahkan bahawa sistem kriptografi hibrid klasik-kuantum menyediakan pertahanan berlapis semasa tempoh peralihan kuantum dengan pemantauan prestasi.                                                       |   3   | D/V  |

---

## C4.16 Pengkomputeran Sulit & Enklaf Selamat

Melindungi beban kerja AI dan berat model menggunakan persekitaran pelaksanaan dipercayai berasaskan perkakasan dan teknologi pengkomputeran rahsia.

|   #    | Description                                                                                                                                                                 | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.16.1 | Sahkan bahawa model AI sensitif dijalankan dalam enclave Intel SGX, AMD SEV-SNP, atau ARM TrustZone dengan memori yang disulitkan dan pengesahan atestasi.                  |   3   | D/V  |
| 4.16.2 | Sahkan bahawa kontena rahsia (Kata Containers, gVisor dengan pengkomputeran rahsia) memisahkan beban kerja AI dengan penyulitan memori yang dikuatkuasakan oleh perkakasan. |   3   | D/V  |
| 4.16.3 | Sahkan bahawa atestasi jauh mengesahkan integriti enclave sebelum memuatkan model AI dengan bukti kriptografi keaslian persekitaran pelaksanaan.                            |   3   | D/V  |
| 4.16.4 | Sahkan bahawa perkhidmatan inferens AI sulit menghalang pengeksportan model melalui pengiraan terenkripsi dengan berat model yang disegel dan pelaksanaan yang dilindungi.  |   3   | D/V  |
| 4.16.5 | Sahkan bahawa pengorkesan persekitaran pelaksanaan terjamin menguruskan kitar hayat enclave selamat dengan pensijilan jauh dan saluran komunikasi yang disulitkan.          |   3   | D/V  |
| 4.16.6 | Sahkan bahawa pengiraan pelbagai pihak yang selamat (SMPC) membolehkan latihan AI secara kolaboratif tanpa mendedahkan set data individu atau parameter model.              |   3   | D/V  |

---

## C4.17 Infrastruktur Pengetahuan-Nol

Laksanakan sistem bukti tanpa pengetahuan untuk pengesahan dan pengesahan AI yang menjaga privasi tanpa mendedahkan maklumat sensitif.

|   #    | Description                                                                                                                                                             | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.17.1 | Sahkan bahawa bukti tanpa pengetahuan (ZK-SNARKs, ZK-STARKs) mengesahkan integriti model AI dan asal usul latihan tanpa mendedahkan berat model atau data latihan.      |   3   | D/V  |
| 4.17.2 | Sahkan bahawa sistem pengesahan berasaskan ZK membolehkan pengesahan pengguna yang menjaga privasi untuk perkhidmatan AI tanpa mendedahkan maklumat berkaitan identiti. |   3   | D/V  |
| 4.17.3 | Sahkan bahawa protokol persilangan set persendirian (PSI) membolehkan pemadanan data yang selamat untuk AI persekutuan tanpa mendedahkan set data individu.             |   3   | D/V  |
| 4.17.4 | Sahkan bahawa sistem pembelajaran mesin pengetahuan sifar (ZKML) membolehkan inferens AI yang boleh disahkan dengan bukti kriptografi pengiraan yang betul.             |   3   | D/V  |
| 4.17.5 | Sahkan bahawa ZK-rollups menyediakan pemprosesan transaksi AI yang boleh diskalakan dan mengekalkan privasi dengan pengesahan pukal serta pengurangan beban pengiraan.  |   3   | D/V  |

---

## C4.18 Pencegahan Serangan Saluran Sisi

Melindungi infrastruktur AI daripada serangan saluran sisi berasaskan masa, kuasa, elektromagnetik, dan cache yang boleh mendedahkan maklumat sensitif.

|   #    | Description                                                                                                                                                  | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 4.18.1 | Sahkan bahawa masa inferens AI dinormalisasikan menggunakan algoritma masa tetap dan padding untuk mengelakkan serangan ekstraksi model berdasarkan masa.    |   3   | D/V  |
| 4.18.2 | Sahkan bahawa perlindungan analisis kuasa merangkumi suntikan gangguan, penapisan garis kuasa, dan corak pelaksanaan rawak untuk perkakasan AI.              |   3   | D/V  |
| 4.18.3 | Sahkan bahawa mitigasi saluran sisi berasaskan cache menggunakan pembahagian cache, pengacakan, dan arahan flush untuk mengelakkan kebocoran maklumat.       |   3   | D/V  |
| 4.18.4 | Sahkan bahawa perlindungan pelepasan elektromagnetik merangkumi penebatan, penapisan isyarat, dan pemprosesan rawak untuk mengelakkan serangan gaya TEMPEST. |   3   | D/V  |
| 4.18.5 | Sahkan bahawa pertahanan saluran sisi mikroarkitektur termasuk kawalan pelaksanaan spekulatif dan penyamaran corak akses memori.                             |   3   | D/V  |

---

## C4.19 Keselamatan Perkakasan AI Neuromorfik & Khusus

Amankan seni bina perkakasan AI baru termasuk cip neuromorfik, FPGA, ASIC tersuai, dan sistem pengkomputeran optik.

|   #    | Description                                                                                                                                                                    | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 4.19.1 | Sahkan bahawa keselamatan cip neuromorfik termasuk penyulitan corak denyutan, perlindungan berat sinaps, dan pengesahan peraturan pembelajaran berasaskan perkakasan.          |   3   | D/V  |
| 4.19.2 | Sahkan bahawa pemecut AI berasaskan FPGA melaksanakan penyulitan bitstream, mekanisme anti-tamper, dan pemuatan konfigurasi yang selamat dengan kemas kini yang diautentikasi. |   3   | D/V  |
| 4.19.3 | Sahkan bahawa keselamatan ASIC khusus merangkumi pemproses keselamatan pada cip, akar kepercayaan perkakasan, dan penyimpanan kunci selamat dengan pengesanan gangguan.        |   3   | D/V  |
| 4.19.4 | Sahkan bahawa sistem pengkomputeran optik melaksanakan penyulitan optik tahan kuantum, suis fotonik yang selamat, dan pemprosesan isyarat optik yang dilindungi.               |   3   | D/V  |
| 4.19.5 | Sahkan bahawa cip AI hibrid analog-digital merangkumi pengiraan analog yang selamat, penyimpanan berat yang dilindungi, dan penukaran analog-ke-digital yang diautentikasi.    |   3   | D/V  |

---

## C4.20 Infrastruktur Pengkomputeran Menjaga Privasi

Melaksanakan kawalan infrastruktur untuk pengiraan pemeliharaan privasi bagi melindungi data sensitif semasa pemprosesan dan analisis AI.

|   #    | Description                                                                                                                                                                                          | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.20.1 | Sahkan bahawa infrastruktur penyulitan homomorfik membolehkan pengiraan tersembunyi pada beban kerja AI yang sensitif dengan pengesahan integriti kriptografi dan pemantauan prestasi.               |   3   | D/V  |
| 4.20.2 | Sahkan bahawa sistem pengambilan maklumat peribadi membolehkan pertanyaan pangkalan data tanpa mendedahkan corak pertanyaan dengan perlindungan kriptografi terhadap corak capaian.                  |   3   | D/V  |
| 4.20.3 | Sahkan bahawa protokol pengiraan multi-pihak selamat membolehkan inferens AI yang menjaga privasi tanpa mendedahkan input individu atau pengiraan pertengahan.                                       |   3   | D/V  |
| 4.20.4 | Sahkan bahawa pengurusan kunci yang memelihara privasi termasuk penjanaan kunci teragih, kriptografi ambang, dan putaran kunci selamat dengan perlindungan berasaskan perkakasan.                    |   3   | D/V  |
| 4.20.5 | Sahkan bahawa prestasi pengiraan yang memelihara privasi dioptimumkan melalui pengumpulan berkumpulan, pengecaman semula, dan pecutan perkakasan sambil mengekalkan jaminan keselamatan kriptografi. |   3   | D/V  |

---

## C4.15 Keselamatan Integrasi Awan Rangka Kerja Ejen & Pengedaran Hibrid

Kawalan keselamatan untuk rangka kerja ejen bersepadu awan dengan seni bina hibrid on-premises/awan.

|   #    | Description                                                                                                                      | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.15.1 | Sahkan bahawa integrasi penyimpanan awan menggunakan penyulitan hujung-ke-hujung dengan pengurusan kunci yang dikawal oleh ejen. |   1   | D/V  |
| 4.15.2 | Sahkan bahawa sempadan keselamatan pengembangan hibrid ditakrifkan dengan jelas dengan saluran komunikasi yang disulitkan.       |   2   | D/V  |
| 4.15.3 | Sahkan bahawa akses sumber awan termasuk pengesahan sifar-kepercayaan dengan pengesahan berterusan.                              |   2   | D/V  |
| 4.15.4 | Sahkan bahawa keperluan kediaman data dikuatkuasakan melalui pengesahan kriptografi bagi lokasi penyimpanan.                     |   3   | D/V  |
| 4.15.5 | Sahkan bahawa penilaian keselamatan penyedia awan merangkumi pemodelan ancaman khusus agen dan penilaian risiko.                 |   3   | D/V  |

---

## Rujukan

* [NIST Cybersecurity Framework 2.0](https://www.nist.gov/cyberframework)
* [CIS Controls v8](https://www.cisecurity.org/controls/v8)
* [OWASP Container Security Verification Standard](https://github.com/OWASP/Container-Security-Verification-Standard)
* [Kubernetes Security Best Practices](https://kubernetes.io/docs/concepts/security/)
* [SLSA Supply Chain Security Framework](https://slsa.dev/)
* [NIST SP 800-190: Application Container Security Guide](https://csrc.nist.gov/publications/detail/sp/800-190/final)
* [Cloud Security Alliance: Cloud Controls Matrix](https://cloudsecurityalliance.org/research/cloud-controls-matrix/)
* [ENISA: Secure Infrastructure Design](https://www.enisa.europa.eu/topics/critical-information-infrastructures-and-services)
* [NIST SP 800-53: Security Controls for Federal Information Systems](https://csrc.nist.gov/publications/detail/sp/800-53/rev-5/final)
* [ISO 27001:2022 Information Security Management](https://www.iso.org/standard/27001)
* [NIST AI Risk Management Framework](https://www.nist.gov/itl/ai-risk-management-framework)
* [CIS Kubernetes Benchmark](https://www.cisecurity.org/benchmark/kubernetes)
* [FIPS 140-2 Security Requirements](https://csrc.nist.gov/publications/detail/fips/140/2/final)
* [NIST SP 800-207: Zero Trust Architecture](https://csrc.nist.gov/publications/detail/sp/800-207/final)
* [IEEE 2857: Privacy Engineering for AI Systems](https://standards.ieee.org/ieee/2857/7273/)
* [NIST SP 800-161: Cybersecurity Supply Chain Risk Management](https://csrc.nist.gov/publications/detail/sp/800-161/rev-1/final)
* [NIST Post-Quantum Cryptography Standards](https://csrc.nist.gov/Projects/post-quantum-cryptography)
* [Intel SGX Developer Guide](https://www.intel.com/content/www/us/en/developer/tools/software-guard-extensions/overview.html)
* [AMD SEV-SNP White Paper](https://www.amd.com/system/files/TechDocs/SEV-SNP-strengthening-vm-isolation-with-integrity-protection-and-more.pdf)
* [ARM TrustZone Technology](https://developer.arm.com/ip-products/security-ip/trustzone)
* [ZK-SNARKs: A Gentle Introduction](https://blog.ethereum.org/2016/12/05/zksnarks-in-a-nutshell/)
* [NIST SP 800-57: Cryptographic Key Management](https://csrc.nist.gov/publications/detail/sp/800-57-part-1/rev-5/final)
* [Side-Channel Attack Countermeasures](https://link.springer.com/book/10.1007/978-3-319-75268-6)
* [Neuromorphic Computing Security Challenges](https://ieeexplore.ieee.org/document/9458103)
* [FPGA Security: Fundamentals, Evaluation, and Countermeasures](https://link.springer.com/book/10.1007/978-3-319-90385-9)
* [Microsoft SEAL: Homomorphic Encryption Library](https://github.com/Microsoft/SEAL)
* [HElib: Homomorphic Encryption Library](https://github.com/homenc/HElib)
* [PALISADE Lattice Cryptography Library](https://palisade-crypto.org/)
* [Differential Privacy: A Survey of Results](https://link.springer.com/chapter/10.1007/978-3-540-79228-4_1)
* [Secure Aggregation for Federated Learning](https://eprint.iacr.org/2017/281.pdf)
* [Private Information Retrieval: Concepts and Constructions](https://link.springer.com/book/10.1007/978-3-030-16234-8)

