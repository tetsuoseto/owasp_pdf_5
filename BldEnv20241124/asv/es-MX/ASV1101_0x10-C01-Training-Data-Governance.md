# Gobernanza de Datos de Entrenamiento C1 y Gestión de Sesgos

## Objetivo de Control

Los datos de entrenamiento deben ser obtenidos, manejados y mantenidos de manera que se preserve la procedencia, la seguridad, la calidad y la equidad. Hacerlo cumple con las obligaciones legales y reduce los riesgos de sesgo, envenenamiento o violaciones de privacidad a lo largo del ciclo de vida de la IA.

---

## C1.1 Procedencia de los Datos de Entrenamiento

Mantenga un inventario verificable de todos los conjuntos de datos, acepte solo fuentes confiables y registre cada cambio para garantizar la auditabilidad.

|   #   | Description                                                                                                                                                                                                                                                                                  | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.1.1 | Verifique que se mantenga un inventario actualizado de cada fuente de datos de entrenamiento (origen, responsable/propietario, licencia, método de recopilación, restricciones de uso previsto e historial de procesamiento).                                                                |   1   | D/V  |
| 1.1.2 | Verifique que solo se permitan los conjuntos de datos evaluados en cuanto a calidad, representatividad, origen ético y cumplimiento de licencias, reduciendo los riesgos de envenenamiento, sesgos incrustados y violación de la propiedad intelectual.                                      |   1   | D/V  |
| 1.1.3 | Verifique que se aplique la minimización de datos para excluir atributos innecesarios o sensibles.                                                                                                                                                                                           |   1   | D/V  |
| 1.1.4 | Verifique que todos los cambios en el conjunto de datos estén sujetos a un flujo de trabajo de aprobación registrado.                                                                                                                                                                        |   2   | D/V  |
| 1.1.5 | Verifique que la calidad del etiquetado/annotación se garantice mediante la revisión cruzada o consenso entre los revisores.                                                                                                                                                                 |   2   | D/V  |
| 1.1.6 | Verifique que se mantengan "tarjetas de datos" o "hojas de datos para conjuntos de datos" para los conjuntos de datos de entrenamiento significativos, detallando características, motivaciones, composición, procesos de recopilación, preprocesamiento y usos recomendados/desaconsejados. |   2   | D/V  |

---

## C1.2 Seguridad e Integridad de los Datos de Entrenamiento

Restringir el acceso, cifrar los datos en reposo y en tránsito, y validar la integridad para bloquear la manipulación o el robo.

|   #   | Description                                                                                                                                                                                                                                                                                                                                              | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.2.1 | Verifique que los controles de acceso protejan el almacenamiento y las canalizaciones.                                                                                                                                                                                                                                                                   |   1   | D/V  |
| 1.2.2 | Verifique que los conjuntos de datos estén cifrados en tránsito y, para toda la información sensible o personalmente identificable (PII), en reposo, utilizando algoritmos criptográficos y prácticas de gestión de claves estándar en la industria.                                                                                                     |   2   | D/V  |
| 1.2.3 | Verifique que se utilicen hashes criptográficos o firmas digitales para garantizar la integridad de los datos durante el almacenamiento y la transferencia, y que se apliquen técnicas automatizadas de detección de anomalías para proteger contra modificaciones no autorizadas o corrupción, incluidos intentos de envenenamiento de datos dirigidos. |   2   | D/V  |
| 1.2.4 | Verifique que las versiones del conjunto de datos estén rastreadas para permitir la reversión.                                                                                                                                                                                                                                                           |   3   | D/V  |
| 1.2.5 | Verifique que los datos obsoletos se eliminen de forma segura o se anonimicen conforme a las políticas de retención de datos, los requisitos regulatorios y para reducir la superficie de ataque.                                                                                                                                                        |   2   | D/V  |

---

## C1.3 Completitud y Equidad de la Representación

Detectar sesgos demográficos y aplicar mitigaciones para que las tasas de error del modelo sean equitativas entre los grupos.

|   #   | Description                                                                                                                                                                                                                                                                                                                                                                        | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.3.1 | Verifique que los conjuntos de datos sean analizados para detectar desequilibrios representacionales y posibles sesgos en atributos protegidos por la ley (por ejemplo, raza, género, edad) y otras características éticamente sensibles relevantes para el dominio de aplicación del modelo (por ejemplo, estatus socioeconómico, ubicación).                                     |   1   | D/V  |
| 1.3.2 | Verifique que los sesgos identificados se mitiguen mediante estrategias documentadas, como el reequilibrio, la augmentación de datos dirigida, los ajustes algorítmicos (por ejemplo, técnicas de preprocesamiento, procesamiento y posprocesamiento) o el reponderado, y que se evalúe el impacto de la mitigación tanto en la equidad como en el rendimiento general del modelo. |   2   | D/V  |
| 1.3.3 | Verifique que las métricas de equidad post-entrenamiento sean evaluadas y documentadas.                                                                                                                                                                                                                                                                                            |   2   | D/V  |
| 1.3.4 | Verifique que una política de gestión de sesgos en el ciclo de vida asigne responsables y frecuencia de revisión.                                                                                                                                                                                                                                                                  |   3   | D/V  |

---

## C1.4 Calidad, Integridad y Seguridad del Etiquetado de Datos de Entrenamiento

Proteja las etiquetas con cifrado y requiera una revisión dual para las clases críticas.

|   #   | Description                                                                                                                                                                                                                                                                                                          | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.4.1 | Verifique que la calidad del etiquetado/ anotación se garantice mediante directrices claras, revisiones cruzadas por parte de los evaluadores, mecanismos de consenso (por ejemplo, monitoreo del acuerdo entre anotadores) y procesos definidos para resolver discrepancias.                                        |   2   | D/V  |
| 1.4.2 | Verifique que se apliquen hashes criptográficos o firmas digitales a los artefactos de etiquetas para garantizar su integridad y autenticidad.                                                                                                                                                                       |   2   | D/V  |
| 1.4.3 | Verifique que las interfaces y plataformas de etiquetado apliquen controles de acceso estrictos, mantengan registros de auditoría a prueba de manipulaciones de todas las actividades de etiquetado y protejan contra modificaciones no autorizadas.                                                                 |   2   | D/V  |
| 1.4.4 | Verifique que las etiquetas críticas para la seguridad, la protección o la equidad (por ejemplo, la identificación de contenido tóxico, hallazgos médicos críticos) reciban una revisión dual independiente obligatoria o una verificación robusta equivalente.                                                      |   3   | D/V  |
| 1.4.5 | Verifique que la información sensible (incluida la información de identificación personal, PII) capturada inadvertidamente o necesariamente presente en las etiquetas esté redactada, seudonimizada, anonimizada o cifrada tanto en reposo como en tránsito, de acuerdo con los principios de minimización de datos. |   2   | D/V  |
| 1.4.6 | Verifique que las guías de etiquetado e instrucciones sean completas, estén bajo control de versiones y hayan sido revisadas por pares.                                                                                                                                                                              |   2   | D/V  |
| 1.4.7 | Verifique que los esquemas de datos (incluidos los de las etiquetas) estén claramente definidos y controlados por versiones.                                                                                                                                                                                         |   2   | D/V  |
| 1.8.2 | Verifique que los flujos de trabajo de etiquetado externalizados o basados en crowdsourcing incluyan salvaguardas técnicas/procedimentales para garantizar la confidencialidad de los datos, la integridad, la calidad de las etiquetas y prevenir la filtración de datos.                                           |   2   | D/V  |

---

## C1.5 Aseguramiento de la Calidad de los Datos de Entrenamiento

Combine la validación automatizada, las comprobaciones manuales aleatorias y la remediación registrada para garantizar la fiabilidad del conjunto de datos.

|   #   | Description                                                                                                                                                                                                                                                                                                                                      | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 1.5.1 | Verifique que las pruebas automatizadas detecten errores de formato, valores nulos y desviaciones en las etiquetas en cada ingestión o transformación significativa.                                                                                                                                                                             |   1   |  D   |
| 1.5.2 | Verifique que los conjuntos de datos fallidos estén en cuarentena con registros de auditoría.                                                                                                                                                                                                                                                    |   1   | D/V  |
| 1.5.3 | Verifique que las inspecciones puntuales manuales realizadas por expertos en el dominio cubran una muestra estadísticamente significativa (por ejemplo, ≥1% o 1,000 muestras, lo que sea mayor, o según lo determinado por la evaluación de riesgos) para identificar problemas sutiles de calidad que no sean detectados por la automatización. |   2   |  V   |
| 1.5.4 | Verifique que los pasos de remediación estén anexados a los registros de procedencia.                                                                                                                                                                                                                                                            |   2   | D/V  |
| 1.5.5 | Verifique que las puertas de calidad bloqueen conjuntos de datos de calidad inferior a menos que se aprueben excepciones.                                                                                                                                                                                                                        |   2   | D/V  |

---

## C1.6 Detección de Envenenamiento de Datos

Aplicar detección estadística de anomalías y flujos de trabajo de cuarentena para detener inserciones adversariales.

|   #   | Description                                                                                                                                                                                                                                                                                                                                                  | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 1.6.1 | Verifique que se apliquen técnicas de detección de anomalías (por ejemplo, métodos estadísticos, detección de valores atípicos, análisis de incrustaciones) a los datos de entrenamiento durante la ingestión y antes de las ejecuciones principales de entrenamiento para identificar posibles ataques de envenenamiento o corrupción inadvertida de datos. |   2   | D/V  |
| 1.6.2 | Verifique que las muestras marcadas desencadenen una revisión manual antes del entrenamiento.                                                                                                                                                                                                                                                                |   2   | D/V  |
| 1.6.3 | Verifique que los resultados alimenten el expediente de seguridad del modelo e informen la inteligencia continua de amenazas.                                                                                                                                                                                                                                |   2   |  V   |
| 1.6.4 | Verifique que la lógica de detección se actualice con nueva inteligencia de amenazas.                                                                                                                                                                                                                                                                        |   3   | D/V  |
| 1.6.5 | Verifique que las canalizaciones de aprendizaje en línea monitoreen el desplazamiento de la distribución.                                                                                                                                                                                                                                                    |   3   | D/V  |
| 1.6.6 | Verifique que se consideren e implementen defensas específicas contra tipos conocidos de ataques de envenenamiento de datos (por ejemplo, inversión de etiquetas, inserción de activadores de puerta trasera, ataques con instancias influyentes) según el perfil de riesgo del sistema y las fuentes de datos.                                              |   3   | D/V  |

---

## C1.7 Eliminación de Datos de Usuario y Aplicación del Consentimiento

Respetar las solicitudes de eliminación y revocación de consentimiento en todos los conjuntos de datos, copias de seguridad y artefactos derivados.

|   #   | Description                                                                                                                                                                                                                                                                                                                       | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.7.1 | Verifique que los flujos de trabajo de eliminación purguen los datos primarios y derivados y evalué el impacto en el modelo, y que el impacto en los modelos afectados sea evaluado y, si es necesario, abordado (por ejemplo, a través de reentrenamiento o recalibración).                                                      |   1   | D/V  |
| 1.7.2 | Verifique que existan mecanismos para rastrear y respetar el alcance y estado del consentimiento del usuario (y las retiradas) para los datos utilizados en el entrenamiento, y que el consentimiento sea validado antes de incorporar los datos en nuevos procesos de entrenamiento o actualizaciones significativas del modelo. |   2   |  D   |
| 1.7.3 | Verifique que los flujos de trabajo se prueben anualmente y se registren.                                                                                                                                                                                                                                                         |   2   |  V   |

---

## C1.8 Seguridad en la Cadena de Suministro

Verifique a los proveedores externos de datos y confirme la integridad a través de canales autenticados y cifrados.

|   #   | Description                                                                                                                                                                                                                                                                                                                                                                 | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.8.1 | Verifique que los proveedores de datos de terceros, incluidos los proveedores de modelos preentrenados y conjuntos de datos externos, sean sometidos a una debida diligencia en seguridad, privacidad, abastecimiento ético y calidad de datos antes de que sus datos o modelos sean integrados.                                                                            |   2   | D/V  |
| 1.8.2 | Verifique que las transferencias externas utilicen TLS/autenticación y verificaciones de integridad.                                                                                                                                                                                                                                                                        |   1   |  D   |
| 1.8.3 | Verifique que las fuentes de datos de alto riesgo (por ejemplo, conjuntos de datos de código abierto con procedencia desconocida, proveedores no evaluados) reciban un escrutinio reforzado, como análisis en entornos aislados (sandbox), verificaciones exhaustivas de calidad/sesgo y detección específica de envenenamiento, antes de su uso en aplicaciones sensibles. |   2   | D/V  |
| 1.8.4 | Verifique que los modelos preentrenados obtenidos de terceros sean evaluados para detectar sesgos incorporados, posibles puertas traseras, integridad de su arquitectura y la procedencia de sus datos de entrenamiento originales antes de realizar ajustes o implementarlos.                                                                                              |   3   | D/V  |

---

## C1.9 Detección de Muestras Adversariales

Implemente medidas durante la fase de entrenamiento, como el entrenamiento adversarial, para mejorar la resiliencia del modelo frente a ejemplos adversariales.

|   #   | Description                                                                                                                                                                                                                                                                                   | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.9.1 | Verifique que se implementen y ajusten defensas apropiadas, como el entrenamiento adversarial (utilizando ejemplos adversariales generados), la aumentación de datos con entradas perturbadas o técnicas de optimización robusta, para los modelos relevantes según la evaluación de riesgos. |   3   | D/V  |
| 1.9.2 | Verifique que si se utiliza entrenamiento adversarial, la generación, gestión y versionado de conjuntos de datos adversariales estén documentados y controlados.                                                                                                                              |   2   | D/V  |
| 1.9.3 | Verificar que se evalúe, documente y monitoree el impacto del entrenamiento de robustez adversarial en el rendimiento del modelo (tanto contra entradas limpias como adversariales) y en las métricas de equidad.                                                                             |   3   | D/V  |
| 1.9.4 | Verificar que las estrategias para el entrenamiento adversarial y la robustez se revisen y actualicen periódicamente para contrarrestar las técnicas de ataque adversarial en evolución.                                                                                                      |   3   | D/V  |

---

## C1.10 Linaje y Trazabilidad de Datos

Rastree el recorrido completo de cada punto de datos desde la fuente hasta la entrada del modelo para facilitar la auditoría y la respuesta ante incidentes.

|   #    | Description                                                                                                                                        | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.10.1 | Verifique que se registre y pueda reconstruirse el linaje de cada punto de datos, incluyendo todas las transformaciones, aumentos y combinaciones. |   2   | D/V  |
| 1.10.2 | Verifique que los registros de linaje sean inmutables, estén almacenados de forma segura y sean accesibles para auditorías o investigaciones.      |   2   | D/V  |
| 1.10.3 | Verifique que el seguimiento de linaje cubra tanto los datos en bruto como los datos sintéticos.                                                   |   2   | D/V  |

---

## C1.11 Gestión de Datos Sintéticos

Asegúrese de que los datos sintéticos se gestionen, etiqueten y evalúen correctamente en cuanto a riesgos.

|   #    | Description                                                                                                                                                                 | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.11.1 | Verifique que todos los datos sintéticos estén claramente etiquetados y sean distinguibles de los datos reales a lo largo de todo el flujo de trabajo.                      |   2   | D/V  |
| 1.11.2 | Verifique que el proceso de generación, los parámetros y el uso previsto de los datos sintéticos estén documentados.                                                        |   2   | D/V  |
| 1.11.3 | Verificar que los datos sintéticos sean evaluados en cuanto a riesgos de sesgo, filtración de privacidad y problemas de representación antes de su uso en el entrenamiento. |   2   | D/V  |

---

## C1.12 Monitoreo de Acceso a Datos y Detección de Anomalías

Monitorear y alertar sobre accesos inusuales a los datos de entrenamiento para detectar amenazas internas o exfiltración.

|   #    | Description                                                                                                                                                    | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.12.1 | Verifique que todo acceso a los datos de entrenamiento esté registrado, incluyendo usuario, hora y acción.                                                     |   2   | D/V  |
| 1.12.2 | Verifique que los registros de acceso se revisen regularmente para detectar patrones inusuales, como grandes exportaciones o accesos desde ubicaciones nuevas. |   2   | D/V  |
| 1.12.3 | Verifique que se generen alertas para eventos de acceso sospechosos y que se investiguen de manera inmediata.                                                  |   2   | D/V  |

---

## C1.13 Políticas de Retención y Expiración de Datos

Defina y aplique períodos de retención de datos para minimizar el almacenamiento innecesario de datos.

|   #    | Description                                                                                                                           | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.13.1 | Verifique que se definan períodos explícitos de retención para todos los conjuntos de datos de entrenamiento.                         |   1   | D/V  |
| 1.13.2 | Verifique que los conjuntos de datos se expiren, eliminen o revisen automáticamente para su eliminación al final de su ciclo de vida. |   2   | D/V  |
| 1.13.3 | Verifique que las acciones de retención y eliminación estén registradas y sean auditables.                                            |   2   | D/V  |

---

## C1.14 Cumplimiento Normativo y Jurisdiccional

Asegúrese de que todos los datos de entrenamiento cumplan con las leyes y regulaciones aplicables.

|   #    | Description                                                                                                                                            | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 1.14.1 | Verificar que los requisitos de residencia de datos y transferencia transfronteriza estén identificados y aplicados para todos los conjuntos de datos. |   2   | D/V  |
| 1.14.2 | Verifique que las regulaciones específicas del sector (por ejemplo, salud, finanzas) sean identificadas y abordadas en el manejo de datos.             |   2   | D/V  |
| 1.14.3 | Verifique que el cumplimiento de las leyes de privacidad relevantes (por ejemplo, GDPR, CCPA) esté documentado y se revise regularmente.               |   2   | D/V  |

---

## C1.15 Marcado de agua de datos y huella digital

Detectar el uso no autorizado o la filtración de datos propietarios o sensibles.

|   #    | Description                                                                                                                         | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.15.1 | Verifique que los conjuntos de datos o subconjuntos estén marcados con marca de agua o tengan huellas digitales cuando sea posible. |   3   | D/V  |
| 1.15.2 | Verifique que los métodos de marca de agua/marcado de huellas no introduzcan sesgos ni riesgos de privacidad.                       |   3   | D/V  |
| 1.15.3 | Verificar que se realicen controles periódicos para detectar el uso no autorizado o la filtración de datos con marcas de agua.      |   3   | D/V  |

---

## C1.16 Gestión de los Derechos de los Sujetos de Datos

Apoyar los derechos de los sujetos de datos, como el acceso, la rectificación, la restricción y la oposición.

|   #    | Description                                                                                                                                          | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.16.1 | Verifique que existan mecanismos para responder a las solicitudes de los titulares de los datos para acceso, rectificación, restricción u oposición. |   2   | D/V  |
| 1.16.2 | Verifique que las solicitudes sean registradas, rastreadas y cumplidas dentro de los plazos establecidos legalmente.                                 |   2   | D/V  |
| 1.16.3 | Verificar que los procesos de derechos del sujeto de datos sean probados y revisados regularmente para garantizar su efectividad.                    |   2   | D/V  |

---

## C1.17 Análisis del Impacto de la Versión del Conjunto de Datos

Evalúe el impacto de los cambios en el conjunto de datos antes de actualizar o reemplazar las versiones.

|   #    | Description                                                                                                                                                                           | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.17.1 | Verifique que se realice un análisis de impacto antes de actualizar o reemplazar una versión de conjunto de datos, cubriendo el rendimiento del modelo, la equidad y el cumplimiento. |   2   | D/V  |
| 1.17.2 | Verifique que los resultados del análisis de impacto estén documentados y sean revisados por las partes interesadas relevantes.                                                       |   2   | D/V  |
| 1.17.3 | Verifique que existan planes de reversión en caso de que las nuevas versiones introduzcan riesgos inaceptables o regresiones.                                                         |   2   | D/V  |

---

## C1.18 Seguridad de la Fuerza Laboral de Anotación de Datos

Asegurar la seguridad e integridad del personal involucrado en la anotación de datos.

|   #    | Description                                                                                                                                                            | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.18.1 | Verifique que todo el personal involucrado en la anotación de datos haya pasado una verificación de antecedentes y esté capacitado en seguridad y privacidad de datos. |   2   | D/V  |
| 1.18.2 | Verifique que todo el personal de anotación firme acuerdos de confidencialidad y no divulgación.                                                                       |   2   | D/V  |
| 1.18.3 | Verifique que las plataformas de anotación apliquen controles de acceso y supervisen las amenazas internas.                                                            |   2   | D/V  |

---

## Referencias

* [NIST AI Risk Management Framework](https://www.nist.gov/itl/ai-risk-management-framework)
* [EU AI Act – Article 10: Data & Data Governance](https://artificialintelligenceact.eu/article/10/)
* [MITRE ATLAS: Adversary Tactics for AI](https://atlas.mitre.org/)
* [Survey of ML Bias Mitigation Techniques – MDPI](https://www.mdpi.com/2673-6470/4/1/1)
* [Data Provenance & Lineage Best Practices – Nightfall AI](https://www.nightfall.ai/ai-security-101/data-provenance-and-lineage)
* [Data Labeling Quality Standards – LabelYourData](https://labelyourdata.com/articles/data-labeling-quality-and-how-to-measure-it)
* [Training Data Poisoning Guide – Lakera.ai](https://www.lakera.ai/blog/training-data-poisoning)
* [CISA Advisory: Securing Data for AI Systems](https://www.cisa.gov/news-events/cybersecurity-advisories/aa25-142a)
* [ISO/IEC 23053: AI Management Systems Framework](https://www.iso.org/sectors/it-technologies/ai)
* [IBM: What is AI Governance?](https://www.ibm.com/think/topics/ai-governance)
* [Google AI Principles](https://ai.google/principles/)
* [GDPR & AI Training Data – DataProtectionReport](https://www.dataprotectionreport.com/2024/08/recent-regulatory-developments-in-training-artificial-intelligence-ai-models-under-the-gdpr/)
* [Supply-Chain Security for AI Data – AppSOC](https://www.appsoc.com/blog/ai-is-the-new-frontier-of-supply-chain-security)
* [OpenAI Privacy Center – Data Deletion Controls](https://privacy.openai.com/policies?modal=take-control)
* [Adversarial ML Dataset – Kaggle](https://www.kaggle.com/datasets/cnrieiit/adversarial-machine-learning-dataset)

