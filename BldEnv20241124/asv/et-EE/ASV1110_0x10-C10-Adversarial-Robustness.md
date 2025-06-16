# 10 Vastupanuvõime vastastele ja privaatsuskaitse

## Kontrolli Eesmärk

Tagada, et tehisintellekti mudelid jääksid usaldusväärseks, privaatsust kaitsvaiks ja väärkasutuse vastu vastupidavaks, kui nad seisavad silmitsi möödapääsu-, järeldus-, väljavõtmise või mürgitusrünnakutega.

---

## 10.1 Mudeli joondamine ja turvalisus

Kaitske kahjulike või poliitikareegleid rikkunud väljundite eest.

|   #    | Description                                                                                                                                                                         | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 10.1.1 | Kontrollige, et joondamise testkomplekt (punatiimi päringud, piirangute ületamise katsed, keelatud sisu) oleks versioonihalduses ja seda käitatakse iga mudeli väljaandmise korral. |   1   | D/V  |
| 10.1.2 | Kontrolli, et keeldumise ja turvalise lõpuleviimise kaitsepiirded oleksid rakendatud.                                                                                               |   1   |  D   |
| 10.1.3 | Kinnitage, et automaatne hindaja mõõdab kahjuliku sisu määra ja märgistab regressioonid, mis ületavad kindlaksmääratud läve.                                                        |   2   | D/V  |
| 10.1.4 | Kinnitage, et vastujalajailbreaki koolitus on dokumenteeritud ja reprodutseeritav.                                                                                                  |   2   |  D   |
| 10.1.5 | Kinnitage, et ametlikud poliitikavajadusega vastavus- või sertifitseeritud järelevalve tõendid hõlmavad kriitilisi valdkondi.                                                       |   3   |  V   |

---

## 10.2 Vastandnäidete tugevdamine

Suurendage vastupanuvõimet manipuleeritud sisendite suhtes. Praegu on parimaks praktika tugev vastastikune treenimine ja võrdlusmõõdikute skoorimine.

|   #    | Description                                                                                                                                     | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 10.2.1 | Kontrollige, et projekti hoidlate hulka kuuluksid vastandtreeningu konfiguratsioonid korduvtäpsete seemnetega.                                  |   1   |  D   |
| 10.2.2 | Kinnitage, et võõrkeha-näidiste tuvastamine tekitab tootmisliinides blokeerimishoiatusi.                                                        |   2   | D/V  |
| 10.2.4 | Kontrollige, et sertifitseeritud vastupidavuse tõestused või intervall-piirangute sertifikaadid hõlmaksid vähemalt kõige kriitilisemad klassid. |   3   |  V   |
| 10.2.5 | Kontrollige, et regressioonitestid kasutaksid adaptiivseid rünnakuid, et kinnitada, et mõõdetavat vastupidavuse kadu ei esine.                  |   3   |  V   |

---

## 10.3 Kuulumisjärelduste leevendamine

Piira võimalust otsustada, kas kirje kuulus treeningandmetesse. Diferentsiaalne privaatsus ja usalduskoori varjamine jäävad kõige tõhusamateks teadaolevateks kaitsemeetoditeks.

|   #    | Description                                                                                                            | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 10.3.1 | Kontrollige, kas päringu-põhine entroopia regulaarsus või temperatuuri skaleerimine vähendab ülehinnatud prognoose.    |   1   |  D   |
| 10.3.2 | Kinnitage, et treening kasutab tundlike andmekogude puhul ε-piiratud diferentsiaalselt privaatset optimeerimist.       |   2   |  D   |
| 10.3.3 | Kinnitage, et rünnakute simulatsioonid (varjude mudel või must kast) näitavad rünnaku AUC ≤ 0,60 hoitaval andmestikul. |   2   |  V   |

---

## 10.4 Mudeli pöördvõrdluse vastupidavus

Takistage privaatsete atribuutide rekonstrueerimist. Hiljutised uuringud rõhutavad väljundi lühendamist ja differentiaalse privaatsuse (DP) garanteeringuid praktiliste kaitsemeetmetena.

|   #    | Description                                                                                                                               | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 10.4.1 | Kinnitage, et tundlikud atribuudid ei ole kunagi otseselt väljundis; vajadusel kasutage segmentideks jagamist või ühepoolseid teisendusi. |   1   |  D   |
| 10.4.2 | Kinnitage, et päringu sageduse piirangud piiravad korduvaid kohanduvaid päringuid samalt isikult.                                         |   1   | D/V  |
| 10.4.3 | Kinnitage, et mudelit on koolitatud privaatsust säilitava müraga.                                                                         |   2   |  D   |

---

## 10.5 Mudeli-ekstraktsiooni kaitse

Avasta ja tõkesta volitamata kloonimine. Soovitatavad on vesimärgendus ja päringu-mustri analüüs.

|   #    | Description                                                                                                                                                       | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 10.5.1 | Kontrollige, kas järeldustele suunatud väravad rakendavad mudeli meeldejätmise künnisele kohandatud globaalset ja iga API-võtme kohta kehtivat päringupiirangut.  |   1   |  D   |
| 10.5.2 | Kinnitage, et päringu entroopia ja sisendi mitmuse statistika toidavad automatiseeritud ekstraktsiooni tuvastajat.                                                |   2   | D/V  |
| 10.5.3 | Kontrollige, kas habraste või tõenäosuslike vesimärkide tõestamine on võimalik p < 0,01 juures kuni 1000 päringu korral kahtlustatava klooni vastu.               |   2   |  V   |
| 10.5.4 | Kinnitage, et veekohatuse võtmed ja käivitussätted on salvestatud riistvaraturvamoodulisse ning neid vahetatakse kord aastas.                                     |   3   |  D   |
| 10.5.5 | Kontrollige, et ekstraktsiooni-hoiatuse sündmused sisaldaksid rikkumisi tekitavaid päringuid ning oleksid integreeritud intsidentidele reageerimise töökäikudega. |   3   |  V   |

---

## 10.6 Järeldusaja mürgitatud andmete tuvastamine

Tuvastage ja neutraliseerige tagasiukse või mürgitatud sisendid.

|   #    | Description                                                                                                                              | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 10.6.1 | Kontrollige, et sisendid läbiksid enne mudeli järeldamist anomaaliatuvastuse (nt STRIP, järjepidevuse skoorimine).                       |   1   |  D   |
| 10.6.2 | Kinnitage, et detektori läved on häälestatud puhtal/mürgitatud valideerimiskogumil, et saavutada vähem kui 5% valepositiivseid tulemusi. |   1   |  V   |
| 10.6.3 | Kinnitage, et mürgitatud sisendid käivitavad pehme blokeerimise ja inimeste ülevaatuse töövood.                                          |   2   |  D   |
| 10.6.4 | Veenduge, et detektoreid testitakse koormuse all kohanduvate, vallandamiseta tagaukse rünnakutega.                                       |   2   |  V   |
| 10.6.5 | Kontrollige, et tuvastuse efektiivsuse mõõdikud oleksid logitud ja perioodiliselt uuesti hinnatud värske ohuinfoga.                      |   3   |  D   |

---

## 10.7 Dünaamiline turvapoliitika kohandamine

Reaalajas turvapoliitika uuendused, mis põhinevad ohuteabel ja käitumisanalüüsil.

|   #    | Description                                                                                                                                                              | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 10.7.1 | Kinnitage, et turvapoliitikaid saab dünaamiliselt uuendada ilma agendi taaskäivitamiseta, säilitades samal ajal poliitika versiooni terviklikkuse.                       |   1   | D/V  |
| 10.7.2 | Kontrollige, et poliitikauuendused oleksid krüptograafiliselt allkirjastatud volitatud turvapersonalide poolt ning valideeritud enne rakendamist.                        |   2   | D/V  |
| 10.7.3 | Kinnitage, et dünaamilised poliitikamuudatused logitakse täielikult auditeerimisjälgedega, mis sisaldavad põhjendusi, heakskiidetihedusi ja tagasipööramise protseduure. |   2   | D/V  |
| 10.7.4 | Kinnitage, et kohanduvad turvamehhanismid reguleerivad ohu tuvastamise tundlikkust vastavalt riski kontekstile ja käitumismustritele.                                    |   3   | D/V  |
| 10.7.5 | Kinnitage, et poliitikate kohandamise otsused on seletatavad ja sisaldavad turvameeskonna ülevaatamiseks tõendusjälgi.                                                   |   3   | D/V  |

---

## 10.8 Peegeldusel põhinev turvalisuse analüüs

Turvalisuse valideerimine agendi enesereflektsiooni ja metakognitiivse analüüsi kaudu.

|   #    | Description                                                                                                                                 | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 10.8.1 | Kinnitage, et agendi peegeldusmehhanismid hõlmavad otsuste ja tegevuste turvalisusele keskenduvat enesehindamist.                           |   1   | D/V  |
| 10.8.2 | Kontrollige, et peegeldusväljundid oleksid valideeritud, et takistada ründajate sisendite poolt enesehindamismehhanismide manipuleerimist.  |   2   | D/V  |
| 10.8.3 | Kinnitage, et metakognitiivne turvaanalüüs tuvastab potentsiaalse kallutatuse, manipulatsiooni või kompromisse agendi mõtlemisprotsessides. |   2   | D/V  |
| 10.8.4 | Kinnitage, et peegelduse-põhised turvahoiatused käivitavad täiustatud jälgimise ja võimaliku inimsekkumise töövoo.                          |   3   | D/V  |
| 10.8.5 | Kinnitage, et pidev õppimine turvakokkuvõtetest parandab ohtude tuvastamist ilma legitiimset funktsionaalsust kahjustamata.                 |   3   | D/V  |

---

## 10.9 Evolutsioon ja enesetäiustamise turvalisus

Turvakontrollid agentide süsteemidele, mis suudavad iseennast muuta ja areneda.

|   #    | Description                                                                                                                                   | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 10.9.1 | Kinnitage, et enesemuutmisvõimed on piiratud määratud turvaliste aladega, millel on formaalsed verifikatsioonipiirid.                         |   1   | D/V  |
| 10.9.2 | Veenduge, et evolutsiooniplaanid läbiksid turvahindamise enne rakendamist.                                                                    |   2   | D/V  |
| 10.9.3 | Kinnitage, et enesetäiendamise mehhanismid sisaldavad tagasikerimise võimalusi koos terviklikkuse kontrolliga.                                |   2   | D/V  |
| 10.9.4 | Kinnitage, et metauuringu turvalisus takistab täiustamisalgoritmide vastandlikku manipuleerimist.                                             |   3   | D/V  |
| 10.9.5 | Kontrollige, et rekursiivne enesetäiendus oleks piiratud formaalsete ohutuspiirangutega koos matemaatiliste kinnitusetega konvergentsi kohta. |   3   | D/V  |

---

### Viited

* [MITRE ATLAS adversary tactics for ML](https://atlas.mitre.org/)
* [NIST AI Risk Management Framework 1.0, 2023](https://nvlpubs.nist.gov/nistpubs/ai/nist.ai.100-1.pdf)
* [OWASP Top 10 for LLM Applications, 2025](https://owasp.org/www-project-top-10-for-large-language-model-applications/)
* [Adversarial Training: A Survey — Zhao et al., 2024](https://arxiv.org/abs/2410.15042)
* [RobustBench adversarial-robustness benchmark](https://robustbench.github.io/)
* [Membership-Inference & Model-Inversion Risk Survey, 2025](https://www.sciencedirect.com/science/article/abs/pii/S0950705125003867)
* [PURIFIER: Confidence-Score Defense against MI Attacks — AAAI 2023](https://ojs.aaai.org/index.php/AAAI/article/view/26289)
* [Model-Inversion Attacks & Defenses Survey — AI Review, 2025](https://link.springer.com/article/10.1007/s10462-025-11248-0)
* [Comprehensive Defense Framework Against Model Extraction — IEEE TDSC 2024](https://doi.org/10.1109/TDSC.2023.3261327)
* [Fragile Model Watermarking Survey — 2025](https://www.sciencedirect.com/science/article/abs/pii/S0165168425002026)
* [Data Poisoning in Deep Learning: A Survey — Zhao et al., 2025](https://arxiv.org/abs/2503.22759)
* [BDetCLIP: Multimodal Prompting Backdoor Detection — Niu et al., 2024](https://arxiv.org/abs/2405.15269)

