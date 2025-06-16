# C6 Mallien, kehysten ja datan toimitusketjun turvallisuus

## Ohjaustavoite

AI-toimitusketjun hyökkäykset hyödyntävät kolmannen osapuolen malleja, kehyksiä tai tietoaineistoja takaovien, harhan tai hyödynnettävissä olevan koodin upottamiseen. Nämä kontrollit tarjoavat päästä päähän jäljitettävyyden, haavoittuvuuksien hallinnan ja valvonnan suojellakseen koko mallin elinkaaren.

---

## C6.1 Esikoulutettujen mallien arviointi ja alkuperän varmistus

Arvioi ja vahvista kolmannen osapuolen mallien alkuperä, lisenssit ja piilevät toiminnot ennen hienosäätöä tai käyttöönottoa.

|   #   | Description                                                                                                                                                   | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 6.1.1 | Varmista, että jokaisessa kolmannen osapuolen mallin artifaktissa on allekirjoitettu alkuperätietue, joka tunnistaa lähdevaraston ja commit-hashin.           |   1   | D/V  |
| 6.1.2 | Varmista, että mallit tutkitaan automaattisilla työkaluilla haitallisten kerrosten tai Troijan laukaisimien varalta ennen tuontia.                            |   1   | D/V  |
| 6.1.3 | Varmista, että siirto-opetus hienosäätää mallin niin, että se läpäisee vastustava arvioinnin piilotettujen käyttäytymismallien havaitsemiseksi.               |   2   |  D   |
| 6.1.4 | Varmista, että mallin lisenssit, vientivalvontatunnisteet ja datan alkuperäilmoitukset on tallennettu ML-BOM-tietueeseen.                                     |   2   |  V   |
| 6.1.5 | Varmista, että korkean riskin mallit (julkisesti ladatut painot, verifioimattomat tekijät) pysyvät eristyksissä ihmisen tarkastukseen ja hyväksyntään saakka. |   3   | D/V  |

---

## C6.2 Kehys- ja kirjastotarkastus

Jatkuvasti skannaa koneoppimiskehyksiä ja kirjastoja CVE-haavoittuvuuksien ja haitallisen koodin varalta pitääkseen suoritinpinon turvallisena.

|   #   | Description                                                                                                                                         | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 6.2.1 | Varmista, että CI-putket suorittavat riippuvuustarkastuksia tekoälykehyksissä ja kriittisissä kirjastoissa.                                         |   1   | D/V  |
| 6.2.2 | Varmista, että kriittiset haavoittuvuudet (CVSS ≥ 7.0) estävät ylennyksen tuotantokuviksi.                                                          |   1   | D/V  |
| 6.2.3 | Varmista, että staattinen koodianalyysi suoritetaan haarautuneille tai mukaan otetuille koneoppimiskirjastoille.                                    |   2   |  D   |
| 6.2.4 | Varmista, että kehysjärjestelmän päivitysehdotuksiin sisältyy tietoturva-arviointi, jossa viitataan julkisiin CVE-tietoja tarjoaviin lähteisiin.    |   2   |  V   |
| 6.2.5 | Varmista, että ajonaikaiset sensorit hälyttävät odottamattomista dynaamisista kirjastojen latauksista, jotka poikkeavat allekirjoitetusta SBOM:sta. |   3   |  V   |

---

## C6.3 Riippuvuuksien lukitseminen ja varmennus

Kiinnitä jokainen riippuvuus muuttumattomiin tiivisteisiin ja toista rakennukset varmistaaksesi identtiset, väärentämättömät artefaktit.

|   #   | Description                                                                                                                            | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 6.3.1 | Varmista, että kaikki pakettienhallintaohjelmat noudattavat version lukitsemista lukitustiedostojen avulla.                            |   1   | D/V  |
| 6.3.2 | Varmista, että konttiviittauksissa käytetään muuttumattomia tiivisteitä muutettavien tunnisteiden sijaan.                              |   1   | D/V  |
| 6.3.3 | Varmista, että toistettavat rakennustarkistukset vertailevat hajautusarvoja CI-ajojen välillä identtisten tulosteiden varmistamiseksi. |   2   |  D   |
| 6.3.4 | Varmista, että koontivahvistukset säilytetään 18 kuukautta auditointijäljityksen varmistamiseksi.                                      |   2   |  V   |
| 6.3.5 | Varmista, että vanhentuneet kirjastot laukaisevat automaattiset PR-pyynnöt päivittämään tai haaroittamaan kiinnitetyt versiot.         |   3   |  D   |

---

## C6.4 Luotetun lähteen valvonta

Salli artefaktien lataukset vain kryptografisesti varmennetuista, organisaation hyväksymistä lähteistä ja estä kaikki muu.

|   #   | Description                                                                                                                                             | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 6.4.1 | Varmista, että mallipainot, tietojoukot ja säiliöt ladataan vain hyväksytyistä toimialueista tai sisäisistä rekistereistä.                              |   1   | D/V  |
| 6.4.2 | Varmista, että Sigstore/Cosign-allekirjoitukset vahvistavat julkaisijan henkilöllisyyden ennen kuin artefaktit tallennetaan paikallisesti välimuistiin. |   1   | D/V  |
| 6.4.3 | Varmista, että egres-proksit estävät todennuksettomat artefaktin lataukset luotettavan lähdepolitiikan noudattamiseksi.                                 |   2   |  D   |
| 6.4.4 | Varmista, että repositorioluettelot tarkistetaan neljännesvuosittain, ja jokaisesta merkinnästä on liiketoiminnallinen perustelu.                       |   2   |  V   |
| 6.4.5 | Varmista, että käytäntöjen rikkomukset aiheuttavat artefaktien karanteenin ja riippuvaisten putkistojen ajojen palautuksen.                             |   3   |  V   |

---

## C6.5 Kolmannen osapuolen aineistojen riskiarviointi

Arvioi ulkoiset datasetit myrkyllisyyden, harhan ja lainmukaisuuden osalta, ja seuraa niitä koko niiden elinkaaren ajan.

|   #   | Description                                                                                                                             | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 6.5.1 | Varmista, että ulkoiset tietoaineistot käyvät läpi myrkytysriskin arvioinnin (esim. datan sormenjälkitunnistus, poikkeamien tunnistus). |   1   | D/V  |
| 6.5.2 | Varmista, että puolueellisuusmittarit (demografinen yhdenvertaisuus, yhtäläinen mahdollisuus) lasketaan ennen datan hyväksymistä.       |   1   |  D   |
| 6.5.3 | Varmista, että tietojoukkeiden alkuperä- ja lisenssiehdot on tallennettu ML‑BOM‑merkintöihin.                                           |   2   |  V   |
| 6.5.4 | Varmista, että säännöllinen seuranta havaitsee harhailun tai korruption isännöidyissä tietojoukoissa.                                   |   2   |  V   |
| 6.5.5 | Varmista, että kielletty sisältö (tekijänoikeudet, henkilötiedot) poistetaan automatisoidulla puhdistuksella ennen koulutusta.          |   3   |  D   |

---

## C6.6 Toimitusketjun hyökkäysten seuranta

Havaitse toimitusketjun uhkat varhaisessa vaiheessa CVE-syötteiden, tarkastuslokianalytiikan ja red team -simulaatioiden avulla.

|   #   | Description                                                                                                                                                    | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 6.6.1 | Varmista, että CI/CD:n auditointilokit virtaavat SIEM-järjestelmään, jotta voidaan havaita epäilyttävät pakettien hakutapahtumat tai muokatut rakennusvaiheet. |   1   |  V   |
| 6.6.2 | Varmista, että häiriötilanteiden vastausohjeissa on mukana peruutusmenettelyt vaarantuneille malleille tai kirjastoille.                                       |   2   |  D   |
| 6.6.3 | Varmista, että uhkatiedon rikastustunnisteet merkitsevät koneoppimiseen liittyviä indikaattoreita (esim. mallin myrkytyksen IoC:t) hälytyksen käsittelyssä.    |   3   |  V   |

---

## C6.7 ML‑BOM mallin artefakteille

Luo ja allekirjoita yksityiskohtaiset koneoppimiseen (ML) liittyvät ohjelmistokomponenttien koostumustiedot (ML-BOMit), jotta jälkikäyttäjät voivat vahvistaa komponenttien eheyden käyttöönoton yhteydessä.

|   #   | Description                                                                                                                              | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 6.7.1 | Varmista, että jokainen mallin artefakti julkaisee ML-BOM:n, joka luettelee aineistot, painot, hyperparametrit ja lisenssit.             |   1   | D/V  |
| 6.7.2 | Varmista, että ML‑BOM:n luonti ja Cosign-allekirjoitus on automatisoitu CI:ssä ja pakollisia yhdistämiselle.                             |   1   | D/V  |
| 6.7.3 | Varmista, että ML‑BOM:n täydellisyystarkistukset keskeyttävät rakennuksen, jos jokin komponentin metatiedoista (hash, lisenssi) puuttuu. |   2   |  D   |
| 6.7.4 | Varmista, että alavirran käyttäjät voivat kyselyttää ML-BOM:ia API:n kautta validoidakseen tuodut mallit käyttöönottohetkellä.           |   2   |  V   |
| 6.7.5 | Varmista, että ML-BOM:t ovat versiohallinnassa ja eroteltu muutosten havaitsemiseksi luvattomista muokkauksista.                         |   3   |  V   |

---

## Viitteet

* [ML Supply Chain Compromise – MITRE ATLAS](https://misp-galaxy.org/mitre-atlas-attack-pattern/)
* [Supply‑chain Levels for Software Artifacts (SLSA)](https://slsa.dev/)
* [CycloneDX – Machine Learning Bill of Materials](https://cyclonedx.org/capabilities/mlbom/)
* [What is Data Poisoning? – SentinelOne](https://www.sentinelone.com/cybersecurity-101/cybersecurity/data-poisoning/)
* [Transfer Learning Attack – OWASP ML Security Top 10](https://owasp.org/www-project-machine-learning-security-top-10/docs/ML07_2023-Transfer_Learning_Attack)
* [AI Data Security Best Practices – CISA](https://www.cisa.gov/news-events/cybersecurity-advisories/aa25-142a)
* [Secure CI/CD Supply Chain – Sumo Logic](https://www.sumologic.com/blog/secure-azure-devops-github-supply-chain-attacks)
* [AI & Transparency: Protect ML Models – ReversingLabs](https://www.reversinglabs.com/blog/ai-and-transparency-how-ml-model-creators-can-protect-against-supply-chain-attacks)
* [SBOM Overview – CISA](https://www.cisa.gov/sbom)
* [Training Data Poisoning Guide – Lakera.ai](https://www.lakera.ai/blog/training-data-poisoning)
* [Dependency Pinning for Reproducible Python – Medium](https://medium.com/data-science-collective/guarantee-a-locked-reproducible-environment-with-every-python-run-c0e2bf19fb53)

