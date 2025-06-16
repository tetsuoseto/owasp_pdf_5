# C6 Tarneahela turvalisus mudelite, raamistikude ja andmete jaoks

## Kontrolli eesmärk

Tehisintellekti tarneahela rünnakud kasutavad ära kolmandate osapoolte mudeleid, raamistikke või andmekogumeid, et peita tagauksed, kallutatus või ärakasutatav kood. Need kontrollid tagavad mudeli kogu elutsükli ulatuses päritolu jälgimise, haavatavuste haldamise ja järelevalve.

---

## C6.1 Eeltreenitud mudeli kontrollimine ja päritolu

Hinnake ja autentige kolmanda osapoole mudelite päritolu, litsentsid ja peidetud käitumismustrid enne nende täiendõpet või kasutusele võtmist.

|   #   | Description                                                                                                                                          | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 6.1.1 | Kontrolli, et iga kolmanda osapoole mudeli artefakt sisaldab allkirjastatud päritolu kirjet, mis identifitseerib lähtekoodi hoidla ja commit hash'i. |   1   | D/V  |
| 6.1.2 | Kinnitage, et mudelid kontrollitakse pahatahtlike kihtide või Trooja päästikute suhtes, kasutades automatiseritud tööriistu enne importi.            |   1   | D/V  |
| 6.1.3 | Kinnitage, et ülekandeõppe peenhäälestus läbib vastupanuhindamise, et avastada varjatud käitumist.                                                   |   2   |  D   |
| 6.1.4 | Kontrollige, et mudeli litsentsid, ekspordijuhtimise märgendid ja andmete päritolu avaldused oleksid registreeritud ML-BOM kirjes.                   |   2   |  V   |
| 6.1.5 | Kontrollige, et kõrge riskiga mudelid (avalikult üles laaditud kaalud, kinnitamata loojad) jäävad inimkontrolli ja kinnitamiseni karantiini.         |   3   | D/V  |

---

## C6.2 Raamistiku ja teegiskaneerimine

Jätkuvalt skaneerida ML raamistikke ja raamatukogusid CVE-de ning pahatahtliku koodi suhtes, et hoida käitamisvirnastik turvalisena.

|   #   | Description                                                                                                                                   | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 6.2.1 | Kinnitage, et CI torujuhtmed käivitavad sõltuvusskannerid tehisintellekti raamistikudel ja kriitilistel teekidel.                             |   1   | D/V  |
| 6.2.2 | Kinnitage, et kriitilised haavatavused (CVSS ≥ 7.0) takistavad tootmispiltide edasiliikumist.                                                 |   1   | D/V  |
| 6.2.3 | Kinnitage, et staatiline koodi analüüs käivitatakse forkitud või kaasa pakitud ML-teekide peal.                                               |   2   |  D   |
| 6.2.4 | Kontrollige, et raamistikuuuenduse ettepanekutes oleks turvaalane mõjuhindamine, mis viitab avalikele CVE andmevoogudele.                     |   2   |  V   |
| 6.2.5 | Kinnitage, et käitamisajal olevad andurid annavad teada ootamatutest dünaamiliste teekide laadimistest, mis erinevad allkirjastatud SBOM-ist. |   3   |  V   |

---

## C6.3 Sõltuvuste fikseerimine ja kinnitamine

Kinnita kõik sõltuvused muutumatutele digesti väärtustele ja taasta ehitused, et tagada identsed, manipuleerimiskindlad artefaktid.

|   #   | Description                                                                                                                      | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 6.3.1 | Kontrollige, et kõik pakihaldurid rakendaksid versioonide fikseerimist lukustusfailide kaudu.                                    |   1   | D/V  |
| 6.3.2 | Kontrollige, et konteineriviidetes kasutatakse muutumatuid räsi väärtusi muutuvate siltide asemel.                               |   1   | D/V  |
| 6.3.3 | Kinnitage, et reprodutseeritavate koostete kontrollid võrdlevad CI käivituste vahel räsi väärtusi, et tagada identsed väljundid. |   2   |  D   |
| 6.3.4 | Kinnitage, et ehituse tõendid säilitatakse auditijäljendatavuse tagamiseks 18 kuud.                                              |   2   |  V   |
| 6.3.5 | Kontrolli, et aegunud sõltuvused käivitaksid automatiseeritud pull-päringud (PR-id) versioonide uuendamiseks või püüdmiseks.     |   3   |  D   |

---

## C6.4 Usaldusväärse allika täitmine

Lubage artifaktide allalaadimist ainult krüptograafiliselt kinnitatud, organisatsiooni poolt heaks kiidetud allikatest ning blokeerige kõik muu.

|   #   | Description                                                                                                                                  | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 6.4.1 | Kontrollige, et mudeli kaalud, andmekogud ja konteinerid laaditakse alla ainult heakskiidetud domeenidest või sisemistest registritest.      |   1   | D/V  |
| 6.4.2 | Kinnitage, et Sigstore/Cosign allkirjad valideerivad väljaandja identiteedi enne, kui artefaktid kohalikult vahemällu salvestatakse.         |   1   | D/V  |
| 6.4.3 | Kinnitage, et väljaminevad proksid blokeerivad autentimata artefaktide allalaadimised, et rakendada usaldusväärse allika poliitikat.         |   2   |  D   |
| 6.4.4 | Kinnitage, et hoidla lubade nimekirjad vaadatakse läbi kord kvartalis koos ärilise põhjenduse tõendiga iga kirje kohta.                      |   2   |  V   |
| 6.4.5 | Kontrollige, et poliitikareeglite rikkumised põhjustavad artefaktide karantiini panemise ja sõltuvate torujuhtme käivituste tagasipööramise. |   3   |  V   |

---

## C6.5 Kolmanda osapoole andmekogu riskihindamine

Hinnake väliseid andmekogusid mürgituse, kallutatuse ja õigusnõuetele vastavuse osas ning jälgige neid kogu nende elutsükli vältel.

|   #   | Description                                                                                                                    | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 6.5.1 | Kinnitage, et väliseid andmekogumeid hinnatakse mürgitamise riski suhtes (nt andmesõrmejälgede loomine, äärmuste tuvastamine). |   1   | D/V  |
| 6.5.2 | Kinnitage, et kallutatuse mõõdikud (demograafiline pariteet, võrdne võimalus) arvutatakse enne andmekogu heakskiitu.           |   1   |  D   |
| 6.5.3 | Kinnitage, et andmekogumite päritolu ja litsentsitingimused on ML-BOM kirjetes dokumenteeritud.                                |   2   |  V   |
| 6.5.4 | Kinnitage, et perioodiline jälgimine tuvastab võõrustatud andmekogumites toimuvad kadumid või riknemised.                      |   2   |  V   |
| 6.5.5 | Kontrollige, et keelatud sisu (autoriõigus, isikuandmed) eemaldatakse enne koolitust automaatse puhastamise teel.              |   3   |  D   |

---

## C6.6 Tarneahela rünnakute jälgimine

Avastage tarneahela ohud varakult CVE andmeside, auditi-logianalüüsi ja punase meeskonna simulatsioonide kaudu.

|   #   | Description                                                                                                                                                 | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 6.6.1 | Kinnitage, et CI/CD auditeerimislogid voogavad SIEM-i tuvastustesse, et avastada ebatavalisi pakettide allalaadimisi või muudetud koostamisprotsessi samme. |   1   |  V   |
| 6.6.2 | Kinnitage, et intsidentidele reageerimise käsiraamatutes on olemas tagasipöördumise protseduurid kompromiteeritud mudelite või teekide puhul.               |   2   |  D   |
| 6.6.3 | Kinnitage, et ohuteabe rikastamise märgendid märgistavad ML-spetsiifilisi indikaatoreid (nt mudeli mürgitamise IoC-sid) häirete triieerimisel.              |   3   |  V   |

---

## C6.7 ML-BOM mudelimaterjalide jaoks

Genereeri ja allkirjasta üksikasjalikke masinaõppele spetsiifilisi tarkvara komponentide nimekirju (ML-BOMid), et allpool olevad kasutajad saaksid juurutamise ajal komponentide terviklikkust kontrollida.

|   #   | Description                                                                                                                            | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 6.7.1 | Veenduge, et iga mudeliartifakt avaldaks ML-BOM-i, mis sisaldab andmekogumeid, kaalusid, hüperparameetreid ja litsentse.               |   1   | D/V  |
| 6.7.2 | Kontrolli, et ML-BOM genereerimine ja Cosign allkirjastamine oleksid CI-s automatiseeritud ning nõutud ühinemiseks.                    |   1   | D/V  |
| 6.7.3 | Kinnitage, et ML-BOM täiuslikkuse kontrollid rikuvad ehituse, kui mõni komponendi metaandmetest (räsi, litsents) puudub.               |   2   |  D   |
| 6.7.4 | Kontrollige, et allpool olevad tarbijad saavad ML-BOM-e API kaudu pärida, et valideerida imporditud mudeleid juurutamise ajal.         |   2   |  V   |
| 6.7.5 | Kontrollige, et ML-BOM-e haldatakse versioonikontrolli all ja võrreldakse muudatuste tuvastamiseks volitamata muudatuste avastamiseks. |   3   |  V   |

---

## Viited

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

