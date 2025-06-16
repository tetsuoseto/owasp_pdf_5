# C2 kasutajasisendi valideerimine

## Juhtimise Eesmärk

Tugev kasutajasisestuse valideerimine on esmane kaitsejoon mõnede kõige kahjulikumate rünnakute vastu AI süsteemide vastu. Käskluste sisestamise rünnakud võivad üle kirjutada süsteemi juhised, lekkida tundlikke andmeid või suunata mudelit lubamatu käitumise poole. Kui spetsiaalsed filtrid ja juhiste hierarhiad puuduvad, näitab teadustöö, et pikale kontekstile võimenduvad "multi-shot" jailbreak rünnakud on tõhusad. Samuti võivad peened vasturünnakud—näiteks homoglüüfi vahetused või leetspeak—vaikselt muuta mudeli otsuseid.

---

## C2.1 Prompt-süstimise kaitse

Promptsüsti on üks peamisi riske tehisintellekti süsteemide jaoks. Sellise taktika vastu kaitsmiseks kasutatakse staatiliste mustrifiltrite, dünaamiliste klassifikaatorite ja juhiste hierarhia rakendamise kombinatsiooni.

|   #   | Description                                                                                                                                                                                                 | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 2.1.1 | Kontrollige, et kasutaja sisendid läbiksid pidevalt uuendatava tuntud prompti süstimise mustrite (vanglakoodi märksõnad, "ignore previous", rollimänguahelad, kaudsed HTML/URL rünnakud) vastase sõelumise. |   1   | D/V  |
| 2.1.2 | Kinnitage, et süsteem rakendab juhiste hierarhiat, kus süsteemi või arendaja sõnumid on kasutaja juhistest kõrgemad, isegi pärast kontekstiakna laiendamist.                                                |   1   | D/V  |
| 2.1.3 | Kinnitage, et vastasehindamise testid (nt Red Team "palju-korral" käsud) viiakse läbi enne iga mudeli või käsukujunduse avaldamist, edukuse künniste ja regressioonide automaatse takistussüsteemiga.       |   2   | D/V  |
| 2.1.4 | Kinnitage, et kolmandate osapoolte sisust (veebilehed, PDF-id, e-kirjad) pärinevad promptid puhastatakse isoleeritud parsimiskontekstis enne, kui need põhiprompti hulka ühendatakse.                       |   2   |  D   |
| 2.1.5 | Kontrollige, et kõik prompt-filtri reeglite uuendused, klassifikaatormudeli versioonid ja blokeerimisnimekirja muudatused oleksid versioonihalduses ja auditeeritavad.                                      |   3   | D/V  |

---

## C2.2 Vastaseltnäidete vastupanuvõime

Loodusliku keele töötlemise (NLP) mudelid on endiselt haavatavad peente tähe- või sõnetasandiliste häirete suhtes, mida inimesed sageli ei märka, kuid mida mudelid kipuvad valesti klassifitseerima.

|   #   | Description                                                                                                                                                                                                            | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 2.2.1 | Kinnitage, et põhisisendi normaliseerimise sammud (Unicode NFC, homoglüüfi kaardistamine, tühikute kärpimine) toimuvad enne tokeniseerimist.                                                                           |   1   |  D   |
| 2.2.2 | Kinnitage, et statistiline anomaaliate tuvastamine märgistab sisendid, millel on ebatavaliselt kõrge redigeerimiskaugus keelenormidest, liigne korduvate tokenite esinemine või ebanormaalsed sisutõlgenduse kaugused. |   2   | D/V  |
| 2.2.3 | Kinnitage, et järelduskanal toetab valikulisi vastuolulise treeninguga tugevdunud mudelivariandid või kaitsekihid (nt juhuslikustamine, kaitsev destilleerimine) kõrge riskiga lõpp-punktide jaoks.                    |   2   |  D   |
| 2.2.4 | Veenduge, et kahtlustatavad vaenulikud sisendid oleksid karantiinis, logitud koos täielike andmepakettidega (pärast isikuandmete eemaldamist).                                                                         |   2   |  V   |
| 2.2.5 | Kontrolli, et tugevusmõõdikuid (tuntud ründe komplektide õnnestumismäära) jälgitakse aja jooksul ning regressioonid põhjustavad väljalaske blokeerija käivitamise.                                                     |   3   | D/V  |

---

## C2.3 Skeemi, tüübi ja pikkuse valideerimine

AI rünnakud, kus esitatakse valesti vormistatud või liiga suuri sisendeid, võivad põhjustada parsimisvigu, käskude lekkimist väljade vahel ja ressursside ammendumist. Ranget skeemi järgimist nõutakse ka deterministlike tööriistakutsete teostamisel.

|   #   | Description                                                                                                                                                                                               | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 2.3.1 | Kinnitage, et iga API või funktsioonikõne lõpp-punkt määratleb selgesõnalise sisendi skeemi (JSON Schema, Protobuf või multimodaalne ekvivalent) ning et sisendid valideeritakse enne päringu koostamist. |   1   |  D   |
| 2.3.2 | Kontrollige, et maksimaalse märksõna- või baitide piiri ületavad sisendid lükatakse tagasi turvalise veateatega ega kärbita vaikimisi.                                                                    |   1   | D/V  |
| 2.3.3 | Kontrollige, et tüübikontrollid (nt arvulised vahemikud, loendväljad, pildide/heli MIME-tüübid) oleksid rakendatud serveripoolselt, mitte ainult kliendipoolse koodi tasandil.                            |   2   | D/V  |
| 2.3.4 | Kontrollige, et semantilised valideerijad (nt JSON Schema) töötaksid konstantses ajas, et vältida algoritmilist DoS-rünnakut.                                                                             |   2   |  D   |
| 2.3.5 | Kinnitage, et valideerimisvead salvestatakse logi punaseeritud andmeosade ja ühemõtteliste veakoodidega, et hõlbustada turvalisuse klassifitseerimist.                                                    |   3   |  V   |

---

## C2.4 Sisu ja poliitika kontrollimine

Arendajad peaksid suutma tuvastada süntaktiliselt kehtivaid sisendeid, mis nõuavad keelatud sisu (näiteks ebaseaduslikke juhiseid, vihkamiskõnet ja autoriõigustega kaitstud teksti) ning seejärel takistama nende levikut.

|   #   | Description                                                                                                                                                                                                                   | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 2.4.1 | Kontrollige, et sisuklassifikaator (null-silm või peenhäälestatud) hindab iga sisendi vägivaldsuse, enesevigastamise, vihkamise, seksuaalse sisu ja ebaseaduslike päringute osas, kasutades konfigureeritavaid lävi väärtusi. |   1   |  D   |
| 2.4.2 | Kinnitage, et poliitikate rikkumisega sisendid saavad standardiseeritud keeldumised või turvalised lõpetamised, et need ei leviks alluvatesse LLM-kõnedesse.                                                                  |   1   | D/V  |
| 2.4.3 | Kontrollige, et filtreerimismudel või reeregist on uuendatud või ümberõpetatud vähemalt kord kvartalis, kaasates uued täheldatud läbimurdmis- või poliitikast kõrvalehiilimise mustrid.                                       |   2   |  D   |
| 2.4.4 | Kontrollige, et sõeluuring austaks kasutajapõhiseid poliitikaid (vanus, piirkondlikud juriidilised piirangud) atribuutidel põhinevate reeglite kaudu, mis lahendatakse taotluse esitamise ajal.                               |   2   |  D   |
| 2.4.5 | Kontrollige, et sõeluuringu logides oleksid olemas klassifikaatori usaldusmäära skoorid ja poliitikakategooria sildid SOC seostamiseks ning tulevase red-team analüüsi jaoks.                                                 |   3   |  V   |

---

## C2.5 Sisendi kiiruse piiramine ja kuritarvituste ennetamine

Arendajad peaksid takistama väärkasutust, ressursikulu tühjenemist ja automatiseeritud rünnakuid tehisintellekti süsteemide vastu, piirates sisendi mahtu ja tuvastades ebanormaalseid kasutusmustreid.

|   #   | Description                                                                                                                                                                    | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 2.5.1 | Kontrollige, et kasutajapõhised, IP-aadressipõhised ja API-võtme põhised kiirusepiirangud oleksid kõigi sisendpunktide jaoks kehtestatud.                                      |   1   | D/V  |
| 2.5.2 | Kontrolli, et plahvatusliku ja pideva kiiruse piirangud oleksid häälestatud nii, et need takistaksid teenusetõkestus- (DoS) ja jõurünnakuid.                                   |   2   | D/V  |
| 2.5.3 | Kontrollige, et ebatavalised kasutusmustrid (nt kiirete järjestikuste päringute esitamine, sisendi üleujutamine) käivitaksid automatiseeritud blokeeringud või eskaleerimised. |   2   | D/V  |
| 2.5.4 | Kinnitage, et väärkasutuse ennetamise logid säilitatakse ja neid vaadatakse läbi tekkivate ründe mustrite tuvastamiseks.                                                       |   3   |  V   |

---

## C2.6 Mitme modaaliga sisendi valideerimine

Tehisintellekti süsteemides tuleks rakendada tugevat valideerimist mitte-tekstuaalsete sisendite (pildid, heli, failid) jaoks, et vältida süstimist, vältimist või ressursside väärkasutust.

|   #   | Description                                                                                                                         | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 2.6.1 | Kinnitage, et kõik mittetekstilised sisendid (pildid, heli, failid) kontrollitakse tüübi, suuruse ja formaadi osas enne töötlemist. |   1   |  D   |
| 2.6.2 | Kontrollige, et failid oleksid enne sissetoomist pahavara ja steganograafiliste sisulastide suhtes skaneeritud.                     |   2   | D/V  |
| 2.6.3 | Kinnitage, et pildi/heli sisenditel kontrollitakse vaenulikke häireid või teadaolevaid ründe mustreid.                              |   2   | D/V  |
| 2.6.4 | Kontrollige, et mitme-modaalse sisendi valideerimisvead registreeritakse ja käivitavad uurimiseks hoiatused.                        |   3   |  V   |

---

## C2.7 Sisendi päritolu ja atribuutimine

AI-süsteemid peaksid toetama auditeerimist, väärkasutuse jälgimist ja vastavust, jälgides ja märgistades kõigi kasutajasisendite päritolu.

|   #   | Description                                                                                                                                 | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 2.7.1 | Kinnitage, et kõik kasutaja sisendid on vastuvõtmisel märgistatud metaandmetega (kasutajatunnus, sessioon, allikas, ajatempli, IP-aadress). |   1   | D/V  |
| 2.7.2 | Kinnitage, et päritolumetadata säilitatakse ja see on auditeeritav kõigi töödeldud sisendite puhul.                                         |   2   | D/V  |
| 2.7.3 | Kinnitage, et anomaalsed või usaldamatud sisendallikad märgistatakse ja allutatakse täiendavale järelevalvele või blokeerimisele.           |   2   | D/V  |

---

## C2.8 Reaalajas kohanduvate ohtude tuvastamine

Arendajad peaksid kasutama täiustatud ohutuvastussüsteeme tehisintellekti jaoks, mis kohanduvad uute ründe mustritega ja pakuvad reaalajas kaitset koos kompileeritud mustri sobitamisega.

|   #   | Description                                                                                                                                                                                  | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 2.8.1 | Kinnitage, et ohutuvastuse mustrid kompileeritakse optimeeritud regulaaravaldiste mootoritesse kõrge jõudlusega reaalajas filtreerimiseks, millel on minimaalne latentsusmõju.               |   1   | D/V  |
| 2.8.2 | Kinnitage, et ohu tuvastamise süsteemid hoiavad eraldi mustrite raamatukogusid erinevate ohu kategooriate jaoks (põhjusliku süstimise, kahjuliku sisu, tundlike andmete, süsteemikäskluste). |   1   | D/V  |
| 2.8.3 | Kinnitage, et adaptiivne ohu tuvastamine hõlmab masinõppemudeleid, mis uuendavad ohu tundlikkust rünnakute sageduse ja õnnestumismäärade põhjal.                                             |   2   | D/V  |
| 2.8.4 | Kinnitage, et reaalajas ohuteabe voogudes värskendatakse mustrikogusid automaatselt uute rünnakusignatuuride ja kompromisseerimismärkide (IOC-de) abil.                                      |   2   | D/V  |
| 2.8.5 | Kinnitage, et ohu tuvastamise valepositiivsete määrasid jälgitakse pidevalt ja mustri spetsiifilisust reguleeritakse automaatselt, et minimeerida seaduslike kasutusjuhtude häirimist.       |   3   | D/V  |
| 2.8.6 | Kinnitage, et kontekstuaalne ohuanalüüs arvestab sisendi allikat, kasutaja käitumismustreid ja sessiooni ajalugu, et parandada avastamise täpsust.                                           |   3   | D/V  |
| 2.8.7 | Kontrollige, et ohu tuvastamise jõudlusnäitajaid (tuvastussagedus, töötlemise latentsus, ressursikasutus) jälgitakse ja optimeeritakse reaalajas.                                            |   3   | D/V  |

---

## C2.9 Mitme-modaalne turvalisuse valideerimise torujuhe

Arendajad peaksid pakkuma turvakontrolli tekstile, pildile, heli- ja muudele tehisintellekti sisendimodaalsustele, kasutades konkreetseid ohutuvastuse meetodeid ja ressursside isoleerimist.

|   #   | Description                                                                                                                                                                                                                                                          | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 2.9.1 | Kinnitage, et iga sisendimodaalsus omab spetsiaalseid turvakontrollereid dokumenteeritud ohumustritega (tekst: käsurea süstimine, pildid: steganograafia, heli: spektrogrammi rünnakud) ja tuvastuskünnistega.                                                       |   1   | D/V  |
| 2.9.2 | Kontrollige, et mitmemoodilised sisendid töödeldakse isoleeritud liivakastides, millel on iga mooduli tüübi jaoks määratletud ressursipiirangud (mälu, protsessor, töötlemisaeg) ja mis on dokumenteeritud turvapoliitikates.                                        |   2   | D/V  |
| 2.9.3 | Kinnitage, et ristmeedia ründe tuvastamine avastab koordineeritud rünnakud, mis hõlmavad mitut sisutüüpi (nt piltides peidetud steganograafilised andmed koos tekstis tehtavate promptide süstimisega), kasutades korrelatsioonireegleid ja hoiatuste genereerimist. |   2   | D/V  |
| 2.9.4 | Kontrollige, et multimodaalsed valideerimisvead käivitaksid üksikasjaliku logimise, mis hõlmab kõiki sisendmoodulaid, valideerimistulemusi, ohuhindeid ja korrelatsioonianalüüsi, kasutades struktureeritud logivorminguid SIEM-integratsiooniks.                    |   3   | D/V  |
| 2.9.5 | Kinnitage, et modaalspetsiifilised sisuklassifikaatorid on värskendatud dokumenteeritud ajakava alusel (vähemalt kord kvartalis) uute ohu mustrite, vastandlike näidete ja jõudlusstandarditega, mis säilitavad taseme üle baasjoonte.                               |   3   | D/V  |

---

## Viited

* [LLM01:2025 Prompt Injection – OWASP Top 10 for LLM & Generative AI Security](https://genai.owasp.org/llmrisk/llm01-prompt-injection/)
* [Generative AI's Biggest Security Flaw Is Not Easy to Fix](https://www.wired.com/story/generative-ai-prompt-injection-hacking)
* [Many-shot jailbreaking \ Anthropic](https://www.anthropic.com/research/many-shot-jailbreaking)
* [$PDF$ OpenAI GPT-4.5 System Card](https://cdn.openai.com/gpt-4-5-system-card-2272025.pdf)
* [Notebook for the CheckThat Lab at CLEF 2024](https://ceur-ws.org/Vol-3740/paper-53.pdf)
* [Mitigate jailbreaks and prompt injections – Anthropic](https://docs.anthropic.com/en/docs/test-and-evaluate/strengthen-guardrails/mitigate-jailbreaks)
* [Chapter 3 MITRE ATT\&CK – Adversarial Model Analysis](https://ama.drwhy.ai/mitre-attck.html)
* [OWASP Top 10 for LLM Applications 2025 – WorldTech IT](https://wtit.com/blog/2025/04/17/owasp-top-10-for-llm-applications-2025/)
* [OWASP Machine Learning Security Top Ten](https://owasp.org/www-project-machine-learning-security-top-10/)
* [Few words about AI Security – Jussi Metso](https://www.jussimetso.com/index.php/2024/09/28/few-words-about-ai-security/)
* [How To Ensure LLM Output Adheres to a JSON Schema | Modelmetry](https://modelmetry.com/blog/how-to-ensure-llm-output-adheres-to-a-json-schema)
* [Easily enforcing valid JSON schema following – API](https://community.openai.com/t/feature-request-function-calling-easily-enforcing-valid-json-schema-following/263515?utm_source)
* [AI Safety + Cybersecurity R\&D Tracker – Fairly AI](https://www.fairly.ai/blog/ai-cybersecurity-tracker)
* [Anthropic makes 'jailbreak' advance to stop AI models producing harmful results](https://www.ft.com/content/cf11ebd8-aa0b-4ed4-945b-a5d4401d186e)
* [Pattern matching filter rules - IBM](https://www.ibm.com/docs/ssw_aix_71/security/intrusion_pattern_matching_filter_rules.html)
* [Real-time Threat Detection](https://www.darktrace.com/cyber-ai-glossary/real-time-threat-detection)

