# C6 Forsyningskjedesikkerhet for modeller, rammeverk og data

## Kontrollmål

Angrep på AI-forsyningskjeden utnytter tredjepartsmodeller, -rammeverk eller -datasett for å legge inn bakdører, skjevheter eller utnyttbar kode. Disse kontrollene gir ende-til-ende opprinnelse, sårbarhetsstyring og overvåking for å beskytte hele modellens livssyklus.

---

## C6.1 Forhåndstrent modellvurdering og opprinnelse

Vurder og autentiser tredjepartsmodellers opprinnelse, lisenser og skjulte atferd før finjustering eller distribusjon.

|   #   | Description                                                                                                                                      | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 6.1.1 | Bekreft at hvert tredjeparts modellartefakt inkluderer en signert opprinnelsespost som identifiserer kildearkivet og commit-hashen.              |   1   | D/V  |
| 6.1.2 | Bekreft at modeller skannes for ondsinnede lag eller trojanske utløsere ved hjelp av automatiserte verktøy før import.                           |   1   | D/V  |
| 6.1.3 | Verifiser at overføringslæring finjusteres for å bestå adversariell evaluering for å oppdage skjulte atferder.                                   |   2   |  D   |
| 6.1.4 | Bekreft at modell-lisenser, eksportkontrollmerker og dataopprinnelsesuttalelser er registrert i en ML-BOM-post.                                  |   2   |  V   |
| 6.1.5 | Sørg for at høyrisikomodeller (offentlig opplastede vekter, uverifiserte skapere) forblir isolert inntil menneskelig gjennomgang og godkjenning. |   3   | D/V  |

---

## C6.2 Rammeverk- og biblioteks-skanning

Kontinuerlig skanne ML-rammeverk og biblioteker for CVE-er og ondsinnet kode for å holde kjøretidsstakken sikker.

|   #   | Description                                                                                                                            | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 6.2.1 | Bekreft at CI-pipelines kjører avhengighetsskannere på AI-rammeverk og kritiske biblioteker.                                           |   1   | D/V  |
| 6.2.2 | Verifiser at kritiske sårbarheter (CVSS ≥ 7,0) blokkerer forfremmelse til produksjonsbilder.                                           |   1   | D/V  |
| 6.2.3 | Bekreft at statisk kodeanalyse kjøres på forkede eller innleide ML-biblioteker.                                                        |   2   |  D   |
| 6.2.4 | Bekreft at forslag til rammeverksoppgraderinger inkluderer en vurdering av sikkerhetspåvirkning med referanse til offentlige CVE-feed. |   2   |  V   |
| 6.2.5 | Verifiser at kjøretidssensorer varsler om uventede dynamiske bibliotekinnlastinger som avviker fra den signerte SBOM-en.               |   3   |  V   |

---

## C6.3 Avhengighetsfiksering og verifisering

Fest alle avhengigheter til uforanderlige digests og gjenskap bygg for å garantere identiske, manipulasjonssikre artefakter.

|   #   | Description                                                                                                                  | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 6.3.1 | Bekreft at alle pakkebehandlere håndhever versjonsfesting via låsefil.                                                       |   1   | D/V  |
| 6.3.2 | Bekreft at immutablesummer brukes i stedet for mutable tagger i containerreferanser.                                         |   1   | D/V  |
| 6.3.3 | Bekreft at kontroller for reproducerbare bygg sammenligner hasher på tvers av CI-kjøringer for å sikre identiske resultater. |   2   |  D   |
| 6.3.4 | Bekreft at byggeattester lagres i 18 måneder for revisjonssporbarhet.                                                        |   2   |  V   |
| 6.3.5 | Bekreft at utløpte avhengigheter utløser automatiserte PR-er for å oppdatere eller forgreine festede versjoner.              |   3   |  D   |

---

## C6.4 Håndheving av pålitelig kilde

Tillat bare nedlastinger av artefakter fra kryptografisk verifiserte, organisasjonsgodkjente kilder, og blokker alt annet.

|   #   | Description                                                                                                                     | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 6.4.1 | Bekreft at modellvekter, datasett og containere kun lastes ned fra godkjente domener eller interne registre.                    |   1   | D/V  |
| 6.4.2 | Bekreft at Sigstore/Cosign-signaturer validerer utgiveridentitet før artefakter lagres lokalt i hurtigbuffer.                   |   1   | D/V  |
| 6.4.3 | Bekreft at utgående proxyer blokkerer uautentiserte nedlastinger av artefakter for å håndheve policy for pålitelig kilde.       |   2   |  D   |
| 6.4.4 | Verifiser at tillatelseslister for depot gjennomgås kvartalsvis med dokumentasjon av forretningsbegrunnelse for hver oppføring. |   2   |  V   |
| 6.4.5 | Bekreft at brudd på retningslinjer utløser karantene av artefakter og tilbakestilling av avhengige pipeline-kjøringer.          |   3   |  V   |

---

## C6.5 Risikoanalyse for tredjepartsdatasett

Evaluer eksterne datasett for forgiftning, skjevhet og juridisk samsvar, og overvåk dem gjennom hele livssyklusen.

|   #   | Description                                                                                                                          | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 6.5.1 | Verifiser at eksterne datasett gjennomgår vurdering av risiko for forgiftning (f.eks. datafingeravtrykk, avvikssøk).                 |   1   | D/V  |
| 6.5.2 | Bekreft at skjevhetsmetrikker (demografisk paritet, lik mulighet) beregnes før godkjenning av datasettet.                            |   1   |  D   |
| 6.5.3 | Bekreft at opphavsrett og lisensbetingelser for datasett er dokumentert i ML-BOM-oppføringene.                                       |   2   |  V   |
| 6.5.4 | Bekreft at periodisk overvåking oppdager drift eller korrupsjon i hostede datasett.                                                  |   2   |  V   |
| 6.5.5 | Verifiser at ulovlig innhold (opphavsrett, personlig identifiserbar informasjon) fjernes gjennom automatisert rensing før opplæring. |   3   |  D   |

---

## C6.6 Overvåking av leverandørkjedeangrep

Oppdag trusler mot forsyningskjeden tidlig gjennom CVE-feeder, revisjonslogganalyse og rødt-lag simuleringer.

|   #   | Description                                                                                                                   | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 6.6.1 | Bekreft at CI/CD-revisjonslogger strømmes til SIEM-deteksjoner for unormale pakke-nedlastinger eller manipulerte byggtrinn.   |   1   |  V   |
| 6.6.2 | Bekreft at hendelsesrespons-spillebøker inkluderer tilbakestillingsprosedyrer for kompromitterte modeller eller biblioteker.  |   2   |  D   |
| 6.6.3 | Verifiser at trusselintelligens-berikelsesmerker ML-spesifikke indikatorer (f.eks. modell-forgiftende IoC-er) i varseltriage. |   3   |  V   |

---

## C6.7 ML‑BOM for Modellartefakter

Generer og signer detaljerte ML-spesifikke SBOM-er (ML-BOM-er) slik at nedstrømsbrukere kan verifisere komponentintegritet ved distribusjonstidspunktet.

|   #   | Description                                                                                                               | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 6.7.1 | Bekreft at hvert modellartifakt publiserer en ML-BOM som lister opp datasett, vekter, hyperparametere og lisenser.        |   1   | D/V  |
| 6.7.2 | Bekreft at ML-BOM-generering og Cosign-signering er automatisert i CI og kreves for sammenslåing.                         |   1   | D/V  |
| 6.7.3 | Bekreft at ML-BOM-fullstendighetskontroller feiler byggeprosessen hvis noen komponentmetadata (hash, lisens) mangler.     |   2   |  D   |
| 6.7.4 | Bekreft at nedstrømsbrukere kan spørre ML-BOM-er via API for å validere importerte modeller ved distribusjonstidspunktet. |   2   |  V   |
| 6.7.5 | Sjekk at ML-BOM-er er versjonsstyrt og diffet for å oppdage uautoriserte endringer.                                       |   3   |  V   |

---

## Referanser

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

