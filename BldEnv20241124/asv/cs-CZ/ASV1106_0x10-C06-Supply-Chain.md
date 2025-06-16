# C6 Bezpečnost dodavatelského řetězce pro modely, rámce a data

## Řídicí cíl

Útoky na dodavatelský řetězec AI zneužívají modely třetích stran, rámce nebo datové sady k vložení zadních vrátek, zkreslení nebo zranitelného kódu. Tyto kontroly poskytují end-to-end sledovatelnost, správu zranitelností a monitorování k ochraně celého životního cyklu modelu.

---

## C6.1 Ověřování a původ předtrénovaného modelu

Posoudit a ověřit původ modelů třetích stran, licence a skryté chování před jakýmkoli doladěním nebo nasazením.

|   #   | Description                                                                                                                                | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 6.1.1 | Ověřte, že každý třetí modelový artefakt zahrnuje podepsaný záznam původu s identifikací zdrojového úložiště a hash commitu.               |   1   | D/V  |
| 6.1.2 | Ověřte, že modely jsou před importem pomocí automatizovaných nástrojů prohledány na škodlivé vrstvy nebo spouštěče Trójských koní.         |   1   | D/V  |
| 6.1.3 | Ověřte, že doladění transferového učení obstojí v adversariálním hodnocení pro detekci skrytých chování.                                   |   2   |  D   |
| 6.1.4 | Ověřte, zda jsou v položce ML-BOM zaznamenány licenční podmínky modelu, značky pro kontrolu vývozu a prohlášení o původu dat.              |   2   |  V   |
| 6.1.5 | Ověřte, že modely s vysokým rizikem (veřejně nahrané váhy, neověření tvůrci) zůstávají v karanténě až do lidského přezkoumání a schválení. |   3   | D/V  |

---

## C6.2 Skenování rámců a knihoven

Nepřetržitě skenovat rámce a knihovny strojového učení (ML) pro zranitelnosti (CVE) a škodlivý kód, aby byla runtime vrstva bezpečná.

|   #   | Description                                                                                                                 | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 6.2.1 | Ověřte, že CI pipeline spouštějí skenery závislostí na AI rámcích a kritických knihovnách.                                  |   1   | D/V  |
| 6.2.2 | Ověřte, že kritické zranitelnosti (CVSS ≥ 7,0) blokují nasazení do produkčních obrazů.                                      |   1   | D/V  |
| 6.2.3 | Ověřte, že statická analýza kódu probíhá na odvozených nebo dodaných knihovnách strojového učení.                           |   2   |  D   |
| 6.2.4 | Ověřte, že návrhy na upgrade frameworku zahrnují posouzení bezpečnostního dopadu s odkazem na veřejné zdroje CVE.           |   2   |  V   |
| 6.2.5 | Ověřte, že runtime senzory upozorňují na neočekávané načítání dynamických knihoven, které se odchylují od podepsaného SBOM. |   3   |  V   |

---

## C6.3 Připnutí a ověření závislostí

Připněte všechny závislosti na neměnné digesty a opakujte sestavení, aby bylo zaručeno, že artefakty jsou identické a bez zásahů.

|   #   | Description                                                                                                              | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 6.3.1 | Ověřte, že všechny správce balíčků vyžadují pevné určení verzí prostřednictvím zámkových souborů.                        |   1   | D/V  |
| 6.3.2 | Ověřte, že v odkazech na kontejnery jsou používány neměnné digesty místo proměnlivých tagů.                              |   1   | D/V  |
| 6.3.3 | Ověřte, že kontroly reprodukovatelných sestavení porovnávají hashe napříč běhy CI, aby byla zajištěna identická výstupy. |   2   |  D   |
| 6.3.4 | Ověřte, že potvrzení o sestavení jsou uchovávána po dobu 18 měsíců pro auditní sledovatelnost.                           |   2   |  V   |
| 6.3.5 | Ověřte, že expirované závislosti spouštějí automatizované PR pro aktualizaci nebo rozvětvení připnutých verzí.           |   3   |  D   |

---

## C6.4 Vynucení důvěryhodného zdroje

Povolte stahování artefaktů pouze z kryptograficky ověřených zdrojů schválených organizací a zablokujte vše ostatní.

|   #   | Description                                                                                                                | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 6.4.1 | Ověřte, že váhy modelu, datové sady a kontejnery jsou stahovány pouze z schválených domén nebo interních registrů.         |   1   | D/V  |
| 6.4.2 | Ověřte, že podpisy Sigstore/Cosign ověřují identitu vydavatele před tím, než jsou artefakty uloženy do místní cache.       |   1   | D/V  |
| 6.4.3 | Ověřte, že odchozí proxy blokují neautorizované stahování artefaktů, aby byla vynucena politika důvěryhodného zdroje.      |   2   |  D   |
| 6.4.4 | Ověřte, že seznamy povolených repozitářů jsou přezkoumávány čtvrtletně s doložením obchodního odůvodnění pro každý záznam. |   2   |  V   |
| 6.4.5 | Ověřte, že porušení politiky spouští karanténu artefaktů a návrat zpět závislých běhů pipeline.                            |   3   |  V   |

---

## C6.5 Hodnocení rizik souboru dat třetí strany

Vyhodnocujte externí datové sady z hlediska otravy, zaujatosti a právní shody a sledujte je během celého jejich životního cyklu.

|   #   | Description                                                                                                                        | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 6.5.1 | Ověřte, že externí datové sady procházejí hodnocením rizika otravy (například otisk dat, detekce odlehlých hodnot).                |   1   | D/V  |
| 6.5.2 | Ověřte, že metriky zaujatosti (demografická parita, rovné příležitosti) jsou vypočítány před schválením datové sady.               |   1   |  D   |
| 6.5.3 | Ověřte, že původ a licenční podmínky datasetů jsou zachyceny v položkách ML‑BOM.                                                   |   2   |  V   |
| 6.5.4 | Ověřte, že pravidelný monitoring detekuje posun nebo poškození v hostovaných datech.                                               |   2   |  V   |
| 6.5.5 | Ověřte, že nepovolený obsah (autorská práva, osobní identifikační údaje) je před tréninkem odstraněn pomocí automatického čištění. |   3   |  D   |

---

## C6.6 Monitorování útoků na dodavatelský řetězec

Včasně detekujte hrozby v dodavatelském řetězci prostřednictvím zdrojů CVE, analýzy auditních záznamů a simulací červeného týmu.

|   #   | Description                                                                                                                                                                        | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 6.6.1 | Ověřte, že auditní záznamy CI/CD jsou streamovány do SIEM detekcí pro anomální stahování balíčků nebo pozměněné kroky sestavení.                                                   |   1   |  V   |
| 6.6.2 | Ověřte, že hrací knihy pro reakci na incidenty zahrnují postupy pro návrat zpět v případě kompromitovaných modelů nebo knihoven.                                                   |   2   |  D   |
| 6.6.3 | Ověřte, že značky obohacení zpravodajských informací o hrozbách označují indikátory specifické pro strojové učení (např. IoC týkající se poškození modelu) při třídění upozornění. |   3   |  V   |

---

## C6.7 ML-BOM pro modelové artefakty

Generujte a podepisujte podrobné SBOM specifické pro strojové učení (ML-BOMy), aby mohli následní uživatelé ověřit integritu komponent při nasazení.

|   #   | Description                                                                                                                      | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 6.7.1 | Ověřte, že každý modelový artefakt zveřejňuje ML‑BOM, který uvádí datasety, váhy, hyperparametry a licence.                      |   1   | D/V  |
| 6.7.2 | Ověřte, že generování ML-BOM a podepisování Cosign jsou automatizovány v CI a jsou požadovány pro sloučení.                      |   1   | D/V  |
| 6.7.3 | Ověřte, že kontroly úplnosti ML‑BOM selžou a sestavení bude zastaveno, pokud chybí jakákoli metadata komponenty (hash, licence). |   2   |  D   |
| 6.7.4 | Ověřte, že downstream uživatelé mohou dotazovat ML-BOMy přes API pro ověření importovaných modelů při nasazení.                  |   2   |  V   |
| 6.7.5 | Ověřte, že ML‑BOM jsou verzovány a porovnávány, aby bylo možné odhalit neoprávněné úpravy.                                       |   3   |  V   |

---

## Reference

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

