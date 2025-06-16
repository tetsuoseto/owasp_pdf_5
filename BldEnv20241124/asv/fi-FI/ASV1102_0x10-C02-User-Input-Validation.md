# C2 Käyttäjän syötteen validointi

## Ohjaustavoite

Käyttäjän syötteen vahva validointi on ensisijainen puolustuskeino eräitä tekoälyjärjestelmiin kohdistuvia haitallisimpia hyökkäyksiä vastaan. Kehoteinjektiohyökkäykset voivat ohittaa järjestelmän ohjeistukset, vuotaa arkaluontoisia tietoja tai ohjata mallin sallimattomaan käyttäytymiseen. Elleivät erilliset suodattimet ja ohjehierarkiat ole käytössä, tutkimukset osoittavat, että "monisäikeiset" jailbreak-hyökkäykset, jotka hyödyntävät erittäin pitkiä kontekstikkunoja, ovat tehokkaita. Lisäksi hienovaraiset vihamieliset häiriöhyökkäykset — kuten homoglyph-vaihdot tai leetspeak — voivat hiljaisesti muuttaa mallin päätöksiä.

---

## C2.1 Kehoteinjektiosuojus

Kehotteen injektointi on yksi suurimmista riskeistä tekoälyjärjestelmille. Tämän taktiikan torjumiseksi käytetään yhdistelmää staattisia kuviofilttereitä, dynaamisia luokittelijoita ja ohjehierarkian noudattamisen valvontaa.

|   #   | Description                                                                                                                                                                                                                            | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 2.1.1 | Varmista, että käyttäjän syötteet tarkistetaan jatkuvasti päivitettävään tunnettuja kehotteiden injektiomalleja (jailbreak-avainsanoja, "ohita edellinen", roolipelausketjuja, epäsuoria HTML/URL-hyökkäyksiä) sisältävään kirjastoon. |   1   | D/V  |
| 2.1.2 | Varmista, että järjestelmä noudattaa ohjehierarkiaa, jossa järjestelmä- tai kehittäjäviestit ohittavat käyttäjän ohjeet, myös laajennetun kontekstikehyksen jälkeen.                                                                   |   1   | D/V  |
| 2.1.3 | Varmista, että vastustava arviointi (esim. Red Teamin "many-shot" -kehotteet) suoritetaan ennen jokaista mallin tai kehotemallin julkaisua, asettaen onnistumisprosentin kynnykset ja automaattiset estimet regressioiden varalta.     |   2   | D/V  |
| 2.1.4 | Varmista, että kolmannen osapuolen sisällöstä (verkkosivut, PDF:t, sähköpostit) peräisin olevat kehotteet puhdistetaan eristetyssä jäsennysympäristössä ennen kuin ne liitetään pääkehoteeseen.                                        |   2   |  D   |
| 2.1.5 | Varmista, että kaikki kehotteiden suodatussääntöjen päivitykset, luokittelijan malliversiot ja estolistamuutokset ovat versiohallittuja ja tarkastettavissa.                                                                           |   3   | D/V  |

---

## C2.2 Vihamielisten esimerkkien vastustuskyky

Luonnollisen kielen käsittelyn (NLP) mallit ovat edelleen alttiita hienovaraisille merkkien tai sanojen tason häiriöille, jotka ihmiset usein ohittavat, mutta joita mallit yleensä luokittelevat väärin.

|   #   | Description                                                                                                                                                                                                                | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 2.2.1 | Varmista, että perus syötteen normalisointivaiheet (Unicode NFC, homoglyph-kartoitus, välilyöntien trimmaus) suoritetaan ennen tokenisointia.                                                                              |   1   |  D   |
| 2.2.2 | Varmista, että tilastollinen poikkeamien havaitseminen merkitsee syötteitä, joilla on epätavallisen korkea muokkausetäisyys kielinormeihin nähden, liiallinen toistuvien tokenien määrä tai epänormaalit upotusetäisyydet. |   2   | D/V  |
| 2.2.3 | Varmista, että päättelyputki tukee valinnaisia vastustavaan harjoitteluun kovetettuja mallivariantteja tai puolustuskerroksia (esim. satunnaistaminen, puolustava tislanta) korkean riskin päätepisteille.                 |   2   |  D   |
| 2.2.4 | Varmista, että epäillyt vastustajan syötteet asetetaan karanteeniin ja kirjataan täydellisten tietomassojen kanssa (henkilötietojen poistamisen jälkeen).                                                                  |   2   |  V   |
| 2.2.5 | Varmista, että robustiuden mittarit (tunnettujen hyökkäyssarjojen onnistumisprosentti) seurataan ajan kuluessa ja että regressiot aiheuttavat julkaisun eston.                                                             |   3   | D/V  |

---

## C2.3 Skeeman, tyypin ja pituuden validointi

Muodottomat tai liian suuret syötteet sisältävät tekoälyhyökkäykset voivat aiheuttaa jäsentämisvirheitä, kehotteiden leviämistä kenttien yli ja resurssien loppumista. Tiukka skeeman valvonta on myös edellytys determinististen työkalukutsujen suorittamisessa.

|   #   | Description                                                                                                                                                                                     | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 2.3.1 | Varmista, että jokainen API- tai funktiokutsupiste määrittelee selkeän syöttökaavion (JSON Schema, Protobuf tai multimodaalinen vastaava) ja että syötteet validoidaan ennen kehotteen koontia. |   1   |  D   |
| 2.3.2 | Varmista, että syötteet, jotka ylittävät enimmäismäärän tavuissa tai tokeneissa, hylätään turvallisella virheellä eikä niitä koskaan leikata hiljaa.                                            |   1   | D/V  |
| 2.3.3 | Varmista, että tyyppitarkistukset (esim. numeeriset arvovälit, enum-arvot, MIME-tyypit kuville/äänelle) toteutetaan palvelinpuolella, ei pelkästään asiakasohjelmakoodissa.                     |   2   | D/V  |
| 2.3.4 | Varmista, että semanttiset validoijat (esim. JSON Schema) toimivat vakioaikaisesti estääkseen algoritmisen palvelunestohyökkäyksen.                                                             |   2   |  D   |
| 2.3.5 | Varmista, että validoinnin epäonnistumiset kirjataan sensuroituine tietosisältöineen ja yksiselitteisine virhekoodeineen turvallisuuden arvioinnin helpottamiseksi.                             |   3   |  V   |

---

## C2.4 Sisällön ja politiikan tarkastus

Kehittäjien tulisi pystyä tunnistamaan syntaktisesti kelvolliset kehotteet, jotka pyytävät kiellettyä sisältöä (kuten laittomia ohjeita, vihapuhetta ja tekijänoikeudella suojattua tekstiä) ja estämään niiden leviämisen.

|   #   | Description                                                                                                                                                                                                                       | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 2.4.1 | Varmista, että sisällönluokittelija (nollakosketus tai hienosäädetty) arvioi jokaisen syötteen väkivallan, itsehaitan, vihan, seksuaalisen sisällön ja laittomien pyyntöjen osalta, käyttäen määriteltävissä olevia kynnysarvoja. |   1   |  D   |
| 2.4.2 | Varmista, että politiikkoja rikkovat syötteet saavat vakioidut hylkäykset tai turvalliset täydennykset, jotta ne eivät siirry myöhempiin suurten kielimallien kutsuihin.                                                          |   1   | D/V  |
| 2.4.3 | Varmista, että seulontamalli tai sääntöjoukko koulutetaan uudelleen/päivitetään vähintään neljännesvuosittain, ottaen huomioon äskettäin havaittuja jailbreak- tai politiikan kiertämismalleja.                                   |   2   |  D   |
| 2.4.4 | Varmista, että seulonta noudattaa käyttäjäkohtaisia politiikkoja (ikä, alueelliset lakisääteiset rajoitukset) ominaisuuksiin perustuvien sääntöjen avulla, jotka ratkaistaan pyynnön yhteydessä.                                  |   2   |  D   |
| 2.4.5 | Varmista, että seulontalokit sisältävät luokittelijan luottamusarvot ja politiikkakategorian tunnisteet SOC-korrelointia ja tulevaa red teamin toistoa varten.                                                                    |   3   |  V   |

---

## C2.5 Syöttönopeuden rajoittaminen ja väärinkäytösten ehkäisy

Kehittäjien tulisi estää väärinkäyttö, resurssien ylikuormitus ja automatisoidut hyökkäykset tekoälyjärjestelmiä vastaan rajoittamalla syötteen määrää ja tunnistamalla poikkeavat käyttökäyttäytymismallit.

|   #   | Description                                                                                                                                             | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 2.5.1 | Varmista, että käyttäjäkohtaiset, IP-osoitekohtaiset ja API-avainkohtaiset käyttörajoitukset otetaan käyttöön kaikilla syöttöpisteillä.                 |   1   | D/V  |
| 2.5.2 | Varmista, että purkaus- ja jatkuvat nopeusrajoitukset on säädetty estämään palvelunestohyökkäykset (DoS) ja raakavoimahyökkäykset.                      |   2   | D/V  |
| 2.5.3 | Varmista, että poikkeavat käyttökuviot (esim. nopeasti peräkkäiset pyynnöt, syötteen tulva) laukaisevat automaattiset esto- tai eskalointitoimenpiteet. |   2   | D/V  |
| 2.5.4 | Varmista, että väärinkäytön estolokit säilytetään ja tarkastetaan tunnistettavien hyökkäyskuvioiden varalta.                                            |   3   |  V   |

---

## C2.6 Monimodaalinen syötteen validointi

AI-järjestelmien tulisi sisältää vahva validointi tekstittömille syötteille (kuvat, ääni, tiedostot) estääkseen injektoinnin, kiertämisen tai resurssien väärinkäytön.

|   #   | Description                                                                                                                              | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 2.6.1 | Varmista, että kaikki ei-tekstimuotoiset syötteet (kuvat, äänet, tiedostot) tarkistetaan tyypin, koon ja muodon osalta ennen käsittelyä. |   1   |  D   |
| 2.6.2 | Varmista, että tiedostot skannataan haittaohjelmien ja steganografisten tietojenkantajien varalta ennen syöttämistä.                     |   2   | D/V  |
| 2.6.3 | Varmista, että kuva- ja ääniosat tarkastetaan vihamielisten häiriöiden tai tunnettujen hyökkäyskuvioiden varalta.                        |   2   | D/V  |
| 2.6.4 | Varmista, että multimodaaliset syötteen validointivirheet kirjataan lokiin ja laukaisevat hälytykset tutkintaa varten.                   |   3   |  V   |

---

## C2.7 Syötteen alkuperä ja attribuutio

Tekoälyjärjestelmien tulisi tukea tarkastuksia, väärinkäytösten seurantaa ja vaatimustenmukaisuutta seuraamalla ja merkitsemällä kaikkien käyttäjäsyötteiden alkuperät.

|   #   | Description                                                                                                                                  | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 2.7.1 | Varmista, että kaikki käyttäjän syötteet merkitään metatiedoilla (käyttäjätunnus, istunto, lähde, aikaleima, IP-osoite) sisäänottovaiheessa. |   1   | D/V  |
| 2.7.2 | Varmista, että alkuperätietojen metatiedot säilyvät ja ovat tarkastettavissa kaikille käsitellyille syötteille.                              |   2   | D/V  |
| 2.7.3 | Varmista, että poikkeavat tai epäluotettavat syöttölähteet tunnistetaan ja ne altistetaan tehostetulle tarkastelulle tai estetään.           |   2   | D/V  |

---

## C2.8 Reaaliaikainen adaptiivinen uhkien tunnistus

Kehittäjien tulisi käyttää kehittyneitä uhkien tunnistusjärjestelmiä tekoälylle, jotka sopeutuvat uusiin hyökkäyskuvioihin ja tarjoavat reaaliaikaista suojaa kootun kuvion tunnistuksen avulla.

|   #   | Description                                                                                                                                                                                                           | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 2.8.1 | Varmista, että uhkien tunnistuskuviot on käännetty optimoiduiksi säännöllisen lausekkeen (regex) moottoreiksi, jotka tarjoavat korkean suorituskyvyn reaaliaikaiseen suodatukseen minimaalisen viiveen vaikutuksella. |   1   | D/V  |
| 2.8.2 | Varmista, että uhkien havaitsemisjärjestelmät ylläpitävät erillisiä mallikirjastoja eri uhkaluokille (kehotteiden injektointi, haitallinen sisältö, arkaluonteiset tiedot, järjestelmäkomennot).                      |   1   | D/V  |
| 2.8.3 | Varmista, että mukautuva uhkien tunnistus sisältää koneoppimismallit, jotka päivittävät uhkien herkkyyttä hyökkäysten tiheyden ja onnistumisprosenttien perusteella.                                                  |   2   | D/V  |
| 2.8.4 | Varmista, että reaaliaikaiset uhkatiedustelusyötteet päivittävät automaattisesti mallikirjastot uusilla hyökkäysallekirjoituksilla ja kompromissin tunnusmerkeillä (IOCs).                                            |   2   | D/V  |
| 2.8.5 | Varmista, että uhkien tunnistuksen väärien positiivisten osuuksia seurataan jatkuvasti ja kaavojen spesifisyyttä säädetään automaattisesti minimoimaan laillisten käyttötapausten häiriöt.                            |   3   | D/V  |
| 2.8.6 | Varmista, että kontekstuaalinen uhka-analyysi ottaa huomioon syötteen lähteen, käyttäytymismallit ja istunnon historian parantaakseen tunnistustarkkuutta.                                                            |   3   | D/V  |
| 2.8.7 | Varmista, että uhkien tunnistus suorituskykymittarit (tunnistusaste, käsittelyviive, resurssien käyttö) seurataan ja optimoidaan reaaliajassa.                                                                        |   3   | D/V  |

---

## C2.9 Monimodaalinen tietoturvan varmistusputkisto

Kehittäjien tulisi tarjota tietoturvan validointi teksti-, kuva-, ääni- ja muille tekoälyn syöttömuodoille erityyppisten uhkien havaitsemisen ja resurssien eristyksen avulla.

|   #   | Description                                                                                                                                                                                                                                                                               | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 2.9.1 | Varmista, että jokaisella syöttömodaliteetilla on omistetut tietoturvatarkastajat, joilla on dokumentoidut uhkamallit (teksti: käskeiden injektio, kuvat: steganografia, ääni: spektrikuvahyökkäykset) ja tunnistusrajat.                                                                 |   1   | D/V  |
| 2.9.2 | Varmista, että multimodaaliset syötteet käsitellään eristetyissä hiekkalaatikoissa, joilla on määritellyt resurssirajat (muisti, suoritin, käsittelyaika) kullekin modaalisuustyypille, ja nämä on dokumentoitu turvallisuuspolitiikoissa.                                                |   2   | D/V  |
| 2.9.3 | Varmista, että ristiinmodalinen hyökkäysten havaitseminen tunnistaa koordinoidut hyökkäykset, jotka ulottuvat useisiin syötetyyppeihin (esim. steganografiset kuormitukset kuvissa yhdistettynä kehotteen injektointiin tekstissä) korrelaatiosääntöjen ja hälytysten generoinnin avulla. |   2   | D/V  |
| 2.9.4 | Varmista, että monimuotoiset validointivirheet laukaisevat yksityiskohtaisen lokituksen, joka sisältää kaikki syötteen muodot, validointitulokset, uhkapisteet ja korrelaatioanalyysin strukturoiduissa lokimuodoissa SIEM-integraatiota varten.                                          |   3   | D/V  |
| 2.9.5 | Varmista, että modality-kohtaiset sisältöluokittelijat päivitetään dokumentoitujen aikataulujen mukaisesti (vähintään neljännesvuosittain) uusilla uhkamalleilla, vastustavilla esimerkeillä ja suorituskykymittareilla, jotka pysyvät perustasoa korkeammalla.                           |   3   | D/V  |

---

## Viitteet

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

