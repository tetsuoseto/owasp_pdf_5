# C1 Koulutusdatan hallinta ja vinouman hallinta

## Valvontatavoite

Koulutusdata on hankittava, käsiteltävä ja ylläpidettävä siten, että säilytetään alkuperä, turvallisuus, laatu ja oikeudenmukaisuus. Tämä täyttää lakisääteiset velvoitteet ja vähentää puolueellisuuden, myrkytyksen tai tietosuojarikkomusten riskiä koko tekoälyn elinkaaren ajan.

---

## C1.1 Koulutusdatan alkuperä

Pidä yllä todennettavissa olevaa luetteloa kaikista tietoaineistoista, hyväksy ainoastaan luotettavat lähteet ja kirjaa jokainen muutos auditointia varten.

|   #   | Description                                                                                                                                                                                                                          | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 1.1.1 | Varmista, että pidetään ajan tasalla oleva luettelo jokaisesta harjoitusdatan lähteestä (alkuperä, vastuuhenkilö/omistaja, lisenssi, keräystapa, käyttötarkoitukseen liittyvät rajoitukset ja käsittelyhistoria).                    |   1   | D/V  |
| 1.1.2 | Varmista, että vain laadun, edustavuuden, eettisen hankinnan ja lisenssivaatimusten tarkastamat aineistot sallitaan, mikä vähentää myrkytyksen, sisäistetyn vinouman ja immateriaalioikeuksien loukkaamisen riskejä.                 |   1   | D/V  |
| 1.1.3 | Varmista, että tietojen minimointi on toteutettu siten, että tarpeettomat tai arkaluonteiset ominaisuudet suljetaan pois.                                                                                                            |   1   | D/V  |
| 1.1.4 | Varmista, että kaikki tietojoukon muutokset käyvät läpi kirjallisen hyväksymisprosessin.                                                                                                                                             |   2   | D/V  |
| 1.1.5 | Varmista, että merkintöjen/annotaatioiden laatu varmistetaan tarkistajien ristiintarkastuksilla tai yhteisymmärryksen kautta.                                                                                                        |   2   | D/V  |
| 1.1.6 | Varmista, että merkittäville koulutusdatasetille ylläpidetään "datakortteja" tai "datasheettejä", joissa kuvataan ominaisuudet, motivaatio, koostumus, keräysprosessit, esikäsittely sekä suositellut ja ei-suositellut käyttötavat. |   2   | D/V  |

---

## C1.2 Koulutusdatan turvallisuus ja eheys

Rajoita pääsyä, salaa tiedot levossa ja siirron aikana sekä tarkista eheys estääksesi manipulointia tai varkautta.

|   #   | Description                                                                                                                                                                                                                                                                                                                           | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.2.1 | Varmista, että pääsynvalvonta suojaa tallennustilat ja putkistot.                                                                                                                                                                                                                                                                     |   1   | D/V  |
| 1.2.2 | Varmista, että aineistot ovat salattuja siirron aikana ja kaikille arkaluonteisille tai henkilöitä tunnistaville tiedoille (PII) myös levossa käyttäen alan standardien mukaisia kryptografisia algoritmeja ja avaintenhallintakäytäntöjä.                                                                                            |   2   | D/V  |
| 1.2.3 | Varmista, että tietojen eheyttä varmistetaan tallennuksen ja siirron aikana käyttämällä kryptografisia tiivisteitä tai digitaalisia allekirjoituksia, ja että automatisoituja poikkeavuuksien tunnistamistekniikoita sovelletaan luvattomien muutosten tai vaurioiden, mukaan lukien kohdennetut tietomyrkytysyritykset, estämiseksi. |   2   | D/V  |
| 1.2.4 | Varmista, että datasetin versiot seurataan palautuksen mahdollistamiseksi.                                                                                                                                                                                                                                                            |   3   | D/V  |
| 1.2.5 | Varmista, että vanhentuneet tiedot poistetaan turvallisesti tai anonymisoidaan tietojen säilytyskäytäntöjen, sääntelyvaatimusten mukaisesti ja hyökkäyspinta-alan pienentämiseksi.                                                                                                                                                    |   2   | D/V  |

---

## C1.3 Esityksen täydellisyys ja oikeudenmukaisuus

Tunnista demografiset vinoumat ja ota käyttöön korjaustoimet, jotta mallin virheprosentit ovat tasapuolisia eri ryhmien välillä.

|   #   | Description                                                                                                                                                                                                                                                                                                                                                             | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.3.1 | Varmista, että datasarjoille tehdään analyysi edustuksellisesta epätasapainosta ja mahdollisista puolueellisuuksista laillisesti suojeltujen ominaisuuksien (esim. rotu, sukupuoli, ikä) sekä muiden mallin sovellusalueeseen liittyvien eettisesti herkkiä piirteitä (esim. sosioekonominen asema, sijainti) koskevien tekijöiden osalta.                              |   1   | D/V  |
| 1.3.2 | Varmista, että tunnistetut vinoumat on lievennetty dokumentoitujen strategioiden avulla, kuten uudelleen tasapainottaminen, kohdennettu aineiston lisäys, algoritmiset säädöt (esim. esikäsittely-, käsittely- ja jälkikäsittelytekniikat) tai uudelleen painotus, ja että lieventämisen vaikutus sekä oikeudenmukaisuuteen että koko mallin suorituskykyyn arvioidaan. |   2   | D/V  |
| 1.3.3 | Varmista, että jälkikoulutuksen reiluusmittarit arvioidaan ja dokumentoidaan.                                                                                                                                                                                                                                                                                           |   2   | D/V  |
| 1.3.4 | Varmista, että elinkaaren vinoumanhallintapolitiikka määrittelee vastuuhenkilöt ja tarkastelutiheyden.                                                                                                                                                                                                                                                                  |   3   | D/V  |

---

## C1.4 Koulutusdatan merkintöjen laatu, eheys ja turvallisuus

Suojaa tunnisteet salauksella ja vaadi kaksoistarkastus kriittisille luokille.

|   #   | Description                                                                                                                                                                                                                                                                 | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.4.1 | Varmista, että merkintöjen/annotaatioiden laatu varmistetaan selkeiden ohjeiden, tarkastajien ristiintarkastusten, yksimielisyysmekanismien (esim. annotaattoreiden välisten sopimusten valvonta) sekä määriteltyjen menettelyjen avulla ristiriitojen ratkaisemiseksi.     |   2   | D/V  |
| 1.4.2 | Varmista, että kryptografisia tiivisteitä tai digitaalisia allekirjoituksia käytetään tunniste-artefaktien eheyttä ja aitoutta varmistamaan.                                                                                                                                |   2   | D/V  |
| 1.4.3 | Varmista, että merkintäkäyttöliittymät ja -alustat toteuttavat vahvat pääsynvalvontamekanismit, ylläpitävät muokkaamattomuuden todistavia tarkastuslokimerkintöjä kaikista merkintätoiminnoista ja suojaavat luvattomalta muokkaukselta.                                    |   2   | D/V  |
| 1.4.4 | Varmista, että turvallisuuden, suojauksen tai oikeudenmukaisuuden kannalta kriittiset tunnisteet (esim. myrkyllisen sisällön tunnistaminen, kriittiset lääketieteelliset löydökset) saavat pakollisen riippumattoman kaksoistarkastuksen tai vastaavan vahvan varmennuksen. |   3   | D/V  |
| 1.4.5 | Varmista, että vahingossa tallentunut tai välttämättä etiketeissä oleva arkaluonteinen tieto (mukaan lukien henkilötiedot) on peitetty, pseudonymisoitu, anonymisoitu tai salattu lepäävänä ja siirrettäessä, noudattaen tietojen minimoinnin periaatteita.                 |   2   | D/V  |
| 1.4.6 | Varmista, että merkintäohjeet ja -ohjeistukset ovat kattavia, versiohallittuja ja vertaisarvioituja.                                                                                                                                                                        |   2   | D/V  |
| 1.4.7 | Varmista, että datakaaviot (mukaan lukien tunnisteet) on määritelty selkeästi ja versiohallittu.                                                                                                                                                                            |   2   | D/V  |
| 1.8.2 | Varmista, että ulkoistetut tai joukkorahoituksella toteutetut luokittelutyönkulut sisältävät teknisiä/prosessuaalisia turvatoimia tietojen luottamuksellisuuden, eheyden ja luokittelun laadun varmistamiseksi sekä datavuotojen estämiseksi.                               |   2   | D/V  |

---

## C1.5 Koulutusdatan laadunvarmistus

Yhdistä automatisoitu validointi, manuaaliset pistokokeet ja lokitettu korjaustoimenpiteet takaamaan tietojoukkojen luotettavuus.

|   #   | Description                                                                                                                                                                                                                                                                                     | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.5.1 | Varmista, että automatisoidut testit havaitsevat muotoiluvirheet, null-arvot ja etikettien vääristymät jokaisessa tietojen vastaanotossa tai merkittävässä muunnoksessa.                                                                                                                        |   1   |  D   |
| 1.5.2 | Varmista, että virheelliset tietojoukot asetetaan karanteeniin auditointilokein.                                                                                                                                                                                                                |   1   | D/V  |
| 1.5.3 | Varmista, että manuaaliset pistokokeet alakohtaisten asiantuntijoiden toimesta kattavat tilastollisesti merkittävän otoksen (esim. ≥1 % tai 1 000 otosta, kumpi tahansa on suurempi, tai riskinarvioinnin määrittämänä) havaitakseen hienovaraisia laatuongelmia, joita automaatio ei tunnista. |   2   |  V   |
| 1.5.4 | Varmista, että korjaustoimenpiteet lisätään alkuperätietoihin.                                                                                                                                                                                                                                  |   2   | D/V  |
| 1.5.5 | Varmista, että laatukriteerit estävät heikkolaatuiset aineistot, ellei poikkeuksia ole hyväksytty.                                                                                                                                                                                              |   2   | D/V  |

---

## C1.6 Datan myrkytyksen havaitseminen

Sovella tilastollista poikkeavuuksien tunnistusta ja eristysprosesseja pysäyttämään vihamieliset lisäykset.

|   #   | Description                                                                                                                                                                                                                                                                                                     | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.6.1 | Varmista, että poikkeavuuksien havaitsemismenetelmiä (esim. tilastolliset menetelmät, poikkeamien tunnistus, upotusanalyysi) sovelletaan harjoitusdataan tietojen vastaanoton yhteydessä ja ennen merkittäviä harjoituskierroksia mahdollisten myrkytysiskujen tai tahattoman datan korruption havaitsemiseksi. |   2   | D/V  |
| 1.6.2 | Varmista, että liputetut näytteet käynnistävät manuaalisen tarkastelun ennen koulutusta.                                                                                                                                                                                                                        |   2   | D/V  |
| 1.6.3 | Varmista, että tulokset syötetään mallin turvallisuusdossieeriin ja tiedottavat jatkuvaa uhkatiedustelua.                                                                                                                                                                                                       |   2   |  V   |
| 1.6.4 | Varmista, että tunnistuslogiikka päivitetään uudella uhkatiedolla.                                                                                                                                                                                                                                              |   3   | D/V  |
| 1.6.5 | Varmista, että verkkopohjaiset oppimispylväät valvovat jakauman siirtymää.                                                                                                                                                                                                                                      |   3   | D/V  |
| 1.6.6 | Varmista, että tietyt puolustukset tunnettuja datan myrkytys hyökkäystyyppejä vastaan (esim. luokittelun kääntäminen, takaportin liipaisimen lisääminen, vaikuttavien näytteiden hyökkäykset) otetaan huomioon ja toteutetaan järjestelmän riskiarvion ja datalähteiden perusteella.                            |   3   | D/V  |

---

## C1.7 Käyttäjätietojen poisto ja suostumuksen valvonta

Kunnioita poistopyyntöjä ja suostumuksen peruuttamisia kaikissa tietojoukoissa, varmuuskopioissa ja johdannaisissa artefakteissa.

|   #   | Description                                                                                                                                                                                                                                                                                                        | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 1.7.1 | Varmista, että poistoprosessit tyhjentävät ensisijaiset ja johdetut tiedot sekä arvioivat mallin vaikutukset, ja että vaikutukset asianomaisiin malleihin arvioidaan ja tarvittaessa korjataan (esim. uudelleenkoulutuksella tai uudelleensäätämisellä).                                                           |   1   | D/V  |
| 1.7.2 | Varmista, että mekanismit ovat olemassa käyttäjän suostumuksen (ja peruuttamisten) laajuuden ja tilan seuraamiseksi ja kunnioittamiseksi koulutuksessa käytettävien tietojen osalta, ja että suostumus vahvistetaan ennen tietojen sisällyttämistä uusiin koulutusprosesseihin tai merkittäviin mallipäivityksiin. |   2   |  D   |
| 1.7.3 | Varmista, että työnkulut testataan vuosittain ja niistä pidetään lokia.                                                                                                                                                                                                                                            |   2   |  V   |

---

## C1.8 Toimitusketjun turvallisuus

Tarkasta ulkoiset datantoimittajat ja varmista eheys todennetuilla, salatuilla yhteyksillä.

|   #   | Description                                                                                                                                                                                                                                                                                                                                                               | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.8.1 | Varmista, että kolmannen osapuolen datantoimittajat, mukaan lukien esikoulutettujen mallien ja ulkoisten tietoaineistojen tarjoajat, käyvät läpi turvallisuus-, tietosuoja-, eettisen hankinnan ja datalaadun due diligence -arvioinnin ennen kuin heidän datansa tai mallinsa integroidaan.                                                                              |   2   | D/V  |
| 1.8.2 | Varmista, että ulkoiset siirrot käyttävät TLS:ää/autentikointia ja eheystarkistuksia.                                                                                                                                                                                                                                                                                     |   1   |  D   |
| 1.8.3 | Varmista, että korkean riskin tietolähteille (esim. avoimen lähdekoodin aineistot, joiden alkuperä on tuntematon, tai arvostelematon toimittajat) kohdistetaan tehostettu tarkastelu, kuten suojatussa ympäristössä tehtävä analyysi, laajat laatu- ja vinoumatarkastukset sekä kohdennettu myrkytyksen havaitseminen, ennen niiden käyttöönottoa herkissä sovelluksissa. |   2   | D/V  |
| 1.8.4 | Varmista, että kolmansilta osapuolilta saadut ennalta koulutetut mallit arvioidaan sisäistettyjen vinoumien, mahdollisten takaovien, niiden arkkitehtuurin eheys sekä alkuperäisen koulutusdatan alkuperä ennen hienosäätöä tai käyttöönottoa.                                                                                                                            |   3   | D/V  |

---

## C1.9 Vihamielisten näytteiden havaitseminen

Ota koulutusvaiheessa käyttöön menetelmiä, kuten vastustajakoulutus, parantaaksesi mallin kestävyyttä vastustajaesimerkkejä vastaan.

|   #   | Description                                                                                                                                                                                                                                                                           | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.9.1 | Varmista, että asianmukaiset puolustustoimenpiteet, kuten vastustajakoulutus (generoitujen vastustajaesimerkkien käyttö), datan laajentaminen häirittyjen syötteiden avulla tai kestävät optimointitekniikat, on toteutettu ja säädetty asianmukaisesti riskinarvioinnin perusteella. |   3   | D/V  |
| 1.9.2 | Varmista, että jos käytetään vihamielistä harjoittelua, vihamielisten tietojoukkojen luominen, hallinta ja versionhallinta on dokumentoitu ja hallittu.                                                                                                                               |   2   | D/V  |
| 1.9.3 | Varmista, että vihamielisen kestävyyden koulutuksen vaikutus mallin suorituskykyyn (sekä puhtaita että vihamielisiä syötteitä vastaan) ja reiluusmittareihin arvioidaan, dokumentoidaan ja seurataan.                                                                                 |   3   | D/V  |
| 1.9.4 | Varmista, että vihamieliseen harjoitteluun ja robustisuuteen liittyvät strategiat tarkistetaan ja päivitetään säännöllisesti vastauksena kehittyviin vihamielisten hyökkäystekniikoihin.                                                                                              |   3   | D/V  |

---

## C1.10 Datan alkuperä ja jäljitettävyys

Seuraa jokaisen datapisteen koko matkaa lähteestä mallin syötteeksi auditoinnin ja häiriöiden hallinnan vuoksi.

|   #    | Description                                                                                                                                            | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 1.10.1 | Varmista, että kunkin datapisteen sukulaisuus, mukaan lukien kaikki muunnokset, laajennukset ja yhdistämiset, on tallennettu ja voidaan rekonstruoida. |   2   | D/V  |
| 1.10.2 | Varmista, että jäljitettävyystiedot ovat muuttumattomia, turvallisesti tallennettuja ja saatavilla tarkastuksia tai tutkimuksia varten.                |   2   | D/V  |
| 1.10.3 | Varmista, että linjaselvitys kattaa sekä raakadatan että synteettisen datan.                                                                           |   2   | D/V  |

---

## C1.11 Synteettisen datan hallinta

Varmista, että synteettisiä tietoja hallitaan asianmukaisesti, merkitään ja riskinarvioidaan.

|   #    | Description                                                                                                                                                                            | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.11.1 | Varmista, että kaikki synteettiset tiedot on selvästi merkitty ja erotettavissa todellisista tiedoista koko prosessin ajan.                                                            |   2   | D/V  |
| 1.11.2 | Varmista, että synteettisen datan generointiprosessi, parametrit ja aiottu käyttötarkoitus on dokumentoitu.                                                                            |   2   | D/V  |
| 1.11.3 | Varmista, että synteettinen data on arvioitu riskien suhteen puolueellisuuden, yksityisyyden vuotamisen ja esitykseen liittyvien ongelmien osalta ennen sen käyttämistä koulutuksessa. |   2   | D/V  |

---

## C1.12 Tietojen käyttöoikeuden valvonta ja poikkeamien havaitseminen

Valvo ja hälytä epätavallisesta pääsystä koulutusdataan sisäpiirin uhkien tai tiedon vuotamisen havaitsemiseksi.

|   #    | Description                                                                                                                                                        | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 1.12.1 | Varmista, että kaikki koulutusdataan kohdistuva pääsy kirjataan, mukaan lukien käyttäjä, aika ja toimenpide.                                                       |   2   | D/V  |
| 1.12.2 | Varmista, että käyttölogit tarkastetaan säännöllisesti epätavallisten kuvioiden varalta, kuten suurten vientien tai uusista sijainneista tapahtuvan pääsyn osalta. |   2   | D/V  |
| 1.12.3 | Varmista, että epäilyttävistä käyttöoikeustapahtumista luodaan hälytyksiä ja ne tutkitaan viipymättä.                                                              |   2   | D/V  |

---

## C1.13 Tietojen säilytys- ja vanhenemiskäytännöt

Määritä ja valvo tietojen säilytysaikoja minimoidaksesi tarpeettoman tietojen tallennuksen.

|   #    | Description                                                                                                                     | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.13.1 | Varmista, että kaikille koulutusdatakokoelmille on määritelty yksiselitteiset säilytysajat.                                     |   1   | D/V  |
| 1.13.2 | Varmista, että tietoaineistot vanhenevat, poistetaan tai tarkistetaan poistettavaksi automaattisesti niiden elinkaaren lopussa. |   2   | D/V  |
| 1.13.3 | Varmista, että säilytys- ja poistotoimenpiteet kirjataan ja että ne ovat auditoitavissa.                                        |   2   | D/V  |

---

## C1.14 Sääntely- ja toimivaltaisuusvaatimusten noudattaminen

Varmista, että kaikki koulutusdata noudattaa sovellettavia lakeja ja asetuksia.

|   #    | Description                                                                                                                                          | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.14.1 | Varmista, että kaikille aineistoille on tunnistettu ja noudatetaan tietojen säilytyspaikkaa ja rajat ylittäviä siirtovaatimuksia.                    |   2   | D/V  |
| 1.14.2 | Varmista, että toimialakohtaiset säädökset (esim. terveydenhuolto, rahoitus) tunnistetaan ja otetaan huomioon tiedon käsittelyssä.                   |   2   | D/V  |
| 1.14.3 | Varmista, että vaatimustenmukaisuus asiaankuuluvien tietosuojalakien (esim. GDPR, CCPA) kanssa on dokumentoitu ja sitä tarkastellaan säännöllisesti. |   2   | D/V  |

---

## C1.15 Tiedon vesileimaus ja sormenjälkitunnistus

Havaitse luvaton uudelleenkäyttö tai luottamuksellisten tai arkaluonteisten tietojen vuotaminen.

|   #    | Description                                                                                                         | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.15.1 | Varmista, että aineistot tai osajoukot on vesileimattu tai sormenjäljitetty, kun se on mahdollista.                 |   3   | D/V  |
| 1.15.2 | Varmista, että vesileimaus-/sormenjälkimenetelmissä ei synny harhaa tai yksityisyysriskejä.                         |   3   | D/V  |
| 1.15.3 | Varmista, että säännöllisiä tarkastuksia tehdään havaitsemaan vesileimatun datan luvaton uudelleenkäyttö tai vuoto. |   3   | D/V  |

---

## C1.16 Rekisteröidyn oikeuksien hallinta

Tukea rekisteröidyn oikeuksia, kuten pääsyä tietoihin, oikaisua, rajoittamista ja vastustamista.

|   #    | Description                                                                                                                                        | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.16.1 | Varmista, että on olemassa mekanismeja, joilla voidaan vastata rekisteröidyn pyyntöihin pääsystä, oikaisusta, rajoittamisesta tai vastustamisesta. |   2   | D/V  |
| 1.16.2 | Varmista, että pyynnöt kirjataan, seurataan ja täytetään laissa määrättyjen aikarajojen puitteissa.                                                |   2   | D/V  |
| 1.16.3 | Varmista, että rekisteröityjen oikeuksiin liittyvät prosessit testataan ja tarkastetaan säännöllisesti niiden toimivuuden varmistamiseksi.         |   2   | D/V  |

---

## C1.17 Datasetin version vaikutusanalyysi

Arvioi datanmuutosten vaikutus ennen versioiden päivittämistä tai korvaamista.

|   #    | Description                                                                                                                                                                   | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.17.1 | Varmista, että vaikutusanalyysi tehdään ennen tietojoukon version päivittämistä tai korvaamista, kattaen mallin suorituskyvyn, oikeudenmukaisuuden ja vaatimustenmukaisuuden. |   2   | D/V  |
| 1.17.2 | Varmista, että vaikutusanalyysin tulokset on dokumentoitu ja tarkastettu asianomaisten sidosryhmien toimesta.                                                                 |   2   | D/V  |
| 1.17.3 | Varmista, että palautussuunnitelmat ovat olemassa siltä varalta, että uudet versiot aiheuttavat hyväksymättömiä riskejä tai takapakkia.                                       |   2   | D/V  |

---

## C1.18 Tietojen merkintätyövoiman turvallisuus

Varmista työntekijöiden, jotka osallistuvat datankirjaamiseen, turvallisuus ja eheys.

|   #    | Description                                                                                                                                      | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 1.18.1 | Varmista, että kaikki tietojen merkinnässä mukana olevat henkilöt ovat taustaselvitettyjä ja koulutettuja tietoturvaan ja yksityisyyden suojaan. |   2   | D/V  |
| 1.18.2 | Varmista, että kaikki annotaattorit allekirjoittavat salassapito- ja vaitiolositoumukset.                                                        |   2   | D/V  |
| 1.18.3 | Varmista, että annotaatioalustat toteuttavat pääsynvalvontaa ja valvovat sisäisiä uhkia.                                                         |   2   | D/V  |

---

## Viitteet

* [NIST AI Risk Management Framework](https://www.nist.gov/itl/ai-risk-management-framework)
* [EU AI Act – Article 10: Data & Data Governance](https://artificialintelligenceact.eu/article/10/)
* [MITRE ATLAS: Adversary Tactics for AI](https://atlas.mitre.org/)
* [Survey of ML Bias Mitigation Techniques – MDPI](https://www.mdpi.com/2673-6470/4/1/1)
* [Data Provenance & Lineage Best Practices – Nightfall AI](https://www.nightfall.ai/ai-security-101/data-provenance-and-lineage)
* [Data Labeling Quality Standards – LabelYourData](https://labelyourdata.com/articles/data-labeling-quality-and-how-to-measure-it)
* [Training Data Poisoning Guide – Lakera.ai](https://www.lakera.ai/blog/training-data-poisoning)
* [CISA Advisory: Securing Data for AI Systems](https://www.cisa.gov/news-events/cybersecurity-advisories/aa25-142a)
* [ISO/IEC 23053: AI Management Systems Framework](https://www.iso.org/sectors/it-technologies/ai)
* [IBM: What is AI Governance?](https://www.ibm.com/think/topics/ai-governance)
* [Google AI Principles](https://ai.google/principles/)
* [GDPR & AI Training Data – DataProtectionReport](https://www.dataprotectionreport.com/2024/08/recent-regulatory-developments-in-training-artificial-intelligence-ai-models-under-the-gdpr/)
* [Supply-Chain Security for AI Data – AppSOC](https://www.appsoc.com/blog/ai-is-the-new-frontier-of-supply-chain-security)
* [OpenAI Privacy Center – Data Deletion Controls](https://privacy.openai.com/policies?modal=take-control)
* [Adversarial ML Dataset – Kaggle](https://www.kaggle.com/datasets/cnrieiit/adversarial-machine-learning-dataset)

