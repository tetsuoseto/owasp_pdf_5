# Validación de la entrada del usuario C2

## Objetivo de Control

La validación robusta de la entrada del usuario es una defensa de primera línea contra algunos de los ataques más dañinos en los sistemas de IA. Los ataques de inyección de comandos pueden anular las instrucciones del sistema, filtrar datos sensibles o dirigir el modelo hacia comportamientos no permitidos. A menos que existan filtros dedicados y jerarquías de instrucciones, la investigación muestra que los "jailbreaks multi-disparo" que explotan ventanas de contexto muy largas serán efectivos. Además, los ataques sutiles de perturbación adversarial, como los intercambios de homoglifos o el leetspeak, pueden cambiar silenciosamente las decisiones de un modelo.

---

## C2.1 Defensa contra la inyección de indicaciones

La inyección de indicaciones es uno de los principales riesgos para los sistemas de IA. Las defensas contra esta táctica emplean una combinación de filtros de patrones estáticos, clasificadores dinámicos y la aplicación de jerarquías de instrucciones.

|   #   | Description                                                                                                                                                                                                                                                               | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 2.1.1 | Verifique que las entradas del usuario sean filtradas contra una biblioteca continuamente actualizada de patrones conocidos de inyección de indicaciones (palabras clave de jailbreak, "ignorar lo anterior", cadenas de juego de roles, ataques indirectos en HTML/URL). |   1   | D/V  |
| 2.1.2 | Verifique que el sistema imponga una jerarquía de instrucciones en la que los mensajes del sistema o del desarrollador prevalezcan sobre las instrucciones del usuario, incluso después de la expansión de la ventana de contexto.                                        |   1   | D/V  |
| 2.1.3 | Verifique que las pruebas de evaluación adversarial (por ejemplo, indicaciones "many-shot" del Equipo Rojo) se realicen antes de cada lanzamiento de modelo o plantilla de indicaciones, con umbrales de tasa de éxito y bloqueadores automáticos para regresiones.       |   2   | D/V  |
| 2.1.4 | Verifique que los prompts provenientes de contenido de terceros (páginas web, PDFs, correos electrónicos) sean limpiados en un contexto de análisis aislado antes de ser concatenados en el prompt principal.                                                             |   2   |  D   |
| 2.1.5 | Verifique que todas las actualizaciones de reglas de filtro de indicaciones, versiones del modelo clasificador y cambios en la lista de bloqueo estén bajo control de versiones y sean auditables.                                                                        |   3   | D/V  |

---

## C2.2 Resistencia a Ejemplos Adversarios

Los modelos de Procesamiento de Lenguaje Natural (PLN) siguen siendo vulnerables a perturbaciones sutiles a nivel de carácter o palabra que los humanos a menudo pasan por alto, pero que los modelos tienden a clasificar incorrectamente.

|   #   | Description                                                                                                                                                                                                                                   | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 2.2.1 | Verifique que los pasos básicos de normalización de entrada (Unicode NFC, mapeo de homógrafos, recorte de espacios en blanco) se ejecuten antes de la tokenización.                                                                           |   1   |  D   |
| 2.2.2 | Verifique que la detección estadística de anomalías marque entradas con una distancia de edición inusualmente alta respecto a las normas del lenguaje, tokens repetidos en exceso o distancias anormales en las incrustaciones.               |   2   | D/V  |
| 2.2.3 | Verifique que la canalización de inferencia soporte variantes opcionales de modelos reforzados mediante entrenamiento adversarial o capas de defensa (por ejemplo, aleatorización, destilación defensiva) para puntos finales de alto riesgo. |   2   |  D   |
| 2.2.4 | Verifique que las entradas adversarias sospechosas estén aisladas, registradas con cargas completas (después de la redacción de información personal identificable).                                                                          |   2   |  V   |
| 2.2.5 | Verifique que las métricas de robustez (tasa de éxito de los conjuntos de ataques conocidos) se monitoreen a lo largo del tiempo y que las regresiones activen un bloqueo de lanzamiento.                                                     |   3   | D/V  |

---

## C2.3 Validación de Esquema, Tipo y Longitud

Los ataques de IA que presentan entradas malformadas o de tamaño excesivo pueden causar errores de análisis, desbordamiento de indicaciones entre campos y agotamiento de recursos. La aplicación estricta de esquemas también es un requisito previo al realizar llamadas a herramientas deterministas.

|   #   | Description                                                                                                                                                                                                           | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 2.3.1 | Verifique que cada punto final de llamada de API o función defina un esquema de entrada explícito (JSON Schema, Protobuf o equivalente multimodal) y que las entradas sean validadas antes del ensamblaje del prompt. |   1   |  D   |
| 2.3.2 | Verifique que las entradas que excedan los límites máximos de tokens o bytes sean rechazadas con un error seguro y nunca se trunquen silenciosamente.                                                                 |   1   | D/V  |
| 2.3.3 | Verifique que las comprobaciones de tipo (por ejemplo, rangos numéricos, valores enum, tipos MIME para imágenes/audio) se apliquen del lado del servidor, no solo en el código del cliente.                           |   2   | D/V  |
| 2.3.4 | Verifique que los validadores semánticos (por ejemplo, JSON Schema) se ejecuten en tiempo constante para prevenir ataques de denegación de servicio algorítmica (DoS).                                                |   2   |  D   |
| 2.3.5 | Verifique que los fallos de validación se registren con fragmentos de carga útiles redactados y códigos de error inequívocos para facilitar el triaje de seguridad.                                                   |   3   |  V   |

---

## C2.4 Evaluación de Contenido y Políticas

Los desarrolladores deberían poder detectar indicaciones sintácticamente válidas que soliciten contenido prohibido (como instrucciones ilícitas, discursos de odio y texto con derechos de autor) y luego impedir que se propaguen.

|   #   | Description                                                                                                                                                                                                     | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 2.4.1 | Verifique que un clasificador de contenido (de cero disparos o ajustado finamente) puntúe cada entrada para violencia, autolesiones, odio, contenido sexual y solicitudes ilegales, con umbrales configurables. |   1   |  D   |
| 2.4.2 | Verifique que las entradas que violen las políticas reciban rechazos estandarizados o completaciones seguras para que no se propaguen a llamadas posteriores de modelos de lenguaje grandes (LLM).              |   1   | D/V  |
| 2.4.3 | Verifique que el modelo de filtrado o el conjunto de reglas se reentrenen/actualicen al menos trimestralmente, incorporando los nuevos patrones de evasión de restricciones o elusión de políticas observados.  |   2   |  D   |
| 2.4.4 | Verificar que el filtrado respete las políticas específicas del usuario (edad, restricciones legales regionales) mediante reglas basadas en atributos resueltas en el momento de la solicitud.                  |   2   |  D   |
| 2.4.5 | Verifique que los registros de selección incluyan puntajes de confianza del clasificador y etiquetas de categoría de política para la correlación SOC y la reproducción futura de red team.                     |   3   |  V   |

---

## C2.5 Limitación de la tasa de entrada y prevención de abusos

Los desarrolladores deben prevenir el abuso, el agotamiento de recursos y los ataques automatizados contra los sistemas de IA limitando las tasas de entrada y detectando patrones de uso anómalos.

|   #   | Description                                                                                                                                                          | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 2.5.1 | Verifique que los límites de tasa por usuario, por IP y por clave API se apliquen en todos los puntos de entrada de datos.                                           |   1   | D/V  |
| 2.5.2 | Verifique que los límites de velocidad punta y sostenida estén ajustados para prevenir ataques de Denegación de Servicio (DoS) y ataques de fuerza bruta.            |   2   | D/V  |
| 2.5.3 | Verifique que los patrones de uso anómalos (por ejemplo, solicitudes rápidas consecutivas, inundación de entradas) desencadenen bloqueos automáticos o escalaciones. |   2   | D/V  |
| 2.5.4 | Verifique que los registros de prevención de abusos se conserven y revisen para identificar patrones de ataque emergentes.                                           |   3   |  V   |

---

## C2.6 Validación de Entrada Multimodal

Los sistemas de IA deben incluir una validación robusta para entradas no textuales (imágenes, audio, archivos) para prevenir inyecciones, evasiones o abuso de recursos.

|   #   | Description                                                                                                                                              | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 2.6.1 | Verifique que todas las entradas que no son texto (imágenes, audio, archivos) sean validadas en cuanto a tipo, tamaño y formato antes de ser procesadas. |   1   |  D   |
| 2.6.2 | Verifique que los archivos sean analizados en busca de malware y cargas ocultas esteganográficas antes de su ingestión.                                  |   2   | D/V  |
| 2.6.3 | Verifique que las entradas de imagen/audio sean examinadas para detectar perturbaciones adversariales o patrones de ataque conocidos.                    |   2   | D/V  |
| 2.6.4 | Verifique que las fallas en la validación de entradas multimodales se registren y generen alertas para su investigación.                                 |   3   |  V   |

---

## C2.7 Procedencia y Atribución de la Entrada

Los sistemas de IA deben respaldar la auditoría, el seguimiento de abusos y el cumplimiento mediante la supervisión y el etiquetado del origen de todas las entradas de los usuarios.

|   #   | Description                                                                                                                                                            | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 2.7.1 | Verifique que todas las entradas de usuario estén etiquetadas con metadatos (ID de usuario, sesión, origen, marca de tiempo, dirección IP) al momento de la ingestión. |   1   | D/V  |
| 2.7.2 | Verifique que los metadatos de procedencia se conserven y sean auditables para todas las entradas procesadas.                                                          |   2   | D/V  |
| 2.7.3 | Verifique que las fuentes de entrada anómalas o no confiables sean señaladas y estén sujetas a un escrutinio reforzado o bloqueo.                                      |   2   | D/V  |

---

## C2.8 Detección Adaptativa de Amenazas en Tiempo Real

Los desarrolladores deben emplear sistemas avanzados de detección de amenazas para IA que se adapten a nuevos patrones de ataque y proporcionen protección en tiempo real mediante la coincidencia de patrones compilados.

|   #   | Description                                                                                                                                                                                                                         | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 2.8.1 | Verifique que los patrones de detección de amenazas estén compilados en motores regex optimizados para un filtrado en tiempo real de alto rendimiento con un impacto mínimo en la latencia.                                         |   1   | D/V  |
| 2.8.2 | Verifique que los sistemas de detección de amenazas mantengan bibliotecas de patrones separadas para diferentes categorías de amenazas (inyección de comandos, contenido dañino, datos sensibles, comandos del sistema).            |   1   | D/V  |
| 2.8.3 | Verifique que la detección adaptativa de amenazas incorpore modelos de aprendizaje automático que actualicen la sensibilidad a las amenazas en función de la frecuencia y tasas de éxito de los ataques.                            |   2   | D/V  |
| 2.8.4 | Verifique que los flujos de inteligencia de amenazas en tiempo real actualicen automáticamente las bibliotecas de patrones con nuevas firmas de ataque e IOCs (Indicadores de Compromiso).                                          |   2   | D/V  |
| 2.8.5 | Verifique que las tasas de falsos positivos en la detección de amenazas se monitoreen continuamente y que la especificidad de los patrones se ajuste automáticamente para minimizar la interferencia en los casos de uso legítimos. |   3   | D/V  |
| 2.8.6 | Verifique que el análisis contextual de amenazas considere la fuente de entrada, los patrones de comportamiento del usuario y el historial de la sesión para mejorar la precisión de la detección.                                  |   3   | D/V  |
| 2.8.7 | Verifique que las métricas de rendimiento de detección de amenazas (tasa de detección, latencia de procesamiento, utilización de recursos) se monitoreen y optimicen en tiempo real.                                                |   3   | D/V  |

---

## C2.9 Canal de Validación de Seguridad Multimodal

Los desarrolladores deben proporcionar validación de seguridad para texto, imagen, audio y otras modalidades de entrada de IA con tipos específicos de detección de amenazas y aislamiento de recursos.

|   #   | Description                                                                                                                                                                                                                                                                                       | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 2.9.1 | Verifique que cada modalidad de entrada tenga validadores de seguridad dedicados con patrones de amenazas documentados (texto: inyección de indicaciones, imágenes: esteganografía, audio: ataques de espectrograma) y umbrales de detección.                                                     |   1   | D/V  |
| 2.9.2 | Verifique que las entradas multimodales se procesen en entornos aislados con límites de recursos definidos (memoria, CPU, tiempo de procesamiento) específicos para cada tipo de modalidad y documentados en las políticas de seguridad.                                                          |   2   | D/V  |
| 2.9.3 | Verifique que la detección de ataques cross-modal identifique ataques coordinados que abarquen múltiples tipos de entrada (por ejemplo, cargas útiles esteganográficas en imágenes combinadas con inyección de prompts en texto) mediante reglas de correlación y generación de alertas.          |   2   | D/V  |
| 2.9.4 | Verifique que los fallos de validación multimodal desencadenen un registro detallado que incluya todas las modalidades de entrada, los resultados de la validación, las puntuaciones de amenaza y el análisis de correlación con formatos de registro estructurados para la integración con SIEM. |   3   | D/V  |
| 2.9.5 | Verifique que los clasificadores de contenido específicos de cada modalidad se actualicen según los calendarios documentados (mínimo trimestralmente) con nuevos patrones de amenaza, ejemplos adversariales y puntos de referencia de rendimiento mantenidos por encima de los umbrales mínimos. |   3   | D/V  |

---

## Referencias

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

