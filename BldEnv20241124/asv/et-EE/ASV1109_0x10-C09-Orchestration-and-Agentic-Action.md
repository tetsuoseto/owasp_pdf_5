# 9 Autonoomne orkestratsioon ja agendi tegevuse turvalisus

## Kontrollieesmärk

Tagada, et autonoomsed või mitmeagendilised tehisintellekti süsteemid saaksid teostada ainult selliseid toiminguid, mis on selgelt kavandatud, autentitud, auditeeritavad ning jäävad määratletud kulude ja riskide piiridesse. See kaitseb selliste ohtude eest nagu autonoomse süsteemi kompromiteerimine, tööriistade väärkasutus, agendi silmuse tuvastamine, kommunikatsiooni hõivamine, identiteedi võltsimine, parvede manipuleerimine ja kavatsuse manipuleerimine.

---

## 9.1 Agendi ülesannete planeerimise ja rekursiooni eelarved

Pidurdage rekursiivseid plaane ja sundige inimeste kontrollpunkte privileegitud toimingute jaoks.

|   #   | Description                                                                                                                                                                           | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.1.1 | Kinnitage, et maksimaalne rekursiooni sügavus, laiendus, seinakella aeg, tokenid ja rahaline kulu iga agendi täitmise kohta on tsentraalselt konfigureeritud ja versioonihalduses.    |   1   | D/V  |
| 9.1.2 | Kinnitage, et privileegitud või pöördumatud toimingud (nt koodi kinnitused, rahalised ülekanded) nõuavad enne täitmist selgesõnalist inimlikku heakskiitu auditeeritava kanali kaudu. |   1   | D/V  |
| 9.1.3 | Kinnitage, et reaalajas ressursimonitorid käivitavad kaablilõikuri katkestuse, kui ületatakse mis tahes eelarve läviväärtus, peatades täiendava ülesannete laienemise.                |   2   |  D   |
| 9.1.4 | Kontrollige, et lülitusseadme sündmused oleksid logitud koos agendi ID, vallanduva tingimuse ja salvestatud plaani olekuga kohtuekspertiisi ülevaatamiseks.                           |   2   | D/V  |
| 9.1.5 | Kinnitage, et turvatestid hõlmavad eelarve ammendumise ja jooksva plaani stsenaariume, kinnitades turvalist peatamist ilma andmekadudeta.                                             |   3   |  V   |
| 9.1.6 | Kinnitage, et eelarvepoliitikad on väljendatud kui poliitika-koodi ja jõustatakse CI/CD-s konfiguratsioonide nihkumise takistamiseks.                                                 |   3   |  D   |

---

## 9.2 Tööriista pistikprogrammi liivakastimine

Isoleerige tööriistade suhtlused selleks, et vältida volitamata süsteemile juurdepääsu või koodi täitmist.

|   #   | Description                                                                                                                                                                                | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 9.2.1 | Kontrolli, et iga tööriist/plugin täidaks operatsioonisüsteemi, konteineri või WASM-tasemel sandboxis, järgides minimaalsete õigustega failisüsteemi, võrgu ja süsteemikõnede poliitikaid. |   1   | D/V  |
| 9.2.2 | Kontrollige, et liivakasti ressursi kvoodid (CPU, mälu, ketas, võrgu väljapääs) ja täitmise ajalimiidid oleksid rakendatud ja logitud.                                                     |   1   | D/V  |
| 9.2.3 | Kontrolli, et tööriistade binaarfailid või kirjeldajad oleksid digitaalselt allkirjastatud; allkirju kontrollitakse enne nende laadimist.                                                  |   2   | D/V  |
| 9.2.4 | Kinnitage, et liivakasti telemeetria voolab SIEM-i; anomaaliad (nt katse väljaminevate ühenduste loomiseks) tekitavad hoiatusi.                                                            |   2   |  V   |
| 9.2.5 | Kontrollige, et kõrge riskitasemega pistikprogrammid läbiksid enne tootmiskeskkonda jõudmist turvaülevaate ja sissetungimistestimise.                                                      |   3   |  V   |
| 9.2.6 | Kontrollige, kas liivakasti põgenemise katsed blokeeritakse automaatselt ning rikkumise toime pannud pistikprogramm paigutatakse uurimise ajaks karantiini.                                |   3   | D/V  |

---

## 9.3 Autonoomne tsükkel ja kulude piiramise mehhanism

Tuvastage ja peatage kontrollimatu agendi-agendi rekursioon ja kulude plahvatused.

|   #   | Description                                                                                                                               | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.3.1 | Kinnitage, et agentidevahelised kõned sisaldavad hüppelimiiti või TTL-i, mida täitmise ajal vähendatakse ja millele järgimist valvatakse. |   1   | D/V  |
| 9.3.2 | Kontrollige, et agendid säilitaksid ainulaadse kutse-kaariku ID, et tuvastada enesekutse või tsüklilised mustrid.                         |   2   |  D   |
| 9.3.3 | Kinnitage, et kumulatiivseid arvutusüksuse ja kulutuse loendurid jälgitakse päringu ahela lõikes; limiidi ületamine katkestab ahela.      |   2   | D/V  |
| 9.3.4 | Kinnitage, et formaalne analüüs või mudelite kontrollimine tõendab piiramatute rekursioonide puudumist agendi protokollides.              |   3   |  V   |
| 9.3.5 | Kinnitage, et tsükli katkestamise sündmused tekitavad hoiatusi ja edastavad pideva täiustamise mõõdikuid.                                 |   3   |  D   |

---

## 9.4 Protokolli taseme väärkasutuse kaitse

Turvalised kommunikatsioonikanalid agentide ja välissüsteemide vahel kaaperdamise või manipuleerimise vältimiseks.

|   #   | Description                                                                                                                                                      | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.4.1 | Kinnitage, et kõik agendi ja tööriista ning agendi ja agendi vahelised sõnumid on autentitud (nt vastastikune TLS või JWT) ja otsast lõpuni krüpteeritud.        |   1   | D/V  |
| 9.4.2 | Kontrollige, et skeemid oleksid rangelt valideeritud; tundmatud väljad või valesti vormistatud sõnumid lükatakse tagasi.                                         |   1   |  D   |
| 9.4.3 | Kinnitage, et terviklikkuse kontrollid (MAC-id või digitaalsed allkirjad) katavad kogu sõnumi kasuliku koormuse, sealhulgas tööriista parameetrid.               |   2   | D/V  |
| 9.4.4 | Kinnitage, et kordusrünnete vältimine (nontsid või ajatempli aknad) on protokolli tasemel jõustatud.                                                             |   2   |  D   |
| 9.4.5 | Kontrollige, et protokolli rakendused läbiksid süstematiseeritud testimise (fuzzing) ja staatilise analüüsi, et tuvastada süstimise või deserialiseerimise vigu. |   3   |  V   |

---

## 9.5 Agendi identiteet ja manipuleerimiskindlus

Tagage, et toimingud oleksid jälgitavad ja muudatused tuvastatavad.

|   #   | Description                                                                                                                    | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 9.5.1 | Kontrollige, et iga agendi eksemplar omab unikaalset krüptograafilist identiteeti (võtme-paari või riistvarapõhist volikirja). |   1   | D/V  |
| 9.5.2 | Kontrollige, et kõik agendi toimingud on allkirjastatud ja ajatemplitud; logides on allkiri tagamaks eitustõkendust.           |   2   | D/V  |
| 9.5.3 | Veenduge, et muutmisjälgi kuvatavad logid salvestatakse ainult lisamise või ainult kirjutamisega keskkonda.                    |   2   |  V   |
| 9.5.4 | Kontrolli, et identiteedivõtmed vahetuksid määratletud ajakava alusel ning kompromiteerimise tunnuste ilmnemisel.              |   3   |  D   |
| 9.5.5 | Kinnitage, et võltsimis- või võtmekonflikti katsed põhjustavad mõjutatud agendi kohese karantiini sattumise.                   |   3   | D/V  |

---

## 9.6 Mitmeagendi parve riskide vähendamine

Kollektiivkäitumise ohte vähendatakse isolatsiooni ja formaalse ohutusmodelleerimise kaudu.

|   #   | Description                                                                                                                      | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.6.1 | Kontrollige, et erinevates turvadomeenides tegutsevad agendid töötaksid isoleeritud käituskeskkondades või võrgu segmentides.    |   1   | D/V  |
| 9.6.2 | Kinnitage, et parvkäitumisi on mudeldatud ja formaalselt kontrollitud elujõulisuse ja ohutuse osas enne juurutamist.             |   3   |  V   |
| 9.6.3 | Kinnitage, et tööajal monitore tuvastavad tekkivaid ohtlikke mustreid (nt kõikumised, ummikseisud) ja algatavad parandusmeetmed. |   3   |  D   |

---

## 9.7 Kasutaja ja tööriista autentimine / autoriseerimine

Rakendage iga agendi käivitatud toimingu jaoks usaldusväärsed juurdepääsukontrollid.

|   #   | Description                                                                                                                                          | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.7.1 | Kontrollige, et agendid autentiks end alamprogrammides esimese järgu põhisõlmena, kunagi mitte kasutades taaskord lõppkasutaja mandaate.             |   1   | D/V  |
| 9.7.2 | Kinnitage, et peenhäälestatud autoriseerimispoliitikad piiravad, milliseid tööriistu agent võib kutsuda ning milliseid parameetreid ta võib esitada. |   2   |  D   |
| 9.7.3 | Kinnitage, et privileegikontrollid hinnatakse uuesti iga kõne puhul (kontinuous autoriseerimine), mitte ainult sessiooni alguses.                    |   2   |  V   |
| 9.7.4 | Kontrollige, et volitatud õigused aeguvad automaatselt ja nõuavad pärast ajapiirangu või õiguste ulatuse muutust uuesti nõusolekut.                  |   3   |  D   |

---

## 9.8 Agendi-agendi suhtluse turvalisus

Krüpteeri ja kaitse terviklikkust kõigi agendi vaheliste sõnumite puhul, et takistada pealtkuulamist ja sõnumite muutmist.

|   #   | Description                                                                                                                                   | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.8.1 | Kontrollige, et agendi kanalite puhul oleksid kohustuslikud vastastikune autentimine ja perfekaalse edasikaitsega krüpteerimine (nt TLS 1.3). |   1   | D/V  |
| 9.8.2 | Kinnitage, et sõnumi terviklikkus ja päritolu kontrollitakse enne töötlemist; vigade korral antakse hoiatused ja sõnum loobutakse.            |   1   |  D   |
| 9.8.3 | Kinnitage, et suhtluse metadata (ajatempleid, järjenumbreid) logitakse kohtuekspertiisi rekonstrueerimise toetamiseks.                        |   2   | D/V  |
| 9.8.4 | Kontrollige, et formaalne verifitseerimine või mudelisõelumine kinnitab, et protokolli olekumasinaid ei saa viia ebaturvalistesse olekutesse. |   3   |  V   |

---

## 9.9 Eesmärgi kinnitamine ja piirangute jõustamine

Kinnitage, et agendi tegevused vastavad kasutaja väljendatud kavatsusele ja süsteemi piirangutele.

|   #   | Description                                                                                                                                                                                  | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.9.1 | Kinnitage, et eelpööramise tingimuste lahendajad kontrollivad pakutud toiminguid kõva kodeeritud ohutus- ja poliitikareeglite vastu.                                                         |   1   |  D   |
| 9.9.2 | Kinnitage, et kõrge mõjuga toimingud (rahaliselt olulised, hävitavad, privaatsust mõjutavad) nõuavad algse kasutaja selgesõnalist kavatsuse kinnitamist.                                     |   2   | D/V  |
| 9.9.3 | Kontrollige, et järeltingimuste kontrollid kinnitaksid, et lõpetatud toimingud saavutasid kavandatud mõjud ilma kõrvalmõjudeta; erinevused käivitavad tagasipööramise.                       |   2   |  V   |
| 9.9.4 | Kinnitage, et formaalsed meetodid (nt mudelipõhine kontroll, teoreemide tõestamine) või omadustel põhinevad testid tõendavad, et agendi plaanid vastavad kõigile deklareeritud piirangutele. |   3   |  V   |
| 9.9.5 | Kinnitage, et kavatsuseainete kokkusobimatus või piirangute rikkumise juhtumid toidavad pidevate paranemistsüklite ja ohuintelligentsi jagamist.                                             |   3   |  D   |

---

## 9.10 Agendi järeldusstrateegia turvalisus

Erinevate järeldusstrateegiate, sealhulgas ReAct, Chain-of-Thought ja Tree-of-Thoughts meetodite turvaline valimine ja käivitamine.

|   #    | Description                                                                                                                                                                                                                             | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.10.1 | Kinnitage, et mõtlemisstrateegia valik kasutab deterministlikke kriteeriume (sisendi keerukus, ülesande tüüp, turvakontekst) ning identsed sisendid annavad sama turvakonteksti puhul sama strateegia valiku.                           |   1   | D/V  |
| 9.10.2 | Veenduge, et igal mõtlemisstrateegial (ReAct, Chain-of-Thought, Tree-of-Thoughts) oleks pühendatud sisendi valideerimine, väljundi puhastamine ja täitmisaja piirangud, mis on spetsiifilised selle kognitiivsele lähenemisele.         |   1   | D/V  |
| 9.10.3 | Kinnitage, et mõtlemisstrateegiate üleminekud salvestatakse koos täieliku kontekstiga, sealhulgas sisendi omadused, valikukriteeriumide väärtused ja täitmise metaandmed, auditi jälje taastamiseks.                                    |   2   | D/V  |
| 9.10.4 | Kinnitage, et mõttepuu (Tree-of-Thoughts) järeldusmehhanismides on olemas harude kärpimise mehhanismid, mis lõpetavad uurimise poliitikate rikkumiste, ressursside piirangute või turvapiiride tuvastamisel.                            |   2   | D/V  |
| 9.10.5 | Kinnitage, et ReAct (Reason-Act-Observe) tsüklid sisaldavad valideerimispunkte igas etapis: mõtlemisfaasi sammude kontroll, tegevuse autoriseerimine ja vaatlustulemite puhastamine enne jätkamist.                                     |   2   | D/V  |
| 9.10.6 | Kontrollige, et järeldusstrateegia tulemuslikkuse mõõdikuid (täitmisaeg, ressursikasutus, väljundi kvaliteet) jälgitakse ning automaatsete hoiatussignaalidega teavitatakse, kui mõõdikud kalduvad konfigureeritud lävenditest kõrvale. |   3   | D/V  |
| 9.10.7 | Kinnitage, et hübriidotsustusmeetodid, mis ühendavad mitut strateegiat, säilitavad kõigi koosneva strateegiate sisendi valideerimise ja väljundi piirangud ilma ühegi turvakontrolli ümberkäimiseta.                                    |   3   | D/V  |
| 9.10.8 | Kinnitage, et mõtlemisstrateegia turvatestimine hõlmab vigaste sisendite fuzzerimist, strateegia vahetamiseks mõeldud vaenulikke küsimusi ja iga kognitiivse lähenemise piirtingimuste testimist.                                       |   3   | D/V  |

---

## 9.11 Agendi elutsükli oleku haldus ja turvalisus

Turvaline agendi initsialiseerimine, olekuüleminekud ja lõpetamine krüptograafiliste auditeerimisjälgede ning määratletud taastemenetlustega.

|   #    | Description                                                                                                                                                                                                                                                                          | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 9.11.1 | Kontrollige, et agendi initsialiseerimine hõlmaks krüptograafilise identiteedi loomist riistvara-põhiste volitustega ning muutumatuid käivitamise auditiloge, mis sisaldavad agendi ID-d, ajatemplit, konfiguratsiooni räsi ja initsialiseerimisparameetreid.                        |   1   | D/V  |
| 9.11.2 | Kinnitage, et agendi olekuüleminekud on krüptograafiliselt allkirjastatud, ajatemplitud ja logitud täieliku kontekstiga, sealhulgas käivitavad sündmused, eelmise oleku räsi, uue oleku räsi ja teostatud turvakontrollid.                                                           |   2   | D/V  |
| 9.11.3 | Kontrollige, et agendi väljalülitamise protseduurid hõlmaksid turvalist mälupuhastust krüptograafilise kustutamise või mitmekordse üle kirjutamisega, volituste tühistamist sertifikaadi tõrkehoiatusedega ning muutmiskindlate lõpetamistunnistuste genereerimist.                  |   2   | D/V  |
| 9.11.4 | Kontrollige, kas agendi taastemehhanismid valideerivad oleku terviklikkust krüptograafiliste kontrollsummadega (vähemalt SHA-256) ning pöörduvad automaatselt tagasi tuntud heade olekuteni korruptsiooni avastamisel koos automatiseeritud teadete ja käsitsi kinnitamise nõuetega. |   3   | D/V  |
| 9.11.5 | Kinnitage, et agentide püsivuse mehhanismid krüpteerivad tundlikud olekuandmed iga agenti kohta eraldi AES-256 võtmetega ning rakendavad turvalist võtmevahetust konfigureeritavate ajakavadega (kuni 90 päeva), tagades nullse katkestuseta juurutamise.                            |   3   | D/V  |

---

## 9.12 Tööriistade integreerimise turvasüsteem

Turvameetmed dünaamilise tööriista laadimiseks, täitmiseks ja tulemuste valideerimiseks, millel on määratletud riskihindamise ja kinnitamisprotsessid.

|   #    | Description                                                                                                                                                                                                                                                                       | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.12.1 | Kontrolli, et tööriista kirjeldustes oleks turvaandmed, mis täpsustavad nõutavad õigused (lugemine/kirjutamine/käivitus), riskitasemed (madal/keskmine/kõrge), ressursipiirangud (CPU, mälu, võrk) ja valideerimisnõuded, mis on dokumenteeritud tööriista manifestides.          |   1   | D/V  |
| 9.12.2 | Kontrollige, et tööriista täitmise tulemused kinnitatakse vastavalt oodatud skeemidele (JSON-skeem, XML-skeem) ja turvapoliitikatele (väljundi puhastamine, andmete klassifitseerimine) enne integreerimist ajapiirangute ja veahaldusprotseduuridega.                            |   1   | D/V  |
| 9.12.3 | Kontrollige, et tööriista interaktsioonilogid sisaldaksid üksikasjalikku turvakonteksti, sealhulgas õiguste kasutamist, andmete juurdepääsumustreid, täitmisaja, ressursside tarbimist ja tagastuskoodide struktureeritud logimist SIEM-süsteemide integreerimiseks.              |   2   | D/V  |
| 9.12.4 | Kontrollige, et dünaamilised tööriista laadimise mehhanismid valideeriksid digitaalallkirju, kasutades PKI infrastruktuuri, ning rakendaksid turvalisi laadimisprotokolle liivakasti isolatsiooni ja õiguste kontrolliga enne täitmist.                                           |   2   | D/V  |
| 9.12.5 | Kinnitage, et tööriistade turvakontrollid käivituvad automaatselt uute versioonide puhul kohustuslike heakskiitvate etappidega, mis hõlmavad staatilist analüüsi, dünaamilist testimist ja turvatiimi ülevaadet dokumenteeritud heakskiitukriteeriumide ja teenustaseme nõuetega. |   3   | D/V  |

---

### Viited

* [MITRE ATLAS tactics ML09](https://atlas.mitre.org/)
* [Circuit-breaker research for AI agents — Zou et al., 2024](https://arxiv.org/abs/2406.04313)
* [Trend Micro analysis of sandbox escapes in AI agents — Park, 2025](https://www.trendmicro.com/vinfo/us/security/news/cybercrime-and-digital-threats/unveiling-ai-agent-vulnerabilities-code-execution)
* [Auth0 guidance on human-in-the-loop authorization for agents — Martinez, 2025](https://auth0.com/blog/secure-human-in-the-loop-interactions-for-ai-agents/)
* [Medium deep-dive on MCP & A2A protocol hijacking — ForAISec, 2025](https://medium.com/%40foraisec/security-analysis-potential-ai-agent-hijacking-via-mcp-and-a2a-protocol-insights-cd1ec5e6045f)
* [Rapid7 fundamentals on spoofing attack prevention — 2024](https://www.rapid7.com/fundamentals/spoofing-attacks/)
* [Imperial College verification of swarm systems — Lomuscio et al.](https://sail.doc.ic.ac.uk/projects/swarms/)
* [NIST AI Risk Management Framework 1.0, 2023](https://nvlpubs.nist.gov/nistpubs/ai/nist.ai.100-1.pdf)
* [WIRED security briefing on encryption best practices, 2024](https://www.wired.com/story/encryption-apps-chinese-telecom-hacking-hydra-russia-exxon)
* [OWASP Top 10 for LLM Applications, 2025](https://owasp.org/www-project-top-10-for-large-language-model-applications/)
* [Comprehensive Vulnerability Analysis is Necessary for Trustworthy LLM-MAS](https://arxiv.org/html/2506.01245v1)
* [How Is LLM Reasoning Distracted by Irrelevant Context?
  An Analysis Using a Controlled Benchmark](https://www.arxiv.org/pdf/2505.18761)
* [Large Language Model Sentinel: LLM Agent for Adversarial Purification](https://arxiv.org/pdf/2405.20770)
* [Securing Agentic AI: A Comprehensive Threat Model and Mitigation Framework for Generative AI Agents](https://arxiv.org/html/2504.19956v2)

