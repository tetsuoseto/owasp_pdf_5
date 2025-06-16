# C6 Ellátási lánc biztonsága modellek, keretrendszerek és adatok esetében

## Ellenőrzési célkitűzés

Az AI ellátási lánc támadások kihasználják a harmadik féltől származó modelleket, keretrendszereket vagy adatállományokat hátsó ajtók, torzítások vagy kihasználható kód beágyazására. Ezek az ellenőrzések végponttól végpontig biztosítják az eredetiség nyomonkövetését, a sérülékenységek kezelését és a megfigyelést, hogy megvédjék az egész modell életciklusát.

---

## C6.1 Előre betanított modell átvilágítása és eredetellenőrzése

Értékelje és hitelesítse a harmadik fél modelljeinek eredetét, licencét és rejtett viselkedését bármilyen finomhangolás vagy telepítés előtt.

|   #   | Description                                                                                                                                                                                    | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 6.1.1 | Ellenőrizze, hogy minden harmadik fél modellartifaktum tartalmaz-e egy aláírt származási nyilatkozatot, amely azonosítja a forráskód-tárhelyet és a commit hash-t.                             |   1   | D/V  |
| 6.1.2 | Ellenőrizze, hogy a modelleket automatikus eszközökkel átvizsgálták-e káros rétegek vagy hátsóajtó aktiválók szempontjából az importálás előtt.                                                |   1   | D/V  |
| 6.1.3 | Ellenőrizze, hogy az átviteli tanulással finomhangolt modellek átmennek-e az ellenséges értékelésen a rejtett viselkedések felismeréséhez.                                                     |   2   |  D   |
| 6.1.4 | Ellenőrizni kell, hogy a modelllicencek, a kivitel-ellenőrzési címkék és az adatforrás-nyilatkozatok rögzítve vannak-e egy ML-BOM bejegyzésben.                                                |   2   |  V   |
| 6.1.5 | Ellenőrizze, hogy a magas kockázatú modellek (nyilvánosan feltöltött súlyok, nem ellenőrzött alkotók) karanténban maradnak-e addig, amíg emberi felülvizsgálat és jóváhagyás meg nem történik. |   3   | D/V  |

---

## C6.2 Keretrendszer- és Könyvtárvizsgálat

Folyamatosan vizsgálja az ML keretrendszereket és könyvtárakat CVE-k és rosszindulatú kódok után, hogy a futtatási környezet biztonságos maradjon.

|   #   | Description                                                                                                                               | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 6.2.1 | Ellenőrizze, hogy a CI-pipeline-ok futtatnak-e függőségvizsgálókat az AI-keretrendszereken és a kritikus könyvtárakon.                    |   1   | D/V  |
| 6.2.2 | Ellenőrizze, hogy a kritikus sebezhetőségek (CVSS ≥ 7,0) megakadályozzák-e a promóciót a gyártási képekhez.                               |   1   | D/V  |
| 6.2.3 | Ellenőrizze, hogy a statikus kódelemzés fut-e a fork-olt vagy beágyazott ML könyvtárakon.                                                 |   2   |  D   |
| 6.2.4 | Ellenőrizze, hogy a keretrendszer frissítési javaslatai tartalmazzák-e a nyilvános CVE adatfolyamokra hivatkozó biztonsági hatáselemzést. |   2   |  V   |
| 6.2.5 | Ellenőrizze, hogy a futásidejű érzékelők riasztanak-e az aláírt SBOM-tól eltérő váratlan dinamikus könyvtárbetöltések esetén.             |   3   |  V   |

---

## C6.3 Függőség rögzítése és ellenőrzése

Minden függőséget rögzíts változtathatatlan digesztként, és építsd újra a buildet az azonos, sértetlen artefaktumok garantálásához.

|   #   | Description                                                                                                                                            | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 6.3.1 | Ellenőrizze, hogy minden csomagkezelő érvényesíti-e a verziórögzítést zárolási fájlokon keresztül.                                                     |   1   | D/V  |
| 6.3.2 | Ellenőrizze, hogy a konténerhivatkozásokban módosíthatatlan címkék helyett módosíthatatlan lenyomatok (digestek) legyenek használva.                   |   1   | D/V  |
| 6.3.3 | Ellenőrizze, hogy az ismételhető build ellenőrzések összehasonlítják-e a hash-értékeket a CI futások között az azonos kimenetek biztosítása érdekében. |   2   |  D   |
| 6.3.4 | Ellenőrizze, hogy az építési tanúsítványok 18 hónapig tárolódnak-e az audit nyomkövethetőséghez.                                                       |   2   |  V   |
| 6.3.5 | Ellenőrizze, hogy a lejárt függőségek automatikus PR-eket váltanak-e ki a rögzített verziók frissítésére vagy elágaztatására.                          |   3   |  D   |

---

## C6.4 Megbízható Forrás Érvényesítése

Engedélyezze az artefaktumok letöltését csak kriptográfiailag ellenőrzött, szervezet által jóváhagyott forrásokból, és blokkoljon minden egyéb forrást.

|   #   | Description                                                                                                                                                   | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 6.4.1 | Ellenőrizze, hogy a modell súlyait, adatállományokat és tárolókat kizárólag jóváhagyott domainekről vagy belső regisztrációs helyekről töltik le.             |   1   | D/V  |
| 6.4.2 | Ellenőrizze, hogy a Sigstore/Cosign aláírások igazolják-e a kiadó személyazonosságát, mielőtt az artefaktumokat helyileg gyorsítótárazná.                     |   1   | D/V  |
| 6.4.3 | Ellenőrizze, hogy a kilépési proxyk blokkolják-e a nem hitelesített műtárgyletöltéseket a megbízható forrásokra vonatkozó szabályzat érvényesítése érdekében. |   2   |  D   |
| 6.4.4 | Ellenőrizze, hogy a tárház engedélyezési listáit negyedévente felülvizsgálják, üzleti indoklás igazolásával minden egyes bejegyzéshez.                        |   2   |  V   |
| 6.4.5 | Ellenőrizze, hogy a szabályzati megsértések kiváltják-e az artefaktumok elkülönítését és az egymásra épülő pipeline futások visszavonását.                    |   3   |  V   |

---

## C6.5 Harmadik fél adatbázis-kockázatértékelése

Értékelje a külső adathalmazokat mérgezés, elfogultság és jogi megfelelés szempontjából, és figyelje őket az egész élettartamuk alatt.

|   #   | Description                                                                                                                                     | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 6.5.1 | Ellenőrizze, hogy a külső adatállományokat megmérik-e mérgezés kockázatára (pl. adatujjlenyomat-készítés, kiugró értékek detektálása).          |   1   | D/V  |
| 6.5.2 | Ellenőrizze, hogy az elfogultsági mutatók (demográfiai egyenlőség, egyenlő esélyek) kiszámítása megtörténik-e az adatkészlet jóváhagyása előtt. |   1   |  D   |
| 6.5.3 | Ellenőrizze, hogy az adatállományok eredete és licencfeltételei rögzítve vannak-e az ML-BOM bejegyzésekben.                                     |   2   |  V   |
| 6.5.4 | Ellenőrizze, hogy a rendszeres monitorozás észleli-e az eltolódást vagy a sérülést a hosztolt adatállományokban.                                |   2   |  V   |
| 6.5.5 | Ellenőrizze, hogy a tiltott tartalom (szerzői jog, személyes adatok) automatikus tisztítással eltávolításra került-e a képzés előtt.            |   3   |  D   |

---

## C6.6 Ellátási lánc támadásfigyelés

A beszállítói lánc fenyegetéseinek korai észlelése CVE-hírcsatornák, audit-napló elemzések és piros csapat szimulációk segítségével.

|   #   | Description                                                                                                                                                          | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 6.6.1 | Ellenőrizze, hogy a CI/CD auditnaplók folyamatosan továbbítódnak-e a SIEM rendszerbe a rendellenes csomagletöltések vagy manipulált build lépések észlelésére.       |   1   |  V   |
| 6.6.2 | Ellenőrizze, hogy az incidenskezelési játékkönyvek tartalmazzák-e a visszagörgetési eljárásokat a sérült modellek vagy könyvtárak esetére.                           |   2   |  D   |
| 6.6.3 | Ellenőrizze, hogy a fenyegetés‑intelligencia gazdagító eszközök az ML‑specifikus indikátorokat (pl. modell‑mérgezési IoC-ket) címkézik‑e a riasztások szűrése során. |   3   |  V   |

---

## C6.7 ML‑BOM a modell artefaktumokhoz

Részletes, gépi tanulásra specifikus SBOM-okat (ML-BOM-okat) generáljon és írjon alá, hogy a későbbi felhasználók a telepítéskor ellenőrizhessék a komponensek integritását.

|   #   | Description                                                                                                                                             | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 6.7.1 | Ellenőrizze, hogy minden modell-artifaktum közzétesz-e egy ML-BOM-ot, amely felsorolja az adatállományokat, súlyokat, hiperparamétereket és licenceket. |   1   | D/V  |
| 6.7.2 | Ellenőrizze, hogy az ML-BOM generálása és a Cosign aláírás automatizált-e a CI-ben, és kötelező-e az egyesítéshez.                                      |   1   | D/V  |
| 6.7.3 | Ellenőrizze, hogy az ML‑BOM teljességi ellenőrzések sikertelenül leállítják-e a buildet, ha bármely komponens metaadata (hash, licenc) hiányzik.        |   2   |  D   |
| 6.7.4 | Ellenőrizze, hogy a végfelhasználók képesek-e az ML-BOM-ok lekérdezésére API-n keresztül az importált modellek telepítési időbeni érvényesítéséhez.     |   2   |  V   |
| 6.7.5 | Ellenőrizze, hogy az ML‑BOM-ok verziókövetettek és különbségvizsgálattal vannak ellenőrizve az engedély nélküli módosítások észlelésére.                |   3   |  V   |

---

## Hivatkozások

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

