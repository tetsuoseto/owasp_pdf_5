# Liite D: AI-avusteinen turvallisen koodauksen hallinta ja varmennus

## Tavoite

Tämä luku määrittelee perustason organisatoriset hallintakeinot AI-avusteisten ohjelmointityökalujen turvalliseen ja tehokkaaseen käyttöön ohjelmistokehityksen aikana, varmistaen turvallisuuden ja jäljitettävyyden koko ohjelmistokehityksen elinkaaren (SDLC) ajan.

---

## AD.1 AI-avusteinen turvallisen koodauksen työnkulku

Integroi tekoälytyökalut organisaation turvallisen ohjelmistokehityksen elinkaaren (SSDLC) prosessiin heikentämättä olemassa olevia turvallisuusportteja.

|   #    | Description                                                                                                                                                                            | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| AD.1.1 | Varmista, että dokumentoitu työnkulku kuvaa, milloin ja miten tekoälytyökaluja voidaan käyttää koodin generointiin, refaktorointiin tai tarkistamiseen.                                |   1   | D/V  |
| AD.1.2 | Varmista, että työnkulku vastaa jokaista SSDLC-vaihetta (suunnittelu, toteutus, koodikatselmointi, testaus, käyttöönotto).                                                             |   2   |  D   |
| AD.1.3 | Varmista, että mittareita (esim. haavoittuvuustiheys, keskimääräinen havaitsemisaika) kerätään tekoälyn tuottamasta koodista ja verrataan ihmisen ainoastaan tuottamiin lähtötasoihin. |   3   | D/V  |

---

## AD.2 AI-työkalun kelpoisuus ja uhkamallinnus

Varmista, että tekoälykoodausvälineet arvioidaan turvallisuusominaisuuksien, riskien ja toimitusketjun vaikutusten osalta ennen käyttöönottoa.

|   #    | Description                                                                                                                                                                                | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| AD.2.1 | Varmista, että jokaisen tekoälytyökalun uhkamalli tunnistaa väärinkäytön, mallin käänteisen hyödyntämisen, tietovuodot ja riippuvuusketjun riskit.                                         |   1   | D/V  |
| AD.2.2 | Varmista, että työkalujen arvioinnit sisältävät paikallisten komponenttien staattisen/dynaamisen analyysin sekä SaaS-päätepisteiden (TLS, tunnistautuminen/valtuutus, lokitus) arvioinnin. |   2   |  D   |
| AD.2.3 | Varmista, että arvioinnit noudattavat tunnustettua viitekehystä ja suoritetaan uudelleen merkittävien versiopäivitysten jälkeen.                                                           |   3   | D/V  |

---

## AD.3 Turvallinen kehotteiden ja kontekstinhallinta

Estä salaisuuksien, omistusoikeudellisen koodin ja henkilökohtaisten tietojen vuotaminen AI-mallien kehotteita tai konteksteja rakennettaessa.

|   #    | Description                                                                                                                                               | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| AD.3.1 | Varmista, että kirjallinen ohjeistus kieltää salaisuuksien, tunnistetietojen tai luokitellun datan lähettämisen kehotteissa.                              |   1   | D/V  |
| AD.3.2 | Varmista, että tekniset ohjausmenetelmät (asiakaspuolen peittäminen, hyväksytyt kontekstisuodattimet) poistavat automaattisesti arkaluonteiset tiedot.    |   2   |  D   |
| AD.3.3 | Varmista, että kehote- ja vastaustiedot tokenisoidaan, salataan siirron aikana ja levossa, ja että säilytysaikojen tiedonluokituspolitiikkaa noudatetaan. |   3   | D/V  |

---

## AD.4 AI-Generoidun Koodin Vahvistaminen

Havaitse ja korjaa tekoälyn tuottamien tulosten aiheuttamat haavoittuvuudet ennen kuin koodi yhdistetään tai julkaistaan.

|   #    | Description                                                                                                                                                                       | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| AD.4.1 | Varmista, että tekoälyn generoima koodi käy aina läpi ihmisen tekemän koodikatselmoinnin.                                                                                         |   1   | D/V  |
| AD.4.2 | Varmista, että automatisoidut skannerit (SAST/IAST/DAST) suoritetaan kaikissa AI-generoitua koodia sisältävissä vetopyynnöissä ja estä yhdistämiset kriittisissä löydöksissä.     |   2   |  D   |
| AD.4.3 | Varmista, että differentiaalinen fuzz-testaus tai ominaisuuspohjaiset testit todistavat turvallisuuskriittiset käyttäytymismallit (esim. syötteen validointi, valtuutuslogiikka). |   3   | D/V  |

---

## AD.5 Koodiehdotusten selitettävyys ja jäljitettävyys

Tarjoa tarkastajille ja kehittäjille ymmärrystä siitä, miksi ehdotus tehtiin ja miten se kehittyi.

|   #    | Description                                                                                                                                                               | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| AD.5.1 | Varmista, että kehotteet/vastausparit kirjataan sitoutumisen tunnisteilla.                                                                                                |   1   | D/V  |
| AD.5.2 | Varmista, että kehittäjät voivat näyttää malliviitteitä (koulutusnäytteitä, dokumentaatiota) ehdotuksen tukemiseksi.                                                      |   2   |  D   |
| AD.5.3 | Varmista, että selitettävyysraportit tallennetaan suunnitteluaineistojen kanssa ja viitataan turvallisuuskatselmuksissa, täyttäen ISO/IEC 42001 -jäljityksen periaatteet. |   3   | D/V  |

---

## AD.6 Jatkuva palaute ja mallin hienosäätö

Paranna mallin turvallisuussuorituskykyä ajan myötä samalla kun estät negatiivisen siirtymän.

|   #    | Description                                                                                                                                                                                             | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| AD.6.1 | Varmista, että kehittäjät voivat merkitä epävarmat tai ei-yhteensopivat ehdotukset ja että merkinnät seurataan.                                                                                         |   1   | D/V  |
| AD.6.2 | Varmista, että koottu palaute ohjaa säännöllistä hienosäätöä tai hakua tehostettua generointia varmennetuilla tietoturvallisen koodauksen aineistoilla (esim. OWASP Cheat Sheets).                      |   2   |  D   |
| AD.6.3 | Varmista, että suljetun silmukan arviointikehys suorittaa regressiotestit jokaisen hienosäädön jälkeen; turvallisuusmittareiden on täytettävä tai ylitettävä aiemmat vertailuarvot ennen käyttöönottoa. |   3   | D/V  |

---

### Viitteet

* [NIST AI Risk Management Framework 1.0](https://nvlpubs.nist.gov/nistpubs/ai/nist.ai.100-1.pdf)
* [ISO/IEC 42001:2023 — AI Management Systems Requirements](https://www.iso.org/standard/81230.html)
* [OWASP Secure Coding Practices — Quick Reference Guide](https://owasp.org/www-project-secure-coding-practices-quick-reference-guide/)

