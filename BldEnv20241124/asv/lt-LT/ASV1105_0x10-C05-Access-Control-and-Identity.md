# C5 Prieigos valdymas ir tapatybės nustatymas AI komponentams ir naudotojams

## Valdymo tikslas

Efektyvi prieigos kontrolė AI sistemoms reikalauja tvirto tapatybės valdymo, kontekstą atitinkančios autorizacijos ir vykdymo realiuoju laiku pagal nulinės pasitikėjimo principus. Šios kontrolės užtikrina, kad žmonės, paslaugos ir autonominiai agentai sąveikautų tik su modeliais, duomenimis ir skaičiavimo ištekliais griežtai nustatytose ribose, vykdant nuolatinį patikrinimą ir audito galimybes.

---

## C5.1 Tapatybės valdymas ir autentifikacija

Sukurkite visų subjektų kriptografiškai pagrįstas tapatybes su daugiafaktorine autentifikacija privilegijuotoms operacijoms.

|   #   | Description                                                                                                                                                                                                                                              | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 5.1.1 | Patvirtinkite, kad visi žmonių vartotojai ir paslaugų principalai autentifikuojasi per centralizuotą įmonės identiteto tiekėją (IdP) naudojant OIDC/SAML protokolus su unikaliais tapatybės į žetoną susiejimais (be bendrinamų paskyrų ar kredencialų). |   1   | D/V  |
| 5.1.2 | Patikrinkite, ar didelės rizikos operacijos (modelio diegimas, svorių eksportas, mokymo duomenų prieiga, gamybos konfigūracijos pakeitimai) reikalauja daugiaplanio autentifikavimo arba papildomo autentifikavimo su sesijos pakartotiniu patvirtinimu. |   1   | D/V  |
| 5.1.3 | Patikrinkite, ar nauji vadovai prieš įgaudami prieigą prie gamybos sistemos yra patvirtinti tapatybės pagal NIST 800-63-3 IAL-2 arba lygiavertius standartus.                                                                                            |   2   |  D   |
| 5.1.4 | Patikrinkite, ar prieigos peržiūros atliekamos kas ketvirtį, naudojant automatizuotą neveiklių paskyrų aptikimą, kredencialų sukimosi laikymą ir deprovisionavimo veiklos procesus.                                                                      |   2   |  V   |
| 5.1.5 | Patikrinkite, ar federuoti DI agentai autentifikuojami per pasirašytus JWT tvirtinimus, kurių maksimalus galiojimo laikas yra 24 valandos ir kuriuose yra kriptografinis kilmės įrodymas.                                                                |   3   | D/V  |

---

## C5.2 Išteklių autorizacija ir mažiausios privilegijos

Įdiekite smulkios kontrolės prieigą prie visų DI išteklių naudodami aiškius leidimų modelius ir audito pėdsakus.

|   #   | Description                                                                                                                                                                                                                                                                                                | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 5.2.1 | Patikrinkite, ar kiekvienas DI išteklius (duomenų rinkiniai, modeliai, galutiniai taškai, vektorių kolekcijos, įterptųjų indeksai, skaičiavimo instancijos) taiko vaidmenų pagrindu paremtą prieigos kontrolę su aiškiomis leidimų sąrašais ir numatytomis draudimo politikomis.                           |   1   | D/V  |
| 5.2.2 | Patikrinkite, ar pagal numatytuosius nustatymus su paslaugų paskyromis taikomi mažiausios privilegijos principai, pradedant nuo tik skaitymo teisių, o rašymo prieigai reikalingas dokumentuotas verslo pateisinimas.                                                                                      |   1   | D/V  |
| 5.2.3 | Patikrinkite, ar visi prieigos valdymo pakeitimai yra susieti su patvirtintais pakeitimų prašymais ir nekeičiamai įrašyti su laiko žymomis, veikėjų tapatybėmis, išteklių identifikatoriais ir leidimų skirtumais.                                                                                         |   1   |  V   |
| 5.2.4 | Patikrinkite, ar duomenų klasifikacijos etiketės (asmens identifikavimo informacija - PII, sveikatos informacija - PHI, eksporto kontrolė, nuosavybės teisės) automatiškai perduodamos išvestinėms ištekliams (įterpimams, užklausų talpykloms, modelio išvestims) užtikrinant nuoseklų politikos vykdymą. |   2   |  D   |
| 5.2.5 | Patikrinkite, ar neautorizuoti prieigos bandymai ir privilegijų eskalavimo įvykiai sukelia realaus laiko įspėjimus su kontekstine metaduomenimis SIEM sistemoms per 5 minutes.                                                                                                                             |   2   | D/V  |

---

## C5.3 Dinaminis politikos vertinimas

Diegti atributais pagrįstą prieigos valdymo (ABAC) sistemą, skirtą kontekstiniais duomenimis pagrįstiems autorizacijos sprendimams, turint audito galimybes.

|   #   | Description                                                                                                                                                                                                                     | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 5.3.1 | Patikrinkite, ar autorizacijos sprendimai yra išoriniai ir perduodami specialiai skirtam politikos varikliui (OPA, Cedar ar ekvivalentui), kuris yra pasiekiamas per autentifikuotus API su kriptografinės vientisybės apsauga. |   1   | D/V  |
| 5.3.2 | Patikrinkite, ar politikos įvertina dinamiškus atributus vykdymo metu, įskaitant vartotojo leidimo lygį, išteklių jautrumo klasifikaciją, užklausos kontekstą, nuomininko izoliaciją ir laiko apribojimus.                      |   1   | D/V  |
| 5.3.3 | Patikrinkite, ar politikos apibrėžimai yra valdomi versijų kontrole, peržiūrimi kolegų ir patvirtinami automatizuotais testavimais CI/CD grandinėse prieš diegiant į gamybą.                                                    |   2   |  D   |
| 5.3.4 | Patikrinkite, ar politikos vertinimo rezultatai apima struktūruotas sprendimų priežastis ir yra perduodami SIEM sistemoms koreliacijos analizei ir atitikties ataskaitų teikimui.                                               |   2   |  V   |
| 5.3.5 | Patikrinkite, ar politikos talpyklos laiko gyvavimo (TTL) reikšmės neviršija 5 minučių jautriems ištekliams ir 1 valandos standartiniams ištekliams su talpyklos nebegaliojimo galimybėmis.                                     |   3   | D/V  |

---

## C5.4 Užklausos laikotarpio saugumo užtikrinimas

Įgyvendinkite duomenų bazės lygio saugumo valdiklius su privaloma filtracija ir eilutės lygio saugumo politikomis.

|   #   | Description                                                                                                                                                                                                                           | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 5.4.1 | Patikrinkite, ar visi vektorinių duomenų bazių ir SQL užklausos apima privalomus saugumo filtrus (nuomininko ID, jautrumo žymas, vartotojo aprėptį), kurie yra įgyvendinti duomenų bazės variklio lygyje, o ne programos kodo lygyje. |   1   | D/V  |
| 5.4.2 | Patikrinkite, ar eilučių lygio saugumo (RLS) politikos ir laukų lygio maskavimas yra įgalinti su politikos paveldėjimu visose vektorinių duomenų baze, paieškos indeksų ir mokymo duomenų rinkiniuose.                                |   1   | D/V  |
| 5.4.3 | Patikrinkite, ar nepavykusios autorizacijos vertinimai užkirs kelią „supainioto tarnytojo atakoms“ nedelsiant nutraukiant užklausas ir grąžinant aiškius autorizacijos klaidų kodus, o ne tuščius rezultatų rinkinius.                |   2   |  D   |
| 5.4.4 | Patikrinkite, ar politikos vertinimo delsos laikas nuolat stebimas su automatiniais įspėjimais apie laiko viršijimo sąlygas, kurios galėtų leisti apeiti autorizaciją.                                                                |   2   |  V   |
| 5.4.5 | Patikrinkite, ar užklausų pakartojimo mechanizmai iš naujo vertina autorizacijos politikas, atsižvelgdami į dinamiškus leidimų pakeitimus aktyvių naudotojų sesijų metu.                                                              |   3   | D/V  |

---

## C5.5 Išvesties filtravimas ir duomenų praradimo prevencija

Vykdykite galutinio apdorojimo kontrolę, kad būtų užkirstas kelias neleistinam duomenų atskleidimui AI sugeneruotame turinyje.

|   #   | Description                                                                                                                                                                                                                           | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 5.5.1 | Patikrinkite, ar po inferencijos filtravimo mechanizmai nuskenuoja ir pašalina neautorizuotą asmeninę identifikuojamą informaciją (PII), klasifikuotą informaciją ir nuosavybės duomenis prieš pateikiant turinį užklausos teikėjams. |   1   | D/V  |
| 5.5.2 | Patikrinkite, ar modelio išvestyse esantys citavimai, nuorodos ir šaltinių priskyrimai yra patvirtinti pagal kviečiančiojo teises, ir pašalinkite juos, jei nustatoma neautorizuota prieiga.                                          |   1   | D/V  |
| 5.5.3 | Patikrinkite, ar išvesties formato apribojimai (valyti PDF failai, nuotraukos be metaduomenų, patvirtinti failų tipai) yra taikomi pagal vartotojo leidimų lygius ir duomenų klasifikacijas.                                          |   2   |  D   |
| 5.5.4 | Patikrinkite, ar redagavimo algoritmai yra deterministiniai, versijų valdomi ir palaiko audito žurnalus, kad būtų užtikrinta atitikties tyrimų ir forensikos analizės galimybė.                                                       |   2   |  V   |
| 5.5.5 | Patikrinkite, ar didelės rizikos redagavimo įvykiai generuoja adaptuojamus žurnalus, kuriuose yra pirminio turinio kriptografiniai maišos žymekliai, skirti teismo ekspertizės atkūrimui be duomenų atskleidimo.                      |   3   |  V   |

---

## C5.6 Daugiakartinė nuomininkų izoliacija

Užtikrinkite kriptografinę ir loginę izoliaciją tarp nuomininkų bendroje DI infrastruktūroje.

|   #   | Description                                                                                                                                                                                                                  | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 5.6.1 | Patikrinkite, ar atminties vietos, įterpimo saugyklos, talpyklos įrašai ir laikini failai yra atskirti pagal vardų sritis kiekvienam nuomininkui, užtikrinant saugų jų ištrynimą nuomininkui pašalinus arba užbaigus sesiją. |   1   | D/V  |
| 5.6.2 | Patikrinkite, ar kiekvienas API užklausimas apima autentifikuotą nuomininko identifikatorių, kuris yra kriptografiškai patvirtintas atsižvelgiant į sesijos kontekstą ir naudotojo teises.                                   |   1   | D/V  |
| 5.6.3 | Patikrinkite, ar tinklo politikos įgyvendina numatytąjį draudimo principą (default-deny) tarp nuomininkų bendravimo paslaugų tinkleliuose ir konteinerių koordinavimo platformose.                                           |   2   |  D   |
| 5.6.4 | Patikrinkite, ar šifravimo raktai yra unikalūs kiekvienam nuomininkui, naudojant kliento valdomą raktą (CMK) ir užtikrinant kriptografinę izoliaciją tarp nuomininkų duomenų saugyklų.                                       |   3   |  D   |

---

## C5.7 Autonominio agente autorizavimas

Valdykite AI agentų ir autonominių sistemų teises naudodami apriboto galiojimo gebėjimų žetonus ir nuolatinį autorizavimą.

|   #   | Description                                                                                                                                                                                                                                                        | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 5.7.1 | Patikrinkite, ar autonominiai agentai gauna apribotųjų galimybių žetonus, kurie aiškiai nurodo leidžiamus veiksmus, prieinamus išteklius, laiko ribas ir veiklos apribojimus.                                                                                      |   1   | D/V  |
| 5.7.2 | Patikrinkite, ar didelę riziką keliančios galimybės (prieiga prie failų sistemos, kodo vykdymas, išoriniai API kvietimai, finansinės operacijos) pagal numatytuosius nustatymus yra išjungtos ir jų aktyvavimui reikalingi aiškūs leidimai su verslo pagrindimais. |   1   | D/V  |
| 5.7.3 | Patikrinkite, ar galios žetonai yra susieti su naudotojo sesijomis, įtraukti kriptografinės vientisumo apsaugą ir užtikrinti, kad jų negalima būtų išsaugoti ar pakartotinai naudoti neprisijungus.                                                                |   2   |  D   |
| 5.7.4 | Patikrinkite, ar agento inicijuotos akcijos pereina antrinį autorizavimą per ABAC politikos variklį su pilnu konteksto įvertinimu ir audito žurnalų fiksavimu.                                                                                                     |   2   |  V   |
| 5.7.5 | Patikrinkite, ar agentų klaidų sąlygos ir išimčių apdorojimas apima galimybių srities informaciją, kad būtų galima palaikyti incidentų analizę ir teismo ekspertizę.                                                                                               |   3   |  V   |

---

## Nuorodos

### Standartai ir pagrindai

* [NIST SP 800-63-3: Digital Identity Guidelines](https://pages.nist.gov/800-63-3/)
* [Zero Trust Architecture – NIST SP 800-207](https://nvlpubs.nist.gov/nistpubs/specialpublications/NIST.SP.800-207.pdf)
* [OWASP Application Security Verification Standard (AISVS)](https://owasp.org/www-project-application-security-verification-standard/)
  ​
### Įgyvendinimo vadovai

* [Identity and Access Management in the AI Era: 2025 Guide – IDSA](https://www.idsalliance.org/blog/identity-and-access-management-in-the-ai-era-2025-guide/)
* [Attribute-Based Access Control with OPA – Permify](https://medium.com/permify-tech-blog/attribute-based-access-control-abac-implementation-with-open-policy-agent-opa-b47052248f29)
* [How We Designed Cedar to Be Intuitive, Fast, and Safe – AWS](https://aws.amazon.com/blogs/security/how-we-designed-cedar-to-be-intuitive-to-use-fast-and-safe/)
  ​
### Dirbtinio intelekto specifinis saugumas

* [Row Level Security in Vector DBs for RAG – Bluetuple.ai](https://medium.com/bluetuple-ai/implementing-row-level-security-in-vector-dbs-for-rag-applications-fdbccb63d464)
* [Tenant Isolation in Multi-Tenant Systems – WorkOS](https://workos.com/blog/tenant-isolation-in-multi-tenant-systems)
* [Handling AI Agent Permissions – Stytch](https://stytch.com/blog/handling-ai-agent-permissions/)
* [OWASP Top 10 for Large Language Model Applications](https://owasp.org/www-project-top-10-for-large-language-model-applications/)

