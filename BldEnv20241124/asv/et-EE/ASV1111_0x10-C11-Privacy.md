# 11 Privaatsuskaitse ja isikuandmete haldamine

## Kontrolli eesmärk

Tagada rangelt privaatsuse järgimine kogu tehisintellekti elutsükli vältel — andmete kogumine, treenimine, järeldamine ja intsidentidele reageerimine — nii et isikuandmeid töödeldakse ainult selge nõusoleku, minimaalsete vajalike ulatuse, tõendatava kustutamise ja ametlike privaatsusgarantiide alusel.

---

## 11.1 Anonüümimine ja andmete minimeerimine

|   #    | Description                                                                                                                                           | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 11.1.1 | Kontrollige, et otsesed ja kvasi-identifikaatorid oleksid eemaldatud või räsi muudetud.                                                               |   1   | D/V  |
| 11.1.2 | Kinnitage, et automatiseeritud auditid mõõdavad k-anonüümsust/l-mitmekesisust ja annavad hoiatuse, kui läviväärtused langevad alla poliitika piiri.   |   2   | D/V  |
| 11.1.3 | Kinnitage, et mudeli tunnuse-tähtsuse aruanded tõendavad, et identifikaatori lekkimine ei ületa ε = 0,01 omavahelise informatsiooni taset.            |   2   |  V   |
| 11.1.4 | Kinnitage, et formaalsed tõestused või sünteetilise andmestiku sertifitseerimine näitavad ümber tuvastamise riski ≤ 0,05 isegi seoserünnakute korral. |   3   |  V   |

---

## 11.2 Õigus olla unustatud ja kustutamise tagamine

|   #    | Description                                                                                                                                                                                       | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 11.2.1 | Kontrollige, et andmesubjekti kustutamise päringud leviksid algandmekogudele, kontrollpunktidele, manustele, logidele ja varukoopiatele teenusetasemete kokkulepete raames, mis on alla 30 päeva. |   1   | D/V  |
| 11.2.2 | Kinnitage, et "masinõppe mahavõtmise" rutiinid teostavad füüsilist ümberõpet või ligikaudset eemaldamist sertifitseeritud unlearning-algoritmide abil.                                            |   2   |  D   |
| 11.2.3 | Kinnitage, et varjemudeli hindamine tõestab, et unustatud kirjed mõjutavad eemaldamise järel vähem kui 1% väljunditest.                                                                           |   2   |  V   |
| 11.2.4 | Kontrollige, et kustutussündmused oleksid muutumatult logitud ja regulaatoritele auditeeritavad.                                                                                                  |   3   |  V   |

---

## 11.3 Diferentsiaalturvalisuse kaitsed

|   #    | Description                                                                                                                 | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 11.3.1 | Kinnitage, et privaatsuskahjude arvestamise armatuurlauad annavad hoiatuse, kui kumulatiivne ε ületab poliitika piirmäärad. |   2   | D/V  |
| 11.3.2 | Kinnitage, et musta kasti privaatsusauditeerimine hindab ε̂ 10% ulatuses deklaratsioonis toodud väärtusest.                 |   2   |  V   |
| 11.3.3 | Kinnitage, et formaalsed tõestused hõlmavad kõiki koolitusejärgseid täiendavaid treeninguid ja manuseid.                    |   3   |  V   |

---

## 11.4 Eesmärgipiirang ja ulatuse laienemise kaitse

|   #    | Description                                                                                                                        | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 11.4.1 | Kinnitage, et iga andmekogum ja mudeli kontrollpunkt kannab masinloetavat eesmärgitähist, mis on kooskõlas algse nõusolekuga.      |   1   |  D   |
| 11.4.2 | Kinnitage, et käitamismonitoorid tuvastavad päringud, mis on vastuolus deklareeritud eesmärgiga, ning käivitavad pehme keeldumise. |   1   | D/V  |
| 11.4.3 | Kinnitage, et poliitika-koodi tõkked takistavad mudelite ümberpaigaldamist uutele domeenidele ilma DPIA ülevaatust läbi viimata.   |   3   |  D   |
| 11.4.4 | Kinnitage, et formaalsed jälgitavuse tõendid näitavad, et kogu isikuandmete elutsükkel jääb nõusolekuga määratletud ulatusse.      |   3   |  V   |

---

## 11.5 Nõusoleku haldamine ja õigusliku aluse jälgimine

|   #    | Description                                                                                                                  | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 11.5.1 | Kinnitage, et nõusolekuhalduse platvorm (CMP) salvestab andmesubjekti kohta opt-in staatuse, eesmärgi ja säilitamisperioodi. |   1   | D/V  |
| 11.5.2 | Kontrollige, et API-d avaldaksid nõusoleku märke; mudelid peavad enne ennustust kinnitama märgi ulatuse.                     |   2   |  D   |
| 11.5.3 | Kinnitage, et keeldumine või tagasivõtmine peatab andmetöötlusprotsessid 24 tunni jooksul.                                   |   2   | D/V  |

---

## 11.6 Föderaalse õppe privaatsuse kontrollidega

|   #    | Description                                                                                                              | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 11.6.1 | Kontrollige, et kliendiuuendused kasutaksid kogumiseelselt lokaalset diferentsiaalset privaatsusmehhanismi müralisamist. |   1   |  D   |
| 11.6.2 | Kinnitage, et koolitusmõõdikud on diferentsiaalselt privaatsed ega avalikusta kunagi ühe kliendi kaotust.                |   2   | D/V  |
| 11.6.3 | Kontrollige, et mürgistuskindel agregatsioon (nt Krum/Trimmed-Mean) oleks lubatud.                                       |   2   |  V   |
| 11.6.4 | Kinnitage, et formaalsed tõestused näitavad kogu ε eelarvet kaotusega väiksem kui 5 kasutustasemel.                      |   3   |  V   |

---

### Viited

* [GDPR & AI Compliance Best Practices](https://www.exabeam.com/explainers/gdpr-compliance/the-intersection-of-gdpr-and-ai-and-6-compliance-best-practices/)
* [EU Parliament Study on GDPR & AI, 2020](https://www.europarl.europa.eu/RegData/etudes/STUD/2020/641530/EPRS_STU%282020%29641530_EN.pdf)
* [ISO 31700-1:2023 — Privacy by Design for Consumer Products](https://www.iso.org/standard/84977.html)
* [NIST Privacy Framework 1.1 (2025 Draft)](https://www.nist.gov/privacy-framework)
* [Machine Unlearning: Right-to-Be-Forgotten Techniques](https://www.kaggle.com/code/tamlhp/machine-unlearning-the-right-to-be-forgotten)
* [A Survey of Machine Unlearning, 2024](https://arxiv.org/html/2209.02299v6)
* [Auditing DP-SGD — ArXiv 2024](https://arxiv.org/html/2405.14106v4)
* [DP-SGD Explained — PyTorch Blog](https://medium.com/pytorch/differential-privacy-series-part-1-dp-sgd-algorithm-explained-12512c3959a3)
* [Purpose-Limitation for AI — IJLIT 2025](https://academic.oup.com/ijlit/article/doi/10.1093/ijlit/eaaf003/8121663)
* [Data-Protection Considerations for AI — URM Consulting](https://www.urmconsulting.com/blog/data-protection-considerations-for-artificial-intelligence-ai)
* [Top Consent-Management Platforms, 2025](https://www.enzuzo.com/blog/best-consent-management-platforms)
* [Secure Aggregation in DP Federated Learning — ArXiv 2024](https://arxiv.org/abs/2407.19286)

