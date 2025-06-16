# C5 juurdepääsukontroll ja identiteet tehisintellekti komponentide ja kasutajate jaoks

## Kontrolli Eesmärk

AI-süsteemide tõhus juurdepääsukontroll nõuab tugevat identiteedihaldust, kontekstitundlikku autoriseerimist ja jooksuaegset täitmist, järgides nullusalduspõhimõtteid. Need kontrollid tagavad, et inimesed, teenused ja autonoomsed agendid suhtlevad ainult selgesõnaliselt lubatud ulatusega mudelite, andmete ja arvutusressurssidega, võimaldades pidevat kontrolli ja auditeerimist.

---

## C5.1 Identiteedi haldus ja autentimine

Loo kõigi üksuste jaoks krüptograafiliselt toetatud identiteedid mitmefaktorilise autentimisega privileegitud toimingute jaoks.

|   #   | Description                                                                                                                                                                                                                                             | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 5.1.1 | Veenduge, et kõik inimesed kasutajad ja teenuse põhimõtted autentiksid tsentraliseeritud ettevõtte identiteedipakkuja (IdP) kaudu, kasutades OIDC/SAML protokolle unikaalsete identiteedi ja tokeni sidumistega (ilma jagatud kontode või volitusteta). |   1   | D/V  |
| 5.1.2 | Kontrollige, et kõrge riskiga toimingud (mudeli juurutamine, kaalude eksport, treeningandmete juurdepääs, tootmiskonfiguratsiooni muutmine) nõuaksid multifaktorilist autentimist või autentimise täiendamist koos sessiooni uuesti valideerimisega.    |   1   | D/V  |
| 5.1.3 | Kontrollige, et uued juhid läbivad identiteedi tõestamise, mis vastab NIST 800-63-3 IAL-2 või selle ekvivalendile enne tootmissüsteemi juurdepääsu saamist.                                                                                             |   2   |  D   |
| 5.1.4 | Kontrollige, et juurdepääsu ülevaated toimuvad kvartali kaupa, kasutades automaatset tegevusetute kontode tuvastamist, mandaadi vahetamise nõuet ja deprovisioneerimise töövooge.                                                                       |   2   |  V   |
| 5.1.5 | Kinnitage, et liitunud tehisintellekti agendid autentivad allkirjastatud JWT väidete kaudu, mille maksimaalne kehtivusaeg on 24 tundi ning mis sisaldavad krüptograafilist päritolu tõendit.                                                            |   3   | D/V  |

---

## C5.2 Ressursside autoriseerimine ja minimaalne õiguste põhimõte

Rakenda kõigi tehisintellekti ressursside jaoks peenhäälestatud juurdepääsukontrollid, kasutades selgeid õiguste mudeleid ja auditeerimislugusid.

|   #   | Description                                                                                                                                                                                                                                              | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 5.2.1 | Veenduge, et iga tehisintellekti ressurss (andmekogud, mudelid, lõpp-punktid, vektorkogud, manustamiste indeksid, arvutusinstantsid) rakendaks rollipõhist juurdepääsu kontrolli koos selgete lubatud nimekirjade ja vaikimisi keeldamise poliitikatega. |   1   | D/V  |
| 5.2.2 | Kinnitage, et teenusekontode puhul rakendatakse vaikimisi vähima privileegi põhimõtteid, alustades ainult lugemisõigustega ning kirjutamisõiguse saamiseks nõutakse dokumenteeritud äripõhjendust.                                                       |   1   | D/V  |
| 5.2.3 | Kontrollige, et kõik juurdepääsukontrolli muudatused oleksid seotud kinnitatud muudatusettepanekutega ning logitud muutumatult koos ajatemplit, tegija identiteetide, ressursi identifikaatorite ja loa erinevustega.                                    |   1   |  V   |
| 5.2.4 | Kinnitage, et andmete klassifitseerimise sildid (PII, PHI, ekspordikontrolli all olev, patenteeritud) kanduvad automaatselt üle tuletatud ressurssidele (embeddings, prompti vahemälud, mudelitulemused) ja poliitika rakendamine on järjepidev.         |   2   |  D   |
| 5.2.5 | Kontrollige, et volitamata juurdepääsu katsed ja õiguste tõstmise sündmused käivitaksid SIEM-süsteemides reaalajas hoiatused koos kontekstuaalse metainfoga viie minuti jooksul.                                                                         |   2   | D/V  |

---

## C5.3 Dünaamiline poliitika hindamine

Kasutage kontekstitundlike autoriseerimisotsuste tegemiseks omadusbaasilise juurdepääsu kontrolli (ABAC) mootorite juurutamist koos auditeerimisvõimalustega.

|   #   | Description                                                                                                                                                                                                            | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 5.3.1 | Kinnitage, et autoriseerimisotsused on väljastatud spetsiaalsele poliitikamootorile (OPA, Cedar või samaväärne), mis on ligipääsetav autentitud API-de kaudu ning millel on krüptograafilise terviklikkuse kaitse.     |   1   | D/V  |
| 5.3.2 | Kinnitage, et poliitikad hindavad dünaamilisi atribuute käituse ajal, sealhulgas kasutaja ligipääsutaset, ressursi tundlikkuse klassifikatsiooni, päringu konteksti, üürniku isolatsiooni ja ajutisi piiranguid.       |   1   | D/V  |
| 5.3.3 | Kinnitage, et poliitika määratlused on versioonihalduses, vertikaalselt läbi vaadatud ja valideeritud automatiseeritud testimise kaudu CI/CD torujuhtmetes enne tootmisse juurutamist.                                 |   2   |  D   |
| 5.3.4 | Kinnitage, et poliitika hindamise tulemused sisaldavad struktureeritud otsuse põhjendusi ning edastatakse SIEM-süsteemidele korrelatsioonianalüüsi ja vastavusaruandluse jaoks.                                        |   2   |  V   |
| 5.3.5 | Kontrollige, et poliitika vahemälu aeg-toimimise (TTL) väärtused ei ületaks kõrge tundlikkusega ressursside puhul 5 minutit ja tavaliste ressursside puhul, millel on vahemälu kehtetuks muutmise võimalused, 1 tundi. |   3   | D/V  |

---

## C5.4 Päringuajal turvapoliitika täitmine

Rakendage andmebaasi tasandi turvakontrollid kohustusliku filtreerimise ja rea tasandi turvapoliitikatega.

|   #   | Description                                                                                                                                                                                                                                 | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 5.4.1 | Kontrollige, et kõik vektordatabase ja SQL-päringud sisaldaksid kohustuslikke turvafiltreid (liikuva ID, tundlikkuse sildid, kasutaja ulatus), mida rakendatakse andmebaasi mootoritasemel, mitte rakenduse koodi tasemel.                  |   1   | D/V  |
| 5.4.2 | Kontrollige, et kõikides vektordatabases, otsingukihtides ja treeningandmestikes oleks lubatud rea-tasandi turvapoliitikad (RLS) ning välja-tasandi maskimine koos poliitika pärandumisega.                                                 |   1   | D/V  |
| 5.4.3 | Kinnitage, et ebaõnnestunud autoriseerimise hinnangud takistavad "segaduses oleva mandaadi rünnakuid", katkestades päringud viivitamatult ja tagastades selged autoriseerimisvea koodid, selle asemel et tagastada tühjad tulemuste hulgad. |   2   |  D   |
| 5.4.4 | Kinnitage, et poliitika hindamise latentsust jälgitakse pidevalt automaatsete hoiatustega ajalõpu tingimuste korral, mis võiksid võimaldada autoriseerimise mööda hiilimist.                                                                |   2   |  V   |
| 5.4.5 | Kontrollige, et päringu taaskäivitamise mehhanismid hindaksid autoriseerimispoliitikaid uuesti, võttes arvesse dünaamilisi õiguste muudatusi aktiivsete kasutajaseansside jooksul.                                                          |   3   | D/V  |

---

## C5.5 Väljundi filtreerimine ja andmekao ennetamine

Rakenda järelprotsessimise kontrollid, et vältida volitamata andmete avalikustamist tehisintellekti loodud sisus.

|   #   | Description                                                                                                                                                                                                        | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 5.5.1 | Kinnitage, et järeldusjärgsed filtreerimismehhanismid kontrollivad ja peidavad volitamata isikuandmeid (PII), salastatud teavet ning patenteeritud andmeid enne sisu edastamist nõudjatele.                        |   1   | D/V  |
| 5.5.2 | Veenduge, et mudeli väljundites olevad viited, viited ja allikaviited oleksid kontrollitud vastavalt kutsuja õigustele ning eemaldatud, kui tuvastatakse volitamata juurdepääs.                                    |   1   | D/V  |
| 5.5.3 | Kontrollige, et väljundvormingupiirangud (puhastatud PDF-id, metaandmetest puhastatud pildid, kinnitatud failitüübid) oleks rakendatud vastavalt kasutaja õigustasanditele ja andmeklassifikatsioonidele.          |   2   |  D   |
| 5.5.4 | Kinnitage, et redigeerimisalgoritmid on deterministlikud, versioonikontrolli all ning säilitavad auditi logisid, et toetada vastavuse uurimisi ja kohtuekspertiisi analüüsi.                                       |   2   |  V   |
| 5.5.5 | Kontrollige, et kõrge riskiga redigeerimise sündmused genereeriksid adaptiivseid logisid, mis sisaldavad krüptograafilisi räsi algsest sisust kohtuekspertiisi tagasiside saamiseks ilma andmete avalikustamiseta. |   3   |  V   |

---

## C5.6 Mitmeüürilisuse isolatsioon

Tagada krüptograafiline ja loogiline isolatsioon rentnike vahel jagatud tehisintellekti infrastruktuuris.

|   #   | Description                                                                                                                                                                                                       | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 5.6.1 | Kinnitage, et mäluruumid, manustamispoodid, vahemälukirjed ja ajutised failid on juurdepääsuvahemiku lõikes eraldatud ning need kustutatakse turvaliselt juurdepääsuvahemiku kustutamisel või seansi lõpetamisel. |   1   | D/V  |
| 5.6.2 | Kontrollige, et iga API-päring sisaldab autentitud üürniku identifikaatorit, mis on krüptograafiliselt valideeritud vastavalt sessiooni kontekstile ja kasutaja õigustele.                                        |   1   | D/V  |
| 5.6.3 | Kinnitage, et võrgupoliitikad rakendavad vaikimisi keelamise reegleid tenantidevaheliseks suhtluseks teenusevõrkudes ja konteinerite orkestreerimise platvormidel.                                                |   2   |  D   |
| 5.6.4 | Kontrollige, et krüpteerimisvõtmed oleksid üheselt määratletud iga rentniku kohta koos kliendihaldusvõtme (CMK) toe ja rentnike andmepoodide vahelise krüptograafilise isolatsiooniga.                            |   3   |  D   |

---

## C5.7 Autonoomse agente volitused

Kontrolli AI-agentide ja autonoomsete süsteemide õigusi läbi piiritletud võimekusmärkide ja pideva autoriseerimise.

|   #   | Description                                                                                                                                                                                                                                 | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 5.7.1 | Kontrollige, et autonoomsetele agentidele antakse ulatuslikud volitustunnistused, mis selgelt loetlevad lubatud tegevused, kättesaadavad ressursid, ajapiirangud ja tegevusalased piirangud.                                                |   1   | D/V  |
| 5.7.2 | Kinnitage, et kõrge riskiga funktsioonid (failisüsteemi juurdepääs, koodi täitmine, väliste API-kõnede tegemine, finantstehingud) on vaikimisi keelatud ning nende aktiveerimiseks on vajalikud selged õigused koos äriliste põhjendustega. |   1   | D/V  |
| 5.7.3 | Kontrollige, et võimekustokeneid seotakse kasutajaseanssidega, sisaldavad krüptograafilist terviklikkuse kaitset ning tagage, et neid ei saa salvestada ega taaskasutada võrguühenduseta olukordades.                                       |   2   |  D   |
| 5.7.4 | Kontrollige, et agendi algatatud toimingud läbiksid sekundaarse volituse ABAC-poliitika mootoris, kasutades täielikku konteksti hindamist ja auditeerimispäevikut.                                                                          |   2   |  V   |
| 5.7.5 | Kontrollige, et agendi veatingimused ja erandite käsitlemine sisaldavad võimekuse ulatuse teavet, et toetada intsidentide analüüsi ja kohtuekspertiisi uurimist.                                                                            |   3   |  V   |

---

## Viited

### Standardid ja raamistikud

* [NIST SP 800-63-3: Digital Identity Guidelines](https://pages.nist.gov/800-63-3/)
* [Zero Trust Architecture – NIST SP 800-207](https://nvlpubs.nist.gov/nistpubs/specialpublications/NIST.SP.800-207.pdf)
* [OWASP Application Security Verification Standard (AISVS)](https://owasp.org/www-project-application-security-verification-standard/)
  ​
### Rakendamise juhendid

* [Identity and Access Management in the AI Era: 2025 Guide – IDSA](https://www.idsalliance.org/blog/identity-and-access-management-in-the-ai-era-2025-guide/)
* [Attribute-Based Access Control with OPA – Permify](https://medium.com/permify-tech-blog/attribute-based-access-control-abac-implementation-with-open-policy-agent-opa-b47052248f29)
* [How We Designed Cedar to Be Intuitive, Fast, and Safe – AWS](https://aws.amazon.com/blogs/security/how-we-designed-cedar-to-be-intuitive-to-use-fast-and-safe/)
  ​
### Tehisintellektile Spetsiifiline Turvalisus

* [Row Level Security in Vector DBs for RAG – Bluetuple.ai](https://medium.com/bluetuple-ai/implementing-row-level-security-in-vector-dbs-for-rag-applications-fdbccb63d464)
* [Tenant Isolation in Multi-Tenant Systems – WorkOS](https://workos.com/blog/tenant-isolation-in-multi-tenant-systems)
* [Handling AI Agent Permissions – Stytch](https://stytch.com/blog/handling-ai-agent-permissions/)
* [OWASP Top 10 for Large Language Model Applications](https://owasp.org/www-project-top-10-for-large-language-model-applications/)

