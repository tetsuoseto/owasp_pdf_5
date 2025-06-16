# C5 Käyttöoikeuksien hallinta ja identiteetti tekoälykomponenteille ja käyttäjille

## Ohjaustavoite

Tehokas käyttöoikeuksien hallinta tekoälyjärjestelmissä edellyttää vahvaa identiteetin hallintaa, kontekstin tuntevaa valtuutusta ja suoritusajan valvontaa noudattaen nollaluottamusperiaatteita. Nämä hallintakeinot varmistavat, että ihmiset, palvelut ja autonomiset agentit käyttävät malleja, tietoja ja laskentaresursseja vain nimenomaisesti myönnetyissä laajuuksissa, jatkuvan vahvistamisen ja auditointimahdollisuuksien tukemina.

---

## C5.1 Identiteetin hallinta ja todennus

Perusta kaikille toimijoille kryptografisesti varmennetut identiteetit monivaiheisella todennuksella valtuutettuihin toimiin.

|   #   | Description                                                                                                                                                                                                                                                             | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 5.1.1 | Varmista, että kaikki ihmis- ja palveluperiaatteet todennetaan keskitetyn yrityksen identiteetin tarjoajan (IdP) kautta käyttäen OIDC/SAML-protokollia ainutlaatuisilla identiteetistä tokeniin kartoittamisilla (ei yhteiskäytössä olevia tilejä tai tunnistetietoja). |   1   | D/V  |
| 5.1.2 | Varmista, että korkean riskin toimenpiteet (mallin käyttöönotto, painojen vienti, koulutusdatan käyttöoikeus, tuotantokonfiguraation muutokset) vaativat monivaiheisen tunnistautumisen tai lisävahvistuksen istunnon uudelleentarkistuksella.                          |   1   | D/V  |
| 5.1.3 | Varmista, että uudet johtajat käyvät läpi henkilöllisyyden todentamisen, joka on linjassa NIST 800-63-3 IAL-2 -standardin tai vastaavien standardien kanssa, ennen kuin he saavat pääsyn tuotantojärjestelmään.                                                         |   2   |  D   |
| 5.1.4 | Varmista, että käyttöoikeustarkastukset suoritetaan neljännesvuosittain automaattisella epäaktiivisten tilien havaitsemisella, tunnistetietojen kierron valvonnalla ja poistoprosesseilla.                                                                              |   2   |  V   |
| 5.1.5 | Varmista, että liitetyt tekoälyagentit todennetaan allekirjoitettujen JWT-väitteiden avulla, joiden enimmäiskesto on 24 tuntia ja jotka sisältävät kryptografisen alkuperätodisteen.                                                                                    |   3   | D/V  |

---

## C5.2 Resurssien valtuutus ja vähimmän oikeuden periaate

Toteuta hienojakoiset käyttöoikeuksien hallinnat kaikille tekoälyresursseille selkeillä lupamalleilla ja tarkastuspoluilla.

|   #   | Description                                                                                                                                                                                                                                             | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 5.2.1 | Varmista, että jokainen tekoälyresurssi (aineistot, mallit, päätepisteet, vektorikokoelmat, upotusindeksit, laskenta-instanssit) käyttää roolipohjaisia käyttöoikeuksia, joissa on eksplisiittiset sallintalistat ja oletuksena kieltävät käytännöt.    |   1   | D/V  |
| 5.2.2 | Varmista, että vähimmän etuoikeuden periaatteet toteutuvat oletuksena palvelutilien kohdalla, aloittaen lukuoikeuksista, ja että kirjoitusoikeuksille vaaditaan dokumentoitu liiketoiminnallinen perustelu.                                             |   1   | D/V  |
| 5.2.3 | Varmista, että kaikki käyttöoikeuksien muutokset ovat liitetty hyväksyttyihin muutospyyntöihin ja kirjattu muuttumattomasti aikaleimojen, toimijoiden tunnisteiden, resurssien tunnisteiden ja oikeusmuutosten kanssa.                                  |   1   |  V   |
| 5.2.4 | Varmista, että tietoluokittelutunnisteet (henkilötiedot, potilastiedot, vientivalvottu, luottamuksellinen) siirtyvät automaattisesti johdettuihin resursseihin (upotukset, kehotemuistit, mallin tulokset) johdonmukaisella politiikan noudattamisella. |   2   |  D   |
| 5.2.5 | Varmista, että luvattomat käyttöyritykset ja etuoikeuksien korotustapahtumat laukaisevat reaaliaikaiset hälytykset kontekstuaalisine metatietoineen SIEM-järjestelmiin viiden minuutin kuluessa.                                                        |   2   | D/V  |

---

## C5.3 Dynaaminen politiikan arviointi

Ota käyttöön attribuuttipohjaiset pääsynvalvontamoottorit (ABAC) kontekstietietoisten valtuutuspäätösten tekemiseen auditointimahdollisuuksilla.

|   #   | Description                                                                                                                                                                                                              | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 5.3.1 | Varmista, että valtuutuspäätökset ulkoistetaan omistetulle politiikkamoottorille (OPA, Cedar tai vastaava), johon pääsee käsiksi todennetuilla API-rajapinnoilla, jotka tarjoavat kryptografisen eheyden suojauksen.     |   1   | D/V  |
| 5.3.2 | Varmista, että käytännöt arvioivat dynaamisia attribuutteja suoritusajon aikana, mukaan lukien käyttäjän valtuutustaso, resurssin arkaluonteisuusluokitus, pyyntöympäristö, vuokralais-eristys ja ajalliset rajoitukset. |   1   | D/V  |
| 5.3.3 | Varmista, että politiikan määritelmät ovat versiohallittuja, vertaisarvioituja ja validoitu automaattisen testauksen avulla CI/CD-putkissa ennen tuotantoon käyttöönottoa.                                               |   2   |  D   |
| 5.3.4 | Varmista, että politiikan arviointitulokset sisältävät jäsennellyt päätöspohjat ja ne lähetetään SIEM-järjestelmiin korrelaatioanalyysia ja vaatimustenmukaisuusraportointia varten.                                     |   2   |  V   |
| 5.3.5 | Varmista, että politiikan välimuistin elinaika-arvot (TTL) eivät ylitä 5 minuuttia korkean herkkyyden omaaville resursseille ja 1 tuntia vakiomääräysten resursseille, joilla on välimuistin mitätöintikyky.             |   3   | D/V  |

---

## C5.4 Kyselyajan turvallisuuden valvonta

Ota käyttöön tietokantakerroksen turvallisuusohjaimet pakollisilla suodatuksilla ja rivitason turvallisuuspolitiikoilla.

|   #   | Description                                                                                                                                                                                                                     | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 5.4.1 | Varmista, että kaikki vektoritietokanta- ja SQL-kyselyt sisältävät pakolliset suojaussuodattimet (vuokralais-ID, herkkyystunnisteet, käyttäjän käyttöalue), jotka toteutetaan tietokantamoottorin tasolla, ei sovelluskoodissa. |   1   | D/V  |
| 5.4.2 | Varmista, että rivitasoisen suojauksen (RLS) käytännöt ja kenttätason peittäminen ovat käytössä politiikan periytymisellä kaikissa vektorikannoissa, hakemistotiedoissa ja koulutusaineistoissa.                                |   1   | D/V  |
| 5.4.3 | Varmista, että epäonnistuneet valtuutuksen arvioinnit estävät "sekaannus-edustaja-hyökkäykset" keskeyttämällä kyselyt välittömästi ja palauttamalla selkeät valtuutusvirhekoodit tyhjien tulosjoukkojen sijaan.                 |   2   |  D   |
| 5.4.4 | Varmista, että politiikan arviointiviivettä valvotaan jatkuvasti automatisoitujen hälytysten avulla aikakatkaisutilanteissa, jotka voisivat mahdollistaa valtuutuksen ohittamisen.                                              |   2   |  V   |
| 5.4.5 | Varmista, että kyselyn uudelleenyrittomekanismit arvioivat valtuutuspolitiikat uudelleen ottaen huomioon dynaamiset käyttöoikeusmuutokset aktiivisten käyttäjäistuntojen aikana.                                                |   3   | D/V  |

---

## C5.5 Tulosteen suodatus ja tietojen menetyksen estäminen

Ota käyttöön jälkikäsittelyohjaimet estääksesi luvattoman tietojen paljastumisen tekoälyn tuottamassa sisällössä.

|   #   | Description                                                                                                                                                                                                             | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 5.5.1 | Varmista, että jälkipäätöksentekoon perustuvat suodatusmekanismit skannaavat ja poistavat luvattoman henkilötiedon (PII), luokitellun tiedon ja omistusoikeudellisen datan ennen sisällön toimittamista pyytäjille.     |   1   | D/V  |
| 5.5.2 | Varmista, että mallin tuottamien viitteiden, lähdeviitteiden ja lähdeviittausten oikeellisuus tarkistetaan soittajan oikeuksien perusteella ja poistetaan, jos luvaton pääsy havaitaan.                                 |   1   | D/V  |
| 5.5.3 | Varmista, että tulostusmuodon rajoitukset (puhdistetut PDF-tiedostot, metatietojen poistetut kuvat, hyväksytyt tiedostotyypit) toteutetaan käyttäjän lupatason ja tietoluokitusten perusteella.                         |   2   |  D   |
| 5.5.4 | Varmista, että sensurointialgoritmit ovat deterministisiä, versiohallittuja ja ylläpitävät tarkastuslokeja tukemaan vaatimustenmukaisuustutkintoja ja oikeuslääketieteellisiä analyyseja.                               |   2   |  V   |
| 5.5.5 | Varmista, että korkean riskin salaus tapahtumat tuottavat adaptiivisia lokitietoja, jotka sisältävät alkuperäisen sisällön kryptografiset tiivisteet oikeuslääketieteellistä hakua varten ilman tietojen paljastumista. |   3   |  V   |

---

## C5.6 Monivuokralais-eristys

Varmista kryptografinen ja looginen eristys vuokralaisten välillä jaetussa tekoälyinfrastruktuurissa.

|   #   | Description                                                                                                                                                                                                                                                        | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 5.6.1 | Varmista, että muistitilat, upotusten tallennustilat, välimuistin kohteet ja väliaikaiset tiedostot ovat nimialueittain erillään kunkin vuokralaisen osalta, ja että vuokralaisen poistamisen tai istunnon päättymisen yhteydessä tiedot poistetaan turvallisesti. |   1   | D/V  |
| 5.6.2 | Varmista, että jokainen API-pyyntö sisältää todennetun vuokralaisen tunnisteen, joka on kryptografisesti validoitu istuntokontekstin ja käyttäjäoikeuksien perusteella.                                                                                            |   1   | D/V  |
| 5.6.3 | Varmista, että verkkopolitiikat toteuttavat oletusarvoisesti kieltävät säännöt monivuokraajaviestinnälle palveluverkkojen ja konttien orkestrointialustojen sisällä.                                                                                               |   2   |  D   |
| 5.6.4 | Varmista, että salausavaimet ovat uniikkeja jokaiselle vuokralaiselle, kun käytössä on asiakkaan hallinnoima avain (CMK), ja että vuokratilojen tietovarastojen välillä on kryptografinen eristys.                                                                 |   3   |  D   |

---

## C5.7 Autonomisen agentin valtuutus

Ohjaoikeudet tekoälyagentteihin ja autonomisiin järjestelmiin hallitaan laajuusrajoitetuilla valtuutustunnuksilla ja jatkuvalla valtuutuksella.

|   #   | Description                                                                                                                                                                                                                                                 | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 5.7.1 | Varmista, että autonomiset agentit saavat rajatut käyttöoikeustunnukset, jotka erittelevät nimenomaisesti sallitut toiminnot, käytettävissä olevat resurssit, aikarajat ja toimintarajoitukset.                                                             |   1   | D/V  |
| 5.7.2 | Varmista, että korkean riskin toiminnot (tiedostojärjestelmän käyttö, koodin suoritus, ulkoiset API-kutsut, taloudelliset tapahtumat) ovat oletuksena pois päältä ja niiden aktivoiminen vaatii selkeät käyttöoikeudet liiketoiminnallisilla perusteluilla. |   1   | D/V  |
| 5.7.3 | Varmista, että käyttöoikeustunnukset ovat sidottuja käyttäjäistuntoihin, sisältävät kryptografisen eheyden suojauksen ja että niitä ei voi tallentaa tai käyttää uudelleen offline-tilanteissa.                                                             |   2   |  D   |
| 5.7.4 | Varmista, että agentin aloittamat toimet käyvät läpi toissijaisen valtuutuksen ABAC-politiikkamoottorin kautta käyttäen täydellistä kontekstiarviota ja auditointilokien kirjausta.                                                                         |   2   |  V   |
| 5.7.5 | Varmista, että agentin virhetilanteet ja poikkeusten käsittely sisältävät käyttöoikeuksien laajuustiedot tukemaan tapausanalyysiä ja oikeuslääketieteellistä tutkimusta.                                                                                    |   3   |  V   |

---

## Viitteet

### Standardit ja viitekehykset

* [NIST SP 800-63-3: Digital Identity Guidelines](https://pages.nist.gov/800-63-3/)
* [Zero Trust Architecture – NIST SP 800-207](https://nvlpubs.nist.gov/nistpubs/specialpublications/NIST.SP.800-207.pdf)
* [OWASP Application Security Verification Standard (AISVS)](https://owasp.org/www-project-application-security-verification-standard/)
  ​
### Toteutusoppaat

* [Identity and Access Management in the AI Era: 2025 Guide – IDSA](https://www.idsalliance.org/blog/identity-and-access-management-in-the-ai-era-2025-guide/)
* [Attribute-Based Access Control with OPA – Permify](https://medium.com/permify-tech-blog/attribute-based-access-control-abac-implementation-with-open-policy-agent-opa-b47052248f29)
* [How We Designed Cedar to Be Intuitive, Fast, and Safe – AWS](https://aws.amazon.com/blogs/security/how-we-designed-cedar-to-be-intuitive-to-use-fast-and-safe/)
  ​
### AI-spesifinen tietoturva

* [Row Level Security in Vector DBs for RAG – Bluetuple.ai](https://medium.com/bluetuple-ai/implementing-row-level-security-in-vector-dbs-for-rag-applications-fdbccb63d464)
* [Tenant Isolation in Multi-Tenant Systems – WorkOS](https://workos.com/blog/tenant-isolation-in-multi-tenant-systems)
* [Handling AI Agent Permissions – Stytch](https://stytch.com/blog/handling-ai-agent-permissions/)
* [OWASP Top 10 for Large Language Model Applications](https://owasp.org/www-project-top-10-for-large-language-model-applications/)

