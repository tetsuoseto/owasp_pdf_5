# Apéndice D: Gobernanza y Verificación de Codificación Segura Asistida por IA

## Objetivo

Este capítulo define controles organizacionales básicos para el uso seguro y efectivo de herramientas de codificación asistida por IA durante el desarrollo de software, garantizando la seguridad y la trazabilidad a lo largo del ciclo de vida del desarrollo de software (SDLC).

---

## AD.1 Flujo de trabajo de codificación segura asistida por IA

Integre las herramientas de IA en el ciclo de vida de desarrollo de software seguro (SSDLC) de la organización sin debilitar las barreras de seguridad existentes.

|   #    | Description                                                                                                                                                                                                   | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| AD.1.1 | Verifique que un flujo de trabajo documentado describa cuándo y cómo las herramientas de IA pueden generar, refactorizar o revisar código.                                                                    |   1   | D/V  |
| AD.1.2 | Verifique que el flujo de trabajo corresponda a cada fase del SSDLC (diseño, implementación, revisión de código, pruebas, despliegue).                                                                        |   2   |  D   |
| AD.1.3 | Verifique que se recopilen métricas (por ejemplo, densidad de vulnerabilidades, tiempo medio de detección) sobre el código producido por IA y se comparen con las bases de referencia exclusivamente humanas. |   3   | D/V  |

---

## AD.2 Calificación de Herramientas de IA y Modelado de Amenazas

Asegúrese de que las herramientas de codificación de IA sean evaluadas por sus capacidades de seguridad, riesgos y el impacto en la cadena de suministro antes de su adopción.

|   #    | Description                                                                                                                                                                                           | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| AD.2.1 | Verifique que un modelo de amenaza para cada herramienta de IA identifique el uso indebido, la inversión del modelo, la filtración de datos y los riesgos de la cadena de dependencias.               |   1   | D/V  |
| AD.2.2 | Verifique que las evaluaciones de herramientas incluyan análisis estático/dinámico de cualquier componente local y evaluación de los puntos finales SaaS (TLS, autenticación/autorización, registro). |   2   |  D   |
| AD.2.3 | Verifique que las evaluaciones sigan un marco reconocido y se realicen nuevamente después de cambios importantes de versión.                                                                          |   3   | D/V  |

---

## AD.3 Gestión Segura de Indicaciones y Contexto

Evitar la filtración de secretos, código propietario y datos personales al construir indicaciones o contextos para modelos de IA.

|   #    | Description                                                                                                                                                                                | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| AD.3.1 | Verifique que las directrices escritas prohíban enviar secretos, credenciales o datos clasificados en los indicios.                                                                        |   1   | D/V  |
| AD.3.2 | Verifique que los controles técnicos (redacción del lado del cliente, filtros de contexto aprobados) eliminen automáticamente los elementos sensibles.                                     |   2   |  D   |
| AD.3.3 | Verifique que los indicios y respuestas estén tokenizados, cifrados durante la transmisión y en reposo, y que los períodos de retención cumplan con la política de clasificación de datos. |   3   | D/V  |

---

## AD.4 Validación del Código Generado por IA

Detectar y corregir vulnerabilidades introducidas por la salida de IA antes de que el código sea fusionado o desplegado.

|   #    | Description                                                                                                                                                                                               | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| AD.4.1 | Verifique que el código generado por IA siempre sea sometido a una revisión humana del código.                                                                                                            |   1   | D/V  |
| AD.4.2 | Verifique que los escáneres automatizados (SAST/IAST/DAST) se ejecuten en cada solicitud de extracción que contenga código generado por IA y bloqueen las fusiones en caso de hallazgos críticos.         |   2   |  D   |
| AD.4.3 | Verifique que las pruebas de fuzzing diferencial o las pruebas basadas en propiedades demuestren comportamientos críticos para la seguridad (por ejemplo, validación de entrada, lógica de autorización). |   3   | D/V  |

---

## AD.5 Explicabilidad y Trazabilidad de las Sugerencias de Código

Proporcionar a los auditores y desarrolladores una visión sobre por qué se hizo una sugerencia y cómo evolucionó.

|   #    | Description                                                                                                                                                                                                   | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| AD.5.1 | Verifique que los pares de indicaciones/respuestas se registren con los IDs de commit.                                                                                                                        |   1   | D/V  |
| AD.5.2 | Verifique que los desarrolladores puedan mostrar citas del modelo (fragmentos de entrenamiento, documentación) que respalden una sugerencia.                                                                  |   2   |  D   |
| AD.5.3 | Verifique que los informes de explicabilidad se almacenen junto con los artefactos de diseño y se referencien en las revisiones de seguridad, cumpliendo con los principios de trazabilidad de ISO/IEC 42001. |   3   | D/V  |

---

## AD.6 Retroalimentación continua y ajuste fino del modelo

Mejorar el rendimiento de la seguridad del modelo con el tiempo mientras se previene la deriva negativa.

|   #    | Description                                                                                                                                                                                                           | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| AD.6.1 | Verificar que los desarrolladores puedan marcar sugerencias inseguras o no conformes, y que dichas marcas sean registradas.                                                                                           |   1   | D/V  |
| AD.6.2 | Verifique que la retroalimentación agregada informe el ajuste fino periódico o la generación aumentada por recuperación con corpus de codificación segura verificados (por ejemplo, OWASP Cheat Sheets).              |   2   |  D   |
| AD.6.3 | Verifique que un entorno de evaluación de circuito cerrado ejecute pruebas de regresión después de cada afinación; las métricas de seguridad deben cumplir o superar las líneas base anteriores antes del despliegue. |   3   | D/V  |

---

### Referencias

* [NIST AI Risk Management Framework 1.0](https://nvlpubs.nist.gov/nistpubs/ai/nist.ai.100-1.pdf)
* [ISO/IEC 42001:2023 — AI Management Systems Requirements](https://www.iso.org/standard/81230.html)
* [OWASP Secure Coding Practices — Quick Reference Guide](https://owasp.org/www-project-secure-coding-practices-quick-reference-guide/)

