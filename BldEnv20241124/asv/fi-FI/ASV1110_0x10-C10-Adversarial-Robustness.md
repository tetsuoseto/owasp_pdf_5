# 10 Vihamielinen kestävyys ja yksityisyyden suojaaminen

## Ohjaustavoite

Varmista, että tekoälymallit pysyvät luotettavina, yksityisyyttä suojaavina ja väärinkäytöksiltä suojattuina vastustaessaan kiertämis-, päättely-, poiminta- tai myrkytyshyökkäyksiä.

---

## 10.1 Mallin sovitus ja turvallisuus

Suojaa haitallisilta tai politiikkaa rikkovilta tulosteilta.

|   #    | Description                                                                                                                                                                       | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 10.1.1 | Varmista, että yhdenmukaisuuden testikokoelma (red-team-kehotteet, jailbreak-kyselyt, kielletty sisältö) on versionhallinnassa ja suoritetaan jokaisen mallijulkaisun yhteydessä. |   1   | D/V  |
| 10.1.2 | Varmista, että kieltäytymisen ja turvallisen suorituksen suojakehykset ovat voimassa.                                                                                             |   1   |  D   |
| 10.1.3 | Varmista, että automatisoitu arvostelija mittaa haitallisen sisällön määrää ja merkitsee uudelleenlaskennat, jotka ylittävät asetetun kynnyksen.                                  |   2   | D/V  |
| 10.1.4 | Varmista, että vastamurtokoulutus on dokumentoitu ja toistettavissa.                                                                                                              |   2   |  D   |
| 10.1.5 | Varmista, että muodolliset politiikanmukaisuuden todisteet tai sertifioitu valvonta kattavat kriittiset alueet.                                                                   |   3   |  V   |

---

## 10.2 Vastustavien esimerkkien vahvistaminen

Lisää vastustuskykyä manipuloiduille syötteille. Vahva vastustajapohjainen koulutus ja vertailuarviointi ovat nykyiset parhaat käytännöt.

|   #    | Description                                                                                                                            | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 10.2.1 | Varmista, että projektivarastoissa on vihamielisen koulutuksen asetukset toistettavilla siemenarvoilla.                                |   1   |  D   |
| 10.2.2 | Varmista, että vihamielisten esimerkkien tunnistus laukaisee estohälytykset tuotantoputkissa.                                          |   2   | D/V  |
| 10.2.4 | Varmista, että sertifioidut kestävyyden todistukset tai väliarvorajat kattavat vähintään tärkeimmät kriittiset luokat.                 |   3   |  V   |
| 10.2.5 | Varmista, että regressiotestit käyttävät adaptiivisia hyökkäyksiä vahvistaakseen, ettei havaittavissa ole suorituskyvyn heikkenemistä. |   3   |  V   |

---

## 10.3 Kuuluvuuden päättelyn lieventäminen

Rajoita kykyä päättää, oliko tietue harjoitusdatassa. Differentiaalinen yksityisyys ja luottamusarvon peittäminen ovat edelleen tehokkaimmat tunnetut suojakeinot.

|   #    | Description                                                                                                                                   | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 10.3.1 | Varmista, että kyselykohtainen entropian säännöstely tai lämpötilan skaalaus vähentää yliluottavaisia ennusteita.                             |   1   |  D   |
| 10.3.2 | Varmista, että harjoittelu käyttää ε-rajoitettua differentiaalista yksityisyyttä hyödyntävää optimointia arkaluonteisille tietoaineistoille.  |   2   |  D   |
| 10.3.3 | Varmista, että hyökkäyssimulaatiot (varjomalli tai mustan laatikon menetelmä) näyttävät hyökkäyksen AUC ≤ 0,60 erikseen pidetyissä testeissä. |   2   |  V   |

---

## 10.4 Mallin kääntövastus

Estä yksityisten attribuuttien uudelleenrakentaminen. Viimeaikaiset tutkimukset korostavat tuloksen katkaisua ja differentiaalisen yksityisyyden (DP) takuita käytännöllisinä suojakeinoina.

|   #    | Description                                                                                                                         | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 10.4.1 | Varmista, että arkaluonteisia attribuutteja ei koskaan suoraan tulosteta; tarvittaessa käytä luokkia tai yksisuuntaisia muunnoksia. |   1   |  D   |
| 10.4.2 | Varmista, että kyselynopeusrajoitukset hillitsevät toistuvia adaptiivisia kyselyjä samalta taholta.                                 |   1   | D/V  |
| 10.4.3 | Varmista, että malli on koulutettu yksityisyyttä suojaavalla häiriöllä.                                                             |   2   |  D   |

---

## 10.5 Mallin uuttamisen torjunta

Havaitse ja estä luvaton kloonaus. Suositellaan vesileimausta ja kyselykuvion analyysiä.

|   #    | Description                                                                                                                                                   | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 10.5.1 | Varmista, että inferenssisillat toteuttavat globaaleja ja API-avainkohtaisia käyttötaajuusrajoituksia, jotka on säädetty mallin muistamisen kynnyksen mukaan. |   1   |  D   |
| 10.5.2 | Varmista, että kysely-entropia- ja syöte-monimuotoisuusstatistiikat syöttävät automaattisen poiminnan tunnistimen.                                            |   2   | D/V  |
| 10.5.3 | Varmista, että hauraita tai todennäköisyyspohjaisia vesileimoja voidaan todistaa p-arvolla < 0,01 enintään 1 000 kyselyllä epäillyn kloonin kohdalla.         |   2   |  V   |
| 10.5.4 | Varmista, että vesileimain avaimet ja laukaisuvarmistukset tallennetaan laitteistoturvamoduuliin ja vaihdetaan vuosittain.                                    |   3   |  D   |
| 10.5.5 | Varmista, että poiminta-hälytys tapahtumat sisältävät rikkomukseen johtavat kyselyt ja on integroitu tapausvastauksen toimintasuunnitelmiin.                  |   3   |  V   |

---

## 10.6 Inferenssiajan myrkytetyn datan tunnistus

Tunnista ja neutralisoi takaportilla tai myrkyllä manipuloidut syötteet.

|   #    | Description                                                                                                                                              | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 10.6.1 | Varmista, että syötteet kulkevat poikkeavuustunnistimen (esim. STRIP, konsistenssipisteytys) kautta ennen mallin päätelmää.                              |   1   |  D   |
| 10.6.2 | Varmista, että havaitsemiskynnykset on säädetty puhtailla/myrkyllisillä vahvistusjoukoilla siten, että virheellisiä positiivisia ilmoituksia on alle 5%. |   1   |  V   |
| 10.6.3 | Varmista, että myrkyllisiksi merkityt syötteet laukaisevat pehmeän eston ja ihmisen tarkastusprosessit.                                                  |   2   |  D   |
| 10.6.4 | Varmista, että detektorit altistetaan kuormitustestaukselle adaptiivisilla ilman laukaistinta toimivilla takaoven hyökkäyksillä.                         |   2   |  V   |
| 10.6.5 | Varmista, että tunnistustehokkuuden mittarit kirjataan ja arvioidaan uudelleen säännöllisesti uusilla uhkatiedoilla.                                     |   3   |  D   |

---

## 10.7 Dynaaminen turvallisuuspolitiikan mukauttaminen

Reaaliaikaiset tietoturvapolitiikan päivitykset uhkatiedon ja käyttäytymisanalyysin perusteella.

|   #    | Description                                                                                                                                               | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 10.7.1 | Varmista, että tietoturvakäytäntöjä voidaan päivittää dynaamisesti ilman agentin uudelleenkäynnistystä samalla, kun varmistetaan käytäntöversion eheys.   |   1   | D/V  |
| 10.7.2 | Varmista, että politiikkapäivitykset on kryptografisesti allekirjoitettu valtuutettujen turvallisuushenkilöiden toimesta ja validoitu ennen soveltamista. |   2   | D/V  |
| 10.7.3 | Varmista, että dynaamiset politiikkamuutokset kirjataan täydellisin tarkastuslokein, jotka sisältävät perustelut, hyväksymisketjut ja palautusmenettelyt. |   2   | D/V  |
| 10.7.4 | Varmista, että adaptiiviset tietoturvamekanismit säätelevät uhkien havaitsemisen herkkyyttä riskikontekstin ja käyttäytymismallien perusteella.           |   3   | D/V  |
| 10.7.5 | Varmista, että politiikan mukauttamispäätökset ovat selitettäviä ja sisältävät todistepolut turvallisuusryhmän tarkastelua varten.                        |   3   | D/V  |

---

## 10.8 Heijastusperusteinen turvallisuusanalyysi

Turvallisuuden validointi agentin itsearvioinnin ja metakognitiivisen analyysin kautta.

|   #    | Description                                                                                                                                                | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 10.8.1 | Varmista, että agentin reflektiojärjestelmät sisältävät turvallisuuteen keskittyvän itsearvioinnin päätöksistä ja toimista.                                |   1   | D/V  |
| 10.8.2 | Varmista, että heijastusten tulokset validoidaan estämään itsearviointimekanismien manipulointi vihamielisillä syötteillä.                                 |   2   | D/V  |
| 10.8.3 | Varmista, että metakognitiivinen turvallisuusanalyysi tunnistaa mahdollisen puolueellisuuden, manipuloinnin tai väärinkäytön agentin päättelyprosesseissa. |   2   | D/V  |
| 10.8.4 | Varmista, että heijastusperusteiset turvallisuusvaroitukset laukaisevat tehostetun valvonnan ja mahdolliset ihmisen väliintulon työnkulut.                 |   3   | D/V  |
| 10.8.5 | Varmista, että jatkuva oppiminen turvallisuusreflektioista parantaa uhkien havaitsemista vaarantamatta laillista toimintaa.                                |   3   | D/V  |

---

## 10.9 Evoluutio ja itseparannuksen turvallisuus

Turvallisuusvalvontatoimet itsensä muokkaamiseen ja kehittymiseen kykeneville agenttijärjestelmille.

|   #    | Description                                                                                                                                 | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 10.9.1 | Varmista, että itse-modifikaatiokykyjä rajoitetaan nimetyille turvallisille alueille muodollisten varmennusrajojen puitteissa.              |   1   | D/V  |
| 10.9.2 | Varmista, että evoluutiosehdotukset käyvät läpi turvallisuusvaikutusten arvioinnin ennen käyttöönottoa.                                     |   2   | D/V  |
| 10.9.3 | Varmista, että itseparannusmekanismit sisältävät paluuominaisuudet ja eheyden tarkistuksen.                                                 |   2   | D/V  |
| 10.9.4 | Varmista, että metaoppimisen tietoturva estää parannusalgoritmien vihamielisen manipuloinnin.                                               |   3   | D/V  |
| 10.9.5 | Varmista, että rekursiivinen itseparantaminen on rajattu muodollisilla turvallisuusrajoitteilla matemaattisilla todisteilla suppenemisesta. |   3   | D/V  |

---

### Viitteet

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

