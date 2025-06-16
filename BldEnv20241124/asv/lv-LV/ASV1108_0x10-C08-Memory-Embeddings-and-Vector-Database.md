# C8 Atmiņa, Iegultības un Vektoru Datubāžu Drošība

## Kontroles mērķis

Ieguldi un vektoru krātuves darbojas kā mūsdienu mākslīgā intelekta sistēmu "tiešās atmiņas", pastāvīgi pieņemot lietotāja sniegtos datus un atgriežot tos modeļa kontekstos, izmantojot izgūšanas paplašināto ģenerēšanu (Retrieval-Augmented Generation, RAG). Ja šī atmiņa netiek kontrolēta, tā var nopludināt personas identificējošu informāciju (PII), pārkāpt piekrišanu vai tikt apgriezta, lai atjaunotu sākotnējo tekstu. Šīs kontroles grupas mērķis ir nostiprināt atmiņas plūsmas un vektoru datubāzes tā, lai piekļuve būtu pēc iespējas ierobežota (least-privilege), ieguldījumi aizsargātu privātumu, glabātajiem vektoriem būtu termiņš vai tie būtu atsaucami pēc pieprasījuma, un katra lietotāja atmiņa nekad nekļūtu par cita lietotāja uzvedņu vai aizpildījumu avotu.

---

## C8.1 Piekļuves kontrole atmiņai un RAG indeksiem

Ieviesiet smalkas piekļuves kontroli katrā vektoru kolekcijā.

|   #   | Description                                                                                                                                                                         | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 8.1.1 | Pārbaudiet, vai rindas/ietilpības līmeņa piekļuves kontroles noteikumi ierobežo pievienošanas, dzēšanas un vaicājumu operācijas pēc īrnieka, kolekcijas vai dokumenta tagiem.       |   1   | D/V  |
| 8.1.2 | Pārliecinieties, ka API atslēgām vai JWT ir piešķirtas ierobežotas tiesības (piemēram, kolekciju ID, darbības verbi) un tās tiek mainītas vismaz reizi ceturksnī.                   |   1   | D/V  |
| 8.1.3 | Pārbaudiet, vai privilēģiju eskalācijas mēģinājumi (piemēram, līdzību vaicājumi starp nosaukumu telpām) tiek atklāti un reģistrēti SIEM sistēmā 5 minūšu laikā.                     |   2   | D/V  |
| 8.1.4 | Pārbaudiet, vai vektoru datubāzes auditi reģistrē subjekta identifikatoru, darbību, vektora ID/nosaukumvietu, līdzības slieksni un rezultātu skaitu.                                |   2   | D/V  |
| 8.1.5 | Pārliecinieties, ka piekļuves lēmumi tiek pārbaudīti attiecībā uz apietām kļūdām katru reizi, kad tiek atjauninātas dzinēju versijas vai mainās indeksēšanas sadalīšanas noteikumi. |   3   |  V   |

---

## C8.2 Iebūvētā tīrīšana un validācija

Veiciet teksta iepriekšēju pārbaudi, lai identificētu personiski identificējamu informāciju (PII), veiciet tās slēpšanu vai pseidonimizēšanu pirms vektorizācijas, un pēc vajadzības izpildiet papildus apstrādi iegūtajām iegultnēm, lai noņemtu atlikušos signālus.

|   #   | Description                                                                                                                                                                                              | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 8.2.1 | Pārliecinieties, ka PII un reglamentētie dati tiek atklāti, izmantojot automatizētus klasifikatorus, un pirms iegultā attēlojuma tie tiek maskēti, tokenizēti vai izslēgti.                              |   1   | D/V  |
| 8.2.2 | Pārbaudiet, vai iegultās plūsmas nepieņem vai nesatur karantīnā ievades datus, kuros ir izpildāms kods vai ne-UTF-8 artefakti, kas varētu piesārņot indeksu.                                             |   1   |  D   |
| 8.2.3 | Pārbaudiet, vai vietējā vai metrikas diferenciālās privātuma sanitizācija tiek piemērota teikumu iegultnēm, kuru attālums līdz jebkuram zināmam PII tokenam nokrīt zem konfigurējamas sliekšņa vērtības. |   2   | D/V  |
| 8.2.4 | Pārbaudiet, vai sanitizācijas efektivitāte (piemēram, PII redakcijas atskaites līmenis, semantiskā nobīde) tiek apstiprināta vismaz reizi sešos mēnešos, salīdzinot ar etalona korpusiem.                |   2   |  V   |
| 8.2.5 | Pārliecinieties, ka sanitizācijas konfigurācijas ir versiju kontrolētas un izmaiņas tiek pārskatītas kolēģu vidū.                                                                                        |   3   | D/V  |

---

## C8.3 Atmiņas derīguma termiņa beigas, atsaukšana un dzēšana

GDPR "tiesības tikt aizmirstam" un līdzīgi likumi prasa savlaicīgu dzēšanu; vektoru krātuves tādēļ jāatbalsta TTL (laiks līdz dzēšanai), pilnīgas dzēšanas un "kapu zīmju" izmantošanu, lai atsauktos vektorus nevarētu atgūt vai atkārtoti indeksēt.

|   #   | Description                                                                                                                                                                        | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 8.3.1 | Pārliecinieties, ka katram vektoram un metadatu ierakstam ir TTL vai skaidri norādīta saglabāšanas atzīme, kuru ievēro automatizētie tīrīšanas darbi.                              |   1   | D/V  |
| 8.3.2 | Pārbaudiet, vai lietotāja pieprasītās dzēšanas darbības iznīcina vektorus, metadatus, kešatmiņas kopijas un atvasinātos indeksus 30 dienu laikā.                                   |   1   | D/V  |
| 8.3.3 | Pārbaudiet, vai loģiskās dzēšanas tiek izpildītas ar kriptogrāfisku glabāšanas bloku iznīcināšanu, ja aparatūra to atbalsta, vai arī ar atslēgas glabāšanas atslēgas iznīcināšanu. |   2   |  D   |
| 8.3.4 | Pārbaudiet, vai beigušies vektori tiek izslēgti no tuvāko kaimiņu meklēšanas rezultātiem mazāk nekā 500 ms pēc to derīguma termiņa beigām.                                         |   3   | D/V  |

---

## C8.4 Novērst iegultās informācijas apgriešanu un noplūdi

Nesenās aizsardzības metodes — trokšņa virskārta, projekcijas tīkli, privātuma neironu perturbācija un lietojumprogrammu slāņa šifrēšana — var samazināt tokena līmeņa apgrieztības rādītājus zem 5%.

|   #   | Description                                                                                                                                                                          | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 8.4.1 | Pārbaudiet, vai pastāv formāls draudu modelis, kas aptver invertēšanas, dalības un atribūtu secināšanas uzbrukumus, un vai tas tiek pārskatīts ikgadēji.                             |   1   |  V   |
| 8.4.2 | Pārliecinieties, ka lietojumprogrammas slāņa šifrēšana vai meklējama šifrēšana aizsargā vektorus no tiešas pārlūkošanas no infrastruktūras administratoriem vai mākoņa darbiniekiem. |   2   | D/V  |
| 8.4.3 | Pārbaudiet, vai aizsardzības parametri (ε DP, trokšņa σ, projekcijas ranga k) nodrošina privātumu ≥ 99 % tokenu aizsardzību un lietderību ≤ 3 % precizitātes zudumu.                 |   3   |  V   |
| 8.4.4 | Pārliecinieties, ka inversijas noturības metri ir daļa no izlaiduma barjerām modeļa atjauninājumiem, ar definētiem regresijas budžetiem.                                             |   3   | D/V  |

---

## C8.5 Lietotājam specifiskas atmiņas diapazona ievērošana

Krusto-nomaļu noplūde joprojām ir augsts RAG risks: nepareizi filtrēti līdzības vaicājumi var atklāt cita klienta privātos dokumentus.

|   #   | Description                                                                                                                                                                          | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 8.5.1 | Pārliecinieties, ka katrs izgūšanas vaicājums tiek apstrādāts ar nomnieka/lietošanas ID pēc tam, kad tas ir izfiltrēts, pirms to nodod LLM promptam.                                 |   1   | D/V  |
| 8.5.2 | Pārliecinieties, ka kolekciju nosaukumi vai nosaukumvietas ID ir sāļoti katram lietotājam vai nomniekam, lai vektori nevarētu sakrist dažādās darbības jomās.                        |   1   |  D   |
| 8.5.3 | Pārliecinieties, ka līdzības rezultāti, kas pārsniedz konfigurējamu attāluma slieksni, bet atrodas ārpus izsaucēja darbības jomas, tiek noraidīti un izraisīt drošības brīdinājumus. |   2   | D/V  |
| 8.5.4 | Pārbaudiet, vai daudzlietotāju slodzes testi simulē pretinieciski noskaņotus vaicājumus, kas mēģina izgūt dokumentus ārpus piekļuves zonas, un pierāda nulles datu noplūdi.          |   2   |  V   |
| 8.5.5 | Pārliecinieties, ka šifrēšanas atslēgas ir nodalītas pa nomniekiem, nodrošinot kriptogrāfisku izolāciju pat tad, ja fiziskā glabāšana tiek koplietota.                               |   3   | D/V  |

---

## C8.6 Uzlabota atmiņas sistēmas drošība

Drošības kontroles sarežģītām atmiņas arhitektūrām, tostarp episodiālajai, semantiskajai un darba atmiņai ar specifiskām izolācijas un validācijas prasībām.

|   #   | Description                                                                                                                                                                                                                                               | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 8.6.1 | Pārbaudiet, vai dažādi atmiņas tipi (episodiskā, semantiskā, darba) ir nodalīti drošības konteksti ar lomu balstītām piekļuves kontrolēm, atsevišķām šifrēšanas atslēgām un dokumentētiem piekļuves modeļiem katram atmiņas tipam.                        |   1   | D/V  |
| 8.6.2 | Pārliecinieties, ka atmiņas konsolidācijas procesi ietver drošības validāciju, lai novērstu ļaunprātīgu atmiņu ievadi, izmantojot satura sanitāciju, avotu pārbaudi un integritātes pārbaudes pirms glabāšanas.                                           |   2   | D/V  |
| 8.6.3 | Pārbaudiet, vai atmiņas izgūšanas vaicājumi tiek pārbaudīti un attīrīti, lai novērstu neatļautas informācijas izguvi, izmantojot vaicājumu modeļu analīzi, piekļuves kontroles piemērošanu un rezultātu filtrēšanu.                                       |   2   | D/V  |
| 8.6.4 | Pārbaudiet, vai atmiņas aizmirstošanas mehānismi droši dzēš sensitīvu informāciju ar kriptogrāfiskās dzēšanas garantijām, izmantojot atslēgas dzēšanu, vairākkārtēju pārrakstīšanu vai aparatūras bāzētu drošu dzēšanu ar verifikācijas sertifikātiem.    |   3   | D/V  |
| 8.6.5 | Pārbaudiet, vai atmiņas sistēmas integritāte tiek nepārtraukti uzraudzīta, lai atklātu nesankcionētas izmaiņas vai bojājumus, izmantojot kontrolsummas, audita žurnālus un automatizētas brīdinājumus, kad atmiņas saturs mainās ārpus normālas darbības. |   3   | D/V  |

---

## Atsauces

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

