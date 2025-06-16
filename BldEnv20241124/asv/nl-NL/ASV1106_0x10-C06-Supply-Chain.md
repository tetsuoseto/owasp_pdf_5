# C6 Beveiliging van de toeleveringsketen voor modellen, frameworks en data

## Beheersdoelstelling

AI-aanvalsaanvallen op de toeleveringsketen maken misbruik van modellen, frameworks of datasets van derden om achterdeurtjes, vooroordelen of exploiteerbare code in te bouwen. Deze controles bieden end-to-end herkomst, kwetsbaarheidsbeheer en monitoring om de volledige levenscyclus van het model te beschermen.

---

## C6.1 Controleren en herkomst van voorgetrainde modellen

Beoordeel en verifieer de herkomst, licenties en verborgen gedragingen van modellen van derden voordat u deze fijn afstemt of inzet.

|   #   | Description                                                                                                                                                               | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 6.1.1 | Controleer of elk artefact van een model van een derde partij een ondertekend provenance-record bevat waarin de bronrepository en commit-hash worden geïdentificeerd.     |   1   | D/V  |
| 6.1.2 | Controleer of modellen worden gescand op kwaadaardige lagen of Trojaanse triggers met behulp van geautomatiseerde tools voordat ze worden geïmporteerd.                   |   1   | D/V  |
| 6.1.3 | Verifieer dat transferleren-fijnstemming een adversariale evaluatie doorstaat om verborgen gedragingen te detecteren.                                                     |   2   |  D   |
| 6.1.4 | Controleer of modellicenties, exportcontrolelabels en verklaringen over de herkomst van data worden geregistreerd in een ML-BOM-invoer.                                   |   2   |  V   |
| 6.1.5 | Verifieer dat hoogrisicomodellen (openbaar geüploade gewichten, niet-geverifieerde makers) in quarantaine blijven totdat ze zijn beoordeeld en goedgekeurd door een mens. |   3   | D/V  |

---

## C6.2 Framework- en bibliotheekscanning

Blijf ML-frameworks en bibliotheken voortdurend scannen op CVE's en kwaadaardige code om de runtime-stack veilig te houden.

|   #   | Description                                                                                                                                 | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 6.2.1 | Controleer of CI-pijplijnen afhankelijkheidsscanners uitvoeren op AI-frameworks en kritieke bibliotheken.                                   |   1   | D/V  |
| 6.2.2 | Verifieer dat kritieke kwetsbaarheden (CVSS ≥ 7.0) voorkomen dat promotie naar productie-afbeeldingen plaatsvindt.                          |   1   | D/V  |
| 6.2.3 | Controleer of statische code-analyse wordt uitgevoerd op geforkte of ingevoegde ML-bibliotheken.                                            |   2   |  D   |
| 6.2.4 | Controleer of voorstel voor framework-upgrades een beoordeling van de beveiligingsimpact bevat met verwijzing naar openbare CVE-feeds.      |   2   |  V   |
| 6.2.5 | Controleer of runtime-sensoren een waarschuwing geven bij onverwachte dynamische bibliotheekladingen die afwijken van de ondertekende SBOM. |   3   |  V   |

---

## C6.3 Afhankelijkheidsverankering en verificatie

Beperk elke afhankelijkheid tot onveranderlijke digests en reproduceer builds om identieke, niet-manipuleerbare artefacten te garanderen.

|   #   | Description                                                                                                                         | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 6.3.1 | Controleer of alle pakketbeheerders versievergrendeling afdwingen via lockfiles.                                                    |   1   | D/V  |
| 6.3.2 | Verifieer dat onveranderlijke digests worden gebruikt in plaats van veranderlijke tags in containerreferenties.                     |   1   | D/V  |
| 6.3.3 | Controleer of reproducible-buildcontroles hashes vergelijken over CI-uitvoeringen om identieke uitkomsten te waarborgen.            |   2   |  D   |
| 6.3.4 | Controleer of bouwverklaringen gedurende 18 maanden worden opgeslagen voor audittraceerbaarheid.                                    |   2   |  V   |
| 6.3.5 | Controleer of verlopen afhankelijkheden geautomatiseerde pull requests activeren om bijgewerkte of geforkte vaste versies te maken. |   3   |  D   |

---

## C6.4 Handhaving van Vertrouwde Bron

Sta alleen het downloaden van artefacten toe van cryptografisch geverifieerde, door de organisatie goedgekeurde bronnen en blokkeer alles wat daarvan afwijkt.

|   #   | Description                                                                                                                                           | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 6.4.1 | Controleer of modelgewichten, datasets en containers alleen worden gedownload van goedgekeurde domeinen of interne registers.                         |   1   | D/V  |
| 6.4.2 | Controleer of Sigstore/Cosign-handtekeningen de identiteit van de uitgever verifiëren voordat artefacten lokaal worden gecached.                      |   1   | D/V  |
| 6.4.3 | Controleer of uitgaande proxies niet-geauthenticeerde artifact-downloads blokkeren om het beleid voor vertrouwde bronnen af te dwingen.               |   2   |  D   |
| 6.4.4 | Verifieer dat de toegangscontrolelijsten van de repository elk kwartaal worden herzien met bewijs van zakelijke rechtvaardiging voor elke vermelding. |   2   |  V   |
| 6.4.5 | Controleer of beleidschendingen het in quarantaine plaatsen van artefacten en het terugdraaien van afhankelijke pijplijnuitvoeringen veroorzaken.     |   3   |  V   |

---

## C6.5 Risicobeoordeling van datasets van derden

Evalueer externe datasets op vergiftiging, vooringenomenheid en juridische naleving, en monitor ze gedurende hun gehele levenscyclus.

|   #   | Description                                                                                                                          | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 6.5.1 | Zorg ervoor dat externe datasets een risicoscore voor vergiftiging ondergaan (bijv. data fingerprinting, detectie van uitschieters). |   1   | D/V  |
| 6.5.2 | Controleer of bias-metrieken (demografische pariteit, gelijke kansen) worden berekend voordat de dataset wordt goedgekeurd.          |   1   |  D   |
| 6.5.3 | Controleer of herkomst en licentievoorwaarden voor datasets zijn vastgelegd in ML-BOM-vermeldingen.                                  |   2   |  V   |
| 6.5.4 | Verifieer of periodieke monitoring afwijkingen of corruptie in gehoste datasets detecteert.                                          |   2   |  V   |
| 6.5.5 | Verifieer dat ontoegestane inhoud (auteursrecht, PII) voorafgaand aan training automatisch wordt verwijderd via scrubbing.           |   3   |  D   |

---

## C6.6 Monitoring van Supply Chain-aanvallen

Detecteer supply‑chain bedreigingen vroegtijdig via CVE-feeds, auditloganalyse en red-team simulaties.

|   #   | Description                                                                                                                            | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 6.6.1 | Verifieer dat CI/CD-auditlogs worden doorgestuurd naar SIEM-detecties voor afwijkende pakketdownloads of gemanipuleerde build-stappen. |   1   |  V   |
| 6.6.2 | Verifieer dat incidentrespons-scenario's rollbackprocedures bevatten voor gecompromitteerde modellen of bibliotheken.                  |   2   |  D   |
| 6.6.3 | Verifieer dat threat‑intel verrijking ML‑specifieke indicatoren (bijv. modelvergiftiging IoC's) tagt tijdens de alarmtriage.           |   3   |  V   |

---

## C6.7 ML-BOM voor Model Artefacten

Genereer en onderteken gedetailleerde ML-specifieke SBOM's (ML-BOM's) zodat downstream gebruikers de componentintegriteit kunnen verifiëren op het moment van deployment.

|   #   | Description                                                                                                                                  | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 6.7.1 | Verifieer dat elk modelartefact een ML-BOM publiceert die datasets, gewichten, hyperparameters en licenties vermeldt.                        |   1   | D/V  |
| 6.7.2 | Controleer of ML-BOM-generatie en Cosign-ondertekening geautomatiseerd zijn in CI en vereist zijn voor samenvoeging.                         |   1   | D/V  |
| 6.7.3 | Controleer of de completeness-controle van ML-BOM de build faalt als er metadata van een component (hash, licentie) ontbreekt.               |   2   |  D   |
| 6.7.4 | Verifieer dat downstream-gebruikers ML-BOM's via de API kunnen opvragen om geïmporteerde modellen tijdens de implementatiefase te valideren. |   2   |  V   |
| 6.7.5 | Controleer of ML-BOM's versiebeheer hebben en worden vergeleken om ongeautoriseerde wijzigingen te detecteren.                               |   3   |  V   |

---

## Referenties

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

