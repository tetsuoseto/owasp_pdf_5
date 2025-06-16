# C5 Åtkomstkontroll och identitet för AI-komponenter och användare

## Kontrollmål

Effektiv åtkomstkontroll för AI-system kräver robust identitetshantering, kontextmedveten auktorisering och körningstidshantering enligt zero-trust-principer. Dessa kontroller säkerställer att människor, tjänster och autonoma agenter endast interagerar med modeller, data och beräkningsresurser inom uttryckligen beviljade områden, med kontinuerlig verifiering och revisionsmöjligheter.

---

## C5.1 Identitetshantering och autentisering

Etablera kryptografiskt säkrade identiteter för alla enheter med multifaktorautentisering för privilegierade operationer.

|   #   | Description                                                                                                                                                                                                                                                                  | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 5.1.1 | Verifiera att alla mänskliga användare och tjänsteprincipaler autentiserar sig genom en centraliserad företagsidentitetsleverantör (IdP) med hjälp av OIDC/SAML-protokoll med unika identitets-till-token-kartläggningar (inga delade konton eller autentiseringsuppgifter). |   1   | D/V  |
| 5.1.2 | Verifiera att hög-riskoperationer (modellimplementering, viktexport, åtkomst till träningsdata, ändringar i produktionskonfiguration) kräver multifaktorautentisering eller stegvis autentisering med sessionsvalidering.                                                    |   1   | D/V  |
| 5.1.3 | Verifiera att nya huvudansvariga genomgår identitetskontroll i enlighet med NIST 800-63-3 IAL-2 eller motsvarande standarder innan de får tillgång till produktionssystemet.                                                                                                 |   2   |  D   |
| 5.1.4 | Verifiera att åtkomstgranskningar genomförs kvartalsvis med automatiserad detektion av inaktiva konton, implementering av byte av autentiseringsuppgifter och arbetsflöden för avveckling av åtkomst.                                                                        |   2   |  V   |
| 5.1.5 | Verifiera att federerade AI-agenter autentiserar via signerade JWT-påståenden som har en maximal livslängd på 24 timmar och inkluderar kryptografiskt bevis på ursprung.                                                                                                     |   3   | D/V  |

---

## C5.2 Resursauktorisation och minsta privilegium

Implementera detaljerade åtkomstkontroller för alla AI-resurser med explicita behörighetsmodeller och revisionsspår.

|   #   | Description                                                                                                                                                                                                                             | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 5.2.1 | Verifiera att varje AI-resurs (datamängder, modeller, slutpunkter, vektorsamlingar, inbäddningsindex, beräkningsinstanser) tillämpar rollbaserade åtkomstkontroller med uttryckliga tillåtelselistor och standardprinciper för nekande. |   1   | D/V  |
| 5.2.2 | Verifiera att principerna för minimal behörighet tillämpas som standard för tjänstekonton, med start från läsbehörighet, och att dokumenterad affärsmässig motivering krävs för skrivbehörighet.                                        |   1   | D/V  |
| 5.2.3 | Verifiera att alla ändringar i åtkomstkontrollen är kopplade till godkända ändringsförfrågningar och loggas oföränderligt med tidsstämplar, aktörsidentiteter, resursidentifierare och behörighetsdifferenser.                          |   1   |  V   |
| 5.2.4 | Verifiera att dataklassificeringsetiketter (PII, PHI, exportkontrollerad, proprietär) automatiskt överförs till härledda resurser (embeddingar, promptcache, modellutdata) med konsekvent policyhantering.                              |   2   |  D   |
| 5.2.5 | Verifiera att obehöriga åtkomstförsök och händelser av privilegieeskalering utlöser realtidsvarningar med kontextuell metadata till SIEM-system inom 5 minuter.                                                                         |   2   | D/V  |

---

## C5.3 Dynamisk Policyutvärdering

Distribuera attributbaserade åtkomstkontrollmotorer (ABAC) för kontextmedvetna auktoriseringsbeslut med revisionsmöjligheter.

|   #   | Description                                                                                                                                                                                                       | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 5.3.1 | Verifiera att auktorisationsbeslut är externaliserade till en dedikerad policymotor (OPA, Cedar eller motsvarande) som är åtkomlig via autentiserade API:er med kryptografiskt integritetsskydd.                  |   1   | D/V  |
| 5.3.2 | Verifiera att policyer utvärderar dynamiska attribut vid körning inklusive användarens behörighetsnivå, resursens känslighetsklassificering, begärans kontext, hyresgästsisolering och tidsmässiga begränsningar. |   1   | D/V  |
| 5.3.3 | Verifiera att policysdefinitioner är versionskontrollerade, granskas av kollegor och valideras genom automatiserade tester i CI/CD-pipelines innan produktsättning.                                               |   2   |  D   |
| 5.3.4 | Verifiera att policyevalueringsresultat inkluderar strukturerade beslut-rationaler och överförs till SIEM-system för korrelationsanalys och efterlevnadsrapportering.                                             |   2   |  V   |
| 5.3.5 | Verifiera att policy cache time-to-live (TTL)-värden inte överstiger 5 minuter för resurser med hög känslighet och 1 timme för standardresurser med cache ogiltigförklaringsfunktioner.                           |   3   | D/V  |

---

## C5.4 Säkerhetsgenomförande vid frågetidpunkten

Implementera säkerhetskontroller på databasskiktet med obligatorisk filtrering och radnivåsäkerhetspolicyer.

|   #   | Description                                                                                                                                                                                                                                | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 5.4.1 | Verifiera att alla vektordatabas- och SQL-frågor inkluderar obligatoriska säkerhetsfilter (tenant-ID, känslighetsetiketter, användaromfång) som tillämpas på databasmotornivå, inte i applikationskoden.                                   |   1   | D/V  |
| 5.4.2 | Verifiera att radnivåsäkerhet (RLS)-policyer och fältnivåmaskering är aktiverade med policysärvning för alla vektordatabaser, sökindex och träningsdatasätt.                                                                               |   1   | D/V  |
| 5.4.3 | Verifiera att misslyckade auktoriseringsbedömningar förhindrar "förvirrade ombud-attacker" genom att omedelbart avbryta förfrågningar och returnera tydliga auktoriseringsfelkoder istället för att returnera tomma resultatuppsättningar. |   2   |  D   |
| 5.4.4 | Verifiera att policyutvärderingslatens övervakas kontinuerligt med automatiska varningar för tidsgränstillstånd som kan möjliggöra att auktorisering omgås.                                                                                |   2   |  V   |
| 5.4.5 | Verifiera att mekanismer för omförsök av förfrågningar omprövar auktoriseringspolicyer för att ta hänsyn till dynamiska ändringar av behörigheter inom aktiva användarsessioner.                                                           |   3   | D/V  |

---

## C5.5 Utdatafiltrering och förebyggande av dataförlust

Implementera efterbehandlingskontroller för att förhindra obehörig dataexponering i AI-genererat innehåll.

|   #   | Description                                                                                                                                                                                                         | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 5.5.1 | Verifiera att filtreringsmekanismer efter inferens skannar och tar bort obehörig personligt identifierbar information (PII), klassificerad information och proprietär data innan innehåll levereras till begärarna. |   1   | D/V  |
| 5.5.2 | Verifiera att citat, referenser och källhänvisningar i modellutdata kontrolleras mot anroparens behörigheter och tas bort om obehörig åtkomst upptäcks.                                                             |   1   | D/V  |
| 5.5.3 | Verifiera att begränsningar för utdataformat (saniterade PDF-filer, metadata-fria bilder, godkända filtyper) upprätthålls baserat på användarens behörighetsnivåer och dataklassificeringar.                        |   2   |  D   |
| 5.5.4 | Verifiera att maskeringsalgoritmer är deterministiska, versionskontrollerade och upprätthåller revisionsloggar för att stödja regelefterlevnadsundersökningar och rättsmedicinska analyser.                         |   2   |  V   |
| 5.5.5 | Verifiera att högrisk-hanteringshändelser genererar adaptiva loggar som inkluderar kryptografiska hashvärden av originalinnehållet för forensisk återhämtning utan dataexponering.                                  |   3   |  V   |

---

## C5.6 Multi-Tenant-isolering

Säkerställ kryptografisk och logisk isolering mellan hyresgäster i delad AI-infrastruktur.

|   #   | Description                                                                                                                                                                                           | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 5.6.1 | Verifiera att minnesutrymmen, inbäddningslagringar, cacheposter och temporära filer är namnrymdsseparerade per hyresgäst med säker borttagning vid radering av hyresgäst eller avslutning av session. |   1   | D/V  |
| 5.6.2 | Verifiera att varje API-förfrågan inkluderar en autentiserad hyresgästadministratör som är kryptografiskt validerad mot sessionskontext och användarrättigheter.                                      |   1   | D/V  |
| 5.6.3 | Verifiera att nätverkspolicys implementerar standardavvisningsregler för kommunikation mellan hyresgäster inom servicemeshar och plattformar för containerorkestrering.                               |   2   |  D   |
| 5.6.4 | Verifiera att krypteringsnycklar är unika för varje hyresgäst med kundhanterade nycklar (CMK) och kryptografisk isolering mellan hyresgästernas datalager.                                            |   3   |  D   |

---

## C5.7 Auktorisering av autonoma agenter

Kontrollera behörigheter för AI-agenter och autonoma system genom avgränsade kapabilitetstoken och kontinuerlig auktorisation.

|   #   | Description                                                                                                                                                                                                               | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 5.7.1 | Verifiera att autonoma agenter erhåller avgränsade behörighetstoken som tydligt uppräkna tillåtna åtgärder, åtkomliga resurser, tidsgränser och operativa restriktioner.                                                  |   1   | D/V  |
| 5.7.2 | Verifiera att hög-riskfunktioner (åtkomst till filsystmet, kodkörning, externa API-anrop, finansiella transaktioner) är inaktiverade som standard och kräver uttryckliga tillstånd för aktivering med affärsmotiveringar. |   1   | D/V  |
| 5.7.3 | Verifiera att kapabilitetstoken är bundna till användarsessioner, inkluderar kryptografiskt integritetsskydd och säkerställ att de inte kan sparas eller återanvändas i offline-scenarier.                                |   2   |  D   |
| 5.7.4 | Verifiera att agentinitierade åtgärder genomgår sekundär auktorisation via ABAC-policynmotorn med full kontextevaluering och revisionsloggning.                                                                           |   2   |  V   |
| 5.7.5 | Verifiera att agentens fellägen och undantagshantering inkluderar information om kapacitetsomfång för att stödja incidentanalys och rättsmedicinsk undersökning.                                                          |   3   |  V   |

---

## Referenser

### Standarder och ramverk

* [NIST SP 800-63-3: Digital Identity Guidelines](https://pages.nist.gov/800-63-3/)
* [Zero Trust Architecture – NIST SP 800-207](https://nvlpubs.nist.gov/nistpubs/specialpublications/NIST.SP.800-207.pdf)
* [OWASP Application Security Verification Standard (AISVS)](https://owasp.org/www-project-application-security-verification-standard/)
  ​
### Implementeringsguider

* [Identity and Access Management in the AI Era: 2025 Guide – IDSA](https://www.idsalliance.org/blog/identity-and-access-management-in-the-ai-era-2025-guide/)
* [Attribute-Based Access Control with OPA – Permify](https://medium.com/permify-tech-blog/attribute-based-access-control-abac-implementation-with-open-policy-agent-opa-b47052248f29)
* [How We Designed Cedar to Be Intuitive, Fast, and Safe – AWS](https://aws.amazon.com/blogs/security/how-we-designed-cedar-to-be-intuitive-to-use-fast-and-safe/)
  ​
### AI-specifik säkerhet

* [Row Level Security in Vector DBs for RAG – Bluetuple.ai](https://medium.com/bluetuple-ai/implementing-row-level-security-in-vector-dbs-for-rag-applications-fdbccb63d464)
* [Tenant Isolation in Multi-Tenant Systems – WorkOS](https://workos.com/blog/tenant-isolation-in-multi-tenant-systems)
* [Handling AI Agent Permissions – Stytch](https://stytch.com/blog/handling-ai-agent-permissions/)
* [OWASP Top 10 for Large Language Model Applications](https://owasp.org/www-project-top-10-for-large-language-model-applications/)

