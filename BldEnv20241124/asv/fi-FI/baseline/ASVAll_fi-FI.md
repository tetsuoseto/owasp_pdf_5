## Etusivu

### Tietoa standardista

Tekoälyn tietoturvan varmistusstandardi (AISVS) on yhteisön luoma tietoturvavaatimusten luettelo, jota datatieteilijät, MLOps-insinöörit, ohjelmistoarkkitehdit, kehittäjät, testaajat, tietoturva-asiantuntijat, työkalutoimittajat, sääntelijät ja käyttäjät voivat käyttää suunnitellessaan, rakentaessaan, testatessaan ja varmistaessaan luotettavia tekoälyä hyödyntäviä järjestelmiä ja sovelluksia. Se tarjoaa yhteisen kielen tietoturvakontrollien määrittelyyn tekoälyn elinkaaren eri vaiheissa — datan keruusta ja mallin kehityksestä käyttöönottoon ja jatkuvaan valvontaan — jotta organisaatiot voivat mitata ja parantaa tekoälyratkaisujensa kestävyyttä, yksityisyyttä ja turvallisuutta.

### Tekijänoikeudet ja lisenssi

Versio 0.1 (Ensimmäinen julkinen luonnos - Työn alla), 2025  

![license](images/license.png)
Tekijänoikeudet © 2025 AISVS-projekti.  

Julkaistu lisenssin alaisenaCreative Commons Attribution‑ShareAlike 4.0 International License.
Kaikessa uudelleenkäytössä tai jakelussa sinun on selkeästi kerrottava tämän työn lisenssiehdot muille.

### Projektin vetäjät

Jim Manico
Aras "Russ" Memisyazici

### Osallistujat ja Arvostelijat

https://github.com/ottosulin
https://github.com/mbhatt1
https://github.com/vineethsai
https://github.com/cciprofm
https://github.com/deepakrpandey12


---

AISVS on täysin uusi standardi, joka on luotu erityisesti vastaamaan tekoälyjärjestelmien ainutlaatuisiin turvallisuushaasteisiin. Vaikka se ammentaa inspiraatiota laajemmista turvallisuuden parhaista käytännöistä, jokainen AISVS:n vaatimus on kehitetty alusta alkaen heijastamaan tekoälyn uhkakenttää ja auttamaan organisaatioita rakentamaan turvallisempia, kestävämpiä tekoälyratkaisuja.

## Esipuhe

Tervetuloa Tekoälyn turvallisuuden varmistamisen standardiin (AISVS) versio 1.0!

### Johdanto

Vuonna 2025 perustettu AISVS määrittelee turvallisuusvaatimukset, jotka on otettava huomioon suunniteltaessa, kehitettäessä, käyttöönotettaessa ja ylläpidettäessä nykyaikaisia tekoälymalleja, putkistoja ja tekoälyllä tehostettuja palveluja.

AISVS v1.0 edustaa sen projektin vetäjien, työryhmän ja laajemman yhteisön yhteistyön tulosta, jonka tavoitteena on luoda käytännöllinen ja testattavissa oleva perusta tekoälyjärjestelmien suojaamiseksi.

Tavoitteenamme tämän julkaisun myötä on tehdä AISVS:n käyttöönotosta vaivatonta samalla kun pysymme tiukasti sen määritellyssä laajuudessa ja vastaamme AI:lle ainutlaatuisesti kehittyvään riskimaisemaan.

### Keskeiset tavoitteet AISVS-versiolle 1.0

Versio 1.0 luodaan useiden ohjaavien periaatteiden pohjalta.

#### Selkeästi määritelty laajuus

Jokaisen vaatimuksen on oltava linjassa AISVS:n nimen ja tehtävän kanssa:

Tekoäly – Kontrollit toimivat tekoäly/koneoppimiskerroksella (data, malli, putkisto tai päättely) ja niiden vastuullisia ovat tekoälyasiantuntijat.
Turvallisuus – Vaatimukset suoraan lieventävät tunnistettuja turvallisuus-, tietosuoja- tai turvallisuusriskitekijöitä.
Varmennus – Kieli on kirjoitettu siten, että vaatimustenmukaisuus voidaan objektiivisesti validoida.
Standardi – Osat noudattavat johdonmukaista rakennetta ja terminologiaa muodostaen yhtenäisen viitekehyksen.
​
---

Noudattamalla AISVS:ää organisaatiot voivat järjestelmällisesti arvioida ja vahvistaa tekoälyratkaisujensa turvallisuusasemaa, edistäen turvallisen tekoälyinsinöörikulttuurin kehittymistä.

## AISVS:n käyttäminen

Tekoälyn turvallisuussertifiointistandardi (AISVS) määrittelee turvallisuusvaatimuksia nykyaikaisille tekoälysovelluksille ja -palveluille, keskittyen sovelluskehittäjien hallinnassa oleviin näkökohtiin.

AISVS on tarkoitettu kaikille, jotka kehittävät tai arvioivat tekoälysovellusten turvallisuutta, mukaan lukien kehittäjät, arkkitehdit, turvallisuusinsinöörit ja tarkastajat. Tässä luvussa esitellään AISVS:n rakenne ja käyttö, mukaan lukien sen varmennustasot ja suunnitellut käyttötapaukset.

### Tekoälyn turvallisuuden varmistustasot

AISVS määrittelee kolme etenevää turvallisuusvarmennustasoa. Jokainen taso lisää syvyyttä ja monimutkaisuutta, jolloin organisaatiot voivat räätälöidä turvallisuusasentonsa AI-järjestelmiensä riskitasoon sopivaksi.

Organisaatiot voivat aloittaa tasolta 1 ja edetä asteittain korkeammille tasoille tietoturvan kypsyysasteen ja uhkien lisääntyessä.

#### Tasojen määritelmä

Jokainen AISVS v1.0 -version vaatimus on jaettu seuraaviin tasoihin:

 Taso 1 vaatimukset

Taso 1 sisältää kriittisimmät ja perustavanlaatuisimmat turvallisuusvaatimukset. Ne keskittyvät yleisten hyökkäysten estämiseen, jotka eivät perustu muihin edellytyksiin tai haavoittuvuuksiin. Suurin osa Tason 1 ohjauskeinoista on joko helppoja toteuttaa tai riittävän välttämättömiä, jotta niiden toteuttaminen on perusteltua.

 Tason 2 vaatimukset

Taso 2 käsittelee kehittyneempiä tai harvinaisempia hyökkäyksiä sekä kerroksellisia puolustuksia laajalle levinneitä uhkia vastaan. Nämä vaatimukset voivat sisältää monimutkaisempaa logiikkaa tai kohdistua tiettyihin hyökkäyksen edellytyksiin.

 Taso 3 vaatimukset

Taso 3 sisältää hallintakeinoja, jotka ovat tyypillisesti vaikeampia toteuttaa tai soveltuvat tilanteesta riippuen. Ne edustavat usein puolustuksen syvyyttä lisääviä mekanismeja tai lieventäviä toimia kapeiden, kohdennettujen tai korkean monimutkaisuuden hyökkäysten varalta.

#### Rooli (D/V)

Jokainen AISVS-vaatimus on merkitty ensisijaisen kohdeyleisön mukaan:

D – Kehittäjäkeskeiset vaatimukset
V – Tarkastajaan/tarkastaja-keskeiset vaatimukset
D/V – Merkityksellinen sekä kehittäjille että varmennusasiantuntijoille

## C1 Koulutusdatan hallinta ja vinouman hallinta

### Valvontatavoite

Koulutusdata on hankittava, käsiteltävä ja ylläpidettävä siten, että säilytetään alkuperä, turvallisuus, laatu ja oikeudenmukaisuus. Tämä täyttää lakisääteiset velvoitteet ja vähentää puolueellisuuden, myrkytyksen tai tietosuojarikkomusten riskiä koko tekoälyn elinkaaren ajan.

---

### C1.1 Koulutusdatan alkuperä

Pidä yllä todennettavissa olevaa luetteloa kaikista tietoaineistoista, hyväksy ainoastaan luotettavat lähteet ja kirjaa jokainen muutos auditointia varten.

 #1.1.1    Level: 1    Role: D/V
 Varmista, että pidetään ajan tasalla oleva luettelo jokaisesta harjoitusdatan lähteestä (alkuperä, vastuuhenkilö/omistaja, lisenssi, keräystapa, käyttötarkoitukseen liittyvät rajoitukset ja käsittelyhistoria).
 #1.1.2    Level: 1    Role: D/V
 Varmista, että vain laadun, edustavuuden, eettisen hankinnan ja lisenssivaatimusten tarkastamat aineistot sallitaan, mikä vähentää myrkytyksen, sisäistetyn vinouman ja immateriaalioikeuksien loukkaamisen riskejä.
 #1.1.3    Level: 1    Role: D/V
 Varmista, että tietojen minimointi on toteutettu siten, että tarpeettomat tai arkaluonteiset ominaisuudet suljetaan pois.
 #1.1.4    Level: 2    Role: D/V
 Varmista, että kaikki tietojoukon muutokset käyvät läpi kirjallisen hyväksymisprosessin.
 #1.1.5    Level: 2    Role: D/V
 Varmista, että merkintöjen/annotaatioiden laatu varmistetaan tarkistajien ristiintarkastuksilla tai yhteisymmärryksen kautta.
 #1.1.6    Level: 2    Role: D/V
 Varmista, että merkittäville koulutusdatasetille ylläpidetään "datakortteja" tai "datasheettejä", joissa kuvataan ominaisuudet, motivaatio, koostumus, keräysprosessit, esikäsittely sekä suositellut ja ei-suositellut käyttötavat.

---

### C1.2 Koulutusdatan turvallisuus ja eheys

Rajoita pääsyä, salaa tiedot levossa ja siirron aikana sekä tarkista eheys estääksesi manipulointia tai varkautta.

 #1.2.1    Level: 1    Role: D/V
 Varmista, että pääsynvalvonta suojaa tallennustilat ja putkistot.
 #1.2.2    Level: 2    Role: D/V
 Varmista, että aineistot ovat salattuja siirron aikana ja kaikille arkaluonteisille tai henkilöitä tunnistaville tiedoille (PII) myös levossa käyttäen alan standardien mukaisia kryptografisia algoritmeja ja avaintenhallintakäytäntöjä.
 #1.2.3    Level: 2    Role: D/V
 Varmista, että tietojen eheyttä varmistetaan tallennuksen ja siirron aikana käyttämällä kryptografisia tiivisteitä tai digitaalisia allekirjoituksia, ja että automatisoituja poikkeavuuksien tunnistamistekniikoita sovelletaan luvattomien muutosten tai vaurioiden, mukaan lukien kohdennetut tietomyrkytysyritykset, estämiseksi.
 #1.2.4    Level: 3    Role: D/V
 Varmista, että datasetin versiot seurataan palautuksen mahdollistamiseksi.
 #1.2.5    Level: 2    Role: D/V
 Varmista, että vanhentuneet tiedot poistetaan turvallisesti tai anonymisoidaan tietojen säilytyskäytäntöjen, sääntelyvaatimusten mukaisesti ja hyökkäyspinta-alan pienentämiseksi.

---

### C1.3 Esityksen täydellisyys ja oikeudenmukaisuus

Tunnista demografiset vinoumat ja ota käyttöön korjaustoimet, jotta mallin virheprosentit ovat tasapuolisia eri ryhmien välillä.

 #1.3.1    Level: 1    Role: D/V
 Varmista, että datasarjoille tehdään analyysi edustuksellisesta epätasapainosta ja mahdollisista puolueellisuuksista laillisesti suojeltujen ominaisuuksien (esim. rotu, sukupuoli, ikä) sekä muiden mallin sovellusalueeseen liittyvien eettisesti herkkiä piirteitä (esim. sosioekonominen asema, sijainti) koskevien tekijöiden osalta.
 #1.3.2    Level: 2    Role: D/V
 Varmista, että tunnistetut vinoumat on lievennetty dokumentoitujen strategioiden avulla, kuten uudelleen tasapainottaminen, kohdennettu aineiston lisäys, algoritmiset säädöt (esim. esikäsittely-, käsittely- ja jälkikäsittelytekniikat) tai uudelleen painotus, ja että lieventämisen vaikutus sekä oikeudenmukaisuuteen että koko mallin suorituskykyyn arvioidaan.
 #1.3.3    Level: 2    Role: D/V
 Varmista, että jälkikoulutuksen reiluusmittarit arvioidaan ja dokumentoidaan.
 #1.3.4    Level: 3    Role: D/V
 Varmista, että elinkaaren vinoumanhallintapolitiikka määrittelee vastuuhenkilöt ja tarkastelutiheyden.

---

### C1.4 Koulutusdatan merkintöjen laatu, eheys ja turvallisuus

Suojaa tunnisteet salauksella ja vaadi kaksoistarkastus kriittisille luokille.

 #1.4.1    Level: 2    Role: D/V
 Varmista, että merkintöjen/annotaatioiden laatu varmistetaan selkeiden ohjeiden, tarkastajien ristiintarkastusten, yksimielisyysmekanismien (esim. annotaattoreiden välisten sopimusten valvonta) sekä määriteltyjen menettelyjen avulla ristiriitojen ratkaisemiseksi.
 #1.4.2    Level: 2    Role: D/V
 Varmista, että kryptografisia tiivisteitä tai digitaalisia allekirjoituksia käytetään tunniste-artefaktien eheyttä ja aitoutta varmistamaan.
 #1.4.3    Level: 2    Role: D/V
 Varmista, että merkintäkäyttöliittymät ja -alustat toteuttavat vahvat pääsynvalvontamekanismit, ylläpitävät muokkaamattomuuden todistavia tarkastuslokimerkintöjä kaikista merkintätoiminnoista ja suojaavat luvattomalta muokkaukselta.
 #1.4.4    Level: 3    Role: D/V
 Varmista, että turvallisuuden, suojauksen tai oikeudenmukaisuuden kannalta kriittiset tunnisteet (esim. myrkyllisen sisällön tunnistaminen, kriittiset lääketieteelliset löydökset) saavat pakollisen riippumattoman kaksoistarkastuksen tai vastaavan vahvan varmennuksen.
 #1.4.5    Level: 2    Role: D/V
 Varmista, että vahingossa tallentunut tai välttämättä etiketeissä oleva arkaluonteinen tieto (mukaan lukien henkilötiedot) on peitetty, pseudonymisoitu, anonymisoitu tai salattu lepäävänä ja siirrettäessä, noudattaen tietojen minimoinnin periaatteita.
 #1.4.6    Level: 2    Role: D/V
 Varmista, että merkintäohjeet ja -ohjeistukset ovat kattavia, versiohallittuja ja vertaisarvioituja.
 #1.4.7    Level: 2    Role: D/V
 Varmista, että datakaaviot (mukaan lukien tunnisteet) on määritelty selkeästi ja versiohallittu.
 #1.8.2    Level: 2    Role: D/V
 Varmista, että ulkoistetut tai joukkorahoituksella toteutetut luokittelutyönkulut sisältävät teknisiä/prosessuaalisia turvatoimia tietojen luottamuksellisuuden, eheyden ja luokittelun laadun varmistamiseksi sekä datavuotojen estämiseksi.

---

### C1.5 Koulutusdatan laadunvarmistus

Yhdistä automatisoitu validointi, manuaaliset pistokokeet ja lokitettu korjaustoimenpiteet takaamaan tietojoukkojen luotettavuus.

 #1.5.1    Level: 1    Role: D
 Varmista, että automatisoidut testit havaitsevat muotoiluvirheet, null-arvot ja etikettien vääristymät jokaisessa tietojen vastaanotossa tai merkittävässä muunnoksessa.
 #1.5.2    Level: 1    Role: D/V
 Varmista, että virheelliset tietojoukot asetetaan karanteeniin auditointilokein.
 #1.5.3    Level: 2    Role: V
 Varmista, että manuaaliset pistokokeet alakohtaisten asiantuntijoiden toimesta kattavat tilastollisesti merkittävän otoksen (esim. ≥1 % tai 1 000 otosta, kumpi tahansa on suurempi, tai riskinarvioinnin määrittämänä) havaitakseen hienovaraisia laatuongelmia, joita automaatio ei tunnista.
 #1.5.4    Level: 2    Role: D/V
 Varmista, että korjaustoimenpiteet lisätään alkuperätietoihin.
 #1.5.5    Level: 2    Role: D/V
 Varmista, että laatukriteerit estävät heikkolaatuiset aineistot, ellei poikkeuksia ole hyväksytty.

---

### C1.6 Datan myrkytyksen havaitseminen

Sovella tilastollista poikkeavuuksien tunnistusta ja eristysprosesseja pysäyttämään vihamieliset lisäykset.

 #1.6.1    Level: 2    Role: D/V
 Varmista, että poikkeavuuksien havaitsemismenetelmiä (esim. tilastolliset menetelmät, poikkeamien tunnistus, upotusanalyysi) sovelletaan harjoitusdataan tietojen vastaanoton yhteydessä ja ennen merkittäviä harjoituskierroksia mahdollisten myrkytysiskujen tai tahattoman datan korruption havaitsemiseksi.
 #1.6.2    Level: 2    Role: D/V
 Varmista, että liputetut näytteet käynnistävät manuaalisen tarkastelun ennen koulutusta.
 #1.6.3    Level: 2    Role: V
 Varmista, että tulokset syötetään mallin turvallisuusdossieeriin ja tiedottavat jatkuvaa uhkatiedustelua.
 #1.6.4    Level: 3    Role: D/V
 Varmista, että tunnistuslogiikka päivitetään uudella uhkatiedolla.
 #1.6.5    Level: 3    Role: D/V
 Varmista, että verkkopohjaiset oppimispylväät valvovat jakauman siirtymää.
 #1.6.6    Level: 3    Role: D/V
 Varmista, että tietyt puolustukset tunnettuja datan myrkytys hyökkäystyyppejä vastaan (esim. luokittelun kääntäminen, takaportin liipaisimen lisääminen, vaikuttavien näytteiden hyökkäykset) otetaan huomioon ja toteutetaan järjestelmän riskiarvion ja datalähteiden perusteella.

---

### C1.7 Käyttäjätietojen poisto ja suostumuksen valvonta

Kunnioita poistopyyntöjä ja suostumuksen peruuttamisia kaikissa tietojoukoissa, varmuuskopioissa ja johdannaisissa artefakteissa.

 #1.7.1    Level: 1    Role: D/V
 Varmista, että poistoprosessit tyhjentävät ensisijaiset ja johdetut tiedot sekä arvioivat mallin vaikutukset, ja että vaikutukset asianomaisiin malleihin arvioidaan ja tarvittaessa korjataan (esim. uudelleenkoulutuksella tai uudelleensäätämisellä).
 #1.7.2    Level: 2    Role: D
 Varmista, että mekanismit ovat olemassa käyttäjän suostumuksen (ja peruuttamisten) laajuuden ja tilan seuraamiseksi ja kunnioittamiseksi koulutuksessa käytettävien tietojen osalta, ja että suostumus vahvistetaan ennen tietojen sisällyttämistä uusiin koulutusprosesseihin tai merkittäviin mallipäivityksiin.
 #1.7.3    Level: 2    Role: V
 Varmista, että työnkulut testataan vuosittain ja niistä pidetään lokia.

---

### C1.8 Toimitusketjun turvallisuus

Tarkasta ulkoiset datantoimittajat ja varmista eheys todennetuilla, salatuilla yhteyksillä.

 #1.8.1    Level: 2    Role: D/V
 Varmista, että kolmannen osapuolen datantoimittajat, mukaan lukien esikoulutettujen mallien ja ulkoisten tietoaineistojen tarjoajat, käyvät läpi turvallisuus-, tietosuoja-, eettisen hankinnan ja datalaadun due diligence -arvioinnin ennen kuin heidän datansa tai mallinsa integroidaan.
 #1.8.2    Level: 1    Role: D
 Varmista, että ulkoiset siirrot käyttävät TLS:ää/autentikointia ja eheystarkistuksia.
 #1.8.3    Level: 2    Role: D/V
 Varmista, että korkean riskin tietolähteille (esim. avoimen lähdekoodin aineistot, joiden alkuperä on tuntematon, tai arvostelematon toimittajat) kohdistetaan tehostettu tarkastelu, kuten suojatussa ympäristössä tehtävä analyysi, laajat laatu- ja vinoumatarkastukset sekä kohdennettu myrkytyksen havaitseminen, ennen niiden käyttöönottoa herkissä sovelluksissa.
 #1.8.4    Level: 3    Role: D/V
 Varmista, että kolmansilta osapuolilta saadut ennalta koulutetut mallit arvioidaan sisäistettyjen vinoumien, mahdollisten takaovien, niiden arkkitehtuurin eheys sekä alkuperäisen koulutusdatan alkuperä ennen hienosäätöä tai käyttöönottoa.

---

### C1.9 Vihamielisten näytteiden havaitseminen

Ota koulutusvaiheessa käyttöön menetelmiä, kuten vastustajakoulutus, parantaaksesi mallin kestävyyttä vastustajaesimerkkejä vastaan.

 #1.9.1    Level: 3    Role: D/V
 Varmista, että asianmukaiset puolustustoimenpiteet, kuten vastustajakoulutus (generoitujen vastustajaesimerkkien käyttö), datan laajentaminen häirittyjen syötteiden avulla tai kestävät optimointitekniikat, on toteutettu ja säädetty asianmukaisesti riskinarvioinnin perusteella.
 #1.9.2    Level: 2    Role: D/V
 Varmista, että jos käytetään vihamielistä harjoittelua, vihamielisten tietojoukkojen luominen, hallinta ja versionhallinta on dokumentoitu ja hallittu.
 #1.9.3    Level: 3    Role: D/V
 Varmista, että vihamielisen kestävyyden koulutuksen vaikutus mallin suorituskykyyn (sekä puhtaita että vihamielisiä syötteitä vastaan) ja reiluusmittareihin arvioidaan, dokumentoidaan ja seurataan.
 #1.9.4    Level: 3    Role: D/V
 Varmista, että vihamieliseen harjoitteluun ja robustisuuteen liittyvät strategiat tarkistetaan ja päivitetään säännöllisesti vastauksena kehittyviin vihamielisten hyökkäystekniikoihin.

---

### C1.10 Datan alkuperä ja jäljitettävyys

Seuraa jokaisen datapisteen koko matkaa lähteestä mallin syötteeksi auditoinnin ja häiriöiden hallinnan vuoksi.

 #1.10.1    Level: 2    Role: D/V
 Varmista, että kunkin datapisteen sukulaisuus, mukaan lukien kaikki muunnokset, laajennukset ja yhdistämiset, on tallennettu ja voidaan rekonstruoida.
 #1.10.2    Level: 2    Role: D/V
 Varmista, että jäljitettävyystiedot ovat muuttumattomia, turvallisesti tallennettuja ja saatavilla tarkastuksia tai tutkimuksia varten.
 #1.10.3    Level: 2    Role: D/V
 Varmista, että linjaselvitys kattaa sekä raakadatan että synteettisen datan.

---

### C1.11 Synteettisen datan hallinta

Varmista, että synteettisiä tietoja hallitaan asianmukaisesti, merkitään ja riskinarvioidaan.

 #1.11.1    Level: 2    Role: D/V
 Varmista, että kaikki synteettiset tiedot on selvästi merkitty ja erotettavissa todellisista tiedoista koko prosessin ajan.
 #1.11.2    Level: 2    Role: D/V
 Varmista, että synteettisen datan generointiprosessi, parametrit ja aiottu käyttötarkoitus on dokumentoitu.
 #1.11.3    Level: 2    Role: D/V
 Varmista, että synteettinen data on arvioitu riskien suhteen puolueellisuuden, yksityisyyden vuotamisen ja esitykseen liittyvien ongelmien osalta ennen sen käyttämistä koulutuksessa.

---

### C1.12 Tietojen käyttöoikeuden valvonta ja poikkeamien havaitseminen

Valvo ja hälytä epätavallisesta pääsystä koulutusdataan sisäpiirin uhkien tai tiedon vuotamisen havaitsemiseksi.

 #1.12.1    Level: 2    Role: D/V
 Varmista, että kaikki koulutusdataan kohdistuva pääsy kirjataan, mukaan lukien käyttäjä, aika ja toimenpide.
 #1.12.2    Level: 2    Role: D/V
 Varmista, että käyttölogit tarkastetaan säännöllisesti epätavallisten kuvioiden varalta, kuten suurten vientien tai uusista sijainneista tapahtuvan pääsyn osalta.
 #1.12.3    Level: 2    Role: D/V
 Varmista, että epäilyttävistä käyttöoikeustapahtumista luodaan hälytyksiä ja ne tutkitaan viipymättä.

---

### C1.13 Tietojen säilytys- ja vanhenemiskäytännöt

Määritä ja valvo tietojen säilytysaikoja minimoidaksesi tarpeettoman tietojen tallennuksen.

 #1.13.1    Level: 1    Role: D/V
 Varmista, että kaikille koulutusdatakokoelmille on määritelty yksiselitteiset säilytysajat.
 #1.13.2    Level: 2    Role: D/V
 Varmista, että tietoaineistot vanhenevat, poistetaan tai tarkistetaan poistettavaksi automaattisesti niiden elinkaaren lopussa.
 #1.13.3    Level: 2    Role: D/V
 Varmista, että säilytys- ja poistotoimenpiteet kirjataan ja että ne ovat auditoitavissa.

---

### C1.14 Sääntely- ja toimivaltaisuusvaatimusten noudattaminen

Varmista, että kaikki koulutusdata noudattaa sovellettavia lakeja ja asetuksia.

 #1.14.1    Level: 2    Role: D/V
 Varmista, että kaikille aineistoille on tunnistettu ja noudatetaan tietojen säilytyspaikkaa ja rajat ylittäviä siirtovaatimuksia.
 #1.14.2    Level: 2    Role: D/V
 Varmista, että toimialakohtaiset säädökset (esim. terveydenhuolto, rahoitus) tunnistetaan ja otetaan huomioon tiedon käsittelyssä.
 #1.14.3    Level: 2    Role: D/V
 Varmista, että vaatimustenmukaisuus asiaankuuluvien tietosuojalakien (esim. GDPR, CCPA) kanssa on dokumentoitu ja sitä tarkastellaan säännöllisesti.

---

### C1.15 Tiedon vesileimaus ja sormenjälkitunnistus

Havaitse luvaton uudelleenkäyttö tai luottamuksellisten tai arkaluonteisten tietojen vuotaminen.

 #1.15.1    Level: 3    Role: D/V
 Varmista, että aineistot tai osajoukot on vesileimattu tai sormenjäljitetty, kun se on mahdollista.
 #1.15.2    Level: 3    Role: D/V
 Varmista, että vesileimaus-/sormenjälkimenetelmissä ei synny harhaa tai yksityisyysriskejä.
 #1.15.3    Level: 3    Role: D/V
 Varmista, että säännöllisiä tarkastuksia tehdään havaitsemaan vesileimatun datan luvaton uudelleenkäyttö tai vuoto.

---

### C1.16 Rekisteröidyn oikeuksien hallinta

Tukea rekisteröidyn oikeuksia, kuten pääsyä tietoihin, oikaisua, rajoittamista ja vastustamista.

 #1.16.1    Level: 2    Role: D/V
 Varmista, että on olemassa mekanismeja, joilla voidaan vastata rekisteröidyn pyyntöihin pääsystä, oikaisusta, rajoittamisesta tai vastustamisesta.
 #1.16.2    Level: 2    Role: D/V
 Varmista, että pyynnöt kirjataan, seurataan ja täytetään laissa määrättyjen aikarajojen puitteissa.
 #1.16.3    Level: 2    Role: D/V
 Varmista, että rekisteröityjen oikeuksiin liittyvät prosessit testataan ja tarkastetaan säännöllisesti niiden toimivuuden varmistamiseksi.

---

### C1.17 Datasetin version vaikutusanalyysi

Arvioi datanmuutosten vaikutus ennen versioiden päivittämistä tai korvaamista.

 #1.17.1    Level: 2    Role: D/V
 Varmista, että vaikutusanalyysi tehdään ennen tietojoukon version päivittämistä tai korvaamista, kattaen mallin suorituskyvyn, oikeudenmukaisuuden ja vaatimustenmukaisuuden.
 #1.17.2    Level: 2    Role: D/V
 Varmista, että vaikutusanalyysin tulokset on dokumentoitu ja tarkastettu asianomaisten sidosryhmien toimesta.
 #1.17.3    Level: 2    Role: D/V
 Varmista, että palautussuunnitelmat ovat olemassa siltä varalta, että uudet versiot aiheuttavat hyväksymättömiä riskejä tai takapakkia.

---

### C1.18 Tietojen merkintätyövoiman turvallisuus

Varmista työntekijöiden, jotka osallistuvat datankirjaamiseen, turvallisuus ja eheys.

 #1.18.1    Level: 2    Role: D/V
 Varmista, että kaikki tietojen merkinnässä mukana olevat henkilöt ovat taustaselvitettyjä ja koulutettuja tietoturvaan ja yksityisyyden suojaan.
 #1.18.2    Level: 2    Role: D/V
 Varmista, että kaikki annotaattorit allekirjoittavat salassapito- ja vaitiolositoumukset.
 #1.18.3    Level: 2    Role: D/V
 Varmista, että annotaatioalustat toteuttavat pääsynvalvontaa ja valvovat sisäisiä uhkia.

---

### Viitteet

NIST AI Risk Management Framework
EU AI Act – Article 10: Data & Data Governance
MITRE ATLAS: Adversary Tactics for AI
Survey of ML Bias Mitigation Techniques – MDPI
Data Provenance & Lineage Best Practices – Nightfall AI
Data Labeling Quality Standards – LabelYourData
Training Data Poisoning Guide – Lakera.ai
CISA Advisory: Securing Data for AI Systems
ISO/IEC 23053: AI Management Systems Framework
IBM: What is AI Governance?
Google AI Principles
GDPR & AI Training Data – DataProtectionReport
Supply-Chain Security for AI Data – AppSOC
OpenAI Privacy Center – Data Deletion Controls
Adversarial ML Dataset – Kaggle

## C2 Käyttäjän syötteen validointi

### Ohjaustavoite

Käyttäjän syötteen vahva validointi on ensisijainen puolustuskeino eräitä tekoälyjärjestelmiin kohdistuvia haitallisimpia hyökkäyksiä vastaan. Kehoteinjektiohyökkäykset voivat ohittaa järjestelmän ohjeistukset, vuotaa arkaluontoisia tietoja tai ohjata mallin sallimattomaan käyttäytymiseen. Elleivät erilliset suodattimet ja ohjehierarkiat ole käytössä, tutkimukset osoittavat, että "monisäikeiset" jailbreak-hyökkäykset, jotka hyödyntävät erittäin pitkiä kontekstikkunoja, ovat tehokkaita. Lisäksi hienovaraiset vihamieliset häiriöhyökkäykset — kuten homoglyph-vaihdot tai leetspeak — voivat hiljaisesti muuttaa mallin päätöksiä.

---

### C2.1 Kehoteinjektiosuojus

Kehotteen injektointi on yksi suurimmista riskeistä tekoälyjärjestelmille. Tämän taktiikan torjumiseksi käytetään yhdistelmää staattisia kuviofilttereitä, dynaamisia luokittelijoita ja ohjehierarkian noudattamisen valvontaa.

 #2.1.1    Level: 1    Role: D/V
 Varmista, että käyttäjän syötteet tarkistetaan jatkuvasti päivitettävään tunnettuja kehotteiden injektiomalleja (jailbreak-avainsanoja, "ohita edellinen", roolipelausketjuja, epäsuoria HTML/URL-hyökkäyksiä) sisältävään kirjastoon.
 #2.1.2    Level: 1    Role: D/V
 Varmista, että järjestelmä noudattaa ohjehierarkiaa, jossa järjestelmä- tai kehittäjäviestit ohittavat käyttäjän ohjeet, myös laajennetun kontekstikehyksen jälkeen.
 #2.1.3    Level: 2    Role: D/V
 Varmista, että vastustava arviointi (esim. Red Teamin "many-shot" -kehotteet) suoritetaan ennen jokaista mallin tai kehotemallin julkaisua, asettaen onnistumisprosentin kynnykset ja automaattiset estimet regressioiden varalta.
 #2.1.4    Level: 2    Role: D
 Varmista, että kolmannen osapuolen sisällöstä (verkkosivut, PDF:t, sähköpostit) peräisin olevat kehotteet puhdistetaan eristetyssä jäsennysympäristössä ennen kuin ne liitetään pääkehoteeseen.
 #2.1.5    Level: 3    Role: D/V
 Varmista, että kaikki kehotteiden suodatussääntöjen päivitykset, luokittelijan malliversiot ja estolistamuutokset ovat versiohallittuja ja tarkastettavissa.

---

### C2.2 Vihamielisten esimerkkien vastustuskyky

Luonnollisen kielen käsittelyn (NLP) mallit ovat edelleen alttiita hienovaraisille merkkien tai sanojen tason häiriöille, jotka ihmiset usein ohittavat, mutta joita mallit yleensä luokittelevat väärin.

 #2.2.1    Level: 1    Role: D
 Varmista, että perus syötteen normalisointivaiheet (Unicode NFC, homoglyph-kartoitus, välilyöntien trimmaus) suoritetaan ennen tokenisointia.
 #2.2.2    Level: 2    Role: D/V
 Varmista, että tilastollinen poikkeamien havaitseminen merkitsee syötteitä, joilla on epätavallisen korkea muokkausetäisyys kielinormeihin nähden, liiallinen toistuvien tokenien määrä tai epänormaalit upotusetäisyydet.
 #2.2.3    Level: 2    Role: D
 Varmista, että päättelyputki tukee valinnaisia vastustavaan harjoitteluun kovetettuja mallivariantteja tai puolustuskerroksia (esim. satunnaistaminen, puolustava tislanta) korkean riskin päätepisteille.
 #2.2.4    Level: 2    Role: V
 Varmista, että epäillyt vastustajan syötteet asetetaan karanteeniin ja kirjataan täydellisten tietomassojen kanssa (henkilötietojen poistamisen jälkeen).
 #2.2.5    Level: 3    Role: D/V
 Varmista, että robustiuden mittarit (tunnettujen hyökkäyssarjojen onnistumisprosentti) seurataan ajan kuluessa ja että regressiot aiheuttavat julkaisun eston.

---

### C2.3 Skeeman, tyypin ja pituuden validointi

Muodottomat tai liian suuret syötteet sisältävät tekoälyhyökkäykset voivat aiheuttaa jäsentämisvirheitä, kehotteiden leviämistä kenttien yli ja resurssien loppumista. Tiukka skeeman valvonta on myös edellytys determinististen työkalukutsujen suorittamisessa.

 #2.3.1    Level: 1    Role: D
 Varmista, että jokainen API- tai funktiokutsupiste määrittelee selkeän syöttökaavion (JSON Schema, Protobuf tai multimodaalinen vastaava) ja että syötteet validoidaan ennen kehotteen koontia.
 #2.3.2    Level: 1    Role: D/V
 Varmista, että syötteet, jotka ylittävät enimmäismäärän tavuissa tai tokeneissa, hylätään turvallisella virheellä eikä niitä koskaan leikata hiljaa.
 #2.3.3    Level: 2    Role: D/V
 Varmista, että tyyppitarkistukset (esim. numeeriset arvovälit, enum-arvot, MIME-tyypit kuville/äänelle) toteutetaan palvelinpuolella, ei pelkästään asiakasohjelmakoodissa.
 #2.3.4    Level: 2    Role: D
 Varmista, että semanttiset validoijat (esim. JSON Schema) toimivat vakioaikaisesti estääkseen algoritmisen palvelunestohyökkäyksen.
 #2.3.5    Level: 3    Role: V
 Varmista, että validoinnin epäonnistumiset kirjataan sensuroituine tietosisältöineen ja yksiselitteisine virhekoodeineen turvallisuuden arvioinnin helpottamiseksi.

---

### C2.4 Sisällön ja politiikan tarkastus

Kehittäjien tulisi pystyä tunnistamaan syntaktisesti kelvolliset kehotteet, jotka pyytävät kiellettyä sisältöä (kuten laittomia ohjeita, vihapuhetta ja tekijänoikeudella suojattua tekstiä) ja estämään niiden leviämisen.

 #2.4.1    Level: 1    Role: D
 Varmista, että sisällönluokittelija (nollakosketus tai hienosäädetty) arvioi jokaisen syötteen väkivallan, itsehaitan, vihan, seksuaalisen sisällön ja laittomien pyyntöjen osalta, käyttäen määriteltävissä olevia kynnysarvoja.
 #2.4.2    Level: 1    Role: D/V
 Varmista, että politiikkoja rikkovat syötteet saavat vakioidut hylkäykset tai turvalliset täydennykset, jotta ne eivät siirry myöhempiin suurten kielimallien kutsuihin.
 #2.4.3    Level: 2    Role: D
 Varmista, että seulontamalli tai sääntöjoukko koulutetaan uudelleen/päivitetään vähintään neljännesvuosittain, ottaen huomioon äskettäin havaittuja jailbreak- tai politiikan kiertämismalleja.
 #2.4.4    Level: 2    Role: D
 Varmista, että seulonta noudattaa käyttäjäkohtaisia politiikkoja (ikä, alueelliset lakisääteiset rajoitukset) ominaisuuksiin perustuvien sääntöjen avulla, jotka ratkaistaan pyynnön yhteydessä.
 #2.4.5    Level: 3    Role: V
 Varmista, että seulontalokit sisältävät luokittelijan luottamusarvot ja politiikkakategorian tunnisteet SOC-korrelointia ja tulevaa red teamin toistoa varten.

---

### C2.5 Syöttönopeuden rajoittaminen ja väärinkäytösten ehkäisy

Kehittäjien tulisi estää väärinkäyttö, resurssien ylikuormitus ja automatisoidut hyökkäykset tekoälyjärjestelmiä vastaan rajoittamalla syötteen määrää ja tunnistamalla poikkeavat käyttökäyttäytymismallit.

 #2.5.1    Level: 1    Role: D/V
 Varmista, että käyttäjäkohtaiset, IP-osoitekohtaiset ja API-avainkohtaiset käyttörajoitukset otetaan käyttöön kaikilla syöttöpisteillä.
 #2.5.2    Level: 2    Role: D/V
 Varmista, että purkaus- ja jatkuvat nopeusrajoitukset on säädetty estämään palvelunestohyökkäykset (DoS) ja raakavoimahyökkäykset.
 #2.5.3    Level: 2    Role: D/V
 Varmista, että poikkeavat käyttökuviot (esim. nopeasti peräkkäiset pyynnöt, syötteen tulva) laukaisevat automaattiset esto- tai eskalointitoimenpiteet.
 #2.5.4    Level: 3    Role: V
 Varmista, että väärinkäytön estolokit säilytetään ja tarkastetaan tunnistettavien hyökkäyskuvioiden varalta.

---

### C2.6 Monimodaalinen syötteen validointi

AI-järjestelmien tulisi sisältää vahva validointi tekstittömille syötteille (kuvat, ääni, tiedostot) estääkseen injektoinnin, kiertämisen tai resurssien väärinkäytön.

 #2.6.1    Level: 1    Role: D
 Varmista, että kaikki ei-tekstimuotoiset syötteet (kuvat, äänet, tiedostot) tarkistetaan tyypin, koon ja muodon osalta ennen käsittelyä.
 #2.6.2    Level: 2    Role: D/V
 Varmista, että tiedostot skannataan haittaohjelmien ja steganografisten tietojenkantajien varalta ennen syöttämistä.
 #2.6.3    Level: 2    Role: D/V
 Varmista, että kuva- ja ääniosat tarkastetaan vihamielisten häiriöiden tai tunnettujen hyökkäyskuvioiden varalta.
 #2.6.4    Level: 3    Role: V
 Varmista, että multimodaaliset syötteen validointivirheet kirjataan lokiin ja laukaisevat hälytykset tutkintaa varten.

---

### C2.7 Syötteen alkuperä ja attribuutio

Tekoälyjärjestelmien tulisi tukea tarkastuksia, väärinkäytösten seurantaa ja vaatimustenmukaisuutta seuraamalla ja merkitsemällä kaikkien käyttäjäsyötteiden alkuperät.

 #2.7.1    Level: 1    Role: D/V
 Varmista, että kaikki käyttäjän syötteet merkitään metatiedoilla (käyttäjätunnus, istunto, lähde, aikaleima, IP-osoite) sisäänottovaiheessa.
 #2.7.2    Level: 2    Role: D/V
 Varmista, että alkuperätietojen metatiedot säilyvät ja ovat tarkastettavissa kaikille käsitellyille syötteille.
 #2.7.3    Level: 2    Role: D/V
 Varmista, että poikkeavat tai epäluotettavat syöttölähteet tunnistetaan ja ne altistetaan tehostetulle tarkastelulle tai estetään.

---

### C2.8 Reaaliaikainen adaptiivinen uhkien tunnistus

Kehittäjien tulisi käyttää kehittyneitä uhkien tunnistusjärjestelmiä tekoälylle, jotka sopeutuvat uusiin hyökkäyskuvioihin ja tarjoavat reaaliaikaista suojaa kootun kuvion tunnistuksen avulla.

 #2.8.1    Level: 1    Role: D/V
 Varmista, että uhkien tunnistuskuviot on käännetty optimoiduiksi säännöllisen lausekkeen (regex) moottoreiksi, jotka tarjoavat korkean suorituskyvyn reaaliaikaiseen suodatukseen minimaalisen viiveen vaikutuksella.
 #2.8.2    Level: 1    Role: D/V
 Varmista, että uhkien havaitsemisjärjestelmät ylläpitävät erillisiä mallikirjastoja eri uhkaluokille (kehotteiden injektointi, haitallinen sisältö, arkaluonteiset tiedot, järjestelmäkomennot).
 #2.8.3    Level: 2    Role: D/V
 Varmista, että mukautuva uhkien tunnistus sisältää koneoppimismallit, jotka päivittävät uhkien herkkyyttä hyökkäysten tiheyden ja onnistumisprosenttien perusteella.
 #2.8.4    Level: 2    Role: D/V
 Varmista, että reaaliaikaiset uhkatiedustelusyötteet päivittävät automaattisesti mallikirjastot uusilla hyökkäysallekirjoituksilla ja kompromissin tunnusmerkeillä (IOCs).
 #2.8.5    Level: 3    Role: D/V
 Varmista, että uhkien tunnistuksen väärien positiivisten osuuksia seurataan jatkuvasti ja kaavojen spesifisyyttä säädetään automaattisesti minimoimaan laillisten käyttötapausten häiriöt.
 #2.8.6    Level: 3    Role: D/V
 Varmista, että kontekstuaalinen uhka-analyysi ottaa huomioon syötteen lähteen, käyttäytymismallit ja istunnon historian parantaakseen tunnistustarkkuutta.
 #2.8.7    Level: 3    Role: D/V
 Varmista, että uhkien tunnistus suorituskykymittarit (tunnistusaste, käsittelyviive, resurssien käyttö) seurataan ja optimoidaan reaaliajassa.

---

### C2.9 Monimodaalinen tietoturvan varmistusputkisto

Kehittäjien tulisi tarjota tietoturvan validointi teksti-, kuva-, ääni- ja muille tekoälyn syöttömuodoille erityyppisten uhkien havaitsemisen ja resurssien eristyksen avulla.

 #2.9.1    Level: 1    Role: D/V
 Varmista, että jokaisella syöttömodaliteetilla on omistetut tietoturvatarkastajat, joilla on dokumentoidut uhkamallit (teksti: käskeiden injektio, kuvat: steganografia, ääni: spektrikuvahyökkäykset) ja tunnistusrajat.
 #2.9.2    Level: 2    Role: D/V
 Varmista, että multimodaaliset syötteet käsitellään eristetyissä hiekkalaatikoissa, joilla on määritellyt resurssirajat (muisti, suoritin, käsittelyaika) kullekin modaalisuustyypille, ja nämä on dokumentoitu turvallisuuspolitiikoissa.
 #2.9.3    Level: 2    Role: D/V
 Varmista, että ristiinmodalinen hyökkäysten havaitseminen tunnistaa koordinoidut hyökkäykset, jotka ulottuvat useisiin syötetyyppeihin (esim. steganografiset kuormitukset kuvissa yhdistettynä kehotteen injektointiin tekstissä) korrelaatiosääntöjen ja hälytysten generoinnin avulla.
 #2.9.4    Level: 3    Role: D/V
 Varmista, että monimuotoiset validointivirheet laukaisevat yksityiskohtaisen lokituksen, joka sisältää kaikki syötteen muodot, validointitulokset, uhkapisteet ja korrelaatioanalyysin strukturoiduissa lokimuodoissa SIEM-integraatiota varten.
 #2.9.5    Level: 3    Role: D/V
 Varmista, että modality-kohtaiset sisältöluokittelijat päivitetään dokumentoitujen aikataulujen mukaisesti (vähintään neljännesvuosittain) uusilla uhkamalleilla, vastustavilla esimerkeillä ja suorituskykymittareilla, jotka pysyvät perustasoa korkeammalla.

---

### Viitteet

LLM01:2025 Prompt Injection – OWASP Top 10 for LLM & Generative AI Security
Generative AI's Biggest Security Flaw Is Not Easy to Fix
Many-shot jailbreaking \ Anthropic
$PDF$ OpenAI GPT-4.5 System Card
Notebook for the CheckThat Lab at CLEF 2024
Mitigate jailbreaks and prompt injections – Anthropic
Chapter 3 MITRE ATT\&CK – Adversarial Model Analysis
OWASP Top 10 for LLM Applications 2025 – WorldTech IT
OWASP Machine Learning Security Top Ten
Few words about AI Security – Jussi Metso
How To Ensure LLM Output Adheres to a JSON Schema | Modelmetry
Easily enforcing valid JSON schema following – API
AI Safety + Cybersecurity R\&D Tracker – Fairly AI
Anthropic makes 'jailbreak' advance to stop AI models producing harmful results
Pattern matching filter rules - IBM
Real-time Threat Detection

## C3-mallin elinkaaren hallinta ja muutosten valvonta

### Ohjaustavoite

Tekoälyjärjestelmien on otettava käyttöön muutoshallintaprosessit, jotka estävät luvattomat tai turvattomat mallimuutokset pääsemästä tuotantoon. Tämä hallintamekanismi varmistaa mallin eheyden koko elinkaaren ajan – kehityksestä käyttöönottoon ja käytöstä poistoon – mikä mahdollistaa nopean tapauskohtaisen reagoinnin ja ylläpitää vastuullisuuden kaikille muutoksille.

Ydinturvatavoite: Vain valtuutetut ja validoidut mallit pääsevät tuotantoon käyttämällä hallittuja prosesseja, jotka ylläpitävät eheyttä, jäljitettävyyttä ja palautettavuutta.

---

### C3.1 Mallin valtuutus ja eheys

Vain valtuutetut mallit, joiden eheys on vahvistettu, pääsevät tuotantoympäristöihin.

 #3.1.1    Level: 1    Role: D/V
 Varmista, että kaikki mallin artefaktit (painot, konfiguraatiot, tokenisaattorit) on kryptografisesti allekirjoitettu valtuutettujen tahojen toimesta ennen käyttöönottoa.
 #3.1.2    Level: 1    Role: D/V
 Varmista, että mallin eheys tarkistetaan käyttöönottohetkellä ja allekirjoituksen varmennuksen epäonnistuminen estää mallin lataamisen.
 #3.1.3    Level: 2    Role: D/V
 Varmista, että mallin alkuperätiedot sisältävät valtuuttavan tahon henkilöllisyyden, koulutusdatasta laskettavat tarkistussummat, validointitestien tulokset läpäisy-/epäonnistumistilanteineen sekä luontihetken ajan leiman.
 #3.1.4    Level: 2    Role: D/V
 Varmista, että kaikki mallin artefaktit käyttävät semanttista versiota (MAJOR.MINOR.PATCH) ja niille on dokumentoidut kriteerit, jotka määrittävät, milloin kukin version komponentti kasvaa.
 #3.1.5    Level: 2    Role: V
 Varmista, että riippuvuuksien seuranta ylläpitää reaaliaikaista inventaariota, joka mahdollistaa kaikkien kuluttavien järjestelmien nopean tunnistamisen.

---

### C3.2 Mallin validointi ja testaus

Mallien on läpäistävä määritellyt turvallisuus- ja suojausvarmistukset ennen käyttöönottoa.

 #3.2.1    Level: 1    Role: D/V
 Varmista, että mallit käyvät läpi automatisoidun turvallisuustestauksen, joka sisältää syötteen validoinnin, tulosten puhdistuksen ja turvallisuusarvioinnit ennalta sovittujen organisaation läpäisy/hylätty -rajojen mukaisesti ennen käyttöönottoa.
 #3.2.2    Level: 1    Role: D/V
 Varmista, että validointivirheet estävät automaattisesti mallin käyttöönoton, vaikka siihen olisi myönnetty nimenomainen poikkeuslupa ennalta määrätyiltä valtuutetuilta henkilöiltä, joilla on dokumentoidut liiketoiminnalliset perustelut.
 #3.2.3    Level: 2    Role: V
 Varmista, että testitulokset on kryptografisesti allekirjoitettu ja muuttumattomasti yhdistetty tarkastettavan malliversion hajautusarvoon.
 #3.2.4    Level: 2    Role: D/V
 Varmista, että hätäkäyttöönotot edellyttävät dokumentoitua tietoturvariskien arviointia ja hyväksyntää ennalta nimetyltä tietoturvaviranomaiselta sovittujen aikarajojen puitteissa.

---

### C3.3 Hallittu käyttöönotto ja takaisinperintä

Malli käyttöönotot on oltava hallittuja, valvottuja ja palautettavissa.

 #3.3.1    Level: 1    Role: D
 Varmista, että tuotantoon siirroissa käytetään asteittaisen käyttöönoton mekanismeja (kanariasiirrot, sinivihreät käyttöönotot) automaattisten palautustoimintojen laukaisijoilla, jotka perustuvat ennalta sovittuihin virhesuhteisiin, viivekynnysarvoihin tai turvallisuushälytystekijöihin.
 #3.3.2    Level: 1    Role: D/V
 Varmista, että peruutusominaisuudet palauttavat täydellisen mallin tilan (painot, konfiguraatiot, riippuvuudet) atomisesti ennalta määriteltyjen organisaation aikarajojen sisällä.
 #3.3.3    Level: 2    Role: D/V
 Varmista, että käyttöönotto-prosessit validoivat kryptografiset allekirjoitukset ja laskevat eheystarkistussummat ennen mallin aktivointia, epäonnistuen käyttöönotossa kaikissa epäyhtäpään tapauksissa.
 #3.3.4    Level: 2    Role: D/V
 Varmista, että hätätilan mallin sammutusominaisuudet voivat poistaa mallin päätepisteet käytöstä ennalta määritettyjen vasteaikojen puitteissa automaattisten piirikytkinten tai manuaalisten hätäkytkinten avulla.
 #3.3.5    Level: 2    Role: V
 Varmista, että palautusartifaktit (aiemmat malliversiot, konfiguraatiot, riippuvuudet) säilytetään organisaation politiikkojen mukaisesti muuttumattomassa tallennustilassa häiriötilanteiden hallintaa varten.

---

### C3.4 Muutosten Vastuu ja Tarkastus

Kaikkien mallin elinkaaren muutosten on oltava jäljitettäviä ja auditoitavia.

 #3.4.1    Level: 1    Role: V
 Varmista, että kaikki mallimuutokset (käyttöönotto, konfigurointi, poistaminen) tuottavat muuttumattomia tarkastustietueita, jotka sisältävät aikaleiman, todennetun käyttäjätunnuksen, muutostyypin sekä ennen ja jälkeen -tilat.
 #3.4.2    Level: 2    Role: D/V
 Varmista, että tarkastuslokin käyttö edellyttää asianmukaista valtuutusta ja että kaikki käyttöyritykset kirjataan käyttäjän tunnistetiedoilla ja aikaleimalla.
 #3.4.3    Level: 2    Role: D/V
 Varmista, että kehotemallit ja järjestelmäviestit ovat versionhallinnassa git-repositorioissa, ja että pakolliseen koodikatselmukseen sekä nimettyjen tarkastajien hyväksyntään vaaditaan ennen käyttöönottoa.
 #3.4.4    Level: 2    Role: V
 Varmista, että auditointitiedot sisältävät riittävät yksityiskohdat (mallin hajautusarvot, kokoonpanon tilannevedokset, riippuvuuksien versiot) mahdollistamaan mallin tilan täydellisen rekonstruoinnin mille tahansa ajankohdalle säilytysajan puitteissa.

---

### C3.5 Turvalliset kehityskäytännöt

Mallin kehitys- ja koulutusprosessien on noudatettava turvallisia käytäntöjä kompromissien estämiseksi.

 #3.5.1    Level: 1    Role: D
 Varmista, että mallin kehitys-, testaus- ja tuotantoympäristöt ovat fyysisesti tai loogisesti erillisiä. Niillä ei ole jaettua infrastruktuuria, erilliset käyttöoikeuksien hallinnat ja eristetyt tietovarastot.
 #3.5.2    Level: 1    Role: D
 Varmista, että mallin koulutus ja hienosäätö tapahtuvat eristetyissä ympäristöissä, joilla on hallittu verkkoyhteys.
 #3.5.3    Level: 1    Role: D/V
 Varmista, että koulutusdatan lähteet tarkistetaan eheystarkastuksilla ja todentavat luotettavat lähteet, joilla on dokumentoitu hallintaketju, ennen käyttöä mallin kehityksessä.
 #3.5.4    Level: 2    Role: D
 Varmista, että mallin kehitysartifaktit (hyperparametrit, koulutusskriptit, konfiguraatiotiedostot) tallennetaan versionhallintaan ja niiden käyttö koulutuksessa edellyttää vertaisarviointihyvääksyntää.

---

### C3.6 Mallin poistaminen käytöstä ja käytöstäpoisto

Mallit on poistettava turvallisesti käytöstä, kun niitä ei enää tarvita tai kun tietoturvaongelmia havaitaan.

 #3.6.1    Level: 1    Role: D
 Varmista, että mallin eläkkeelle siirtymisprosessit skannaavat automaattisesti riippuvuuskaaviot, tunnistavat kaikki kuluttajajärjestelmät ja tarjoavat ennalta sovitut ennakkoilmoitusajat ennen käytöstä poistamista.
 #3.6.2    Level: 1    Role: D/V
 Varmista, että eläkkeelle jääneet mallin artefaktit pyyhitään turvallisesti kryptografisella poistolla tai monikertaisella ylikirjoituksella dokumentoitujen tietojen säilytyskäytäntöjen mukaisesti, ja että tuhoutumisesta on varmennettu todistus.
 #3.6.3    Level: 2    Role: V
 Varmista, että mallin poistumistapahtumat kirjataan aikaleiman ja toimijan tunnisteen kanssa, ja mallin allekirjoitukset peruutetaan uudelleenkäytön estämiseksi.
 #3.6.4    Level: 2    Role: D/V
 Varmista, että hätätilannemallin poistaminen käytöstä voi estää mallin käytön ennalta määritettyjen hätätilannevasteaikojen puitteissa automatisoitujen katkaisukytkimien avulla, jos kriittisiä tietoturva-aukkoja havaitaan.

---

### Viitteet

MLOps Principles
Securing AI/ML Ops – Cisco.com
Audit logs security: cryptographically signed tamper-proof logs
Machine Learning Model Versioning: Top Tools & Best Practices
AI Hygiene Starts with Models and Data Loaders – SEI Blog
How to handle versioning and rollback of a deployed ML model?
Reinforcement fine-tuning – OpenAI API
Auditing Machine Learning models: Governance, Data Security and …
Adversarial Training to Improve Model Robustness
What is AI adversarial robustness? – IBM Research
Exploring Data Provenance: Ensuring Data Integrity and Authenticity
MITRE ATLAS
AWS Prescriptive Guidance – Best practices for retiring applications …

## C4-infrastruktuuri, konfiguraatio ja käyttöönoton turvallisuus

### Hallintatavoite

Tekoälyinfrastruktuuri on vahvistettava etuoikeuksien laajentamista, toimitusketjun manipulointia ja sivuttaisliikettä vastaan turvallisen konfiguraation, suorituseristyksen, luotettavien käyttöönotto-putkien ja kattavan valvonnan avulla. Vain valtuutetut, validoidut infrastruktuurin komponentit ja konfiguraatiot pääsevät tuotantoon hallittujen prosessien kautta, jotka ylläpitävät turvallisuutta, eheyttä ja auditoitavuutta.

Ydin turvallisuustavoite: Vain kryptografisesti allekirjoitetut, haavoittuvuusskannatut infrastruktuurikomponentit pääsevät tuotantoon automaattisten validointiputkien kautta, jotka noudattavat turvallisuuspolitiikkoja ja ylläpitävät muuttumattomia tarkastusepäkirjoja.

---

### C4.1 Suoritusaikaympäristön eristäminen

Estä säiliöiden karkailu ja oikeuksien korotus kernel-tason eristysprimitivien sekä pakollisten käyttöoikeuksien valvonnan avulla.

 #4.1.1    Level: 1    Role: D/V
 Varmista, että kaikista tekoälysäilöistä poistetaan KAIKKI Linuxin käyttöoikeudet lukuun ottamatta CAP_SETUID-, CAP_SETGID- ja turvallisuusperustaasiakirjoissa eksplisiittisesti vaadittuja käyttöoikeuksia.
 #4.1.2    Level: 1    Role: D/V
 Varmista, että seccomp-profiilit estävät kaikki järjestelmäkutsut paitsi ne, jotka ovat ennalta hyväksytyissä sallituissa listoissa, ja että rikkomukset johtavat kontin lopettamiseen ja turvallisuushälytysten luomiseen.
 #4.1.3    Level: 2    Role: D/V
 Varmista, että tekoälytyökuormat ajetaan vain-luku -juurihakemistojärjestelmillä, väliaikaiselle datalle käytetään tmpfs:ää ja pysyvälle datalle nimettyjä volumeeja, joihin on sovellettu noexec-liitinvaihtoehtoja.
 #4.1.4    Level: 2    Role: D/V
 Varmista, että eBPF-pohjainen ajonaikainen valvonta (Falco, Tetragon tai vastaava) havaitsee oikeuksien korottamisyritykset ja tappaa automaattisesti rikkomukseen syyllistyneet prosessit organisaation vasteaikavaatimusten mukaisesti.
 #4.1.5    Level: 3    Role: D/V
 Varmista, että korkean riskin tekoälykuormitukset suoritetaan laitteistollisesti eristetyissä ympäristöissä (Intel TXT, AMD SVM tai omistetut bare-metal-solmut) käyttäen todentamisvarmistusta.

---

### C4.2 Turvatut rakennus- ja käyttöönotto-putket

Varmista kryptografinen eheys ja toimitusketjun turvallisuus toistettavien rakennosten ja allekirjoitettujen artefaktien avulla.

 #4.2.1    Level: 1    Role: D/V
 Varmista, että infrastruktuuri koodina skannataan työkaluilla (tfsec, Checkov tai Terrascan) jokaisessa commitissa, ja estä yhdistämiset, jos löydökset ovat kriittisiä tai vakavia (CRITICAL tai HIGH).
 #4.2.2    Level: 1    Role: D/V
 Varmista, että konttien rakennukset ovat toistettavissa identtisillä SHA256-tiivisteillä eri rakennusten välillä, ja luo SLSA-tason 3 alkuperätodistukset, jotka on allekirjoitettu Sigstorella.
 #4.2.3    Level: 2    Role: D/V
 Varmista, että konttikuvat sisältävät CycloneDX- tai SPDX-SBOM-tiedostot ja että ne on allekirjoitettu Cosignilla ennen kuvien työntämistä rekisteriin, ja hylkää allekirjoittamattomat kuvat käyttöönoton yhteydessä.
 #4.2.4    Level: 2    Role: D/V
 Varmista, että CI/CD-putkistot käyttävät OIDC-tunnuksia HashiCorp Vaultista, AWS IAM -rooleista tai Azure Managed Identitystä, joiden voimassaoloaika ei ylitä organisaation turvallisuuspolitiikan rajoja.
 #4.2.5    Level: 2    Role: D/V
 Varmista, että Cosign-allekirjoitukset ja SLSA-lähdetiedot validoidaan käyttöönoton aikana ennen säilön suorittamista ja että varmennusvirheet aiheuttavat käyttöönoton epäonnistumisen.
 #4.2.6    Level: 2    Role: D/V
 Varmista, että käännösympäristöt toimivat väliaikaisissa säiliöissä tai virtuaalikoneissa ilman pysyvää tallennustilaa ja tuotantoverkon VPC:iden kanssa eristettynä.

---

### C4.3 Verkkoturva ja pääsynvalvonta

Toteuta nollaluottamusverkot oletuskieltopolitiikoilla ja salatuilla viestintäyhteyksillä.

 #4.3.1    Level: 1    Role: D/V
 Varmista, että Kubernetes NetworkPolicies tai vastaava toteuttaa oletusarvoisen eston sisääntulevaan/ulosmeno-liikenteeseen ja sallii eksplisiittisesti vain tarvittavat portit (443, 8080 jne.).
 #4.3.2    Level: 1    Role: D/V
 Varmista, että SSH (portti 22), RDP (portti 3389) ja pilven metatiedon päätepisteet (169.254.169.254) ovat estettyjä tai vaativat varmennepohjaisen todennuksen.
 #4.3.3    Level: 2    Role: D/V
 Varmista, että lähtevää liikennettä suodatetaan HTTP/HTTPS-proksien (Squid, Istio tai pilven NAT-porttien) kautta käyttämällä sallittujen verkkotunnusten luetteloita, ja estetyt pyynnöt kirjataan.
 #4.3.4    Level: 2    Role: D/V
 Varmista, että palveluiden välinen viestintä käyttää molemminpuolista TLS:ää, jossa sertifikaatit kiertävät organisaation politiikan mukaisesti ja sertifikaattien validointi toteutetaan (ei ohiteta varmennuksen tarkistuksia).
 #4.3.5    Level: 2    Role: D/V
 Varmista, että tekoälyinfrastruktuuri toimii omistetuissa VPC:issä/VNet:eissä ilman suoraa internet-yhteyttä ja kommunikoi ainoastaan NAT-porttien tai bastion-palvelimien kautta.

---

### C4.4 Salaisuuksien ja kryptografisten avainten hallinta

Suojaa tunnistetiedot laitteistopohjaisella tallennuksella ja automaattisella kierrätyksellä nollaluottamuksen pääsynhallinnalla.

 #4.4.1    Level: 1    Role: D/V
 Varmista, että salaisuudet tallennetaan HashiCorp Vaultiin, AWS Secrets Manageriin, Azure Key Vaultiin tai Google Secret Manageriin AES-256-salauksella lepotilassa.
 #4.4.2    Level: 1    Role: D/V
 Varmista, että salausavaimet luodaan FIPS 140-2 Tason 2 HSM-laitteissa (AWS CloudHSM, Azure Dedicated HSM) avainten kierron mukaisesti organisaation salauspolitiikan mukaisesti.
 #4.4.3    Level: 2    Role: D/V
 Varmista, että salaisuuksien kierto on automatisoitu niin, että käyttöönotto tapahtuu ilman käyttökatkoa ja kierto käynnistyy välittömästi henkilöstömuutosten tai turvallisuuspoikkeamien yhteydessä.
 #4.4.4    Level: 2    Role: D/V
 Varmista, että konttikuvat skannataan työkaluilla (GitLeaks, TruffleHog tai detect-secrets), jotka estävät käännökset, jotka sisältävät API-avaimia, salasanoja tai sertifikaatteja.
 #4.4.5    Level: 2    Role: D/V
 Varmista, että tuotannon salainen pääsy vaatii monivaiheisen todennuksen (MFA) laitteistotunnisteilla (YubiKey, FIDO2) ja että siihen liittyvät toimet kirjataan muuttumattomiin auditointilokeihin käyttäjäidentiteettien ja aikaleimojen kanssa.
 #4.4.6    Level: 2    Role: D/V
 Varmista, että salaisuudet syötetään Kubernetes-salaisuuksien, liitettyjen volyymien tai init-konttien kautta, ja varmista, ettei salaisuuksia koskaan upoteta ympäristömuuttujiin tai kuviin.

---

### C4.5 AI-kuormituksen säiliöinti ja validointi

Eristä epäluotettavat tekoälymallit suojattuihin hiekkalaatikoihin kattavalla käyttäytymisanalyysillä.

 #4.5.1    Level: 1    Role: D/V
 Varmista, että ulkoiset tekoälymallit suoritetaan gVisorissa, microVM:issä (kuten Firecracker, CrossVM) tai Docker-kontteissa käyttäen --security-opt=no-new-privileges ja --read-only -lipukkeita.
 #4.5.2    Level: 1    Role: D/V
 Varmista, että hiekkalaatikkoympäristöillä ei ole verkkoyhteyttä (--network=none) tai että niillä on vain localhost-yhteys, ja kaikki ulkoiset pyynnöt on estetty iptables-säännöillä.
 #4.5.3    Level: 2    Role: D/V
 Varmista, että tekoälymallin validointi sisältää automatisoidun red-team -testauksen, jossa on organisaation määrittelemä testikattavuus ja käyttäytymisanalyysi takaovien havaitsemiseksi.
 #4.5.4    Level: 2    Role: D/V
 Varmista, että ennen kuin tekoälymalli otetaan käyttöön tuotannossa, sen hiekkalaatikkotulokset allekirjoitetaan kryptografisesti valtuutettujen tietoturvahenkilöiden toimesta ja tallennetaan muutumattomiin auditointilokeihin.
 #4.5.5    Level: 2    Role: D/V
 Varmista, että hiekkalaatikkoympäristöt tuhotaan ja luodaan uudelleen kullanarvoisista kuvista arviointien välillä täydellisellä tiedostojärjestelmän ja muistin tyhjennyksellä.

---

### C4.6 Infrastruktuurin turvallisuuden valvonta

Jatkuvasti skannaa ja valvo infrastruktuuria automaattisen korjauksen ja reaaliaikaisen hälytysjärjestelmän avulla.

 #4.6.1    Level: 1    Role: D/V
 Varmista, että konttikuvat skannataan organisaation aikataulujen mukaisesti siten, että KRIITTISIÄ haavoittuvuuksia sisältävät kuvat estävät käyttöönoton organisaation riskikynnysten perusteella.
 #4.6.2    Level: 1    Role: D/V
 Varmista, että infrastruktuuri täyttää CIS Benchmarkien tai NIST 800-53 -kontrollien vaatimukset organisaation määrittelemien vaatimustenmukaisuusrajojen mukaisesti ja tarjoaa automaattisen korjauksen epäonnistuneille tarkastuksille.
 #4.6.3    Level: 2    Role: D/V
 Varmista, että KORKEAN tason haavoittuvuudet on korjattu organisaation riskienhallintaaikataulujen mukaisesti hätätoimenpiteillä aktiivisesti hyödynnettyjen CVE:iden osalta.
 #4.6.4    Level: 2    Role: V
 Varmista, että tietoturvahälytykset integroituvat SIEM-alustoihin (Splunk, Elastic tai Sentinel) käyttäen CEF- tai STIX/TAXII-muotoja automaattisen rikastamisen kanssa.
 #4.6.5    Level: 3    Role: V
 Varmista, että infrastruktuurimittarit viedään valvontajärjestelmiin (Prometheus, DataDog) SLA-hallintapaneeleiden ja johdon raportoinnin kanssa.
 #4.6.6    Level: 2    Role: D/V
 Varmista, että konfiguraation poikkeamat havaitaan työkaluilla (Chef InSpec, AWS Config) organisaation valvontavaatimusten mukaisesti, ja että luvattomien muutosten automaattinen palautus on käytössä.

---

### C4.7 AI-infrastruktuurin resurssienhallinta

Estä resurssien loppumisiskut ja varmista reilu resurssien jakautuminen kiintiöiden ja seurannan avulla.

 #4.7.1    Level: 1    Role: D/V
 Varmista, että GPU/TPU:n käyttöastetta valvotaan ja hälytykset laukaistaan organisaation määrittelemissä kynnysarvoissa sekä että automaattinen skaalaus tai kuormantasapainotus aktivoituu kapasiteetin hallintakäytäntöjen mukaisesti.
 #4.7.2    Level: 1    Role: D/V
 Varmista, että tekoälyn työkuorman mittarit (päätelmän viive, läpimenonopeus, virhesuhteet) kerätään organisaation valvontavaatimusten mukaisesti ja korreloidaan infrastruktuurin käytön kanssa.
 #4.7.3    Level: 2    Role: D/V
 Varmista, että Kubernetes ResourceQuotas tai vastaava rajoittavat yksittäiset työkuormat organisaation resurssien allokointipolitiikkojen mukaisesti siten, että tiukat rajat tulevat voimaan.
 #4.7.4    Level: 2    Role: V
 Varmista, että kustannusseuranta seuraa menoja työkuormittain/vuokraajittain organisaation budjettirajojen perusteella annettavilla hälytyksillä ja budjetin ylitysten automaattisilla kontrollitoimilla.
 #4.7.5    Level: 3    Role: V
 Varmista, että kapasiteettisuunnittelu käyttää historiallista dataa organisaation määrittämien ennustejaksojen mukaisesti ja automatisoitua resurssien tarjoamista kysyntäkuvioiden perusteella.
 #4.7.6    Level: 2    Role: D/V
 Varmista, että resurssien loppuminen laukaisee piirikytkimet organisaation vastevaatimusten mukaisesti, mukaan lukien kapasiteettipolitiikkoihin perustuva nopeuden rajoitus ja työkuorman eristäminen.

---

### C4.8 Ympäristön erottelu ja siirto-ohjaukset

Toteuta tiukat ympäristörajoitukset automatisoiduilla edistämisporteilla ja turvallisuusvalidoinnilla.

 #4.8.1    Level: 1    Role: D/V
 Varmista, että kehitys-, testaus- ja tuotantoympäristöt toimivat erillisissä VPC:issä/VNet:issä ilman yhteisiä IAM-rooleja, tietoturvaryhmiä tai verkkoyhteyksiä.
 #4.8.2    Level: 1    Role: D/V
 Varmista, että ympäristön edistäminen vaatii hyväksynnän organisaation määrittämiltä valtuutetuilta henkilöiltä kryptografisilla allekirjoituksilla ja muuttumattomilla auditointilokeilla.
 #4.8.3    Level: 2    Role: D/V
 Varmista, että tuotantoympäristöt estävät SSH-yhteydet, poistavat käytöstä virheenkorjauspisteet ja edellyttävät muutospyyntöjä organisaation etukäteisilmoitusvaatimuksineen paitsi hätätilanteissa.
 #4.8.4    Level: 2    Role: D/V
 Varmista, että infrastruktuuri koodina -muutokset vaativat vertaisarvioinnin, automaattisen testauksen ja turvallisuustarkastuksen ennen yhdistämistä päähaaraan.
 #4.8.5    Level: 2    Role: D/V
 Varmista, että ei-tuotantotiedot on anonymisoitu organisaation tietosuojavaatimusten mukaisesti, synteettisen datan generoinnilla tai täydellisellä datan peittämisellä, johon kuuluu henkilötunnistettavien tietojen (PII) poisto.
 #4.8.6    Level: 2    Role: D/V
 Varmista, että siirtymäportit sisältävät automatisoidut turvallisuustestit (SAST, DAST, konttien skannaus), ja hyväksyntää varten vaaditaan nolla kriittistä havaintoa.

---

### C4.9 Infrastruktuurin varmuuskopiointi ja palautus

Varmista infrastruktuurin kestävyys automatisoitujen varmuuskopioiden, testattujen palautusmenetelmien ja katastrofipalautusominaisuuksien avulla.

 #4.9.1    Level: 1    Role: D/V
 Varmista, että infrastruktuurin kokoonpanot varmuuskopioidaan organisaation varmuuskopiointiaikataulujen mukaisesti maantieteellisesti erillisiin alueisiin 3-2-1-varmuuskopiointistrategian mukaisesti.
 #4.9.2    Level: 2    Role: D/V
 Varmista, että varmuuskopiointijärjestelmät toimivat eristetyissä verkoissa, joissa on erilliset käyttöoikeustiedot ja erillään oleva tallennustila kiristysohjelmasuojauksen vuoksi.
 #4.9.3    Level: 2    Role: V
 Varmista, että palautusmenettelyt testataan ja validoidaan automatisoidun testauksen avulla organisaation aikataulujen mukaisesti siten, että RTO- ja RPO-tavoitteet täyttävät organisaation vaatimukset.
 #4.9.4    Level: 3    Role: V
 Varmista, että katastrofipalautus sisältää tekoälykohtaiset toimintasuunnitelmat, joissa on mallipainojen palautus, GPU-klusterin uudelleenrakentaminen ja palveluiden riippuvuuskartoitus.

---

### C4.10 Infrastruktuurin vaatimustenmukaisuus ja hallinto

Ylläpidä säädösten noudattamista jatkuvan arvioinnin, dokumentoinnin ja automaattisten valvontamekanismien avulla.

 #4.10.1    Level: 2    Role: D/V
 Varmista, että infrastruktuurin vaatimustenmukaisuus arvioidaan organisaation aikataulujen mukaisesti SOC 2:n, ISO 27001:n tai FedRAMP-ohjausten mukaisesti automatisoidulla todisteiden keruulla.
 #4.10.2    Level: 2    Role: V
 Varmista, että infrastruktuuridokumentaatio sisältää verkon kaaviot, tietovirtojen kartat ja uhkamallit, jotka on päivitetty organisaation muutoshallintavaatimusten mukaisesti.
 #4.10.3    Level: 3    Role: D/V
 Varmista, että infrastruktuurimuutokset käyvät läpi automatisoidun vaatimustenmukaisuuden vaikutusten arvioinnin korkean riskin muutoksille tarkoitettujen sääntelyhyväksyntätyönkulkujen kanssa.

---

### C4.11 AI-laitteiston suojaus

Turvaa AI-spesifiset laitteistokomponentit, mukaan lukien GPU:t, TPU:t ja erikoistuneet AI-kiihdyttimet.

 #4.11.1    Level: 2    Role: D/V
 Varmista, että tekoälykiihdyttimen laiteohjelmisto (GPU BIOS, TPU-laiteohjelmisto) on varmennettu kryptografisilla allekirjoituksilla ja päivitetty organisaation korjaushallinnan aikataulujen mukaisesti.
 #4.11.2    Level: 2    Role: D/V
 Varmista, että ennen työkuorman suorittamista tekoälykiihdyttimen eheyttä validoidaan laitteistotodennuksella käyttäen TPM 2.0:aa, Intel TXT:tä tai AMD SVM:ää.
 #4.11.3    Level: 2    Role: D/V
 Varmista, että GPU-muisti on erotettu työnkuormien välillä käyttämällä SR-IOV:ta, MIG:iä (Multi-Instance GPU) tai vastaavaa laitteistopohjaista jakamista, jossa on muistinpuhdistus työn välillä.
 #4.11.4    Level: 3    Role: V
 Varmista, että tekoälylaitteiston toimitusketju sisältää alkuperän varmennuksen valmistajan todistuksilla ja jälkiä osoittavan pakkauksen tarkistuksen.
 #4.11.5    Level: 3    Role: D/V
 Varmista, että laitteistoturvamoduulit (HSM) suojaavat tekoälymallin painot ja salausavaimet FIPS 140-2 Taso 3 tai Common Criteria EAL4+ -sertifioinnin mukaisesti.

---

### C4.12 Reuna- ja hajautettu tekoälyinfrastruktuuri

Turvalliset hajautetut tekoälyn käyttöönotot, mukaan lukien reunalaskenta, liittoutunut oppiminen ja monipaikkaiset arkkitehtuurit.

 #4.12.1    Level: 2    Role: D/V
 Varmista, että reunalaitteet todennetaan keskusjärjestelmään käyttämällä molemminpuolista TLS:ää laitevarmenteilla, jotka kierrätetään organisaation varmenteiden hallintapolitiikan mukaisesti.
 #4.12.2    Level: 2    Role: D/V
 Varmista, että reunalaitteet toteuttavat suojatun käynnistyksen vahvistetuilla allekirjoituksilla ja palautussuojausominaisuudella, joka estää laiteohjelmiston takaisinversion hyökkäykset.
 #4.12.3    Level: 3    Role: D/V
 Varmista, että hajautettu tekoälyn koordinointi käyttää bysanttilaisvikakestävää konsensusalgoritmia, jossa on osallistujien vahvistus ja haitallisten solmujen tunnistus.
 #4.12.4    Level: 3    Role: D/V
 Varmista, että reunasta pilveen -viestintä sisältää kaistanleveyden rajoituksen, tietojen pakkaamisen ja offline-toimintamahdollisuudet turvallisen paikallisen tallennuksen kanssa.

---

### C4.13 Monipilvipalvelu- ja hybridi-infrastruktuurin turvallisuus

Turvaa tekoälysovellukset useiden pilvipalveluntarjoajien ja hybridi pilvi-paikallisten käyttöönottojen välillä.

 #4.13.1    Level: 2    Role: D/V
 Varmista, että monipilvi-AI-ratkaisut käyttävät pilviriippumatonta identiteetin yhdistämistä (OIDC, SAML) ja keskitettyä politiikan hallintaa eri tarjoajien välillä.
 #4.13.2    Level: 2    Role: D/V
 Varmista, että pilvienvälisessä datansiirrossa käytetään päästä päähän -salausta, jossa avaimet hallinnoidaan asiakkaan toimesta, ja että tietojen sijaintia koskevat säädökset toteutetaan kunkin lainkäyttöalueen vaatimusten mukaisesti.
 #4.13.3    Level: 2    Role: D/V
 Varmista, että hybridi-pilvin tekoälytyökuormat toteuttavat johdonmukaiset turvallisuuspolitiikat paikallisissa ja pilviympäristöissä yhdistetyllä valvonnalla ja hälytyksillä.
 #4.13.4    Level: 3    Role: V
 Varmista, että pilvipalveluntarjoajan lukkiutumisen estäminen sisältää siirrettävän infrastruktuurin koodina, standardoidut API:t ja tiedon vientiominaisuudet muunnostyökaluineen.
 #4.13.5    Level: 3    Role: V
 Varmista, että monipilvi-kustannusten optimointiin sisältyy tietoturvakontrolleja, jotka estävät resurssien leviämisen sekä luvattomat pilvien väliset tietoliikennemaksut.

---

### C4.14 Infrastruktuurin automaatio ja GitOpsin tietoturva

Suojaa infrastruktuurin automaatioputket ja GitOps-työnkulut tekoälyn infrastruktuurin hallintaan.

 #4.14.1    Level: 2    Role: D/V
 Varmista, että GitOps-repositoriot vaativat allekirjoitettuja committeja GPG-avaimilla ja että haarasuojaukset estävät suorat pushit päähaaroihin.
 #4.14.2    Level: 2    Role: D/V
 Varmista, että infrastruktuurin automaatio sisältää poikkeamien tunnistuksen, jonka yhteydessä on automaattinen korjaus ja palautusmahdollisuudet, jotka käynnistyvät organisaation vastausvaatimusten mukaisesti luvattomille muutoksille.
 #4.14.3    Level: 2    Role: D/V
 Varmista, että automatisoitu infrastruktuurin käyttöönotto sisältää tietoturvapolitiikan validoinnin ja estää käyttöönoton, jos kokoonpano ei ole vaatimusten mukainen.
 #4.14.4    Level: 2    Role: D/V
 Varmista, että infrastruktuurin automaation salaisuuksia hallitaan ulkoisten salaisuuksien operaattoreiden (External Secrets Operator, Bank-Vaults) kautta automaattisella vaihtamisella.
 #4.14.5    Level: 3    Role: V
 Varmista, että itseparantuva infrastruktuuri sisältää turvallisuustapahtumien korrelaation automatisoidulla häiriötilanteiden käsittelyllä ja sidosryhmien ilmoitusprosessien työnkuluilla.

---

### C4.15 Kvanttivarmennettu infrastruktuurin turvallisuus

Valmistele tekoälyn infrastruktuuri kvanttilaskennan uhkia varten postkvanttisalauksen ja kvanttiturvallisten protokollien avulla.

 #4.15.1    Level: 3    Role: D/V
 Varmista, että tekoälyn infrastruktuuri toteuttaa NIST:n hyväksymiä jälkikvanttisia kryptografisia algoritmeja (CRYSTALS-Kyber, CRYSTALS-Dilithium, SPHINCS+) avaintenvaihtoon ja digitaalisille allekirjoituksille.
 #4.15.2    Level: 3    Role: D/V
 Varmista, että kvanttisalauksen avaintenjakelujärjestelmät (QKD) on toteutettu korkeaturvallisiin tekoälyn viestintöihin kvanttiturvallisilla avainhallintaprotokollilla.
 #4.15.3    Level: 3    Role: D/V
 Varmista, että kryptografisen ketteryyden kehykset mahdollistavat nopean siirtymisen uusiin postkvanttialgoritmeihin automatisoidun varmenteiden ja avainten kierron avulla.
 #4.15.4    Level: 3    Role: V
 Varmista, että kvanttihyökkäysten uhat arvioidaan AI-infrastruktuurin haavoittuvuuden osalta kvanttihyökkäyksiin, sisältäen dokumentoidut siirtymäaikataulut ja riskinarviot.
 #4.15.5    Level: 3    Role: D/V
 Varmista, että hybridit klassisen ja kvanttikryptografian järjestelmät tarjoavat syvyyspuolustuksen kvanttisiirtymäkauden aikana suorituskyvyn seurannan avulla.

---

### C4.16 Luottamuksellinen laskenta ja suojatut enklavit

Suojaa tekoälytyökuormat ja mallipainot laitteistopohjaisten luotettujen suoritusalustojen ja luottamuksellisten laskentateknologioiden avulla.

 #4.16.1    Level: 3    Role: D/V
 Varmista, että arkaluonteiset tekoälymallit suoritetaan Intel SGX -yksiköissä, AMD SEV-SNP:ssä tai ARM TrustZone -ympäristössä salatun muistin ja varmennuksen kanssa.
 #4.16.2    Level: 3    Role: D/V
 Varmista, että luottamukselliset kontit (Kata Containers, gVisor luottamuksellisella laskennalla) eristävät tekoälykuormat laitteistolla valvotulla muistin salauksella.
 #4.16.3    Level: 3    Role: D/V
 Varmista, että etätodentaminen vahvistaa kotelon eheyden ennen tekoälymallien lataamista kryptografisella todisteella suorituksen ympäristön aitoudesta.
 #4.16.4    Level: 3    Role: D/V
 Varmista, että luottamukselliset tekoälyn päättelypalvelut estävät mallin poiminnan salatun laskennan avulla, jossa mallin painot on suojattu ja suoritus suojattu.
 #4.16.5    Level: 3    Role: D/V
 Varmista, että luotettu ajoitusympäristö hallinnoi turvallisen ympäristön elinkaarta etävarmennuksen ja salattujen viestintäkanavien avulla.
 #4.16.6    Level: 3    Role: D/V
 Varmista, että turvallinen moniosapuolinen laskenta (SMPC) mahdollistaa yhteistyöhön perustuvan tekoälyn koulutuksen paljastamatta yksittäisiä tietojoukkoja tai mallin parametreja.

---

### C4.17 Nollatietoinen infrastruktuuri

Toteuta nollatiedon todistejärjestelmiä yksityisyyttä suojaavaa tekoälyn varmennusta ja todennusta varten paljastamatta arkaluonteisia tietoja.

 #4.17.1    Level: 3    Role: D/V
 Varmista, että nollahäiriötodistukset (ZK-SNARKit, ZK-STARKit) validoivat tekoälymallin eheyden ja koulutuksen alkuperän paljastamatta mallin painoja tai koulutusdataa.
 #4.17.2    Level: 3    Role: D/V
 Varmista, että nollatietotodistuksiin perustuvat tunnistusjärjestelmät mahdollistavat yksityisyyttä suojaavan käyttäjän vahvistamisen tekoälypalveluissa paljastamatta henkilöllisyyteen liittyviä tietoja.
 #4.17.3    Level: 3    Role: D/V
 Varmista, että yksityinen joukkojen leikkaus (PSI) -protokollat mahdollistavat turvallisen tietojen yhdistämisen hajautetussa tekoälyssä paljastamatta yksittäisiä tietojoukkoja.
 #4.17.4    Level: 3    Role: D/V
 Varmista, että nollatietoinen koneoppiminen (ZKML) -järjestelmät mahdollistavat varmennettavat tekoälypäätelmät kryptografisella todistuksella oikeasta laskennasta.
 #4.17.5    Level: 3    Role: D/V
 Varmista, että ZK-rollupit tarjoavat skaalautuvan, yksityisyyttä suojaavan tekoälytransaktioiden käsittelyn ryhmätarkistuksella ja vähentyneellä laskentakuormalla.

---

### C4.18 Sivukanavahyökkäysten ehkäisy

Suojaa tekoälyn infrastruktuuri ajoitus-, virta-, sähkömagneettisilta ja välimuistiin perustuvilta sivukanavahyökkäyksiltä, jotka voivat vuotaa arkaluontoista tietoa.

 #4.18.1    Level: 3    Role: D/V
 Varmista, että tekoälyn päättelyaika on normalisoitu käyttäen vakioaikaisia algoritmeja ja täyttöjä estämään ajoitukseen perustuvat mallin uuttamisiskut.
 #4.18.2    Level: 3    Role: D/V
 Varmista, että virran analyysisuojaukseen sisältyy kohinasyöttö, virtalinjan suodatus ja satunnaistetut suorituksen kuvioinnit AI-laitteistolle.
 #4.18.3    Level: 3    Role: D/V
 Varmista, että välimuistiin perustuva sivukanavahaitta ontorjunta käyttää välimuistin erottelua, satunnaistamista ja tyhjennyskäskyjä estääkseen tiedon vuotamisen.
 #4.18.4    Level: 3    Role: D/V
 Varmista, että sähkömagneettinen säteilynsuojaus sisältää suojauksen, signaalin suodatuksen ja satunnaistetun käsittelyn TEMPEST-tyyppisten hyökkäysten estämiseksi.
 #4.18.5    Level: 3    Role: D/V
 Varmista, että mikr arkkitehtoniset sivukanavasuojaukset sisältävät spekulatiivisen suorituksen hallinnan ja muistin käyttötapojen peittämisen.

---

### C4.19 Neuromorfinen ja erikoistunut tekoälylaitteiston turvallisuus

Varmista nousevien tekoälylaitteistojen arkkitehtuurien, kuten neuromorfisten sirujen, FPGA-piirien, räätälöityjen ASIC-piirien ja optisten laskentajärjestelmien turvallisuus.

 #4.19.1    Level: 3    Role: D/V
 Varmista, että neuromorfisen sirun turvallisuus sisältää piikkikuvion salauksen, synaptisen painon suojauksen ja laitteistopohjaisen oppimissäännön validoinnin.
 #4.19.2    Level: 3    Role: D/V
 Varmista, että FPGA-pohjaiset tekoälykiihdyttimet toteuttavat bitstream-salauksen, manipulaationestomekanismit ja turvallisen konfiguraation latauksen todennetuilla päivityksillä.
 #4.19.3    Level: 3    Role: D/V
 Varmista, että räätälöity ASIC-turvallisuus sisältää sirulle integroidut turvallisuusprosessorit, laitteistopohjaisen luottamuksen juuren ja turvallisen avainten säilytyksen, jossa on manipuloinnin tunnistus.
 #4.19.4    Level: 3    Role: D/V
 Varmista, että optiset laskentajärjestelmät toteuttavat quantum-turvallisen optisen salauksen, suojatun fotonisen kytkennän ja suojatun optisen signaalinkäsittelyn.
 #4.19.5    Level: 3    Role: D/V
 Varmista, että hybridi analogi-digitaalinen tekoälysiru sisältää turvallisen analogisen laskennan, suojatun painovarastoinnin ja vahvistetun analogi-digitaalisen muunnoksen.

---

### C4.20 Yksityisyyttä säilyttävä laskentainfrastruktuuri

Ota käyttöön infrastruktuurin valvontatoimet yksityisyyttä säilyttävän laskennan varmistamiseksi, jotta arkaluontoiset tiedot suojataan tekoälyn käsittelyn ja analyysin aikana.

 #4.20.1    Level: 3    Role: D/V
 Varmista, että homomorfinen salausinfrastruktuuri mahdollistaa salausten laskennan arkaluonteisilla tekoälykuormilla kryptografisella eheyden varmistuksella ja suorituskyvyn valvonnalla.
 #4.20.2    Level: 3    Role: D/V
 Varmista, että yksityiset tiedonhakujärjestelmät mahdollistavat tietokantakyselyt paljastamatta kyselykuvioita kryptografisella suojausmenetelmällä pääsykuvioille.
 #4.20.3    Level: 3    Role: D/V
 Varmista, että turvalliset moniosapuolten laskentaprotokollat mahdollistavat yksityisyyttä suojaavan tekoälyn päätelmän ilman, että yksittäiset syötteet tai välivaiheen laskelmat paljastuvat.
 #4.20.4    Level: 3    Role: D/V
 Varmista, että yksityisyyttä suojaava avaintenhallinta sisältää hajautetun avainten generoinnin, kynnyskriptografian ja turvallisen avainten kierron laitteistotukea hyödyntäen.
 #4.20.5    Level: 3    Role: D/V
 Varmista, että yksityisyyttä suojaavan laskennan suorituskyky on optimoitu eräajoilla, välimuistilla ja laitteistokiihdytyksellä samalla kun säilytetään kryptografiset turvallisuustakuuet.

---

### C4.15 Agenttikehyksen pilvijärjestelmän integroinnin turvallisuus ja hybridi- käyttöönotto

Turvallisuusvalvontatoimet pilveen integroiduille agenttikehyksille hybridi paikallinen/pilvi-arkkitehtuureissa.

 #4.15.1    Level: 1    Role: D/V
 Varmista, että pilvitallennusintegraatio käyttää päästä päähän -salausta ja agentin hallitsemaa avainhallintaa.
 #4.15.2    Level: 2    Role: D/V
 Varmista, että hybridi-jakelun turvallisuusrajat on selkeästi määritelty ja että viestintäkanavat ovat salattuja.
 #4.15.3    Level: 2    Role: D/V
 Varmista, että pilviresurssien käyttöoikeudet sisältävät nollaluottamuksen varmennuksen jatkuvalla autentikoinnilla.
 #4.15.4    Level: 3    Role: D/V
 Varmista, että tietojen sijaintivaatimuksia noudatetaan salausteknisellä tallennuspaikkojen todentamisella.
 #4.15.5    Level: 3    Role: D/V
 Varmista, että pilvipalveluntarjoajan turvallisuusarvioinnit sisältävät agenttikohtaisen uhkamallinnuksen ja riskinarvioinnin.

---

### Viitteet

NIST Cybersecurity Framework 2.0
CIS Controls v8
OWASP Container Security Verification Standard
Kubernetes Security Best Practices
SLSA Supply Chain Security Framework
NIST SP 800-190: Application Container Security Guide
Cloud Security Alliance: Cloud Controls Matrix
ENISA: Secure Infrastructure Design
NIST SP 800-53: Security Controls for Federal Information Systems
ISO 27001:2022 Information Security Management
NIST AI Risk Management Framework
CIS Kubernetes Benchmark
FIPS 140-2 Security Requirements
NIST SP 800-207: Zero Trust Architecture
IEEE 2857: Privacy Engineering for AI Systems
NIST SP 800-161: Cybersecurity Supply Chain Risk Management
NIST Post-Quantum Cryptography Standards
Intel SGX Developer Guide
AMD SEV-SNP White Paper
ARM TrustZone Technology
ZK-SNARKs: A Gentle Introduction
NIST SP 800-57: Cryptographic Key Management
Side-Channel Attack Countermeasures
Neuromorphic Computing Security Challenges
FPGA Security: Fundamentals, Evaluation, and Countermeasures
Microsoft SEAL: Homomorphic Encryption Library
HElib: Homomorphic Encryption Library
PALISADE Lattice Cryptography Library
Differential Privacy: A Survey of Results
Secure Aggregation for Federated Learning
Private Information Retrieval: Concepts and Constructions

## C5 Käyttöoikeuksien hallinta ja identiteetti tekoälykomponenteille ja käyttäjille

### Ohjaustavoite

Tehokas käyttöoikeuksien hallinta tekoälyjärjestelmissä edellyttää vahvaa identiteetin hallintaa, kontekstin tuntevaa valtuutusta ja suoritusajan valvontaa noudattaen nollaluottamusperiaatteita. Nämä hallintakeinot varmistavat, että ihmiset, palvelut ja autonomiset agentit käyttävät malleja, tietoja ja laskentaresursseja vain nimenomaisesti myönnetyissä laajuuksissa, jatkuvan vahvistamisen ja auditointimahdollisuuksien tukemina.

---

### C5.1 Identiteetin hallinta ja todennus

Perusta kaikille toimijoille kryptografisesti varmennetut identiteetit monivaiheisella todennuksella valtuutettuihin toimiin.

 #5.1.1    Level: 1    Role: D/V
 Varmista, että kaikki ihmis- ja palveluperiaatteet todennetaan keskitetyn yrityksen identiteetin tarjoajan (IdP) kautta käyttäen OIDC/SAML-protokollia ainutlaatuisilla identiteetistä tokeniin kartoittamisilla (ei yhteiskäytössä olevia tilejä tai tunnistetietoja).
 #5.1.2    Level: 1    Role: D/V
 Varmista, että korkean riskin toimenpiteet (mallin käyttöönotto, painojen vienti, koulutusdatan käyttöoikeus, tuotantokonfiguraation muutokset) vaativat monivaiheisen tunnistautumisen tai lisävahvistuksen istunnon uudelleentarkistuksella.
 #5.1.3    Level: 2    Role: D
 Varmista, että uudet johtajat käyvät läpi henkilöllisyyden todentamisen, joka on linjassa NIST 800-63-3 IAL-2 -standardin tai vastaavien standardien kanssa, ennen kuin he saavat pääsyn tuotantojärjestelmään.
 #5.1.4    Level: 2    Role: V
 Varmista, että käyttöoikeustarkastukset suoritetaan neljännesvuosittain automaattisella epäaktiivisten tilien havaitsemisella, tunnistetietojen kierron valvonnalla ja poistoprosesseilla.
 #5.1.5    Level: 3    Role: D/V
 Varmista, että liitetyt tekoälyagentit todennetaan allekirjoitettujen JWT-väitteiden avulla, joiden enimmäiskesto on 24 tuntia ja jotka sisältävät kryptografisen alkuperätodisteen.

---

### C5.2 Resurssien valtuutus ja vähimmän oikeuden periaate

Toteuta hienojakoiset käyttöoikeuksien hallinnat kaikille tekoälyresursseille selkeillä lupamalleilla ja tarkastuspoluilla.

 #5.2.1    Level: 1    Role: D/V
 Varmista, että jokainen tekoälyresurssi (aineistot, mallit, päätepisteet, vektorikokoelmat, upotusindeksit, laskenta-instanssit) käyttää roolipohjaisia käyttöoikeuksia, joissa on eksplisiittiset sallintalistat ja oletuksena kieltävät käytännöt.
 #5.2.2    Level: 1    Role: D/V
 Varmista, että vähimmän etuoikeuden periaatteet toteutuvat oletuksena palvelutilien kohdalla, aloittaen lukuoikeuksista, ja että kirjoitusoikeuksille vaaditaan dokumentoitu liiketoiminnallinen perustelu.
 #5.2.3    Level: 1    Role: V
 Varmista, että kaikki käyttöoikeuksien muutokset ovat liitetty hyväksyttyihin muutospyyntöihin ja kirjattu muuttumattomasti aikaleimojen, toimijoiden tunnisteiden, resurssien tunnisteiden ja oikeusmuutosten kanssa.
 #5.2.4    Level: 2    Role: D
 Varmista, että tietoluokittelutunnisteet (henkilötiedot, potilastiedot, vientivalvottu, luottamuksellinen) siirtyvät automaattisesti johdettuihin resursseihin (upotukset, kehotemuistit, mallin tulokset) johdonmukaisella politiikan noudattamisella.
 #5.2.5    Level: 2    Role: D/V
 Varmista, että luvattomat käyttöyritykset ja etuoikeuksien korotustapahtumat laukaisevat reaaliaikaiset hälytykset kontekstuaalisine metatietoineen SIEM-järjestelmiin viiden minuutin kuluessa.

---

### C5.3 Dynaaminen politiikan arviointi

Ota käyttöön attribuuttipohjaiset pääsynvalvontamoottorit (ABAC) kontekstietietoisten valtuutuspäätösten tekemiseen auditointimahdollisuuksilla.

 #5.3.1    Level: 1    Role: D/V
 Varmista, että valtuutuspäätökset ulkoistetaan omistetulle politiikkamoottorille (OPA, Cedar tai vastaava), johon pääsee käsiksi todennetuilla API-rajapinnoilla, jotka tarjoavat kryptografisen eheyden suojauksen.
 #5.3.2    Level: 1    Role: D/V
 Varmista, että käytännöt arvioivat dynaamisia attribuutteja suoritusajon aikana, mukaan lukien käyttäjän valtuutustaso, resurssin arkaluonteisuusluokitus, pyyntöympäristö, vuokralais-eristys ja ajalliset rajoitukset.
 #5.3.3    Level: 2    Role: D
 Varmista, että politiikan määritelmät ovat versiohallittuja, vertaisarvioituja ja validoitu automaattisen testauksen avulla CI/CD-putkissa ennen tuotantoon käyttöönottoa.
 #5.3.4    Level: 2    Role: V
 Varmista, että politiikan arviointitulokset sisältävät jäsennellyt päätöspohjat ja ne lähetetään SIEM-järjestelmiin korrelaatioanalyysia ja vaatimustenmukaisuusraportointia varten.
 #5.3.5    Level: 3    Role: D/V
 Varmista, että politiikan välimuistin elinaika-arvot (TTL) eivät ylitä 5 minuuttia korkean herkkyyden omaaville resursseille ja 1 tuntia vakiomääräysten resursseille, joilla on välimuistin mitätöintikyky.

---

### C5.4 Kyselyajan turvallisuuden valvonta

Ota käyttöön tietokantakerroksen turvallisuusohjaimet pakollisilla suodatuksilla ja rivitason turvallisuuspolitiikoilla.

 #5.4.1    Level: 1    Role: D/V
 Varmista, että kaikki vektoritietokanta- ja SQL-kyselyt sisältävät pakolliset suojaussuodattimet (vuokralais-ID, herkkyystunnisteet, käyttäjän käyttöalue), jotka toteutetaan tietokantamoottorin tasolla, ei sovelluskoodissa.
 #5.4.2    Level: 1    Role: D/V
 Varmista, että rivitasoisen suojauksen (RLS) käytännöt ja kenttätason peittäminen ovat käytössä politiikan periytymisellä kaikissa vektorikannoissa, hakemistotiedoissa ja koulutusaineistoissa.
 #5.4.3    Level: 2    Role: D
 Varmista, että epäonnistuneet valtuutuksen arvioinnit estävät "sekaannus-edustaja-hyökkäykset" keskeyttämällä kyselyt välittömästi ja palauttamalla selkeät valtuutusvirhekoodit tyhjien tulosjoukkojen sijaan.
 #5.4.4    Level: 2    Role: V
 Varmista, että politiikan arviointiviivettä valvotaan jatkuvasti automatisoitujen hälytysten avulla aikakatkaisutilanteissa, jotka voisivat mahdollistaa valtuutuksen ohittamisen.
 #5.4.5    Level: 3    Role: D/V
 Varmista, että kyselyn uudelleenyrittomekanismit arvioivat valtuutuspolitiikat uudelleen ottaen huomioon dynaamiset käyttöoikeusmuutokset aktiivisten käyttäjäistuntojen aikana.

---

### C5.5 Tulosteen suodatus ja tietojen menetyksen estäminen

Ota käyttöön jälkikäsittelyohjaimet estääksesi luvattoman tietojen paljastumisen tekoälyn tuottamassa sisällössä.

 #5.5.1    Level: 1    Role: D/V
 Varmista, että jälkipäätöksentekoon perustuvat suodatusmekanismit skannaavat ja poistavat luvattoman henkilötiedon (PII), luokitellun tiedon ja omistusoikeudellisen datan ennen sisällön toimittamista pyytäjille.
 #5.5.2    Level: 1    Role: D/V
 Varmista, että mallin tuottamien viitteiden, lähdeviitteiden ja lähdeviittausten oikeellisuus tarkistetaan soittajan oikeuksien perusteella ja poistetaan, jos luvaton pääsy havaitaan.
 #5.5.3    Level: 2    Role: D
 Varmista, että tulostusmuodon rajoitukset (puhdistetut PDF-tiedostot, metatietojen poistetut kuvat, hyväksytyt tiedostotyypit) toteutetaan käyttäjän lupatason ja tietoluokitusten perusteella.
 #5.5.4    Level: 2    Role: V
 Varmista, että sensurointialgoritmit ovat deterministisiä, versiohallittuja ja ylläpitävät tarkastuslokeja tukemaan vaatimustenmukaisuustutkintoja ja oikeuslääketieteellisiä analyyseja.
 #5.5.5    Level: 3    Role: V
 Varmista, että korkean riskin salaus tapahtumat tuottavat adaptiivisia lokitietoja, jotka sisältävät alkuperäisen sisällön kryptografiset tiivisteet oikeuslääketieteellistä hakua varten ilman tietojen paljastumista.

---

### C5.6 Monivuokralais-eristys

Varmista kryptografinen ja looginen eristys vuokralaisten välillä jaetussa tekoälyinfrastruktuurissa.

 #5.6.1    Level: 1    Role: D/V
 Varmista, että muistitilat, upotusten tallennustilat, välimuistin kohteet ja väliaikaiset tiedostot ovat nimialueittain erillään kunkin vuokralaisen osalta, ja että vuokralaisen poistamisen tai istunnon päättymisen yhteydessä tiedot poistetaan turvallisesti.
 #5.6.2    Level: 1    Role: D/V
 Varmista, että jokainen API-pyyntö sisältää todennetun vuokralaisen tunnisteen, joka on kryptografisesti validoitu istuntokontekstin ja käyttäjäoikeuksien perusteella.
 #5.6.3    Level: 2    Role: D
 Varmista, että verkkopolitiikat toteuttavat oletusarvoisesti kieltävät säännöt monivuokraajaviestinnälle palveluverkkojen ja konttien orkestrointialustojen sisällä.
 #5.6.4    Level: 3    Role: D
 Varmista, että salausavaimet ovat uniikkeja jokaiselle vuokralaiselle, kun käytössä on asiakkaan hallinnoima avain (CMK), ja että vuokratilojen tietovarastojen välillä on kryptografinen eristys.

---

### C5.7 Autonomisen agentin valtuutus

Ohjaoikeudet tekoälyagentteihin ja autonomisiin järjestelmiin hallitaan laajuusrajoitetuilla valtuutustunnuksilla ja jatkuvalla valtuutuksella.

 #5.7.1    Level: 1    Role: D/V
 Varmista, että autonomiset agentit saavat rajatut käyttöoikeustunnukset, jotka erittelevät nimenomaisesti sallitut toiminnot, käytettävissä olevat resurssit, aikarajat ja toimintarajoitukset.
 #5.7.2    Level: 1    Role: D/V
 Varmista, että korkean riskin toiminnot (tiedostojärjestelmän käyttö, koodin suoritus, ulkoiset API-kutsut, taloudelliset tapahtumat) ovat oletuksena pois päältä ja niiden aktivoiminen vaatii selkeät käyttöoikeudet liiketoiminnallisilla perusteluilla.
 #5.7.3    Level: 2    Role: D
 Varmista, että käyttöoikeustunnukset ovat sidottuja käyttäjäistuntoihin, sisältävät kryptografisen eheyden suojauksen ja että niitä ei voi tallentaa tai käyttää uudelleen offline-tilanteissa.
 #5.7.4    Level: 2    Role: V
 Varmista, että agentin aloittamat toimet käyvät läpi toissijaisen valtuutuksen ABAC-politiikkamoottorin kautta käyttäen täydellistä kontekstiarviota ja auditointilokien kirjausta.
 #5.7.5    Level: 3    Role: V
 Varmista, että agentin virhetilanteet ja poikkeusten käsittely sisältävät käyttöoikeuksien laajuustiedot tukemaan tapausanalyysiä ja oikeuslääketieteellistä tutkimusta.

---

### Viitteet

#### Standardit ja viitekehykset

NIST SP 800-63-3: Digital Identity Guidelines
Zero Trust Architecture – NIST SP 800-207
OWASP Application Security Verification Standard (AISVS)
​
#### Toteutusoppaat

Identity and Access Management in the AI Era: 2025 Guide – IDSA
Attribute-Based Access Control with OPA – Permify
How We Designed Cedar to Be Intuitive, Fast, and Safe – AWS
​
#### AI-spesifinen tietoturva

Row Level Security in Vector DBs for RAG – Bluetuple.ai
Tenant Isolation in Multi-Tenant Systems – WorkOS
Handling AI Agent Permissions – Stytch
OWASP Top 10 for Large Language Model Applications

## C6 Mallien, kehysten ja datan toimitusketjun turvallisuus

### Ohjaustavoite

AI-toimitusketjun hyökkäykset hyödyntävät kolmannen osapuolen malleja, kehyksiä tai tietoaineistoja takaovien, harhan tai hyödynnettävissä olevan koodin upottamiseen. Nämä kontrollit tarjoavat päästä päähän jäljitettävyyden, haavoittuvuuksien hallinnan ja valvonnan suojellakseen koko mallin elinkaaren.

---

### C6.1 Esikoulutettujen mallien arviointi ja alkuperän varmistus

Arvioi ja vahvista kolmannen osapuolen mallien alkuperä, lisenssit ja piilevät toiminnot ennen hienosäätöä tai käyttöönottoa.

 #6.1.1    Level: 1    Role: D/V
 Varmista, että jokaisessa kolmannen osapuolen mallin artifaktissa on allekirjoitettu alkuperätietue, joka tunnistaa lähdevaraston ja commit-hashin.
 #6.1.2    Level: 1    Role: D/V
 Varmista, että mallit tutkitaan automaattisilla työkaluilla haitallisten kerrosten tai Troijan laukaisimien varalta ennen tuontia.
 #6.1.3    Level: 2    Role: D
 Varmista, että siirto-opetus hienosäätää mallin niin, että se läpäisee vastustava arvioinnin piilotettujen käyttäytymismallien havaitsemiseksi.
 #6.1.4    Level: 2    Role: V
 Varmista, että mallin lisenssit, vientivalvontatunnisteet ja datan alkuperäilmoitukset on tallennettu ML-BOM-tietueeseen.
 #6.1.5    Level: 3    Role: D/V
 Varmista, että korkean riskin mallit (julkisesti ladatut painot, verifioimattomat tekijät) pysyvät eristyksissä ihmisen tarkastukseen ja hyväksyntään saakka.

---

### C6.2 Kehys- ja kirjastotarkastus

Jatkuvasti skannaa koneoppimiskehyksiä ja kirjastoja CVE-haavoittuvuuksien ja haitallisen koodin varalta pitääkseen suoritinpinon turvallisena.

 #6.2.1    Level: 1    Role: D/V
 Varmista, että CI-putket suorittavat riippuvuustarkastuksia tekoälykehyksissä ja kriittisissä kirjastoissa.
 #6.2.2    Level: 1    Role: D/V
 Varmista, että kriittiset haavoittuvuudet (CVSS ≥ 7.0) estävät ylennyksen tuotantokuviksi.
 #6.2.3    Level: 2    Role: D
 Varmista, että staattinen koodianalyysi suoritetaan haarautuneille tai mukaan otetuille koneoppimiskirjastoille.
 #6.2.4    Level: 2    Role: V
 Varmista, että kehysjärjestelmän päivitysehdotuksiin sisältyy tietoturva-arviointi, jossa viitataan julkisiin CVE-tietoja tarjoaviin lähteisiin.
 #6.2.5    Level: 3    Role: V
 Varmista, että ajonaikaiset sensorit hälyttävät odottamattomista dynaamisista kirjastojen latauksista, jotka poikkeavat allekirjoitetusta SBOM:sta.

---

### C6.3 Riippuvuuksien lukitseminen ja varmennus

Kiinnitä jokainen riippuvuus muuttumattomiin tiivisteisiin ja toista rakennukset varmistaaksesi identtiset, väärentämättömät artefaktit.

 #6.3.1    Level: 1    Role: D/V
 Varmista, että kaikki pakettienhallintaohjelmat noudattavat version lukitsemista lukitustiedostojen avulla.
 #6.3.2    Level: 1    Role: D/V
 Varmista, että konttiviittauksissa käytetään muuttumattomia tiivisteitä muutettavien tunnisteiden sijaan.
 #6.3.3    Level: 2    Role: D
 Varmista, että toistettavat rakennustarkistukset vertailevat hajautusarvoja CI-ajojen välillä identtisten tulosteiden varmistamiseksi.
 #6.3.4    Level: 2    Role: V
 Varmista, että koontivahvistukset säilytetään 18 kuukautta auditointijäljityksen varmistamiseksi.
 #6.3.5    Level: 3    Role: D
 Varmista, että vanhentuneet kirjastot laukaisevat automaattiset PR-pyynnöt päivittämään tai haaroittamaan kiinnitetyt versiot.

---

### C6.4 Luotetun lähteen valvonta

Salli artefaktien lataukset vain kryptografisesti varmennetuista, organisaation hyväksymistä lähteistä ja estä kaikki muu.

 #6.4.1    Level: 1    Role: D/V
 Varmista, että mallipainot, tietojoukot ja säiliöt ladataan vain hyväksytyistä toimialueista tai sisäisistä rekistereistä.
 #6.4.2    Level: 1    Role: D/V
 Varmista, että Sigstore/Cosign-allekirjoitukset vahvistavat julkaisijan henkilöllisyyden ennen kuin artefaktit tallennetaan paikallisesti välimuistiin.
 #6.4.3    Level: 2    Role: D
 Varmista, että egres-proksit estävät todennuksettomat artefaktin lataukset luotettavan lähdepolitiikan noudattamiseksi.
 #6.4.4    Level: 2    Role: V
 Varmista, että repositorioluettelot tarkistetaan neljännesvuosittain, ja jokaisesta merkinnästä on liiketoiminnallinen perustelu.
 #6.4.5    Level: 3    Role: V
 Varmista, että käytäntöjen rikkomukset aiheuttavat artefaktien karanteenin ja riippuvaisten putkistojen ajojen palautuksen.

---

### C6.5 Kolmannen osapuolen aineistojen riskiarviointi

Arvioi ulkoiset datasetit myrkyllisyyden, harhan ja lainmukaisuuden osalta, ja seuraa niitä koko niiden elinkaaren ajan.

 #6.5.1    Level: 1    Role: D/V
 Varmista, että ulkoiset tietoaineistot käyvät läpi myrkytysriskin arvioinnin (esim. datan sormenjälkitunnistus, poikkeamien tunnistus).
 #6.5.2    Level: 1    Role: D
 Varmista, että puolueellisuusmittarit (demografinen yhdenvertaisuus, yhtäläinen mahdollisuus) lasketaan ennen datan hyväksymistä.
 #6.5.3    Level: 2    Role: V
 Varmista, että tietojoukkeiden alkuperä- ja lisenssiehdot on tallennettu ML‑BOM‑merkintöihin.
 #6.5.4    Level: 2    Role: V
 Varmista, että säännöllinen seuranta havaitsee harhailun tai korruption isännöidyissä tietojoukoissa.
 #6.5.5    Level: 3    Role: D
 Varmista, että kielletty sisältö (tekijänoikeudet, henkilötiedot) poistetaan automatisoidulla puhdistuksella ennen koulutusta.

---

### C6.6 Toimitusketjun hyökkäysten seuranta

Havaitse toimitusketjun uhkat varhaisessa vaiheessa CVE-syötteiden, tarkastuslokianalytiikan ja red team -simulaatioiden avulla.

 #6.6.1    Level: 1    Role: V
 Varmista, että CI/CD:n auditointilokit virtaavat SIEM-järjestelmään, jotta voidaan havaita epäilyttävät pakettien hakutapahtumat tai muokatut rakennusvaiheet.
 #6.6.2    Level: 2    Role: D
 Varmista, että häiriötilanteiden vastausohjeissa on mukana peruutusmenettelyt vaarantuneille malleille tai kirjastoille.
 #6.6.3    Level: 3    Role: V
 Varmista, että uhkatiedon rikastustunnisteet merkitsevät koneoppimiseen liittyviä indikaattoreita (esim. mallin myrkytyksen IoC:t) hälytyksen käsittelyssä.

---

### C6.7 ML‑BOM mallin artefakteille

Luo ja allekirjoita yksityiskohtaiset koneoppimiseen (ML) liittyvät ohjelmistokomponenttien koostumustiedot (ML-BOMit), jotta jälkikäyttäjät voivat vahvistaa komponenttien eheyden käyttöönoton yhteydessä.

 #6.7.1    Level: 1    Role: D/V
 Varmista, että jokainen mallin artefakti julkaisee ML-BOM:n, joka luettelee aineistot, painot, hyperparametrit ja lisenssit.
 #6.7.2    Level: 1    Role: D/V
 Varmista, että ML‑BOM:n luonti ja Cosign-allekirjoitus on automatisoitu CI:ssä ja pakollisia yhdistämiselle.
 #6.7.3    Level: 2    Role: D
 Varmista, että ML‑BOM:n täydellisyystarkistukset keskeyttävät rakennuksen, jos jokin komponentin metatiedoista (hash, lisenssi) puuttuu.
 #6.7.4    Level: 2    Role: V
 Varmista, että alavirran käyttäjät voivat kyselyttää ML-BOM:ia API:n kautta validoidakseen tuodut mallit käyttöönottohetkellä.
 #6.7.5    Level: 3    Role: V
 Varmista, että ML-BOM:t ovat versiohallinnassa ja eroteltu muutosten havaitsemiseksi luvattomista muokkauksista.

---

### Viitteet

ML Supply Chain Compromise – MITRE ATLAS
Supply‑chain Levels for Software Artifacts (SLSA)
CycloneDX – Machine Learning Bill of Materials
What is Data Poisoning? – SentinelOne
Transfer Learning Attack – OWASP ML Security Top 10
AI Data Security Best Practices – CISA
Secure CI/CD Supply Chain – Sumo Logic
AI & Transparency: Protect ML Models – ReversingLabs
SBOM Overview – CISA
Training Data Poisoning Guide – Lakera.ai
Dependency Pinning for Reproducible Python – Medium

## C7-mallin käyttäytyminen, tulostehallinta ja turvallisuuden varmistus

### Ohjaustavoite

Mallin tuotosten on oltava rakenteellisia, luotettavia, turvallisia, selitettäviä ja jatkuvasti valvottuja tuotantoympäristössä. Näin toimimalla vähennetään harhaluuloja, tietosuojavuotoja, haitallista sisältöä ja hallitsemattomia toimintoja, samalla kun lisätään käyttäjien luottamusta ja sääntelyvaatimusten noudattamista.

---

### C7.1 Tulostemuodon valvonta

Tiukat skeemat, rajoitettu dekoodaus ja jälkikäsittelyn validointi estävät virheellistä tai haitallista sisältöä leviämästä.

 #7.1.1    Level: 1    Role: D/V
 Varmista, että vastauskäsikirjat (esim. JSON-skeema) sisältyvät järjestelmäkehotteeseen ja että jokainen tuloste validoidaan automaattisesti; vääränmuotoiset tulosteet aiheuttavat korjauksen tai hylkäyksen.
 #7.1.2    Level: 1    Role: D/V
 Varmista, että rajoitettu dekoodaus (pysäytystunnisteet, säännölliset lausekkeet, maksimi-tokenit) on käytössä ylivuodon tai kehotteen injektointia sisältävien sivukanavien estämiseksi.
 #7.1.3    Level: 2    Role: D/V
 Varmista, että alemmat komponenteet käsittelevät lähtötiedot epäluotettavina ja validoivat ne skeemojen tai injektioilta suojaavien deserialisoijien avulla.
 #7.1.4    Level: 3    Role: V
 Varmista, että virheelliset tulostustapahtumat kirjataan, niiden määrä rajoitetaan ja ne näkyvät valvonnassa.

---

### C7.2 Harhan tunnistaminen ja lieventäminen

Epävarmuuden arviointi ja varatoimenpiteet rajoittavat tekaistuja vastauksia.

 #7.2.1    Level: 1    Role: D/V
 Varmista, että token-tason log-todennäköisyydet, joukkoyhteenkuuluvuus itsevarmuusmenetelmässä tai hienosäädetyt harhallisuuden tunnistimet antavat luottamusarvon jokaiselle vastaukselle.
 #7.2.2    Level: 1    Role: D/V
 Varmista, että vastaukset, joiden luottamustaso on alle määriteltävän kynnyksen, laukaisevat varajärjestelmät (esim. hakua lisätty generointi, toissijainen malli tai ihmistarkastus).
 #7.2.3    Level: 2    Role: D/V
 Varmista, että hallusinaatiotapaukset on merkitty juurisyy-metatiedoilla ja syötetty jälkiarviointi- ja hienosäätöputkiin.
 #7.2.4    Level: 3    Role: D/V
 Varmista, että kynnysarvot ja ilmaisimet kalibroidaan uudelleen merkittävien mallin tai tietopohjan päivitysten jälkeen.
 #7.2.5    Level: 3    Role: V
 Varmista, että kojelaudan visualisoinnit seuraavat hallusinaatiotasoja.

---

### C7.3 Tulosteen turvallisuus- ja yksityisyydensuodatus

Politiikkasuodattimet ja red-team-tarkastus suojaavat käyttäjiä ja luottamuksellisia tietoja.

 #7.3.1    Level: 1    Role: D/V
 Varmista, että esigenerointi- ja jälkigenerointiluokittimet estävät vihapuheen, häirinnän, itsetuhoisuuden, ääriliikkeiden ja seksuaalisesti eksplisiittisen sisällön, jotka ovat linjassa politiikan kanssa.
 #7.3.2    Level: 1    Role: D/V
 Varmista, että PII/PCI-tunnistus ja automaattinen peittäminen suoritetaan jokaisessa vastauksessa; rikkomukset johtavat tietosuojaloukkausilmoitukseen.
 #7.3.3    Level: 2    Role: D
 Varmista, että luottamuksellisuustunnisteet (esim. liikesalaisuudet) leviävät eri muotojen välillä estäen vuotoja tekstissä, kuvissa tai koodissa.
 #7.3.4    Level: 3    Role: D/V
 Varmista, että suodattimen ohitusyritykset tai korkean riskin luokitukset vaativat toissijaisen hyväksynnän tai käyttäjän uudelleenautentikoinnin.
 #7.3.5    Level: 3    Role: D/V
 Varmista, että suodatuskynnysarvot heijastavat laillisia toimivalta-alueita sekä käyttäjän ikä/roolikontekstia.

---

### C7.4 Tulosteen ja toimien rajoittaminen

Nopeusrajoitukset ja hyväksymisportit estävät väärinkäytökset ja liiallisen autonomian.

 #7.4.1    Level: 1    Role: D
 Varmista, että käyttäjäkohtaiset ja API-avaimenkohtaiset kiintiöt rajoittavat pyyntöjä, tokeneita ja kustannuksia eksponentiaalisen takaisinperuutuksen avulla 429-virheissä.
 #7.4.2    Level: 1    Role: D/V
 Varmista, että etuoikeutetut toiminnot (tiedostojen kirjoitus, koodin suoritus, verkkopyynnöt) vaativat politiikanmukaista hyväksyntää tai ihmisen hyväksynnän prosessissa.
 #7.4.3    Level: 2    Role: D/V
 Varmista, että ristiinmodaliteettinen johdonmukaisuuden tarkistus takaa, ettei saman pyynnön perusteella luotua kuvaa, koodia ja tekstiä voi käyttää haitallisen sisällön salakuljettamiseen.
 #7.4.4    Level: 2    Role: D
 Varmista, että agentin valtuutuksen syvyys, rekursion rajat ja sallitut työkaluluettelot on määritelty selvästi.
 #7.4.5    Level: 3    Role: V
 Varmista, että rajojen ylityksestä syntyy jäsenneltyjä turvallisuustapahtumia SIEM-järjestelmän keräystä varten.

---

### C7.5 Tulosteen selitettävyys

Läpinäkyvät signaalit parantavat käyttäjien luottamusta ja sisäistä vianetsintää.

 #7.5.1    Level: 2    Role: D/V
 Varmista, että käyttäjälle näkyvät luottamuspisteet tai lyhyet perusteluyhteenvedot näytetään, kun riskinarviointi katsoo sen sopivaksi.
 #7.5.2    Level: 2    Role: D/V
 Varmista, että tuotetut selitykset eivät paljasta arkaluonteisia järjestelmäkehotteita tai omistusoikeudellisia tietoja.
 #7.5.3    Level: 3    Role: D
 Varmista, että järjestelmä tallentaa token-tason lok todennäköisyydet tai attentio-matriisit ja säilyttää ne valtuutettua tarkastusta varten.
 #7.5.4    Level: 3    Role: V
 Varmista, että selitettävyysartefaktit ovat versiohallinnassa mallijulkaisujen yhteydessä tarkastettavuutta varten.

---

### C7.6 Valvonnan integrointi

Reaaliaikainen havaittavuus sulkee silmukan kehityksen ja tuotannon välillä.

 #7.6.1    Level: 1    Role: D
 Varmista, että mittarit (skeeman rikkomiset, hallusinaatiotaso, toksisuus, henkilötietovuodot, viive, kustannukset) siirtyvät keskitettyyn valvonta-alustaan.
 #7.6.2    Level: 1    Role: V
 Varmista, että kullekin turvallisuusmittarille on määritelty hälytysrajat, ja että on olemassa päivystyskorotushakemistot.
 #7.6.3    Level: 2    Role: V
 Varmista, että kojelaudat yhdistävät poikkeavuudet mallin/versioiden, ominaisuuksien kytkimen ja ylävirran datamuutosten kanssa.
 #7.6.4    Level: 2    Role: D/V
 Varmista, että valvontatiedot palautuvat uudelleenkoulutukseen, hienosäätöön tai sääntöpäivityksiin dokumentoidun MLOps-työnkulun puitteissa.
 #7.6.5    Level: 3    Role: V
 Varmista, että seurantaputkistot on testattu tunkeutumisen varalta ja niihin on pääsyrajoitukset, jotta arkaluontoisten lokitietojen vuotaminen estyy.

---

### 7.7 Generatiivisen median suojatoimet

Varmista, että tekoälyjärjestelmät eivät tuota laittomia, haitallisia tai luvattomia mediasisältöjä noudattamalla politiikkarajoituksia, tekemällä tulosten validointia ja varmistamalla jäljitettävyys.

 #7.7.1    Level: 1    Role: D/V
 Varmista, että järjestelmän kehotteet ja käyttäjän ohjeet kieltävät nimenomaisesti laittomien, haitallisten tai ei-suostumuksellisten deepfake-materiaalien (esim. kuvat, videot, äänet) tuottamisen.
 #7.7.2    Level: 2    Role: D/V
 Varmista, että kehotteet suodatetaan yrityksiltä luoda jäljitelmiä, seksuaalisesti eksplisiittisiä deepfake-videoita tai materiaalia, joka kuvaa todellisia henkilöitä ilman suostumusta.
 #7.7.3    Level: 2    Role: V
 Varmista, että järjestelmä käyttää havaintopohjaista hajautusta, vesileiman tunnistusta tai sormenjälkitunnistusta estääkseen tekijänoikeudella suojatun median luvattoman kopioinnin.
 #7.7.4    Level: 3    Role: D/V
 Varmista, että kaikki luotu media on kryptografisesti allekirjoitettu, vesileimattu tai varustettu muokkausta kestävillä alkuperäisyystiedoilla jäljitettävyyttä varten.
 #7.7.5    Level: 3    Role: V
 Varmista, että ohitusyritykset (esim. kehotteen peittely, slangin käyttö, vihamielinen ilmaisutapa) tunnistetaan, kirjataan ja rajoitetaan; toistuva väärinkäyttö raportoidaan valvontajärjestelmille.

### Viitteet

NIST AI Risk Management Framework
ISO/IEC 42001:2023 – AI Management System
OWASP Top-10 for Large Language Model Applications (2025)
Improper Output Handling – OWASP LLM05:2025
Practical Techniques to Constrain LLM Output
Dataiku – Structured Text Generation Guide
VL-Uncertainty: Detecting Hallucinations
HaDeMiF: Hallucination Detection & Mitigation
Building Confidence in LLM Outputs
Explainable AI & LLMs
LLM Red-Teaming Guide
Sensitive Information Disclosure in LLMs
LangChain – Chat Model Rate Limiting
OpenAI Rate-Limit & Exponential Back-off
Arize AI – LLM Observability Platform

## C8-muisti, upotukset ja vektoritietokannan turvallisuus

### Ohjaustavoite

Upotukset ja vektorivarastot toimivat nykyaikaisten tekoälyjärjestelmien "elävinä muistoina", jotka jatkuvasti vastaanottavat käyttäjän tarjoamaa dataa ja palauttavat sen mallien konteksteihin hakua täydentävän generoinnin (Retrieval-Augmented Generation, RAG) kautta. Jos tätä muistia ei hallita, se voi vuotaa henkilötietoja, rikkoa suostumusehtoja tai kääntyä alkuperäisen tekstin rekonstruoimiseksi. Tämän kontrolliperheen tavoitteena on vahvistaa muistiputkia ja vektoritietokantoja siten, että pääsy on vähimmän etuoikeuden periaatteen mukaista, upotukset säilyttävät yksityisyyden, tallennetut vektorit vanhenevat tai ne voidaan perua pyynnöstä, ja käyttäjäkohtainen muisti ei koskaan saastuta toisen käyttäjän kehotteita tai täydentämiä vastauksia.

---

### C8.1 Pääsynhallinta muistille ja RAG-indekseille

Toteuta tarkkarajaiset käyttöoikeuksien valvontamekanismit jokaiseen vektorikokoelmaan.

 #8.1.1    Level: 1    Role: D/V
 Varmista, että rivikohtaiset/namespace-tason käyttöoikeussäännöt rajoittavat lisäys-, poisto- ja kyselytoiminnot jokaiselle vuokralaiselle, kokoelmalle tai asiakirjan tunnisteelle.
 #8.1.2    Level: 1    Role: D/V
 Varmista, että API-avaimissa tai JWT:issä on määritelty rajatut valtuudet (esim. kokoelman tunnisteet, toimintaverbit) ja että ne kierrätetään vähintään neljännesvuosittain.
 #8.1.3    Level: 2    Role: D/V
 Varmista, että etuoikeuksien korotuspyrkimykset (esim. poikkitilan samankaltaisuuskyselyt) havaitaan ja kirjataan SIEM-järjestelmään viiden minuutin kuluessa.
 #8.1.4    Level: 2    Role: D/V
 Varmista, että vektoritietokanta tarkastaa lokia, joka sisältää kohdetunnisteen, toimenpiteen, vektorin tunnuksen/nimiavaruuden, samankaltaisuuskynnyksen ja tulosmäärän.
 #8.1.5    Level: 3    Role: V
 Varmista, että pääsyä koskevat päätökset testataan ohitusvirheiden varalta aina, kun moottoreita päivitetään tai indeksi- jaottelusäännöt muuttuvat.

---

### C8.2 Upotusten puhdistus ja validointi

Esi­tarkista teksti henkilötietojen varalta, sensuroi tai pe­su­doo­ni­mise­raa ennen vektoroimista, ja tarvittaessa poista upotuksista kaikki jäännökselliset signaalit jälkikäsittelyssä.

 #8.2.1    Level: 1    Role: D/V
 Varmista, että henkilötunnistetiedot (PII) ja säädellyt tiedot tunnistetaan automatisoitujen luokittimien avulla ja ne peitetään, tokenisoidaan tai poistetaan ennen upotusta.
 #8.2.2    Level: 1    Role: D
 Varmista, että upotusputket hylkäävät tai eristävät syötteet, jotka sisältävät suoritettavaa koodia tai ei-UTF-8-artifakteja, jotka voisivat myrkyttää indeksin.
 #8.2.3    Level: 2    Role: D/V
 Varmista, että paikallista tai metristä differentiaalisuojaussanitointia sovelletaan lauselausekkeisiin, joiden etäisyys mihin tahansa tunnettuun henkilötietomerkkiin (PII) alittaa asetettavissa olevan kynnyksen.
 #8.2.4    Level: 2    Role: V
 Varmista, että puhdistuksen tehokkuus (esim. henkilötietojen poiston palautuskyky, semanttinen muutosten seuranta) validoidaan vähintään puolen vuoden välein vertailukorpusten avulla.
 #8.2.5    Level: 3    Role: D/V
 Varmista, että puhdistusasetukset ovat versionhallinnassa ja muutokset käyvät läpi vertaisarvioinnin.

---

### C8.3 Muistin vanhentuminen, peruutus ja poisto

GDPR:n "oikeus tulla unohdetuksi" ja vastaavat lait vaativat tietojen oikea-aikaista poistamista; vektorivarastojen on siksi tuettava TTL:iä, pysyviä poistoja ja tomb-stoningia, jotta peruutettuja vektoreita ei voida palauttaa tai uudelleenindeksoida.

 #8.3.1    Level: 1    Role: D/V
 Varmista, että jokainen vektori- ja metatietue sisältää TTL:n tai nimenomaisen säilytysmerkinnän, jota automatisoidut puhdistustehtävät noudattavat.
 #8.3.2    Level: 1    Role: D/V
 Varmista, että käyttäjän aloittamat poistopyynnöt poistavat vektorit, metatiedot, välimuistikopiot ja johdetut indeksit 30 päivän kuluessa.
 #8.3.3    Level: 2    Role: D
 Varmista, että loogisten poistojen jälkeen suoritetaan tallennuslohkojen kryptografinen tuhoaminen, jos laitteisto tukee sitä, tai avainnipun avaimen tuhoaminen.
 #8.3.4    Level: 3    Role: D/V
 Varmista, että vanhentuneet vektorit suljetaan pois lähimmän naapurin hakutuloksista alle 500 ms vanhenemisen jälkeen.

---

### C8.4 Estä upotusten kääntäminen ja vuotaminen

Viimeaikaiset puolustukset—kohinan päällekkäisyys, projektion verkot, yksityisyysneuronin häirintä ja sovelluskerroksen salaus—pystyvät vähentämään token-tason käännösprosentit alle 5 %:iin.

 #8.4.1    Level: 1    Role: V
 Varmista, että olemassa on muodollinen uhkamalli, joka kattaa käännös-, jäsenyys- ja ominaisuustietojen arviointihyökkäykset, ja että sitä tarkastellaan vuosittain.
 #8.4.2    Level: 2    Role: D/V
 Varmista, että sovelluskerroksen salaus tai haettavissa oleva salaus suojaa vektoreita infrastruktuurin ylläpitäjien tai pilvipalvelun henkilöstön suoralta lukemiselta.
 #8.4.3    Level: 3    Role: V
 Varmista, että suojausparametrit (ε DP:lle, kohina σ, projektion rangen k) tasapainottavat yksityisyyden ≥ 99 % tokenin suojauksen ja hyödyllisyyden ≤ 3 % tarkkuuden aleneman kanssa.
 #8.4.4    Level: 3    Role: D/V
 Varmista, että käännösresilienssimittarit ovat osa julkaisujäseniä mallipäivityksille, ja aseta regressiorajat.

---

### C8.5 Käyttöoikeuksien valvonta käyttäjäkohtaiselle muistille

Vuokralaisesta vuokralaiseen tapahtuva vuoto on edelleen merkittävä RAG-riski: huonosti suodatetut samankaltaisuuskyselyt voivat paljastaa toisen asiakkaan yksityiset asiakirjat.

 #8.5.1    Level: 1    Role: D/V
 Varmista, että jokainen hakukysely suodatetaan jälkikäteen vuokralaisen/käyttäjän tunnuksella ennen kuin se lähetetään LLM-kehotteeseen.
 #8.5.2    Level: 1    Role: D
 Varmista, että kokoelman nimet tai nimetyt tunnisteet suolataan käyttäjäkohtaisesti tai vuokraajakohtaisesti, jotta vektorit eivät voi törmätä eri alueiden välillä.
 #8.5.3    Level: 2    Role: D/V
 Varmista, että edellä mainitut samankaltaisuustulokset, jotka ylittävät määritettävissä olevan etäisyyskynnyksen mutta jäävät kutsujan alueen ulkopuolelle, hylätään ja aiheuttavat turvallisuushälytyksiä.
 #8.5.4    Level: 2    Role: V
 Varmista, että monivuokraajaympäristön kuormitustestit simuloivat vihamielisiä kyselyitä, jotka yrittävät hakea soveltamisalan ulkopuolisia asiakirjoja, ja osoittavat nollavuotoa.
 #8.5.5    Level: 3    Role: D/V
 Varmista, että salausavaimet on eroteltu jokaiselle vuokralaiselle erikseen, varmistaen kryptografisen eristyksen, vaikka fyysinen tallennustila olisi jaettu.

---

### C8.6 Kehittynyt muistijärjestelmän suojaus

Turvallisuusvalvontamekanismit kehittyneille muistijärjestelmille, kuten episodiselle, semanttiselle ja työmuistille, joilla on erityiset eristys- ja validointivaatimukset.

 #8.6.1    Level: 1    Role: D/V
 Varmista, että eri muistityypeillä (episodinen, semanttinen, työmuisti) on eristetyt tietoturvakontekstit roolipohjaisilla käyttöoikeuksilla, erilliset salausavaimet ja dokumentoidut käyttömallit kullekin muistityypille.
 #8.6.2    Level: 2    Role: D/V
 Varmista, että muistien konsolidointiprosessit sisältävät turvallisuusvalidoinnin estääkseen haitallisten muistojen injektoinnin sisällön puhdistuksen, lähteen varmennuksen ja eheystarkastusten avulla ennen tallennusta.
 #8.6.3    Level: 2    Role: D/V
 Varmista, että muistin hakukyselyt validoidaan ja puhdistetaan estääkseen luvattoman tiedon poimimisen kyselykuvioiden analyysin, käyttöoikeuksien valvonnan ja tulosten suodatuksen avulla.
 #8.6.4    Level: 3    Role: D/V
 Varmista, että muistin unohtamismekanismit poistavat arkaluonteiset tiedot turvallisesti kryptografisen tuhoamisen takuilla käyttämällä avaimen poistamista, moninkertaista ylikirjoitusta tai laitteistopohjaista turvallista poistamista vahvistustodistusten kanssa.
 #8.6.5    Level: 3    Role: D/V
 Varmista, että muistijärjestelmän eheyttä valvotaan jatkuvasti luvattomien muutosten tai korruptoitumisen varalta käyttämällä tarkistussummia, tarkastuslokeja ja automaattisia hälytyksiä, kun muistin sisältö muuttuu normaalitoimintojen ulkopuolella.

---

### Viitteet

Vector database security: Pinecone – IronCore Labs
Securing the Backbone of AI: Safeguarding Vector Databases and Embeddings – Privacera
Enhancing Data Security with RBAC of Qdrant Vector Database – AI Advances
Mitigating Privacy Risks in LLM Embeddings from Embedding Inversion – arXiv
DPPN: Detecting and Perturbing Privacy-Sensitive Neurons – OpenReview
Art. 17 GDPR – Right to Erasure
Sensitive Data in Text Embeddings Is Recoverable – Tonic.ai
PII Identification and Removal – NVIDIA NeMo Docs
De-identifying Sensitive Data – Google Cloud DLP
Remove PII from Conversations Using Sensitive Information Filters – AWS Bedrock Guardrails
Think Your RAG Is Secure? Think Again – Medium
Design a Secure Multitenant RAG Inferencing Solution – Microsoft Learn
Best Practices for Multi-Tenancy RAG with Milvus – Milvus Blog

## 9 Autonominen orkestrointi ja agenteettinen toiminnan turvallisuus

### Ohjaustavoite

Varmista, että autonomiset tai moniagenttiset tekoälyjärjestelmät voivat suorittaa vain toimia, jotka ovat nimenomaisesti tarkoitettuja, todennettuja, auditoitavissa ja kustannus- sekä riskirajojen sisällä. Tämä suojaa uhkilta kuten autonomisen järjestelmän kaappaus, työkalujen väärinkäyttö, agenttien silmukointihavainnointi, viestinnän kaappaus, identiteetin väärentäminen, parven manipulointi ja aikeiden manipulointi.

---

### 9.1 Agentin tehtäväsuunnittelu ja rekursion budjetit

Rajoita rekursiivisia suunnitelmia ja pakota ihmisen tarkistuspisteet etuoikeutetuissa toiminnoissa.

 #9.1.1    Level: 1    Role: D/V
 Varmista, että maksimisyvyyden, leveyden, seinäajan, tokenien ja rahallisten kustannusten enimmäismäärät agenttien suorituksissa on keskitetysti määritelty ja versiohallittu.
 #9.1.2    Level: 1    Role: D/V
 Varmista, että etuoikeutetut tai peruuttamattomat toimet (esim. koodin sitomiset, rahansiirrot) vaativat ennen suorittamista eksplisiittisen ihmisen hyväksynnän auditoitavan kanavan kautta.
 #9.1.3    Level: 2    Role: D
 Varmista, että reaaliaikaiset resurssienvalvontatyökalut laukaisevat katkaisimen keskeytyksen, kun jokin budjettiraja ylittyy, pysäyttäen lisätehtävien laajentamisen.
 #9.1.4    Level: 2    Role: D/V
 Varmista, että katkaisintapahtumat kirjataan agentin tunnuksella, laukaisevalla ehdolla ja tallennetulla suunnitelmatilalla oikeudellista tarkastelua varten.
 #9.1.5    Level: 3    Role: V
 Varmista, että turvallisuustestit kattavat budjetin ylittymisen ja hallitsemattoman suunnitelman skenaariot, varmistaen turvallisen pysäytyksen ilman tietojen menetystä.
 #9.1.6    Level: 3    Role: D
 Varmista, että budjettipolitiikat on ilmaistu politiikkana koodina ja että niitä sovelletaan CI/CD-putkissa estämään konfiguraation poikkeamia.

---

### 9.2 Työkalulisäosan hiekkalaatikkoympäristö

Eristä työkalujen vuorovaikutukset estääksesi luvattoman järjestelmän käytön tai koodin suorittamisen.

 #9.2.1    Level: 1    Role: D/V
 Varmista, että jokainen työkalu/laajennus suoritetaan käyttöjärjestelmän, kontin tai WASM-tasoisessa hiekkalaatikossa, jossa on vähimmillä oikeuksilla toimivat tiedostojärjestelmä-, verkko- ja järjestelmäkutsu-ikäpolitiikat.
 #9.2.2    Level: 1    Role: D/V
 Varmista, että hiekkalaatikkoympäristön resurssikiintiöt (CPU, muisti, levytila, verkkoliikenteen lähteinen liikenne) ja suoritusaikarajat otetaan käyttöön ja kirjataan.
 #9.2.3    Level: 2    Role: D/V
 Varmista, että työkalujen binaaritiedostot tai kuvaustiedostot ovat digitaalisesti allekirjoitettuja; allekirjoitukset tarkistetaan ennen lataamista.
 #9.2.4    Level: 2    Role: V
 Varmista, että hiekkalaatikon telemetria virtaa SIEM-järjestelmään; poikkeavuudet (esim. yritykset muodostaa ulospäin suuntautuvia yhteyksiä) laukaisevat hälytyksiä.
 #9.2.5    Level: 3    Role: V
 Varmista, että korkean riskin laajennukset käyvät läpi turvallisuustarkastuksen ja tunkeutumistestauksen ennen käyttöönottoa tuotantoympäristössä.
 #9.2.6    Level: 3    Role: D/V
 Varmista, että hiekkalaatikon pakenemispyrkimykset estetään automaattisesti ja että rikkomuksesta vastuussa oleva lisäosa eristetään tutkimuksen ajaksi.

---

### 9.3 Autonominen silmukka ja kustannusten rajaaminen

Havaitse ja pysäytä hallitsematon agenttien välinen rekursio ja kustannusten räjähdys.

 #9.3.1    Level: 1    Role: D/V
 Varmista, että agenttien välisissä kutsuissa on mukana hyppyrajoitus tai TTL, jota ajonaikainen ympäristö vähentää ja valvoo.
 #9.3.2    Level: 2    Role: D
 Varmista, että agentit ylläpitävät ainutlaatuista kutsupuiden tunnistetta (invocation-graph ID) havaitakseen itseinvokaation tai sykliset mallit.
 #9.3.3    Level: 2    Role: D/V
 Varmista, että kumulatiiviset laskentayksikkö- ja kulutuslaskurit seurataan kunkin pyyntöketjun mukaan; rajan ylittäminen keskeyttää ketjun.
 #9.3.4    Level: 3    Role: V
 Varmista, että formaali analyysi tai mallintarkastus osoittaa agenttien protokollissa olevan rekursion rajoittamattomuuden poissaolon.
 #9.3.5    Level: 3    Role: D
 Varmista, että silmukan keskeytystapahtumat luovat hälytyksiä ja syöttävät jatkuvan parantamisen mittareita.

---

### 9.4 Protokollatason väärinkäytön suojaus

Turvalliset viestintäkanavat agenttien ja ulkoisten järjestelmien välillä kaappauksen tai manipuloinnin estämiseksi.

 #9.4.1    Level: 1    Role: D/V
 Varmista, että kaikki agentin ja työkalun sekä agenttien väliset viestit ovat todennettuja (esim. molemminpuolinen TLS tai JWT) ja päästä päähän salattuja.
 #9.4.2    Level: 1    Role: D
 Varmista, että skeemat tarkistetaan tiukasti; tuntemattomat kentät tai virheellisesti muodostetut viestit hylätään.
 #9.4.3    Level: 2    Role: D/V
 Varmista, että eheystarkistukset (MAC-arvot tai digitaaliset allekirjoitukset) kattavat koko viestin sisällön, mukaan lukien työkalun parametrit.
 #9.4.4    Level: 2    Role: D
 Varmista, että uudelleenlähetyksen suojaus (nonssit tai aikaleiman ikkunat) on toteutettu protokollakerroksella.
 #9.4.5    Level: 3    Role: V
 Varmista, että protokollan toteutukset käyvät läpi fuzzauksen ja staattisen analyysin injektio- tai deserialisointivirheiden varalta.

---

### 9.5 Agentin identiteetti ja manipuloinnin havaitseminen

Varmista, että toimet ovat jäljitettävissä ja muutokset havaittavissa.

 #9.5.1    Level: 1    Role: D/V
 Varmista, että jokaisella agentti-instanssilla on ainutlaatuinen kryptografinen identiteetti (avainpari tai laitteistopohjainen tunniste).
 #9.5.2    Level: 2    Role: D/V
 Varmista, että kaikki agenttitoimet on allekirjoitettu ja aikaleimattu; lokit sisältävät allekirjoituksen kiistämisen estämiseksi.
 #9.5.3    Level: 2    Role: V
 Varmista, että manipulointia osoittavat lokit tallennetaan liitettävään tai kirjoituskertaan tallennusvälineeseen.
 #9.5.4    Level: 3    Role: D
 Varmista, että identiteettiavaimet vaihtuvat määritellyn aikataulun mukaisesti ja kompromissin merkkeihin perustuen.
 #9.5.5    Level: 3    Role: D/V
 Varmista, että huijaus- tai avainkonfliktiyritykset aiheuttavat välittömän karanteenin kyseiselle agentille.

---

### 9.6 Moniagenttisen parvitoiminnan riskien vähentäminen

Rajoita kollektiivisen käyttäytymisen vaaroja eristyksen ja muodollisen turvallisuusmallinnuksen avulla.

 #9.6.1    Level: 1    Role: D/V
 Varmista, että eri suojausalueilla toimivat agentit suoritetaan eristetyissä ajonaikaisissa hiekkalaatikoissa tai verkkosegmenteissä.
 #9.6.2    Level: 3    Role: V
 Varmista, että parvetoimintojen mallit on luotu ja ne on muodollisesti varmennettu elinvoimaisuuden ja turvallisuuden osalta ennen käyttöönottoa.
 #9.6.3    Level: 3    Role: D
 Varmista, että ajonaikaiset valvontajärjestelmät havaitsevat nousevat vaaralliset mallit (esim. värähtelyt, umpikuopat) ja käynnistävät korjaavat toimenpiteet.

---

### 9.7 Käyttäjän ja työkalun todennus / valtuutus

Ota käyttöön vahvat pääsynvalvontamekanismit jokaiselle agentin käynnistämälle toiminnolle.

 #9.7.1    Level: 1    Role: D/V
 Varmista, että agentit todentuvat ensiluokkaisina toimijoina alajärjestelmiin käyttäen, eivätkä koskaan uudelleenkäytä loppukäyttäjän tunnistetietoja.
 #9.7.2    Level: 2    Role: D
 Varmista, että hienojakoiset valtuutuspolitiikat rajoittavat, mitä työkaluja agentti saa käyttää ja mitä parametreja se saa antaa.
 #9.7.3    Level: 2    Role: V
 Varmista, että käyttöoikeustarkistukset arvioidaan uudelleen jokaisella kutsulla (jatkuva valtuutus), ei vain istunnon alussa.
 #9.7.4    Level: 3    Role: D
 Varmista, että valtuutetut oikeudet vanhenevat automaattisesti ja että niiden vahvistaminen vaatii uudelleen suostumuksen aikakatkaisun tai käyttöoikeusalueen muutoksen jälkeen.

---

### 9.8 Agenttien välinen viestinnän turvallisuus

Salaa ja suojaa kaikki agenttien väliset viestit eheyden varmistamiseksi estääksesi salakuuntelun ja manipuloinnin.

 #9.8.1    Level: 1    Role: D/V
 Varmista, että keskinäinen todennus ja täydellinen eteenpäin suojattu salaus (esim. TLS 1.3) ovat pakollisia agenttikanaville.
 #9.8.2    Level: 1    Role: D
 Varmista, että viestin eheys ja alkuperä tarkistetaan ennen käsittelyä; epäonnistumiset aiheuttavat hälytyksiä ja viestin hylkäämisen.
 #9.8.3    Level: 2    Role: D/V
 Varmista, että viestinnän metatiedot (aikaleimat, sekvenssinumerot) kirjataan forensista uudelleenrakennusta varten.
 #9.8.4    Level: 3    Role: V
 Varmista, että formaali verifiointi tai mallintarkastus vahvistaa, että protokollan tilakoneita ei voida johtaa vaarallisiin tiloihin.

---

### 9.9 Tarkoituksen vahvistaminen ja rajoitusten noudattamisen varmistaminen

Varmista, että agentin toimet vastaavat käyttäjän ilmoitettua tarkoitusta ja järjestelmän rajoituksia.

 #9.9.1    Level: 1    Role: D
 Varmista, että esisuorituksen rajoiteanalysoijat tarkistavat ehdotetut toiminnot kovakoodattuja turvallisuus- ja politiikkasääntöjä vastaan.
 #9.9.2    Level: 2    Role: D/V
 Varmista, että merkittäviä toimenpiteitä (taloudellisia, tuhoisia, yksityisyydensuojan kannalta herkkiä) varten vaaditaan selkeä tarkoituksen vahvistus aloittavalta käyttäjältä.
 #9.9.3    Level: 2    Role: V
 Varmista, että jälkiehtojen tarkistukset validoivat, että suoritetut toimenpiteet saavuttivat tarkoitetut vaikutukset ilman sivuvaikutuksia; epäjohdonmukaisuudet käynnistävät palautuksen.
 #9.9.4    Level: 3    Role: V
 Vahvista, että formaalit menetelmät (esim. mallintarkastus, aksiomien todistaminen) tai ominaisuusperusteiset testit osoittavat, että agenttien suunnitelmat täyttävät kaikki ilmoitetut rajoitukset.
 #9.9.5    Level: 3    Role: D
 Varmista, että tarkoituksenmukaisuuden poikkeamat tai rajoitusten rikkomistapaukset syöttävät jatkuvan parantamisen sykleihin ja uhkatiedon jakamiseen.

---

### 9.10 Agentin päättelystrategian turvallisuus

Eri päättelystrategioiden, kuten ReActin, Chain-of-Thoughtin ja Tree-of-Thoughts-lähestymistapojen turvallinen valinta ja suoritus.

 #9.10.1    Level: 1    Role: D/V
 Varmista, että päättelystrategian valinta perustuu deterministisiin kriteereihin (tulosteen monimutkaisuus, tehtävän tyyppi, turvallisuuskonteksti) ja että identtiset syötteet tuottavat identtiset strategian valinnat saman turvallisuuskontekstin sisällä.
 #9.10.2    Level: 1    Role: D/V
 Varmista, että jokaisella päättelystrategialla (ReAct, Chain-of-Thought, Tree-of-Thoughts) on oma syötteen validointi, tulosten puhdistus ja suoritusaikarajat, jotka ovat räätälöity sen kognitiivisen lähestymistavan mukaisesti.
 #9.10.3    Level: 2    Role: D/V
 Varmista, että päättelystrategian siirtymät kirjataan täydellisen kontekstin kanssa, mukaan lukien syötteen ominaisuudet, valintakriteerien arvot ja suoritusmetadata, auditointijäljen uudelleenrakentamista varten.
 #9.10.4    Level: 2    Role: D/V
 Varmista, että Tree-of-Thoughts -päättely sisältää haarojen karsimismekanismit, jotka lopettavat tutkinnan, kun havaitaan politiikan rikkomuksia, resurssirajoituksia tai turvallisuusrajoja.
 #9.10.5    Level: 2    Role: D/V
 Varmista, että ReAct (Reason-Act-Observe) -syklit sisältävät validointipisteet kussakin vaiheessa: päättelyaskeleen tarkistus, toiminnan valtuutus ja havainnon puhdistus ennen etenemistä.
 #9.10.6    Level: 3    Role: D/V
 Varmista, että päättelystrategian suorituskykymittareita (suoritusaika, resurssien käyttö, tuloksen laatu) seurataan ja että poikkeamista asetettuihin raja-arvoihin annetaan automaattiset hälytykset.
 #9.10.7    Level: 3    Role: D/V
 Varmista, että hybridipäätöksentekomenetelmät, jotka yhdistävät useita strategioita, säilyttävät kaikkien osastrategioiden syötteen validoinnin ja tulosrajoitukset ilman, että kiertävät yhtäkään turvallisuusvalvontaa.
 #9.10.8    Level: 3    Role: D/V
 Varmista, että päättelystrategian turvallisuustestaus sisältää väärinmuotoiltujen syötteiden fuzzauksen, vastustavat kehotteet, jotka on suunniteltu pakottamaan strategian vaihto, sekä rajatilaustestauksen jokaiselle kognitiiviselle lähestymistavalle.

---

### 9.11 Agentin elinkaaren tilanhallinta ja turvallisuus

Turvallinen agentin alustaminen, tilan muutokset ja lopetus kryptografisten tarkastusjälkien ja määriteltyjen palautusmenettelyjen avulla.

 #9.11.1    Level: 1    Role: D/V
 Varmista, että agentin alustus sisältää kryptografisen identiteetin perustamisen laitteistopohjaisilla tunnuksilla sekä muuttumattomat käynnistysauditointilokit, jotka sisältävät agentin tunnuksen, aikaleiman, kokoonpanohashin ja alustuksen parametrit.
 #9.11.2    Level: 2    Role: D/V
 Varmista, että agentin tilasiirtymät ovat kryptografisesti allekirjoitettuja, aikaleimattuja ja kirjattuja täydellisen kontekstin kanssa, mukaan lukien laukaisevat tapahtumat, edellisen tilan tiiviste, uuden tilan tiiviste ja suoritetut tietoturvatarkastukset.
 #9.11.3    Level: 2    Role: D/V
 Varmista, että agentin sammutusmenettelyt sisältävät turvallisen muistin tyhjennyksen käyttäen kryptografista poistamista tai monivaiheista ylikirjoitusta, tunnistetietojen peruutuksen varmenneviranomaiselle ilmoittamisen kanssa sekä muuttamattomuuden todistavien päättötodistusten luomisen.
 #9.11.4    Level: 3    Role: D/V
 Varmista, että agentin palautusmekanismit validoivat tilan eheyden käyttämällä kryptografisia tarkistussummia (vähintään SHA-256) ja palauttavat tilan tunnetusti ehjiin tiloihin, kun korruptio havaitaan, käyttäen automatisoituja hälytyksiä ja manuaalisia hyväksymisvaatimuksia.
 #9.11.5    Level: 3    Role: D/V
 Varmista, että agentin pysyvyysmekanismit salaavat arkaluontoiset tilatiedot agenttikohtaisilla AES-256-avaimilla ja toteuttavat turvallisen avainten kierrätyksen määritettävissä aikatauluissa (enintään 90 päivää) niin, että käyttöönotto tapahtuu ilman seisokkeja.

---

### 9.12 Työkalujen integraation turvallisuuskehys

Turvallisuusvalvontamekanismit dynaamiseen työkalujen lataamiseen, suorittamiseen ja tulosten validointiin määriteltyjen riskinarviointi- ja hyväksymisprosessien mukaisesti.

 #9.12.1    Level: 1    Role: D/V
 Varmista, että työkalukuvaajat sisältävät turvadataa, jossa määritellään vaaditut oikeudet (luku/kirjoitus/suoritus), riskitasot (matala/keskitaso/korkea), resurssirajoitukset (CPU, muisti, verkko) ja työkaluluetteloissa dokumentoidut validointivaatimukset.
 #9.12.2    Level: 1    Role: D/V
 Varmista, että työkalun suoritusresultaatit validoidaan odotettujen skeemojen (JSON-skeema, XML-skeema) ja turvallisuuspolitiikkojen (tulosteen puhdistus, dataluokittelu) mukaisesti ennen integrointia aikakatkaisurajojen ja virheenkäsittelymenetelmien kanssa.
 #9.12.3    Level: 2    Role: D/V
 Varmista, että työkalun vuorovaikutuslokit sisältävät yksityiskohtaisen turvallisuuskontekstin, mukaan lukien oikeustason käyttö, tietojen käyttökuviot, suoritusaika, resurssien kulutus ja paluuarvot rakenteellisella lokituksella SIEM-integraatiota varten.
 #9.12.4    Level: 2    Role: D/V
 Varmista, että dynaamiset työkalujen latausmekanismit validoivat digitaaliset allekirjoitukset PKI-infrastruktuurin avulla ja toteuttavat turvalliset latausprotokollat hiekkalaatikkoympäristön eristämisellä sekä käyttöoikeuksien varmennuksella ennen suorittamista.
 #9.12.5    Level: 3    Role: D/V
 Varmista, että työkalujen turvallisuusarvioinnit käynnistyvät automaattisesti uusille versioille pakollisten hyväksymiskanavien avulla, jotka sisältävät staattisen analyysin, dynaamisen testauksen ja turvallisuustiimin tarkastelun, dokumentoiduilla hyväksymiskriteereillä ja SLA-vaatimuksilla.

---

#### Viitteet

MITRE ATLAS tactics ML09
Circuit-breaker research for AI agents — Zou et al., 2024
Trend Micro analysis of sandbox escapes in AI agents — Park, 2025
Auth0 guidance on human-in-the-loop authorization for agents — Martinez, 2025
Medium deep-dive on MCP & A2A protocol hijacking — ForAISec, 2025
Rapid7 fundamentals on spoofing attack prevention — 2024
Imperial College verification of swarm systems — Lomuscio et al.
NIST AI Risk Management Framework 1.0, 2023
WIRED security briefing on encryption best practices, 2024
OWASP Top 10 for LLM Applications, 2025
Comprehensive Vulnerability Analysis is Necessary for Trustworthy LLM-MAS
[How Is LLM Reasoning Distracted by Irrelevant Context?
An Analysis Using a Controlled Benchmark](https://www.arxiv.org/pdf/2505.18761)
Large Language Model Sentinel: LLM Agent for Adversarial Purification
Securing Agentic AI: A Comprehensive Threat Model and Mitigation Framework for Generative AI Agents

## 10 Vihamielinen kestävyys ja yksityisyyden suojaaminen

### Ohjaustavoite

Varmista, että tekoälymallit pysyvät luotettavina, yksityisyyttä suojaavina ja väärinkäytöksiltä suojattuina vastustaessaan kiertämis-, päättely-, poiminta- tai myrkytyshyökkäyksiä.

---

### 10.1 Mallin sovitus ja turvallisuus

Suojaa haitallisilta tai politiikkaa rikkovilta tulosteilta.

 #10.1.1    Level: 1    Role: D/V
 Varmista, että yhdenmukaisuuden testikokoelma (red-team-kehotteet, jailbreak-kyselyt, kielletty sisältö) on versionhallinnassa ja suoritetaan jokaisen mallijulkaisun yhteydessä.
 #10.1.2    Level: 1    Role: D
 Varmista, että kieltäytymisen ja turvallisen suorituksen suojakehykset ovat voimassa.
 #10.1.3    Level: 2    Role: D/V
 Varmista, että automatisoitu arvostelija mittaa haitallisen sisällön määrää ja merkitsee uudelleenlaskennat, jotka ylittävät asetetun kynnyksen.
 #10.1.4    Level: 2    Role: D
 Varmista, että vastamurtokoulutus on dokumentoitu ja toistettavissa.
 #10.1.5    Level: 3    Role: V
 Varmista, että muodolliset politiikanmukaisuuden todisteet tai sertifioitu valvonta kattavat kriittiset alueet.

---

### 10.2 Vastustavien esimerkkien vahvistaminen

Lisää vastustuskykyä manipuloiduille syötteille. Vahva vastustajapohjainen koulutus ja vertailuarviointi ovat nykyiset parhaat käytännöt.

 #10.2.1    Level: 1    Role: D
 Varmista, että projektivarastoissa on vihamielisen koulutuksen asetukset toistettavilla siemenarvoilla.
 #10.2.2    Level: 2    Role: D/V
 Varmista, että vihamielisten esimerkkien tunnistus laukaisee estohälytykset tuotantoputkissa.
 #10.2.4    Level: 3    Role: V
 Varmista, että sertifioidut kestävyyden todistukset tai väliarvorajat kattavat vähintään tärkeimmät kriittiset luokat.
 #10.2.5    Level: 3    Role: V
 Varmista, että regressiotestit käyttävät adaptiivisia hyökkäyksiä vahvistaakseen, ettei havaittavissa ole suorituskyvyn heikkenemistä.

---

### 10.3 Kuuluvuuden päättelyn lieventäminen

Rajoita kykyä päättää, oliko tietue harjoitusdatassa. Differentiaalinen yksityisyys ja luottamusarvon peittäminen ovat edelleen tehokkaimmat tunnetut suojakeinot.

 #10.3.1    Level: 1    Role: D
 Varmista, että kyselykohtainen entropian säännöstely tai lämpötilan skaalaus vähentää yliluottavaisia ennusteita.
 #10.3.2    Level: 2    Role: D
 Varmista, että harjoittelu käyttää ε-rajoitettua differentiaalista yksityisyyttä hyödyntävää optimointia arkaluonteisille tietoaineistoille.
 #10.3.3    Level: 2    Role: V
 Varmista, että hyökkäyssimulaatiot (varjomalli tai mustan laatikon menetelmä) näyttävät hyökkäyksen AUC ≤ 0,60 erikseen pidetyissä testeissä.

---

### 10.4 Mallin kääntövastus

Estä yksityisten attribuuttien uudelleenrakentaminen. Viimeaikaiset tutkimukset korostavat tuloksen katkaisua ja differentiaalisen yksityisyyden (DP) takuita käytännöllisinä suojakeinoina.

 #10.4.1    Level: 1    Role: D
 Varmista, että arkaluonteisia attribuutteja ei koskaan suoraan tulosteta; tarvittaessa käytä luokkia tai yksisuuntaisia muunnoksia.
 #10.4.2    Level: 1    Role: D/V
 Varmista, että kyselynopeusrajoitukset hillitsevät toistuvia adaptiivisia kyselyjä samalta taholta.
 #10.4.3    Level: 2    Role: D
 Varmista, että malli on koulutettu yksityisyyttä suojaavalla häiriöllä.

---

### 10.5 Mallin uuttamisen torjunta

Havaitse ja estä luvaton kloonaus. Suositellaan vesileimausta ja kyselykuvion analyysiä.

 #10.5.1    Level: 1    Role: D
 Varmista, että inferenssisillat toteuttavat globaaleja ja API-avainkohtaisia käyttötaajuusrajoituksia, jotka on säädetty mallin muistamisen kynnyksen mukaan.
 #10.5.2    Level: 2    Role: D/V
 Varmista, että kysely-entropia- ja syöte-monimuotoisuusstatistiikat syöttävät automaattisen poiminnan tunnistimen.
 #10.5.3    Level: 2    Role: V
 Varmista, että hauraita tai todennäköisyyspohjaisia vesileimoja voidaan todistaa p-arvolla < 0,01 enintään 1 000 kyselyllä epäillyn kloonin kohdalla.
 #10.5.4    Level: 3    Role: D
 Varmista, että vesileimain avaimet ja laukaisuvarmistukset tallennetaan laitteistoturvamoduuliin ja vaihdetaan vuosittain.
 #10.5.5    Level: 3    Role: V
 Varmista, että poiminta-hälytys tapahtumat sisältävät rikkomukseen johtavat kyselyt ja on integroitu tapausvastauksen toimintasuunnitelmiin.

---

### 10.6 Inferenssiajan myrkytetyn datan tunnistus

Tunnista ja neutralisoi takaportilla tai myrkyllä manipuloidut syötteet.

 #10.6.1    Level: 1    Role: D
 Varmista, että syötteet kulkevat poikkeavuustunnistimen (esim. STRIP, konsistenssipisteytys) kautta ennen mallin päätelmää.
 #10.6.2    Level: 1    Role: V
 Varmista, että havaitsemiskynnykset on säädetty puhtailla/myrkyllisillä vahvistusjoukoilla siten, että virheellisiä positiivisia ilmoituksia on alle 5%.
 #10.6.3    Level: 2    Role: D
 Varmista, että myrkyllisiksi merkityt syötteet laukaisevat pehmeän eston ja ihmisen tarkastusprosessit.
 #10.6.4    Level: 2    Role: V
 Varmista, että detektorit altistetaan kuormitustestaukselle adaptiivisilla ilman laukaistinta toimivilla takaoven hyökkäyksillä.
 #10.6.5    Level: 3    Role: D
 Varmista, että tunnistustehokkuuden mittarit kirjataan ja arvioidaan uudelleen säännöllisesti uusilla uhkatiedoilla.

---

### 10.7 Dynaaminen turvallisuuspolitiikan mukauttaminen

Reaaliaikaiset tietoturvapolitiikan päivitykset uhkatiedon ja käyttäytymisanalyysin perusteella.

 #10.7.1    Level: 1    Role: D/V
 Varmista, että tietoturvakäytäntöjä voidaan päivittää dynaamisesti ilman agentin uudelleenkäynnistystä samalla, kun varmistetaan käytäntöversion eheys.
 #10.7.2    Level: 2    Role: D/V
 Varmista, että politiikkapäivitykset on kryptografisesti allekirjoitettu valtuutettujen turvallisuushenkilöiden toimesta ja validoitu ennen soveltamista.
 #10.7.3    Level: 2    Role: D/V
 Varmista, että dynaamiset politiikkamuutokset kirjataan täydellisin tarkastuslokein, jotka sisältävät perustelut, hyväksymisketjut ja palautusmenettelyt.
 #10.7.4    Level: 3    Role: D/V
 Varmista, että adaptiiviset tietoturvamekanismit säätelevät uhkien havaitsemisen herkkyyttä riskikontekstin ja käyttäytymismallien perusteella.
 #10.7.5    Level: 3    Role: D/V
 Varmista, että politiikan mukauttamispäätökset ovat selitettäviä ja sisältävät todistepolut turvallisuusryhmän tarkastelua varten.

---

### 10.8 Heijastusperusteinen turvallisuusanalyysi

Turvallisuuden validointi agentin itsearvioinnin ja metakognitiivisen analyysin kautta.

 #10.8.1    Level: 1    Role: D/V
 Varmista, että agentin reflektiojärjestelmät sisältävät turvallisuuteen keskittyvän itsearvioinnin päätöksistä ja toimista.
 #10.8.2    Level: 2    Role: D/V
 Varmista, että heijastusten tulokset validoidaan estämään itsearviointimekanismien manipulointi vihamielisillä syötteillä.
 #10.8.3    Level: 2    Role: D/V
 Varmista, että metakognitiivinen turvallisuusanalyysi tunnistaa mahdollisen puolueellisuuden, manipuloinnin tai väärinkäytön agentin päättelyprosesseissa.
 #10.8.4    Level: 3    Role: D/V
 Varmista, että heijastusperusteiset turvallisuusvaroitukset laukaisevat tehostetun valvonnan ja mahdolliset ihmisen väliintulon työnkulut.
 #10.8.5    Level: 3    Role: D/V
 Varmista, että jatkuva oppiminen turvallisuusreflektioista parantaa uhkien havaitsemista vaarantamatta laillista toimintaa.

---

### 10.9 Evoluutio ja itseparannuksen turvallisuus

Turvallisuusvalvontatoimet itsensä muokkaamiseen ja kehittymiseen kykeneville agenttijärjestelmille.

 #10.9.1    Level: 1    Role: D/V
 Varmista, että itse-modifikaatiokykyjä rajoitetaan nimetyille turvallisille alueille muodollisten varmennusrajojen puitteissa.
 #10.9.2    Level: 2    Role: D/V
 Varmista, että evoluutiosehdotukset käyvät läpi turvallisuusvaikutusten arvioinnin ennen käyttöönottoa.
 #10.9.3    Level: 2    Role: D/V
 Varmista, että itseparannusmekanismit sisältävät paluuominaisuudet ja eheyden tarkistuksen.
 #10.9.4    Level: 3    Role: D/V
 Varmista, että metaoppimisen tietoturva estää parannusalgoritmien vihamielisen manipuloinnin.
 #10.9.5    Level: 3    Role: D/V
 Varmista, että rekursiivinen itseparantaminen on rajattu muodollisilla turvallisuusrajoitteilla matemaattisilla todisteilla suppenemisesta.

---

#### Viitteet

MITRE ATLAS adversary tactics for ML
NIST AI Risk Management Framework 1.0, 2023
OWASP Top 10 for LLM Applications, 2025
Adversarial Training: A Survey — Zhao et al., 2024
RobustBench adversarial-robustness benchmark
Membership-Inference & Model-Inversion Risk Survey, 2025
PURIFIER: Confidence-Score Defense against MI Attacks — AAAI 2023
Model-Inversion Attacks & Defenses Survey — AI Review, 2025
Comprehensive Defense Framework Against Model Extraction — IEEE TDSC 2024
Fragile Model Watermarking Survey — 2025
Data Poisoning in Deep Learning: A Survey — Zhao et al., 2025
BDetCLIP: Multimodal Prompting Backdoor Detection — Niu et al., 2024

## 11 Tietosuoja ja henkilötietojen hallinta

### Kontrollitavoite

Ylläpidä tiukkoja yksityisyystakuita koko tekoälyn elinkaaren ajan—keräämisen, koulutuksen, päättelyn ja häiriötilanteisiin reagoinnin aikana—jotta henkilötietoja käsitellään vain selkeällä suostumuksella, tarvittavimmassa laajuudessa, todennettavissa olevalla poistolla ja muodollisilla yksityisyystakuuilla.

---

### 11.1 Anonymisointi ja datan minimointi

 #11.1.1    Level: 1    Role: D/V
 Varmista, että suorat ja kvasi-tunnisteet poistetaan tai hajautetaan.
 #11.1.2    Level: 2    Role: D/V
 Varmista, että automaattiset tarkastukset mittaavat k-anonymiteettiä/l-monimuotoisuutta ja antavat hälytyksen, kun kynnysarvot laskevat politiikan alapuolelle.
 #11.1.3    Level: 2    Role: V
 Varmista, että mallin ominaisuuksien tärkeysraportit osoittavat, ettei tunnistevuotoa esiinny yli ε = 0,01 keskinäisen informaation.
 #11.1.4    Level: 3    Role: V
 Varmista, että muodolliset todistukset tai synteettisen datan sertifiointi osoittavat uudelleentunnistamisriskin olevan ≤ 0,05 jopa linkitysiskujen aikana.

---

### 11.2 Oikeus tulla unohdetuksi ja poistamisen täytäntöönpano

 #11.2.1    Level: 1    Role: D/V
 Varmista, että henkilötietojen poistopyynnöt leviävät raakadatakokoelmiin, tarkistuspisteisiin, upotuksiin, lokitietoihin ja varmuuskopioihin alle 30 päivän palvelutasosopimuksen puitteissa.
 #11.2.2    Level: 2    Role: D
 Varmista, että "koneoppimisen unohtaminen" -rutiinit fyysisesti uudelleenkouluttavat tai lähestyvät poistoa sertifioiduilla unohtamisen algoritmeilla.
 #11.2.3    Level: 2    Role: V
 Varmista, että varjomallin arviointi todistaa unohdettujen tietueiden vaikuttavan alle 1 % tuloksista unohdettamisen jälkeen.
 #11.2.4    Level: 3    Role: V
 Varmista, että poistotapahtumat kirjataan muuttumattomasti ja ovat auditoitavissa sääntelyviranomaisille.

---

### 11.3 Diferentiaalisen yksityisyyden turvatoimet

 #11.3.1    Level: 2    Role: D/V
 Varmista, että yksityisyyden menetyslaskentapaneelit hälyttävät, kun kumulatiivinen ε ylittää politiikan asettamat rajat.
 #11.3.2    Level: 2    Role: V
 Varmista, että mustan laatikon tietosuojatarkastukset arvioivat ε̂:n enintään 10 %:n tarkkuudella ilmoitetusta arvosta.
 #11.3.3    Level: 3    Role: V
 Varmista, että muodolliset todistukset kattavat kaikki jälkikoulutuksen hienosäädöt ja upotukset.

---

### 11.4 Tarkoituksen rajoittaminen ja laajuuden hallinta

 #11.4.1    Level: 1    Role: D
 Varmista, että jokaisessa tietojoukossa ja mallin tarkistuspisteessä on koneellisesti luettava käyttötarkoitustunniste, joka vastaa alkuperäistä suostumusta.
 #11.4.2    Level: 1    Role: D/V
 Varmista, että suoritusajan valvontajärjestelmät havaitsevat kyselyt, jotka ovat ristiriidassa ilmoitetun tarkoituksen kanssa, ja laukaisevat kevyen kieltäytymisen.
 #11.4.3    Level: 3    Role: D
 Varmista, että politiikka-koodina -portit estävät mallien uudelleenkäytön uusille toimialueille ilman DPIA-tarkastelua.
 #11.4.4    Level: 3    Role: V
 Varmista, että muodolliset jäljitettävyystodistukset osoittavat, että jokainen henkilötietojen elinkaaren vaihe pysyy suostumuksen mukaisessa laajuudessa.

---

### 11.5 Suostumuksen hallinta ja laillisen perusteen seuranta

 #11.5.1    Level: 1    Role: D/V
 Varmista, että suostumuksenhallintajärjestelmä (CMP) tallentaa kunkin rekisteröidyn osapuolen valintatilan, käyttötarkoituksen ja säilytysajan.
 #11.5.2    Level: 2    Role: D
 Varmista, että API:t paljastavat suostumustunnukset; mallien on validoitava tunnuksen käyttöoikeus ennen päättelyä.
 #11.5.3    Level: 2    Role: D/V
 Varmista, että evätty tai peruutettu suostumus pysäyttää käsittelyputket 24 tunnin kuluessa.

---

### 11.6 Federatiivinen oppiminen yksityisyydensuojan hallinnalla

 #11.6.1    Level: 1    Role: D
 Varmista, että asiakas päivitykset käyttävät paikallisen differentiaalisen yksityisyyden melun lisäystä ennen yhdistämistä.
 #11.6.2    Level: 2    Role: D/V
 Varmista, että koulutusmittarit ovat differentiaalisesti yksityisiä eivätkä koskaan paljasta yksittäisen asiakkaan tappiota.
 #11.6.3    Level: 2    Role: V
 Varmista, että myrkytyskestävä yhdistely (esim. Krum/Trimmed-Mean) on käytössä.
 #11.6.4    Level: 3    Role: V
 Varmista, että muodolliset todistukset osoittavat kokonais-ε-budjetin, jossa hyötymenetys on alle 5.

---

#### Viitteet

GDPR & AI Compliance Best Practices
EU Parliament Study on GDPR & AI, 2020
ISO 31700-1:2023 — Privacy by Design for Consumer Products
NIST Privacy Framework 1.1 (2025 Draft)
Machine Unlearning: Right-to-Be-Forgotten Techniques
A Survey of Machine Unlearning, 2024
Auditing DP-SGD — ArXiv 2024
DP-SGD Explained — PyTorch Blog
Purpose-Limitation for AI — IJLIT 2025
Data-Protection Considerations for AI — URM Consulting
Top Consent-Management Platforms, 2025
Secure Aggregation in DP Federated Learning — ArXiv 2024

## C12 Valvonta, lokitus ja poikkeavuuksien havaitseminen

### Kontrollin tavoite

Tämä osio sisältää vaatimukset reaaliaikaisen ja tutkintatason näkyvyyden tarjoamiseksi siihen, mitä malli ja muut tekoälykomponentit näkevät, tekevät ja palauttavat, jotta uhkia voidaan havaita, arvioida ja oppia niistä.

### C12.1 Pyyntöjen ja vastausten kirjaaminen

 #12.1.1    Level: 1    Role: D/V
 Varmista, että kaikki käyttäjän kehoteet ja mallin vastaukset kirjataan asianmukaisilla metatiedoilla (esim. aikaleima, käyttäjätunnus, istunnon tunnus, malliversio).
 #12.1.2    Level: 1    Role: D/V
 Varmista, että lokit tallennetaan turvallisiin, pääsynvalvottuihin säilytyspaikkoihin, joissa on asianmukaiset säilytyskäytännöt ja varmuuskopiointimenettelyt.
 #12.1.3    Level: 1    Role: D/V
 Varmista, että lokien tallennusjärjestelmät toteuttavat salauksen levossa ja siirrossa suojatakseen lokeissa olevia arkaluonteisia tietoja.
 #12.1.4    Level: 1    Role: D/V
 Varmista, että kehotteiden ja tulosteiden arkaluonteiset tiedot sensuroidaan tai peitetään automaattisesti ennen kirjaamista, ja että sensurointisäännöt henkilökohtaisille tunnistetiedoille (PII), tunnuksille ja omistusoikeuteen kuuluville tiedoille ovat konfiguroitavissa.
 #12.1.5    Level: 2    Role: D/V
 Varmista, että politiikkapäätökset ja turvallisuussuodatus toimenpiteet kirjataan riittävän yksityiskohtaisesti, jotta sisällönvalvontajärjestelmien tarkastaminen ja virheiden korjaaminen on mahdollista.
 #12.1.6    Level: 2    Role: D/V
 Varmista, että lokien eheys on suojattu esimerkiksi kryptografisilla allekirjoituksilla tai kirjoitusvain tallennuksella.

---

### C12.2 Väärinkäytösten tunnistus ja hälyttäminen

 #12.2.1    Level: 1    Role: D/V
 Varmista, että järjestelmä havaitsee ja hälyttää tunnetuista jailbreak-kuvioista, kehotteiden injektiopyrkimyksistä ja vastustavista syötteistä käyttämällä allekirjoituspohjaista tunnistusta.
 #12.2.2    Level: 1    Role: D/V
 Varmista, että järjestelmä integroituu olemassa oleviin turvallisuustieto- ja tapahtumahallinnan (SIEM) alustoihin käyttäen standardeja lokimuotoja ja protokollia.
 #12.2.3    Level: 2    Role: D/V
 Varmista, että rikastetuissa turvallisuustapahtumissa on tekoälyyn liittyvää kontekstia, kuten mallin tunnisteita, luottamuspisteitä ja turvallisuussuodattimen päätöksiä.
 #12.2.4    Level: 2    Role: D/V
 Varmista, että käyttäytymisen poikkeavuuksien havaitseminen tunnistaa epätavalliset keskustelumallit, liiallisen uudelleenkäyttöyritysten määrän tai systemaattiset tutkiskelukäyttäytymiset.
 #12.2.5    Level: 2    Role: D/V
 Varmista, että reaaliaikaiset hälytysmekanismit ilmoittavat turvallisuustiimeille, kun mahdollisia sääntörikkomuksia tai hyökkäyspyrkimyksiä havaitaan.
 #12.2.6    Level: 2    Role: D/V
 Varmista, että mukautetut säännöt on lisätty tunnistamaan tekoälyyn liittyviä uhkakuvioita, kuten koordinoituja jailbreak-yrityksiä, komennon injektointikampanjoita ja mallin poiminta -hyökkäyksiä.
 #12.2.7    Level: 3    Role: D/V
 Varmista, että automatisoidut häiriötilanteiden käsittelytyönkulut voivat eristää vaarantuneet mallit, estää haitalliset käyttäjät ja nostaa esiin kriittiset tietoturvatapahtumat.

---

### C12.3 Mallin liukuman havaitseminen

 #12.3.1    Level: 1    Role: D/V
 Varmista, että järjestelmä seuraa perussuorituskykymittareita, kuten tarkkuutta, luottamusarvoja, viivettä ja virheprosentteja malliversioiden ja ajanjaksojen välillä.
 #12.3.2    Level: 2    Role: D/V
 Varmista, että automaattinen hälytys aktivoituu, kun suorituskykymittarit ylittävät ennalta määritetyt heikentymiskynnykset tai poikkeavat merkittävästi vertailutasoista.
 #12.3.3    Level: 2    Role: D/V
 Varmista, että harhantunnistuksen valvojat havaitsevat ja merkitsevät tapaukset, joissa mallin tuottamassa sisällössä on tosiasiallisesti virheellistä, epäjohdonmukaista tai keksittyä tietoa.

---

### C12.4 Suorituskyky- ja käyttäytymistietojen telemetria

 #12.4.1    Level: 1    Role: D/V
 Varmista, että operatiiviset mittarit, mukaan lukien pyyntöviive, tokenien kulutus, muistin käyttö ja läpimeno, kerätään ja seurataan jatkuvasti.
 #12.4.2    Level: 1    Role: D/V
 Varmista, että onnistumis- ja epäonnistumisprosentit seurataan virhetyyppien ja niiden perussyiden luokittelun avulla.
 #12.4.3    Level: 2    Role: D/V
 Varmista, että resurssien käytön seuranta kattaa GPU/CPU:n käytön, muistinkulutuksen ja tallennustarpeet sekä sisältää hälytykset kynnysarvorikkomuksista.

---

### C12.5 AI-tapahtumien käsittelysuunnittelu ja toteutus

 #12.5.1    Level: 1    Role: D/V
 Varmista, että häiriötilanteiden hallintasuunnitelmat käsittelevät nimenomaisesti tekoälyyn liittyviä tietoturvatapahtumia, kuten mallin vaarantumista, datan myrkyttämistä ja vastustavien hyökkäysten torjuntaa.
 #12.5.2    Level: 2    Role: D/V
 Varmista, että häiriönhallintatiimeillä on käytössään tekoälyyn erikoistuneet forensiset työkalut ja asiantuntemus mallin käyttäytymisen ja hyökkäysvektoreiden tutkimiseksi.
 #12.5.3    Level: 3    Role: D/V
 Varmista, että jälkitapahtuma-analyysi sisältää mallin uudelleenkoulutuksen huomioimisen, turvallisuussuodattimien päivitykset ja opittujen asioiden integroinnin tietoturvakontrolleihin.

---

### C12.5 AI:n suorituskyvyn heikkenemisen havaitseminen

Seuraa ja havaitse tekoälymallin suorituskyvyn ja laadun heikkenemistä ajan myötä.

 #12.5.1    Level: 1    Role: D/V
 Varmista, että mallin tarkkuutta, precision, recall-arvoja ja F1-mittareita seurataan jatkuvasti ja verrataan perustasoarvoihin.
 #12.5.2    Level: 1    Role: D/V
 Varmista, että datan muutoksen havaitseminen valvoo syötteen jakauman muutoksia, jotka voivat vaikuttaa mallin suorituskykyyn.
 #12.5.3    Level: 2    Role: D/V
 Varmista, että käsitepoikkeaman havainto tunnistaa muutokset syötteiden ja odotettujen tulosten välisessä suhteessa.
 #12.5.4    Level: 2    Role: D/V
 Varmista, että suorituskyvyn heikkeneminen laukaisee automaattiset hälytykset ja käynnistää mallin uudelleenkoulutus- tai korvaustyönkulut.
 #12.5.5    Level: 3    Role: V
 Varmista, että suorituskyvyn heikkenemisen juurisyyanalyysi yhdistää suorituskyvyn laskut datan muutoksiin, infrastruktuuriongelmiin tai ulkoisiin tekijöihin.

---

### C12.6 DAG-visualisointi ja työnkulun turvallisuus

Suojaa työnkulun visualisointijärjestelmät tietovuodoilta ja manipulointihyökkäyksiltä.

 #12.6.1    Level: 1    Role: D/V
 Varmista, että DAG-visualisointitiedot puhdistetaan poistamaan arkaluonteiset tiedot ennen tallennusta tai siirtoa.
 #12.6.2    Level: 1    Role: D/V
 Varmista, että työnkulun visualisoinnin käyttöoikeudet takaavat, että vain valtuutetut käyttäjät voivat tarkastella agentin päätöspolkuja ja perusteluja.
 #12.6.3    Level: 2    Role: D/V
 Varmista, että DAG-tietojen eheys on suojattu kryptografisilla allekirjoituksilla ja manipuloinnin havaitsemiseen tarkoitetuilla tallennusmekanismeilla.
 #12.6.4    Level: 2    Role: D/V
 Varmista, että työnkulun visualisointijärjestelmät toteuttavat syötteen validoinnin estääkseen injektiohyökkäykset muokatun solmu- tai reuna-aineiston kautta.
 #12.6.5    Level: 3    Role: D/V
 Varmista, että reaaliaikaiset DAG-päivitykset ovat nopeusrajoitettuja ja validoituja estämään palvelunestohyökkäyksiä visualisointijärjestelmiin.

---

### C12.7 Ennakoiva turvallisuuskäyttäytymisen seuranta

Turvallisuusuhkien havaitseminen ja estäminen proaktiivisen agenttien käyttäytymisanalyysin avulla.

 #12.7.1    Level: 1    Role: D/V
 Varmista, että proaktiivisten agenttien käyttäytymismallit ovat tietoturvallisesti validoituja ennen suorittamista riskinarvioinnin integroinnilla.
 #12.7.2    Level: 2    Role: D/V
 Varmista, että autonomisen aloitteen laukaisevat tekijät sisältävät turvallisuuskontekstin arvioinnin ja uhkakentän analyysin.
 #12.7.3    Level: 2    Role: D/V
 Varmista, että ennakoivat käyttäytymismallit analysoidaan mahdollisten turvallisuusvaikutusten ja tahattomien seurauksien varalta.
 #12.7.4    Level: 3    Role: D/V
 Varmista, että turvallisuuden kannalta kriittiset proaktiiviset toimet vaativat selkeät hyväksymisketjut auditointilokien kera.
 #12.7.5    Level: 3    Role: D/V
 Varmista, että käyttäytymisen poikkeavuuksien havaitseminen tunnistaa poikkeamat proaktiivisten agenttien malleissa, jotka voivat viitata järjestelmän vaarantumiseen.

---

### Viitteet

NIST AI Risk Management Framework 1.0 - Manage 4.1 and 4.3
ISO/IEC 42001:2023 — AI Management Systems Requirements - Annex B 6.2.6
EU AI Act — Article 12, 13, 16 and 19 on Logging and Record-keeping

## C13 Ihmisen valvonta, vastuu ja hallinnointi

### Ohjaustavoite

Tämä luku sisältää vaatimukset ihmisen valvonnan ja selkeiden vastuuketjujen ylläpitämiseksi tekoälyjärjestelmissä, varmistaen selitettävyyden, läpinäkyvyyden ja eettisen hallinnoinnin tekoälyn koko elinkaaren ajan.

---

### C13.1 Hätäpysäytys- ja Ylikirjoitusmekanismit

Tarjoa sammutus- tai palautusreitit, kun tekoälyjärjestelmän vaarallista käyttäytymistä havaitaan.

 #13.1.1    Level: 1    Role: D/V
 Varmista, että käsikäyttöinen hätäpysäytystoiminto on olemassa tekoälymallin päätelmän ja tulosteiden välitöntä pysäyttämistä varten.
 #13.1.2    Level: 1    Role: D
 Varmista, että ohitusvalvontatoiminnot ovat käytettävissä vain valtuutetulle henkilöstölle.
 #13.1.3    Level: 3    Role: D/V
 Varmista, että palautusmenettelyt voivat palauttaa aiemmat malliversiot tai toimivat turvallisuustilassa.
 #13.1.4    Level: 3    Role: V
 Varmista, että ohitusmekanismit testataan säännöllisesti.

---

### C13.2 Ihmisen osallisuus päätöksenteon tarkistuspisteissä

Vaatikaa ihmisen hyväksyntä, kun panokset ylittävät ennalta määritellyt riskirajat.

 #13.2.1    Level: 1    Role: D/V
 Varmista, että korkean riskin tekoälypäätökset vaativat nimenomaisen ihmisen hyväksynnän ennen toteutusta.
 #13.2.2    Level: 1    Role: D
 Varmista, että riskirajat on määritelty selkeästi ja ne laukaisevat automaattisesti ihmisen tarkastusprosessit.
 #13.2.3    Level: 2    Role: D
 Varmista, että aikakriittisillä päätöksillä on varajärjestelyt siltä varalta, että ihmisen hyväksyntää ei saada vaaditussa aikarajassa.
 #13.2.4    Level: 3    Role: D/V
 Varmista, että eskalaatioproseduureissa määritellään selkeät valtuustasot eri päätöstyypeille tai riskiluokille, mikäli sovellettavissa.

---

### C13.3 Vastuun ketju ja auditointimahdollisuus

Kirjaa operaattorin toiminnot ja mallin päätökset.

 #13.3.1    Level: 1    Role: D/V
 Varmista, että kaikki tekoälyjärjestelmän päätökset ja ihmisen tekemät toimenpiteet kirjataan ajoitusleimojen, käyttäjätunnusten ja päätöksen perustelujen kanssa.
 #13.3.2    Level: 2    Role: D
 Varmista, että tarkastuslokeihin ei voi tehdä muutoksia ja että ne sisältävät eheystarkistusmekanismeja.

---

### C13.4 Selitettävät tekoälytekniikat

Pintapuolen ominaisuuksien tärkeys, vastin-tapaukset ja paikalliset selitykset.

 #13.4.1    Level: 1    Role: D/V
 Varmista, että tekoälyjärjestelmät tarjoavat päätöksistään perustavanlaatuiset selitykset ihmisen luettavassa muodossa.
 #13.4.2    Level: 2    Role: V
 Varmista, että selityksen laatu on validoitu ihmisten tekemillä arviointitutkimuksilla ja mittareilla.
 #13.4.3    Level: 3    Role: D/V
 Varmista, että kriittisille päätöksille on saatavilla ominaisuuksien tärkeyspisteet tai attribuutiomenetelmät (kuten SHAP, LIME jne.).
 #13.4.4    Level: 3    Role: V
 Varmista, että kontrafaktuaaliset selitykset osoittavat, miten syötteitä voitaisiin muuttaa tulosten muuttamiseksi, jos se on sovellettavissa käyttötapaukseen ja toimialaan.

---

### C13.5 Mallikortit ja Käyttöilmoitukset

Pidä yllä mallikortteja suunnitellusta käytöstä, suorituskykymittareista ja eettisistä näkökohdista.

 #13.5.1    Level: 1    Role: D
 Varmista, että mallikortit dokumentoivat suunnitellut käyttötapaukset, rajoitukset ja tunnetut epäonnistumistilat.
 #13.5.2    Level: 1    Role: D/V
 Varmista, että suorituskykymittarit eri soveltuvien käyttötapausten osalta on julkistettu.
 #13.5.3    Level: 2    Role: D
 Varmista, että eettiset näkökohdat, harha-arviot, oikeudenmukaisuuden arvioinnit, koulutusdatan ominaisuudet ja tunnetut koulutusdatan rajoitukset on dokumentoitu ja päivitetty säännöllisesti.
 #13.5.4    Level: 2    Role: D/V
 Varmista, että mallikortit ovat versionhallinnassa ja niitä ylläpidetään mallin elinkaaren ajan muutosseurannan avulla.

---

### C13.6 Epävarmuuden kvantifiointi

Levitä luottamuspisteitä tai entropiamittauksia vastauksissa.

 #13.6.1    Level: 1    Role: D
 Varmista, että tekoälyjärjestelmät antavat tulostensa yhteydessä varmuuspisteet tai epävarmuusmittarit.
 #13.6.2    Level: 2    Role: D/V
 Varmista, että epävarmuuskynnykset laukaisevat lisäarvioinnin ihmisen toimesta tai vaihtoehtoiset päätöksentekopolut.
 #13.6.3    Level: 2    Role: V
 Varmista, että epävarmuuden määrityksen menetelmät on kalibroitu ja validoitu todellisiin todellisuustietoihin perustuen.
 #13.6.4    Level: 3    Role: D/V
 Varmista, että epävarmuuden kulkeutuminen säilyy monivaiheisissa tekoälytyönkuluissa.

---

### C13.7 Käyttäjille suunnatut läpinäkyvyysraportit

Tarjoa säännöllisiä raportteja tapahtumista, mallin muutoksista ja datan käytöstä.

 #13.7.1    Level: 1    Role: D/V
 Varmista, että tietojen käyttöä koskevat säännöt ja käyttäjien suostumuksen hallintakäytännöt on selkeästi viestitty sidosryhmille.
 #13.7.2    Level: 2    Role: D/V
 Varmista, että tekoälyn vaikutusten arvioinnit tehdään ja tulokset sisällytetään raportointiin.
 #13.7.3    Level: 2    Role: D/V
 Varmista, että säännöllisesti julkaistavat läpinäkyvyysraportit paljastavat tekoälytapahtumat ja toiminnalliset mittarit kohtuullisessa yksityiskohtaisuudessa.

#### Viitteet

EU Artificial Intelligence Act — Regulation (EU) 2024/1689 (Official Journal, 12 July 2024)
ISO/IEC 23894:2023 — Artificial Intelligence — Guidance on Risk Management
ISO/IEC 42001:2023 — AI Management Systems Requirements
NIST AI Risk Management Framework 1.0
NIST SP 800-53 Revision 5 — Security and Privacy Controls
A Unified Approach to Interpreting Model Predictions (SHAP, ICML 2017)
Model Cards for Model Reporting (Mitchell et al., 2018)
Dropout as a Bayesian Approximation: Representing Model Uncertainty in Deep Learning (Gal & Ghahramani, 2016)
ISO/IEC 24029-2:2023 — Robustness of Neural Networks — Methodology for Formal Methods
IEEE 7001-2021 — Transparency of Autonomous Systems
GDPR — Article 5 "Transparency Principle" (Regulation (EU) 2016/679)
Human Oversight under Article 14 of the EU AI Act (Fink, 2025)

## Liite A: Sanasto

Tämä kattava sanasto tarjoaa määritelmiä keskeisille tekoälyyn (AI), koneoppimiseen (ML) ja tietoturvaan liittyville termeille, joita käytetään AISVS:ssä selkeyden ja yhteisen ymmärryksen varmistamiseksi.
​
Vihamielinen esimerkki: Syöte, joka on tarkoituksellisesti laadittu saattamaan tekoälymalli tekemään virheen, usein lisäämällä hienovaraisia häiriöitä, joita ihmiset eivät havaitse.
​
Hyökkäyksenkestävyys – Hyökkäyksenkestävyys tekoälyssä tarkoittaa mallin kykyä säilyttää suorituskykynsä ja vastustaa tarkoituksellisesti suunniteltujen, haitallisten syötteiden aiheuttamia virheitä tai manipulointia.
​
Agentti – AI-agentit ovat ohjelmistojärjestelmiä, jotka käyttävät tekoälyä tavoitteen saavuttamiseen ja tehtävien suorittamiseen käyttäjien puolesta. Ne osoittavat päättelykykyä, suunnittelua ja muistia sekä omaavat tietyn tason autonomian päätöksenteossa, oppimisessa ja sopeutumisessa.
​
Agenttinen tekoäly: Tekoälyjärjestelmät, jotka voivat toimia jossain määrin itsenäisesti saavuttaakseen tavoitteita, usein tekemällä päätöksiä ja toimia ilman suoraa ihmisen väliintuloa.
​
Attribuuttipohjainen pääsynvalvonta (ABAC): Pääsynvalvonnan malli, jossa valtuutuspäätökset perustuvat käyttäjän, resurssin, toiminnon ja ympäristön attribuutteihin, jotka arvioidaan kyselyhetkellä.
​
Takaportti-hyökkäys: Eräänlainen datan myrkytyshyökkäys, jossa malli opetetaan reagoimaan tietyllä tavalla tiettyihin laukaisimiin samalla kun se käyttäytyy normaalisti muuten.
​
Vinouma: Järjestelmälliset virheet tekoälymallin tuloksissa, jotka voivat johtaa epäoikeudenmukaisiin tai syrjiviin lopputuloksiin tietyissä ryhmissä tai tilanteissa.
​
Vinouman hyödyntäminen: Hyökkäystekniikka, joka hyödyntää tekoälymallien tunnettuja vinoumia manipuloidakseen tuloksia tai lopputulemia.
​
Cedar: Amazonin politiikkakieli ja -moottori hienojakoisten käyttöoikeuksien määrittelyyn, jota käytetään AI-järjestelmien ABAC:n toteuttamiseen.
​
Ajatusketju: Tekniikka, joka parantaa päättelyä kielimalleissa tuottamalla välivaiheen päättelyaskeleita ennen lopullisen vastauksen antamista.
​
Virtakatkaisimet: Mekanismeja, jotka keskeyttävät tekoälyjärjestelmän toiminnan automaattisesti, kun tiettyjä riskirajoja ylitetään.
​
Tietovuoto: Salaisten tietojen tahaton paljastuminen tekoälymallien tulosten tai käyttäytymisen kautta.
​
Datan myrkytys: Harjoitusdatan tahallinen turmeltuminen mallin eheyden vaarantamiseksi, usein takaovien asentamiseksi tai suorituskyvyn huonontamiseksi.
​
Differentiaalinen yksityisyys – Differentiaalinen yksityisyys on matemaattisesti tarkka kehys tilastollisen tiedon julkaisemiseksi tietoaineistoista samalla kun suojataan yksilöllisten tietojen yksityisyys. Sen avulla tietoa hallinnoiva taho voi jakaa ryhmän aggregaattimalleja rajoittaen kuitenkin yksittäisiä henkilöitä koskevien tietojen vuotamista.
​
Upotukset: Tiheät vektoriedustukset datasta (teksti, kuvat jne.), jotka vangitsevat semanttisen merkityksen korkean ulottuvuuden tilassa.
​
Selitettävyys – Selitettävyys tekoälyssä tarkoittaa kykyä tarjota ihmisen ymmärtämiä syitä päätöksilleen ja ennusteilleen, tarjoten samalla näkemyksiä sen sisäisestä toiminnasta.
​
Selitettävä tekoäly (XAI): tekoälyjärjestelmät, jotka on suunniteltu tarjoamaan ihmisen ymmärrettäviä selityksiä päätöksilleen ja käyttäytymiselleen erilaisten tekniikoiden ja viitekehysten avulla.
​
Federated Learning: Koneoppimisen menetelmä, jossa malleja koulutetaan useilla hajautetuilla laitteilla, jotka sisältävät paikallisia datanäytteitä, ilman että dataa vaihdetaan laitteiden välillä.
​
Turvatoimet: Rajoitukset, jotka on toteutettu estämään tekoälyjärjestelmiä tuottamasta haitallisia, vinoutuneita tai muita ei-toivottuja tuloksia.
​
Halucinaatio – AI-halucinaatiolla tarkoitetaan ilmiötä, jossa tekoälymalli tuottaa virheellistä tai harhaanjohtavaa tietoa, joka ei perustu sen koulutusdataan tai tosiasialliseen todellisuuteen.
​
Ihmisen osallisuus silmukassa (Human-in-the-Loop, HITL): Järjestelmät, jotka on suunniteltu edellyttämään ihmisen valvontaa, vahvistusta tai väliintuloa keskeisissä päätöspisteissä.
​
Infrastruktuuri koodina (IaC): Infrastruktuurin hallinta ja käyttöönotto koodin avulla manuaalisten prosessien sijaan, mahdollistaen turvallisuustarkastukset ja johdonmukaiset käyttöönotot.
​
Jailbreak: Menetelmät, joilla kiertää turvallisuusrajoituksia tekoälyjärjestelmissä, erityisesti suurissa kielimalleissa, tuottamaan kiellettyä sisältöä.
​
Vähimmän oikeuden periaate: Tietoturvaperiaate, jossa käyttäjille ja prosesseille myönnetään vain välttämättömimmät oikeudet.
​
LIME (Local Interpretable Model-agnostic Explanations): Menetelmä koneoppimisen luokittelijan ennusteiden selittämiseen paikallisesti tulkittavalla mallilla.
​
Jäsenyyspäätelmähyökkäys: Hyökkäys, jonka tavoitteena on selvittää, käytettiinkö tiettyä datapistettä koneoppimismallin kouluttamiseen.
​
MITRE ATLAS: Vastustajan uhkakenttä tekoälyjärjestelmille; tietopohja vastustajan taktiikoista ja tekniikoista tekoälyjärjestelmiä vastaan.
​
Mallikortti – Mallikortti on asiakirja, joka tarjoaa standardoitua tietoa tekoälymallin suorituskyvystä, rajoituksista, suunnitelluista käyttötarkoituksista ja eettisistä näkökohdista edistääkseen läpinäkyvyyttä ja vastuullista tekoälyn kehitystä.
​
Mallin poiminta: Hyökkäys, jossa hyökkääjä tekee toistuvia kyselyjä kohdemallille luodakseen toiminnallisesti samanlaisen kopion ilman lupaa.
​
Mallin invertointi: Hyökkäys, joka pyrkii rekonstruoimaan harjoitteludataa analysoimalla mallin tulosteita.
​
Mallin elinkaaren hallinta – AI-mallin elinkaaren hallinta on prosessi, jossa valvotaan kaikki AI-mallin olemassaolon vaiheet, mukaan lukien sen suunnittelu, kehitys, käyttöönotto, seuranta, ylläpito ja lopullinen käytöstä poistaminen, jotta malli pysyy tehokkaana ja tavoitteiden mukaisena.
​
Mallin myrkyttäminen: Haavoittuvuuksien tai takaovien lisääminen suoraan malliin koulutusprosessin aikana.
​
Mallin varastaminen/varkaus: Omistusoikeuteen perustuvan mallin kopioiminen tai likimääräinen jäljentäminen toistuvien kyselyiden avulla.
​
Moniagenttijärjestelmä: Järjestelmä, joka koostuu useista vuorovaikutteisista tekoälyagentsseista, joilla voi olla erilaisia kykyjä ja tavoitteita.
​
OPA (Open Policy Agent): Avoimen lähdekoodin politiikkamoottori, joka mahdollistaa yhtenäisen politiikan täytäntöönpanon koko pinossa.
​
Yksityisyyttä säilyttävä koneoppiminen (PPML): Tekniikat ja menetelmät ML-mallien kouluttamiseen ja käyttöönottoon siten, että koulutusdatan yksityisyys säilyy.
​
Kehoteinjektio: Hyökkäys, jossa haitallisia ohjeita upotetaan syötteisiin mallin suunnitellun toiminnan ohittamiseksi.
​
RAG (Retrieval-Augmented Generation): Tekniikka, joka parantaa suuria kielimalleja hakemalla oleellista tietoa ulkoisista tietolähteistä ennen vastauksen luomista.
​
Red-Teaming: Käytäntö, jossa testataan tekoälyjärjestelmiä aktiivisesti simuloimalla hyökkäyksiä vihamielisistä tahoista haavoittuvuuksien tunnistamiseksi.
​
SBOM (Ohjelmistokomponenttien luettelo): Virallinen tietue, joka sisältää yksityiskohdat ja toimitusketjusuhteet eri komponenteista, joita käytetään ohjelmiston tai tekoälymallien rakentamiseen.
​
SHAP (SHapley Additive exPlanations): Peliteoreettinen lähestymistapa, jolla selitetään minkä tahansa koneoppimismallin tulosta laskemalla kunkin piirteen kontribuutio ennusteeseen.
​
Toimitusketjun hyökkäys: järjestelmän vaarantaminen kohdistamalla heikommin suojattuihin osiin sen toimitusketjussa, kuten kolmannen osapuolen kirjastoihin, tietoaineistoihin tai esikoulutettuihin malleihin.
​
Siirto-oppiminen: Tekniikka, jossa yhdelle tehtävälle kehitetty malli käytetään uudelleen lähtökohtana mallille toisessa tehtävässä.
​
Vektoripohjainen tietokanta: Erikoistunut tietokanta, joka on suunniteltu tallentamaan korkeulotteisia vektoreita (upotuksia) ja suorittamaan tehokkaita samankaltaisuushakuja.
​
Haavoittuvuusskannaus: Automaattiset työkalut, jotka tunnistavat tunnetut tietoturvahaavoittuvuudet ohjelmistokomponenteissa, mukaan lukien tekoälykehykset ja riippuvuudet.
​
Vesileimauksen tekniikat: Tapoja upottaa aistimattomia merkkejä tekoälyn tuottamaan sisältöön sen alkuperän seuraamiseksi tai tekoälyn generoiman sisällön tunnistamiseksi.
​
Zero-Day-haavoittuvuus: Aiemmin tuntematon haavoittuvuus, jota hyökkääjät voivat käyttää hyväkseen ennen kuin kehittäjät luovat ja käyttöönotavat korjauksen.

## Liite B: Viitteet

### TODO

## Liite C: Tekoälyn turvallisuuden hallinto ja dokumentaatio

### Tavoite

Tämä liite esittää perustavanlaatuiset vaatimukset organisaatiorakenteiden, politiikkojen ja prosessien perustamiseksi AI:n turvallisuuden hallitsemiseksi koko järjestelmän elinkaaren ajan.

---

### AC.1 Tekoälyn riskienhallintakehyksen käyttöönotto

Tarjoa virallinen kehys tekoälyyn liittyvien riskien tunnistamiseksi, arvioimiseksi ja lieventämiseksi koko järjestelmän elinkaaren ajan.

 #AC.1.1    Level: 1    Role: D/V
 Varmista, että tekoälyyn liittyvä riskinarviointimenetelmä on dokumentoitu ja otettu käyttöön.
 #AC.1.2    Level: 2    Role: D
 Varmista, että riskinarvioinnit tehdään tekoälyn elinkaaren keskeisissä vaiheissa ja merkittävien muutosten yhteydessä.
 #AC.1.3    Level: 3    Role: D/V
 Varmista, että riskienhallintakehys on linjassa vakiintuneiden standardien kanssa (esim. NIST AI RMF).

---

### AC.2 Tekoälyn turvallisuuskäytännöt ja -menettelyt

Määrittele ja valvo organisaation standardeja turvalliselle tekoälyn kehitykselle, käyttöönotolle ja toiminnalle.

 #AC.2.1    Level: 1    Role: D/V
 Varmista, että dokumentoidut tekoälyn turvallisuuspolitiikat ovat olemassa.
 #AC.2.2    Level: 2    Role: D
 Varmista, että käytännöt tarkistetaan ja päivitetään vähintään vuosittain sekä merkittävien uhkakentän muutosten jälkeen.
 #AC.2.3    Level: 3    Role: D/V
 Varmista, että politiikat kattavat kaikki AISVS-luokat ja sovellettavat sääntelyvaatimukset.

---

### AC.3 Roolit ja vastuut tekoälyn turvallisuudessa

Määrittele selkeä vastuu AI-tietoturvasta koko organisaatiossa.

 #AC.3.1    Level: 1    Role: D/V
 Varmista, että tekoälyn turvallisuusroolit ja vastuut on dokumentoitu.
 #AC.3.2    Level: 2    Role: D
 Varmista, että vastuuhenkilöillä on asianmukainen turvallisuusosaaminen.
 #AC.3.3    Level: 3    Role: D/V
 Varmista, että korkean riskin tekoälyjärjestelmille on perustettu tekoälyn etiikkakomitea tai hallintoneuvosto.

---

### AC.4 Eettisen tekoälyn ohjeistusten täytäntöönpano

Varmista, että tekoälyjärjestelmät toimivat vakiintuneiden eettisten periaatteiden mukaisesti.

 #AC.4.1    Level: 1    Role: D/V
 Varmista, että tekoälyn kehittämistä ja käyttöönottoa koskevat eettiset ohjeistukset ovat olemassa.
 #AC.4.2    Level: 2    Role: D
 Varmista, että mekanismit eettisten rikkomusten havaitsemiseksi ja raportoimiseksi ovat käytössä.
 #AC.4.3    Level: 3    Role: D/V
 Varmista, että käyttöön otettujen tekoälyjärjestelmien säännölliset eettiset tarkastukset tehdään.

---

### AC.5 tekoälyn sääntelyn noudattamisen valvonta

Pysy tietoisena ja noudata kehittyviä tekoälyä koskevia säädöksiä.

 #AC.5.1    Level: 1    Role: D/V
 Varmista, että prosessit olemassa soveltuvien tekoälysäädösten tunnistamiseksi.
 #AC.5.2    Level: 2    Role: D
 Varmista, että kaikkien säädösten noudattaminen arvioidaan.
 #AC.5.3    Level: 3    Role: D/V
 Varmista, että sääntelymuutokset laukaisevat AI-järjestelmien oikea-aikaiset tarkastelut ja päivitykset.

#### Viitteet

NIST AI Risk Management Framework 1.0
ISO/IEC 42001:2023 — AI Management Systems Requirements
ISO/IEC 23894:2023 — Artificial Intelligence — Guidance on Risk Management
EU Artificial Intelligence Act — Regulation (EU) 2024/1689
ISO/IEC 24029‑2:2023 — Robustness of Neural Networks — Methodology for Formal Methods

## Liite D: AI-avusteinen turvallisen koodauksen hallinta ja varmennus

### Tavoite

Tämä luku määrittelee perustason organisatoriset hallintakeinot AI-avusteisten ohjelmointityökalujen turvalliseen ja tehokkaaseen käyttöön ohjelmistokehityksen aikana, varmistaen turvallisuuden ja jäljitettävyyden koko ohjelmistokehityksen elinkaaren (SDLC) ajan.

---

### AD.1 AI-avusteinen turvallisen koodauksen työnkulku

Integroi tekoälytyökalut organisaation turvallisen ohjelmistokehityksen elinkaaren (SSDLC) prosessiin heikentämättä olemassa olevia turvallisuusportteja.

 #AD.1.1    Level: 1    Role: D/V
 Varmista, että dokumentoitu työnkulku kuvaa, milloin ja miten tekoälytyökaluja voidaan käyttää koodin generointiin, refaktorointiin tai tarkistamiseen.
 #AD.1.2    Level: 2    Role: D
 Varmista, että työnkulku vastaa jokaista SSDLC-vaihetta (suunnittelu, toteutus, koodikatselmointi, testaus, käyttöönotto).
 #AD.1.3    Level: 3    Role: D/V
 Varmista, että mittareita (esim. haavoittuvuustiheys, keskimääräinen havaitsemisaika) kerätään tekoälyn tuottamasta koodista ja verrataan ihmisen ainoastaan tuottamiin lähtötasoihin.

---

### AD.2 AI-työkalun kelpoisuus ja uhkamallinnus

Varmista, että tekoälykoodausvälineet arvioidaan turvallisuusominaisuuksien, riskien ja toimitusketjun vaikutusten osalta ennen käyttöönottoa.

 #AD.2.1    Level: 1    Role: D/V
 Varmista, että jokaisen tekoälytyökalun uhkamalli tunnistaa väärinkäytön, mallin käänteisen hyödyntämisen, tietovuodot ja riippuvuusketjun riskit.
 #AD.2.2    Level: 2    Role: D
 Varmista, että työkalujen arvioinnit sisältävät paikallisten komponenttien staattisen/dynaamisen analyysin sekä SaaS-päätepisteiden (TLS, tunnistautuminen/valtuutus, lokitus) arvioinnin.
 #AD.2.3    Level: 3    Role: D/V
 Varmista, että arvioinnit noudattavat tunnustettua viitekehystä ja suoritetaan uudelleen merkittävien versiopäivitysten jälkeen.

---

### AD.3 Turvallinen kehotteiden ja kontekstinhallinta

Estä salaisuuksien, omistusoikeudellisen koodin ja henkilökohtaisten tietojen vuotaminen AI-mallien kehotteita tai konteksteja rakennettaessa.

 #AD.3.1    Level: 1    Role: D/V
 Varmista, että kirjallinen ohjeistus kieltää salaisuuksien, tunnistetietojen tai luokitellun datan lähettämisen kehotteissa.
 #AD.3.2    Level: 2    Role: D
 Varmista, että tekniset ohjausmenetelmät (asiakaspuolen peittäminen, hyväksytyt kontekstisuodattimet) poistavat automaattisesti arkaluonteiset tiedot.
 #AD.3.3    Level: 3    Role: D/V
 Varmista, että kehote- ja vastaustiedot tokenisoidaan, salataan siirron aikana ja levossa, ja että säilytysaikojen tiedonluokituspolitiikkaa noudatetaan.

---

### AD.4 AI-Generoidun Koodin Vahvistaminen

Havaitse ja korjaa tekoälyn tuottamien tulosten aiheuttamat haavoittuvuudet ennen kuin koodi yhdistetään tai julkaistaan.

 #AD.4.1    Level: 1    Role: D/V
 Varmista, että tekoälyn generoima koodi käy aina läpi ihmisen tekemän koodikatselmoinnin.
 #AD.4.2    Level: 2    Role: D
 Varmista, että automatisoidut skannerit (SAST/IAST/DAST) suoritetaan kaikissa AI-generoitua koodia sisältävissä vetopyynnöissä ja estä yhdistämiset kriittisissä löydöksissä.
 #AD.4.3    Level: 3    Role: D/V
 Varmista, että differentiaalinen fuzz-testaus tai ominaisuuspohjaiset testit todistavat turvallisuuskriittiset käyttäytymismallit (esim. syötteen validointi, valtuutuslogiikka).

---

### AD.5 Koodiehdotusten selitettävyys ja jäljitettävyys

Tarjoa tarkastajille ja kehittäjille ymmärrystä siitä, miksi ehdotus tehtiin ja miten se kehittyi.

 #AD.5.1    Level: 1    Role: D/V
 Varmista, että kehotteet/vastausparit kirjataan sitoutumisen tunnisteilla.
 #AD.5.2    Level: 2    Role: D
 Varmista, että kehittäjät voivat näyttää malliviitteitä (koulutusnäytteitä, dokumentaatiota) ehdotuksen tukemiseksi.
 #AD.5.3    Level: 3    Role: D/V
 Varmista, että selitettävyysraportit tallennetaan suunnitteluaineistojen kanssa ja viitataan turvallisuuskatselmuksissa, täyttäen ISO/IEC 42001 -jäljityksen periaatteet.

---

### AD.6 Jatkuva palaute ja mallin hienosäätö

Paranna mallin turvallisuussuorituskykyä ajan myötä samalla kun estät negatiivisen siirtymän.

 #AD.6.1    Level: 1    Role: D/V
 Varmista, että kehittäjät voivat merkitä epävarmat tai ei-yhteensopivat ehdotukset ja että merkinnät seurataan.
 #AD.6.2    Level: 2    Role: D
 Varmista, että koottu palaute ohjaa säännöllistä hienosäätöä tai hakua tehostettua generointia varmennetuilla tietoturvallisen koodauksen aineistoilla (esim. OWASP Cheat Sheets).
 #AD.6.3    Level: 3    Role: D/V
 Varmista, että suljetun silmukan arviointikehys suorittaa regressiotestit jokaisen hienosäädön jälkeen; turvallisuusmittareiden on täytettävä tai ylitettävä aiemmat vertailuarvot ennen käyttöönottoa.

---

#### Viitteet

NIST AI Risk Management Framework 1.0
ISO/IEC 42001:2023 — AI Management Systems Requirements
OWASP Secure Coding Practices — Quick Reference Guide

## Liite E: Esimerkkejä työkaluista ja kehyksistä

### Tavoite

Tämä luku tarjoaa esimerkkejä työkaluista ja kehyksistä, jotka voivat tukea tietyn AISVS-vaatimuksen toteuttamista tai täyttämistä. Näitä ei tule pitää AISVS-tiimin tai OWASP GenAI Security -projektin suosituksina tai suosituksina.

---

### AE.1 Koulutusdatan hallinta ja vinoumien hallinta

Työkalut, joita käytetään data-analytiikkaan, hallintaan ja puolueellisuuden hallintaan.

 #AE.1.1    Section: 1.1
 Tietovaraston hallintatyökalut: Tietovaraston hallintaan tarkoitetut työkalut, kuten...
 #AE.1.2    Section: 1.2
 Salaus siirron aikana Käytä TLS:ää HTTPS-pohjaisissa sovelluksissa, hyödyntäen työkaluja kuten openSSL ja pythonin`ssl`kirjasto.

---

### AE.2 Käyttäjän syötteen validointi

Työkalut käyttäjätietojen käsittelyyn ja validointiin.

 #AE.2.1    Section: 2.1
 Keinot suojautua kehotteiden injektoinnilta: Käytä suojaustyökaluja, kuten NVIDIA:n NeMo tai Guardrails AI.

---

