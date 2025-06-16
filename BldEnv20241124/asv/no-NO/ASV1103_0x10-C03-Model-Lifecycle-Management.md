# C3-modell livssyklusstyring og endringskontroll

## Kontrollmål

AI-systemer må implementere endringskontrollprosesser som forhindrer uautoriserte eller usikre modellendringer fra å nå produksjon. Denne kontrollen sikrer modellens integritet gjennom hele livssyklusen—fra utvikling gjennom utrulling til utfasing—som muliggjør rask hendelsesrespons og opprettholder ansvarlighet for alle endringer.

Kjernesikkerhetsmål: Kun autoriserte, validerte modeller når produksjon ved å bruke kontrollerte prosesser som opprettholder integritet, sporbarhet og gjenopprettbarhet.

---

## C3.1 Modellautorisasjon og integritet

Kun autoriserte modeller med verifisert integritet når produksjonsmiljøer.

|   #   | Description                                                                                                                                                                                                             | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 3.1.1 | Bekreft at alle modellartefakter (vekter, konfigurasjoner, tokenizere) er kryptografisk signert av autoriserte enheter før distribuering.                                                                               |   1   | D/V  |
| 3.1.2 | Sørg for at modellens integritet valideres ved distribusjonstidspunkt, og at signaturverifiseringsfeil forhindrer lasting av modellen.                                                                                  |   1   | D/V  |
| 3.1.3 | Verifiser at modellens opphavsregistreringer inkluderer en autoriserende enhets identitet, kontrollsummer for treningsdata, valideringstestresultater med godkjent/ikke godkjent status, og et opprettelsestidsstempel. |   2   | D/V  |
| 3.1.4 | Bekreft at alle modellartefakter bruker semantisk versjonering (MAJOR.MINOR.PATCH) med dokumenterte kriterier som spesifiserer når hver versjonskomponent øker.                                                         |   2   | D/V  |
| 3.1.5 | Bekreft at avhengighetssporing opprettholder et sanntidslager som muliggjør rask identifisering av alle systemer som bruker ressursene.                                                                                 |   2   |  V   |

---

## C3.2 Modellvalidering og testing

Modeller må bestå definerte sikkerhets- og trygghetsvalideringer før distribusjon.

|   #   | Description                                                                                                                                                                                                                       | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 3.2.1 | Sørg for at modeller gjennomgår automatisert sikkerhetstesting som inkluderer inndata validering, utdata sanitering, og sikkerhetsvurderinger med forhåndsavtalte organisatoriske bestått/ikke bestått terskler før distribusjon. |   1   | D/V  |
| 3.2.2 | Bekreft at valideringsfeil automatisk blokkerer modellimplementering etter eksplisitt overstyringsgodkjenning fra forhåndsbestemt autorisert personell med dokumenterte forretningsbegrunnelser.                                  |   1   | D/V  |
| 3.2.3 | Bekreft at testrapportene er kryptografisk signert og uforanderlig knyttet til den spesifikke modellversjonens hash som blir validert.                                                                                            |   2   |  V   |
| 3.2.4 | Bekreft at nødutplasseringer krever dokumentert sikkerhetsrisikovurdering og godkjenning fra en forhåndsbestemt sikkerhetsmyndighet innen forhåndsavtalte tidsrammer.                                                             |   2   | D/V  |

---

## C3.3 Kontrollert utrulling og tilbakeføring

Modellutrullinger må kontrolleres, overvåkes og kunne reverseres.

|   #   | Description                                                                                                                                                                                                                                             | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 3.3.1 | Verifiser at produksjonsutrullinger implementerer gradvise utrullingsmekanismer (kanarirutrullinger, blå-grønn utrulling) med automatiske tilbakeføringsutløsere basert på forhåndsavtalte feilrater, latensgrenser eller sikkerhetsvarslingskriterier. |   1   |  D   |
| 3.3.2 | Bekreft at tilbakestillingsmuligheter gjenoppretter den komplette modelltilstanden (vekter, konfigurasjoner, avhengigheter) atomisk innenfor forhåndsdefinerte organisasjonelle tidsvinduer.                                                            |   1   | D/V  |
| 3.3.3 | Bekreft at distribusjonsprosesser validerer kryptografiske signaturer og beregner integritetskontrollsummer før modellaktivering, og at distribusjonen feiler ved enhver avvik.                                                                         |   2   | D/V  |
| 3.3.4 | Bekreft at nødstoppfunksjoner for modellen kan deaktivere modellendepunkter innen forhåndsdefinerte responstider gjennom automatiske strømkretser eller manuelle avbrytere.                                                                             |   2   | D/V  |
| 3.3.5 | Bekreft at rollback-artifakter (tidligere modellversjoner, konfigurasjoner, avhengigheter) oppbevares i henhold til organisasjonens retningslinjer med uforanderlig lagring for hendelseshåndtering.                                                    |   2   |  V   |

---

## C3.4 Endringsansvar og revisjon

Alle endringer i modellens livssyklus må kunne spores og revideres.

|   #   | Description                                                                                                                                                                                                                                             | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 3.4.1 | Bekreft at alle modellendringer (utrulling, konfigurasjon, utfasing) genererer uforanderlige revisjonslogger som inkluderer tidsstempel, en autentisert aktøridentitet, en endringstype, samt før- og efter-tilstander.                                 |   1   |  V   |
| 3.4.2 | Bekreft at tilgang til revisjonsloggen krever riktig autorisasjon, og at alle tilgangsforsøk logges med brukeridentitet og tidsstempel.                                                                                                                 |   2   | D/V  |
| 3.4.3 | Sørg for at promptmaler og systemmeldinger er versjonskontrollert i git-repositorier med obligatorisk kodegjennomgang og godkjenning fra utpekte vurderere før distribusjon.                                                                            |   2   | D/V  |
| 3.4.4 | Bekreft at revisjonslogger inneholder tilstrekkelige detaljer (modell-hasher, konfigurasjonsøyeblikksbilder, avhengighetsversjoner) for å muliggjøre fullstendig rekonstruksjon av modelltilstand for enhver tidsstempel innenfor oppbevaringsperioden. |   2   |  V   |

---

## C3.5 Sikker utviklingspraksis

Modellutvikling og treningsprosesser må følge sikre metoder for å forhindre kompromittering.

|   #   | Description                                                                                                                                                                         | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 3.5.1 | Bekreft at modellutvikling, testing og produksjonsmiljøer er fysisk eller logisk adskilt. De skal ikke ha delt infrastruktur, ulike tilgangskontroller, og isolerte datalagre.      |   1   |  D   |
| 3.5.2 | Sørg for at modelltrening og finjustering skjer i isolerte miljøer med kontrollert nettverkstilgang.                                                                                |   1   |  D   |
| 3.5.3 | Bekreft at treningsdatas kilder blir validert gjennom integritetskontroller og autentisert via pålitelige kilder med dokumentert kjede av forvaring før bruk i modellutvikling.     |   1   | D/V  |
| 3.5.4 | Bekreft at modellutviklingsartefakter (hyperparametere, treningsskript, konfigurasjonsfiler) blir lagret i versjonskontroll og krever godkjenning fra kollegaer før bruk i trening. |   2   |  D   |

---

## C3.6 Modellavvikling og avvikling av systemer

Modeller må trygt avvikles når de ikke lenger er nødvendige eller når sikkerhetsproblemer blir identifisert.

|   #   | Description                                                                                                                                                                                                                     | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 3.6.1 | Sørg for at prosessene for nedleggelse av modeller automatisk skanner avhengighetsgrafer, identifiserer alle systemer som bruker modellen, og gir forhåndsavtalt varslingsperiode før utfasing.                                 |   1   |  D   |
| 3.6.2 | Bekreft at arkiverte modellartefakter blir sikkert slettet ved bruk av kryptografisk utsletting eller flerpassoverskriving i henhold til dokumenterte retningslinjer for datalagring, med verifiserte destruksjonssertifikater. |   1   | D/V  |
| 3.6.3 | Bekreft at hendelser for modellavvikling logges med tidsstempel og aktøridentitet, og at modellsignaturer tilbakekalles for å hindre gjenbruk.                                                                                  |   2   |  V   |
| 3.6.4 | Bekreft at nødmodellpensjonering kan deaktivere modelltilgang innen forhåndsbestemte tidsrammer for nødsituasjoner gjennom automatiske avstengningsmekanismer hvis kritiske sikkerhetssårbarheter oppdages.                     |   2   | D/V  |

---

## Referanser

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

