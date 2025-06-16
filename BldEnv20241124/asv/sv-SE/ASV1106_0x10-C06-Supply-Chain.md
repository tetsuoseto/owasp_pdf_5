# C6 Säkerhet i leveranskedjan för modeller, ramverk och data

## Styrningsmål

Angrepp på AI-försörjningskedjan utnyttjar tredjepartsmodeller, ramverk eller dataset för att infoga bakdörrar, bias eller utnyttjbar kod. Dessa kontrollåtgärder erbjuder end-to-end spårbarhet, hantering av sårbarheter och övervakning för att skydda hela modellens livscykel.

---

## C6.1 Granskning och härstamning av förtränade modeller

Utvärdera och autentisera tredjepartsmodellernas ursprung, licenser och dolda beteenden innan någon finjustering eller implementering.

|   #   | Description                                                                                                                                                      | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 6.1.1 | Verifiera att varje tredjepartsmodellobjekt innehåller en signerad ursprungsanteckning som identifierar källförvaret och commit-hashen.                          |   1   | D/V  |
| 6.1.2 | Verifiera att modeller skannas efter skadliga lager eller Trojanutlösare med automatiserade verktyg innan import.                                                |   1   | D/V  |
| 6.1.3 | Verifiera att finjustering med överföringsinlärning klarar adversarial utvärdering för att upptäcka dolda beteenden.                                             |   2   |  D   |
| 6.1.4 | Verifiera att modelllicenser, exportkontrolltaggar och uppgifter om dataursprung är registrerade i en ML-BOM-post.                                               |   2   |  V   |
| 6.1.5 | Verifiera att hög­risk­modeller (offentligt uppladdade vikter, overifierade skapare) förblir i karantän tills mänsklig granskning och godkännande är genomförda. |   3   | D/V  |

---

## C6.2 Ramverks- och biblioteksskanning

Skanna kontinuerligt ML-ramverk och bibliotek för CVE:er och skadlig kod för att hålla körstacken säker.

|   #   | Description                                                                                                                          | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 6.2.1 | Verifiera att CI-pipelines kör beroendegranskare på AI-ramverk och kritiska bibliotek.                                               |   1   | D/V  |
| 6.2.2 | Verifiera att kritiska sårbarheter (CVSS ≥ 7,0) blockerar befordran till produktionsbilder.                                          |   1   | D/V  |
| 6.2.3 | Verifiera att statisk kodanalys körs på forkade eller levererade ML-bibliotek.                                                       |   2   |  D   |
| 6.2.4 | Verifiera att förslag på ramverksuppgraderingar inkluderar en säkerhetspåverkansbedömning med hänvisning till offentliga CVE-flöden. |   2   |  V   |
| 6.2.5 | Verifiera att runtime-sensorer larmar vid oväntade dynamiska biblioteksladdningar som avviker från den signerade SBOM.               |   3   |  V   |

---

## C6.3 Hantering av beroenden genom fastlåsning och verifiering

Lås varje beroende till oföränderliga digestvärden och reproducera byggen för att garantera identiska, manipulationsfria artefakter.

|   #   | Description                                                                                                           | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 6.3.1 | Verifiera att alla pakethanterare upprätthåller versionsspärrning via låsfiler.                                       |   1   | D/V  |
| 6.3.2 | Verifiera att oföränderliga digest används istället för föränderliga taggar i containerreferenser.                    |   1   | D/V  |
| 6.3.3 | Verifiera att reproducible-build-kontroller jämför hashvärden över CI-körningar för att säkerställa identiska utdata. |   2   |  D   |
| 6.3.4 | Verifiera att byggintyg lagras i 18 månader för revisionsspårbarhet.                                                  |   2   |  V   |
| 6.3.5 | Verifiera att utgångna beroenden utlöser automatiska PR:er för att uppdatera eller förgrena fastställda versioner.    |   3   |  D   |

---

## C6.4 Tillämpning av betrodd källa

Tillåt endast nedladdning av artefakter från kryptografiskt verifierade, organisationsgodkända källor och blockera allt annat.

|   #   | Description                                                                                                                               | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 6.4.1 | Verifiera att modellvikter, datamängder och containrar endast laddas ner från godkända domäner eller interna register.                    |   1   | D/V  |
| 6.4.2 | Verifiera att Sigstore/Cosign-signaturer bekräftar utgivarens identitet innan artefakter cachas lokalt.                                   |   1   | D/V  |
| 6.4.3 | Verifiera att egress-proxies blockerar icke-auktoriserade nedladdningar av artefakter för att upprätthålla en policy för betrodda källor. |   2   |  D   |
| 6.4.4 | Verifiera att repository-vitlistor granskas varje kvartal med bevis på affärsmotivering för varje post.                                   |   2   |  V   |
| 6.4.5 | Verifiera att policyöverträdelser utlöser karantän av artefakter och återställning av beroende pipeline-körningar.                        |   3   |  V   |

---

## C6.5 Riskbedömning av dataset från tredje part

Utvärdera externa dataset för förgiftning, partiskhet och laglig efterlevnad, och övervaka dem under hela deras livscykel.

|   #   | Description                                                                                                                            | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 6.5.1 | Verifiera att externa dataset genomgår riskbedömning för förgiftning (t.ex. dataspårning, avvikelsedetektion).                         |   1   | D/V  |
| 6.5.2 | Verifiera att bias-mått (demografisk paritet, lika möjligheter) beräknas innan datamängden godkänns.                                   |   1   |  D   |
| 6.5.3 | Verifiera att ursprung och licensvillkor för datamängder är dokumenterade i ML-BOM-poster.                                             |   2   |  V   |
| 6.5.4 | Verifiera att periodisk övervakning upptäcker avvikelser eller korruption i hostade datamängder.                                       |   2   |  V   |
| 6.5.5 | Verifiera att otillåtet innehåll (upphovsrätt, personligt identifierbar information) tas bort via automatiserad rensning före träning. |   3   |  D   |

---

## C6.6 Övervakning av leverantörskedjeangrepp

Upptäck hot mot leveranskedjan tidigt genom CVE-flöden, analys av revisionsloggar och red team-simuleringar.

|   #   | Description                                                                                                                                     | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 6.6.1 | Verifiera att CI/CD-revisionsloggar strömmas till SIEM-detektioner för att identifiera onormala paketnedladdningar eller manipulerade byggsteg. |   1   |  V   |
| 6.6.2 | Verifiera att incidentresponsplaner inkluderar återställningsprocedurer för komprometterade modeller eller bibliotek.                           |   2   |  D   |
| 6.6.3 | Verifiera att threat-intel berikning taggar ML-specifika indikatorer (t.ex. model-förgiftning IoC:er) i larmhantering.                          |   3   |  V   |

---

## C6.7 ML-BOM för modellartefakter

Generera och signera detaljerade ML-specifika SBOM:er (ML-BOM:er) så att nedströms användare kan verifiera komponenternas integritet vid distribution.

|   #   | Description                                                                                                             | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 6.7.1 | Verifiera att varje modellartefakt publicerar en ML‑BOM som listar dataset, viktningar, hyperparametrar och licenser.   |   1   | D/V  |
| 6.7.2 | Verifiera att ML‑BOM-generering och Cosign-signering är automatiserade i CI och krävs för sammanslagning.               |   1   | D/V  |
| 6.7.3 | Verifiera att ML-BOM kompletthetskontroller misslyckas med bygget om någon komponentmetadata (hash, licens) saknas.     |   2   |  D   |
| 6.7.4 | Verifiera att nedströmsanvändare kan fråga ML-BOMs via API för att validera importerade modeller vid driftsättningstid. |   2   |  V   |
| 6.7.5 | Verifiera att ML-BOM:er är versionsstyrda och jämförda för att upptäcka obehöriga ändringar.                            |   3   |  V   |

---

## Referenser

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

