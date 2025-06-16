# 10 Motståndskraft mot adversariella attacker och sekretessförsvar

## Kontrollmål

Säkerställ att AI-modeller förblir pålitliga, integritetsbevarande och motståndskraftiga mot missbruk vid attacker som undvikande, inferens, extraktion eller förgiftning.

---

## 10.1 Modelljustering och säkerhet

Skydda mot skadliga eller policyöverträdande resultat.

|   #    | Description                                                                                                                                                  | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 10.1.1 | Verifiera att en testsuite för justering (red-team-promptar, jailbreak-prober, otillåtet innehåll) är versionskontrollerad och körs vid varje modellrelease. |   1   | D/V  |
| 10.1.2 | Verifiera att avvisning och säkerhetsavslutningsskydd är upprätthållna.                                                                                      |   1   |  D   |
| 10.1.3 | Verifiera att en automatiserad utvärderare mäter andelen skadligt innehåll och markerar regressionsnivåer som överstiger en angiven tröskel.                 |   2   | D/V  |
| 10.1.4 | Verifiera att counter-jailbreak-träning är dokumenterad och reproducerbar.                                                                                   |   2   |  D   |
| 10.1.5 | Verifiera att formella bevis för efterlevnad av policy eller certifierad övervakning täcker kritiska områden.                                                |   3   |  V   |

---

## 10.2 Motståndskraft mot adversariella exempel

Öka motståndskraften mot manipulerade indata. Robust adversarial-träning och benchmark-poängsättning är den nuvarande bästa metoden.

|   #    | Description                                                                                                                           | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 10.2.1 | Verifiera att projektets repositorier inkluderar konfigurationer för adversarial träning med reproducerbara slumpmässiga tal (seeds). |   1   |  D   |
| 10.2.2 | Verifiera att detektionssystemet för adversariella exempel genererar blockeringlarm i produktionspipelines.                           |   2   | D/V  |
| 10.2.4 | Verifiera att certifierade robusthetsbevis eller intervallgränscertifikat täcker åtminstone de mest kritiska klasserna.               |   3   |  V   |
| 10.2.5 | Verifiera att regressionstester använder adaptiva attacker för att bekräfta att ingen mätbar robusthetsförlust förekommer.            |   3   |  V   |

---

## 10.3 Åtgärder mot medlemskapsinferens

Begränsa möjligheten att avgöra om en post fanns i träningsdata. Differentierad sekretess och maskering av konfidenspoäng är fortfarande de mest effektiva kända försvaren.

|   #    | Description                                                                                                      | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 10.3.1 | Verifiera att entropiregularisering per förfrågan eller temperaturskalning minskar överförsäkrade förutsägelser. |   1   |  D   |
| 10.3.2 | Verifiera att träningen använder ε-begränsad differentierad privat optimering för känsliga dataset.              |   2   |  D   |
| 10.3.3 | Verifiera att attacksimuleringar (skuggmodell eller svartlåda) visar attack AUC ≤ 0,60 på hållna testdata.       |   2   |  V   |

---

## 10.4 Motstånd mot modell-inversion

Förhindra rekonstruktion av privata attribut. Nya undersökningar betonar utdataavklippning och DP-garantier som praktiska skyddsåtgärder.

|   #    | Description                                                                                                 | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 10.4.1 | Verifiera att känsliga attribut aldrig direkt visas; använd vid behov grupper eller en vägstransformering.  |   1   |  D   |
| 10.4.2 | Verifiera att förfrågningshastighetsgränser begränsar upprepade adaptiva förfrågningar från samma huvudman. |   1   | D/V  |
| 10.4.3 | Verifiera att modellen är tränad med integritetsbevarande brus.                                             |   2   |  D   |

---

## 10.5 Försvar mot modellutvinning

Upptäck och förhindra obehörig kloning. Vattenmärkning och analys av frågemönster rekommenderas.

|   #    | Description                                                                                                                                   | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 10.5.1 | Verifiera att inferens-gateways upprätthåller globala och per-API-nyckel hastighetsbegränsningar anpassade till modellens memoreringströskel. |   1   |  D   |
| 10.5.2 | Verifiera att statistik för fråga-entropi och indata-flertal används för att mata en automatisk extraktionsdetektor.                          |   2   | D/V  |
| 10.5.3 | Verifiera att känsliga eller probabilistiska vattenstämplar kan bevisas med p < 0,01 i ≤ 1 000 förfrågningar mot en misstänkt klon.           |   2   |  V   |
| 10.5.4 | Verifiera att vattenmärkesnycklar och triggersatser lagras i en hårdvarusäkerhetsmodul och roteras årligen.                                   |   3   |  D   |
| 10.5.5 | Verifiera att extraktions-varningshändelser inkluderar stötande frågor och är integrerade med incidenthanteringsspel.                         |   3   |  V   |

---

## 10.6 Upptäckt av förorenade data vid inferenstidpunkt

Identifiera och neutralisera bakdörrs- eller förgiftade ingångar.

|   #    | Description                                                                                                                                  | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 10.6.1 | Verifiera att ingångar passerar genom en anomalidetektor (t.ex. STRIP, konsekvenspoängsättning) innan modellinferens.                        |   1   |  D   |
| 10.6.2 | Verifiera att detektors tröskelvärden är justerade på rena/förgiftade valideringsuppsättningar för att uppnå mindre än 5 % falska positiver. |   1   |  V   |
| 10.6.3 | Verifiera att indata som flaggats som förgiftade utlöser mjuka blockeringar och arbetsflöden för manuell granskning.                         |   2   |  D   |
| 10.6.4 | Verifiera att detektorer är stresstestad med adaptiva, triggerlösa bakdörrsattacker.                                                         |   2   |  V   |
| 10.6.5 | Verifiera att mätvärden för upptäcktseffektivitet loggas och periodvis omvärderas med uppdaterad hotinformation.                             |   3   |  D   |

---

## 10.7 Dynamisk anpassning av säkerhetspolicy

Säkerhetspolicyuppdateringar i realtid baserade på hotintelligens och beteendeanalys.

|   #    | Description                                                                                                                                         | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 10.7.1 | Verifiera att säkerhetspolicys kan uppdateras dynamiskt utan att agenten startas om samtidigt som integriteten för policyns version bibehålls.      |   1   | D/V  |
| 10.7.2 | Verifiera att policyuppdateringar är kryptografiskt signerade av auktoriserad säkerhetspersonal och validerade innan de tillämpas.                  |   2   | D/V  |
| 10.7.3 | Verifiera att dynamiska policyändringar loggas med fullständiga revisionsspår inklusive motivering, godkännandekedjor och återställningsprocedurer. |   2   | D/V  |
| 10.7.4 | Verifiera att adaptiva säkerhetsmekanismer justerar känsligheten för hotdetektion baserat på riskkontext och beteendemönster.                       |   3   | D/V  |
| 10.7.5 | Verifiera att beslut om policyanpassning är förklarbara och inkluderar spår av bevis för säkerhetsteamets granskning.                               |   3   | D/V  |

---

## 10.8 Reflektionsbaserad säkerhetsanalys

Säkerhetsvalidering genom agentens självreflektion och metakognitiv analys.

|   #    | Description                                                                                                                                        | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 10.8.1 | Verifiera att agentens reflektionsmekanismer inkluderar säkerhetsinriktad självvärdering av beslut och åtgärder.                                   |   1   | D/V  |
| 10.8.2 | Verifiera att reflektionens utdata valideras för att förhindra manipulation av självbedömningsmekanismer av fientliga indata.                      |   2   | D/V  |
| 10.8.3 | Verifiera att metakognitiv säkerhetsanalys identifierar potentiell partiskhet, manipulation eller kompromettering i agenters resoneringsprocesser. |   2   | D/V  |
| 10.8.4 | Verifiera att säkerhetsvarningar baserade på reflektion utlöser förbättrad övervakning och potentiella arbetsflöden för mänsklig intervention.     |   3   | D/V  |
| 10.8.5 | Verifiera att kontinuerligt lärande från säkerhetsreflektioner förbättrar hotdetektering utan att försämra legitim funktionalitet.                 |   3   | D/V  |

---

## 10.9 Evolution och Självförbättringssäkerhet

Säkerhetskontroller för agentsystem med förmåga till självmodifiering och evolution.

|   #    | Description                                                                                                             | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 10.9.1 | Verifiera att självmodifieringsfunktioner är begränsade till utpekade säkra områden med formella verifieringsgränser.   |   1   | D/V  |
| 10.9.2 | Verifiera att utvecklingsförslag genomgår en säkerhetspåverkansbedömning innan de implementeras.                        |   2   | D/V  |
| 10.9.3 | Verifiera att självförbättringsmekanismer inkluderar återställningsfunktioner med integritetskontroll.                  |   2   | D/V  |
| 10.9.4 | Verifiera att meta-lärande säkerhet förhindrar illvillig manipulation av förbättringsalgoritmer.                        |   3   | D/V  |
| 10.9.5 | Verifiera att rekursiv självförbättring är begränsad av formella säkerhetsvillkor med matematiska bevis för konvergens. |   3   | D/V  |

---

### Referenser

* [MITRE ATLAS adversary tactics for ML](https://atlas.mitre.org/)
* [NIST AI Risk Management Framework 1.0, 2023](https://nvlpubs.nist.gov/nistpubs/ai/nist.ai.100-1.pdf)
* [OWASP Top 10 for LLM Applications, 2025](https://owasp.org/www-project-top-10-for-large-language-model-applications/)
* [Adversarial Training: A Survey — Zhao et al., 2024](https://arxiv.org/abs/2410.15042)
* [RobustBench adversarial-robustness benchmark](https://robustbench.github.io/)
* [Membership-Inference & Model-Inversion Risk Survey, 2025](https://www.sciencedirect.com/science/article/abs/pii/S0950705125003867)
* [PURIFIER: Confidence-Score Defense against MI Attacks — AAAI 2023](https://ojs.aaai.org/index.php/AAAI/article/view/26289)
* [Model-Inversion Attacks & Defenses Survey — AI Review, 2025](https://link.springer.com/article/10.1007/s10462-025-11248-0)
* [Comprehensive Defense Framework Against Model Extraction — IEEE TDSC 2024](https://doi.org/10.1109/TDSC.2023.3261327)
* [Fragile Model Watermarking Survey — 2025](https://www.sciencedirect.com/science/article/abs/pii/S0165168425002026)
* [Data Poisoning in Deep Learning: A Survey — Zhao et al., 2025](https://arxiv.org/abs/2503.22759)
* [BDetCLIP: Multimodal Prompting Backdoor Detection — Niu et al., 2024](https://arxiv.org/abs/2405.15269)

