# C4-infrastruktuuri, konfiguraatio ja käyttöönoton turvallisuus

## Hallintatavoite

Tekoälyinfrastruktuuri on vahvistettava etuoikeuksien laajentamista, toimitusketjun manipulointia ja sivuttaisliikettä vastaan turvallisen konfiguraation, suorituseristyksen, luotettavien käyttöönotto-putkien ja kattavan valvonnan avulla. Vain valtuutetut, validoidut infrastruktuurin komponentit ja konfiguraatiot pääsevät tuotantoon hallittujen prosessien kautta, jotka ylläpitävät turvallisuutta, eheyttä ja auditoitavuutta.

Ydin turvallisuustavoite: Vain kryptografisesti allekirjoitetut, haavoittuvuusskannatut infrastruktuurikomponentit pääsevät tuotantoon automaattisten validointiputkien kautta, jotka noudattavat turvallisuuspolitiikkoja ja ylläpitävät muuttumattomia tarkastusepäkirjoja.

---

## C4.1 Suoritusaikaympäristön eristäminen

Estä säiliöiden karkailu ja oikeuksien korotus kernel-tason eristysprimitivien sekä pakollisten käyttöoikeuksien valvonnan avulla.

|   #   | Description                                                                                                                                                                                                                               | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.1.1 | Varmista, että kaikista tekoälysäilöistä poistetaan KAIKKI Linuxin käyttöoikeudet lukuun ottamatta CAP_SETUID-, CAP_SETGID- ja turvallisuusperustaasiakirjoissa eksplisiittisesti vaadittuja käyttöoikeuksia.                             |   1   | D/V  |
| 4.1.2 | Varmista, että seccomp-profiilit estävät kaikki järjestelmäkutsut paitsi ne, jotka ovat ennalta hyväksytyissä sallituissa listoissa, ja että rikkomukset johtavat kontin lopettamiseen ja turvallisuushälytysten luomiseen.               |   1   | D/V  |
| 4.1.3 | Varmista, että tekoälytyökuormat ajetaan vain-luku -juurihakemistojärjestelmillä, väliaikaiselle datalle käytetään tmpfs:ää ja pysyvälle datalle nimettyjä volumeeja, joihin on sovellettu noexec-liitinvaihtoehtoja.                     |   2   | D/V  |
| 4.1.4 | Varmista, että eBPF-pohjainen ajonaikainen valvonta (Falco, Tetragon tai vastaava) havaitsee oikeuksien korottamisyritykset ja tappaa automaattisesti rikkomukseen syyllistyneet prosessit organisaation vasteaikavaatimusten mukaisesti. |   2   | D/V  |
| 4.1.5 | Varmista, että korkean riskin tekoälykuormitukset suoritetaan laitteistollisesti eristetyissä ympäristöissä (Intel TXT, AMD SVM tai omistetut bare-metal-solmut) käyttäen todentamisvarmistusta.                                          |   3   | D/V  |

---

## C4.2 Turvatut rakennus- ja käyttöönotto-putket

Varmista kryptografinen eheys ja toimitusketjun turvallisuus toistettavien rakennosten ja allekirjoitettujen artefaktien avulla.

|   #   | Description                                                                                                                                                                                                            | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.2.1 | Varmista, että infrastruktuuri koodina skannataan työkaluilla (tfsec, Checkov tai Terrascan) jokaisessa commitissa, ja estä yhdistämiset, jos löydökset ovat kriittisiä tai vakavia (CRITICAL tai HIGH).               |   1   | D/V  |
| 4.2.2 | Varmista, että konttien rakennukset ovat toistettavissa identtisillä SHA256-tiivisteillä eri rakennusten välillä, ja luo SLSA-tason 3 alkuperätodistukset, jotka on allekirjoitettu Sigstorella.                       |   1   | D/V  |
| 4.2.3 | Varmista, että konttikuvat sisältävät CycloneDX- tai SPDX-SBOM-tiedostot ja että ne on allekirjoitettu Cosignilla ennen kuvien työntämistä rekisteriin, ja hylkää allekirjoittamattomat kuvat käyttöönoton yhteydessä. |   2   | D/V  |
| 4.2.4 | Varmista, että CI/CD-putkistot käyttävät OIDC-tunnuksia HashiCorp Vaultista, AWS IAM -rooleista tai Azure Managed Identitystä, joiden voimassaoloaika ei ylitä organisaation turvallisuuspolitiikan rajoja.            |   2   | D/V  |
| 4.2.5 | Varmista, että Cosign-allekirjoitukset ja SLSA-lähdetiedot validoidaan käyttöönoton aikana ennen säilön suorittamista ja että varmennusvirheet aiheuttavat käyttöönoton epäonnistumisen.                               |   2   | D/V  |
| 4.2.6 | Varmista, että käännösympäristöt toimivat väliaikaisissa säiliöissä tai virtuaalikoneissa ilman pysyvää tallennustilaa ja tuotantoverkon VPC:iden kanssa eristettynä.                                                  |   2   | D/V  |

---

## C4.3 Verkkoturva ja pääsynvalvonta

Toteuta nollaluottamusverkot oletuskieltopolitiikoilla ja salatuilla viestintäyhteyksillä.

|   #   | Description                                                                                                                                                                                                                       | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.3.1 | Varmista, että Kubernetes NetworkPolicies tai vastaava toteuttaa oletusarvoisen eston sisääntulevaan/ulosmeno-liikenteeseen ja sallii eksplisiittisesti vain tarvittavat portit (443, 8080 jne.).                                 |   1   | D/V  |
| 4.3.2 | Varmista, että SSH (portti 22), RDP (portti 3389) ja pilven metatiedon päätepisteet (169.254.169.254) ovat estettyjä tai vaativat varmennepohjaisen todennuksen.                                                                  |   1   | D/V  |
| 4.3.3 | Varmista, että lähtevää liikennettä suodatetaan HTTP/HTTPS-proksien (Squid, Istio tai pilven NAT-porttien) kautta käyttämällä sallittujen verkkotunnusten luetteloita, ja estetyt pyynnöt kirjataan.                              |   2   | D/V  |
| 4.3.4 | Varmista, että palveluiden välinen viestintä käyttää molemminpuolista TLS:ää, jossa sertifikaatit kiertävät organisaation politiikan mukaisesti ja sertifikaattien validointi toteutetaan (ei ohiteta varmennuksen tarkistuksia). |   2   | D/V  |
| 4.3.5 | Varmista, että tekoälyinfrastruktuuri toimii omistetuissa VPC:issä/VNet:eissä ilman suoraa internet-yhteyttä ja kommunikoi ainoastaan NAT-porttien tai bastion-palvelimien kautta.                                                |   2   | D/V  |

---

## C4.4 Salaisuuksien ja kryptografisten avainten hallinta

Suojaa tunnistetiedot laitteistopohjaisella tallennuksella ja automaattisella kierrätyksellä nollaluottamuksen pääsynhallinnalla.

|   #   | Description                                                                                                                                                                                                                                        | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.4.1 | Varmista, että salaisuudet tallennetaan HashiCorp Vaultiin, AWS Secrets Manageriin, Azure Key Vaultiin tai Google Secret Manageriin AES-256-salauksella lepotilassa.                                                                               |   1   | D/V  |
| 4.4.2 | Varmista, että salausavaimet luodaan FIPS 140-2 Tason 2 HSM-laitteissa (AWS CloudHSM, Azure Dedicated HSM) avainten kierron mukaisesti organisaation salauspolitiikan mukaisesti.                                                                  |   1   | D/V  |
| 4.4.3 | Varmista, että salaisuuksien kierto on automatisoitu niin, että käyttöönotto tapahtuu ilman käyttökatkoa ja kierto käynnistyy välittömästi henkilöstömuutosten tai turvallisuuspoikkeamien yhteydessä.                                             |   2   | D/V  |
| 4.4.4 | Varmista, että konttikuvat skannataan työkaluilla (GitLeaks, TruffleHog tai detect-secrets), jotka estävät käännökset, jotka sisältävät API-avaimia, salasanoja tai sertifikaatteja.                                                               |   2   | D/V  |
| 4.4.5 | Varmista, että tuotannon salainen pääsy vaatii monivaiheisen todennuksen (MFA) laitteistotunnisteilla (YubiKey, FIDO2) ja että siihen liittyvät toimet kirjataan muuttumattomiin auditointilokeihin käyttäjäidentiteettien ja aikaleimojen kanssa. |   2   | D/V  |
| 4.4.6 | Varmista, että salaisuudet syötetään Kubernetes-salaisuuksien, liitettyjen volyymien tai init-konttien kautta, ja varmista, ettei salaisuuksia koskaan upoteta ympäristömuuttujiin tai kuviin.                                                     |   2   | D/V  |

---

## C4.5 AI-kuormituksen säiliöinti ja validointi

Eristä epäluotettavat tekoälymallit suojattuihin hiekkalaatikoihin kattavalla käyttäytymisanalyysillä.

|   #   | Description                                                                                                                                                                                                                        | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.5.1 | Varmista, että ulkoiset tekoälymallit suoritetaan gVisorissa, microVM:issä (kuten Firecracker, CrossVM) tai Docker-kontteissa käyttäen --security-opt=no-new-privileges ja --read-only -lipukkeita.                                |   1   | D/V  |
| 4.5.2 | Varmista, että hiekkalaatikkoympäristöillä ei ole verkkoyhteyttä (--network=none) tai että niillä on vain localhost-yhteys, ja kaikki ulkoiset pyynnöt on estetty iptables-säännöillä.                                             |   1   | D/V  |
| 4.5.3 | Varmista, että tekoälymallin validointi sisältää automatisoidun red-team -testauksen, jossa on organisaation määrittelemä testikattavuus ja käyttäytymisanalyysi takaovien havaitsemiseksi.                                        |   2   | D/V  |
| 4.5.4 | Varmista, että ennen kuin tekoälymalli otetaan käyttöön tuotannossa, sen hiekkalaatikkotulokset allekirjoitetaan kryptografisesti valtuutettujen tietoturvahenkilöiden toimesta ja tallennetaan muutumattomiin auditointilokeihin. |   2   | D/V  |
| 4.5.5 | Varmista, että hiekkalaatikkoympäristöt tuhotaan ja luodaan uudelleen kullanarvoisista kuvista arviointien välillä täydellisellä tiedostojärjestelmän ja muistin tyhjennyksellä.                                                   |   2   | D/V  |

---

## C4.6 Infrastruktuurin turvallisuuden valvonta

Jatkuvasti skannaa ja valvo infrastruktuuria automaattisen korjauksen ja reaaliaikaisen hälytysjärjestelmän avulla.

|   #   | Description                                                                                                                                                                                                                               | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.6.1 | Varmista, että konttikuvat skannataan organisaation aikataulujen mukaisesti siten, että KRIITTISIÄ haavoittuvuuksia sisältävät kuvat estävät käyttöönoton organisaation riskikynnysten perusteella.                                       |   1   | D/V  |
| 4.6.2 | Varmista, että infrastruktuuri täyttää CIS Benchmarkien tai NIST 800-53 -kontrollien vaatimukset organisaation määrittelemien vaatimustenmukaisuusrajojen mukaisesti ja tarjoaa automaattisen korjauksen epäonnistuneille tarkastuksille. |   1   | D/V  |
| 4.6.3 | Varmista, että KORKEAN tason haavoittuvuudet on korjattu organisaation riskienhallintaaikataulujen mukaisesti hätätoimenpiteillä aktiivisesti hyödynnettyjen CVE:iden osalta.                                                             |   2   | D/V  |
| 4.6.4 | Varmista, että tietoturvahälytykset integroituvat SIEM-alustoihin (Splunk, Elastic tai Sentinel) käyttäen CEF- tai STIX/TAXII-muotoja automaattisen rikastamisen kanssa.                                                                  |   2   |  V   |
| 4.6.5 | Varmista, että infrastruktuurimittarit viedään valvontajärjestelmiin (Prometheus, DataDog) SLA-hallintapaneeleiden ja johdon raportoinnin kanssa.                                                                                         |   3   |  V   |
| 4.6.6 | Varmista, että konfiguraation poikkeamat havaitaan työkaluilla (Chef InSpec, AWS Config) organisaation valvontavaatimusten mukaisesti, ja että luvattomien muutosten automaattinen palautus on käytössä.                                  |   2   | D/V  |

---

## C4.7 AI-infrastruktuurin resurssienhallinta

Estä resurssien loppumisiskut ja varmista reilu resurssien jakautuminen kiintiöiden ja seurannan avulla.

|   #   | Description                                                                                                                                                                                                                              | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.7.1 | Varmista, että GPU/TPU:n käyttöastetta valvotaan ja hälytykset laukaistaan organisaation määrittelemissä kynnysarvoissa sekä että automaattinen skaalaus tai kuormantasapainotus aktivoituu kapasiteetin hallintakäytäntöjen mukaisesti. |   1   | D/V  |
| 4.7.2 | Varmista, että tekoälyn työkuorman mittarit (päätelmän viive, läpimenonopeus, virhesuhteet) kerätään organisaation valvontavaatimusten mukaisesti ja korreloidaan infrastruktuurin käytön kanssa.                                        |   1   | D/V  |
| 4.7.3 | Varmista, että Kubernetes ResourceQuotas tai vastaava rajoittavat yksittäiset työkuormat organisaation resurssien allokointipolitiikkojen mukaisesti siten, että tiukat rajat tulevat voimaan.                                           |   2   | D/V  |
| 4.7.4 | Varmista, että kustannusseuranta seuraa menoja työkuormittain/vuokraajittain organisaation budjettirajojen perusteella annettavilla hälytyksillä ja budjetin ylitysten automaattisilla kontrollitoimilla.                                |   2   |  V   |
| 4.7.5 | Varmista, että kapasiteettisuunnittelu käyttää historiallista dataa organisaation määrittämien ennustejaksojen mukaisesti ja automatisoitua resurssien tarjoamista kysyntäkuvioiden perusteella.                                         |   3   |  V   |
| 4.7.6 | Varmista, että resurssien loppuminen laukaisee piirikytkimet organisaation vastevaatimusten mukaisesti, mukaan lukien kapasiteettipolitiikkoihin perustuva nopeuden rajoitus ja työkuorman eristäminen.                                  |   2   | D/V  |

---

## C4.8 Ympäristön erottelu ja siirto-ohjaukset

Toteuta tiukat ympäristörajoitukset automatisoiduilla edistämisporteilla ja turvallisuusvalidoinnilla.

|   #   | Description                                                                                                                                                                                                                         | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.8.1 | Varmista, että kehitys-, testaus- ja tuotantoympäristöt toimivat erillisissä VPC:issä/VNet:issä ilman yhteisiä IAM-rooleja, tietoturvaryhmiä tai verkkoyhteyksiä.                                                                   |   1   | D/V  |
| 4.8.2 | Varmista, että ympäristön edistäminen vaatii hyväksynnän organisaation määrittämiltä valtuutetuilta henkilöiltä kryptografisilla allekirjoituksilla ja muuttumattomilla auditointilokeilla.                                         |   1   | D/V  |
| 4.8.3 | Varmista, että tuotantoympäristöt estävät SSH-yhteydet, poistavat käytöstä virheenkorjauspisteet ja edellyttävät muutospyyntöjä organisaation etukäteisilmoitusvaatimuksineen paitsi hätätilanteissa.                               |   2   | D/V  |
| 4.8.4 | Varmista, että infrastruktuuri koodina -muutokset vaativat vertaisarvioinnin, automaattisen testauksen ja turvallisuustarkastuksen ennen yhdistämistä päähaaraan.                                                                   |   2   | D/V  |
| 4.8.5 | Varmista, että ei-tuotantotiedot on anonymisoitu organisaation tietosuojavaatimusten mukaisesti, synteettisen datan generoinnilla tai täydellisellä datan peittämisellä, johon kuuluu henkilötunnistettavien tietojen (PII) poisto. |   2   | D/V  |
| 4.8.6 | Varmista, että siirtymäportit sisältävät automatisoidut turvallisuustestit (SAST, DAST, konttien skannaus), ja hyväksyntää varten vaaditaan nolla kriittistä havaintoa.                                                             |   2   | D/V  |

---

## C4.9 Infrastruktuurin varmuuskopiointi ja palautus

Varmista infrastruktuurin kestävyys automatisoitujen varmuuskopioiden, testattujen palautusmenetelmien ja katastrofipalautusominaisuuksien avulla.

|   #   | Description                                                                                                                                                                                               | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.9.1 | Varmista, että infrastruktuurin kokoonpanot varmuuskopioidaan organisaation varmuuskopiointiaikataulujen mukaisesti maantieteellisesti erillisiin alueisiin 3-2-1-varmuuskopiointistrategian mukaisesti.  |   1   | D/V  |
| 4.9.2 | Varmista, että varmuuskopiointijärjestelmät toimivat eristetyissä verkoissa, joissa on erilliset käyttöoikeustiedot ja erillään oleva tallennustila kiristysohjelmasuojauksen vuoksi.                     |   2   | D/V  |
| 4.9.3 | Varmista, että palautusmenettelyt testataan ja validoidaan automatisoidun testauksen avulla organisaation aikataulujen mukaisesti siten, että RTO- ja RPO-tavoitteet täyttävät organisaation vaatimukset. |   2   |  V   |
| 4.9.4 | Varmista, että katastrofipalautus sisältää tekoälykohtaiset toimintasuunnitelmat, joissa on mallipainojen palautus, GPU-klusterin uudelleenrakentaminen ja palveluiden riippuvuuskartoitus.               |   3   |  V   |

---

## C4.10 Infrastruktuurin vaatimustenmukaisuus ja hallinto

Ylläpidä säädösten noudattamista jatkuvan arvioinnin, dokumentoinnin ja automaattisten valvontamekanismien avulla.

|   #    | Description                                                                                                                                                                                        | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.10.1 | Varmista, että infrastruktuurin vaatimustenmukaisuus arvioidaan organisaation aikataulujen mukaisesti SOC 2:n, ISO 27001:n tai FedRAMP-ohjausten mukaisesti automatisoidulla todisteiden keruulla. |   2   | D/V  |
| 4.10.2 | Varmista, että infrastruktuuridokumentaatio sisältää verkon kaaviot, tietovirtojen kartat ja uhkamallit, jotka on päivitetty organisaation muutoshallintavaatimusten mukaisesti.                   |   2   |  V   |
| 4.10.3 | Varmista, että infrastruktuurimuutokset käyvät läpi automatisoidun vaatimustenmukaisuuden vaikutusten arvioinnin korkean riskin muutoksille tarkoitettujen sääntelyhyväksyntätyönkulkujen kanssa.  |   3   | D/V  |

---

## C4.11 AI-laitteiston suojaus

Turvaa AI-spesifiset laitteistokomponentit, mukaan lukien GPU:t, TPU:t ja erikoistuneet AI-kiihdyttimet.

|   #    | Description                                                                                                                                                                                                 | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.11.1 | Varmista, että tekoälykiihdyttimen laiteohjelmisto (GPU BIOS, TPU-laiteohjelmisto) on varmennettu kryptografisilla allekirjoituksilla ja päivitetty organisaation korjaushallinnan aikataulujen mukaisesti. |   2   | D/V  |
| 4.11.2 | Varmista, että ennen työkuorman suorittamista tekoälykiihdyttimen eheyttä validoidaan laitteistotodennuksella käyttäen TPM 2.0:aa, Intel TXT:tä tai AMD SVM:ää.                                             |   2   | D/V  |
| 4.11.3 | Varmista, että GPU-muisti on erotettu työnkuormien välillä käyttämällä SR-IOV:ta, MIG:iä (Multi-Instance GPU) tai vastaavaa laitteistopohjaista jakamista, jossa on muistinpuhdistus työn välillä.          |   2   | D/V  |
| 4.11.4 | Varmista, että tekoälylaitteiston toimitusketju sisältää alkuperän varmennuksen valmistajan todistuksilla ja jälkiä osoittavan pakkauksen tarkistuksen.                                                     |   3   |  V   |
| 4.11.5 | Varmista, että laitteistoturvamoduulit (HSM) suojaavat tekoälymallin painot ja salausavaimet FIPS 140-2 Taso 3 tai Common Criteria EAL4+ -sertifioinnin mukaisesti.                                         |   3   | D/V  |

---

## C4.12 Reuna- ja hajautettu tekoälyinfrastruktuuri

Turvalliset hajautetut tekoälyn käyttöönotot, mukaan lukien reunalaskenta, liittoutunut oppiminen ja monipaikkaiset arkkitehtuurit.

|   #    | Description                                                                                                                                                                                      | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 4.12.1 | Varmista, että reunalaitteet todennetaan keskusjärjestelmään käyttämällä molemminpuolista TLS:ää laitevarmenteilla, jotka kierrätetään organisaation varmenteiden hallintapolitiikan mukaisesti. |   2   | D/V  |
| 4.12.2 | Varmista, että reunalaitteet toteuttavat suojatun käynnistyksen vahvistetuilla allekirjoituksilla ja palautussuojausominaisuudella, joka estää laiteohjelmiston takaisinversion hyökkäykset.     |   2   | D/V  |
| 4.12.3 | Varmista, että hajautettu tekoälyn koordinointi käyttää bysanttilaisvikakestävää konsensusalgoritmia, jossa on osallistujien vahvistus ja haitallisten solmujen tunnistus.                       |   3   | D/V  |
| 4.12.4 | Varmista, että reunasta pilveen -viestintä sisältää kaistanleveyden rajoituksen, tietojen pakkaamisen ja offline-toimintamahdollisuudet turvallisen paikallisen tallennuksen kanssa.             |   3   | D/V  |

---

## C4.13 Monipilvipalvelu- ja hybridi-infrastruktuurin turvallisuus

Turvaa tekoälysovellukset useiden pilvipalveluntarjoajien ja hybridi pilvi-paikallisten käyttöönottojen välillä.

|   #    | Description                                                                                                                                                                                                                                 | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.13.1 | Varmista, että monipilvi-AI-ratkaisut käyttävät pilviriippumatonta identiteetin yhdistämistä (OIDC, SAML) ja keskitettyä politiikan hallintaa eri tarjoajien välillä.                                                                       |   2   | D/V  |
| 4.13.2 | Varmista, että pilvienvälisessä datansiirrossa käytetään päästä päähän -salausta, jossa avaimet hallinnoidaan asiakkaan toimesta, ja että tietojen sijaintia koskevat säädökset toteutetaan kunkin lainkäyttöalueen vaatimusten mukaisesti. |   2   | D/V  |
| 4.13.3 | Varmista, että hybridi-pilvin tekoälytyökuormat toteuttavat johdonmukaiset turvallisuuspolitiikat paikallisissa ja pilviympäristöissä yhdistetyllä valvonnalla ja hälytyksillä.                                                             |   2   | D/V  |
| 4.13.4 | Varmista, että pilvipalveluntarjoajan lukkiutumisen estäminen sisältää siirrettävän infrastruktuurin koodina, standardoidut API:t ja tiedon vientiominaisuudet muunnostyökaluineen.                                                         |   3   |  V   |
| 4.13.5 | Varmista, että monipilvi-kustannusten optimointiin sisältyy tietoturvakontrolleja, jotka estävät resurssien leviämisen sekä luvattomat pilvien väliset tietoliikennemaksut.                                                                 |   3   |  V   |

---

## C4.14 Infrastruktuurin automaatio ja GitOpsin tietoturva

Suojaa infrastruktuurin automaatioputket ja GitOps-työnkulut tekoälyn infrastruktuurin hallintaan.

|   #    | Description                                                                                                                                                                                                                                 | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.14.1 | Varmista, että GitOps-repositoriot vaativat allekirjoitettuja committeja GPG-avaimilla ja että haarasuojaukset estävät suorat pushit päähaaroihin.                                                                                          |   2   | D/V  |
| 4.14.2 | Varmista, että infrastruktuurin automaatio sisältää poikkeamien tunnistuksen, jonka yhteydessä on automaattinen korjaus ja palautusmahdollisuudet, jotka käynnistyvät organisaation vastausvaatimusten mukaisesti luvattomille muutoksille. |   2   | D/V  |
| 4.14.3 | Varmista, että automatisoitu infrastruktuurin käyttöönotto sisältää tietoturvapolitiikan validoinnin ja estää käyttöönoton, jos kokoonpano ei ole vaatimusten mukainen.                                                                     |   2   | D/V  |
| 4.14.4 | Varmista, että infrastruktuurin automaation salaisuuksia hallitaan ulkoisten salaisuuksien operaattoreiden (External Secrets Operator, Bank-Vaults) kautta automaattisella vaihtamisella.                                                   |   2   | D/V  |
| 4.14.5 | Varmista, että itseparantuva infrastruktuuri sisältää turvallisuustapahtumien korrelaation automatisoidulla häiriötilanteiden käsittelyllä ja sidosryhmien ilmoitusprosessien työnkuluilla.                                                 |   3   |  V   |

---

## C4.15 Kvanttivarmennettu infrastruktuurin turvallisuus

Valmistele tekoälyn infrastruktuuri kvanttilaskennan uhkia varten postkvanttisalauksen ja kvanttiturvallisten protokollien avulla.

|   #    | Description                                                                                                                                                                                                          | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.15.1 | Varmista, että tekoälyn infrastruktuuri toteuttaa NIST:n hyväksymiä jälkikvanttisia kryptografisia algoritmeja (CRYSTALS-Kyber, CRYSTALS-Dilithium, SPHINCS+) avaintenvaihtoon ja digitaalisille allekirjoituksille. |   3   | D/V  |
| 4.15.2 | Varmista, että kvanttisalauksen avaintenjakelujärjestelmät (QKD) on toteutettu korkeaturvallisiin tekoälyn viestintöihin kvanttiturvallisilla avainhallintaprotokollilla.                                            |   3   | D/V  |
| 4.15.3 | Varmista, että kryptografisen ketteryyden kehykset mahdollistavat nopean siirtymisen uusiin postkvanttialgoritmeihin automatisoidun varmenteiden ja avainten kierron avulla.                                         |   3   | D/V  |
| 4.15.4 | Varmista, että kvanttihyökkäysten uhat arvioidaan AI-infrastruktuurin haavoittuvuuden osalta kvanttihyökkäyksiin, sisältäen dokumentoidut siirtymäaikataulut ja riskinarviot.                                        |   3   |  V   |
| 4.15.5 | Varmista, että hybridit klassisen ja kvanttikryptografian järjestelmät tarjoavat syvyyspuolustuksen kvanttisiirtymäkauden aikana suorituskyvyn seurannan avulla.                                                     |   3   | D/V  |

---

## C4.16 Luottamuksellinen laskenta ja suojatut enklavit

Suojaa tekoälytyökuormat ja mallipainot laitteistopohjaisten luotettujen suoritusalustojen ja luottamuksellisten laskentateknologioiden avulla.

|   #    | Description                                                                                                                                                                          | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 4.16.1 | Varmista, että arkaluonteiset tekoälymallit suoritetaan Intel SGX -yksiköissä, AMD SEV-SNP:ssä tai ARM TrustZone -ympäristössä salatun muistin ja varmennuksen kanssa.               |   3   | D/V  |
| 4.16.2 | Varmista, että luottamukselliset kontit (Kata Containers, gVisor luottamuksellisella laskennalla) eristävät tekoälykuormat laitteistolla valvotulla muistin salauksella.             |   3   | D/V  |
| 4.16.3 | Varmista, että etätodentaminen vahvistaa kotelon eheyden ennen tekoälymallien lataamista kryptografisella todisteella suorituksen ympäristön aitoudesta.                             |   3   | D/V  |
| 4.16.4 | Varmista, että luottamukselliset tekoälyn päättelypalvelut estävät mallin poiminnan salatun laskennan avulla, jossa mallin painot on suojattu ja suoritus suojattu.                  |   3   | D/V  |
| 4.16.5 | Varmista, että luotettu ajoitusympäristö hallinnoi turvallisen ympäristön elinkaarta etävarmennuksen ja salattujen viestintäkanavien avulla.                                         |   3   | D/V  |
| 4.16.6 | Varmista, että turvallinen moniosapuolinen laskenta (SMPC) mahdollistaa yhteistyöhön perustuvan tekoälyn koulutuksen paljastamatta yksittäisiä tietojoukkoja tai mallin parametreja. |   3   | D/V  |

---

## C4.17 Nollatietoinen infrastruktuuri

Toteuta nollatiedon todistejärjestelmiä yksityisyyttä suojaavaa tekoälyn varmennusta ja todennusta varten paljastamatta arkaluonteisia tietoja.

|   #    | Description                                                                                                                                                                                                 | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.17.1 | Varmista, että nollahäiriötodistukset (ZK-SNARKit, ZK-STARKit) validoivat tekoälymallin eheyden ja koulutuksen alkuperän paljastamatta mallin painoja tai koulutusdataa.                                    |   3   | D/V  |
| 4.17.2 | Varmista, että nollatietotodistuksiin perustuvat tunnistusjärjestelmät mahdollistavat yksityisyyttä suojaavan käyttäjän vahvistamisen tekoälypalveluissa paljastamatta henkilöllisyyteen liittyviä tietoja. |   3   | D/V  |
| 4.17.3 | Varmista, että yksityinen joukkojen leikkaus (PSI) -protokollat mahdollistavat turvallisen tietojen yhdistämisen hajautetussa tekoälyssä paljastamatta yksittäisiä tietojoukkoja.                           |   3   | D/V  |
| 4.17.4 | Varmista, että nollatietoinen koneoppiminen (ZKML) -järjestelmät mahdollistavat varmennettavat tekoälypäätelmät kryptografisella todistuksella oikeasta laskennasta.                                        |   3   | D/V  |
| 4.17.5 | Varmista, että ZK-rollupit tarjoavat skaalautuvan, yksityisyyttä suojaavan tekoälytransaktioiden käsittelyn ryhmätarkistuksella ja vähentyneellä laskentakuormalla.                                         |   3   | D/V  |

---

## C4.18 Sivukanavahyökkäysten ehkäisy

Suojaa tekoälyn infrastruktuuri ajoitus-, virta-, sähkömagneettisilta ja välimuistiin perustuvilta sivukanavahyökkäyksiltä, jotka voivat vuotaa arkaluontoista tietoa.

|   #    | Description                                                                                                                                                          | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.18.1 | Varmista, että tekoälyn päättelyaika on normalisoitu käyttäen vakioaikaisia algoritmeja ja täyttöjä estämään ajoitukseen perustuvat mallin uuttamisiskut.            |   3   | D/V  |
| 4.18.2 | Varmista, että virran analyysisuojaukseen sisältyy kohinasyöttö, virtalinjan suodatus ja satunnaistetut suorituksen kuvioinnit AI-laitteistolle.                     |   3   | D/V  |
| 4.18.3 | Varmista, että välimuistiin perustuva sivukanavahaitta ontorjunta käyttää välimuistin erottelua, satunnaistamista ja tyhjennyskäskyjä estääkseen tiedon vuotamisen.  |   3   | D/V  |
| 4.18.4 | Varmista, että sähkömagneettinen säteilynsuojaus sisältää suojauksen, signaalin suodatuksen ja satunnaistetun käsittelyn TEMPEST-tyyppisten hyökkäysten estämiseksi. |   3   | D/V  |
| 4.18.5 | Varmista, että mikr arkkitehtoniset sivukanavasuojaukset sisältävät spekulatiivisen suorituksen hallinnan ja muistin käyttötapojen peittämisen.                      |   3   | D/V  |

---

## C4.19 Neuromorfinen ja erikoistunut tekoälylaitteiston turvallisuus

Varmista nousevien tekoälylaitteistojen arkkitehtuurien, kuten neuromorfisten sirujen, FPGA-piirien, räätälöityjen ASIC-piirien ja optisten laskentajärjestelmien turvallisuus.

|   #    | Description                                                                                                                                                                                                      | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.19.1 | Varmista, että neuromorfisen sirun turvallisuus sisältää piikkikuvion salauksen, synaptisen painon suojauksen ja laitteistopohjaisen oppimissäännön validoinnin.                                                 |   3   | D/V  |
| 4.19.2 | Varmista, että FPGA-pohjaiset tekoälykiihdyttimet toteuttavat bitstream-salauksen, manipulaationestomekanismit ja turvallisen konfiguraation latauksen todennetuilla päivityksillä.                              |   3   | D/V  |
| 4.19.3 | Varmista, että räätälöity ASIC-turvallisuus sisältää sirulle integroidut turvallisuusprosessorit, laitteistopohjaisen luottamuksen juuren ja turvallisen avainten säilytyksen, jossa on manipuloinnin tunnistus. |   3   | D/V  |
| 4.19.4 | Varmista, että optiset laskentajärjestelmät toteuttavat quantum-turvallisen optisen salauksen, suojatun fotonisen kytkennän ja suojatun optisen signaalinkäsittelyn.                                             |   3   | D/V  |
| 4.19.5 | Varmista, että hybridi analogi-digitaalinen tekoälysiru sisältää turvallisen analogisen laskennan, suojatun painovarastoinnin ja vahvistetun analogi-digitaalisen muunnoksen.                                    |   3   | D/V  |

---

## C4.20 Yksityisyyttä säilyttävä laskentainfrastruktuuri

Ota käyttöön infrastruktuurin valvontatoimet yksityisyyttä säilyttävän laskennan varmistamiseksi, jotta arkaluontoiset tiedot suojataan tekoälyn käsittelyn ja analyysin aikana.

|   #    | Description                                                                                                                                                                                     | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.20.1 | Varmista, että homomorfinen salausinfrastruktuuri mahdollistaa salausten laskennan arkaluonteisilla tekoälykuormilla kryptografisella eheyden varmistuksella ja suorituskyvyn valvonnalla.      |   3   | D/V  |
| 4.20.2 | Varmista, että yksityiset tiedonhakujärjestelmät mahdollistavat tietokantakyselyt paljastamatta kyselykuvioita kryptografisella suojausmenetelmällä pääsykuvioille.                             |   3   | D/V  |
| 4.20.3 | Varmista, että turvalliset moniosapuolten laskentaprotokollat mahdollistavat yksityisyyttä suojaavan tekoälyn päätelmän ilman, että yksittäiset syötteet tai välivaiheen laskelmat paljastuvat. |   3   | D/V  |
| 4.20.4 | Varmista, että yksityisyyttä suojaava avaintenhallinta sisältää hajautetun avainten generoinnin, kynnyskriptografian ja turvallisen avainten kierron laitteistotukea hyödyntäen.                |   3   | D/V  |
| 4.20.5 | Varmista, että yksityisyyttä suojaavan laskennan suorituskyky on optimoitu eräajoilla, välimuistilla ja laitteistokiihdytyksellä samalla kun säilytetään kryptografiset turvallisuustakuuet.    |   3   | D/V  |

---

## C4.15 Agenttikehyksen pilvijärjestelmän integroinnin turvallisuus ja hybridi- käyttöönotto

Turvallisuusvalvontatoimet pilveen integroiduille agenttikehyksille hybridi paikallinen/pilvi-arkkitehtuureissa.

|   #    | Description                                                                                                                    | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 4.15.1 | Varmista, että pilvitallennusintegraatio käyttää päästä päähän -salausta ja agentin hallitsemaa avainhallintaa.                |   1   | D/V  |
| 4.15.2 | Varmista, että hybridi-jakelun turvallisuusrajat on selkeästi määritelty ja että viestintäkanavat ovat salattuja.              |   2   | D/V  |
| 4.15.3 | Varmista, että pilviresurssien käyttöoikeudet sisältävät nollaluottamuksen varmennuksen jatkuvalla autentikoinnilla.           |   2   | D/V  |
| 4.15.4 | Varmista, että tietojen sijaintivaatimuksia noudatetaan salausteknisellä tallennuspaikkojen todentamisella.                    |   3   | D/V  |
| 4.15.5 | Varmista, että pilvipalveluntarjoajan turvallisuusarvioinnit sisältävät agenttikohtaisen uhkamallinnuksen ja riskinarvioinnin. |   3   | D/V  |

---

## Viitteet

* [NIST Cybersecurity Framework 2.0](https://www.nist.gov/cyberframework)
* [CIS Controls v8](https://www.cisecurity.org/controls/v8)
* [OWASP Container Security Verification Standard](https://github.com/OWASP/Container-Security-Verification-Standard)
* [Kubernetes Security Best Practices](https://kubernetes.io/docs/concepts/security/)
* [SLSA Supply Chain Security Framework](https://slsa.dev/)
* [NIST SP 800-190: Application Container Security Guide](https://csrc.nist.gov/publications/detail/sp/800-190/final)
* [Cloud Security Alliance: Cloud Controls Matrix](https://cloudsecurityalliance.org/research/cloud-controls-matrix/)
* [ENISA: Secure Infrastructure Design](https://www.enisa.europa.eu/topics/critical-information-infrastructures-and-services)
* [NIST SP 800-53: Security Controls for Federal Information Systems](https://csrc.nist.gov/publications/detail/sp/800-53/rev-5/final)
* [ISO 27001:2022 Information Security Management](https://www.iso.org/standard/27001)
* [NIST AI Risk Management Framework](https://www.nist.gov/itl/ai-risk-management-framework)
* [CIS Kubernetes Benchmark](https://www.cisecurity.org/benchmark/kubernetes)
* [FIPS 140-2 Security Requirements](https://csrc.nist.gov/publications/detail/fips/140/2/final)
* [NIST SP 800-207: Zero Trust Architecture](https://csrc.nist.gov/publications/detail/sp/800-207/final)
* [IEEE 2857: Privacy Engineering for AI Systems](https://standards.ieee.org/ieee/2857/7273/)
* [NIST SP 800-161: Cybersecurity Supply Chain Risk Management](https://csrc.nist.gov/publications/detail/sp/800-161/rev-1/final)
* [NIST Post-Quantum Cryptography Standards](https://csrc.nist.gov/Projects/post-quantum-cryptography)
* [Intel SGX Developer Guide](https://www.intel.com/content/www/us/en/developer/tools/software-guard-extensions/overview.html)
* [AMD SEV-SNP White Paper](https://www.amd.com/system/files/TechDocs/SEV-SNP-strengthening-vm-isolation-with-integrity-protection-and-more.pdf)
* [ARM TrustZone Technology](https://developer.arm.com/ip-products/security-ip/trustzone)
* [ZK-SNARKs: A Gentle Introduction](https://blog.ethereum.org/2016/12/05/zksnarks-in-a-nutshell/)
* [NIST SP 800-57: Cryptographic Key Management](https://csrc.nist.gov/publications/detail/sp/800-57-part-1/rev-5/final)
* [Side-Channel Attack Countermeasures](https://link.springer.com/book/10.1007/978-3-319-75268-6)
* [Neuromorphic Computing Security Challenges](https://ieeexplore.ieee.org/document/9458103)
* [FPGA Security: Fundamentals, Evaluation, and Countermeasures](https://link.springer.com/book/10.1007/978-3-319-90385-9)
* [Microsoft SEAL: Homomorphic Encryption Library](https://github.com/Microsoft/SEAL)
* [HElib: Homomorphic Encryption Library](https://github.com/homenc/HElib)
* [PALISADE Lattice Cryptography Library](https://palisade-crypto.org/)
* [Differential Privacy: A Survey of Results](https://link.springer.com/chapter/10.1007/978-3-540-79228-4_1)
* [Secure Aggregation for Federated Learning](https://eprint.iacr.org/2017/281.pdf)
* [Private Information Retrieval: Concepts and Constructions](https://link.springer.com/book/10.1007/978-3-030-16234-8)

