# Gobernanza de Datos de Entrenamiento C1 y Gestión de Sesgos

## Objetivo de Control

Los datos de entrenamiento deben obtenerse, manejarse y mantenerse de manera que se preserve la procedencia, la seguridad, la calidad y la equidad. Hacerlo cumple con las obligaciones legales y reduce los riesgos de sesgo, envenenamiento o violaciones de privacidad durante todo el ciclo de vida de la IA.

---

## C1.1 Procedencia de los Datos de Entrenamiento

Mantenga un inventario verificable de todos los conjuntos de datos, acepte solo fuentes confiables y registre cada cambio para garantizar la auditabilidad.

|   #   | Description                                                                                                                                                                                                                                                                                 | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.1.1 | Verifique que se mantenga un inventario actualizado de cada fuente de datos de entrenamiento (origen, responsable/propietario, licencia, método de recopilación, restricciones de uso previstas e historial de procesamiento).                                                              |   1   | D/V  |
| 1.1.2 | Verificar que solo se permitan conjuntos de datos evaluados para calidad, representatividad, origen ético y cumplimiento de licencias, reduciendo los riesgos de envenenamiento, sesgos incorporados e infracción de propiedad intelectual.                                                 |   1   | D/V  |
| 1.1.3 | Verifique que se aplique la minimización de datos para que se excluyan atributos innecesarios o sensibles.                                                                                                                                                                                  |   1   | D/V  |
| 1.1.4 | Verifique que todos los cambios en el conjunto de datos estén sujetos a un flujo de trabajo de aprobación registrado.                                                                                                                                                                       |   2   | D/V  |
| 1.1.5 | Verifique que la calidad del etiquetado/anotación esté garantizada mediante verificaciones cruzadas o consenso de los revisores.                                                                                                                                                            |   2   | D/V  |
| 1.1.6 | Verifique que se mantengan "tarjetas de datos" o "hojas de datos para conjuntos de datos" para los conjuntos de datos de entrenamiento significativos, detallando características, motivaciones, composición, procesos de recolección, preprocesamiento y usos recomendados/desaconsejados. |   2   | D/V  |

---

## C1.2 Seguridad e Integridad de los Datos de Entrenamiento

Restringir el acceso, cifrar los datos en reposo y en tránsito, y validar la integridad para bloquear la manipulación o el robo.

|   #   | Description                                                                                                                                                                                                                                                                                                                                             | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.2.1 | Verifique que los controles de acceso protejan el almacenamiento y las canalizaciones.                                                                                                                                                                                                                                                                  |   1   | D/V  |
| 1.2.2 | Verifique que los conjuntos de datos estén cifrados en tránsito y, para toda la información sensible o personalmente identificable (PII), en reposo, utilizando algoritmos criptográficos estándar de la industria y prácticas de gestión de claves.                                                                                                    |   2   | D/V  |
| 1.2.3 | Verifique que se utilicen hashes criptográficos o firmas digitales para asegurar la integridad de los datos durante el almacenamiento y la transferencia, y que se apliquen técnicas automatizadas de detección de anomalías para proteger contra modificaciones no autorizadas o corrupción, incluyendo intentos dirigidos de envenenamiento de datos. |   2   | D/V  |
| 1.2.4 | Verifique que las versiones del conjunto de datos estén registradas para permitir la reversión.                                                                                                                                                                                                                                                         |   3   | D/V  |
| 1.2.5 | Verifique que los datos obsoletos se eliminen de forma segura o se anonimicen conforme a las políticas de retención de datos, los requisitos regulatorios y para reducir la superficie de ataque.                                                                                                                                                       |   2   | D/V  |

---

## C1.3 Integridad y Equidad de la Representación

Detectar sesgos demográficos y aplicar mitigación para que las tasas de error del modelo sean equitativas entre los grupos.

|   #   | Description                                                                                                                                                                                                                                                                                                                                                                         | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.3.1 | Verifique que los conjuntos de datos sean analizados para detectar desequilibrios representativos y posibles sesgos en atributos legalmente protegidos (por ejemplo, raza, género, edad) y otras características éticamente sensibles relevantes para el dominio de aplicación del modelo (por ejemplo, estatus socioeconómico, ubicación).                                         |   1   | D/V  |
| 1.3.2 | Verifique que los sesgos identificados se mitiguen mediante estrategias documentadas como el reequilibrio, la aumentación de datos dirigida, ajustes algorítmicos (por ejemplo, técnicas de preprocesamiento, procesamiento interno, postprocesamiento) o reponderación, y que se evalúe el impacto de la mitigación tanto en la equidad como en el rendimiento general del modelo. |   2   | D/V  |
| 1.3.3 | Verifique que las métricas de equidad posteriores al entrenamiento sean evaluadas y documentadas.                                                                                                                                                                                                                                                                                   |   2   | D/V  |
| 1.3.4 | Verifique que una política de gestión de sesgos en el ciclo de vida asigne responsables y un ritmo de revisión.                                                                                                                                                                                                                                                                     |   3   | D/V  |

---

## C1.4 Calidad, Integridad y Seguridad del Etiquetado de Datos de Entrenamiento

Proteja las etiquetas con cifrado y requiera una revisión dual para las clases críticas.

|   #   | Description                                                                                                                                                                                                                                                                                                 | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.4.1 | Verifique que la calidad del etiquetado/anotación esté garantizada mediante directrices claras, revisiones cruzadas por parte de los evaluadores, mecanismos de consenso (p. ej., monitoreo del acuerdo interanotadores) y procesos definidos para resolver discrepancias.                                  |   2   | D/V  |
| 1.4.2 | Verifique que se apliquen hashes criptográficos o firmas digitales a los artefactos de etiquetado para garantizar su integridad y autenticidad.                                                                                                                                                             |   2   | D/V  |
| 1.4.3 | Verifique que las interfaces y plataformas de etiquetado apliquen controles de acceso estrictos, mantengan registros de auditoría a prueba de manipulaciones de todas las actividades de etiquetado y protejan contra modificaciones no autorizadas.                                                        |   2   | D/V  |
| 1.4.4 | Verifique que las etiquetas críticas para la seguridad, protección o equidad (por ejemplo, la identificación de contenido tóxico, hallazgos médicos críticos) reciban una revisión dual independiente obligatoria o una verificación robusta equivalente.                                                   |   3   | D/V  |
| 1.4.5 | Verifique que la información sensible (incluida la información de identificación personal, PII) capturada inadvertidamente o necesariamente presente en las etiquetas esté redactada, seudonimizada, anonimizada o cifrada en reposo y en tránsito, de acuerdo con los principios de minimización de datos. |   2   | D/V  |
| 1.4.6 | Verifique que las guías de etiquetado e instrucciones sean completas, estén controladas por versiones y revisadas por pares.                                                                                                                                                                                |   2   | D/V  |
| 1.4.7 | Verifique que los esquemas de datos (incluidos los de etiquetas) estén claramente definidos y bajo control de versiones.                                                                                                                                                                                    |   2   | D/V  |
| 1.8.2 | Verifique que los flujos de trabajo de etiquetado subcontratados o generados mediante crowdsourcing incluyan salvaguardas técnicas/procedimentales para garantizar la confidencialidad, integridad de los datos, calidad de las etiquetas y prevenir la filtración de datos.                                |   2   | D/V  |

---

## C1.5 Aseguramiento de la Calidad de los Datos de Entrenamiento

Combine la validación automatizada, las verificaciones manuales aleatorias y la remediación registrada para garantizar la fiabilidad del conjunto de datos.

|   #   | Description                                                                                                                                                                                                                                                                                                                                       | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.5.1 | Verifique que las pruebas automatizadas detecten errores de formato, valores nulos y desalineaciones de etiquetas en cada ingestión o transformación significativa.                                                                                                                                                                               |   1   |  D   |
| 1.5.2 | Verifique que los conjuntos de datos fallidos estén en cuarentena con registros de auditoría.                                                                                                                                                                                                                                                     |   1   | D/V  |
| 1.5.3 | Verifique que las inspecciones manuales aleatorias realizadas por expertos en el dominio cubran una muestra estadísticamente significativa (por ejemplo, ≥1% o 1,000 muestras, lo que sea mayor, o según lo determinado por la evaluación de riesgos) para identificar problemas sutiles de calidad que no sean detectados por la automatización. |   2   |  V   |
| 1.5.4 | Verifique que los pasos de remediación estén añadidos a los registros de procedencia.                                                                                                                                                                                                                                                             |   2   | D/V  |
| 1.5.5 | Verifique que los controles de calidad bloqueen conjuntos de datos deficientes a menos que se aprueben excepciones.                                                                                                                                                                                                                               |   2   | D/V  |

---

## C1.6 Detección de envenenamiento de datos

Aplique detección estadística de anomalías y flujos de trabajo de cuarentena para detener inserciones adversariales.

|   #   | Description                                                                                                                                                                                                                                                                                                                                               | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.6.1 | Verifique que las técnicas de detección de anomalías (por ejemplo, métodos estadísticos, detección de valores atípicos, análisis de incrustaciones) se apliquen a los datos de entrenamiento en la ingestión y antes de los principales procesos de entrenamiento para identificar posibles ataques de envenenamiento o corrupción involuntaria de datos. |   2   | D/V  |
| 1.6.2 | Verifique que las muestras marcadas desencadenen una revisión manual antes del entrenamiento.                                                                                                                                                                                                                                                             |   2   | D/V  |
| 1.6.3 | Verifique que los resultados alimenten el expediente de seguridad del modelo e informen la inteligencia de amenazas continua.                                                                                                                                                                                                                             |   2   |  V   |
| 1.6.4 | Verifique que la lógica de detección se actualice con nueva información de amenazas.                                                                                                                                                                                                                                                                      |   3   | D/V  |
| 1.6.5 | Verifique que los pipelines de aprendizaje en línea monitoreen el cambio en la distribución.                                                                                                                                                                                                                                                              |   3   | D/V  |
| 1.6.6 | Verifique que se consideren e implementen defensas específicas contra tipos conocidos de ataques de envenenamiento de datos (por ejemplo, inversión de etiquetas, inserción de disparadores de puerta trasera, ataques de instancias influyentes) basándose en el perfil de riesgo del sistema y las fuentes de datos.                                    |   3   | D/V  |

---

## C1.7 Eliminación de Datos del Usuario y Aplicación del Consentimiento

Respetar las solicitudes de eliminación y de retirada del consentimiento en todos los conjuntos de datos, copias de seguridad y artefactos derivados.

|   #   | Description                                                                                                                                                                                                                                                                                                                       | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.7.1 | Verifique que los flujos de trabajo de eliminación purguen los datos primarios y derivados y evalué el impacto en el modelo, y que el impacto en los modelos afectados sea evaluado y, si es necesario, abordado (por ejemplo, mediante el reentrenamiento o recalibración).                                                      |   1   | D/V  |
| 1.7.2 | Verifique que existan mecanismos para rastrear y respetar el alcance y el estado del consentimiento del usuario (y las retiradas) para los datos utilizados en el entrenamiento, y que el consentimiento se valide antes de incorporar los datos en nuevos procesos de entrenamiento o actualizaciones significativas del modelo. |   2   |  D   |
| 1.7.3 | Verifique que los flujos de trabajo sean probados anualmente y registrados.                                                                                                                                                                                                                                                       |   2   |  V   |

---

## C1.8 Seguridad en la Cadena de Suministro

Verifique a los proveedores externos de datos y confirme la integridad a través de canales autenticados y cifrados.

|   #   | Description                                                                                                                                                                                                                                                                                                                                                            | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.8.1 | Verificar que los proveedores de datos externos, incluidos los proveedores de modelos preentrenados y conjuntos de datos externos, pasen por una debida diligencia en seguridad, privacidad, obtención ética y calidad de datos antes de que sus datos o modelos sean integrados.                                                                                      |   2   | D/V  |
| 1.8.2 | Verifique que las transferencias externas utilicen TLS/autenticación y comprobaciones de integridad.                                                                                                                                                                                                                                                                   |   1   |  D   |
| 1.8.3 | Verifique que las fuentes de datos de alto riesgo (por ejemplo, conjuntos de datos de código abierto con procedencia desconocida, proveedores no evaluados) reciban un escrutinio reforzado, como análisis en entornos aislados (sandbox), controles exhaustivos de calidad/sesgo y detección específica de envenenamiento, antes de su uso en aplicaciones sensibles. |   2   | D/V  |
| 1.8.4 | Verifique que los modelos preentrenados obtenidos de terceros sean evaluados para detectar sesgos incorporados, posibles puertas traseras, la integridad de su arquitectura y la procedencia de sus datos originales de entrenamiento antes de su ajuste fino o implementación.                                                                                        |   3   | D/V  |

---

## C1.9 Detección de Muestras Adversariales

Implemente medidas durante la fase de entrenamiento, como el entrenamiento adversarial, para mejorar la resistencia del modelo contra ejemplos adversariales.

|   #   | Description                                                                                                                                                                                                                                                                                  | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.9.1 | Verifique que se implementen y ajusten defensas adecuadas, como el entrenamiento adversarial (utilizando ejemplos adversariales generados), la aumentación de datos con entradas perturbadas o técnicas de optimización robusta, para los modelos relevantes según la evaluación de riesgos. |   3   | D/V  |
| 1.9.2 | Verifique que si se utiliza entrenamiento adversarial, la generación, gestión y versionado de conjuntos de datos adversariales estén documentados y controlados.                                                                                                                             |   2   | D/V  |
| 1.9.3 | Verifique que se evalúe, documente y supervise el impacto del entrenamiento de robustez adversarial en el rendimiento del modelo (tanto contra entradas limpias como adversariales) y en las métricas de equidad.                                                                            |   3   | D/V  |
| 1.9.4 | Verifique que las estrategias para el entrenamiento adversarial y la robustez sean revisadas y actualizadas periódicamente para contrarrestar las técnicas de ataque adversarial en evolución.                                                                                               |   3   | D/V  |

---

## C1.10 Linaje y trazabilidad de datos

Rastrea todo el recorrido de cada punto de datos desde la fuente hasta la entrada del modelo para garantizar la auditabilidad y la respuesta ante incidentes.

|   #    | Description                                                                                                                                          | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.10.1 | Verifique que el linaje de cada punto de datos, incluidas todas las transformaciones, aumentos y fusiones, esté registrado y pueda ser reconstruido. |   2   | D/V  |
| 1.10.2 | Verifique que los registros de linaje sean inmutables, estén almacenados de forma segura y sean accesibles para auditorías o investigaciones.        |   2   | D/V  |
| 1.10.3 | Verifique que el seguimiento de linaje cubra tanto los datos crudos como los sintéticos.                                                             |   2   | D/V  |

---

## C1.11 Gestión de Datos Sintéticos

Asegurar que los datos sintéticos estén debidamente gestionados, etiquetados y evaluados en cuanto a riesgos.

|   #    | Description                                                                                                                                                                  | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.11.1 | Verifique que todos los datos sintéticos estén claramente etiquetados y sean distinguibles de los datos reales a lo largo de todo el flujo de trabajo.                       |   2   | D/V  |
| 1.11.2 | Verifique que el proceso de generación, los parámetros y el uso previsto de los datos sintéticos estén documentados.                                                         |   2   | D/V  |
| 1.11.3 | Verifique que los datos sintéticos sean evaluados en cuanto a riesgos de sesgo, filtración de privacidad y problemas de representación antes de usarlos en el entrenamiento. |   2   | D/V  |

---

## C1.12 Monitoreo de Acceso a Datos y Detección de Anomalías

Monitorear y alertar sobre accesos inusuales a los datos de entrenamiento para detectar amenazas internas o exfiltración.

|   #    | Description                                                                                                                                                    | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.12.1 | Verifique que todo acceso a los datos de entrenamiento esté registrado, incluyendo usuario, hora y acción.                                                     |   2   | D/V  |
| 1.12.2 | Verifique que los registros de acceso se revisen regularmente para detectar patrones inusuales, como grandes exportaciones o accesos desde nuevas ubicaciones. |   2   | D/V  |
| 1.12.3 | Verifique que se generen alertas para eventos de acceso sospechosos y que se investiguen de manera pronta.                                                     |   2   | D/V  |

---

## C1.13 Políticas de Retención y Expiración de Datos

Definir y hacer cumplir los períodos de retención de datos para minimizar el almacenamiento innecesario de datos.

|   #    | Description                                                                                                                           | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.13.1 | Verifique que se definan períodos de retención explícitos para todos los conjuntos de datos de entrenamiento.                         |   1   | D/V  |
| 1.13.2 | Verifique que los conjuntos de datos se expiren, eliminen o revisen automáticamente para su eliminación al final de su ciclo de vida. |   2   | D/V  |
| 1.13.3 | Verifique que las acciones de retención y eliminación estén registradas y sean auditables.                                            |   2   | D/V  |

---

## C1.14 Cumplimiento Regulatorio y Jurisdiccional

Asegúrese de que todos los datos de entrenamiento cumplan con las leyes y regulaciones aplicables.

|   #    | Description                                                                                                                                              | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.14.1 | Verifique que los requisitos de residencia de datos y de transferencia transfronteriza estén identificados y se apliquen a todos los conjuntos de datos. |   2   | D/V  |
| 1.14.2 | Verifique que las regulaciones específicas del sector (por ejemplo, salud, finanzas) sean identificadas y abordadas en el manejo de datos.               |   2   | D/V  |
| 1.14.3 | Verifique que el cumplimiento con las leyes de privacidad relevantes (por ejemplo, GDPR, CCPA) esté documentado y se revise regularmente.                |   2   | D/V  |

---

## C1.15 Marcado de Agua y Huellas Digitales de Datos

Detectar el uso no autorizado o la filtración de datos propietarios o sensibles.

|   #    | Description                                                                                                                    | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 1.15.1 | Verifique que los conjuntos de datos o subconjuntos estén marcados con una marca de agua o huella digital cuando sea factible. |   3   | D/V  |
| 1.15.2 | Verifique que los métodos de marcas de agua/huellas digitales no introduzcan sesgos ni riesgos de privacidad.                  |   3   | D/V  |
| 1.15.3 | Verificar que se realicen controles periódicos para detectar el uso no autorizado o la filtración de datos con marca de agua.  |   3   | D/V  |

---

## C1.16 Gestión de los Derechos del Sujeto de Datos

Apoyar los derechos del sujeto de datos como el acceso, la rectificación, la restricción y la oposición.

|   #    | Description                                                                                                                                | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 1.16.1 | Verifique que existan mecanismos para responder a las solicitudes del sujeto de datos para acceso, rectificación, restricción u oposición. |   2   | D/V  |
| 1.16.2 | Verifique que las solicitudes sean registradas, rastreadas y cumplidas dentro de los plazos legalmente establecidos.                       |   2   | D/V  |
| 1.16.3 | Verifique que los procesos de derechos del sujeto de datos sean probados y revisados regularmente para garantizar su efectividad.          |   2   | D/V  |

---

## C1.17 Análisis del Impacto de la Versión del Conjunto de Datos

Evalúe el impacto de los cambios en el conjunto de datos antes de actualizar o reemplazar las versiones.

|   #    | Description                                                                                                                                                                            | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.17.1 | Verifique que se realice un análisis de impacto antes de actualizar o reemplazar una versión del conjunto de datos, cubriendo el rendimiento del modelo, la equidad y el cumplimiento. |   2   | D/V  |
| 1.17.2 | Verifique que los resultados del análisis de impacto estén documentados y revisados por las partes interesadas relevantes.                                                             |   2   | D/V  |
| 1.17.3 | Verifique que existan planes de reversión en caso de que las nuevas versiones introduzcan riesgos inaceptables o regresiones.                                                          |   2   | D/V  |

---

## C1.18 Seguridad de la Fuerza Laboral en Anotación de Datos

Garantizar la seguridad e integridad del personal involucrado en la anotación de datos.

|   #    | Description                                                                                                                                                                | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.18.1 | Verifique que todo el personal involucrado en la anotación de datos haya pasado por una verificación de antecedentes y esté capacitado en seguridad y privacidad de datos. |   2   | D/V  |
| 1.18.2 | Verifique que todo el personal de anotación firme acuerdos de confidencialidad y no divulgación.                                                                           |   2   | D/V  |
| 1.18.3 | Verifique que las plataformas de anotación implementen controles de acceso y monitoreen las amenazas internas.                                                             |   2   | D/V  |

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

