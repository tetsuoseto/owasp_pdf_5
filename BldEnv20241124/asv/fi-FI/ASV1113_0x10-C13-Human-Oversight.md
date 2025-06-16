# C13 Ihmisen valvonta, vastuu ja hallinnointi

## Ohjaustavoite

Tämä luku sisältää vaatimukset ihmisen valvonnan ja selkeiden vastuuketjujen ylläpitämiseksi tekoälyjärjestelmissä, varmistaen selitettävyyden, läpinäkyvyyden ja eettisen hallinnoinnin tekoälyn koko elinkaaren ajan.

---

## C13.1 Hätäpysäytys- ja Ylikirjoitusmekanismit

Tarjoa sammutus- tai palautusreitit, kun tekoälyjärjestelmän vaarallista käyttäytymistä havaitaan.

|   #    | Description                                                                                                                           | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 13.1.1 | Varmista, että käsikäyttöinen hätäpysäytystoiminto on olemassa tekoälymallin päätelmän ja tulosteiden välitöntä pysäyttämistä varten. |   1   | D/V  |
| 13.1.2 | Varmista, että ohitusvalvontatoiminnot ovat käytettävissä vain valtuutetulle henkilöstölle.                                           |   1   |  D   |
| 13.1.3 | Varmista, että palautusmenettelyt voivat palauttaa aiemmat malliversiot tai toimivat turvallisuustilassa.                             |   3   | D/V  |
| 13.1.4 | Varmista, että ohitusmekanismit testataan säännöllisesti.                                                                             |   3   |  V   |

---

## C13.2 Ihmisen osallisuus päätöksenteon tarkistuspisteissä

Vaatikaa ihmisen hyväksyntä, kun panokset ylittävät ennalta määritellyt riskirajat.

|   #    | Description                                                                                                                              | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 13.2.1 | Varmista, että korkean riskin tekoälypäätökset vaativat nimenomaisen ihmisen hyväksynnän ennen toteutusta.                               |   1   | D/V  |
| 13.2.2 | Varmista, että riskirajat on määritelty selkeästi ja ne laukaisevat automaattisesti ihmisen tarkastusprosessit.                          |   1   |  D   |
| 13.2.3 | Varmista, että aikakriittisillä päätöksillä on varajärjestelyt siltä varalta, että ihmisen hyväksyntää ei saada vaaditussa aikarajassa.  |   2   |  D   |
| 13.2.4 | Varmista, että eskalaatioproseduureissa määritellään selkeät valtuustasot eri päätöstyypeille tai riskiluokille, mikäli sovellettavissa. |   3   | D/V  |

---

## C13.3 Vastuun ketju ja auditointimahdollisuus

Kirjaa operaattorin toiminnot ja mallin päätökset.

|   #    | Description                                                                                                                                                        | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 13.3.1 | Varmista, että kaikki tekoälyjärjestelmän päätökset ja ihmisen tekemät toimenpiteet kirjataan ajoitusleimojen, käyttäjätunnusten ja päätöksen perustelujen kanssa. |   1   | D/V  |
| 13.3.2 | Varmista, että tarkastuslokeihin ei voi tehdä muutoksia ja että ne sisältävät eheystarkistusmekanismeja.                                                           |   2   |  D   |

---

## C13.4 Selitettävät tekoälytekniikat

Pintapuolen ominaisuuksien tärkeys, vastin-tapaukset ja paikalliset selitykset.

|   #    | Description                                                                                                                                                                   | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 13.4.1 | Varmista, että tekoälyjärjestelmät tarjoavat päätöksistään perustavanlaatuiset selitykset ihmisen luettavassa muodossa.                                                       |   1   | D/V  |
| 13.4.2 | Varmista, että selityksen laatu on validoitu ihmisten tekemillä arviointitutkimuksilla ja mittareilla.                                                                        |   2   |  V   |
| 13.4.3 | Varmista, että kriittisille päätöksille on saatavilla ominaisuuksien tärkeyspisteet tai attribuutiomenetelmät (kuten SHAP, LIME jne.).                                        |   3   | D/V  |
| 13.4.4 | Varmista, että kontrafaktuaaliset selitykset osoittavat, miten syötteitä voitaisiin muuttaa tulosten muuttamiseksi, jos se on sovellettavissa käyttötapaukseen ja toimialaan. |   3   |  V   |

---

## C13.5 Mallikortit ja Käyttöilmoitukset

Pidä yllä mallikortteja suunnitellusta käytöstä, suorituskykymittareista ja eettisistä näkökohdista.

|   #    | Description                                                                                                                                                                                      | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 13.5.1 | Varmista, että mallikortit dokumentoivat suunnitellut käyttötapaukset, rajoitukset ja tunnetut epäonnistumistilat.                                                                               |   1   |  D   |
| 13.5.2 | Varmista, että suorituskykymittarit eri soveltuvien käyttötapausten osalta on julkistettu.                                                                                                       |   1   | D/V  |
| 13.5.3 | Varmista, että eettiset näkökohdat, harha-arviot, oikeudenmukaisuuden arvioinnit, koulutusdatan ominaisuudet ja tunnetut koulutusdatan rajoitukset on dokumentoitu ja päivitetty säännöllisesti. |   2   |  D   |
| 13.5.4 | Varmista, että mallikortit ovat versionhallinnassa ja niitä ylläpidetään mallin elinkaaren ajan muutosseurannan avulla.                                                                          |   2   | D/V  |

---

## C13.6 Epävarmuuden kvantifiointi

Levitä luottamuspisteitä tai entropiamittauksia vastauksissa.

|   #    | Description                                                                                                               | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 13.6.1 | Varmista, että tekoälyjärjestelmät antavat tulostensa yhteydessä varmuuspisteet tai epävarmuusmittarit.                   |   1   |  D   |
| 13.6.2 | Varmista, että epävarmuuskynnykset laukaisevat lisäarvioinnin ihmisen toimesta tai vaihtoehtoiset päätöksentekopolut.     |   2   | D/V  |
| 13.6.3 | Varmista, että epävarmuuden määrityksen menetelmät on kalibroitu ja validoitu todellisiin todellisuustietoihin perustuen. |   2   |  V   |
| 13.6.4 | Varmista, että epävarmuuden kulkeutuminen säilyy monivaiheisissa tekoälytyönkuluissa.                                     |   3   | D/V  |

---

## C13.7 Käyttäjille suunnatut läpinäkyvyysraportit

Tarjoa säännöllisiä raportteja tapahtumista, mallin muutoksista ja datan käytöstä.

|   #    | Description                                                                                                                                                     | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 13.7.1 | Varmista, että tietojen käyttöä koskevat säännöt ja käyttäjien suostumuksen hallintakäytännöt on selkeästi viestitty sidosryhmille.                             |   1   | D/V  |
| 13.7.2 | Varmista, että tekoälyn vaikutusten arvioinnit tehdään ja tulokset sisällytetään raportointiin.                                                                 |   2   | D/V  |
| 13.7.3 | Varmista, että säännöllisesti julkaistavat läpinäkyvyysraportit paljastavat tekoälytapahtumat ja toiminnalliset mittarit kohtuullisessa yksityiskohtaisuudessa. |   2   | D/V  |

### Viitteet

* [EU Artificial Intelligence Act — Regulation (EU) 2024/1689 (Official Journal, 12 July 2024)](https://eur-lex.europa.eu/eli/reg/2024/1689/oj)
* [ISO/IEC 23894:2023 — Artificial Intelligence — Guidance on Risk Management](https://www.iso.org/standard/77304.html)
* [ISO/IEC 42001:2023 — AI Management Systems Requirements](https://www.iso.org/standard/81230.html)
* [NIST AI Risk Management Framework 1.0](https://nvlpubs.nist.gov/nistpubs/ai/nist.ai.100-1.pdf)
* [NIST SP 800-53 Revision 5 — Security and Privacy Controls](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-53r5.pdf)
* [A Unified Approach to Interpreting Model Predictions (SHAP, ICML 2017)](https://arxiv.org/abs/1705.07874)
* [Model Cards for Model Reporting (Mitchell et al., 2018)](https://arxiv.org/abs/1810.03993)
* [Dropout as a Bayesian Approximation: Representing Model Uncertainty in Deep Learning (Gal & Ghahramani, 2016)](https://arxiv.org/abs/1506.02142)
* [ISO/IEC 24029-2:2023 — Robustness of Neural Networks — Methodology for Formal Methods](https://www.iso.org/standard/79804.html)
* [IEEE 7001-2021 — Transparency of Autonomous Systems](https://standards.ieee.org/ieee/7001/6929/)
* [GDPR — Article 5 "Transparency Principle" (Regulation (EU) 2016/679)](https://eur-lex.europa.eu/legal-content/EN/TXT/PDF/?uri=CELEX%3A32016R0679)
* [Human Oversight under Article 14 of the EU AI Act (Fink, 2025)](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=5147196)

