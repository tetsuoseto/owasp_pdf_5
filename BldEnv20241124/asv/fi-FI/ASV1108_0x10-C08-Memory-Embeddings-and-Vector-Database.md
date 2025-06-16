# C8-muisti, upotukset ja vektoritietokannan turvallisuus

## Ohjaustavoite

Upotukset ja vektorivarastot toimivat nykyaikaisten tekoälyjärjestelmien "elävinä muistoina", jotka jatkuvasti vastaanottavat käyttäjän tarjoamaa dataa ja palauttavat sen mallien konteksteihin hakua täydentävän generoinnin (Retrieval-Augmented Generation, RAG) kautta. Jos tätä muistia ei hallita, se voi vuotaa henkilötietoja, rikkoa suostumusehtoja tai kääntyä alkuperäisen tekstin rekonstruoimiseksi. Tämän kontrolliperheen tavoitteena on vahvistaa muistiputkia ja vektoritietokantoja siten, että pääsy on vähimmän etuoikeuden periaatteen mukaista, upotukset säilyttävät yksityisyyden, tallennetut vektorit vanhenevat tai ne voidaan perua pyynnöstä, ja käyttäjäkohtainen muisti ei koskaan saastuta toisen käyttäjän kehotteita tai täydentämiä vastauksia.

---

## C8.1 Pääsynhallinta muistille ja RAG-indekseille

Toteuta tarkkarajaiset käyttöoikeuksien valvontamekanismit jokaiseen vektorikokoelmaan.

|   #   | Description                                                                                                                                                                          | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 8.1.1 | Varmista, että rivikohtaiset/namespace-tason käyttöoikeussäännöt rajoittavat lisäys-, poisto- ja kyselytoiminnot jokaiselle vuokralaiselle, kokoelmalle tai asiakirjan tunnisteelle. |   1   | D/V  |
| 8.1.2 | Varmista, että API-avaimissa tai JWT:issä on määritelty rajatut valtuudet (esim. kokoelman tunnisteet, toimintaverbit) ja että ne kierrätetään vähintään neljännesvuosittain.        |   1   | D/V  |
| 8.1.3 | Varmista, että etuoikeuksien korotuspyrkimykset (esim. poikkitilan samankaltaisuuskyselyt) havaitaan ja kirjataan SIEM-järjestelmään viiden minuutin kuluessa.                       |   2   | D/V  |
| 8.1.4 | Varmista, että vektoritietokanta tarkastaa lokia, joka sisältää kohdetunnisteen, toimenpiteen, vektorin tunnuksen/nimiavaruuden, samankaltaisuuskynnyksen ja tulosmäärän.            |   2   | D/V  |
| 8.1.5 | Varmista, että pääsyä koskevat päätökset testataan ohitusvirheiden varalta aina, kun moottoreita päivitetään tai indeksi- jaottelusäännöt muuttuvat.                                 |   3   |  V   |

---

## C8.2 Upotusten puhdistus ja validointi

Esi­tarkista teksti henkilötietojen varalta, sensuroi tai pe­su­doo­ni­mise­raa ennen vektoroimista, ja tarvittaessa poista upotuksista kaikki jäännökselliset signaalit jälkikäsittelyssä.

|   #   | Description                                                                                                                                                                                                          | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 8.2.1 | Varmista, että henkilötunnistetiedot (PII) ja säädellyt tiedot tunnistetaan automatisoitujen luokittimien avulla ja ne peitetään, tokenisoidaan tai poistetaan ennen upotusta.                                       |   1   | D/V  |
| 8.2.2 | Varmista, että upotusputket hylkäävät tai eristävät syötteet, jotka sisältävät suoritettavaa koodia tai ei-UTF-8-artifakteja, jotka voisivat myrkyttää indeksin.                                                     |   1   |  D   |
| 8.2.3 | Varmista, että paikallista tai metristä differentiaalisuojaussanitointia sovelletaan lauselausekkeisiin, joiden etäisyys mihin tahansa tunnettuun henkilötietomerkkiin (PII) alittaa asetettavissa olevan kynnyksen. |   2   | D/V  |
| 8.2.4 | Varmista, että puhdistuksen tehokkuus (esim. henkilötietojen poiston palautuskyky, semanttinen muutosten seuranta) validoidaan vähintään puolen vuoden välein vertailukorpusten avulla.                              |   2   |  V   |
| 8.2.5 | Varmista, että puhdistusasetukset ovat versionhallinnassa ja muutokset käyvät läpi vertaisarvioinnin.                                                                                                                |   3   | D/V  |

---

## C8.3 Muistin vanhentuminen, peruutus ja poisto

GDPR:n "oikeus tulla unohdetuksi" ja vastaavat lait vaativat tietojen oikea-aikaista poistamista; vektorivarastojen on siksi tuettava TTL:iä, pysyviä poistoja ja tomb-stoningia, jotta peruutettuja vektoreita ei voida palauttaa tai uudelleenindeksoida.

|   #   | Description                                                                                                                                                       | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 8.3.1 | Varmista, että jokainen vektori- ja metatietue sisältää TTL:n tai nimenomaisen säilytysmerkinnän, jota automatisoidut puhdistustehtävät noudattavat.              |   1   | D/V  |
| 8.3.2 | Varmista, että käyttäjän aloittamat poistopyynnöt poistavat vektorit, metatiedot, välimuistikopiot ja johdetut indeksit 30 päivän kuluessa.                       |   1   | D/V  |
| 8.3.3 | Varmista, että loogisten poistojen jälkeen suoritetaan tallennuslohkojen kryptografinen tuhoaminen, jos laitteisto tukee sitä, tai avainnipun avaimen tuhoaminen. |   2   |  D   |
| 8.3.4 | Varmista, että vanhentuneet vektorit suljetaan pois lähimmän naapurin hakutuloksista alle 500 ms vanhenemisen jälkeen.                                            |   3   | D/V  |

---

## C8.4 Estä upotusten kääntäminen ja vuotaminen

Viimeaikaiset puolustukset—kohinan päällekkäisyys, projektion verkot, yksityisyysneuronin häirintä ja sovelluskerroksen salaus—pystyvät vähentämään token-tason käännösprosentit alle 5 %:iin.

|   #   | Description                                                                                                                                                                            | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 8.4.1 | Varmista, että olemassa on muodollinen uhkamalli, joka kattaa käännös-, jäsenyys- ja ominaisuustietojen arviointihyökkäykset, ja että sitä tarkastellaan vuosittain.                   |   1   |  V   |
| 8.4.2 | Varmista, että sovelluskerroksen salaus tai haettavissa oleva salaus suojaa vektoreita infrastruktuurin ylläpitäjien tai pilvipalvelun henkilöstön suoralta lukemiselta.               |   2   | D/V  |
| 8.4.3 | Varmista, että suojausparametrit (ε DP:lle, kohina σ, projektion rangen k) tasapainottavat yksityisyyden ≥ 99 % tokenin suojauksen ja hyödyllisyyden ≤ 3 % tarkkuuden aleneman kanssa. |   3   |  V   |
| 8.4.4 | Varmista, että käännösresilienssimittarit ovat osa julkaisujäseniä mallipäivityksille, ja aseta regressiorajat.                                                                        |   3   | D/V  |

---

## C8.5 Käyttöoikeuksien valvonta käyttäjäkohtaiselle muistille

Vuokralaisesta vuokralaiseen tapahtuva vuoto on edelleen merkittävä RAG-riski: huonosti suodatetut samankaltaisuuskyselyt voivat paljastaa toisen asiakkaan yksityiset asiakirjat.

|   #   | Description                                                                                                                                                                                                 | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 8.5.1 | Varmista, että jokainen hakukysely suodatetaan jälkikäteen vuokralaisen/käyttäjän tunnuksella ennen kuin se lähetetään LLM-kehotteeseen.                                                                    |   1   | D/V  |
| 8.5.2 | Varmista, että kokoelman nimet tai nimetyt tunnisteet suolataan käyttäjäkohtaisesti tai vuokraajakohtaisesti, jotta vektorit eivät voi törmätä eri alueiden välillä.                                        |   1   |  D   |
| 8.5.3 | Varmista, että edellä mainitut samankaltaisuustulokset, jotka ylittävät määritettävissä olevan etäisyyskynnyksen mutta jäävät kutsujan alueen ulkopuolelle, hylätään ja aiheuttavat turvallisuushälytyksiä. |   2   | D/V  |
| 8.5.4 | Varmista, että monivuokraajaympäristön kuormitustestit simuloivat vihamielisiä kyselyitä, jotka yrittävät hakea soveltamisalan ulkopuolisia asiakirjoja, ja osoittavat nollavuotoa.                         |   2   |  V   |
| 8.5.5 | Varmista, että salausavaimet on eroteltu jokaiselle vuokralaiselle erikseen, varmistaen kryptografisen eristyksen, vaikka fyysinen tallennustila olisi jaettu.                                              |   3   | D/V  |

---

## C8.6 Kehittynyt muistijärjestelmän suojaus

Turvallisuusvalvontamekanismit kehittyneille muistijärjestelmille, kuten episodiselle, semanttiselle ja työmuistille, joilla on erityiset eristys- ja validointivaatimukset.

|   #   | Description                                                                                                                                                                                                                                                             | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 8.6.1 | Varmista, että eri muistityypeillä (episodinen, semanttinen, työmuisti) on eristetyt tietoturvakontekstit roolipohjaisilla käyttöoikeuksilla, erilliset salausavaimet ja dokumentoidut käyttömallit kullekin muistityypille.                                            |   1   | D/V  |
| 8.6.2 | Varmista, että muistien konsolidointiprosessit sisältävät turvallisuusvalidoinnin estääkseen haitallisten muistojen injektoinnin sisällön puhdistuksen, lähteen varmennuksen ja eheystarkastusten avulla ennen tallennusta.                                             |   2   | D/V  |
| 8.6.3 | Varmista, että muistin hakukyselyt validoidaan ja puhdistetaan estääkseen luvattoman tiedon poimimisen kyselykuvioiden analyysin, käyttöoikeuksien valvonnan ja tulosten suodatuksen avulla.                                                                            |   2   | D/V  |
| 8.6.4 | Varmista, että muistin unohtamismekanismit poistavat arkaluonteiset tiedot turvallisesti kryptografisen tuhoamisen takuilla käyttämällä avaimen poistamista, moninkertaista ylikirjoitusta tai laitteistopohjaista turvallista poistamista vahvistustodistusten kanssa. |   3   | D/V  |
| 8.6.5 | Varmista, että muistijärjestelmän eheyttä valvotaan jatkuvasti luvattomien muutosten tai korruptoitumisen varalta käyttämällä tarkistussummia, tarkastuslokeja ja automaattisia hälytyksiä, kun muistin sisältö muuttuu normaalitoimintojen ulkopuolella.               |   3   | D/V  |

---

## Viitteet

* [Vector database security: Pinecone – IronCore Labs](https://ironcorelabs.com/vectordbs/pinecone-security/)
* [Securing the Backbone of AI: Safeguarding Vector Databases and Embeddings – Privacera](https://privacera.com/blog/securing-the-backbone-of-ai-safeguarding-vector-databases-and-embeddings/)
* [Enhancing Data Security with RBAC of Qdrant Vector Database – AI Advances](https://ai.gopubby.com/enhancing-data-security-with-role-based-access-control-of-qdrant-vector-database-3878769bec83)
* [Mitigating Privacy Risks in LLM Embeddings from Embedding Inversion – arXiv](https://arxiv.org/html/2411.05034v1)
* [DPPN: Detecting and Perturbing Privacy-Sensitive Neurons – OpenReview](https://openreview.net/forum?id=DF5TVzpTW0)
* [Art. 17 GDPR – Right to Erasure](https://gdpr-info.eu/art-17-gdpr/)
* [Sensitive Data in Text Embeddings Is Recoverable – Tonic.ai](https://www.tonic.ai/blog/sensitive-data-in-text-embeddings-is-recoverable)
* [PII Identification and Removal – NVIDIA NeMo Docs](https://docs.nvidia.com/nemo-framework/user-guide/latest/datacuration/personalidentifiableinformationidentificationandremoval.html)
* [De-identifying Sensitive Data – Google Cloud DLP](https://cloud.google.com/sensitive-data-protection/docs/deidentify-sensitive-data)
* [Remove PII from Conversations Using Sensitive Information Filters – AWS Bedrock Guardrails](https://docs.aws.amazon.com/bedrock/latest/userguide/guardrails-sensitive-filters.html)
* [Think Your RAG Is Secure? Think Again – Medium](https://medium.com/%40vijay.poudel1/think-your-rag-is-secure-think-again-heres-how-to-actually-lock-it-down-c4c30e3864e7)
* [Design a Secure Multitenant RAG Inferencing Solution – Microsoft Learn](https://learn.microsoft.com/en-us/azure/architecture/ai-ml/guide/secure-multitenant-rag)
* [Best Practices for Multi-Tenancy RAG with Milvus – Milvus Blog](https://milvus.io/blog/build-multi-tenancy-rag-with-milvus-best-practices-part-one.md)

