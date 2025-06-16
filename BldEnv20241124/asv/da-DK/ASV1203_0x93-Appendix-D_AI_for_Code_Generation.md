# Bilag D: AI-assisteret styring og verifikation af sikker kodning

## Mål

Dette kapitel definerer grundlæggende organisatoriske kontrolforanstaltninger for sikker og effektiv brug af AI-assisterede kodningsværktøjer under softwareudvikling og sikrer sikkerhed og sporbarhed på tværs af SDLC.

---

## AD.1 AI-assisteret sikker-kodningsarbejdsgang

Integrer AI-værktøjer i organisationens sikre softwareudviklingslivscyklus (SSDLC) uden at svække de eksisterende sikkerhedsværn.

|   #    | Description                                                                                                                                                                            | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| AD.1.1 | Bekræft, at en dokumenteret arbejdsgang beskriver, hvornår og hvordan AI-værktøjer kan generere, omstrukturere eller gennemgå kode.                                                    |   1   | D/V  |
| AD.1.2 | Bekræft, at arbejdsgangen svarer til hver SSDLC-fase (design, implementering, kodegennemgang, testning, implementering).                                                               |   2   |  D   |
| AD.1.3 | Bekræft, at metrikker (f.eks. sårbarhedstæthed, gennemsnitlig tid til at opdage) indsamles for AI-genereret kode og sammenlignes med baselineværdi for udelukkende menneskeskabt kode. |   3   | D/V  |

---

## AD.2 AI-værktøjskvalificering og trusselsmodellering

Sørg for, at AI-kodningsværktøjer evalueres for sikkerhedsfunktioner, risici og forsyningskædepåvirkning, før de tages i brug.

|   #    | Description                                                                                                                                                                          | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| AD.2.1 | Bekræft, at en trusselsmodel for hvert AI-værktøj identificerer misbrug, modelinversion, datalækage og afhængighedskæderisici.                                                       |   1   | D/V  |
| AD.2.2 | Bekræft, at værktøjsevalueringer inkluderer statisk/dynamisk analyse af eventuelle lokale komponenter samt vurdering af SaaS-endpoints (TLS, autentificering/autorisation, logning). |   2   |  D   |
| AD.2.3 | Bekræft, at evalueringer følger en anerkendt ramme og genudføres efter større versionsændringer.                                                                                     |   3   | D/V  |

---

## AD.3 Sikker Prompt- og Kontekststyring

Forhindre lækage af hemmeligheder, proprietær kode og personlige data ved opbygning af prompts eller kontekster til AI-modeller.

|   #    | Description                                                                                                                                                    | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| AD.3.1 | Bekræft, at skriftlige retningslinjer forbyder at sende hemmeligheder, legitimationsoplysninger eller klassificerede data i prompts.                           |   1   | D/V  |
| AD.3.2 | Bekræft, at tekniske kontroller (redigering på klientsiden, godkendte kontekstfiltre) automatisk fjerner følsomme elementer.                                   |   2   |  D   |
| AD.3.3 | Bekræft, at prompts og svar bliver tokeniseret, krypteret under overførsel og i hvile, samt at opbevaringsperioderne overholder dataklassificeringspolitikken. |   3   | D/V  |

---

## AD.4 Validering af AI-genereret kode

Opdag og udbedr sårbarheder introduceret af AI-output, før koden flettes eller implementeres.

|   #    | Description                                                                                                                                                            | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| AD.4.1 | Bekræft, at AI-genereret kode altid underkastes menneskelig kodegennemgang.                                                                                            |   1   | D/V  |
| AD.4.2 | Bekræft, at automatiserede scannere (SAST/IAST/DAST) kører på hver pull request, der indeholder AI-genereret kode, og blokerer for sammenfletninger ved kritiske fund. |   2   |  D   |
| AD.4.3 | Bekræft, at differential fuzz-testing eller egenskabsbaserede tests beviser sikkerhedskritiske adfærd (f.eks. inputvalidering, autorisationslogik).                    |   3   | D/V  |

---

## AD.5 Forklarbarhed og Sporbarhed af Kodeforslag

Giv revisorer og udviklere indsigt i, hvorfor et forslag blev fremsat, og hvordan det udviklede sig.

|   #    | Description                                                                                                                                                               | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| AD.5.1 | Bekræft, at prompt-/responspar logges med commit-id'er.                                                                                                                   |   1   | D/V  |
| AD.5.2 | Bekræft, at udviklere kan fremvise modelhenvisninger (træningsudsnit, dokumentation), der understøtter et forslag.                                                        |   2   |  D   |
| AD.5.3 | Bekræft, at forklarbarhedsrapporter opbevares sammen med designartefakter og refereres til i sikkerhedsgennemgange, hvilket opfylder ISO/IEC 42001 sporbarhedsprincipper. |   3   | D/V  |

---

## AD.6 Kontinuerlig feedback og finjustering af model

Forbedr modelens sikkerhedspræstation over tid, samtidig med at negativ drift forhindres.

|   #    | Description                                                                                                                                                                                   | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| AD.6.1 | Bekræft, at udviklere kan markere usikre eller ikke-kompatible forslag, og at markeringerne bliver registreret.                                                                               |   1   | D/V  |
| AD.6.2 | Bekræft, at samlet feedback informerer periodisk finjustering eller retrieval-augmenteret generering med verificerede sikre-kodningskorpora (f.eks. OWASP Cheat Sheets).                      |   2   |  D   |
| AD.6.3 | Bekræft, at et lukket kredsløbs evalueringsværktøj kører regressions test efter hver finjustering; sikkerhedsmålinger skal opfylde eller overgå tidligere baselineværdier før implementering. |   3   | D/V  |

---

### Referencer

* [NIST AI Risk Management Framework 1.0](https://nvlpubs.nist.gov/nistpubs/ai/nist.ai.100-1.pdf)
* [ISO/IEC 42001:2023 — AI Management Systems Requirements](https://www.iso.org/standard/81230.html)
* [OWASP Secure Coding Practices — Quick Reference Guide](https://owasp.org/www-project-secure-coding-practices-quick-reference-guide/)

