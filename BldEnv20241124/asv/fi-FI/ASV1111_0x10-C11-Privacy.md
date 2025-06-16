# 11 Tietosuoja ja henkilötietojen hallinta

## Kontrollitavoite

Ylläpidä tiukkoja yksityisyystakuita koko tekoälyn elinkaaren ajan—keräämisen, koulutuksen, päättelyn ja häiriötilanteisiin reagoinnin aikana—jotta henkilötietoja käsitellään vain selkeällä suostumuksella, tarvittavimmassa laajuudessa, todennettavissa olevalla poistolla ja muodollisilla yksityisyystakuuilla.

---

## 11.1 Anonymisointi ja datan minimointi

|   #    | Description                                                                                                                                                     | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 11.1.1 | Varmista, että suorat ja kvasi-tunnisteet poistetaan tai hajautetaan.                                                                                           |   1   | D/V  |
| 11.1.2 | Varmista, että automaattiset tarkastukset mittaavat k-anonymiteettiä/l-monimuotoisuutta ja antavat hälytyksen, kun kynnysarvot laskevat politiikan alapuolelle. |   2   | D/V  |
| 11.1.3 | Varmista, että mallin ominaisuuksien tärkeysraportit osoittavat, ettei tunnistevuotoa esiinny yli ε = 0,01 keskinäisen informaation.                            |   2   |  V   |
| 11.1.4 | Varmista, että muodolliset todistukset tai synteettisen datan sertifiointi osoittavat uudelleentunnistamisriskin olevan ≤ 0,05 jopa linkitysiskujen aikana.     |   3   |  V   |

---

## 11.2 Oikeus tulla unohdetuksi ja poistamisen täytäntöönpano

|   #    | Description                                                                                                                                                                                    | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 11.2.1 | Varmista, että henkilötietojen poistopyynnöt leviävät raakadatakokoelmiin, tarkistuspisteisiin, upotuksiin, lokitietoihin ja varmuuskopioihin alle 30 päivän palvelutasosopimuksen puitteissa. |   1   | D/V  |
| 11.2.2 | Varmista, että "koneoppimisen unohtaminen" -rutiinit fyysisesti uudelleenkouluttavat tai lähestyvät poistoa sertifioiduilla unohtamisen algoritmeilla.                                         |   2   |  D   |
| 11.2.3 | Varmista, että varjomallin arviointi todistaa unohdettujen tietueiden vaikuttavan alle 1 % tuloksista unohdettamisen jälkeen.                                                                  |   2   |  V   |
| 11.2.4 | Varmista, että poistotapahtumat kirjataan muuttumattomasti ja ovat auditoitavissa sääntelyviranomaisille.                                                                                      |   3   |  V   |

---

## 11.3 Diferentiaalisen yksityisyyden turvatoimet

|   #    | Description                                                                                                               | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 11.3.1 | Varmista, että yksityisyyden menetyslaskentapaneelit hälyttävät, kun kumulatiivinen ε ylittää politiikan asettamat rajat. |   2   | D/V  |
| 11.3.2 | Varmista, että mustan laatikon tietosuojatarkastukset arvioivat ε̂:n enintään 10 %:n tarkkuudella ilmoitetusta arvosta.   |   2   |  V   |
| 11.3.3 | Varmista, että muodolliset todistukset kattavat kaikki jälkikoulutuksen hienosäädöt ja upotukset.                         |   3   |  V   |

---

## 11.4 Tarkoituksen rajoittaminen ja laajuuden hallinta

|   #    | Description                                                                                                                                                          | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 11.4.1 | Varmista, että jokaisessa tietojoukossa ja mallin tarkistuspisteessä on koneellisesti luettava käyttötarkoitustunniste, joka vastaa alkuperäistä suostumusta.        |   1   |  D   |
| 11.4.2 | Varmista, että suoritusajan valvontajärjestelmät havaitsevat kyselyt, jotka ovat ristiriidassa ilmoitetun tarkoituksen kanssa, ja laukaisevat kevyen kieltäytymisen. |   1   | D/V  |
| 11.4.3 | Varmista, että politiikka-koodina -portit estävät mallien uudelleenkäytön uusille toimialueille ilman DPIA-tarkastelua.                                              |   3   |  D   |
| 11.4.4 | Varmista, että muodolliset jäljitettävyystodistukset osoittavat, että jokainen henkilötietojen elinkaaren vaihe pysyy suostumuksen mukaisessa laajuudessa.           |   3   |  V   |

---

## 11.5 Suostumuksen hallinta ja laillisen perusteen seuranta

|   #    | Description                                                                                                                                     | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 11.5.1 | Varmista, että suostumuksenhallintajärjestelmä (CMP) tallentaa kunkin rekisteröidyn osapuolen valintatilan, käyttötarkoituksen ja säilytysajan. |   1   | D/V  |
| 11.5.2 | Varmista, että API:t paljastavat suostumustunnukset; mallien on validoitava tunnuksen käyttöoikeus ennen päättelyä.                             |   2   |  D   |
| 11.5.3 | Varmista, että evätty tai peruutettu suostumus pysäyttää käsittelyputket 24 tunnin kuluessa.                                                    |   2   | D/V  |

---

## 11.6 Federatiivinen oppiminen yksityisyydensuojan hallinnalla

|   #    | Description                                                                                                                  | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 11.6.1 | Varmista, että asiakas päivitykset käyttävät paikallisen differentiaalisen yksityisyyden melun lisäystä ennen yhdistämistä.  |   1   |  D   |
| 11.6.2 | Varmista, että koulutusmittarit ovat differentiaalisesti yksityisiä eivätkä koskaan paljasta yksittäisen asiakkaan tappiota. |   2   | D/V  |
| 11.6.3 | Varmista, että myrkytyskestävä yhdistely (esim. Krum/Trimmed-Mean) on käytössä.                                              |   2   |  V   |
| 11.6.4 | Varmista, että muodolliset todistukset osoittavat kokonais-ε-budjetin, jossa hyötymenetys on alle 5.                         |   3   |  V   |

---

### Viitteet

* [GDPR & AI Compliance Best Practices](https://www.exabeam.com/explainers/gdpr-compliance/the-intersection-of-gdpr-and-ai-and-6-compliance-best-practices/)
* [EU Parliament Study on GDPR & AI, 2020](https://www.europarl.europa.eu/RegData/etudes/STUD/2020/641530/EPRS_STU%282020%29641530_EN.pdf)
* [ISO 31700-1:2023 — Privacy by Design for Consumer Products](https://www.iso.org/standard/84977.html)
* [NIST Privacy Framework 1.1 (2025 Draft)](https://www.nist.gov/privacy-framework)
* [Machine Unlearning: Right-to-Be-Forgotten Techniques](https://www.kaggle.com/code/tamlhp/machine-unlearning-the-right-to-be-forgotten)
* [A Survey of Machine Unlearning, 2024](https://arxiv.org/html/2209.02299v6)
* [Auditing DP-SGD — ArXiv 2024](https://arxiv.org/html/2405.14106v4)
* [DP-SGD Explained — PyTorch Blog](https://medium.com/pytorch/differential-privacy-series-part-1-dp-sgd-algorithm-explained-12512c3959a3)
* [Purpose-Limitation for AI — IJLIT 2025](https://academic.oup.com/ijlit/article/doi/10.1093/ijlit/eaaf003/8121663)
* [Data-Protection Considerations for AI — URM Consulting](https://www.urmconsulting.com/blog/data-protection-considerations-for-artificial-intelligence-ai)
* [Top Consent-Management Platforms, 2025](https://www.enzuzo.com/blog/best-consent-management-platforms)
* [Secure Aggregation in DP Federated Learning — ArXiv 2024](https://arxiv.org/abs/2407.19286)

