# C6 Forsyningskædesikkerhed for modeller, rammeværk og data

## Kontrolmål

AI forsyningskædeangreb udnytter tredjepartsmodeller, -rammer eller datasæt til at indlejre bagdøre, bias eller udnyttelig kode. Disse kontrolforanstaltninger giver end-to-end oprindelsesstyring, sårbarhedshåndtering og overvågning for at beskytte hele modellens livscyklus.

---

## C6.1 Forudtrænet Modellervurdering og Oprindelse

Vurder og autentificer oprindelse, licenser og skjulte adfærd hos tredjepartsmodeller, inden der foretages finjustering eller implementering.

|   #   | Description                                                                                                                                           | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 6.1.1 | Bekræft, at hver tredjeparts modelartefakt indeholder en signeret proveniensregistrering, der identificerer kildearkivet og commit-hashen.            |   1   | D/V  |
| 6.1.2 | Sørg for, at modeller bliver scannet for skadelige lag eller Trojan-udløsere ved hjælp af automatiserede værktøjer før import.                        |   1   | D/V  |
| 6.1.3 | Bekræft, at transfer-læring finjusterer og består en modstandsdygtighedstest for at opdage skjulte adfærd.                                            |   2   |  D   |
| 6.1.4 | Bekræft, at modelllicenser, eksportkontrolmærker og erklæringer om dataoprindelse er registreret i en ML-BOM-post.                                    |   2   |  V   |
| 6.1.5 | Bekræft, at højrisikomodeller (offentligt uploadede vægte, uverificerede skabere) forbliver i karantæne indtil menneskelig gennemgang og godkendelse. |   3   | D/V  |

---

## C6.2 Framework- og biblioteksscanning

Scan løbende ML-rammeværk og biblioteker for CVE'er og ondsindet kode for at holde runtime-stakken sikker.

|   #   | Description                                                                                                                    | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 6.2.1 | Bekræft, at CI-pipelines kører afhængighedsscannere på AI-rammeværk og kritiske biblioteker.                                   |   1   | D/V  |
| 6.2.2 | Bekræft, at kritiske sårbarheder (CVSS ≥ 7,0) blokerer for promovering til produktionsbilleder.                                |   1   | D/V  |
| 6.2.3 | Bekræft, at statisk kodeanalyse kører på forgrenede eller leverandørintegrerede ML-biblioteker.                                |   2   |  D   |
| 6.2.4 | Bekræft, at forslag til opgraderinger af framework inkluderer en sikkerhedsvurdering med reference til offentlige CVE-feeds.   |   2   |  V   |
| 6.2.5 | Bekræft, at runtime-sensorer alarmerer ved uventede indlæsninger af dynamiske biblioteker, der afviger fra den signerede SBOM. |   3   |  V   |

---

## C6.3 Fastlåsning og verifikation af afhængigheder

Fastgør alle afhængigheder til uforanderlige digests og genskab builds for at garantere identiske, manipulationsfri artefakter.

|   #   | Description                                                                                                                | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 6.3.1 | Bekræft, at alle pakkestyringsprogrammer håndhæver versionsfastlåsning via låsefiler.                                      |   1   | D/V  |
| 6.3.2 | Bekræft, at uforanderlige digests anvendes i stedet for foranderlige tags i containerreferencer.                           |   1   | D/V  |
| 6.3.3 | Bekræft, at reproducible-build-kontroller sammenligner hashes på tværs af CI-kørsler for at sikre identiske output.        |   2   |  D   |
| 6.3.4 | Bekræft, at build-attestationer opbevares i 18 måneder for revisionssporbarhed.                                            |   2   |  V   |
| 6.3.5 | Bekræft, at udløbne afhængigheder udløser automatiserede pull requests for at opdatere eller forgrene fastlåste versioner. |   3   |  D   |

---

## C6.4 Forvaltning af betroede kilder

Tillad kun download af artefakter fra kryptografisk verificerede, organisationsgodkendte kilder og bloker alt andet.

|   #   | Description                                                                                                                              | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 6.4.1 | Bekræft, at modelvægt, datasæt og containere kun downloades fra godkendte domæner eller interne registre.                                |   1   | D/V  |
| 6.4.2 | Bekræft, at Sigstore/Cosign-signaturer validerer udgiverens identitet, før artefakter caches lokalt.                                     |   1   | D/V  |
| 6.4.3 | Bekræft, at egress-proxyer blokerer uautoriserede download af artefakter for at håndhæve politikken for betroede kilder.                 |   2   |  D   |
| 6.4.4 | Bekræft, at tilladelseslister for repositories gennemgås kvartalsvist med dokumentation for forretningsmæssig begrundelse for hver post. |   2   |  V   |
| 6.4.5 | Bekræft, at politikovertrædelser udløser karantæne af artefakter og tilbagerulning af afhængige pipeline-kørsler.                        |   3   |  V   |

---

## C6.5 Tredjepartsdatasæt Risiko Vurdering

Evaluer eksterne datasæt for forgiftning, bias og juridisk overholdelse, og overvåg dem gennem hele deres livscyklus.

|   #   | Description                                                                                                                        | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 6.5.1 | Bekræft, at eksterne datasæt gennemgår en vurdering af risikoen for forgiftning (f.eks. datafingeraftryk, outlier-detektion).      |   1   | D/V  |
| 6.5.2 | Bekræft, at bias-metrikker (demografisk paritet, lige muligheder) beregnes før godkendelse af datasættet.                          |   1   |  D   |
| 6.5.3 | Bekræft, at oprindelse og licensvilkår for datasæt er registreret i ML-BOM-poster.                                                 |   2   |  V   |
| 6.5.4 | Bekræft, at periodisk overvågning opdager drift eller korruption i hostede datasæt.                                                |   2   |  V   |
| 6.5.5 | Sørg for, at ulovligt indhold (ophavsret, personligt identificerbare oplysninger) fjernes via automatisk filtrering inden træning. |   3   |  D   |

---

## C6.6 Overvågning af forsyningskædeangreb

Opdag trusler mod forsyningskæden tidligt gennem CVE-feeds, revisionsloganalyse og red-team-simuleringer.

|   #   | Description                                                                                                                           | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 6.6.1 | Bekræft, at CI/CD revisionslogfiler strømmer til SIEM-detektioner for unormale pakkeoverførsler eller manipulerede build-trin.        |   1   |  V   |
| 6.6.2 | Bekræft, at beredskabsplaner for hændelsesrespons indeholder tilbageførselsprocedurer for kompromitterede modeller eller biblioteker. |   2   |  D   |
| 6.6.3 | Bekræft, at trussels-intel berigelses-tags markerer ML-specifikke indikatorer (f.eks. model-forgiftnings IoC’er) i alarmtriage.       |   3   |  V   |

---

## C6.7 ML-BOM for Model Artefakter

Generer og underskriv detaljerede ML-specifikke SBOM'er (ML-BOM'er), så downstream-forbrugere kan verificere komponentintegritet ved udrulningstidspunktet.

|   #   | Description                                                                                                                             | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 6.7.1 | Bekræft, at hver modelartefakt udgiver en ML-BOM, der angiver datasæt, vægte, hyperparametre og licenser.                               |   1   | D/V  |
| 6.7.2 | Bekræft, at ML-BOM-generering og Cosign-signering er automatiseret i CI og påkrævet for sammensmeltning.                                |   1   | D/V  |
| 6.7.3 | Bekræft, at ML-BOM fuldstændighedskontroller afviser byggeriet, hvis nogen komponentmetadata (hash, licens) mangler.                    |   2   |  D   |
| 6.7.4 | Bekræft, at downstream-forbrugere kan forespørge ML-BOM'er via API for at validere importerede modeller ved implementeringstidspunktet. |   2   |  V   |
| 6.7.5 | Bekræft, at ML-BOM'er er versionskontrollerede og sammenlignede for at opdage uautoriserede ændringer.                                  |   3   |  V   |

---

## Referencer

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

