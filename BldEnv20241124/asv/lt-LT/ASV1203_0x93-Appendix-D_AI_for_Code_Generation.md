# Priedas D: AI Pagalba Užtikrinant Saugų Programavimo Valdymą ir Patikrinimą

## Tikslas

Šiame skyriuje apibrėžiamos pagrindinės organizacinės kontrolės, skirtos saugiam ir veiksmingam AI pagalba atliekamo kodavimo įrankių naudojimui programinės įrangos kūrimo metu, užtikrinant saugumą ir atsekamumą per visą programinės įrangos kūrimo gyvenimo ciklą (SDLC).

---

## AD.1 Dirbtiniu intelektu pagrįstas saugaus kodavimo darbo eiga

Integruokite DI įrankius organizacijos saugaus programinės įrangos kūrimo gyvavimo cikle (SSDLC), nesumažindami esamos saugumo apsaugos.

|   #    | Description                                                                                                                                                                       | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| AD.1.1 | Patikrinkite, ar dokumentuotas darbo procesas aprašo, kada ir kaip AI įrankiai gali generuoti, perrašyti ar peržiūrėti kodą.                                                      |   1   | D/V  |
| AD.1.2 | Patikrinkite, ar darbo eiga atitinka kiekvieną SSDLC fazę (dizainas, įgyvendinimas, kodo peržiūra, testavimas, diegimas).                                                         |   2   |  D   |
| AD.1.3 | Patikrinkite, ar metrikos (pvz., pažeidžiamumo tankis, vidutinis laikas aptikimui) renkami AI sukurtam kodui ir lyginamos su tik žmogaus sukurtų pagrindinių rodiklių reikšmėmis. |   3   | D/V  |

---

## AD.2 DI įrankio kvalifikacija ir grėsmių modeliavimas

Užtikrinkite, kad AI programavimo įrankiai būtų įvertinti pagal saugumo galimybes, riziką ir tiekimo grandinės poveikį prieš juos priimant.

|   #    | Description                                                                                                                                                                           | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| AD.2.1 | Patikrinkite, ar kiekvienos DI priemonės grėsmių modelis identifikuoja neteisėtą naudojimą, modelio invertavimą, duomenų nutekėjimą ir priklausomybių grandinės rizikas.              |   1   | D/V  |
| AD.2.2 | Patikrinkite, ar įrankių vertinimai apima statinę/dinaminę bet kurių vietinių komponentų analizę bei SaaS galinių taškų (TLS, autentifikavimas/autorizacija, žurnalavimas) vertinimą. |   2   |  D   |
| AD.2.3 | Patikrinkite, ar vertinimai atliekami pagal pripažintą sistemą ir kartojami po pagrindinių versijų pakeitimų.                                                                         |   3   | D/V  |

---

## AD.3 Saugaus užklausos ir konteksto valdymas

Užkirsti kelią slaptos informacijos, nuosavybinių kodų ir asmeninių duomenų nutekėjimui formuojant užklausas ar kontekstus dirbtinio intelekto modeliams.

|   #    | Description                                                                                                                                                      | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| AD.3.1 | Patikrinkite, ar rašytinė gairė draudžia siųsti paslaptis, prisijungimo duomenis arba klasifikuotą informaciją užklausose.                                       |   1   | D/V  |
| AD.3.2 | Patikrinkite, ar techninės priemonės (kliento pusės redagavimas, patvirtinti konteksto filtrai) automatiškai pašalina jautrius duomenis.                         |   2   |  D   |
| AD.3.3 | Patikrinkite, ar užklausos ir atsakymai yra tokenizuoti, šifruojami perduodant ir saugant bei ar saugojimo laikotarpiai atitinka duomenų klasifikavimo politiką. |   3   | D/V  |

---

## AD.4 Dirbtinio intelekto sukurtų kodų patikrinimas

Nustatykite ir pašalinkite pažeidžiamumus, sukurtus AI išvesties, prieš sujungiami ar diegiant kodą.

|   #    | Description                                                                                                                                                                             | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| AD.4.1 | Patikrinkite, ar AI sugeneruotas kodas visada yra peržiūrimas žmogaus.                                                                                                                  |   1   | D/V  |
| AD.4.2 | Patikrinkite, ar automatizuoti skaitytuvai (SAST/IAST/DAST) veikia kiekviename patraukimo prašyme, kuriame yra AI sukurtas kodas, ir blokuoja susijungimus esant kritiniams aptikimams. |   2   |  D   |
| AD.4.3 | Patikrinkite, ar diferencialiniai delsimieji testai arba savybių pagrindu sukurti testai įrodo saugumo požiūriu kritines elgsenas (pvz., įvesties tikrinimą, autorizacijos logiką).     |   3   | D/V  |

---

## AD.5 Kodo pasiūlymų paaiškinamumas ir atsekamumas

Suteikite auditoriams ir kūrėjams įžvalgų apie tai, kodėl buvo pateikta pasiūlymas ir kaip jis vystėsi.

|   #    | Description                                                                                                                                                    | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| AD.5.1 | Patikrinkite, ar užklausų/atsakymų poros yra registruojamos kartu su komitų identifikatoriais.                                                                 |   1   | D/V  |
| AD.5.2 | Patikrinkite, ar kūrėjai gali pateikti modelio citatas (mokymo fragmentus, dokumentaciją), pagrindžiančias pasiūlymą.                                          |   2   |  D   |
| AD.5.3 | Patikrinkite, ar aiškinamumo ataskaitos saugomos kartu su dizaino artefaktais ir nurodomos saugumo peržiūrose, atitinkančios ISO/IEC 42001 sekamumo principus. |   3   | D/V  |

---

## AD.6 Nuolatinis atsiliepimų teikimas ir modelio tobulinimas

Laikui bėgant gerinti modelio saugumo veikimą, užkertant kelią neigiamam poslinkiui.

|   #    | Description                                                                                                                                                                                                                | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| AD.6.1 | Patikrinkite, ar kūrėjai gali pažymėti nesaugias arba neprisitaikančias prie reikalavimų pasiūlymus, ir ar šie ženklai yra fiksuojami.                                                                                     |   1   | D/V  |
| AD.6.2 | Patikrinkite, ar apibendrintas grįžtamasis ryšys informuoja periodinį papildomą modelio apmokymą arba atgavimo pagrindu sukurtą generavimą, naudojant patikrintus saugaus kodo rašymo korpusus (pvz., OWASP Cheat Sheets). |   2   |  D   |
| AD.6.3 | Patikrinkite, ar uždaro ciklo vertinimo sistema vykdo regresijos testus po kiekvieno tikslinimo; saugumo metrikos turi atitikti arba viršyti ankstesnius bazinius rodiklius prieš diegiant.                                |   3   | D/V  |

---

### Nuorodos

* [NIST AI Risk Management Framework 1.0](https://nvlpubs.nist.gov/nistpubs/ai/nist.ai.100-1.pdf)
* [ISO/IEC 42001:2023 — AI Management Systems Requirements](https://www.iso.org/standard/81230.html)
* [OWASP Secure Coding Practices — Quick Reference Guide](https://owasp.org/www-project-secure-coding-practices-quick-reference-guide/)

