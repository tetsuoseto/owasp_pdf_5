# 9 Autonominen orkestrointi ja agenteettinen toiminnan turvallisuus

## Ohjaustavoite

Varmista, että autonomiset tai moniagenttiset tekoälyjärjestelmät voivat suorittaa vain toimia, jotka ovat nimenomaisesti tarkoitettuja, todennettuja, auditoitavissa ja kustannus- sekä riskirajojen sisällä. Tämä suojaa uhkilta kuten autonomisen järjestelmän kaappaus, työkalujen väärinkäyttö, agenttien silmukointihavainnointi, viestinnän kaappaus, identiteetin väärentäminen, parven manipulointi ja aikeiden manipulointi.

---

## 9.1 Agentin tehtäväsuunnittelu ja rekursion budjetit

Rajoita rekursiivisia suunnitelmia ja pakota ihmisen tarkistuspisteet etuoikeutetuissa toiminnoissa.

|   #   | Description                                                                                                                                                                                   | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.1.1 | Varmista, että maksimisyvyyden, leveyden, seinäajan, tokenien ja rahallisten kustannusten enimmäismäärät agenttien suorituksissa on keskitetysti määritelty ja versiohallittu.                |   1   | D/V  |
| 9.1.2 | Varmista, että etuoikeutetut tai peruuttamattomat toimet (esim. koodin sitomiset, rahansiirrot) vaativat ennen suorittamista eksplisiittisen ihmisen hyväksynnän auditoitavan kanavan kautta. |   1   | D/V  |
| 9.1.3 | Varmista, että reaaliaikaiset resurssienvalvontatyökalut laukaisevat katkaisimen keskeytyksen, kun jokin budjettiraja ylittyy, pysäyttäen lisätehtävien laajentamisen.                        |   2   |  D   |
| 9.1.4 | Varmista, että katkaisintapahtumat kirjataan agentin tunnuksella, laukaisevalla ehdolla ja tallennetulla suunnitelmatilalla oikeudellista tarkastelua varten.                                 |   2   | D/V  |
| 9.1.5 | Varmista, että turvallisuustestit kattavat budjetin ylittymisen ja hallitsemattoman suunnitelman skenaariot, varmistaen turvallisen pysäytyksen ilman tietojen menetystä.                     |   3   |  V   |
| 9.1.6 | Varmista, että budjettipolitiikat on ilmaistu politiikkana koodina ja että niitä sovelletaan CI/CD-putkissa estämään konfiguraation poikkeamia.                                               |   3   |  D   |

---

## 9.2 Työkalulisäosan hiekkalaatikkoympäristö

Eristä työkalujen vuorovaikutukset estääksesi luvattoman järjestelmän käytön tai koodin suorittamisen.

|   #   | Description                                                                                                                                                                                                                      | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.2.1 | Varmista, että jokainen työkalu/laajennus suoritetaan käyttöjärjestelmän, kontin tai WASM-tasoisessa hiekkalaatikossa, jossa on vähimmillä oikeuksilla toimivat tiedostojärjestelmä-, verkko- ja järjestelmäkutsu-ikäpolitiikat. |   1   | D/V  |
| 9.2.2 | Varmista, että hiekkalaatikkoympäristön resurssikiintiöt (CPU, muisti, levytila, verkkoliikenteen lähteinen liikenne) ja suoritusaikarajat otetaan käyttöön ja kirjataan.                                                        |   1   | D/V  |
| 9.2.3 | Varmista, että työkalujen binaaritiedostot tai kuvaustiedostot ovat digitaalisesti allekirjoitettuja; allekirjoitukset tarkistetaan ennen lataamista.                                                                            |   2   | D/V  |
| 9.2.4 | Varmista, että hiekkalaatikon telemetria virtaa SIEM-järjestelmään; poikkeavuudet (esim. yritykset muodostaa ulospäin suuntautuvia yhteyksiä) laukaisevat hälytyksiä.                                                            |   2   |  V   |
| 9.2.5 | Varmista, että korkean riskin laajennukset käyvät läpi turvallisuustarkastuksen ja tunkeutumistestauksen ennen käyttöönottoa tuotantoympäristössä.                                                                               |   3   |  V   |
| 9.2.6 | Varmista, että hiekkalaatikon pakenemispyrkimykset estetään automaattisesti ja että rikkomuksesta vastuussa oleva lisäosa eristetään tutkimuksen ajaksi.                                                                         |   3   | D/V  |

---

## 9.3 Autonominen silmukka ja kustannusten rajaaminen

Havaitse ja pysäytä hallitsematon agenttien välinen rekursio ja kustannusten räjähdys.

|   #   | Description                                                                                                                                       | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.3.1 | Varmista, että agenttien välisissä kutsuissa on mukana hyppyrajoitus tai TTL, jota ajonaikainen ympäristö vähentää ja valvoo.                     |   1   | D/V  |
| 9.3.2 | Varmista, että agentit ylläpitävät ainutlaatuista kutsupuiden tunnistetta (invocation-graph ID) havaitakseen itseinvokaation tai sykliset mallit. |   2   |  D   |
| 9.3.3 | Varmista, että kumulatiiviset laskentayksikkö- ja kulutuslaskurit seurataan kunkin pyyntöketjun mukaan; rajan ylittäminen keskeyttää ketjun.      |   2   | D/V  |
| 9.3.4 | Varmista, että formaali analyysi tai mallintarkastus osoittaa agenttien protokollissa olevan rekursion rajoittamattomuuden poissaolon.            |   3   |  V   |
| 9.3.5 | Varmista, että silmukan keskeytystapahtumat luovat hälytyksiä ja syöttävät jatkuvan parantamisen mittareita.                                      |   3   |  D   |

---

## 9.4 Protokollatason väärinkäytön suojaus

Turvalliset viestintäkanavat agenttien ja ulkoisten järjestelmien välillä kaappauksen tai manipuloinnin estämiseksi.

|   #   | Description                                                                                                                                                 | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.4.1 | Varmista, että kaikki agentin ja työkalun sekä agenttien väliset viestit ovat todennettuja (esim. molemminpuolinen TLS tai JWT) ja päästä päähän salattuja. |   1   | D/V  |
| 9.4.2 | Varmista, että skeemat tarkistetaan tiukasti; tuntemattomat kentät tai virheellisesti muodostetut viestit hylätään.                                         |   1   |  D   |
| 9.4.3 | Varmista, että eheystarkistukset (MAC-arvot tai digitaaliset allekirjoitukset) kattavat koko viestin sisällön, mukaan lukien työkalun parametrit.           |   2   | D/V  |
| 9.4.4 | Varmista, että uudelleenlähetyksen suojaus (nonssit tai aikaleiman ikkunat) on toteutettu protokollakerroksella.                                            |   2   |  D   |
| 9.4.5 | Varmista, että protokollan toteutukset käyvät läpi fuzzauksen ja staattisen analyysin injektio- tai deserialisointivirheiden varalta.                       |   3   |  V   |

---

## 9.5 Agentin identiteetti ja manipuloinnin havaitseminen

Varmista, että toimet ovat jäljitettävissä ja muutokset havaittavissa.

|   #   | Description                                                                                                                                | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 9.5.1 | Varmista, että jokaisella agentti-instanssilla on ainutlaatuinen kryptografinen identiteetti (avainpari tai laitteistopohjainen tunniste). |   1   | D/V  |
| 9.5.2 | Varmista, että kaikki agenttitoimet on allekirjoitettu ja aikaleimattu; lokit sisältävät allekirjoituksen kiistämisen estämiseksi.         |   2   | D/V  |
| 9.5.3 | Varmista, että manipulointia osoittavat lokit tallennetaan liitettävään tai kirjoituskertaan tallennusvälineeseen.                         |   2   |  V   |
| 9.5.4 | Varmista, että identiteettiavaimet vaihtuvat määritellyn aikataulun mukaisesti ja kompromissin merkkeihin perustuen.                       |   3   |  D   |
| 9.5.5 | Varmista, että huijaus- tai avainkonfliktiyritykset aiheuttavat välittömän karanteenin kyseiselle agentille.                               |   3   | D/V  |

---

## 9.6 Moniagenttisen parvitoiminnan riskien vähentäminen

Rajoita kollektiivisen käyttäytymisen vaaroja eristyksen ja muodollisen turvallisuusmallinnuksen avulla.

|   #   | Description                                                                                                                                                     | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.6.1 | Varmista, että eri suojausalueilla toimivat agentit suoritetaan eristetyissä ajonaikaisissa hiekkalaatikoissa tai verkkosegmenteissä.                           |   1   | D/V  |
| 9.6.2 | Varmista, että parvetoimintojen mallit on luotu ja ne on muodollisesti varmennettu elinvoimaisuuden ja turvallisuuden osalta ennen käyttöönottoa.               |   3   |  V   |
| 9.6.3 | Varmista, että ajonaikaiset valvontajärjestelmät havaitsevat nousevat vaaralliset mallit (esim. värähtelyt, umpikuopat) ja käynnistävät korjaavat toimenpiteet. |   3   |  D   |

---

## 9.7 Käyttäjän ja työkalun todennus / valtuutus

Ota käyttöön vahvat pääsynvalvontamekanismit jokaiselle agentin käynnistämälle toiminnolle.

|   #   | Description                                                                                                                                                                       | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.7.1 | Varmista, että agentit todentuvat ensiluokkaisina toimijoina alajärjestelmiin käyttäen, eivätkä koskaan uudelleenkäytä loppukäyttäjän tunnistetietoja.                            |   1   | D/V  |
| 9.7.2 | Varmista, että hienojakoiset valtuutuspolitiikat rajoittavat, mitä työkaluja agentti saa käyttää ja mitä parametreja se saa antaa.                                                |   2   |  D   |
| 9.7.3 | Varmista, että käyttöoikeustarkistukset arvioidaan uudelleen jokaisella kutsulla (jatkuva valtuutus), ei vain istunnon alussa.                                                    |   2   |  V   |
| 9.7.4 | Varmista, että valtuutetut oikeudet vanhenevat automaattisesti ja että niiden vahvistaminen vaatii uudelleen suostumuksen aikakatkaisun tai käyttöoikeusalueen muutoksen jälkeen. |   3   |  D   |

---

## 9.8 Agenttien välinen viestinnän turvallisuus

Salaa ja suojaa kaikki agenttien väliset viestit eheyden varmistamiseksi estääksesi salakuuntelun ja manipuloinnin.

|   #   | Description                                                                                                                            | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.8.1 | Varmista, että keskinäinen todennus ja täydellinen eteenpäin suojattu salaus (esim. TLS 1.3) ovat pakollisia agenttikanaville.         |   1   | D/V  |
| 9.8.2 | Varmista, että viestin eheys ja alkuperä tarkistetaan ennen käsittelyä; epäonnistumiset aiheuttavat hälytyksiä ja viestin hylkäämisen. |   1   |  D   |
| 9.8.3 | Varmista, että viestinnän metatiedot (aikaleimat, sekvenssinumerot) kirjataan forensista uudelleenrakennusta varten.                   |   2   | D/V  |
| 9.8.4 | Varmista, että formaali verifiointi tai mallintarkastus vahvistaa, että protokollan tilakoneita ei voida johtaa vaarallisiin tiloihin. |   3   |  V   |

---

## 9.9 Tarkoituksen vahvistaminen ja rajoitusten noudattamisen varmistaminen

Varmista, että agentin toimet vastaavat käyttäjän ilmoitettua tarkoitusta ja järjestelmän rajoituksia.

|   #   | Description                                                                                                                                                                                           | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.9.1 | Varmista, että esisuorituksen rajoiteanalysoijat tarkistavat ehdotetut toiminnot kovakoodattuja turvallisuus- ja politiikkasääntöjä vastaan.                                                          |   1   |  D   |
| 9.9.2 | Varmista, että merkittäviä toimenpiteitä (taloudellisia, tuhoisia, yksityisyydensuojan kannalta herkkiä) varten vaaditaan selkeä tarkoituksen vahvistus aloittavalta käyttäjältä.                     |   2   | D/V  |
| 9.9.3 | Varmista, että jälkiehtojen tarkistukset validoivat, että suoritetut toimenpiteet saavuttivat tarkoitetut vaikutukset ilman sivuvaikutuksia; epäjohdonmukaisuudet käynnistävät palautuksen.           |   2   |  V   |
| 9.9.4 | Vahvista, että formaalit menetelmät (esim. mallintarkastus, aksiomien todistaminen) tai ominaisuusperusteiset testit osoittavat, että agenttien suunnitelmat täyttävät kaikki ilmoitetut rajoitukset. |   3   |  V   |
| 9.9.5 | Varmista, että tarkoituksenmukaisuuden poikkeamat tai rajoitusten rikkomistapaukset syöttävät jatkuvan parantamisen sykleihin ja uhkatiedon jakamiseen.                                               |   3   |  D   |

---

## 9.10 Agentin päättelystrategian turvallisuus

Eri päättelystrategioiden, kuten ReActin, Chain-of-Thoughtin ja Tree-of-Thoughts-lähestymistapojen turvallinen valinta ja suoritus.

|   #    | Description                                                                                                                                                                                                                                                    | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.10.1 | Varmista, että päättelystrategian valinta perustuu deterministisiin kriteereihin (tulosteen monimutkaisuus, tehtävän tyyppi, turvallisuuskonteksti) ja että identtiset syötteet tuottavat identtiset strategian valinnat saman turvallisuuskontekstin sisällä. |   1   | D/V  |
| 9.10.2 | Varmista, että jokaisella päättelystrategialla (ReAct, Chain-of-Thought, Tree-of-Thoughts) on oma syötteen validointi, tulosten puhdistus ja suoritusaikarajat, jotka ovat räätälöity sen kognitiivisen lähestymistavan mukaisesti.                            |   1   | D/V  |
| 9.10.3 | Varmista, että päättelystrategian siirtymät kirjataan täydellisen kontekstin kanssa, mukaan lukien syötteen ominaisuudet, valintakriteerien arvot ja suoritusmetadata, auditointijäljen uudelleenrakentamista varten.                                          |   2   | D/V  |
| 9.10.4 | Varmista, että Tree-of-Thoughts -päättely sisältää haarojen karsimismekanismit, jotka lopettavat tutkinnan, kun havaitaan politiikan rikkomuksia, resurssirajoituksia tai turvallisuusrajoja.                                                                  |   2   | D/V  |
| 9.10.5 | Varmista, että ReAct (Reason-Act-Observe) -syklit sisältävät validointipisteet kussakin vaiheessa: päättelyaskeleen tarkistus, toiminnan valtuutus ja havainnon puhdistus ennen etenemistä.                                                                    |   2   | D/V  |
| 9.10.6 | Varmista, että päättelystrategian suorituskykymittareita (suoritusaika, resurssien käyttö, tuloksen laatu) seurataan ja että poikkeamista asetettuihin raja-arvoihin annetaan automaattiset hälytykset.                                                        |   3   | D/V  |
| 9.10.7 | Varmista, että hybridipäätöksentekomenetelmät, jotka yhdistävät useita strategioita, säilyttävät kaikkien osastrategioiden syötteen validoinnin ja tulosrajoitukset ilman, että kiertävät yhtäkään turvallisuusvalvontaa.                                      |   3   | D/V  |
| 9.10.8 | Varmista, että päättelystrategian turvallisuustestaus sisältää väärinmuotoiltujen syötteiden fuzzauksen, vastustavat kehotteet, jotka on suunniteltu pakottamaan strategian vaihto, sekä rajatilaustestauksen jokaiselle kognitiiviselle lähestymistavalle.    |   3   | D/V  |

---

## 9.11 Agentin elinkaaren tilanhallinta ja turvallisuus

Turvallinen agentin alustaminen, tilan muutokset ja lopetus kryptografisten tarkastusjälkien ja määriteltyjen palautusmenettelyjen avulla.

|   #    | Description                                                                                                                                                                                                                                                                                         | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.11.1 | Varmista, että agentin alustus sisältää kryptografisen identiteetin perustamisen laitteistopohjaisilla tunnuksilla sekä muuttumattomat käynnistysauditointilokit, jotka sisältävät agentin tunnuksen, aikaleiman, kokoonpanohashin ja alustuksen parametrit.                                        |   1   | D/V  |
| 9.11.2 | Varmista, että agentin tilasiirtymät ovat kryptografisesti allekirjoitettuja, aikaleimattuja ja kirjattuja täydellisen kontekstin kanssa, mukaan lukien laukaisevat tapahtumat, edellisen tilan tiiviste, uuden tilan tiiviste ja suoritetut tietoturvatarkastukset.                                |   2   | D/V  |
| 9.11.3 | Varmista, että agentin sammutusmenettelyt sisältävät turvallisen muistin tyhjennyksen käyttäen kryptografista poistamista tai monivaiheista ylikirjoitusta, tunnistetietojen peruutuksen varmenneviranomaiselle ilmoittamisen kanssa sekä muuttamattomuuden todistavien päättötodistusten luomisen. |   2   | D/V  |
| 9.11.4 | Varmista, että agentin palautusmekanismit validoivat tilan eheyden käyttämällä kryptografisia tarkistussummia (vähintään SHA-256) ja palauttavat tilan tunnetusti ehjiin tiloihin, kun korruptio havaitaan, käyttäen automatisoituja hälytyksiä ja manuaalisia hyväksymisvaatimuksia.               |   3   | D/V  |
| 9.11.5 | Varmista, että agentin pysyvyysmekanismit salaavat arkaluontoiset tilatiedot agenttikohtaisilla AES-256-avaimilla ja toteuttavat turvallisen avainten kierrätyksen määritettävissä aikatauluissa (enintään 90 päivää) niin, että käyttöönotto tapahtuu ilman seisokkeja.                            |   3   | D/V  |

---

## 9.12 Työkalujen integraation turvallisuuskehys

Turvallisuusvalvontamekanismit dynaamiseen työkalujen lataamiseen, suorittamiseen ja tulosten validointiin määriteltyjen riskinarviointi- ja hyväksymisprosessien mukaisesti.

|   #    | Description                                                                                                                                                                                                                                                                                           | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.12.1 | Varmista, että työkalukuvaajat sisältävät turvadataa, jossa määritellään vaaditut oikeudet (luku/kirjoitus/suoritus), riskitasot (matala/keskitaso/korkea), resurssirajoitukset (CPU, muisti, verkko) ja työkaluluetteloissa dokumentoidut validointivaatimukset.                                     |   1   | D/V  |
| 9.12.2 | Varmista, että työkalun suoritusresultaatit validoidaan odotettujen skeemojen (JSON-skeema, XML-skeema) ja turvallisuuspolitiikkojen (tulosteen puhdistus, dataluokittelu) mukaisesti ennen integrointia aikakatkaisurajojen ja virheenkäsittelymenetelmien kanssa.                                   |   1   | D/V  |
| 9.12.3 | Varmista, että työkalun vuorovaikutuslokit sisältävät yksityiskohtaisen turvallisuuskontekstin, mukaan lukien oikeustason käyttö, tietojen käyttökuviot, suoritusaika, resurssien kulutus ja paluuarvot rakenteellisella lokituksella SIEM-integraatiota varten.                                      |   2   | D/V  |
| 9.12.4 | Varmista, että dynaamiset työkalujen latausmekanismit validoivat digitaaliset allekirjoitukset PKI-infrastruktuurin avulla ja toteuttavat turvalliset latausprotokollat hiekkalaatikkoympäristön eristämisellä sekä käyttöoikeuksien varmennuksella ennen suorittamista.                              |   2   | D/V  |
| 9.12.5 | Varmista, että työkalujen turvallisuusarvioinnit käynnistyvät automaattisesti uusille versioille pakollisten hyväksymiskanavien avulla, jotka sisältävät staattisen analyysin, dynaamisen testauksen ja turvallisuustiimin tarkastelun, dokumentoiduilla hyväksymiskriteereillä ja SLA-vaatimuksilla. |   3   | D/V  |

---

### Viitteet

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

