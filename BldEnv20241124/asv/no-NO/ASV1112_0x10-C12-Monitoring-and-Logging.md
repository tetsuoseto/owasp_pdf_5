# C12 Overvåking, logging og anomalidetektering

## Kontrollmål

Denne seksjonen gir krav for å levere sanntids- og rettsmedisinsk synlighet i hva modellen og andre AI-komponenter ser, gjør og returnerer, slik at trusler kan oppdages, triageres og læres av.

## C12.1 Forespørsel- og responslogging

|   #    | Description                                                                                                                                                                                                       | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 12.1.1 | Sørg for at alle brukerforespørsler og modellresponsene logges med passende metadata (f.eks. tidsstempel, bruker-ID, økt-ID, modellversjon).                                                                      |   1   | D/V  |
| 12.1.2 | Bekreft at logger lagres i sikre, tilgangskontrollerte lagringssteder med riktige retningslinjer for oppbevaring og sikkerhetskopieringsprosedyrer.                                                               |   1   | D/V  |
| 12.1.3 | Bekreft at logglagringssystemer implementerer kryptering i hvilemodus og under overføring for å beskytte sensitiv informasjon som finnes i logger.                                                                |   1   | D/V  |
| 12.1.4 | Bekreft at sensitive data i forespørsler og utdata automatisk blir redigert eller maskert før logging, med konfigurerbare redigeringsregler for personopplysninger (PII), legitimasjon og proprietær informasjon. |   1   | D/V  |
| 12.1.5 | Bekreft at beslutninger om policy og handlinger for sikkerhetsfiltrering loggføres med tilstrekkelig detalj for å muliggjøre revisjon og feilsøking av innholdsmoderering systemer.                               |   2   | D/V  |
| 12.1.6 | Sikkerstill at loggens integritet er beskyttet gjennom for eksempel kryptografiske signaturer eller skrivebeskyttet lagring.                                                                                      |   2   | D/V  |

---

## C12.2 Misbruksdeteksjon og varsling

|   #    | Description                                                                                                                                                                                 | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 12.2.1 | Bekreft at systemet oppdager og varsler om kjente jailbreak-mønstre, forsøk på promptinnsprøytning og fiendtlige innganger ved bruk av signaturbasert deteksjon.                            |   1   | D/V  |
| 12.2.2 | Bekreft at systemet integreres med eksisterende Security Information and Event Management (SIEM) plattformer ved bruk av standard loggformater og protokoller.                              |   1   | D/V  |
| 12.2.3 | Bekreft at berikede sikkerhetshendelser inkluderer AI-spesifikk kontekst som modellidentifikatorer, konfidenspoeng og beslutninger fra sikkerhetsfiltre.                                    |   2   | D/V  |
| 12.2.4 | Bekreft at oppdagelse av atferdsavvik identifiserer uvanlige samtalemønstre, overdrevne forsøk på gjentakelse eller systematiske sonderingsatferder.                                        |   2   | D/V  |
| 12.2.5 | Bekreft at sanntidsvarslingmekanismer varsler sikkerhetsteam når potensielle policybrudd eller angrepsforsøk blir oppdaget.                                                                 |   2   | D/V  |
| 12.2.6 | Bekreft at tilpassede regler er inkludert for å oppdage AI-spesifikke trusselmønstre, inkludert koordinerte jailbreak-forsøk, kampanjer for promptinjeksjon og angrep på modellekstraksjon. |   2   | D/V  |
| 12.2.7 | Verifiser at automatiserte arbeidsflyter for hendelsesrespons kan isolere kompromitterte modeller, blokkere ondsinnede brukere og eskalere kritiske sikkerhetshendelser.                    |   3   | D/V  |

---

## C12.3 Modellavdriftsdeteksjon

|   #    | Description                                                                                                                                                                         | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 12.3.1 | Bekreft at systemet sporer grunnleggende ytelsesindikatorer som nøyaktighet, konfidenspoeng, latenstid og feilrater på tvers av modellversjoner og tidsperioder.                    |   1   | D/V  |
| 12.3.2 | Verifiser at automatiske varsler utløses når ytelsesmetrikker overskrider forhåndsdefinerte nedgangsterskler eller avviker betydelig fra baselinjer.                                |   2   | D/V  |
| 12.3.3 | Bekreft at overvåkingsverktøy for hallusinasjonsdeteksjon identifiserer og markerer tilfeller der modellutdata inneholder faktiske feil, inkonsistent eller fabrikkert informasjon. |   2   | D/V  |

---

## C12.4 Ytelses- og atferdstelemetri

|   #    | Description                                                                                                                                     | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 12.4.1 | Sørg for at driftsmetrikker, inkludert forespørselsventetid, tokenforbruk, minnebruk og gjennomstrømning, kontinuerlig samles inn og overvåkes. |   1   | D/V  |
| 12.4.2 | Verifiser at suksess- og feilrater spores med kategorisering av feiltyper og deres grunnårsaker.                                                |   1   | D/V  |
| 12.4.3 | Bekreft at overvåking av ressursbruk inkluderer GPU/CPU-bruk, minneforbruk og lagringskrav, med varsling ved terskeloverskridelser.             |   2   | D/V  |

---

## C12.5 Planlegging og gjennomføring av AI-hendelsesrespons

|   #    | Description                                                                                                                                                                | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 12.5.1 | Bekreft at beredskapsplaner for hendelser spesifikt tar for seg sikkerhetshendelser relatert til KI, inkludert modellkompromittering, datainfisering og fiendtlige angrep. |   1   | D/V  |
| 12.5.2 | Bekreft at hendelsesresponsteam har tilgang til AI-spesifikke rettsmedisinske verktøy og ekspertise for å undersøke modellatferd og angrepsvektorer.                       |   2   | D/V  |
| 12.5.3 | Bekreft at etterhendelsesanalysen inkluderer vurderinger av modellomtrening, oppdateringer av sikkerhetsfiltre og integrering av lærdommer i sikkerhetskontroller.         |   3   | D/V  |

---

## C12.5 Oppdagelse av nedgang i AI-ytelse

Overvåk og oppdag forringelse i AI-modellens ytelse og kvalitet over tid.

|   #    | Description                                                                                                                                      | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 12.5.1 | Sørg for at modellens nøyaktighet, presisjon, tilbakekalling og F1-poeng kontinuerlig overvåkes og sammenlignes med baseline-terskler.           |   1   | D/V  |
| 12.5.2 | Bekreft at overvåking av data-drift oppdager endringer i inndatadistribusjonen som kan påvirke modellens ytelse.                                 |   1   | D/V  |
| 12.5.3 | Bekreft at konseptdriftoppdagelse identifiserer endringer i forholdet mellom innganger og forventede utganger.                                   |   2   | D/V  |
| 12.5.4 | Bekreft at ytelsesforringelse utløser automatiserte varsler og setter i gang arbeidsflyter for modellomtrening eller utskifting.                 |   2   | D/V  |
| 12.5.5 | Verifiser at rotårsaksanalyse av degradering korrelerer ytelsesnedsettelser med datavariasjoner, infrastrukturproblemer eller eksterne faktorer. |   3   |  V   |

---

## C12.6 DAG-visualisering og arbeidsflytsikkerhet

Beskytt arbeidsflytvisualiseringssystemer mot informasjonslekkasje og manipulasjonsangrep.

|   #    | Description                                                                                                                                              | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 12.6.1 | Sørg for at DAG-visualiseringsdata blir renset for å fjerne sensitiv informasjon før lagring eller overføring.                                           |   1   | D/V  |
| 12.6.2 | Bekreft at tilgangskontroller for arbeidsflytvisualisering sikrer at kun autoriserte brukere kan se agentens beslutningsstier og resonnementsspor.       |   1   | D/V  |
| 12.6.3 | Bekreft at DAG-dataenes integritet er beskyttet gjennom kryptografiske signaturer og manipulasjons-sikre lagringsmekanismer.                             |   2   | D/V  |
| 12.6.4 | Bekreft at arbeidsflytvisualiseringssystemer implementerer inndata-validering for å forhindre injeksjonsangrep gjennom konstruerte node- eller kantdata. |   2   | D/V  |
| 12.6.5 | Bekreft at sanntidsoppdateringer av DAG er hastighetsbegrenset og validert for å forhindre tjenestenektangrep på visualiseringssystemer.                 |   3   | D/V  |

---

## C12.7 Proaktiv overvåking av sikkerhetsatferd

Deteksjon og forebygging av sikkerhetstrusler gjennom proaktiv analyse av agentatferd.

|   #    | Description                                                                                                              | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 12.7.1 | Bekreft at proaktive agentatferder er sikkerhetsvalidert før utførelse med integrert risikovurdering.                    |   1   | D/V  |
| 12.7.2 | Bekreft at autonome initiativutløsere inkluderer evaluering av sikkerhetskontekst og vurdering av trussellandskap.       |   2   | D/V  |
| 12.7.3 | Sørg for at proaktive atferdsmønstre blir analysert for potensielle sikkerhetsimplikasjoner og utilsiktede konsekvenser. |   2   | D/V  |
| 12.7.4 | Sørg for at sikkerhetskritiske proaktive tiltak krever eksplisitte godkjenningskjeder med revisjonsspor.                 |   3   | D/V  |
| 12.7.5 | Bekreft at oppdagelse av atferdsavvik identifiserer avvik i proaktive agentmønstre som kan indikere kompromittering.     |   3   | D/V  |

---

## Referanser

* [NIST AI Risk Management Framework 1.0 - Manage 4.1 and 4.3](https://nvlpubs.nist.gov/nistpubs/ai/nist.ai.100-1.pdf)
* [ISO/IEC 42001:2023 — AI Management Systems Requirements - Annex B 6.2.6](https://www.iso.org/standard/81230.html)
* [EU AI Act — Article 12, 13, 16 and 19 on Logging and Record-keeping](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX%3A32024R1689)

