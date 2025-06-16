# C7-mallin käyttäytyminen, tulostehallinta ja turvallisuuden varmistus

## Ohjaustavoite

Mallin tuotosten on oltava rakenteellisia, luotettavia, turvallisia, selitettäviä ja jatkuvasti valvottuja tuotantoympäristössä. Näin toimimalla vähennetään harhaluuloja, tietosuojavuotoja, haitallista sisältöä ja hallitsemattomia toimintoja, samalla kun lisätään käyttäjien luottamusta ja sääntelyvaatimusten noudattamista.

---

## C7.1 Tulostemuodon valvonta

Tiukat skeemat, rajoitettu dekoodaus ja jälkikäsittelyn validointi estävät virheellistä tai haitallista sisältöä leviämästä.

|   #   | Description                                                                                                                                                                                                    | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 7.1.1 | Varmista, että vastauskäsikirjat (esim. JSON-skeema) sisältyvät järjestelmäkehotteeseen ja että jokainen tuloste validoidaan automaattisesti; vääränmuotoiset tulosteet aiheuttavat korjauksen tai hylkäyksen. |   1   | D/V  |
| 7.1.2 | Varmista, että rajoitettu dekoodaus (pysäytystunnisteet, säännölliset lausekkeet, maksimi-tokenit) on käytössä ylivuodon tai kehotteen injektointia sisältävien sivukanavien estämiseksi.                      |   1   | D/V  |
| 7.1.3 | Varmista, että alemmat komponenteet käsittelevät lähtötiedot epäluotettavina ja validoivat ne skeemojen tai injektioilta suojaavien deserialisoijien avulla.                                                   |   2   | D/V  |
| 7.1.4 | Varmista, että virheelliset tulostustapahtumat kirjataan, niiden määrä rajoitetaan ja ne näkyvät valvonnassa.                                                                                                  |   3   |  V   |

---

## C7.2 Harhan tunnistaminen ja lieventäminen

Epävarmuuden arviointi ja varatoimenpiteet rajoittavat tekaistuja vastauksia.

|   #   | Description                                                                                                                                                                                 | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 7.2.1 | Varmista, että token-tason log-todennäköisyydet, joukkoyhteenkuuluvuus itsevarmuusmenetelmässä tai hienosäädetyt harhallisuuden tunnistimet antavat luottamusarvon jokaiselle vastaukselle. |   1   | D/V  |
| 7.2.2 | Varmista, että vastaukset, joiden luottamustaso on alle määriteltävän kynnyksen, laukaisevat varajärjestelmät (esim. hakua lisätty generointi, toissijainen malli tai ihmistarkastus).      |   1   | D/V  |
| 7.2.3 | Varmista, että hallusinaatiotapaukset on merkitty juurisyy-metatiedoilla ja syötetty jälkiarviointi- ja hienosäätöputkiin.                                                                  |   2   | D/V  |
| 7.2.4 | Varmista, että kynnysarvot ja ilmaisimet kalibroidaan uudelleen merkittävien mallin tai tietopohjan päivitysten jälkeen.                                                                    |   3   | D/V  |
| 7.2.5 | Varmista, että kojelaudan visualisoinnit seuraavat hallusinaatiotasoja.                                                                                                                     |   3   |  V   |

---

## C7.3 Tulosteen turvallisuus- ja yksityisyydensuodatus

Politiikkasuodattimet ja red-team-tarkastus suojaavat käyttäjiä ja luottamuksellisia tietoja.

|   #   | Description                                                                                                                                                                                                   | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 7.3.1 | Varmista, että esigenerointi- ja jälkigenerointiluokittimet estävät vihapuheen, häirinnän, itsetuhoisuuden, ääriliikkeiden ja seksuaalisesti eksplisiittisen sisällön, jotka ovat linjassa politiikan kanssa. |   1   | D/V  |
| 7.3.2 | Varmista, että PII/PCI-tunnistus ja automaattinen peittäminen suoritetaan jokaisessa vastauksessa; rikkomukset johtavat tietosuojaloukkausilmoitukseen.                                                       |   1   | D/V  |
| 7.3.3 | Varmista, että luottamuksellisuustunnisteet (esim. liikesalaisuudet) leviävät eri muotojen välillä estäen vuotoja tekstissä, kuvissa tai koodissa.                                                            |   2   |  D   |
| 7.3.4 | Varmista, että suodattimen ohitusyritykset tai korkean riskin luokitukset vaativat toissijaisen hyväksynnän tai käyttäjän uudelleenautentikoinnin.                                                            |   3   | D/V  |
| 7.3.5 | Varmista, että suodatuskynnysarvot heijastavat laillisia toimivalta-alueita sekä käyttäjän ikä/roolikontekstia.                                                                                               |   3   | D/V  |

---

## C7.4 Tulosteen ja toimien rajoittaminen

Nopeusrajoitukset ja hyväksymisportit estävät väärinkäytökset ja liiallisen autonomian.

|   #   | Description                                                                                                                                                                                   | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 7.4.1 | Varmista, että käyttäjäkohtaiset ja API-avaimenkohtaiset kiintiöt rajoittavat pyyntöjä, tokeneita ja kustannuksia eksponentiaalisen takaisinperuutuksen avulla 429-virheissä.                 |   1   |  D   |
| 7.4.2 | Varmista, että etuoikeutetut toiminnot (tiedostojen kirjoitus, koodin suoritus, verkkopyynnöt) vaativat politiikanmukaista hyväksyntää tai ihmisen hyväksynnän prosessissa.                   |   1   | D/V  |
| 7.4.3 | Varmista, että ristiinmodaliteettinen johdonmukaisuuden tarkistus takaa, ettei saman pyynnön perusteella luotua kuvaa, koodia ja tekstiä voi käyttää haitallisen sisällön salakuljettamiseen. |   2   | D/V  |
| 7.4.4 | Varmista, että agentin valtuutuksen syvyys, rekursion rajat ja sallitut työkaluluettelot on määritelty selvästi.                                                                              |   2   |  D   |
| 7.4.5 | Varmista, että rajojen ylityksestä syntyy jäsenneltyjä turvallisuustapahtumia SIEM-järjestelmän keräystä varten.                                                                              |   3   |  V   |

---

## C7.5 Tulosteen selitettävyys

Läpinäkyvät signaalit parantavat käyttäjien luottamusta ja sisäistä vianetsintää.

|   #   | Description                                                                                                                                   | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 7.5.1 | Varmista, että käyttäjälle näkyvät luottamuspisteet tai lyhyet perusteluyhteenvedot näytetään, kun riskinarviointi katsoo sen sopivaksi.      |   2   | D/V  |
| 7.5.2 | Varmista, että tuotetut selitykset eivät paljasta arkaluonteisia järjestelmäkehotteita tai omistusoikeudellisia tietoja.                      |   2   | D/V  |
| 7.5.3 | Varmista, että järjestelmä tallentaa token-tason lok todennäköisyydet tai attentio-matriisit ja säilyttää ne valtuutettua tarkastusta varten. |   3   |  D   |
| 7.5.4 | Varmista, että selitettävyysartefaktit ovat versiohallinnassa mallijulkaisujen yhteydessä tarkastettavuutta varten.                           |   3   |  V   |

---

## C7.6 Valvonnan integrointi

Reaaliaikainen havaittavuus sulkee silmukan kehityksen ja tuotannon välillä.

|   #   | Description                                                                                                                                                   | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 7.6.1 | Varmista, että mittarit (skeeman rikkomiset, hallusinaatiotaso, toksisuus, henkilötietovuodot, viive, kustannukset) siirtyvät keskitettyyn valvonta-alustaan. |   1   |  D   |
| 7.6.2 | Varmista, että kullekin turvallisuusmittarille on määritelty hälytysrajat, ja että on olemassa päivystyskorotushakemistot.                                    |   1   |  V   |
| 7.6.3 | Varmista, että kojelaudat yhdistävät poikkeavuudet mallin/versioiden, ominaisuuksien kytkimen ja ylävirran datamuutosten kanssa.                              |   2   |  V   |
| 7.6.4 | Varmista, että valvontatiedot palautuvat uudelleenkoulutukseen, hienosäätöön tai sääntöpäivityksiin dokumentoidun MLOps-työnkulun puitteissa.                 |   2   | D/V  |
| 7.6.5 | Varmista, että seurantaputkistot on testattu tunkeutumisen varalta ja niihin on pääsyrajoitukset, jotta arkaluontoisten lokitietojen vuotaminen estyy.        |   3   |  V   |

---

## 7.7 Generatiivisen median suojatoimet

Varmista, että tekoälyjärjestelmät eivät tuota laittomia, haitallisia tai luvattomia mediasisältöjä noudattamalla politiikkarajoituksia, tekemällä tulosten validointia ja varmistamalla jäljitettävyys.

|   #   | Description                                                                                                                                                                                            | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 7.7.1 | Varmista, että järjestelmän kehotteet ja käyttäjän ohjeet kieltävät nimenomaisesti laittomien, haitallisten tai ei-suostumuksellisten deepfake-materiaalien (esim. kuvat, videot, äänet) tuottamisen.  |   1   | D/V  |
| 7.7.2 | Varmista, että kehotteet suodatetaan yrityksiltä luoda jäljitelmiä, seksuaalisesti eksplisiittisiä deepfake-videoita tai materiaalia, joka kuvaa todellisia henkilöitä ilman suostumusta.              |   2   | D/V  |
| 7.7.3 | Varmista, että järjestelmä käyttää havaintopohjaista hajautusta, vesileiman tunnistusta tai sormenjälkitunnistusta estääkseen tekijänoikeudella suojatun median luvattoman kopioinnin.                 |   2   |  V   |
| 7.7.4 | Varmista, että kaikki luotu media on kryptografisesti allekirjoitettu, vesileimattu tai varustettu muokkausta kestävillä alkuperäisyystiedoilla jäljitettävyyttä varten.                               |   3   | D/V  |
| 7.7.5 | Varmista, että ohitusyritykset (esim. kehotteen peittely, slangin käyttö, vihamielinen ilmaisutapa) tunnistetaan, kirjataan ja rajoitetaan; toistuva väärinkäyttö raportoidaan valvontajärjestelmille. |   3   |  V   |

## Viitteet

* [NIST AI Risk Management Framework](https://www.nist.gov/itl/ai-risk-management-framework)
* [ISO/IEC 42001:2023 – AI Management System](https://www.iso.org/obp/ui/en/)
* [OWASP Top-10 for Large Language Model Applications (2025)](https://owasp.org/www-project-top-10-for-large-language-model-applications/)
* [Improper Output Handling – OWASP LLM05:2025](https://genai.owasp.org/llmrisk/llm052025-improper-output-handling/)
* [Practical Techniques to Constrain LLM Output](https://mychen76.medium.com/practical-techniques-to-constraint-llm-output-in-json-format-e3e72396c670)
* [Dataiku – Structured Text Generation Guide](https://blog.dataiku.com/your-guide-to-structured-text-generation)
* [VL-Uncertainty: Detecting Hallucinations](https://arxiv.org/abs/2411.11919)
* [HaDeMiF: Hallucination Detection & Mitigation](https://openreview.net/forum?id=VwOYxPScxB)
* [Building Confidence in LLM Outputs](https://www.alkymi.io/data-science-room/building-confidence-in-llm-outputs)
* [Explainable AI & LLMs](https://duncsand.medium.com/explainable-ai-140912d31b3b)
* [LLM Red-Teaming Guide](https://www.confident-ai.com/blog/red-teaming-llms-a-step-by-step-guide)
* [Sensitive Information Disclosure in LLMs](https://virtualcyberlabs.com/llm-sensitive-information-disclosure/)
* [LangChain – Chat Model Rate Limiting](https://python.langchain.com/docs/how_to/chat_model_rate_limiting/)
* [OpenAI Rate-Limit & Exponential Back-off](https://hackernoon.com/openais-rate-limit-a-guide-to-exponential-backoff-for-llm-evaluation)
* [Arize AI – LLM Observability Platform](https://arize.com/)

