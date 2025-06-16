# C3 Model livscyklusstyring og ændringskontrol

## Kontrolmål

AI-systemer skal implementere ændringskontrolprocesser, der forhindrer uautoriserede eller usikre modelændringer i at nå produktion. Denne kontrol sikrer modelintegritet gennem hele livscyklussen – fra udvikling over implementering til udfasning – hvilket muliggør hurtig hændelsesreaktion og opretholder ansvarlighed for alle ændringer.

Kerntilladelsesmål: Kun autoriserede, validerede modeller når produktion ved at anvende kontrollerede processer, der opretholder integritet, sporbarhed og genoprettelighed.

---

## C3.1 Modelautorisation og integritet

Kun autoriserede modeller med verificeret integritet når produktionsmiljøer.

|   #   | Description                                                                                                                                                                                                 | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 3.1.1 | Bekræft, at alle modelartefakter (vægte, konfigurationer, tokenizer) er kryptografisk signeret af autoriserede enheder før implementering.                                                                  |   1   | D/V  |
| 3.1.2 | Bekræft, at modelintegritet valideres ved implementering, og at fejl i signaturverifikation forhindrer indlæsning af modellen.                                                                              |   1   | D/V  |
| 3.1.3 | Bekræft, at modelproveniensregistre inkluderer en autoriserende enheds identitet, kontrolsummer for træningsdata, valideringstestresultater med bestået/ikke bestået status samt et oprettelsestidsstempel. |   2   | D/V  |
| 3.1.4 | Bekræft, at alle modelartefakter bruger semantisk versionering (MAJOR.MINOR.PATCH) med dokumenterede kriterier, der angiver, hvornår hver versionskomponent øges.                                           |   2   | D/V  |
| 3.1.5 | Bekræft, at afhængighedssporing opretholder et realtidslager, som muliggør hurtig identifikation af alle forbrugende systemer.                                                                              |   2   |  V   |

---

## C3.2 Modelvalidering og testning

Modeller skal bestå definerede sikkerheds- og sikkerhedskontroller, før de implementeres.

|   #   | Description                                                                                                                                                                                                                       | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 3.2.1 | Bekræft, at modeller gennemgår automatiseret sikkerhedstest, som inkluderer inputvalidering, outputrensning og sikkerhedsvurderinger med forudbestemte organisatoriske godkendelses-/afvisningskriterier, inden de implementeres. |   1   | D/V  |
| 3.2.2 | Bekræft, at valideringsfejl automatisk blokerer for modeludrulning efter eksplicit godkendelse af forudbestemte autoriserede personer med dokumenterede forretningsmæssige begrundelser.                                          |   1   | D/V  |
| 3.2.3 | Bekræft, at testresultater er kryptografisk underskrevet og uforanderligt knyttet til den specifikke modelversions hash, der valideres.                                                                                           |   2   |  V   |
| 3.2.4 | Bekræft, at nødudrulninger kræver dokumenteret sikkerhedsrisikovurdering og godkendelse fra en forhåndsudpeget sikkerhedsmyndighed inden for forud aftalte tidsrammer.                                                            |   2   | D/V  |

---

## C3.3 Kontrolleret implementering og tilbagerulning

Modelimplementeringer skal kontrolleres, overvåges og kunne gendannes.

|   #   | Description                                                                                                                                                                                                                                                          | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 3.3.1 | Bekræft, at produktionsudrulninger implementerer gradvise udrulningsmekanismer (kanarieudrulninger, blue-green udrulninger) med automatiserede tilbagetrækningsudløsere baseret på forudbestemte fejlprocenter, latenstærskler eller sikkerhedsalarmeringskriterier. |   1   |  D   |
| 3.3.2 | Bekræft, at rollback-funktioner gendanner den komplette modeltilstand (vægtninger, konfigurationer, afhængigheder) atomisk inden for foruddefinerede organisatoriske tidsvinduer.                                                                                    |   1   | D/V  |
| 3.3.3 | Bekræft, at implementeringsprocesser validerer kryptografiske signaturer og beregner integritetskontrolsummer, inden modellen aktiveres, og at implementeringen fejler ved enhver uoverensstemmelse.                                                                 |   2   | D/V  |
| 3.3.4 | Bekræft, at nødstopfunktioner for modeller kan deaktivere modelendepunkter inden for foruddefinerede svartider via automatiserede afbrydere eller manuelle nødafbrydere.                                                                                             |   2   | D/V  |
| 3.3.5 | Bekræft, at rollback-artifakter (tidligere modelversioner, konfigurationer, afhængigheder) opbevares i henhold til organisatoriske politikker med uforanderlig lagring til hændelsesrespons.                                                                         |   2   |  V   |

---

## C3.4 Ansvarlighed for ændringer og revision

Alle ændringer i modellens livscyklus skal kunne spores og revideres.

|   #   | Description                                                                                                                                                                                                                                             | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 3.4.1 | Bekræft, at alle modelændringer (udrulning, konfiguration, tilbagetrækning) genererer uforanderlige revisionsposter, inklusive et tidsstempel, en autentificeret aktøridentitet, en ændringstype og før/efter tilstande.                                |   1   |  V   |
| 3.4.2 | Bekræft, at adgang til revisionslog kræver passende autorisation, og at alle adgangsforsøg logges med brugeridentitet og tidsstempel.                                                                                                                   |   2   | D/V  |
| 3.4.3 | Bekræft, at promptskabeloner og systemmeddelelser er versionsstyret i git-repositorier med obligatorisk kodegennemgang og godkendelse fra udpegede anmeldere før implementering.                                                                        |   2   | D/V  |
| 3.4.4 | Bekræft, at revisionsregistre indeholder tilstrækkelige detaljer (model-hash, konfigurationsøjebliksbilleder, afhængighedsversioner) til at muliggøre fuldstændig rekonstruktion af modeltilstand for enhver tidsstempel inden for opbevaringsperioden. |   2   |  V   |

---

## C3.5 Sikker udviklingspraksis

Modeludviklings- og træningsprocesser skal følge sikre praksisser for at forhindre kompromittering.

|   #   | Description                                                                                                                                                                             | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 3.5.1 | Bekræft, at modeludviklings-, test- og produktionsmiljøer er fysisk eller logisk adskilte. De har ingen fælles infrastruktur, særskilte adgangskontroller og isolerede datalagre.       |   1   |  D   |
| 3.5.2 | Bekræft, at modeltræning og finjustering foregår i isolerede miljøer med kontrolleret netværksadgang.                                                                                   |   1   |  D   |
| 3.5.3 | Bekræft, at træningsdatakilder valideres gennem integritetskontroller og autentificeres via betroede kilder med dokumenteret kæde af besiddelse, før de anvendes i modeludvikling.      |   1   | D/V  |
| 3.5.4 | Bekræft, at modeludviklingsartefakter (hyperparametre, træningsscripts, konfigurationsfiler) gemmes i versionskontrol og kræver godkendelse via peer review, før de anvendes i træning. |   2   |  D   |

---

## C3.6 Model udfasning og afvikling

Modeller skal sikkert trækkes tilbage, når de ikke længere er nødvendige, eller når sikkerhedsproblemer opdages.

|   #   | Description                                                                                                                                                                                                                | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 3.6.1 | Bekræft, at modelpensationsprocesser automatisk scanner afhængighedsgrafer, identificerer alle forbrugende systemer og giver forudgående varslingsperioder, der er aftalt på forhånd, inden udfasning.                     |   1   |  D   |
| 3.6.2 | Bekræft, at arkiverede modelartefakter er sikkert slettet ved hjælp af kryptografisk sletning eller flerpasses overskrivning i henhold til dokumenterede databevaringspolitikker med verificerede destrueringcertifikater. |   1   | D/V  |
| 3.6.3 | Bekræft, at modelens udfasning begivenheder logges med tidsstempel og aktørens identitet, og at model-signaturer tilbagekaldes for at forhindre genbrug.                                                                   |   2   |  V   |
| 3.6.4 | Bekræft, at nødmodelafvikling kan deaktivere adgang til modellen inden for forudbestemte nødsvarstidsrammer via automatiserede driftsafbrydere, hvis der opdages kritiske sikkerhedssårbarheder.                           |   2   | D/V  |

---

## Referencer

* [MLOps Principles](https://ml-ops.org/content/mlops-principles)
* [Securing AI/ML Ops – Cisco.com](https://sec.cloudapps.cisco.com/security/center/resources/SecuringAIMLOps)
* [Audit logs security: cryptographically signed tamper-proof logs](https://www.cossacklabs.com/blog/audit-logs-security/)
* [Machine Learning Model Versioning: Top Tools & Best Practices](https://lakefs.io/blog/model-versioning/)
* [AI Hygiene Starts with Models and Data Loaders – SEI Blog](https://insights.sei.cmu.edu/documents/6190/AI-Hygiene-Starts-with-Models-and-Data-Loaders_1G0KTRh.pdf)
* [How to handle versioning and rollback of a deployed ML model?](https://learn.microsoft.com/en-au/answers/questions/1845378/how-to-handle-versioning-and-rollback-of-a-deploye)
* [Reinforcement fine-tuning – OpenAI API](https://platform.openai.com/docs/guides/reinforcement-fine-tuning)
* [Auditing Machine Learning models: Governance, Data Security and …](https://www.linkedin.com/pulse/auditing-machine-learning-models-governance-data-security-negrete-yn81f)
* [Adversarial Training to Improve Model Robustness](https://medium.com/%40amit25173/adversarial-training-to-improve-model-robustness-5e285b516713)
* [What is AI adversarial robustness? – IBM Research](https://research.ibm.com/blog/securing-ai-workflows-with-adversarial-robustness)
* [Exploring Data Provenance: Ensuring Data Integrity and Authenticity](https://www.astera.com/type/blog/data-provenance/)
* [MITRE ATLAS](https://atlas.mitre.org/)
* [AWS Prescriptive Guidance – Best practices for retiring applications …](https://docs.aws.amazon.com/pdfs/prescriptive-guidance/latest/migration-app-retirement-best-practices/migration-app-retirement-best-practices.pdf)

