# C12 Valvonta, lokitus ja poikkeavuuksien havaitseminen

## Kontrollin tavoite

Tämä osio sisältää vaatimukset reaaliaikaisen ja tutkintatason näkyvyyden tarjoamiseksi siihen, mitä malli ja muut tekoälykomponentit näkevät, tekevät ja palauttavat, jotta uhkia voidaan havaita, arvioida ja oppia niistä.

## C12.1 Pyyntöjen ja vastausten kirjaaminen

|   #    | Description                                                                                                                                                                                                                                                                       | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 12.1.1 | Varmista, että kaikki käyttäjän kehoteet ja mallin vastaukset kirjataan asianmukaisilla metatiedoilla (esim. aikaleima, käyttäjätunnus, istunnon tunnus, malliversio).                                                                                                            |   1   | D/V  |
| 12.1.2 | Varmista, että lokit tallennetaan turvallisiin, pääsynvalvottuihin säilytyspaikkoihin, joissa on asianmukaiset säilytyskäytännöt ja varmuuskopiointimenettelyt.                                                                                                                   |   1   | D/V  |
| 12.1.3 | Varmista, että lokien tallennusjärjestelmät toteuttavat salauksen levossa ja siirrossa suojatakseen lokeissa olevia arkaluonteisia tietoja.                                                                                                                                       |   1   | D/V  |
| 12.1.4 | Varmista, että kehotteiden ja tulosteiden arkaluonteiset tiedot sensuroidaan tai peitetään automaattisesti ennen kirjaamista, ja että sensurointisäännöt henkilökohtaisille tunnistetiedoille (PII), tunnuksille ja omistusoikeuteen kuuluville tiedoille ovat konfiguroitavissa. |   1   | D/V  |
| 12.1.5 | Varmista, että politiikkapäätökset ja turvallisuussuodatus toimenpiteet kirjataan riittävän yksityiskohtaisesti, jotta sisällönvalvontajärjestelmien tarkastaminen ja virheiden korjaaminen on mahdollista.                                                                       |   2   | D/V  |
| 12.1.6 | Varmista, että lokien eheys on suojattu esimerkiksi kryptografisilla allekirjoituksilla tai kirjoitusvain tallennuksella.                                                                                                                                                         |   2   | D/V  |

---

## C12.2 Väärinkäytösten tunnistus ja hälyttäminen

|   #    | Description                                                                                                                                                                                           | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 12.2.1 | Varmista, että järjestelmä havaitsee ja hälyttää tunnetuista jailbreak-kuvioista, kehotteiden injektiopyrkimyksistä ja vastustavista syötteistä käyttämällä allekirjoituspohjaista tunnistusta.       |   1   | D/V  |
| 12.2.2 | Varmista, että järjestelmä integroituu olemassa oleviin turvallisuustieto- ja tapahtumahallinnan (SIEM) alustoihin käyttäen standardeja lokimuotoja ja protokollia.                                   |   1   | D/V  |
| 12.2.3 | Varmista, että rikastetuissa turvallisuustapahtumissa on tekoälyyn liittyvää kontekstia, kuten mallin tunnisteita, luottamuspisteitä ja turvallisuussuodattimen päätöksiä.                            |   2   | D/V  |
| 12.2.4 | Varmista, että käyttäytymisen poikkeavuuksien havaitseminen tunnistaa epätavalliset keskustelumallit, liiallisen uudelleenkäyttöyritysten määrän tai systemaattiset tutkiskelukäyttäytymiset.         |   2   | D/V  |
| 12.2.5 | Varmista, että reaaliaikaiset hälytysmekanismit ilmoittavat turvallisuustiimeille, kun mahdollisia sääntörikkomuksia tai hyökkäyspyrkimyksiä havaitaan.                                               |   2   | D/V  |
| 12.2.6 | Varmista, että mukautetut säännöt on lisätty tunnistamaan tekoälyyn liittyviä uhkakuvioita, kuten koordinoituja jailbreak-yrityksiä, komennon injektointikampanjoita ja mallin poiminta -hyökkäyksiä. |   2   | D/V  |
| 12.2.7 | Varmista, että automatisoidut häiriötilanteiden käsittelytyönkulut voivat eristää vaarantuneet mallit, estää haitalliset käyttäjät ja nostaa esiin kriittiset tietoturvatapahtumat.                   |   3   | D/V  |

---

## C12.3 Mallin liukuman havaitseminen

|   #    | Description                                                                                                                                                                                     | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 12.3.1 | Varmista, että järjestelmä seuraa perussuorituskykymittareita, kuten tarkkuutta, luottamusarvoja, viivettä ja virheprosentteja malliversioiden ja ajanjaksojen välillä.                         |   1   | D/V  |
| 12.3.2 | Varmista, että automaattinen hälytys aktivoituu, kun suorituskykymittarit ylittävät ennalta määritetyt heikentymiskynnykset tai poikkeavat merkittävästi vertailutasoista.                      |   2   | D/V  |
| 12.3.3 | Varmista, että harhantunnistuksen valvojat havaitsevat ja merkitsevät tapaukset, joissa mallin tuottamassa sisällössä on tosiasiallisesti virheellistä, epäjohdonmukaista tai keksittyä tietoa. |   2   | D/V  |

---

## C12.4 Suorituskyky- ja käyttäytymistietojen telemetria

|   #    | Description                                                                                                                                                | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 12.4.1 | Varmista, että operatiiviset mittarit, mukaan lukien pyyntöviive, tokenien kulutus, muistin käyttö ja läpimeno, kerätään ja seurataan jatkuvasti.          |   1   | D/V  |
| 12.4.2 | Varmista, että onnistumis- ja epäonnistumisprosentit seurataan virhetyyppien ja niiden perussyiden luokittelun avulla.                                     |   1   | D/V  |
| 12.4.3 | Varmista, että resurssien käytön seuranta kattaa GPU/CPU:n käytön, muistinkulutuksen ja tallennustarpeet sekä sisältää hälytykset kynnysarvorikkomuksista. |   2   | D/V  |

---

## C12.5 AI-tapahtumien käsittelysuunnittelu ja toteutus

|   #    | Description                                                                                                                                                                                                        | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 12.5.1 | Varmista, että häiriötilanteiden hallintasuunnitelmat käsittelevät nimenomaisesti tekoälyyn liittyviä tietoturvatapahtumia, kuten mallin vaarantumista, datan myrkyttämistä ja vastustavien hyökkäysten torjuntaa. |   1   | D/V  |
| 12.5.2 | Varmista, että häiriönhallintatiimeillä on käytössään tekoälyyn erikoistuneet forensiset työkalut ja asiantuntemus mallin käyttäytymisen ja hyökkäysvektoreiden tutkimiseksi.                                      |   2   | D/V  |
| 12.5.3 | Varmista, että jälkitapahtuma-analyysi sisältää mallin uudelleenkoulutuksen huomioimisen, turvallisuussuodattimien päivitykset ja opittujen asioiden integroinnin tietoturvakontrolleihin.                         |   3   | D/V  |

---

## C12.5 AI:n suorituskyvyn heikkenemisen havaitseminen

Seuraa ja havaitse tekoälymallin suorituskyvyn ja laadun heikkenemistä ajan myötä.

|   #    | Description                                                                                                                                                    | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 12.5.1 | Varmista, että mallin tarkkuutta, precision, recall-arvoja ja F1-mittareita seurataan jatkuvasti ja verrataan perustasoarvoihin.                               |   1   | D/V  |
| 12.5.2 | Varmista, että datan muutoksen havaitseminen valvoo syötteen jakauman muutoksia, jotka voivat vaikuttaa mallin suorituskykyyn.                                 |   1   | D/V  |
| 12.5.3 | Varmista, että käsitepoikkeaman havainto tunnistaa muutokset syötteiden ja odotettujen tulosten välisessä suhteessa.                                           |   2   | D/V  |
| 12.5.4 | Varmista, että suorituskyvyn heikkeneminen laukaisee automaattiset hälytykset ja käynnistää mallin uudelleenkoulutus- tai korvaustyönkulut.                    |   2   | D/V  |
| 12.5.5 | Varmista, että suorituskyvyn heikkenemisen juurisyyanalyysi yhdistää suorituskyvyn laskut datan muutoksiin, infrastruktuuriongelmiin tai ulkoisiin tekijöihin. |   3   |  V   |

---

## C12.6 DAG-visualisointi ja työnkulun turvallisuus

Suojaa työnkulun visualisointijärjestelmät tietovuodoilta ja manipulointihyökkäyksiltä.

|   #    | Description                                                                                                                                                    | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 12.6.1 | Varmista, että DAG-visualisointitiedot puhdistetaan poistamaan arkaluonteiset tiedot ennen tallennusta tai siirtoa.                                            |   1   | D/V  |
| 12.6.2 | Varmista, että työnkulun visualisoinnin käyttöoikeudet takaavat, että vain valtuutetut käyttäjät voivat tarkastella agentin päätöspolkuja ja perusteluja.      |   1   | D/V  |
| 12.6.3 | Varmista, että DAG-tietojen eheys on suojattu kryptografisilla allekirjoituksilla ja manipuloinnin havaitsemiseen tarkoitetuilla tallennusmekanismeilla.       |   2   | D/V  |
| 12.6.4 | Varmista, että työnkulun visualisointijärjestelmät toteuttavat syötteen validoinnin estääkseen injektiohyökkäykset muokatun solmu- tai reuna-aineiston kautta. |   2   | D/V  |
| 12.6.5 | Varmista, että reaaliaikaiset DAG-päivitykset ovat nopeusrajoitettuja ja validoituja estämään palvelunestohyökkäyksiä visualisointijärjestelmiin.              |   3   | D/V  |

---

## C12.7 Ennakoiva turvallisuuskäyttäytymisen seuranta

Turvallisuusuhkien havaitseminen ja estäminen proaktiivisen agenttien käyttäytymisanalyysin avulla.

|   #    | Description                                                                                                                                                            | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 12.7.1 | Varmista, että proaktiivisten agenttien käyttäytymismallit ovat tietoturvallisesti validoituja ennen suorittamista riskinarvioinnin integroinnilla.                    |   1   | D/V  |
| 12.7.2 | Varmista, että autonomisen aloitteen laukaisevat tekijät sisältävät turvallisuuskontekstin arvioinnin ja uhkakentän analyysin.                                         |   2   | D/V  |
| 12.7.3 | Varmista, että ennakoivat käyttäytymismallit analysoidaan mahdollisten turvallisuusvaikutusten ja tahattomien seurauksien varalta.                                     |   2   | D/V  |
| 12.7.4 | Varmista, että turvallisuuden kannalta kriittiset proaktiiviset toimet vaativat selkeät hyväksymisketjut auditointilokien kera.                                        |   3   | D/V  |
| 12.7.5 | Varmista, että käyttäytymisen poikkeavuuksien havaitseminen tunnistaa poikkeamat proaktiivisten agenttien malleissa, jotka voivat viitata järjestelmän vaarantumiseen. |   3   | D/V  |

---

## Viitteet

* [NIST AI Risk Management Framework 1.0 - Manage 4.1 and 4.3](https://nvlpubs.nist.gov/nistpubs/ai/nist.ai.100-1.pdf)
* [ISO/IEC 42001:2023 — AI Management Systems Requirements - Annex B 6.2.6](https://www.iso.org/standard/81230.html)
* [EU AI Act — Article 12, 13, 16 and 19 on Logging and Record-keeping](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX%3A32024R1689)

