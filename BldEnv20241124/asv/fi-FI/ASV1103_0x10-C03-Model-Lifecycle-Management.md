# C3-mallin elinkaaren hallinta ja muutosten valvonta

## Ohjaustavoite

Tekoälyjärjestelmien on otettava käyttöön muutoshallintaprosessit, jotka estävät luvattomat tai turvattomat mallimuutokset pääsemästä tuotantoon. Tämä hallintamekanismi varmistaa mallin eheyden koko elinkaaren ajan – kehityksestä käyttöönottoon ja käytöstä poistoon – mikä mahdollistaa nopean tapauskohtaisen reagoinnin ja ylläpitää vastuullisuuden kaikille muutoksille.

Ydinturvatavoite: Vain valtuutetut ja validoidut mallit pääsevät tuotantoon käyttämällä hallittuja prosesseja, jotka ylläpitävät eheyttä, jäljitettävyyttä ja palautettavuutta.

---

## C3.1 Mallin valtuutus ja eheys

Vain valtuutetut mallit, joiden eheys on vahvistettu, pääsevät tuotantoympäristöihin.

|   #   | Description                                                                                                                                                                                                                    | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 3.1.1 | Varmista, että kaikki mallin artefaktit (painot, konfiguraatiot, tokenisaattorit) on kryptografisesti allekirjoitettu valtuutettujen tahojen toimesta ennen käyttöönottoa.                                                     |   1   | D/V  |
| 3.1.2 | Varmista, että mallin eheys tarkistetaan käyttöönottohetkellä ja allekirjoituksen varmennuksen epäonnistuminen estää mallin lataamisen.                                                                                        |   1   | D/V  |
| 3.1.3 | Varmista, että mallin alkuperätiedot sisältävät valtuuttavan tahon henkilöllisyyden, koulutusdatasta laskettavat tarkistussummat, validointitestien tulokset läpäisy-/epäonnistumistilanteineen sekä luontihetken ajan leiman. |   2   | D/V  |
| 3.1.4 | Varmista, että kaikki mallin artefaktit käyttävät semanttista versiota (MAJOR.MINOR.PATCH) ja niille on dokumentoidut kriteerit, jotka määrittävät, milloin kukin version komponentti kasvaa.                                  |   2   | D/V  |
| 3.1.5 | Varmista, että riippuvuuksien seuranta ylläpitää reaaliaikaista inventaariota, joka mahdollistaa kaikkien kuluttavien järjestelmien nopean tunnistamisen.                                                                      |   2   |  V   |

---

## C3.2 Mallin validointi ja testaus

Mallien on läpäistävä määritellyt turvallisuus- ja suojausvarmistukset ennen käyttöönottoa.

|   #   | Description                                                                                                                                                                                                                                            | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 3.2.1 | Varmista, että mallit käyvät läpi automatisoidun turvallisuustestauksen, joka sisältää syötteen validoinnin, tulosten puhdistuksen ja turvallisuusarvioinnit ennalta sovittujen organisaation läpäisy/hylätty -rajojen mukaisesti ennen käyttöönottoa. |   1   | D/V  |
| 3.2.2 | Varmista, että validointivirheet estävät automaattisesti mallin käyttöönoton, vaikka siihen olisi myönnetty nimenomainen poikkeuslupa ennalta määrätyiltä valtuutetuilta henkilöiltä, joilla on dokumentoidut liiketoiminnalliset perustelut.          |   1   | D/V  |
| 3.2.3 | Varmista, että testitulokset on kryptografisesti allekirjoitettu ja muuttumattomasti yhdistetty tarkastettavan malliversion hajautusarvoon.                                                                                                            |   2   |  V   |
| 3.2.4 | Varmista, että hätäkäyttöönotot edellyttävät dokumentoitua tietoturvariskien arviointia ja hyväksyntää ennalta nimetyltä tietoturvaviranomaiselta sovittujen aikarajojen puitteissa.                                                                   |   2   | D/V  |

---

## C3.3 Hallittu käyttöönotto ja takaisinperintä

Malli käyttöönotot on oltava hallittuja, valvottuja ja palautettavissa.

|   #   | Description                                                                                                                                                                                                                                                                                     | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 3.3.1 | Varmista, että tuotantoon siirroissa käytetään asteittaisen käyttöönoton mekanismeja (kanariasiirrot, sinivihreät käyttöönotot) automaattisten palautustoimintojen laukaisijoilla, jotka perustuvat ennalta sovittuihin virhesuhteisiin, viivekynnysarvoihin tai turvallisuushälytystekijöihin. |   1   |  D   |
| 3.3.2 | Varmista, että peruutusominaisuudet palauttavat täydellisen mallin tilan (painot, konfiguraatiot, riippuvuudet) atomisesti ennalta määriteltyjen organisaation aikarajojen sisällä.                                                                                                             |   1   | D/V  |
| 3.3.3 | Varmista, että käyttöönotto-prosessit validoivat kryptografiset allekirjoitukset ja laskevat eheystarkistussummat ennen mallin aktivointia, epäonnistuen käyttöönotossa kaikissa epäyhtäpään tapauksissa.                                                                                       |   2   | D/V  |
| 3.3.4 | Varmista, että hätätilan mallin sammutusominaisuudet voivat poistaa mallin päätepisteet käytöstä ennalta määritettyjen vasteaikojen puitteissa automaattisten piirikytkinten tai manuaalisten hätäkytkinten avulla.                                                                             |   2   | D/V  |
| 3.3.5 | Varmista, että palautusartifaktit (aiemmat malliversiot, konfiguraatiot, riippuvuudet) säilytetään organisaation politiikkojen mukaisesti muuttumattomassa tallennustilassa häiriötilanteiden hallintaa varten.                                                                                 |   2   |  V   |

---

## C3.4 Muutosten Vastuu ja Tarkastus

Kaikkien mallin elinkaaren muutosten on oltava jäljitettäviä ja auditoitavia.

|   #   | Description                                                                                                                                                                                                                                                  | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 3.4.1 | Varmista, että kaikki mallimuutokset (käyttöönotto, konfigurointi, poistaminen) tuottavat muuttumattomia tarkastustietueita, jotka sisältävät aikaleiman, todennetun käyttäjätunnuksen, muutostyypin sekä ennen ja jälkeen -tilat.                           |   1   |  V   |
| 3.4.2 | Varmista, että tarkastuslokin käyttö edellyttää asianmukaista valtuutusta ja että kaikki käyttöyritykset kirjataan käyttäjän tunnistetiedoilla ja aikaleimalla.                                                                                              |   2   | D/V  |
| 3.4.3 | Varmista, että kehotemallit ja järjestelmäviestit ovat versionhallinnassa git-repositorioissa, ja että pakolliseen koodikatselmukseen sekä nimettyjen tarkastajien hyväksyntään vaaditaan ennen käyttöönottoa.                                               |   2   | D/V  |
| 3.4.4 | Varmista, että auditointitiedot sisältävät riittävät yksityiskohdat (mallin hajautusarvot, kokoonpanon tilannevedokset, riippuvuuksien versiot) mahdollistamaan mallin tilan täydellisen rekonstruoinnin mille tahansa ajankohdalle säilytysajan puitteissa. |   2   |  V   |

---

## C3.5 Turvalliset kehityskäytännöt

Mallin kehitys- ja koulutusprosessien on noudatettava turvallisia käytäntöjä kompromissien estämiseksi.

|   #   | Description                                                                                                                                                                                                       | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 3.5.1 | Varmista, että mallin kehitys-, testaus- ja tuotantoympäristöt ovat fyysisesti tai loogisesti erillisiä. Niillä ei ole jaettua infrastruktuuria, erilliset käyttöoikeuksien hallinnat ja eristetyt tietovarastot. |   1   |  D   |
| 3.5.2 | Varmista, että mallin koulutus ja hienosäätö tapahtuvat eristetyissä ympäristöissä, joilla on hallittu verkkoyhteys.                                                                                              |   1   |  D   |
| 3.5.3 | Varmista, että koulutusdatan lähteet tarkistetaan eheystarkastuksilla ja todentavat luotettavat lähteet, joilla on dokumentoitu hallintaketju, ennen käyttöä mallin kehityksessä.                                 |   1   | D/V  |
| 3.5.4 | Varmista, että mallin kehitysartifaktit (hyperparametrit, koulutusskriptit, konfiguraatiotiedostot) tallennetaan versionhallintaan ja niiden käyttö koulutuksessa edellyttää vertaisarviointihyvääksyntää.        |   2   |  D   |

---

## C3.6 Mallin poistaminen käytöstä ja käytöstäpoisto

Mallit on poistettava turvallisesti käytöstä, kun niitä ei enää tarvita tai kun tietoturvaongelmia havaitaan.

|   #   | Description                                                                                                                                                                                                                                           | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 3.6.1 | Varmista, että mallin eläkkeelle siirtymisprosessit skannaavat automaattisesti riippuvuuskaaviot, tunnistavat kaikki kuluttajajärjestelmät ja tarjoavat ennalta sovitut ennakkoilmoitusajat ennen käytöstä poistamista.                               |   1   |  D   |
| 3.6.2 | Varmista, että eläkkeelle jääneet mallin artefaktit pyyhitään turvallisesti kryptografisella poistolla tai monikertaisella ylikirjoituksella dokumentoitujen tietojen säilytyskäytäntöjen mukaisesti, ja että tuhoutumisesta on varmennettu todistus. |   1   | D/V  |
| 3.6.3 | Varmista, että mallin poistumistapahtumat kirjataan aikaleiman ja toimijan tunnisteen kanssa, ja mallin allekirjoitukset peruutetaan uudelleenkäytön estämiseksi.                                                                                     |   2   |  V   |
| 3.6.4 | Varmista, että hätätilannemallin poistaminen käytöstä voi estää mallin käytön ennalta määritettyjen hätätilannevasteaikojen puitteissa automatisoitujen katkaisukytkimien avulla, jos kriittisiä tietoturva-aukkoja havaitaan.                        |   2   | D/V  |

---

## Viitteet

* [MLOps Principles](https://ml-ops.org/content/mlops-principles)
* [Securing AI/ML Ops – Cisco.com](https://sec.cloudapps.cisco.com/security/center/resources/SecuringAIMLOps)
* [Audit logs security: cryptographically signed tamper-proof logs](https://www.cossacklabs.com/blog/audit-logs-security/)
* [Machine Learning Model Versioning: Top Tools & Best Practices](https://lakefs.io/blog/model-versioning/)
* [AI Hygiene Starts with Models and Data Loaders – SEI Blog](https://insights.sei.cmu.edu/documents/6190/AI-Hygiene-Starts-with-Models-and-Data-Loaders_1G0KTRh.pdf)
* [How to handle versioning and rollback of a deployed ML model?](https://learn.microsoft.com/en-au/answers/questions/1845378/how-to-handle-versioning-and-rollback-of-a-deploye)
* [Reinforcement fine-tuning – OpenAI API](https://platform.openai.com/docs/guides/reinforcement-fine-tuning)
* [Auditing Machine Learning models: Governance, Data Security and …](https://www.linkedin.com/pulse/auditing-machine-learning-models-governance-data-security-negrete-yn81f)
* [Adversarial Training to Improve Model Robustness](https://medium.com/%40amit25173/adversarial-training-to-improve-model-robustness-5e285b516713)
* [What is AI adversarial robustness? – IBM Research](https://research.ibm.com/blog/securing-ai-workflows-with-adversarial-robustness)
* [Exploring Data Provenance: Ensuring Data Integrity and Authenticity](https://www.astera.com/type/blog/data-provenance/)
* [MITRE ATLAS](https://atlas.mitre.org/)
* [AWS Prescriptive Guidance – Best practices for retiring applications …](https://docs.aws.amazon.com/pdfs/prescriptive-guidance/latest/migration-app-retirement-best-practices/migration-app-retirement-best-practices.pdf)

