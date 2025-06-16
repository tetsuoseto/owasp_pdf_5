# Vedlegg D: Kunstig intelligens-assistert sikker koding styring og verifisering

## Målsetting

Dette kapitlet definerer grunnleggende organisatoriske kontroller for sikker og effektiv bruk av AI-assisterte kodingverktøy under programvareutvikling, og sikrer sikkerhet og sporbarhet gjennom hele programvareutviklingssyklusen (SDLC).

---

## AD.1 AI-assistert sikker-koding arbeidsflyt

Integrer AI-verktøy i organisasjonens sikre programvareutviklingslivssyklus (SSDLC) uten å svekke eksisterende sikkerhetsporter.

|   #    | Description                                                                                                                                                                 | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| AD.1.1 | Bekreft at en dokumentert arbeidsflyt beskriver når og hvordan AI-verktøy kan generere, omstrukturere eller gjennomgå kode.                                                 |   1   | D/V  |
| AD.1.2 | Verifiser at arbeidsflyten samsvarer med hver fase i SSDLC (design, implementering, kodegjennomgang, testing, distribusjon).                                                |   2   |  D   |
| AD.1.3 | Verifiser at måledata (f.eks. sårbarhetstetthet, gjennomsnittlig tid til å oppdage) samles inn for AI-generert kode og sammenlignes med baser uten menneskelig innblanding. |   3   | D/V  |

---

## AD.2 AI-verktøykvalifisering og trusselmodellering

Sørg for at AI-kodeverktøy vurderes for sikkerhetsfunksjoner, risiko og påvirkning på forsyningskjeden før de tas i bruk.

|   #    | Description                                                                                                                                                                      | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| AD.2.1 | Bekreft at en trusselmodell for hvert AI-verktøy identifiserer misbruk, modell-inversjon, datalekkasjer og avhengighetskjede­risikoer.                                           |   1   | D/V  |
| AD.2.2 | Bekreft at verktøyevalueringer inkluderer statisk/dynamisk analyse av eventuelle lokale komponenter og vurdering av SaaS-endepunkter (TLS, autentisering/autorisasjon, logging). |   2   |  D   |
| AD.2.3 | Sørg for at evalueringer følger en anerkjent rammeverk og blir gjennomført på nytt etter større versjonsendringer.                                                               |   3   | D/V  |

---

## AD.3 Sikker Prompt- og Kontekstadministrasjon

Forhindre lekkasje av hemmeligheter, proprietær kode og persondata når man konstruerer prompt eller kontekster for AI-modeller.

|   #    | Description                                                                                                                                              | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| AD.3.1 | Bekreft at skriftlige retningslinjer forbyr å sende hemmeligheter, legitimasjon eller klassifiserte data i forespørsler.                                 |   1   | D/V  |
| AD.3.2 | Bekreft at tekniske kontrollmekanismer (klient-side redigering, godkjente kontekstfiltre) automatisk fjerner sensitive artefakter.                       |   2   |  D   |
| AD.3.3 | Verifiser at forespørsler og svar blir tokenisert, kryptert under overføring og i hvile, og at lagringsperiodene overholder dataklassifiseringspolicyen. |   3   | D/V  |

---

## AD.4 Verifisering av AI-generert kode

Oppdag og utbedre sårbarheter introdusert av AI-resultater før koden slås sammen eller distribueres.

|   #    | Description                                                                                                                                                   | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| AD.4.1 | Sørg for at AI-generert kode alltid blir gjenstand for menneskelig kodegjennomgang.                                                                           |   1   | D/V  |
| AD.4.2 | Bekreft at automatiserte skannere (SAST/IAST/DAST) kjører på hver pull request som inneholder AI-generert kode og blokkerer sammenslåinger ved kritiske funn. |   2   |  D   |
| AD.4.3 | Bekreft at differensielle fuzz-tester eller eiendomsbaserte tester beviser sikkerhetskritiske oppførsel (f.eks. inputvalidering, autorisasjonslogikk).        |   3   | D/V  |

---

## AD.5 Forklarbarhet og sporbarhet av kodeforslag

Gi revisorer og utviklere innsikt i hvorfor et forslag ble gitt og hvordan det utviklet seg.

|   #    | Description                                                                                                                                                            | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| AD.5.1 | Bekreft at spørsmål/svar-par blir logget med commit-IDer.                                                                                                              |   1   | D/V  |
| AD.5.2 | Bekreft at utviklere kan vise modellens referanser (treningsutdrag, dokumentasjon) som støtter et forslag.                                                             |   2   |  D   |
| AD.5.3 | Bekreft at forklaringsrapporter lagres sammen med designartefakter og refereres til i sikkerhetsgjennomganger, i samsvar med ISO/IEC 42001-prinsippene for sporbarhet. |   3   | D/V  |

---

## AD.6 Kontinuerlig tilbakemelding og finjustering av modell

Forbedre modellens sikkerhetsytelse over tid samtidig som man forhindrer negativ drift.

|   #    | Description                                                                                                                                                                       | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| AD.6.1 | Bekreft at utviklere kan merke usikre eller ikke-kompatible forslag, og at merkene blir fulgt opp.                                                                                |   1   | D/V  |
| AD.6.2 | Verifiser at samlet tilbakemelding informerer periodisk finjustering eller gjenhentingsforsterket generering med godkjente sikre-kodingskorpora (f.eks. OWASP Cheat Sheets).      |   2   |  D   |
| AD.6.3 | Bekreft at en lukket løkke evalueringsramme kjører regresjonstester etter hver finjustering; sikkerhetsmålinger må oppfylle eller overgå tidligere referansenivåer før utrulling. |   3   | D/V  |

---

### Referanser

* [NIST AI Risk Management Framework 1.0](https://nvlpubs.nist.gov/nistpubs/ai/nist.ai.100-1.pdf)
* [ISO/IEC 42001:2023 — AI Management Systems Requirements](https://www.iso.org/standard/81230.html)
* [OWASP Secure Coding Practices — Quick Reference Guide](https://owasp.org/www-project-secure-coding-practices-quick-reference-guide/)

