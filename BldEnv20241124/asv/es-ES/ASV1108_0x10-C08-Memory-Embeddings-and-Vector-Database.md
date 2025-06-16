# Memoria C8, Embeddings y Seguridad de Bases de Datos Vectoriales

## Objetivo de Control

Los embeddings y las bases de datos vectoriales actúan como la "memoria viva" de los sistemas de IA contemporáneos, aceptando continuamente datos proporcionados por el usuario y reintroduciéndolos en los contextos del modelo mediante la Generación Aumentada por Recuperación (RAG). Si no se supervisa adecuadamente, esta memoria puede filtrar información de identificación personal (PII), violar el consentimiento o invertirse para reconstruir el texto original. El objetivo de esta familia de controles es fortalecer las canalizaciones de memoria y las bases de datos vectoriales para que el acceso sea de mínimo privilegio, los embeddings preserven la privacidad, los vectores almacenados expiren o puedan ser revocados bajo demanda, y la memoria por usuario nunca contamine las indicaciones ni las respuestas de otro usuario.

---

## C8.1 Controles de acceso en memoria e índices RAG

Implemente controles de acceso detallados en cada colección de vectores.

|   #   | Description                                                                                                                                                                                           | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 8.1.1 | Verifique que las reglas de control de acceso a nivel de fila/espacio de nombres restrinjan las operaciones de inserción, eliminación y consulta por inquilino, colección o etiqueta de documento.    |   1   | D/V  |
| 8.1.2 | Verifique que las claves API o los JWT contengan reclamaciones con ámbito específico (por ejemplo, IDs de colección, verbos de acción) y que se roten al menos trimestralmente.                       |   1   | D/V  |
| 8.1.3 | Verifique que los intentos de escalada de privilegios (por ejemplo, consultas de similitud entre espacios de nombres) sean detectados y registrados en un SIEM dentro de los 5 minutos.               |   2   | D/V  |
| 8.1.4 | Verifique que la base de datos vectorial registre en el auditoría el identificador del sujeto, la operación, el ID/espacio de nombres del vector, el umbral de similitud y el recuento de resultados. |   2   | D/V  |
| 8.1.5 | Verifique que las decisiones de acceso se prueben en busca de fallas de omisión siempre que se actualicen los motores o cambien las reglas de fragmentación de índices.                               |   3   |  V   |

---

## C8.2 Saneamiento y Validación de Incrustaciones

Preseleccione el texto para información de identificación personal (PII), redacte o seudonimice antes de la vectorización, y opcionalmente realice un post-procesamiento de los embeddings para eliminar señales residuales.

|   #   | Description                                                                                                                                                                                                                            | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 8.2.1 | Verifique que los datos de identificación personal (PII) y los datos regulados sean detectados mediante clasificadores automáticos y que se anonimizan, tokenizan o eliminan antes de la generación de incrustaciones (pre-embedding). |   1   | D/V  |
| 8.2.2 | Verifique que las canalizaciones de embeddings rechacen o pongan en cuarentena entradas que contengan código ejecutable o artefactos no UTF-8 que podrían envenenar el índice.                                                         |   1   |  D   |
| 8.2.3 | Verifique que se aplique una sanitización de privacidad diferencial local o métrica a las incrustaciones de oraciones cuya distancia a cualquier token PII conocido caiga por debajo de un umbral configurable.                        |   2   | D/V  |
| 8.2.4 | Verifique que la eficacia de la desinfección (por ejemplo, la recuperación de la redacción de información personal identificable, la deriva semántica) se valide al menos semestralmente contra corpus de referencia.                  |   2   |  V   |
| 8.2.5 | Verifique que las configuraciones de saneamiento estén controladas por versión y que los cambios pasen por una revisión por pares.                                                                                                     |   3   | D/V  |

---

## C8.3 Expiración, Revocación y Eliminación de Memoria

El "derecho al olvido" del GDPR y leyes similares requieren la eliminación oportuna; por lo tanto, los almacenes vectoriales deben soportar TTLs, eliminaciones definitivas y tomb-stoning para que los vectores revocados no puedan ser recuperados ni reindexados.

|   #   | Description                                                                                                                                                                                          | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 8.3.1 | Verifique que cada vector y registro de metadatos tenga un TTL o una etiqueta de retención explícita que sea respetada por los trabajos automáticos de limpieza.                                     |   1   | D/V  |
| 8.3.2 | Verifique que las solicitudes de eliminación iniciadas por el usuario eliminen vectores, metadatos, copias en caché e índices derivados dentro de los 30 días.                                       |   1   | D/V  |
| 8.3.3 | Verifique que las eliminaciones lógicas sean seguidas por el borrado criptográfico de los bloques de almacenamiento si el hardware lo soporta, o por la destrucción de claves del almacén de claves. |   2   |  D   |
| 8.3.4 | Verifique que los vectores caducados se excluyan de los resultados de la búsqueda de vecinos más cercanos en menos de 500 ms después de la expiración.                                               |   3   | D/V  |

---

## C8.4 Prevenir la inversión y filtración de incrustaciones

Las defensas recientes — superposición de ruido, redes de proyección, perturbación de neuronas de privacidad y cifrado a nivel de aplicación — pueden reducir las tasas de inversión a nivel de token por debajo del 5%.

|   #   | Description                                                                                                                                                                                   | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 8.4.1 | Verifique que exista un modelo formal de amenazas que cubra ataques de inversión, membresía e inferencia de atributos y que sea revisado anualmente.                                          |   1   |  V   |
| 8.4.2 | Verifique que el cifrado a nivel de aplicación o el cifrado buscable protejan los vectores de lecturas directas por parte de los administradores de infraestructura o el personal de la nube. |   2   | D/V  |
| 8.4.3 | Verifique que los parámetros de defensa (ε para DP, ruido σ, rango de proyección k) equilibren la privacidad ≥ 99 % de protección de tokens y la utilidad ≤ 3 % de pérdida de precisión.      |   3   |  V   |
| 8.4.4 | Verifique que las métricas de resiliencia a la inversión formen parte de los umbrales de liberación para las actualizaciones del modelo, con presupuestos de regresión definidos.             |   3   | D/V  |

---

## C8.5 Aplicación del Alcance para la Memoria Específica del Usuario

La filtración entre inquilinos sigue siendo un riesgo principal en RAG: las consultas de similitud filtradas incorrectamente pueden mostrar documentos privados de otro cliente.

|   #   | Description                                                                                                                                                                          | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 8.5.1 | Verifique que cada consulta de recuperación sea filtrada posteriormente por ID de inquilino/usuario antes de ser pasada al prompt del LLM.                                           |   1   | D/V  |
| 8.5.2 | Verifique que los nombres de colecciones o los IDs con espacio de nombres estén salados por usuario o inquilino para que los vectores no puedan colisionar entre ámbitos.            |   1   |  D   |
| 8.5.3 | Verifique que los resultados de similitud que superan un umbral de distancia configurable pero están fuera del alcance del llamador sean descartados y generen alertas de seguridad. |   2   | D/V  |
| 8.5.4 | Verifique que las pruebas de estrés multiinquilino simulan consultas adversarias que intentan recuperar documentos fuera de alcance y demuestran ausencia total de filtración.       |   2   |  V   |
| 8.5.5 | Verifique que las claves de cifrado estén segregadas por inquilino, asegurando el aislamiento criptográfico incluso si se comparte el almacenamiento físico.                         |   3   | D/V  |

---

## C8.6 Seguridad Avanzada del Sistema de Memoria

Controles de seguridad para arquitecturas de memoria sofisticadas que incluyen memoria episódica, semántica y de trabajo, con requisitos específicos de aislamiento y validación.

|   #   | Description                                                                                                                                                                                                                                                                                            | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 8.6.1 | Verifique que los diferentes tipos de memoria (episódica, semántica, de trabajo) tengan contextos de seguridad aislados con controles de acceso basados en roles, claves de cifrado separadas y patrones de acceso documentados para cada tipo de memoria.                                             |   1   | D/V  |
| 8.6.2 | Verifique que los procesos de consolidación de memoria incluyan validación de seguridad para prevenir la inyección de memorias maliciosas mediante la sanitización de contenido, verificación de la fuente y controles de integridad antes del almacenamiento.                                         |   2   | D/V  |
| 8.6.3 | Verifique que las consultas de recuperación de memoria sean validadas y saneadas para evitar la extracción de información no autorizada mediante el análisis de patrones de consulta, la aplicación de controles de acceso y el filtrado de resultados.                                                |   2   | D/V  |
| 8.6.4 | Verifique que los mecanismos de olvido de memoria eliminen de forma segura la información sensible con garantías de borrado criptográfico mediante la eliminación de claves, sobrescritura múltiple o eliminación segura basada en hardware con certificados de verificación.                          |   3   | D/V  |
| 8.6.5 | Verifique que la integridad del sistema de memoria sea monitoreada continuamente para detectar modificaciones no autorizadas o corrupciones mediante sumas de verificación, registros de auditoría y alertas automatizadas cuando el contenido de la memoria cambie fuera de las operaciones normales. |   3   | D/V  |

---

## Referencias

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

