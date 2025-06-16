## Frontispicio

### Acerca del Estándar

El Estándar de Verificación de Seguridad de la Inteligencia Artificial (AISVS) es un catálogo impulsado por la comunidad de requisitos de seguridad que científicos de datos, ingenieros de MLOps, arquitectos de software, desarrolladores, evaluadores, profesionales de seguridad, proveedores de herramientas, reguladores y consumidores pueden utilizar para diseñar, construir, probar y verificar sistemas y aplicaciones con IA confiable. Proporciona un lenguaje común para especificar controles de seguridad a lo largo del ciclo de vida de la IA, desde la recopilación de datos y el desarrollo de modelos hasta la implementación y el monitoreo continuo, de modo que las organizaciones puedan medir y mejorar la resiliencia, privacidad y seguridad de sus soluciones de IA.

### Derechos de autor y licencia

Versión 0.1 (Primer Borrador Público - Trabajo en Progreso), 2025  

![license](images/license.png)
Derechos de autor © 2025 El Proyecto AISVS.  

Publicado bajo la licencia Creative Commons Attribution‑ShareAlike 4.0 International License.
Para cualquier reutilización o distribución, debe comunicar claramente a otros los términos de la licencia de este trabajo.

### Líderes de Proyecto

Jim Manico
Aras “Russ” Memisyazici

### Contribuidores y Revisores

https://github.com/ottosulin
https://github.com/mbhatt1
https://github.com/vineethsai
https://github.com/cciprofm
https://github.com/deepakrpandey12


---

AISVS es un estándar completamente nuevo creado específicamente para abordar los desafíos únicos de seguridad de los sistemas de inteligencia artificial. Aunque se inspira en las mejores prácticas generales de seguridad, cada requisito en AISVS ha sido desarrollado desde cero para reflejar el panorama de amenazas de la IA y ayudar a las organizaciones a construir soluciones de IA más seguras y resilientes.

## Prefacio

¡Bienvenido al Estándar de Verificación de Seguridad en Inteligencia Artificial (AISVS) versión 1.0!

### Introducción

Establecida en 2025 mediante un esfuerzo comunitario colaborativo, AISVS define los requisitos de seguridad a considerar al diseñar, desarrollar, implementar y operar modelos de IA modernos, flujos de trabajo y servicios habilitados con IA.

AISVS v1.0 representa el trabajo combinado de sus líderes de proyecto, grupo de trabajo y colaboradores de la comunidad en general para producir una línea base pragmática y comprobable para asegurar los sistemas de IA.

Nuestro objetivo con esta versión es hacer que AISVS sea fácil de adoptar, manteniéndonos enfocados con precisión en su alcance definido y abordando el panorama de riesgos en rápida evolución, único para la IA.

### Objetivos clave para AISVS Versión 1.0

La versión 1.0 se creará con varios principios rectores.

#### Alcance Bien Definido

Cada requisito debe alinearse con el nombre y la misión de AISVS:

Inteligencia Artificial: los controles operan en la capa de IA/ML (datos, modelo, canalización o inferencia) y son responsabilidad de los profesionales de IA.
Seguridad – Los requisitos mitigan directamente los riesgos identificados de seguridad, privacidad o seguridad.
Verificación: el idioma está redactado de manera que la conformidad pueda ser validada objetivamente.
Estándar: Las secciones siguen una estructura y terminología consistentes para formar una referencia coherente.
​
---

Al seguir AISVS, las organizaciones pueden evaluar sistemáticamente y fortalecer la postura de seguridad de sus soluciones de IA, fomentando una cultura de ingeniería segura en IA.

## Usando el AISVS

El Estándar de Verificación de Seguridad en Inteligencia Artificial (AISVS) define los requisitos de seguridad para aplicaciones y servicios modernos de IA, centrándose en aspectos bajo el control de los desarrolladores de aplicaciones.

El AISVS está destinado a cualquier persona que desarrolle o evalúe la seguridad de aplicaciones de inteligencia artificial, incluidos desarrolladores, arquitectos, ingenieros de seguridad y auditores. Este capítulo presenta la estructura y el uso del AISVS, incluidos sus niveles de verificación y casos de uso previstos.

### Niveles de verificación de seguridad en inteligencia artificial

El AISVS define tres niveles ascendentes de verificación de seguridad. Cada nivel añade profundidad y complejidad, permitiendo a las organizaciones adaptar su postura de seguridad al nivel de riesgo de sus sistemas de IA.

Las organizaciones pueden comenzar en el Nivel 1 y adoptar progresivamente niveles más altos a medida que aumentan la madurez en seguridad y la exposición a amenazas.

#### Definición de los Niveles

Cada requisito en AISVS v1.0 se asigna a uno de los siguientes niveles:

 Requisitos de nivel 1

El Nivel 1 incluye los requisitos de seguridad más críticos y fundamentales. Estos se centran en prevenir ataques comunes que no dependen de otras condiciones previas o vulnerabilidades. La mayoría de los controles del Nivel 1 son fáciles de implementar o lo suficientemente esenciales como para justificar el esfuerzo.

 Requisitos de Nivel 2

El Nivel 2 aborda ataques más avanzados o menos comunes, así como defensas en capas contra amenazas generalizadas. Estos requisitos pueden implicar una lógica más compleja o dirigirse a prerrequisitos específicos de ataques.

 Requisitos de nivel 3

El Nivel 3 incluye controles que suelen ser más difíciles de implementar o que son aplicables en situaciones específicas. Estos a menudo representan mecanismos de defensa en profundidad o mitigaciones contra ataques especializados, dirigidos o de alta complejidad.

#### Rol (D/V)

Cada requisito de AISVS está marcado según la audiencia principal:

D – Requisitos enfocados en desarrolladores
V – Requisitos enfocados en el verificador/auditor
D/V – Relevante tanto para desarrolladores como para verificadores

## Gobernanza de Datos de Entrenamiento C1 y Gestión de Sesgos

### Objetivo de Control

Los datos de entrenamiento deben obtenerse, manejarse y mantenerse de manera que se preserve la procedencia, la seguridad, la calidad y la equidad. Hacerlo cumple con las obligaciones legales y reduce los riesgos de sesgo, envenenamiento o violaciones de privacidad durante todo el ciclo de vida de la IA.

---

### C1.1 Procedencia de los Datos de Entrenamiento

Mantenga un inventario verificable de todos los conjuntos de datos, acepte solo fuentes confiables y registre cada cambio para garantizar la auditabilidad.

 #1.1.1    Level: 1    Role: D/V
 Verifique que se mantenga un inventario actualizado de cada fuente de datos de entrenamiento (origen, responsable/propietario, licencia, método de recopilación, restricciones de uso previstas e historial de procesamiento).
 #1.1.2    Level: 1    Role: D/V
 Verificar que solo se permitan conjuntos de datos evaluados para calidad, representatividad, origen ético y cumplimiento de licencias, reduciendo los riesgos de envenenamiento, sesgos incorporados e infracción de propiedad intelectual.
 #1.1.3    Level: 1    Role: D/V
 Verifique que se aplique la minimización de datos para que se excluyan atributos innecesarios o sensibles.
 #1.1.4    Level: 2    Role: D/V
 Verifique que todos los cambios en el conjunto de datos estén sujetos a un flujo de trabajo de aprobación registrado.
 #1.1.5    Level: 2    Role: D/V
 Verifique que la calidad del etiquetado/anotación esté garantizada mediante verificaciones cruzadas o consenso de los revisores.
 #1.1.6    Level: 2    Role: D/V
 Verifique que se mantengan "tarjetas de datos" o "hojas de datos para conjuntos de datos" para los conjuntos de datos de entrenamiento significativos, detallando características, motivaciones, composición, procesos de recolección, preprocesamiento y usos recomendados/desaconsejados.

---

### C1.2 Seguridad e Integridad de los Datos de Entrenamiento

Restringir el acceso, cifrar los datos en reposo y en tránsito, y validar la integridad para bloquear la manipulación o el robo.

 #1.2.1    Level: 1    Role: D/V
 Verifique que los controles de acceso protejan el almacenamiento y las canalizaciones.
 #1.2.2    Level: 2    Role: D/V
 Verifique que los conjuntos de datos estén cifrados en tránsito y, para toda la información sensible o personalmente identificable (PII), en reposo, utilizando algoritmos criptográficos estándar de la industria y prácticas de gestión de claves.
 #1.2.3    Level: 2    Role: D/V
 Verifique que se utilicen hashes criptográficos o firmas digitales para asegurar la integridad de los datos durante el almacenamiento y la transferencia, y que se apliquen técnicas automatizadas de detección de anomalías para proteger contra modificaciones no autorizadas o corrupción, incluyendo intentos dirigidos de envenenamiento de datos.
 #1.2.4    Level: 3    Role: D/V
 Verifique que las versiones del conjunto de datos estén registradas para permitir la reversión.
 #1.2.5    Level: 2    Role: D/V
 Verifique que los datos obsoletos se eliminen de forma segura o se anonimicen conforme a las políticas de retención de datos, los requisitos regulatorios y para reducir la superficie de ataque.

---

### C1.3 Integridad y Equidad de la Representación

Detectar sesgos demográficos y aplicar mitigación para que las tasas de error del modelo sean equitativas entre los grupos.

 #1.3.1    Level: 1    Role: D/V
 Verifique que los conjuntos de datos sean analizados para detectar desequilibrios representativos y posibles sesgos en atributos legalmente protegidos (por ejemplo, raza, género, edad) y otras características éticamente sensibles relevantes para el dominio de aplicación del modelo (por ejemplo, estatus socioeconómico, ubicación).
 #1.3.2    Level: 2    Role: D/V
 Verifique que los sesgos identificados se mitiguen mediante estrategias documentadas como el reequilibrio, la aumentación de datos dirigida, ajustes algorítmicos (por ejemplo, técnicas de preprocesamiento, procesamiento interno, postprocesamiento) o reponderación, y que se evalúe el impacto de la mitigación tanto en la equidad como en el rendimiento general del modelo.
 #1.3.3    Level: 2    Role: D/V
 Verifique que las métricas de equidad posteriores al entrenamiento sean evaluadas y documentadas.
 #1.3.4    Level: 3    Role: D/V
 Verifique que una política de gestión de sesgos en el ciclo de vida asigne responsables y un ritmo de revisión.

---

### C1.4 Calidad, Integridad y Seguridad del Etiquetado de Datos de Entrenamiento

Proteja las etiquetas con cifrado y requiera una revisión dual para las clases críticas.

 #1.4.1    Level: 2    Role: D/V
 Verifique que la calidad del etiquetado/anotación esté garantizada mediante directrices claras, revisiones cruzadas por parte de los evaluadores, mecanismos de consenso (p. ej., monitoreo del acuerdo interanotadores) y procesos definidos para resolver discrepancias.
 #1.4.2    Level: 2    Role: D/V
 Verifique que se apliquen hashes criptográficos o firmas digitales a los artefactos de etiquetado para garantizar su integridad y autenticidad.
 #1.4.3    Level: 2    Role: D/V
 Verifique que las interfaces y plataformas de etiquetado apliquen controles de acceso estrictos, mantengan registros de auditoría a prueba de manipulaciones de todas las actividades de etiquetado y protejan contra modificaciones no autorizadas.
 #1.4.4    Level: 3    Role: D/V
 Verifique que las etiquetas críticas para la seguridad, protección o equidad (por ejemplo, la identificación de contenido tóxico, hallazgos médicos críticos) reciban una revisión dual independiente obligatoria o una verificación robusta equivalente.
 #1.4.5    Level: 2    Role: D/V
 Verifique que la información sensible (incluida la información de identificación personal, PII) capturada inadvertidamente o necesariamente presente en las etiquetas esté redactada, seudonimizada, anonimizada o cifrada en reposo y en tránsito, de acuerdo con los principios de minimización de datos.
 #1.4.6    Level: 2    Role: D/V
 Verifique que las guías de etiquetado e instrucciones sean completas, estén controladas por versiones y revisadas por pares.
 #1.4.7    Level: 2    Role: D/V
 Verifique que los esquemas de datos (incluidos los de etiquetas) estén claramente definidos y bajo control de versiones.
 #1.8.2    Level: 2    Role: D/V
 Verifique que los flujos de trabajo de etiquetado subcontratados o generados mediante crowdsourcing incluyan salvaguardas técnicas/procedimentales para garantizar la confidencialidad, integridad de los datos, calidad de las etiquetas y prevenir la filtración de datos.

---

### C1.5 Aseguramiento de la Calidad de los Datos de Entrenamiento

Combine la validación automatizada, las verificaciones manuales aleatorias y la remediación registrada para garantizar la fiabilidad del conjunto de datos.

 #1.5.1    Level: 1    Role: D
 Verifique que las pruebas automatizadas detecten errores de formato, valores nulos y desalineaciones de etiquetas en cada ingestión o transformación significativa.
 #1.5.2    Level: 1    Role: D/V
 Verifique que los conjuntos de datos fallidos estén en cuarentena con registros de auditoría.
 #1.5.3    Level: 2    Role: V
 Verifique que las inspecciones manuales aleatorias realizadas por expertos en el dominio cubran una muestra estadísticamente significativa (por ejemplo, ≥1% o 1,000 muestras, lo que sea mayor, o según lo determinado por la evaluación de riesgos) para identificar problemas sutiles de calidad que no sean detectados por la automatización.
 #1.5.4    Level: 2    Role: D/V
 Verifique que los pasos de remediación estén añadidos a los registros de procedencia.
 #1.5.5    Level: 2    Role: D/V
 Verifique que los controles de calidad bloqueen conjuntos de datos deficientes a menos que se aprueben excepciones.

---

### C1.6 Detección de envenenamiento de datos

Aplique detección estadística de anomalías y flujos de trabajo de cuarentena para detener inserciones adversariales.

 #1.6.1    Level: 2    Role: D/V
 Verifique que las técnicas de detección de anomalías (por ejemplo, métodos estadísticos, detección de valores atípicos, análisis de incrustaciones) se apliquen a los datos de entrenamiento en la ingestión y antes de los principales procesos de entrenamiento para identificar posibles ataques de envenenamiento o corrupción involuntaria de datos.
 #1.6.2    Level: 2    Role: D/V
 Verifique que las muestras marcadas desencadenen una revisión manual antes del entrenamiento.
 #1.6.3    Level: 2    Role: V
 Verifique que los resultados alimenten el expediente de seguridad del modelo e informen la inteligencia de amenazas continua.
 #1.6.4    Level: 3    Role: D/V
 Verifique que la lógica de detección se actualice con nueva información de amenazas.
 #1.6.5    Level: 3    Role: D/V
 Verifique que los pipelines de aprendizaje en línea monitoreen el cambio en la distribución.
 #1.6.6    Level: 3    Role: D/V
 Verifique que se consideren e implementen defensas específicas contra tipos conocidos de ataques de envenenamiento de datos (por ejemplo, inversión de etiquetas, inserción de disparadores de puerta trasera, ataques de instancias influyentes) basándose en el perfil de riesgo del sistema y las fuentes de datos.

---

### C1.7 Eliminación de Datos del Usuario y Aplicación del Consentimiento

Respetar las solicitudes de eliminación y de retirada del consentimiento en todos los conjuntos de datos, copias de seguridad y artefactos derivados.

 #1.7.1    Level: 1    Role: D/V
 Verifique que los flujos de trabajo de eliminación purguen los datos primarios y derivados y evalué el impacto en el modelo, y que el impacto en los modelos afectados sea evaluado y, si es necesario, abordado (por ejemplo, mediante el reentrenamiento o recalibración).
 #1.7.2    Level: 2    Role: D
 Verifique que existan mecanismos para rastrear y respetar el alcance y el estado del consentimiento del usuario (y las retiradas) para los datos utilizados en el entrenamiento, y que el consentimiento se valide antes de incorporar los datos en nuevos procesos de entrenamiento o actualizaciones significativas del modelo.
 #1.7.3    Level: 2    Role: V
 Verifique que los flujos de trabajo sean probados anualmente y registrados.

---

### C1.8 Seguridad en la Cadena de Suministro

Verifique a los proveedores externos de datos y confirme la integridad a través de canales autenticados y cifrados.

 #1.8.1    Level: 2    Role: D/V
 Verificar que los proveedores de datos externos, incluidos los proveedores de modelos preentrenados y conjuntos de datos externos, pasen por una debida diligencia en seguridad, privacidad, obtención ética y calidad de datos antes de que sus datos o modelos sean integrados.
 #1.8.2    Level: 1    Role: D
 Verifique que las transferencias externas utilicen TLS/autenticación y comprobaciones de integridad.
 #1.8.3    Level: 2    Role: D/V
 Verifique que las fuentes de datos de alto riesgo (por ejemplo, conjuntos de datos de código abierto con procedencia desconocida, proveedores no evaluados) reciban un escrutinio reforzado, como análisis en entornos aislados (sandbox), controles exhaustivos de calidad/sesgo y detección específica de envenenamiento, antes de su uso en aplicaciones sensibles.
 #1.8.4    Level: 3    Role: D/V
 Verifique que los modelos preentrenados obtenidos de terceros sean evaluados para detectar sesgos incorporados, posibles puertas traseras, la integridad de su arquitectura y la procedencia de sus datos originales de entrenamiento antes de su ajuste fino o implementación.

---

### C1.9 Detección de Muestras Adversariales

Implemente medidas durante la fase de entrenamiento, como el entrenamiento adversarial, para mejorar la resistencia del modelo contra ejemplos adversariales.

 #1.9.1    Level: 3    Role: D/V
 Verifique que se implementen y ajusten defensas adecuadas, como el entrenamiento adversarial (utilizando ejemplos adversariales generados), la aumentación de datos con entradas perturbadas o técnicas de optimización robusta, para los modelos relevantes según la evaluación de riesgos.
 #1.9.2    Level: 2    Role: D/V
 Verifique que si se utiliza entrenamiento adversarial, la generación, gestión y versionado de conjuntos de datos adversariales estén documentados y controlados.
 #1.9.3    Level: 3    Role: D/V
 Verifique que se evalúe, documente y supervise el impacto del entrenamiento de robustez adversarial en el rendimiento del modelo (tanto contra entradas limpias como adversariales) y en las métricas de equidad.
 #1.9.4    Level: 3    Role: D/V
 Verifique que las estrategias para el entrenamiento adversarial y la robustez sean revisadas y actualizadas periódicamente para contrarrestar las técnicas de ataque adversarial en evolución.

---

### C1.10 Linaje y trazabilidad de datos

Rastrea todo el recorrido de cada punto de datos desde la fuente hasta la entrada del modelo para garantizar la auditabilidad y la respuesta ante incidentes.

 #1.10.1    Level: 2    Role: D/V
 Verifique que el linaje de cada punto de datos, incluidas todas las transformaciones, aumentos y fusiones, esté registrado y pueda ser reconstruido.
 #1.10.2    Level: 2    Role: D/V
 Verifique que los registros de linaje sean inmutables, estén almacenados de forma segura y sean accesibles para auditorías o investigaciones.
 #1.10.3    Level: 2    Role: D/V
 Verifique que el seguimiento de linaje cubra tanto los datos crudos como los sintéticos.

---

### C1.11 Gestión de Datos Sintéticos

Asegurar que los datos sintéticos estén debidamente gestionados, etiquetados y evaluados en cuanto a riesgos.

 #1.11.1    Level: 2    Role: D/V
 Verifique que todos los datos sintéticos estén claramente etiquetados y sean distinguibles de los datos reales a lo largo de todo el flujo de trabajo.
 #1.11.2    Level: 2    Role: D/V
 Verifique que el proceso de generación, los parámetros y el uso previsto de los datos sintéticos estén documentados.
 #1.11.3    Level: 2    Role: D/V
 Verifique que los datos sintéticos sean evaluados en cuanto a riesgos de sesgo, filtración de privacidad y problemas de representación antes de usarlos en el entrenamiento.

---

### C1.12 Monitoreo de Acceso a Datos y Detección de Anomalías

Monitorear y alertar sobre accesos inusuales a los datos de entrenamiento para detectar amenazas internas o exfiltración.

 #1.12.1    Level: 2    Role: D/V
 Verifique que todo acceso a los datos de entrenamiento esté registrado, incluyendo usuario, hora y acción.
 #1.12.2    Level: 2    Role: D/V
 Verifique que los registros de acceso se revisen regularmente para detectar patrones inusuales, como grandes exportaciones o accesos desde nuevas ubicaciones.
 #1.12.3    Level: 2    Role: D/V
 Verifique que se generen alertas para eventos de acceso sospechosos y que se investiguen de manera pronta.

---

### C1.13 Políticas de Retención y Expiración de Datos

Definir y hacer cumplir los períodos de retención de datos para minimizar el almacenamiento innecesario de datos.

 #1.13.1    Level: 1    Role: D/V
 Verifique que se definan períodos de retención explícitos para todos los conjuntos de datos de entrenamiento.
 #1.13.2    Level: 2    Role: D/V
 Verifique que los conjuntos de datos se expiren, eliminen o revisen automáticamente para su eliminación al final de su ciclo de vida.
 #1.13.3    Level: 2    Role: D/V
 Verifique que las acciones de retención y eliminación estén registradas y sean auditables.

---

### C1.14 Cumplimiento Regulatorio y Jurisdiccional

Asegúrese de que todos los datos de entrenamiento cumplan con las leyes y regulaciones aplicables.

 #1.14.1    Level: 2    Role: D/V
 Verifique que los requisitos de residencia de datos y de transferencia transfronteriza estén identificados y se apliquen a todos los conjuntos de datos.
 #1.14.2    Level: 2    Role: D/V
 Verifique que las regulaciones específicas del sector (por ejemplo, salud, finanzas) sean identificadas y abordadas en el manejo de datos.
 #1.14.3    Level: 2    Role: D/V
 Verifique que el cumplimiento con las leyes de privacidad relevantes (por ejemplo, GDPR, CCPA) esté documentado y se revise regularmente.

---

### C1.15 Marcado de Agua y Huellas Digitales de Datos

Detectar el uso no autorizado o la filtración de datos propietarios o sensibles.

 #1.15.1    Level: 3    Role: D/V
 Verifique que los conjuntos de datos o subconjuntos estén marcados con una marca de agua o huella digital cuando sea factible.
 #1.15.2    Level: 3    Role: D/V
 Verifique que los métodos de marcas de agua/huellas digitales no introduzcan sesgos ni riesgos de privacidad.
 #1.15.3    Level: 3    Role: D/V
 Verificar que se realicen controles periódicos para detectar el uso no autorizado o la filtración de datos con marca de agua.

---

### C1.16 Gestión de los Derechos del Sujeto de Datos

Apoyar los derechos del sujeto de datos como el acceso, la rectificación, la restricción y la oposición.

 #1.16.1    Level: 2    Role: D/V
 Verifique que existan mecanismos para responder a las solicitudes del sujeto de datos para acceso, rectificación, restricción u oposición.
 #1.16.2    Level: 2    Role: D/V
 Verifique que las solicitudes sean registradas, rastreadas y cumplidas dentro de los plazos legalmente establecidos.
 #1.16.3    Level: 2    Role: D/V
 Verifique que los procesos de derechos del sujeto de datos sean probados y revisados regularmente para garantizar su efectividad.

---

### C1.17 Análisis del Impacto de la Versión del Conjunto de Datos

Evalúe el impacto de los cambios en el conjunto de datos antes de actualizar o reemplazar las versiones.

 #1.17.1    Level: 2    Role: D/V
 Verifique que se realice un análisis de impacto antes de actualizar o reemplazar una versión del conjunto de datos, cubriendo el rendimiento del modelo, la equidad y el cumplimiento.
 #1.17.2    Level: 2    Role: D/V
 Verifique que los resultados del análisis de impacto estén documentados y revisados por las partes interesadas relevantes.
 #1.17.3    Level: 2    Role: D/V
 Verifique que existan planes de reversión en caso de que las nuevas versiones introduzcan riesgos inaceptables o regresiones.

---

### C1.18 Seguridad de la Fuerza Laboral en Anotación de Datos

Garantizar la seguridad e integridad del personal involucrado en la anotación de datos.

 #1.18.1    Level: 2    Role: D/V
 Verifique que todo el personal involucrado en la anotación de datos haya pasado por una verificación de antecedentes y esté capacitado en seguridad y privacidad de datos.
 #1.18.2    Level: 2    Role: D/V
 Verifique que todo el personal de anotación firme acuerdos de confidencialidad y no divulgación.
 #1.18.3    Level: 2    Role: D/V
 Verifique que las plataformas de anotación implementen controles de acceso y monitoreen las amenazas internas.

---

### Referencias

NIST AI Risk Management Framework
EU AI Act – Article 10: Data & Data Governance
MITRE ATLAS: Adversary Tactics for AI
Survey of ML Bias Mitigation Techniques – MDPI
Data Provenance & Lineage Best Practices – Nightfall AI
Data Labeling Quality Standards – LabelYourData
Training Data Poisoning Guide – Lakera.ai
CISA Advisory: Securing Data for AI Systems
ISO/IEC 23053: AI Management Systems Framework
IBM: What is AI Governance?
Google AI Principles
GDPR & AI Training Data – DataProtectionReport
Supply-Chain Security for AI Data – AppSOC
OpenAI Privacy Center – Data Deletion Controls
Adversarial ML Dataset – Kaggle

## Validación de la entrada del usuario C2

### Objetivo de Control

La validación robusta de la entrada del usuario es una defensa de primera línea contra algunos de los ataques más dañinos en los sistemas de IA. Los ataques de inyección de comandos pueden anular las instrucciones del sistema, filtrar datos sensibles o dirigir el modelo hacia comportamientos no permitidos. A menos que existan filtros dedicados y jerarquías de instrucciones, la investigación muestra que los "jailbreaks multi-disparo" que explotan ventanas de contexto muy largas serán efectivos. Además, los ataques sutiles de perturbación adversarial, como los intercambios de homoglifos o el leetspeak, pueden cambiar silenciosamente las decisiones de un modelo.

---

### C2.1 Defensa contra la inyección de indicaciones

La inyección de indicaciones es uno de los principales riesgos para los sistemas de IA. Las defensas contra esta táctica emplean una combinación de filtros de patrones estáticos, clasificadores dinámicos y la aplicación de jerarquías de instrucciones.

 #2.1.1    Level: 1    Role: D/V
 Verifique que las entradas del usuario sean filtradas contra una biblioteca continuamente actualizada de patrones conocidos de inyección de indicaciones (palabras clave de jailbreak, "ignorar lo anterior", cadenas de juego de roles, ataques indirectos en HTML/URL).
 #2.1.2    Level: 1    Role: D/V
 Verifique que el sistema imponga una jerarquía de instrucciones en la que los mensajes del sistema o del desarrollador prevalezcan sobre las instrucciones del usuario, incluso después de la expansión de la ventana de contexto.
 #2.1.3    Level: 2    Role: D/V
 Verifique que las pruebas de evaluación adversarial (por ejemplo, indicaciones "many-shot" del Equipo Rojo) se realicen antes de cada lanzamiento de modelo o plantilla de indicaciones, con umbrales de tasa de éxito y bloqueadores automáticos para regresiones.
 #2.1.4    Level: 2    Role: D
 Verifique que los prompts provenientes de contenido de terceros (páginas web, PDFs, correos electrónicos) sean limpiados en un contexto de análisis aislado antes de ser concatenados en el prompt principal.
 #2.1.5    Level: 3    Role: D/V
 Verifique que todas las actualizaciones de reglas de filtro de indicaciones, versiones del modelo clasificador y cambios en la lista de bloqueo estén bajo control de versiones y sean auditables.

---

### C2.2 Resistencia a Ejemplos Adversarios

Los modelos de Procesamiento de Lenguaje Natural (PLN) siguen siendo vulnerables a perturbaciones sutiles a nivel de carácter o palabra que los humanos a menudo pasan por alto, pero que los modelos tienden a clasificar incorrectamente.

 #2.2.1    Level: 1    Role: D
 Verifique que los pasos básicos de normalización de entrada (Unicode NFC, mapeo de homógrafos, recorte de espacios en blanco) se ejecuten antes de la tokenización.
 #2.2.2    Level: 2    Role: D/V
 Verifique que la detección estadística de anomalías marque entradas con una distancia de edición inusualmente alta respecto a las normas del lenguaje, tokens repetidos en exceso o distancias anormales en las incrustaciones.
 #2.2.3    Level: 2    Role: D
 Verifique que la canalización de inferencia soporte variantes opcionales de modelos reforzados mediante entrenamiento adversarial o capas de defensa (por ejemplo, aleatorización, destilación defensiva) para puntos finales de alto riesgo.
 #2.2.4    Level: 2    Role: V
 Verifique que las entradas adversarias sospechosas estén aisladas, registradas con cargas completas (después de la redacción de información personal identificable).
 #2.2.5    Level: 3    Role: D/V
 Verifique que las métricas de robustez (tasa de éxito de los conjuntos de ataques conocidos) se monitoreen a lo largo del tiempo y que las regresiones activen un bloqueo de lanzamiento.

---

### C2.3 Validación de Esquema, Tipo y Longitud

Los ataques de IA que presentan entradas malformadas o de tamaño excesivo pueden causar errores de análisis, desbordamiento de indicaciones entre campos y agotamiento de recursos. La aplicación estricta de esquemas también es un requisito previo al realizar llamadas a herramientas deterministas.

 #2.3.1    Level: 1    Role: D
 Verifique que cada punto final de llamada de API o función defina un esquema de entrada explícito (JSON Schema, Protobuf o equivalente multimodal) y que las entradas sean validadas antes del ensamblaje del prompt.
 #2.3.2    Level: 1    Role: D/V
 Verifique que las entradas que excedan los límites máximos de tokens o bytes sean rechazadas con un error seguro y nunca se trunquen silenciosamente.
 #2.3.3    Level: 2    Role: D/V
 Verifique que las comprobaciones de tipo (por ejemplo, rangos numéricos, valores enum, tipos MIME para imágenes/audio) se apliquen del lado del servidor, no solo en el código del cliente.
 #2.3.4    Level: 2    Role: D
 Verifique que los validadores semánticos (por ejemplo, JSON Schema) se ejecuten en tiempo constante para prevenir ataques de denegación de servicio algorítmica (DoS).
 #2.3.5    Level: 3    Role: V
 Verifique que los fallos de validación se registren con fragmentos de carga útiles redactados y códigos de error inequívocos para facilitar el triaje de seguridad.

---

### C2.4 Evaluación de Contenido y Políticas

Los desarrolladores deberían poder detectar indicaciones sintácticamente válidas que soliciten contenido prohibido (como instrucciones ilícitas, discursos de odio y texto con derechos de autor) y luego impedir que se propaguen.

 #2.4.1    Level: 1    Role: D
 Verifique que un clasificador de contenido (de cero disparos o ajustado finamente) puntúe cada entrada para violencia, autolesiones, odio, contenido sexual y solicitudes ilegales, con umbrales configurables.
 #2.4.2    Level: 1    Role: D/V
 Verifique que las entradas que violen las políticas reciban rechazos estandarizados o completaciones seguras para que no se propaguen a llamadas posteriores de modelos de lenguaje grandes (LLM).
 #2.4.3    Level: 2    Role: D
 Verifique que el modelo de filtrado o el conjunto de reglas se reentrenen/actualicen al menos trimestralmente, incorporando los nuevos patrones de evasión de restricciones o elusión de políticas observados.
 #2.4.4    Level: 2    Role: D
 Verificar que el filtrado respete las políticas específicas del usuario (edad, restricciones legales regionales) mediante reglas basadas en atributos resueltas en el momento de la solicitud.
 #2.4.5    Level: 3    Role: V
 Verifique que los registros de selección incluyan puntajes de confianza del clasificador y etiquetas de categoría de política para la correlación SOC y la reproducción futura de red team.

---

### C2.5 Limitación de la tasa de entrada y prevención de abusos

Los desarrolladores deben prevenir el abuso, el agotamiento de recursos y los ataques automatizados contra los sistemas de IA limitando las tasas de entrada y detectando patrones de uso anómalos.

 #2.5.1    Level: 1    Role: D/V
 Verifique que los límites de tasa por usuario, por IP y por clave API se apliquen en todos los puntos de entrada de datos.
 #2.5.2    Level: 2    Role: D/V
 Verifique que los límites de velocidad punta y sostenida estén ajustados para prevenir ataques de Denegación de Servicio (DoS) y ataques de fuerza bruta.
 #2.5.3    Level: 2    Role: D/V
 Verifique que los patrones de uso anómalos (por ejemplo, solicitudes rápidas consecutivas, inundación de entradas) desencadenen bloqueos automáticos o escalaciones.
 #2.5.4    Level: 3    Role: V
 Verifique que los registros de prevención de abusos se conserven y revisen para identificar patrones de ataque emergentes.

---

### C2.6 Validación de Entrada Multimodal

Los sistemas de IA deben incluir una validación robusta para entradas no textuales (imágenes, audio, archivos) para prevenir inyecciones, evasiones o abuso de recursos.

 #2.6.1    Level: 1    Role: D
 Verifique que todas las entradas que no son texto (imágenes, audio, archivos) sean validadas en cuanto a tipo, tamaño y formato antes de ser procesadas.
 #2.6.2    Level: 2    Role: D/V
 Verifique que los archivos sean analizados en busca de malware y cargas ocultas esteganográficas antes de su ingestión.
 #2.6.3    Level: 2    Role: D/V
 Verifique que las entradas de imagen/audio sean examinadas para detectar perturbaciones adversariales o patrones de ataque conocidos.
 #2.6.4    Level: 3    Role: V
 Verifique que las fallas en la validación de entradas multimodales se registren y generen alertas para su investigación.

---

### C2.7 Procedencia y Atribución de la Entrada

Los sistemas de IA deben respaldar la auditoría, el seguimiento de abusos y el cumplimiento mediante la supervisión y el etiquetado del origen de todas las entradas de los usuarios.

 #2.7.1    Level: 1    Role: D/V
 Verifique que todas las entradas de usuario estén etiquetadas con metadatos (ID de usuario, sesión, origen, marca de tiempo, dirección IP) al momento de la ingestión.
 #2.7.2    Level: 2    Role: D/V
 Verifique que los metadatos de procedencia se conserven y sean auditables para todas las entradas procesadas.
 #2.7.3    Level: 2    Role: D/V
 Verifique que las fuentes de entrada anómalas o no confiables sean señaladas y estén sujetas a un escrutinio reforzado o bloqueo.

---

### C2.8 Detección Adaptativa de Amenazas en Tiempo Real

Los desarrolladores deben emplear sistemas avanzados de detección de amenazas para IA que se adapten a nuevos patrones de ataque y proporcionen protección en tiempo real mediante la coincidencia de patrones compilados.

 #2.8.1    Level: 1    Role: D/V
 Verifique que los patrones de detección de amenazas estén compilados en motores regex optimizados para un filtrado en tiempo real de alto rendimiento con un impacto mínimo en la latencia.
 #2.8.2    Level: 1    Role: D/V
 Verifique que los sistemas de detección de amenazas mantengan bibliotecas de patrones separadas para diferentes categorías de amenazas (inyección de comandos, contenido dañino, datos sensibles, comandos del sistema).
 #2.8.3    Level: 2    Role: D/V
 Verifique que la detección adaptativa de amenazas incorpore modelos de aprendizaje automático que actualicen la sensibilidad a las amenazas en función de la frecuencia y tasas de éxito de los ataques.
 #2.8.4    Level: 2    Role: D/V
 Verifique que los flujos de inteligencia de amenazas en tiempo real actualicen automáticamente las bibliotecas de patrones con nuevas firmas de ataque e IOCs (Indicadores de Compromiso).
 #2.8.5    Level: 3    Role: D/V
 Verifique que las tasas de falsos positivos en la detección de amenazas se monitoreen continuamente y que la especificidad de los patrones se ajuste automáticamente para minimizar la interferencia en los casos de uso legítimos.
 #2.8.6    Level: 3    Role: D/V
 Verifique que el análisis contextual de amenazas considere la fuente de entrada, los patrones de comportamiento del usuario y el historial de la sesión para mejorar la precisión de la detección.
 #2.8.7    Level: 3    Role: D/V
 Verifique que las métricas de rendimiento de detección de amenazas (tasa de detección, latencia de procesamiento, utilización de recursos) se monitoreen y optimicen en tiempo real.

---

### C2.9 Canal de Validación de Seguridad Multimodal

Los desarrolladores deben proporcionar validación de seguridad para texto, imagen, audio y otras modalidades de entrada de IA con tipos específicos de detección de amenazas y aislamiento de recursos.

 #2.9.1    Level: 1    Role: D/V
 Verifique que cada modalidad de entrada tenga validadores de seguridad dedicados con patrones de amenazas documentados (texto: inyección de indicaciones, imágenes: esteganografía, audio: ataques de espectrograma) y umbrales de detección.
 #2.9.2    Level: 2    Role: D/V
 Verifique que las entradas multimodales se procesen en entornos aislados con límites de recursos definidos (memoria, CPU, tiempo de procesamiento) específicos para cada tipo de modalidad y documentados en las políticas de seguridad.
 #2.9.3    Level: 2    Role: D/V
 Verifique que la detección de ataques cross-modal identifique ataques coordinados que abarquen múltiples tipos de entrada (por ejemplo, cargas útiles esteganográficas en imágenes combinadas con inyección de prompts en texto) mediante reglas de correlación y generación de alertas.
 #2.9.4    Level: 3    Role: D/V
 Verifique que los fallos de validación multimodal desencadenen un registro detallado que incluya todas las modalidades de entrada, los resultados de la validación, las puntuaciones de amenaza y el análisis de correlación con formatos de registro estructurados para la integración con SIEM.
 #2.9.5    Level: 3    Role: D/V
 Verifique que los clasificadores de contenido específicos de cada modalidad se actualicen según los calendarios documentados (mínimo trimestralmente) con nuevos patrones de amenaza, ejemplos adversariales y puntos de referencia de rendimiento mantenidos por encima de los umbrales mínimos.

---

### Referencias

LLM01:2025 Prompt Injection – OWASP Top 10 for LLM & Generative AI Security
Generative AI's Biggest Security Flaw Is Not Easy to Fix
Many-shot jailbreaking \ Anthropic
$PDF$ OpenAI GPT-4.5 System Card
Notebook for the CheckThat Lab at CLEF 2024
Mitigate jailbreaks and prompt injections – Anthropic
Chapter 3 MITRE ATT\&CK – Adversarial Model Analysis
OWASP Top 10 for LLM Applications 2025 – WorldTech IT
OWASP Machine Learning Security Top Ten
Few words about AI Security – Jussi Metso
How To Ensure LLM Output Adheres to a JSON Schema | Modelmetry
Easily enforcing valid JSON schema following – API
AI Safety + Cybersecurity R\&D Tracker – Fairly AI
Anthropic makes 'jailbreak' advance to stop AI models producing harmful results
Pattern matching filter rules - IBM
Real-time Threat Detection

## Gestión del Ciclo de Vida del Modelo C3 y Control de Cambios

### Objetivo de Control

Los sistemas de IA deben implementar procesos de control de cambios que eviten modificaciones no autorizadas o inseguras del modelo que lleguen a producción. Este control garantiza la integridad del modelo a lo largo de todo el ciclo de vida, desde el desarrollo hasta el despliegue y la desactivación, lo que permite una respuesta rápida ante incidentes y mantiene la responsabilidad por todos los cambios.

Objetivo principal de seguridad: Solo los modelos autorizados y validados llegan a producción mediante procesos controlados que mantienen la integridad, trazabilidad y recuperabilidad.

---

### C3.1 Autorización e Integridad del Modelo

Solo los modelos autorizados con integridad verificada llegan a los entornos de producción.

 #3.1.1    Level: 1    Role: D/V
 Verifique que todos los artefactos del modelo (pesos, configuraciones, tokenizadores) estén firmados criptográficamente por entidades autorizadas antes del despliegue.
 #3.1.2    Level: 1    Role: D/V
 Verifique que la integridad del modelo se valide en el momento del despliegue y que las fallas en la verificación de la firma eviten la carga del modelo.
 #3.1.3    Level: 2    Role: D/V
 Verifique que los registros de procedencia del modelo incluyan la identidad de la entidad autorizante, sumas de verificación de los datos de entrenamiento, resultados de pruebas de validación con estado de aprobado/reprobado y una marca de tiempo de creación.
 #3.1.4    Level: 2    Role: D/V
 Verifique que todos los artefactos del modelo utilicen versionado semántico (MAYOR.MENOR.PARCHE) con criterios documentados que especifiquen cuándo se incrementa cada componente de la versión.
 #3.1.5    Level: 2    Role: V
 Verifique que el seguimiento de dependencias mantenga un inventario en tiempo real que permita la identificación rápida de todos los sistemas consumidores.

---

### C3.2 Validación y Pruebas del Modelo

Los modelos deben pasar las validaciones definidas de seguridad y protección antes de su implementación.

 #3.2.1    Level: 1    Role: D/V
 Verifique que los modelos se sometan a pruebas automáticas de seguridad que incluyan validación de entradas, saneamiento de salidas y evaluaciones de seguridad con umbrales de aprobación/reprobación organizacionales preacordados antes del despliegue.
 #3.2.2    Level: 1    Role: D/V
 Verifique que las fallas de validación bloqueen automáticamente el despliegue del modelo después de la aprobación explícita de anulación por parte del personal autorizado previamente designado, con justificaciones comerciales documentadas.
 #3.2.3    Level: 2    Role: V
 Verifique que los resultados de las pruebas estén firmados criptográficamente y vinculados de manera inmutable al hash de la versión específica del modelo que se está validando.
 #3.2.4    Level: 2    Role: D/V
 Verifique que los despliegues de emergencia requieran una evaluación de riesgos de seguridad documentada y la aprobación de una autoridad de seguridad predesignada dentro de los plazos previamente acordados.

---

### C3.3 Implementación Controlada y Reversión

Las implementaciones de modelos deben ser controladas, monitoreadas y reversibles.

 #3.3.1    Level: 1    Role: D
 Verifique que los despliegues en producción implementen mecanismos de implementación gradual (despliegues canary, despliegues blue-green) con activadores de reversión automatizados basados en tasas de error preacordadas, umbrales de latencia o criterios de alerta de seguridad.
 #3.3.2    Level: 1    Role: D/V
 Verifique que las capacidades de reversión restauren el estado completo del modelo (pesos, configuraciones, dependencias) de manera atómica dentro de las ventanas de tiempo organizacionales predefinidas.
 #3.3.3    Level: 2    Role: D/V
 Verifique que los procesos de despliegue validen las firmas criptográficas y calculen sumas de verificación de integridad antes de la activación del modelo, deteniendo el despliegue en caso de cualquier discrepancia.
 #3.3.4    Level: 2    Role: D/V
 Verifique que las capacidades de apagado de emergencia del modelo puedan deshabilitar los puntos finales del modelo dentro de los tiempos de respuesta predefinidos mediante disyuntores automáticos o interruptores manuales de apagado.
 #3.3.5    Level: 2    Role: V
 Verifique que los artefactos de reversión (versiones anteriores del modelo, configuraciones, dependencias) se conserven según las políticas organizacionales utilizando almacenamiento inmutable para la respuesta a incidentes.

---

### C3.4 Responsabilidad por Cambios y Auditoría

Todos los cambios en el ciclo de vida del modelo deben ser rastreables y auditables.

 #3.4.1    Level: 1    Role: V
 Verifique que todos los cambios en el modelo (despliegue, configuración, retiro) generen registros de auditoría inmutables que incluyan una marca de tiempo, una identidad de actor autenticada, un tipo de cambio y los estados antes y después.
 #3.4.2    Level: 2    Role: D/V
 Verifique que el acceso al registro de auditoría requiera la autorización adecuada y que todos los intentos de acceso se registren con la identidad del usuario y una marca de tiempo.
 #3.4.3    Level: 2    Role: D/V
 Verifique que las plantillas de indicaciones y los mensajes del sistema estén controlados por versiones en repositorios git, con revisión de código obligatoria y aprobación por parte de revisores designados antes del despliegue.
 #3.4.4    Level: 2    Role: V
 Verifique que los registros de auditoría incluyan suficiente detalle (hashes de modelos, instantáneas de configuración, versiones de dependencias) para permitir la reconstrucción completa del estado del modelo en cualquier momento dentro del período de retención.

---

### C3.5 Prácticas de Desarrollo Seguro

Los procesos de desarrollo y entrenamiento de modelos deben seguir prácticas seguras para prevenir compromisos.

 #3.5.1    Level: 1    Role: D
 Verifique que los entornos de desarrollo de modelos, pruebas y producción estén separados física o lógicamente. No deben compartir infraestructura, deben tener controles de acceso distintos y almacenar los datos de forma aislada.
 #3.5.2    Level: 1    Role: D
 Verifique que el entrenamiento y ajuste fino del modelo se realicen en entornos aislados con acceso controlado a la red.
 #3.5.3    Level: 1    Role: D/V
 Verifique que las fuentes de datos de entrenamiento sean validadas mediante comprobaciones de integridad y autenticadas a través de fuentes confiables con una cadena de custodia documentada antes de su uso en el desarrollo del modelo.
 #3.5.4    Level: 2    Role: D
 Verifique que los artefactos de desarrollo del modelo (hiperparámetros, scripts de entrenamiento, archivos de configuración) estén almacenados en control de versiones y requieran la aprobación de revisión por pares antes de usarse en el entrenamiento.

---

### C3.6 Retiro y Desmantelamiento del Modelo

Los modelos deben ser retirados de manera segura cuando ya no se necesiten o cuando se identifiquen problemas de seguridad.

 #3.6.1    Level: 1    Role: D
 Verifique que los procesos de retiro de modelos escanean automáticamente los gráficos de dependencias, identifican todos los sistemas consumidores y proporcionan períodos de notificación anticipada previamente acordados antes de la desactivación.
 #3.6.2    Level: 1    Role: D/V
 Verifique que los artefactos de modelos retirados se eliminen de forma segura mediante borrado criptográfico o sobreescritura múltiple de acuerdo con las políticas documentadas de retención de datos y con certificados de destrucción verificados.
 #3.6.3    Level: 2    Role: V
 Verifique que los eventos de retiro del modelo se registren con marca de tiempo e identidad del actor, y que las firmas del modelo se revoquen para evitar su reutilización.
 #3.6.4    Level: 2    Role: D/V
 Verifique que la retirada de modelo de emergencia pueda deshabilitar el acceso al modelo dentro de los plazos preestablecidos de respuesta de emergencia mediante interruptores de desconexión automáticos si se descubren vulnerabilidades críticas de seguridad.

---

### Referencias

MLOps Principles
Securing AI/ML Ops – Cisco.com
Audit logs security: cryptographically signed tamper-proof logs
Machine Learning Model Versioning: Top Tools & Best Practices
AI Hygiene Starts with Models and Data Loaders – SEI Blog
How to handle versioning and rollback of a deployed ML model?
Reinforcement fine-tuning – OpenAI API
Auditing Machine Learning models: Governance, Data Security and …
Adversarial Training to Improve Model Robustness
What is AI adversarial robustness? – IBM Research
Exploring Data Provenance: Ensuring Data Integrity and Authenticity
MITRE ATLAS
AWS Prescriptive Guidance – Best practices for retiring applications …

## Seguridad de Infraestructura, Configuración y Despliegue de C4

### Objetivo de Control

La infraestructura de IA debe ser reforzada contra la escalada de privilegios, la manipulación de la cadena de suministro y el movimiento lateral mediante una configuración segura, aislamiento en tiempo de ejecución, canalizaciones de despliegue confiables y monitoreo integral. Solo los componentes y configuraciones de infraestructura autorizados y validados llegan a producción a través de procesos controlados que mantienen la seguridad, integridad y auditabilidad.

Objetivo principal de seguridad: Solo los componentes de infraestructura firmados criptográficamente y escaneados en busca de vulnerabilidades llegan a producción a través de canalizaciones de validación automatizadas que aplican políticas de seguridad y mantienen registros de auditoría inmutables.

---

### C4.1 Aislamiento del Entorno de Ejecución

Prevenir fugas de contenedores y escalada de privilegios mediante primitivas de aislamiento a nivel de kernel y controles de acceso obligatorios.

 #4.1.1    Level: 1    Role: D/V
 Verifique que todos los contenedores de IA eliminen TODAS las capacidades de Linux excepto CAP_SETUID, CAP_SETGID y las capacidades explícitamente requeridas documentadas en las líneas base de seguridad.
 #4.1.2    Level: 1    Role: D/V
 Verifique que los perfiles seccomp bloqueen todas las llamadas al sistema excepto aquellas en listas de permitidos preaprobadas, y que las violaciones terminen el contenedor y generen alertas de seguridad.
 #4.1.3    Level: 2    Role: D/V
 Verifique que las cargas de trabajo de IA se ejecuten con sistemas de archivos raíz de solo lectura, tmpfs para datos temporales y volúmenes nombrados para datos persistentes con opciones de montaje noexec aplicadas.
 #4.1.4    Level: 2    Role: D/V
 Verifique que la monitorización en tiempo real basada en eBPF (Falco, Tetragon o equivalente) detecte intentos de escalamiento de privilegios y finalice automáticamente los procesos infractores dentro de los requisitos de tiempo de respuesta organizacional.
 #4.1.5    Level: 3    Role: D/V
 Verifique que las cargas de trabajo de IA de alto riesgo se ejecuten en entornos aislados por hardware (Intel TXT, AMD SVM o nodos bare-metal dedicados) con verificación de atestación.

---

### C4.2 Canalizaciones Seguras de Construcción y Despliegue

Asegure la integridad criptográfica y la seguridad de la cadena de suministro mediante compilaciones reproducibles y artefactos firmados.

 #4.2.1    Level: 1    Role: D/V
 Verifique que la infraestructura como código sea escaneada con herramientas (tfsec, Checkov o Terrascan) en cada commit, bloqueando las fusiones con hallazgos de severidad CRÍTICA o ALTA.
 #4.2.2    Level: 1    Role: D/V
 Verifique que las compilaciones de contenedores sean reproducibles con hashes SHA256 idénticos en todas las compilaciones y genere atestaciones de procedencia SLSA Nivel 3 firmadas con Sigstore.
 #4.2.3    Level: 2    Role: D/V
 Verifique que las imágenes de contenedor incorporen SBOMs CycloneDX o SPDX y estén firmadas con Cosign antes de ser enviadas al registro, rechazando las imágenes no firmadas en el despliegue.
 #4.2.4    Level: 2    Role: D/V
 Verifique que las canalizaciones CI/CD utilicen tokens OIDC de HashiCorp Vault, roles IAM de AWS o identidad administrada de Azure con duraciones que no excedan los límites establecidos por la política de seguridad organizacional.
 #4.2.5    Level: 2    Role: D/V
 Verifique que las firmas de Cosign y la procedencia SLSA se validen durante el proceso de implementación antes de la ejecución del contenedor y que los errores de verificación provoquen que la implementación falle.
 #4.2.6    Level: 2    Role: D/V
 Verifique que los entornos de compilación se ejecuten en contenedores efímeros o máquinas virtuales sin almacenamiento persistente y con aislamiento de red de las VPC de producción.

---

### C4.3 Seguridad de la Red y Control de Acceso

Implemente una red de confianza cero con políticas de denegación por defecto y comunicaciones encriptadas.

 #4.3.1    Level: 1    Role: D/V
 Verifique que las NetworkPolicies de Kubernetes o cualquier equivalente implementen un rechazo predeterminado para el tráfico de entrada/salida con reglas explícitas de permiso para los puertos requeridos (443, 8080, etc.).
 #4.3.2    Level: 1    Role: D/V
 Verifique que SSH (puerto 22), RDP (puerto 3389) y los puntos finales de metadatos en la nube (169.254.169.254) estén bloqueados o requieran autenticación basada en certificados.
 #4.3.3    Level: 2    Role: D/V
 Verifique que el tráfico de salida sea filtrado a través de proxies HTTP/HTTPS (Squid, Istio o gateways NAT en la nube) con listas de dominios permitidos y que las solicitudes bloqueadas sean registradas.
 #4.3.4    Level: 2    Role: D/V
 Verifique que la comunicación entre servicios utilice TLS mutuo con certificados rotados según la política organizacional y que se aplique la validación de certificados (sin usar flags de omisión de verificación).
 #4.3.5    Level: 2    Role: D/V
 Verifique que la infraestructura de IA funcione en VPCs/VNets dedicadas sin acceso directo a internet y que se comunique únicamente a través de gateways NAT o hosts bastión.

---

### C4.4 Gestión de Secretos y Claves Criptográficas

Proteja las credenciales mediante almacenamiento respaldado por hardware y rotación automatizada con acceso de confianza cero.

 #4.4.1    Level: 1    Role: D/V
 Verifique que los secretos estén almacenados en HashiCorp Vault, AWS Secrets Manager, Azure Key Vault o Google Secret Manager con cifrado en reposo utilizando AES-256.
 #4.4.2    Level: 1    Role: D/V
 Verifique que las claves criptográficas se generen en HSM de nivel 2 FIPS 140-2 (AWS CloudHSM, Azure Dedicated HSM) con rotación de claves de acuerdo con la política criptográfica organizacional.
 #4.4.3    Level: 2    Role: D/V
 Verifique que la rotación de secretos esté automatizada con despliegue sin tiempo de inactividad y que la rotación inmediata sea activada por cambios de personal o incidentes de seguridad.
 #4.4.4    Level: 2    Role: D/V
 Verifique que las imágenes de contenedores sean escaneadas con herramientas (GitLeaks, TruffleHog o detect-secrets) bloqueando las compilaciones que contengan claves API, contraseñas o certificados.
 #4.4.5    Level: 2    Role: D/V
 Verifique que el acceso a secretos de producción requiera MFA con tokens de hardware (YubiKey, FIDO2) y que esté registrado mediante registros de auditoría inmutables con identidades de usuario y marcas de tiempo.
 #4.4.6    Level: 2    Role: D/V
 Verifique que los secretos se inyecten a través de secretos de Kubernetes, volúmenes montados o contenedores init y asegúrese de que los secretos nunca estén incrustados en variables de entorno o imágenes.

---

### C4.5 Aislamiento y Validación de Cargas de Trabajo de IA

Aísle los modelos de IA no confiables en entornos seguros con un análisis conductual integral.

 #4.5.1    Level: 1    Role: D/V
 Verifique que los modelos externos de IA se ejecuten en gVisor, microVMs (como Firecracker, CrossVM) o contenedores Docker con las opciones --security-opt=no-new-privileges y --read-only.
 #4.5.2    Level: 1    Role: D/V
 Verifique que los entornos de sandbox no tengan conectividad de red (--network=none) o que solo tengan acceso a localhost, bloqueando todas las solicitudes externas mediante reglas de iptables.
 #4.5.3    Level: 2    Role: D/V
 Verifique que la validación del modelo de IA incluya pruebas automatizadas de red-team con cobertura de pruebas definida por la organización y análisis de comportamiento para la detección de puertas traseras.
 #4.5.4    Level: 2    Role: D/V
 Verifique que antes de que un modelo de IA sea promovido a producción, sus resultados en el entorno de pruebas estén firmados criptográficamente por personal de seguridad autorizado y almacenados en registros de auditoría inmutables.
 #4.5.5    Level: 2    Role: D/V
 Verifique que los entornos sandbox sean destruidos y recreados a partir de imágenes maestras entre evaluaciones, con una limpieza completa del sistema de archivos y la memoria.

---

### C4.6 Monitoreo de Seguridad de Infraestructura

Escanee y monitoree continuamente la infraestructura con remediación automatizada y alertas en tiempo real.

 #4.6.1    Level: 1    Role: D/V
 Verifique que las imágenes de contenedores sean escaneadas según los cronogramas organizacionales, bloqueando el despliegue si se detectan vulnerabilidades CRÍTICAS según los umbrales de riesgo de la organización.
 #4.6.2    Level: 1    Role: D/V
 Verifique que la infraestructura cumpla con los parámetros de referencia CIS o los controles NIST 800-53 según los umbrales de cumplimiento definidos organizacionalmente y la remediación automatizada para las verificaciones fallidas.
 #4.6.3    Level: 2    Role: D/V
 Verifique que las vulnerabilidades de severidad ALTA estén parcheadas según los plazos de gestión de riesgos organizacionales, con procedimientos de emergencia para las CVEs explotadas activamente.
 #4.6.4    Level: 2    Role: V
 Verifique que las alertas de seguridad se integren con plataformas SIEM (Splunk, Elastic o Sentinel) utilizando los formatos CEF o STIX/TAXII con enriquecimiento automatizado.
 #4.6.5    Level: 3    Role: V
 Verifique que las métricas de infraestructura se exporten a los sistemas de monitoreo (Prometheus, DataDog) con paneles SLA e informes ejecutivos.
 #4.6.6    Level: 2    Role: D/V
 Verifique que la deriva de configuración sea detectada utilizando herramientas (Chef InSpec, AWS Config) de acuerdo con los requisitos de monitoreo organizacional, con reversión automática para cambios no autorizados.

---

### C4.7 Gestión de Recursos de Infraestructura de IA

Prevenir ataques de agotamiento de recursos y garantizar una asignación justa de recursos mediante cuotas y monitoreo.

 #4.7.1    Level: 1    Role: D/V
 Verifique que la utilización de GPU/TPU sea monitoreada con alertas activadas en los umbrales definidos por la organización y que se active el escalado automático o el balanceo de carga basado en las políticas de gestión de capacidad.
 #4.7.2    Level: 1    Role: D/V
 Verifique que las métricas de carga de trabajo de IA (latencia de inferencia, rendimiento, tasas de error) se recopilen según los requisitos de monitoreo organizacional y se correlacionen con la utilización de la infraestructura.
 #4.7.3    Level: 2    Role: D/V
 Verifique que Kubernetes ResourceQuotas o su equivalente limiten cargas de trabajo individuales según las políticas organizacionales de asignación de recursos, con límites estrictos aplicados.
 #4.7.4    Level: 2    Role: V
 Verificar que el monitoreo de costos rastree el gasto por carga de trabajo/inquilino con alertas basadas en los umbrales del presupuesto organizacional y controles automáticos para sobregiros presupuestarios.
 #4.7.5    Level: 3    Role: V
 Verifique que la planificación de capacidad utilice datos históricos con períodos de pronóstico definidos organizacionalmente y aprovisionamiento automatizado de recursos basado en patrones de demanda.
 #4.7.6    Level: 2    Role: D/V
 Verifique que la agotamiento de recursos active los disyuntores conforme a los requisitos de respuesta organizacionales, incluyendo la limitación de tasa basada en políticas de capacidad y el aislamiento de la carga de trabajo.

---

### C4.8 Controles de Separación y Promoción de Entornos

Hacer cumplir límites estrictos en el entorno con puertas automáticas de promoción y validación de seguridad.

 #4.8.1    Level: 1    Role: D/V
 Verifique que los entornos de desarrollo/prueba/producción funcionen en VPCs/VNets separadas sin roles IAM, grupos de seguridad o conectividad de red compartidos.
 #4.8.2    Level: 1    Role: D/V
 Verifique que la promoción del entorno requiera la aprobación del personal autorizado definido organizacionalmente, con firmas criptográficas y registros de auditoría inmutables.
 #4.8.3    Level: 2    Role: D/V
 Verifique que los entornos de producción bloqueen el acceso SSH, deshabiliten los puntos finales de depuración y requieran solicitudes de cambio con requisitos de aviso previo organizacional, excepto en emergencias.
 #4.8.4    Level: 2    Role: D/V
 Verifique que los cambios en infraestructura como código requieran revisión por pares con pruebas automatizadas y análisis de seguridad antes de fusionarse a la rama principal.
 #4.8.5    Level: 2    Role: D/V
 Verifique que los datos no productivos estén anonimizados según los requisitos de privacidad de la organización, la generación de datos sintéticos o el enmascaramiento completo de datos con eliminación de información de identificación personal (PII) verificada.
 #4.8.6    Level: 2    Role: D/V
 Verificar que las puertas de promoción incluyan pruebas automatizadas de seguridad (SAST, DAST, escaneo de contenedores) con cero hallazgos CRÍTICOS requeridos para la aprobación.

---

### C4.9 Respaldo y Recuperación de Infraestructura

Asegure la resiliencia de la infraestructura mediante copias de seguridad automáticas, procedimientos de recuperación probados y capacidades de recuperación ante desastres.

 #4.9.1    Level: 1    Role: D/V
 Verifique que las configuraciones de infraestructura estén respaldadas según los horarios de respaldo organizacionales hacia regiones geográficamente separadas, implementando la estrategia de respaldo 3-2-1.
 #4.9.2    Level: 2    Role: D/V
 Verifique que los sistemas de respaldo funcionen en redes aisladas con credenciales separadas y almacenamiento desconectado para la protección contra ransomware.
 #4.9.3    Level: 2    Role: V
 Verificar que los procedimientos de recuperación sean probados y validados mediante pruebas automatizadas según los cronogramas organizacionales, cumpliendo con los objetivos de RTO y RPO que satisfacen los requisitos de la organización.
 #4.9.4    Level: 3    Role: V
 Verifique que la recuperación ante desastres incluya libros de instrucciones específicos para IA con restauración de pesos del modelo, reconstrucción del clúster GPU y mapeo de dependencias del servicio.

---

### C4.10 Cumplimiento de Infraestructura y Gobernanza

Mantenga el cumplimiento normativo mediante la evaluación continua, la documentación y los controles automatizados.

 #4.10.1    Level: 2    Role: D/V
 Verifique que la conformidad de la infraestructura se evalúe según los calendarios organizacionales con respecto a los controles SOC 2, ISO 27001 o FedRAMP, utilizando la recopilación automatizada de evidencias.
 #4.10.2    Level: 2    Role: V
 Verifique que la documentación de la infraestructura incluya diagramas de red, mapas de flujo de datos y modelos de amenazas actualizados según los requisitos de la gestión de cambios organizacionales.
 #4.10.3    Level: 3    Role: D/V
 Verifique que los cambios en la infraestructura pasen por una evaluación automatizada del impacto en el cumplimiento normativo con flujos de trabajo de aprobación regulatoria para modificaciones de alto riesgo.

---

### C4.11 Seguridad del Hardware de IA

Componentes de hardware específicos para IA seguros, incluidos GPUs, TPUs y aceleradores de IA especializados.

 #4.11.1    Level: 2    Role: D/V
 Verifique que el firmware del acelerador de IA (BIOS de GPU, firmware de TPU) esté verificado con firmas criptográficas y se actualice de acuerdo con los cronogramas de gestión de parches de la organización.
 #4.11.2    Level: 2    Role: D/V
 Verifique que, antes de la ejecución de la carga de trabajo, se valide la integridad del acelerador de IA mediante la atestación de hardware usando TPM 2.0, Intel TXT o AMD SVM.
 #4.11.3    Level: 2    Role: D/V
 Verifique que la memoria GPU esté aislada entre cargas de trabajo utilizando SR-IOV, MIG (GPU de instancia múltiple) o particionamiento de hardware equivalente con saneamiento de memoria entre trabajos.
 #4.11.4    Level: 3    Role: V
 Verifique que la cadena de suministro de hardware de IA incluya la verificación de procedencia con certificados del fabricante y la validación de embalaje a prueba de manipulaciones.
 #4.11.5    Level: 3    Role: D/V
 Verifique que los módulos de seguridad de hardware (HSM) protejan los pesos del modelo de IA y las claves criptográficas con certificación FIPS 140-2 Nivel 3 o Common Criteria EAL4+.

---

### C4.12 Infraestructura de IA en el Borde y Distribuida

Despliegues seguros de IA distribuidos que incluyen computación en el borde, aprendizaje federado y arquitecturas multisede.

 #4.12.1    Level: 2    Role: D/V
 Verifique que los dispositivos de IA perimetral se autentiquen con la infraestructura central utilizando TLS mutuo con certificados de dispositivo rotados conforme a la política organizacional de gestión de certificados.
 #4.12.2    Level: 2    Role: D/V
 Verifique que los dispositivos edge implementen arranque seguro con firmas verificadas y protección contra retrocesos para prevenir ataques de degradación de firmware.
 #4.12.3    Level: 3    Role: D/V
 Verifique que la coordinación de IA distribuida utilice algoritmos de consenso tolerantes a fallos bizantinos con validación de participantes y detección de nodos maliciosos.
 #4.12.4    Level: 3    Role: D/V
 Verifique que la comunicación de borde a nube incluya limitación del ancho de banda, compresión de datos y capacidades de operación sin conexión con almacenamiento local seguro.

---

### C4.13 Seguridad de Infraestructura Multi-Nube e Híbrida

Asegure las cargas de trabajo de IA en múltiples proveedores de nube y despliegues híbridos de nube y local.

 #4.13.1    Level: 2    Role: D/V
 Verifique que las implementaciones de IA multi-nube utilicen federación de identidad independiente de la nube (OIDC, SAML) con gestión centralizada de políticas entre proveedores.
 #4.13.2    Level: 2    Role: D/V
 Verifique que la transferencia de datos entre nubes utilice cifrado de extremo a extremo con claves gestionadas por el cliente y que se apliquen controles de residencia de datos según la jurisdicción.
 #4.13.3    Level: 2    Role: D/V
 Verifique que las cargas de trabajo de IA en la nube híbrida implementen políticas de seguridad consistentes tanto en entornos locales como en la nube, con monitoreo y alertas unificados.
 #4.13.4    Level: 3    Role: V
 Verifique que la prevención del bloqueo del proveedor en la nube incluya infraestructura como código portátil, API estandarizadas y capacidades de exportación de datos con herramientas de conversión de formatos.
 #4.13.5    Level: 3    Role: V
 Verifique que la optimización de costos multinube incluya controles de seguridad que prevengan la proliferación de recursos, así como cargos no autorizados por transferencia de datos entre nubes.

---

### C4.14 Automatización de Infraestructura y Seguridad GitOps

Automatización segura de infraestructuras y flujos de trabajo GitOps para la gestión de infraestructuras de IA.

 #4.14.1    Level: 2    Role: D/V
 Verifique que los repositorios GitOps requieran commits firmados con claves GPG y reglas de protección de ramas que impidan las subidas directas a las ramas principales.
 #4.14.2    Level: 2    Role: D/V
 Verifique que la automatización de la infraestructura incluya detección de desviaciones con capacidades automáticas de remediación y reversión activadas según los requisitos de respuesta organizacional para cambios no autorizados.
 #4.14.3    Level: 2    Role: D/V
 Verifique que la provisión automatizada de infraestructura incluya la validación de políticas de seguridad con bloqueo de despliegues para configuraciones no conformes.
 #4.14.4    Level: 2    Role: D/V
 Verifique que los secretos de automatización de infraestructura se gestionen a través de operadores de secretos externos (External Secrets Operator, Bank-Vaults) con rotación automática.
 #4.14.5    Level: 3    Role: V
 Verifique que la infraestructura autocurable incluya la correlación de eventos de seguridad con la respuesta automática a incidentes y los flujos de trabajo de notificación a las partes interesadas.

---

### C4.15 Seguridad de Infraestructura Resistente a Cuántica

Prepare la infraestructura de IA para las amenazas de la computación cuántica mediante criptografía post-cuántica y protocolos seguros frente a la computación cuántica.

 #4.15.1    Level: 3    Role: D/V
 Verifique que la infraestructura de IA implemente algoritmos criptográficos posteriores a la era cuántica aprobados por NIST (CRYSTALS-Kyber, CRYSTALS-Dilithium, SPHINCS+) para el intercambio de claves y firmas digitales.
 #4.15.2    Level: 3    Role: D/V
 Verifique que los sistemas de distribución cuántica de claves (QKD) estén implementados para comunicaciones de IA de alta seguridad con protocolos de gestión de claves resistentes a la computación cuántica.
 #4.15.3    Level: 3    Role: D/V
 Verifique que los marcos de agilidad criptográfica permitan la migración rápida a nuevos algoritmos post-cuánticos con la rotación automatizada de certificados y claves.
 #4.15.4    Level: 3    Role: V
 Verifique que el modelado de amenazas cuánticas evalúe la vulnerabilidad de la infraestructura de IA a los ataques cuánticos con cronogramas documentados de migración y evaluaciones de riesgos.
 #4.15.5    Level: 3    Role: D/V
 Verifique que los sistemas criptográficos híbridos clásico-cuánticos proporcionen defensa en profundidad durante el periodo de transición cuántica con monitoreo de rendimiento.

---

### C4.16 Computación Confidencial y Enclaves Seguros

Proteja las cargas de trabajo de IA y los pesos del modelo utilizando entornos de ejecución confiables basados en hardware y tecnologías de computación confidencial.

 #4.16.1    Level: 3    Role: D/V
 Verificar que los modelos de IA sensibles se ejecuten dentro de recintos Intel SGX, AMD SEV-SNP o ARM TrustZone con memoria encriptada y verificación de atestación.
 #4.16.2    Level: 3    Role: D/V
 Verifique que los contenedores confidenciales (Kata Containers, gVisor con computación confidencial) aislan las cargas de trabajo de IA con cifrado de memoria reforzado por hardware.
 #4.16.3    Level: 3    Role: D/V
 Verifique que la atestación remota valide la integridad del enclave antes de cargar los modelos de IA con una prueba criptográfica de la autenticidad del entorno de ejecución.
 #4.16.4    Level: 3    Role: D/V
 Verifique que los servicios confidenciales de inferencia de IA eviten la extracción del modelo mediante computación cifrada con pesos del modelo sellados y ejecución protegida.
 #4.16.5    Level: 3    Role: D/V
 Verifique que la orquestación del entorno de ejecución confiable gestione el ciclo de vida del enclave seguro con atestación remota y canales de comunicación cifrados.
 #4.16.6    Level: 3    Role: D/V
 Verifique que el cómputo multipartita seguro (SMPC) permite el entrenamiento colaborativo de IA sin exponer conjuntos de datos individuales ni parámetros del modelo.

---

### C4.17 Infraestructura de Conocimiento Cero

Implementar sistemas de prueba de conocimiento cero para la verificación y autenticación de IA que preserven la privacidad sin revelar información sensible.

 #4.17.1    Level: 3    Role: D/V
 Verifique que las pruebas de conocimiento cero (ZK-SNARKs, ZK-STARKs) validan la integridad del modelo de IA y el origen del entrenamiento sin revelar los pesos del modelo ni los datos de entrenamiento.
 #4.17.2    Level: 3    Role: D/V
 Verifique que los sistemas de autenticación basados en ZK permitan la verificación del usuario que preserva la privacidad para servicios de IA sin revelar información relacionada con la identidad.
 #4.17.3    Level: 3    Role: D/V
 Verifique que los protocolos de intersección privada de conjuntos (PSI) permiten la coincidencia segura de datos para la IA federada sin exponer los conjuntos de datos individuales.
 #4.17.4    Level: 3    Role: D/V
 Verifique que los sistemas de aprendizaje automático de conocimiento cero (ZKML) permiten inferencias de IA verificables con prueba criptográfica de cálculo correcto.
 #4.17.5    Level: 3    Role: D/V
 Verifique que los ZK-rollups ofrecen procesamiento de transacciones de IA escalable y preservador de la privacidad con verificación por lotes y reducción de la sobrecarga computacional.

---

### C4.18 Prevención de Ataques por Canal Lateral

Proteja la infraestructura de IA contra ataques de canal lateral basados en temporización, energía, electromagnetismo y caché que podrían filtrar información sensible.

 #4.18.1    Level: 3    Role: D/V
 Verifique que el tiempo de inferencia de IA esté normalizado utilizando algoritmos de tiempo constante y relleno para prevenir ataques de extracción de modelos basados en el tiempo.
 #4.18.2    Level: 3    Role: D/V
 Verifique que la protección contra análisis de potencia incluya la inyección de ruido, el filtrado de la línea de alimentación y patrones de ejecución aleatorizados para el hardware de IA.
 #4.18.3    Level: 3    Role: D/V
 Verifique que la mitigación de canales laterales basada en caché utiliza particionamiento de caché, aleatorización e instrucciones de vaciado para prevenir la filtración de información.
 #4.18.4    Level: 3    Role: D/V
 Verifique que la protección contra emanaciones electromagnéticas incluya blindaje, filtrado de señales y procesamiento aleatorizado para prevenir ataques al estilo TEMPEST.
 #4.18.5    Level: 3    Role: D/V
 Verifique que las defensas contra canales laterales microarquitectónicos incluyan controles de ejecución especulativa y ofuscación de patrones de acceso a la memoria.

---

### C4.19 Seguridad en Hardware Neuromórfico y de IA Especializada

Asegurar arquitecturas de hardware emergentes de IA, incluyendo chips neuromórficos, FPGAs, ASICs personalizados y sistemas de computación óptica.

 #4.19.1    Level: 3    Role: D/V
 Verifique que la seguridad del chip neuromórfico incluya encriptación de patrones de disparo, protección del peso sináptico y validación de reglas de aprendizaje basadas en hardware.
 #4.19.2    Level: 3    Role: D/V
 Verifique que los aceleradores de IA basados en FPGA implementen cifrado de bitstream, mecanismos anti-manipulación y carga segura de configuración con actualizaciones autenticadas.
 #4.19.3    Level: 3    Role: D/V
 Verifique que la seguridad del ASIC personalizado incluya procesadores de seguridad en chip, raíz de confianza hardware y almacenamiento seguro de claves con detección de manipulación.
 #4.19.4    Level: 3    Role: D/V
 Verifique que los sistemas de computación óptica implementen cifrado óptico cuántico seguro, conmutación fotónica segura y procesamiento de señales ópticas protegido.
 #4.19.5    Level: 3    Role: D/V
 Verifique que los chips de IA híbridos analógico-digital incluyan cálculo analógico seguro, almacenamiento protegido de pesos y conversión analógica a digital autenticada.

---

### C4.20 Infraestructura de Computación Preservadora de la Privacidad

Implemente controles de infraestructura para el cálculo que preserva la privacidad con el fin de proteger datos sensibles durante el procesamiento y análisis de IA.

 #4.20.1    Level: 3    Role: D/V
 Verifique que la infraestructura de cifrado homomórfico permita la computación cifrada en cargas de trabajo de IA sensibles con verificación criptográfica de integridad y monitoreo de rendimiento.
 #4.20.2    Level: 3    Role: D/V
 Verifique que los sistemas de recuperación privada de información permiten consultas a bases de datos sin revelar patrones de consulta mediante la protección criptográfica de los patrones de acceso.
 #4.20.3    Level: 3    Role: D/V
 Verifique que los protocolos de computación multipartita segura permitan la inferencia de IA preservando la privacidad sin exponer entradas individuales o cálculos intermedios.
 #4.20.4    Level: 3    Role: D/V
 Verifique que la gestión de claves que preserva la privacidad incluya generación distribuida de claves, criptografía umbral y rotación segura de claves con protección respaldada por hardware.
 #4.20.5    Level: 3    Role: D/V
 Verifique que el rendimiento de la computación que preserva la privacidad esté optimizado mediante agrupación por lotes, almacenamiento en caché y aceleración por hardware, manteniendo al mismo tiempo las garantías de seguridad criptográfica.

---

### C4.15 Seguridad de Integración en la Nube y Despliegue Híbrido del Marco de Agentes

Controles de seguridad para marcos de agentes integrados en la nube con arquitecturas híbridas locales/nube.

 #4.15.1    Level: 1    Role: D/V
 Verifique que la integración del almacenamiento en la nube utilice cifrado de extremo a extremo con gestión de claves controlada por el agente.
 #4.15.2    Level: 2    Role: D/V
 Verifique que los límites de seguridad en el despliegue híbrido estén claramente definidos con canales de comunicación cifrados.
 #4.15.3    Level: 2    Role: D/V
 Verifique que el acceso a los recursos en la nube incluya una verificación de confianza cero con autenticación continua.
 #4.15.4    Level: 3    Role: D/V
 Verifique que los requisitos de residencia de datos se apliquen mediante la atestación criptográfica de las ubicaciones de almacenamiento.
 #4.15.5    Level: 3    Role: D/V
 Verifique que las evaluaciones de seguridad del proveedor de la nube incluyan modelado de amenazas específico para agentes y evaluación de riesgos.

---

### Referencias

NIST Cybersecurity Framework 2.0
CIS Controls v8
OWASP Container Security Verification Standard
Kubernetes Security Best Practices
SLSA Supply Chain Security Framework
NIST SP 800-190: Application Container Security Guide
Cloud Security Alliance: Cloud Controls Matrix
ENISA: Secure Infrastructure Design
NIST SP 800-53: Security Controls for Federal Information Systems
ISO 27001:2022 Information Security Management
NIST AI Risk Management Framework
CIS Kubernetes Benchmark
FIPS 140-2 Security Requirements
NIST SP 800-207: Zero Trust Architecture
IEEE 2857: Privacy Engineering for AI Systems
NIST SP 800-161: Cybersecurity Supply Chain Risk Management
NIST Post-Quantum Cryptography Standards
Intel SGX Developer Guide
AMD SEV-SNP White Paper
ARM TrustZone Technology
ZK-SNARKs: A Gentle Introduction
NIST SP 800-57: Cryptographic Key Management
Side-Channel Attack Countermeasures
Neuromorphic Computing Security Challenges
FPGA Security: Fundamentals, Evaluation, and Countermeasures
Microsoft SEAL: Homomorphic Encryption Library
HElib: Homomorphic Encryption Library
PALISADE Lattice Cryptography Library
Differential Privacy: A Survey of Results
Secure Aggregation for Federated Learning
Private Information Retrieval: Concepts and Constructions

## Control de Acceso C5 e Identidad para Componentes y Usuarios de IA

### Objetivo de Control

El control de acceso efectivo para sistemas de IA requiere una gestión robusta de identidades, autorización consciente del contexto y aplicación en tiempo de ejecución siguiendo principios de confianza cero. Estos controles garantizan que los humanos, servicios y agentes autónomos solo interactúen con modelos, datos y recursos computacionales dentro de los ámbitos explícitamente otorgados, con capacidades continuas de verificación y auditoría.

---

### C5.1 Gestión de Identidad y Autenticación

Establecer identidades respaldadas criptográficamente para todas las entidades con autenticación multifactor para operaciones privilegiadas.

 #5.1.1    Level: 1    Role: D/V
 Verifique que todos los usuarios humanos y principales de servicio se autentiquen a través de un proveedor de identidad empresarial centralizado (IdP) utilizando los protocolos OIDC/SAML con asignaciones únicas de identidad a token (sin cuentas ni credenciales compartidas).
 #5.1.2    Level: 1    Role: D/V
 Verifique que las operaciones de alto riesgo (despliegue de modelos, exportación de pesos, acceso a datos de entrenamiento, cambios en la configuración de producción) requieran autenticación multifactor o autenticación escalonada con revalidación de sesión.
 #5.1.3    Level: 2    Role: D
 Verifique que los nuevos responsables pasen por un proceso de verificación de identidad alineado con NIST 800-63-3 IAL-2 o estándares equivalentes antes de recibir acceso al sistema de producción.
 #5.1.4    Level: 2    Role: V
 Verifique que las revisiones de acceso se realicen trimestralmente con detección automatizada de cuentas inactivas, aplicación de rotación de credenciales y flujos de trabajo de desprovisión.
 #5.1.5    Level: 3    Role: D/V
 Verifique que los agentes de IA federada se autentiquen mediante aserciones JWT firmadas que tengan una vida útil máxima de 24 horas e incluyan prueba criptográfica de origen.

---

### C5.2 Autorización de Recursos y Mínimos Privilegios

Implemente controles de acceso detallados para todos los recursos de IA con modelos de permiso explícitos y registros de auditoría.

 #5.2.1    Level: 1    Role: D/V
 Verifique que cada recurso de IA (conjuntos de datos, modelos, puntos finales, colecciones vectoriales, índices de incrustación, instancias de cómputo) aplique controles de acceso basados en roles con listas de permisos explícitas y políticas de denegación predeterminadas.
 #5.2.2    Level: 1    Role: D/V
 Verifique que los principios de menor privilegio se apliquen por defecto en las cuentas de servicio, comenzando con permisos de solo lectura y se requiera una justificación comercial documentada para el acceso de escritura.
 #5.2.3    Level: 1    Role: V
 Verifique que todas las modificaciones de control de acceso estén vinculadas a solicitudes de cambio aprobadas y registradas de forma inmutable con marcas de tiempo, identidades de los actores, identificadores de recursos y deltas de permisos.
 #5.2.4    Level: 2    Role: D
 Verifique que las etiquetas de clasificación de datos (PII, PHI, controladas por exportación, propietarias) se propaguen automáticamente a los recursos derivados (incrustaciones, cachés de indicaciones, salidas del modelo) con una aplicación de políticas coherente.
 #5.2.5    Level: 2    Role: D/V
 Verifique que los intentos de acceso no autorizados y los eventos de escalada de privilegios generen alertas en tiempo real con metadatos contextuales a los sistemas SIEM en un plazo de 5 minutos.

---

### C5.3 Evaluación Dinámica de Políticas

Implemente motores de control de acceso basado en atributos (ABAC) para decisiones de autorización conscientes del contexto con capacidades de auditoría.

 #5.3.1    Level: 1    Role: D/V
 Verifique que las decisiones de autorización estén externalizadas a un motor de políticas dedicado (OPA, Cedar o equivalente) accesible a través de APIs autenticadas con protección de integridad criptográfica.
 #5.3.2    Level: 1    Role: D/V
 Verifique que las políticas evalúen atributos dinámicos en tiempo de ejecución, incluyendo el nivel de autorización del usuario, la clasificación de sensibilidad del recurso, el contexto de la solicitud, el aislamiento del inquilino y las restricciones temporales.
 #5.3.3    Level: 2    Role: D
 Verifique que las definiciones de políticas estén controladas por versiones, revisadas por pares y validadas mediante pruebas automatizadas en los pipelines de CI/CD antes del despliegue en producción.
 #5.3.4    Level: 2    Role: V
 Verifique que los resultados de la evaluación de políticas incluyan fundamentos estructurados de las decisiones y se transmitan a los sistemas SIEM para análisis de correlación e informes de cumplimiento.
 #5.3.5    Level: 3    Role: D/V
 Verifique que los valores de tiempo de vida (TTL) de la caché de políticas no excedan los 5 minutos para recursos de alta sensibilidad y 1 hora para recursos estándar con capacidades de invalidación de caché.

---

### C5.4 Aplicación de Seguridad en Tiempo de Consulta

Implemente controles de seguridad a nivel de base de datos con filtrado obligatorio y políticas de seguridad a nivel de fila.

 #5.4.1    Level: 1    Role: D/V
 Verifique que todas las consultas a bases de datos vectoriales y SQL incluyan filtros de seguridad obligatorios (ID de inquilino, etiquetas de sensibilidad, ámbito del usuario) aplicados a nivel del motor de la base de datos, no en el código de la aplicación.
 #5.4.2    Level: 1    Role: D/V
 Verifique que las políticas de seguridad a nivel de fila (RLS) y el enmascaramiento a nivel de campo estén habilitados con herencia de políticas para todas las bases de datos vectoriales, índices de búsqueda y conjuntos de datos de entrenamiento.
 #5.4.3    Level: 2    Role: D
 Verifique que las evaluaciones de autorización fallidas impedirán los "ataques del diputado confundido" al abortar inmediatamente las consultas y devolver códigos de error de autorización explícitos en lugar de devolver conjuntos de resultados vacíos.
 #5.4.4    Level: 2    Role: V
 Verifique que la latencia en la evaluación de políticas se monitoree continuamente con alertas automatizadas para condiciones de tiempo de espera que podrían permitir la omisión de la autorización.
 #5.4.5    Level: 3    Role: D/V
 Verifique que los mecanismos de reintento de consultas vuelvan a evaluar las políticas de autorización para tener en cuenta los cambios dinámicos de permisos dentro de las sesiones activas de los usuarios.

---

### Filtrado de Salida C5.5 y Prevención de Pérdida de Datos

Implemente controles de posprocesamiento para evitar la exposición no autorizada de datos en contenido generado por IA.

 #5.5.1    Level: 1    Role: D/V
 Verifique que los mecanismos de filtrado posterior a la inferencia escaneen y redacten la información de identificación personal (PII), información clasificada y datos propietarios no autorizados antes de entregar el contenido a los solicitantes.
 #5.5.2    Level: 1    Role: D/V
 Verifique que las citas, referencias y atribuciones de fuentes en las salidas del modelo estén validadas contra los derechos del solicitante y que se eliminen si se detecta acceso no autorizado.
 #5.5.3    Level: 2    Role: D
 Verifique que las restricciones de formato de salida (PDFs sanitizados, imágenes sin metadatos, tipos de archivo aprobados) se apliquen según los niveles de permiso del usuario y las clasificaciones de datos.
 #5.5.4    Level: 2    Role: V
 Verifique que los algoritmos de redacción sean deterministas, controlados por versiones y mantengan registros de auditoría para respaldar investigaciones de cumplimiento y análisis forense.
 #5.5.5    Level: 3    Role: V
 Verifique que los eventos de redacción de alto riesgo generen registros adaptativos que incluyan hashes criptográficos del contenido original para su recuperación forense sin exposición de datos.

---

### C5.6 Aislamiento Multiinquilino

Garantizar el aislamiento criptográfico y lógico entre los inquilinos en una infraestructura de IA compartida.

 #5.6.1    Level: 1    Role: D/V
 Verifique que los espacios de memoria, almacenes de incrustaciones, entradas de caché y archivos temporales estén segregados por espacio de nombres para cada inquilino, con purga segura al eliminar el inquilino o al finalizar la sesión.
 #5.6.2    Level: 1    Role: D/V
 Verifique que cada solicitud de API incluya un identificador de inquilino autenticado que sea validado criptográficamente contra el contexto de la sesión y los derechos del usuario.
 #5.6.3    Level: 2    Role: D
 Verifique que las políticas de red implementen reglas de denegación predeterminadas para la comunicación entre inquilinos en mallas de servicios y plataformas de orquestación de contenedores.
 #5.6.4    Level: 3    Role: D
 Verifique que las claves de cifrado sean únicas por inquilino con soporte de clave gestionada por el cliente (CMK) y aislamiento criptográfico entre los almacenes de datos de los inquilinos.

---

### C5.7 Autorización de Agentes Autónomos

Controla los permisos para agentes de IA y sistemas autónomos mediante tokens de capacidad con alcance definido y autorización continua.

 #5.7.1    Level: 1    Role: D/V
 Verifique que los agentes autónomos reciban tokens de capacidad con alcance que enumeren explícitamente las acciones permitidas, los recursos accesibles, los límites de tiempo y las restricciones operativas.
 #5.7.2    Level: 1    Role: D/V
 Verifique que las capacidades de alto riesgo (acceso al sistema de archivos, ejecución de código, llamadas a API externas, transacciones financieras) estén deshabilitadas por defecto y requieran autorizaciones explícitas para su activación con justificaciones comerciales.
 #5.7.3    Level: 2    Role: D
 Verifique que los tokens de capacidad estén vinculados a las sesiones de usuario, incluyan protección criptográfica de integridad y asegure que no puedan ser almacenados ni reutilizados en escenarios fuera de línea.
 #5.7.4    Level: 2    Role: V
 Verifique que las acciones iniciadas por agentes pasen por una autorización secundaria a través del motor de políticas ABAC con evaluación completa del contexto y registro de auditoría.
 #5.7.5    Level: 3    Role: V
 Verifique que las condiciones de error del agente y el manejo de excepciones incluyan información sobre el alcance de capacidades para apoyar el análisis de incidentes y la investigación forense.

---

### Referencias

#### Normas y Marcos de Trabajo

NIST SP 800-63-3: Digital Identity Guidelines
Zero Trust Architecture – NIST SP 800-207
OWASP Application Security Verification Standard (AISVS)
​
#### Guías de Implementación

Identity and Access Management in the AI Era: 2025 Guide – IDSA
Attribute-Based Access Control with OPA – Permify
How We Designed Cedar to Be Intuitive, Fast, and Safe – AWS
​
#### Seguridad específica para IA

Row Level Security in Vector DBs for RAG – Bluetuple.ai
Tenant Isolation in Multi-Tenant Systems – WorkOS
Handling AI Agent Permissions – Stytch
OWASP Top 10 for Large Language Model Applications

## Seguridad en la Cadena de Suministro para Modelos, Frameworks y Datos

### Objetivo de Control

Los ataques a la cadena de suministro de IA explotan modelos, frameworks o conjuntos de datos de terceros para incrustar puertas traseras, sesgos o código explotable. Estos controles proporcionan trazabilidad de principio a fin, gestión de vulnerabilidades y monitoreo para proteger todo el ciclo de vida del modelo.

---

### C6.1 Evaluación y Procedencia del Modelo Preentrenado

Evalúe y autentique los orígenes, licencias y comportamientos ocultos de modelos de terceros antes de cualquier ajuste fino o despliegue.

 #6.1.1    Level: 1    Role: D/V
 Verifique que cada artefacto de modelo de terceros incluya un registro de procedencia firmado que identifique el repositorio fuente y el hash del commit.
 #6.1.2    Level: 1    Role: D/V
 Verifique que los modelos sean escaneados en busca de capas maliciosas o activadores tipo troyano utilizando herramientas automatizadas antes de la importación.
 #6.1.3    Level: 2    Role: D
 Verifique que el aprendizaje por transferencia ajustado pase la evaluación adversarial para detectar comportamientos ocultos.
 #6.1.4    Level: 2    Role: V
 Verifique que las licencias del modelo, las etiquetas de control de exportación y las declaraciones de origen de datos estén registradas en una entrada de ML-BOM.
 #6.1.5    Level: 3    Role: D/V
 Verifique que los modelos de alto riesgo (pesos subidos públicamente, creadores no verificados) permanezcan en cuarentena hasta que sean revisados y aprobados por un humano.

---

### C6.2 Escaneo de Frameworks y Bibliotecas

Escanee continuamente los marcos y bibliotecas de aprendizaje automático (ML) para detectar CVEs y código malicioso y mantener segura la pila de ejecución.

 #6.2.1    Level: 1    Role: D/V
 Verifique que las canalizaciones de integración continua ejecuten escáneres de dependencias en los marcos de IA y las bibliotecas críticas.
 #6.2.2    Level: 1    Role: D/V
 Verifique que las vulnerabilidades críticas (CVSS ≥ 7.0) bloqueen la promoción a imágenes de producción.
 #6.2.3    Level: 2    Role: D
 Verifique que el análisis estático de código se ejecute en bibliotecas de aprendizaje automático bifurcadas o empaquetadas.
 #6.2.4    Level: 2    Role: V
 Verifique que las propuestas de actualización del framework incluyan una evaluación del impacto en la seguridad que haga referencia a fuentes públicas de CVE.
 #6.2.5    Level: 3    Role: V
 Verifique que los sensores en tiempo de ejecución alerten sobre cargas inesperadas de bibliotecas dinámicas que se desvíen del SBOM firmado.

---

### C6.3 Fijación y Verificación de Dependencias

Fije cada dependencia a sumas inmutables y reproduzca las compilaciones para garantizar artefactos idénticos y libres de manipulaciones.

 #6.3.1    Level: 1    Role: D/V
 Verifique que todos los gestores de paquetes apliquen la fijación de versiones mediante archivos de bloqueo.
 #6.3.2    Level: 1    Role: D/V
 Verifique que se usen resúmenes inmutables en lugar de etiquetas mutables en las referencias de contenedores.
 #6.3.3    Level: 2    Role: D
 Verifique que las comprobaciones de compilaciones reproducibles comparen los hashes entre ejecuciones de CI para asegurar salidas idénticas.
 #6.3.4    Level: 2    Role: V
 Verifique que las atestaciones de compilación se almacenen durante 18 meses para la trazabilidad de auditoría.
 #6.3.5    Level: 3    Role: D
 Verifique que las dependencias expiradas desencadenen solicitudes de extracción automatizadas para actualizar o bifurcar versiones fijadas.

---

### C6.4 Aplicación de Fuentes Confiables

Permitir descargas de artefactos solo desde fuentes aprobadas por la organización y verificadas criptográficamente, y bloquear todo lo demás.

 #6.4.1    Level: 1    Role: D/V
 Verifique que los pesos del modelo, los conjuntos de datos y los contenedores se descarguen únicamente de dominios aprobados o registros internos.
 #6.4.2    Level: 1    Role: D/V
 Verifique que las firmas de Sigstore/Cosign validen la identidad del editor antes de que los artefactos se almacenen en caché localmente.
 #6.4.3    Level: 2    Role: D
 Verifique que los proxies de salida bloqueen las descargas de artefactos no autenticadas para hacer cumplir la política de fuentes confiables.
 #6.4.4    Level: 2    Role: V
 Verifique que las listas blancas del repositorio se revisen trimestralmente con evidencia de justificación comercial para cada entrada.
 #6.4.5    Level: 3    Role: V
 Verifique que las violaciones de políticas desencadenen la cuarentena de artefactos y la reversión de las ejecuciones de canalizaciones dependientes.

---

### C6.5 Evaluación de Riesgos de Conjuntos de Datos de Terceros

Evaluar los conjuntos de datos externos en busca de envenenamiento, sesgo y cumplimiento legal, y supervisarlos durante todo su ciclo de vida.

 #6.5.1    Level: 1    Role: D/V
 Verifique que los conjuntos de datos externos sean sometidos a una puntuación de riesgo de envenenamiento (por ejemplo, huellas digitales de datos, detección de valores atípicos).
 #6.5.2    Level: 1    Role: D
 Verifique que las métricas de sesgo (paridad demográfica, igualdad de oportunidades) se calculen antes de la aprobación del conjunto de datos.
 #6.5.3    Level: 2    Role: V
 Verifique que la procedencia y los términos de licencia de los conjuntos de datos estén registrados en las entradas del ML‑BOM.
 #6.5.4    Level: 2    Role: V
 Verifique que la supervisión periódica detecte desviaciones o corrupción en los conjuntos de datos alojados.
 #6.5.5    Level: 3    Role: D
 Verifique que el contenido no permitido (derechos de autor, información personal identificable) sea eliminado mediante un proceso automático de depuración antes del entrenamiento.

---

### C6.6 Monitoreo de Ataques a la Cadena de Suministro

Detecte amenazas en la cadena de suministro temprano mediante fuentes CVE, análisis de registros de auditoría y simulaciones de equipos rojos.

 #6.6.1    Level: 1    Role: V
 Verifique que los registros de auditoría de CI/CD se transmitan a SIEM para detectar extracciones de paquetes anómalas o pasos de compilación manipulados.
 #6.6.2    Level: 2    Role: D
 Verifique que los manuales de respuesta a incidentes incluyan procedimientos de reversión para modelos o bibliotecas comprometidos.
 #6.6.3    Level: 3    Role: V
 Verifique que el enriquecimiento de inteligencia de amenazas etiquete indicadores específicos de ML (por ejemplo, IoCs de envenenamiento de modelos) en la triaje de alertas.

---

### C6.7 ML‑BOM para Artefactos de Modelo

Genere y firme SBOMs específicos para ML detallados (ML-BOMs) para que los consumidores posteriores puedan verificar la integridad de los componentes en el momento del despliegue.

 #6.7.1    Level: 1    Role: D/V
 Verifique que cada artefacto de modelo publique un ML-BOM que liste conjuntos de datos, pesos, hiperparámetros y licencias.
 #6.7.2    Level: 1    Role: D/V
 Verifique que la generación de ML-BOM y la firma con Cosign estén automatizadas en CI y sean obligatorias para la fusión.
 #6.7.3    Level: 2    Role: D
 Verifique que las comprobaciones de integridad de ML-BOM fallen la compilación si falta algún metadato del componente (hash, licencia).
 #6.7.4    Level: 2    Role: V
 Verifique que los consumidores posteriores puedan consultar ML-BOMs a través de la API para validar los modelos importados en el momento del despliegue.
 #6.7.5    Level: 3    Role: V
 Verifique que las ML-BOMs estén controladas por versiones y se comparen para detectar modificaciones no autorizadas.

---

### Referencias

ML Supply Chain Compromise – MITRE ATLAS
Supply‑chain Levels for Software Artifacts (SLSA)
CycloneDX – Machine Learning Bill of Materials
What is Data Poisoning? – SentinelOne
Transfer Learning Attack – OWASP ML Security Top 10
AI Data Security Best Practices – CISA
Secure CI/CD Supply Chain – Sumo Logic
AI & Transparency: Protect ML Models – ReversingLabs
SBOM Overview – CISA
Training Data Poisoning Guide – Lakera.ai
Dependency Pinning for Reproducible Python – Medium

## Comportamiento del Modelo C7, Control de Salida y Garantía de Seguridad

### Objetivo de Control

Los resultados del modelo deben ser estructurados, confiables, seguros, explicables y monitoreados continuamente en producción. Esto reduce alucinaciones, filtraciones de privacidad, contenido dañino y acciones descontroladas, mientras aumenta la confianza del usuario y el cumplimiento normativo.

---

### C7.1 Aplicación del Formato de Salida

Los esquemas estrictos, la decodificación restringida y la validación posterior detienen el contenido malformado o malicioso antes de que se propague.

 #7.1.1    Level: 1    Role: D/V
 Verifique que los esquemas de respuesta (por ejemplo, JSON Schema) se proporcionen en el mensaje del sistema y que cada salida se valide automáticamente; las salidas que no cumplan con el esquema deben activar una reparación o rechazo.
 #7.1.2    Level: 1    Role: D/V
 Verifique que la decodificación restringida (tokens de detención, expresiones regulares, máximo de tokens) esté habilitada para evitar desbordamientos o canales laterales de inyección de indicaciones.
 #7.1.3    Level: 2    Role: D/V
 Verifique que los componentes descendentes traten las salidas como no confiables y las validen contra esquemas o deserializadores seguros contra inyección.
 #7.1.4    Level: 3    Role: V
 Verifique que los eventos de salida incorrecta se registren, se limiten en su frecuencia y se muestren en el monitoreo.

---

### C7.2 Detección y Mitigación de Alucinaciones

La estimación de la incertidumbre y las estrategias de retroceso limitan las respuestas fabricadas.

 #7.2.1    Level: 1    Role: D/V
 Verifique que las probabilidades logarítmicas a nivel de token, la auto-consistencia del conjunto o los detectores de alucinaciones ajustados asignen una puntuación de confianza a cada respuesta.
 #7.2.2    Level: 1    Role: D/V
 Verifique que las respuestas por debajo de un umbral de confianza configurable activen flujos de trabajo de respaldo (por ejemplo, generación aumentada por recuperación, modelo secundario o revisión humana).
 #7.2.3    Level: 2    Role: D/V
 Verifique que los incidentes de alucinación estén etiquetados con metadatos de causa raíz y se envíen a los procesos de análisis post-mortem y ajuste fino.
 #7.2.4    Level: 3    Role: D/V
 Verifique que los umbrales y detectores se recalibren después de actualizaciones importantes del modelo o de la base de conocimientos.
 #7.2.5    Level: 3    Role: V
 Verifique que las visualizaciones del panel de control rastreen las tasas de alucinaciones.

---

### C7.3 Filtrado de Seguridad y Privacidad de la Salida

Los filtros de políticas y la cobertura del equipo rojo protegen a los usuarios y los datos confidenciales.

 #7.3.1    Level: 1    Role: D/V
 Verifique que los clasificadores previos y posteriores a la generación bloqueen contenido de odio, acoso, autolesiones, extremista y sexualmente explícito alineado con la política.
 #7.3.2    Level: 1    Role: D/V
 Verifique que la detección de PII/PCI y la redacción automática se ejecuten en cada respuesta; las violaciones generan un incidente de privacidad.
 #7.3.3    Level: 2    Role: D
 Verifique que las etiquetas de confidencialidad (por ejemplo, secretos comerciales) se propaguen a través de modalidades para evitar filtraciones en texto, imágenes o código.
 #7.3.4    Level: 3    Role: D/V
 Verifique que los intentos de omisión del filtro o las clasificaciones de alto riesgo requieran aprobación secundaria o la reautenticación del usuario.
 #7.3.5    Level: 3    Role: D/V
 Verifique que los umbrales de filtrado reflejen las jurisdicciones legales y el contexto de edad/rol del usuario.

---

### C7.4 Limitación de Salida y Acción

Los límites de tasa y las puertas de aprobación previenen el abuso y la autonomía excesiva.

 #7.4.1    Level: 1    Role: D
 Verifique que las cuotas por usuario y por clave API limiten las solicitudes, tokens y costos con retroceso exponencial en caso de errores 429.
 #7.4.2    Level: 1    Role: D/V
 Verifique que las acciones privilegiadas (escritura de archivos, ejecución de código, llamadas de red) requieran aprobación basada en políticas o intervención humana.
 #7.4.3    Level: 2    Role: D/V
 Verifique que las comprobaciones de consistencia multimodal aseguran que las imágenes, el código y el texto generados para la misma solicitud no puedan ser utilizados para introducir contenido malicioso.
 #7.4.4    Level: 2    Role: D
 Verifique que la profundidad de delegación del agente, los límites de recursión y las listas de herramientas permitidas estén configurados explícitamente.
 #7.4.5    Level: 3    Role: V
 Verifique que la violación de límites emita eventos de seguridad estructurados para la ingestión en SIEM.

---

### C7.5 Explicabilidad de la salida

Las señales transparentes mejoran la confianza del usuario y la depuración interna.

 #7.5.1    Level: 2    Role: D/V
 Verifique que las puntuaciones de confianza dirigidas al usuario o los resúmenes breves de razonamiento se presenten cuando la evaluación de riesgos lo considere apropiado.
 #7.5.2    Level: 2    Role: D/V
 Verifique que las explicaciones generadas eviten revelar indicaciones sensibles del sistema o datos propietarios.
 #7.5.3    Level: 3    Role: D
 Verifique que el sistema capture las probabilidades logarítmicas a nivel de token o los mapas de atención y los almacene para inspección autorizada.
 #7.5.4    Level: 3    Role: V
 Verifique que los artefactos de explicabilidad estén controlados por versiones junto con las versiones del modelo para garantizar la auditabilidad.

---

### C7.6 Integración de Monitoreo

La observabilidad en tiempo real cierra el ciclo entre el desarrollo y la producción.

 #7.6.1    Level: 1    Role: D
 Verifique que las métricas (violaciones de esquema, tasa de alucinaciones, toxicidad, fugas de información personal identificable, latencia, costo) se transmitan a una plataforma central de monitoreo.
 #7.6.2    Level: 1    Role: V
 Verifique que se definan umbrales de alerta para cada métrica de seguridad, con rutas de escalamiento para personal de guardia.
 #7.6.3    Level: 2    Role: V
 Verifique que los paneles correlacionen las anomalías de salida con el modelo/versión, la bandera de función y los cambios en los datos ascendentes.
 #7.6.4    Level: 2    Role: D/V
 Verifique que los datos de monitoreo se retroalimenten en el reentrenamiento, ajuste fino o actualizaciones de reglas dentro de un flujo de trabajo documentado de MLOps.
 #7.6.5    Level: 3    Role: V
 Verifique que las canalizaciones de monitoreo hayan sido sometidas a pruebas de penetración y tengan control de acceso para evitar la filtración de registros sensibles.

---

### 7.7 Salvaguardas de Medios Generativos

Asegurar que los sistemas de IA no generen contenido multimedia ilegal, dañino o no autorizado mediante la aplicación de restricciones de políticas, validación de salidas y trazabilidad.

 #7.7.1    Level: 1    Role: D/V
 Verifique que los mensajes del sistema y las instrucciones para el usuario prohíban explícitamente la generación de medios deepfake ilegales, dañinos o no consensuados (por ejemplo, imágenes, videos, audios).
 #7.7.2    Level: 2    Role: D/V
 Verifique que las indicaciones sean filtradas para detectar intentos de generar suplantaciones, deepfakes sexualmente explícitos o medios que muestren a personas reales sin su consentimiento.
 #7.7.3    Level: 2    Role: V
 Verifique que el sistema utilice hashing perceptual, detección de marcas de agua o huellas digitales para prevenir la reproducción no autorizada de medios con derechos de autor.
 #7.7.4    Level: 3    Role: D/V
 Verifique que todos los medios generados estén firmados criptográficamente, marcados con una marca de agua o integrados con metadatos de procedencia resistentes a la manipulación para la trazabilidad posterior.
 #7.7.5    Level: 3    Role: V
 Verifique que los intentos de bypass (por ejemplo, ofuscación de indicaciones, jerga, formulación adversarial) sean detectados, registrados y sujetos a limitación de tasa; los abusos repetidos se informan a los sistemas de monitoreo.

### Referencias

NIST AI Risk Management Framework
ISO/IEC 42001:2023 – AI Management System
OWASP Top-10 for Large Language Model Applications (2025)
Improper Output Handling – OWASP LLM05:2025
Practical Techniques to Constrain LLM Output
Dataiku – Structured Text Generation Guide
VL-Uncertainty: Detecting Hallucinations
HaDeMiF: Hallucination Detection & Mitigation
Building Confidence in LLM Outputs
Explainable AI & LLMs
LLM Red-Teaming Guide
Sensitive Information Disclosure in LLMs
LangChain – Chat Model Rate Limiting
OpenAI Rate-Limit & Exponential Back-off
Arize AI – LLM Observability Platform

## Memoria C8, Embeddings y Seguridad de Bases de Datos Vectoriales

### Objetivo de Control

Los embeddings y las bases de datos vectoriales actúan como la "memoria viva" de los sistemas de IA contemporáneos, aceptando continuamente datos proporcionados por el usuario y reintroduciéndolos en los contextos del modelo mediante la Generación Aumentada por Recuperación (RAG). Si no se supervisa adecuadamente, esta memoria puede filtrar información de identificación personal (PII), violar el consentimiento o invertirse para reconstruir el texto original. El objetivo de esta familia de controles es fortalecer las canalizaciones de memoria y las bases de datos vectoriales para que el acceso sea de mínimo privilegio, los embeddings preserven la privacidad, los vectores almacenados expiren o puedan ser revocados bajo demanda, y la memoria por usuario nunca contamine las indicaciones ni las respuestas de otro usuario.

---

### C8.1 Controles de acceso en memoria e índices RAG

Implemente controles de acceso detallados en cada colección de vectores.

 #8.1.1    Level: 1    Role: D/V
 Verifique que las reglas de control de acceso a nivel de fila/espacio de nombres restrinjan las operaciones de inserción, eliminación y consulta por inquilino, colección o etiqueta de documento.
 #8.1.2    Level: 1    Role: D/V
 Verifique que las claves API o los JWT contengan reclamaciones con ámbito específico (por ejemplo, IDs de colección, verbos de acción) y que se roten al menos trimestralmente.
 #8.1.3    Level: 2    Role: D/V
 Verifique que los intentos de escalada de privilegios (por ejemplo, consultas de similitud entre espacios de nombres) sean detectados y registrados en un SIEM dentro de los 5 minutos.
 #8.1.4    Level: 2    Role: D/V
 Verifique que la base de datos vectorial registre en el auditoría el identificador del sujeto, la operación, el ID/espacio de nombres del vector, el umbral de similitud y el recuento de resultados.
 #8.1.5    Level: 3    Role: V
 Verifique que las decisiones de acceso se prueben en busca de fallas de omisión siempre que se actualicen los motores o cambien las reglas de fragmentación de índices.

---

### C8.2 Saneamiento y Validación de Incrustaciones

Preseleccione el texto para información de identificación personal (PII), redacte o seudonimice antes de la vectorización, y opcionalmente realice un post-procesamiento de los embeddings para eliminar señales residuales.

 #8.2.1    Level: 1    Role: D/V
 Verifique que los datos de identificación personal (PII) y los datos regulados sean detectados mediante clasificadores automáticos y que se anonimizan, tokenizan o eliminan antes de la generación de incrustaciones (pre-embedding).
 #8.2.2    Level: 1    Role: D
 Verifique que las canalizaciones de embeddings rechacen o pongan en cuarentena entradas que contengan código ejecutable o artefactos no UTF-8 que podrían envenenar el índice.
 #8.2.3    Level: 2    Role: D/V
 Verifique que se aplique una sanitización de privacidad diferencial local o métrica a las incrustaciones de oraciones cuya distancia a cualquier token PII conocido caiga por debajo de un umbral configurable.
 #8.2.4    Level: 2    Role: V
 Verifique que la eficacia de la desinfección (por ejemplo, la recuperación de la redacción de información personal identificable, la deriva semántica) se valide al menos semestralmente contra corpus de referencia.
 #8.2.5    Level: 3    Role: D/V
 Verifique que las configuraciones de saneamiento estén controladas por versión y que los cambios pasen por una revisión por pares.

---

### C8.3 Expiración, Revocación y Eliminación de Memoria

El "derecho al olvido" del GDPR y leyes similares requieren la eliminación oportuna; por lo tanto, los almacenes vectoriales deben soportar TTLs, eliminaciones definitivas y tomb-stoning para que los vectores revocados no puedan ser recuperados ni reindexados.

 #8.3.1    Level: 1    Role: D/V
 Verifique que cada vector y registro de metadatos tenga un TTL o una etiqueta de retención explícita que sea respetada por los trabajos automáticos de limpieza.
 #8.3.2    Level: 1    Role: D/V
 Verifique que las solicitudes de eliminación iniciadas por el usuario eliminen vectores, metadatos, copias en caché e índices derivados dentro de los 30 días.
 #8.3.3    Level: 2    Role: D
 Verifique que las eliminaciones lógicas sean seguidas por el borrado criptográfico de los bloques de almacenamiento si el hardware lo soporta, o por la destrucción de claves del almacén de claves.
 #8.3.4    Level: 3    Role: D/V
 Verifique que los vectores caducados se excluyan de los resultados de la búsqueda de vecinos más cercanos en menos de 500 ms después de la expiración.

---

### C8.4 Prevenir la inversión y filtración de incrustaciones

Las defensas recientes — superposición de ruido, redes de proyección, perturbación de neuronas de privacidad y cifrado a nivel de aplicación — pueden reducir las tasas de inversión a nivel de token por debajo del 5%.

 #8.4.1    Level: 1    Role: V
 Verifique que exista un modelo formal de amenazas que cubra ataques de inversión, membresía e inferencia de atributos y que sea revisado anualmente.
 #8.4.2    Level: 2    Role: D/V
 Verifique que el cifrado a nivel de aplicación o el cifrado buscable protejan los vectores de lecturas directas por parte de los administradores de infraestructura o el personal de la nube.
 #8.4.3    Level: 3    Role: V
 Verifique que los parámetros de defensa (ε para DP, ruido σ, rango de proyección k) equilibren la privacidad ≥ 99 % de protección de tokens y la utilidad ≤ 3 % de pérdida de precisión.
 #8.4.4    Level: 3    Role: D/V
 Verifique que las métricas de resiliencia a la inversión formen parte de los umbrales de liberación para las actualizaciones del modelo, con presupuestos de regresión definidos.

---

### C8.5 Aplicación del Alcance para la Memoria Específica del Usuario

La filtración entre inquilinos sigue siendo un riesgo principal en RAG: las consultas de similitud filtradas incorrectamente pueden mostrar documentos privados de otro cliente.

 #8.5.1    Level: 1    Role: D/V
 Verifique que cada consulta de recuperación sea filtrada posteriormente por ID de inquilino/usuario antes de ser pasada al prompt del LLM.
 #8.5.2    Level: 1    Role: D
 Verifique que los nombres de colecciones o los IDs con espacio de nombres estén salados por usuario o inquilino para que los vectores no puedan colisionar entre ámbitos.
 #8.5.3    Level: 2    Role: D/V
 Verifique que los resultados de similitud que superan un umbral de distancia configurable pero están fuera del alcance del llamador sean descartados y generen alertas de seguridad.
 #8.5.4    Level: 2    Role: V
 Verifique que las pruebas de estrés multiinquilino simulan consultas adversarias que intentan recuperar documentos fuera de alcance y demuestran ausencia total de filtración.
 #8.5.5    Level: 3    Role: D/V
 Verifique que las claves de cifrado estén segregadas por inquilino, asegurando el aislamiento criptográfico incluso si se comparte el almacenamiento físico.

---

### C8.6 Seguridad Avanzada del Sistema de Memoria

Controles de seguridad para arquitecturas de memoria sofisticadas que incluyen memoria episódica, semántica y de trabajo, con requisitos específicos de aislamiento y validación.

 #8.6.1    Level: 1    Role: D/V
 Verifique que los diferentes tipos de memoria (episódica, semántica, de trabajo) tengan contextos de seguridad aislados con controles de acceso basados en roles, claves de cifrado separadas y patrones de acceso documentados para cada tipo de memoria.
 #8.6.2    Level: 2    Role: D/V
 Verifique que los procesos de consolidación de memoria incluyan validación de seguridad para prevenir la inyección de memorias maliciosas mediante la sanitización de contenido, verificación de la fuente y controles de integridad antes del almacenamiento.
 #8.6.3    Level: 2    Role: D/V
 Verifique que las consultas de recuperación de memoria sean validadas y saneadas para evitar la extracción de información no autorizada mediante el análisis de patrones de consulta, la aplicación de controles de acceso y el filtrado de resultados.
 #8.6.4    Level: 3    Role: D/V
 Verifique que los mecanismos de olvido de memoria eliminen de forma segura la información sensible con garantías de borrado criptográfico mediante la eliminación de claves, sobrescritura múltiple o eliminación segura basada en hardware con certificados de verificación.
 #8.6.5    Level: 3    Role: D/V
 Verifique que la integridad del sistema de memoria sea monitoreada continuamente para detectar modificaciones no autorizadas o corrupciones mediante sumas de verificación, registros de auditoría y alertas automatizadas cuando el contenido de la memoria cambie fuera de las operaciones normales.

---

### Referencias

Vector database security: Pinecone – IronCore Labs
Securing the Backbone of AI: Safeguarding Vector Databases and Embeddings – Privacera
Enhancing Data Security with RBAC of Qdrant Vector Database – AI Advances
Mitigating Privacy Risks in LLM Embeddings from Embedding Inversion – arXiv
DPPN: Detecting and Perturbing Privacy-Sensitive Neurons – OpenReview
Art. 17 GDPR – Right to Erasure
Sensitive Data in Text Embeddings Is Recoverable – Tonic.ai
PII Identification and Removal – NVIDIA NeMo Docs
De-identifying Sensitive Data – Google Cloud DLP
Remove PII from Conversations Using Sensitive Information Filters – AWS Bedrock Guardrails
Think Your RAG Is Secure? Think Again – Medium
Design a Secure Multitenant RAG Inferencing Solution – Microsoft Learn
Best Practices for Multi-Tenancy RAG with Milvus – Milvus Blog

## 9 Orquestación Autónoma y Acción Agencial en Seguridad

### Objetivo de Control

Asegurar que los sistemas de IA autónomos o multiagente solo puedan ejecutar acciones que sean explícitamente intencionadas, autenticadas, auditables y dentro de umbrales limitados de costo y riesgo. Esto protege contra amenazas como el compromiso de sistemas autónomos, el uso indebido de herramientas, la detección de bucles de agentes, el secuestro de comunicaciones, la suplantación de identidad, la manipulación de enjambres y la manipulación de intenciones.

---

### 9.1 Presupuestos de Planificación de Tareas y Recursión del Agente

Regule los planes recursivos y establezca puntos de control humanos obligatorios para acciones privilegiadas.

 #9.1.1    Level: 1    Role: D/V
 Verifique que la profundidad máxima de recursión, amplitud, tiempo real, tokens y costo monetario por ejecución de agente estén configurados de manera centralizada y controlados por versión.
 #9.1.2    Level: 1    Role: D/V
 Verifique que las acciones privilegiadas o irreversibles (por ejemplo, commits de código, transferencias financieras) requieran la aprobación explícita de un humano a través de un canal auditable antes de su ejecución.
 #9.1.3    Level: 2    Role: D
 Verifique que los monitores de recursos en tiempo real activen la interrupción del interruptor de circuito cuando se exceda cualquier umbral de presupuesto, deteniendo la expansión adicional de tareas.
 #9.1.4    Level: 2    Role: D/V
 Verifique que los eventos del interruptor automático se registren con la ID del agente, la condición de activación y el estado del plan capturado para revisión forense.
 #9.1.5    Level: 3    Role: V
 Verifique que las pruebas de seguridad cubran escenarios de agotamiento del presupuesto y de planes fuera de control, confirmando una detención segura sin pérdida de datos.
 #9.1.6    Level: 3    Role: D
 Verifique que las políticas de presupuesto estén expresadas como políticas en código y se apliquen en CI/CD para bloquear la desviación de configuración.

---

### 9.2 Aislamiento del complemento de herramientas

Aislar las interacciones de las herramientas para evitar el acceso no autorizado al sistema o la ejecución de código.

 #9.2.1    Level: 1    Role: D/V
 Verifique que cada herramienta/plugin se ejecute dentro de un sistema operativo, contenedor o sandbox a nivel WASM con políticas de privilegios mínimos para el sistema de archivos, red y llamadas al sistema.
 #9.2.2    Level: 1    Role: D/V
 Verifique que se apliquen y registren las cuotas de recursos del sandbox (CPU, memoria, disco, salida de red) y los tiempos de espera de ejecución.
 #9.2.3    Level: 2    Role: D/V
 Verifique que los binarios o descriptores de la herramienta estén firmados digitalmente; las firmas deben ser validadas antes de cargarlos.
 #9.2.4    Level: 2    Role: V
 Verifique que la telemetría del sandbox se transmita a un SIEM; las anomalías (por ejemplo, intentos de conexiones salientes) generan alertas.
 #9.2.5    Level: 3    Role: V
 Verifique que los complementos de alto riesgo pasen por una revisión de seguridad y pruebas de penetración antes del despliegue en producción.
 #9.2.6    Level: 3    Role: D/V
 Verifique que los intentos de escape del sandbox se bloqueen automáticamente y que el complemento infractor sea puesto en cuarentena pendiente de investigación.

---

### 9.3 Bucle Autónomo y Limitación de Costos

Detectar y detener la recursión descontrolada entre agentes y las explosiones de costos.

 #9.3.1    Level: 1    Role: D/V
 Verifique que las llamadas entre agentes incluyan un límite de saltos o TTL que el tiempo de ejecución decremente y aplique.
 #9.3.2    Level: 2    Role: D
 Verifique que los agentes mantengan un ID único de gráfico de invocación para detectar auto-invocaciones o patrones cíclicos.
 #9.3.3    Level: 2    Role: D/V
 Verifique que los contadores acumulativos de unidades de cómputo y gasto se rastreen por cadena de solicitudes; superar el límite aborta la cadena.
 #9.3.4    Level: 3    Role: V
 Verifique que el análisis formal o la verificación mediante modelos demuestren la ausencia de recursión no acotada en los protocolos de agentes.
 #9.3.5    Level: 3    Role: D
 Verifique que los eventos de aborto de bucle generen alertas y alimenten métricas de mejora continua.

---

### 9.4 Protección contra uso indebido a nivel de protocolo

Canales de comunicación seguros entre agentes y sistemas externos para prevenir secuestros o manipulaciones.

 #9.4.1    Level: 1    Role: D/V
 Verifique que todos los mensajes de agente a herramienta y de agente a agente estén autenticados (por ejemplo, TLS mutuo o JWT) y cifrados de extremo a extremo.
 #9.4.2    Level: 1    Role: D
 Verifique que los esquemas sean validados estrictamente; los campos desconocidos o los mensajes mal formados sean rechazados.
 #9.4.3    Level: 2    Role: D/V
 Verifique que las comprobaciones de integridad (MAC o firmas digitales) cubran toda la carga útil del mensaje, incluidos los parámetros de la herramienta.
 #9.4.4    Level: 2    Role: D
 Verifique que la protección contra repetición (números únicos o ventanas de marcas de tiempo) se aplique en la capa del protocolo.
 #9.4.5    Level: 3    Role: V
 Verifique que las implementaciones del protocolo sean sometidas a fuzzing y análisis estático para detectar fallos de inyección o deserialización.

---

### 9.5 Identidad del Agente y Evidencia de Manipulación

Asegurar que las acciones sean atribuibles y las modificaciones detectables.

 #9.5.1    Level: 1    Role: D/V
 Verifique que cada instancia de agente posea una identidad criptográfica única (par de claves o credencial basada en hardware).
 #9.5.2    Level: 2    Role: D/V
 Verifique que todas las acciones del agente estén firmadas y tengan marca de tiempo; los registros deben incluir la firma para evitar la repudio.
 #9.5.3    Level: 2    Role: V
 Verifique que los registros a prueba de manipulaciones se almacenen en un medio solo de adición o de escritura única.
 #9.5.4    Level: 3    Role: D
 Verifique que las claves de identidad roten según un calendario definido y ante indicadores de compromiso.
 #9.5.5    Level: 3    Role: D/V
 Verifique que los intentos de suplantación o conflictos de claves provoquen la cuarentena inmediata del agente afectado.

---

### 9.6 Reducción de Riesgos en Enjambres Multiagente

Mitigar los riesgos de comportamiento colectivo mediante el aislamiento y el modelado formal de seguridad.

 #9.6.1    Level: 1    Role: D/V
 Verifique que los agentes que operan en diferentes dominios de seguridad se ejecuten en entornos de ejecución aislados o segmentos de red separados.
 #9.6.2    Level: 3    Role: V
 Verifique que los comportamientos del enjambre estén modelados y verificados formalmente para vivacidad y seguridad antes del despliegue.
 #9.6.3    Level: 3    Role: D
 Verifique que los monitores en tiempo de ejecución detecten patrones emergentes inseguros (por ejemplo, oscilaciones, bloqueos) e inicien acciones correctivas.

---

### 9.7 Autenticación / Autorización de Usuario y Herramienta

Implemente controles de acceso robustos para cada acción activada por un agente.

 #9.7.1    Level: 1    Role: D/V
 Verifique que los agentes se autentiquen como principales de primera clase ante los sistemas aguas abajo, sin reutilizar jamás las credenciales del usuario final.
 #9.7.2    Level: 2    Role: D
 Verifique que las políticas de autorización detalladas restrinjan qué herramientas puede invocar un agente y qué parámetros puede suministrar.
 #9.7.3    Level: 2    Role: V
 Verifique que las comprobaciones de privilegios se reevalúen en cada llamada (autorización continua), no solo al inicio de la sesión.
 #9.7.4    Level: 3    Role: D
 Verifique que los privilegios delegados expiren automáticamente y requieran nuevo consentimiento después del tiempo de espera o cambio de alcance.

---

### 9.8 Seguridad en la Comunicación entre Agentes

Encripte y proteja la integridad de todos los mensajes entre agentes para evitar la interceptación y la manipulación.

 #9.8.1    Level: 1    Role: D/V
 Verifique que la autenticación mutua y el cifrado con secreto perfecto hacia adelante (por ejemplo, TLS 1.3) sean obligatorios para los canales de agentes.
 #9.8.2    Level: 1    Role: D
 Verifique que la integridad y el origen del mensaje se validen antes de procesarlo; las fallas generan alertas y descartan el mensaje.
 #9.8.3    Level: 2    Role: D/V
 Verifique que los metadatos de comunicación (marcas de tiempo, números de secuencia) se registren para apoyar la reconstrucción forense.
 #9.8.4    Level: 3    Role: V
 Verifique que la verificación formal o la comprobación de modelos confirme que las máquinas de estados del protocolo no pueden ser llevadas a estados inseguros.

---

### 9.9 Verificación de Intenciones y Aplicación de Restricciones

Validar que las acciones del agente estén alineadas con la intención declarada del usuario y las restricciones del sistema.

 #9.9.1    Level: 1    Role: D
 Verifique que los solucionadores de restricciones previas a la ejecución revisen las acciones propuestas contra reglas de seguridad y políticas codificadas rígidamente.
 #9.9.2    Level: 2    Role: D/V
 Verifique que las acciones de alto impacto (financieras, destructivas, sensibles a la privacidad) requieran una confirmación explícita de intención por parte del usuario que las inicia.
 #9.9.3    Level: 2    Role: V
 Verifique que las comprobaciones de post-condición validen que las acciones completadas lograron los efectos previstos sin efectos secundarios; las discrepancias desencadenan una reversión.
 #9.9.4    Level: 3    Role: V
 Verifique que los métodos formales (por ejemplo, verificación de modelos, demostración de teoremas) o las pruebas basadas en propiedades demuestren que los planes de los agentes satisfacen todas las restricciones declaradas.
 #9.9.5    Level: 3    Role: D
 Verifique que los incidentes de incompatibilidad de intención o violación de restricciones alimenten los ciclos de mejora continua y el intercambio de inteligencia sobre amenazas.

---

### 9.10 Estrategia de Razonamiento del Agente y Seguridad

Selección y ejecución segura de diferentes estrategias de razonamiento, incluyendo los enfoques ReAct, Cadena-de-Pensamiento y Árbol-de-Pensamientos.

 #9.10.1    Level: 1    Role: D/V
 Verifique que la selección de la estrategia de razonamiento utilice criterios deterministas (complejidad de la entrada, tipo de tarea, contexto de seguridad) y que entradas idénticas produzcan selecciones de estrategia idénticas dentro del mismo contexto de seguridad.
 #9.10.2    Level: 1    Role: D/V
 Verifique que cada estrategia de razonamiento (ReAct, Cadena de Pensamiento, Árbol de Pensamientos) tenga validación de entrada dedicada, saneamiento de salida y límites de tiempo de ejecución específicos para su enfoque cognitivo.
 #9.10.3    Level: 2    Role: D/V
 Verifique que las transiciones de la estrategia de razonamiento se registren con un contexto completo que incluya las características de entrada, los valores de los criterios de selección y los metadatos de ejecución para la reconstrucción de la pista de auditoría.
 #9.10.4    Level: 2    Role: D/V
 Verifique que el razonamiento del Árbol de Pensamientos incluya mecanismos de poda de ramas que terminen la exploración cuando se detecten violaciones de políticas, límites de recursos o límites de seguridad.
 #9.10.5    Level: 2    Role: D/V
 Verifique que los ciclos ReAct (Razonar-Actuar-Observar) incluyan puntos de control de validación en cada fase: verificación de paso de razonamiento, autorización de acción y sanitización de observación antes de proceder.
 #9.10.6    Level: 3    Role: D/V
 Verifique que las métricas de rendimiento de la estrategia de razonamiento (tiempo de ejecución, uso de recursos, calidad de salida) sean monitoreadas con alertas automáticas cuando las métricas se desvíen más allá de los umbrales configurados.
 #9.10.7    Level: 3    Role: D/V
 Verifique que los enfoques de razonamiento híbrido que combinan múltiples estrategias mantengan la validación de entrada y las restricciones de salida de todas las estrategias constituyentes sin eludir ningún control de seguridad.
 #9.10.8    Level: 3    Role: D/V
 Verifique que la estrategia de razonamiento para las pruebas de seguridad incluya fuzzing con entradas malformadas, mensajes adversariales diseñados para forzar el cambio de estrategia, y pruebas de condiciones límite para cada enfoque cognitivo.

---

### 9.11 Gestión del ciclo de vida y seguridad del estado del agente

Inicialización segura del agente, transiciones de estado y terminación con registros criptográficos de auditoría y procedimientos de recuperación definidos.

 #9.11.1    Level: 1    Role: D/V
 Verifique que la inicialización del agente incluya el establecimiento de identidad criptográfica con credenciales respaldadas por hardware y registros de auditoría inmutables de inicio que contengan ID del agente, marca de tiempo, hash de configuración y parámetros de inicialización.
 #9.11.2    Level: 2    Role: D/V
 Verifique que las transiciones de estado del agente estén firmadas criptográficamente, tengan marca de tiempo y se registren con el contexto completo, incluyendo eventos desencadenantes, hash del estado anterior, hash del nuevo estado y validaciones de seguridad realizadas.
 #9.11.3    Level: 2    Role: D/V
 Verifique que los procedimientos de apagado del agente incluyan el borrado seguro de la memoria mediante borrado criptográfico o sobreescritura múltiple, la revocación de credenciales con notificación a la autoridad certificadora, y la generación de certificados de terminación a prueba de manipulaciones.
 #9.11.4    Level: 3    Role: D/V
 Verifique que los mecanismos de recuperación de agentes validen la integridad del estado utilizando sumas de verificación criptográficas (SHA-256 como mínimo) y retrocedan a estados conocidos y buenos cuando se detecte corrupción, con alertas automatizadas y requisitos de aprobación manual.
 #9.11.5    Level: 3    Role: D/V
 Verifique que los mecanismos de persistencia del agente cifren los datos de estado sensibles con claves AES-256 por agente e implementen la rotación segura de claves en horarios configurables (máximo 90 días) con despliegue sin tiempo de inactividad.

---

### 9.12 Marco de Seguridad para la Integración de Herramientas

Controles de seguridad para la carga dinámica de herramientas, ejecución y validación de resultados con procesos definidos de evaluación de riesgos y aprobación.

 #9.12.1    Level: 1    Role: D/V
 Verifique que los descriptores de herramientas incluyan metadatos de seguridad que especifiquen los privilegios requeridos (lectura/escritura/ejecución), los niveles de riesgo (bajo/medio/alto), los límites de recursos (CPU, memoria, red) y los requisitos de validación documentados en los manifiestos de la herramienta.
 #9.12.2    Level: 1    Role: D/V
 Verifique que los resultados de la ejecución de la herramienta se validen contra los esquemas esperados (Esquema JSON, Esquema XML) y las políticas de seguridad (saneamiento de salida, clasificación de datos) antes de la integración, incluyendo límites de tiempo de espera y procedimientos de manejo de errores.
 #9.12.3    Level: 2    Role: D/V
 Verifique que los registros de interacción con la herramienta incluyan un contexto de seguridad detallado, que abarque el uso de privilegios, los patrones de acceso a datos, el tiempo de ejecución, el consumo de recursos y los códigos de retorno, con un registro estructurado para la integración con SIEM.
 #9.12.4    Level: 2    Role: D/V
 Verifique que los mecanismos de carga dinámica de herramientas validen las firmas digitales utilizando la infraestructura PKI e implementen protocolos de carga seguros con aislamiento en sandbox y verificación de permisos antes de la ejecución.
 #9.12.5    Level: 3    Role: D/V
 Verifique que las evaluaciones de seguridad de herramientas se activen automáticamente para nuevas versiones con puertas de aprobación obligatorias que incluyan análisis estático, pruebas dinámicas y revisión del equipo de seguridad con criterios de aprobación documentados y requisitos de SLA.

---

#### Referencias

MITRE ATLAS tactics ML09
Circuit-breaker research for AI agents — Zou et al., 2024
Trend Micro analysis of sandbox escapes in AI agents — Park, 2025
Auth0 guidance on human-in-the-loop authorization for agents — Martinez, 2025
Medium deep-dive on MCP & A2A protocol hijacking — ForAISec, 2025
Rapid7 fundamentals on spoofing attack prevention — 2024
Imperial College verification of swarm systems — Lomuscio et al.
NIST AI Risk Management Framework 1.0, 2023
WIRED security briefing on encryption best practices, 2024
OWASP Top 10 for LLM Applications, 2025
Comprehensive Vulnerability Analysis is Necessary for Trustworthy LLM-MAS
[How Is LLM Reasoning Distracted by Irrelevant Context?
An Analysis Using a Controlled Benchmark](https://www.arxiv.org/pdf/2505.18761)
Large Language Model Sentinel: LLM Agent for Adversarial Purification
Securing Agentic AI: A Comprehensive Threat Model and Mitigation Framework for Generative AI Agents

## 10 Robustez Adversarial y Defensa de Privacidad

### Objetivo de Control

Garantizar que los modelos de IA permanezcan confiables, preserven la privacidad y sean resistentes al abuso al enfrentar ataques de evasión, inferencia, extracción o envenenamiento.

---

### 10.1 Alineación y Seguridad del Modelo

Protéjase contra salidas dañinas o que violen políticas.

 #10.1.1    Level: 1    Role: D/V
 Verifique que un conjunto de pruebas de alineación (prompts de red-team, sondas de jailbreak, contenido no permitido) esté controlado por versiones y se ejecute en cada lanzamiento del modelo.
 #10.1.2    Level: 1    Role: D
 Verifique que se apliquen las barreras de rechazo y de finalización segura.
 #10.1.3    Level: 2    Role: D/V
 Verifique que un evaluador automatizado mida la tasa de contenido dañino y marque regresiones que superen un umbral establecido.
 #10.1.4    Level: 2    Role: D
 Verifique que el entrenamiento contra jailbreak esté documentado y sea reproducible.
 #10.1.5    Level: 3    Role: V
 Verifique que las pruebas formales de cumplimiento de políticas o la monitorización certificada cubran dominios críticos.

---

### 10.2 Fortalecimiento contra ejemplos adversariales

Incrementar la resiliencia frente a entradas manipuladas. El entrenamiento adversarial robusto y la puntuación de referencia son las mejores prácticas actuales.

 #10.2.1    Level: 1    Role: D
 Verifique que los repositorios del proyecto incluyan configuraciones de entrenamiento adversarial con semillas reproducibles.
 #10.2.2    Level: 2    Role: D/V
 Verifique que la detección de ejemplos adversariales genere alertas de bloqueo en las líneas de producción.
 #10.2.4    Level: 3    Role: V
 Verifique que las pruebas de robustez certificada o los certificados de límites por intervalos cubran al menos las principales clases críticas.
 #10.2.5    Level: 3    Role: V
 Verifique que las pruebas de regresión utilicen ataques adaptativos para confirmar que no hay pérdida de robustez medible.

---

### 10.3 Mitigación de la Inferencia de Membresía

Limitar la capacidad de decidir si un registro formaba parte de los datos de entrenamiento. La privacidad diferencial y el enmascaramiento de la puntuación de confianza siguen siendo las defensas conocidas más efectivas.

 #10.3.1    Level: 1    Role: D
 Verifique que la regularización de entropía por consulta o el escalado de temperatura reducen las predicciones excesivamente confiadas.
 #10.3.2    Level: 2    Role: D
 Verifique que el entrenamiento utilice optimización con privacidad diferencial acotada por ε para conjuntos de datos sensibles.
 #10.3.3    Level: 2    Role: V
 Verifique que las simulaciones de ataque (modelo sombra o caja negra) muestren un AUC de ataque ≤ 0.60 en los datos retenidos.

---

### 10.4 Resistencia a la inversión de modelo

Prevenir la reconstrucción de atributos privados. Encuestas recientes enfatizan la truncación de salida y las garantías de privacidad diferencial (DP) como defensas prácticas.

 #10.4.1    Level: 1    Role: D
 Verifique que los atributos sensibles nunca se expongan directamente; cuando sea necesario, utilice agrupaciones o transformaciones unidireccionales.
 #10.4.2    Level: 1    Role: D/V
 Verifique que los límites de tasa de consulta restrinjan las consultas adaptativas repetidas del mismo principal.
 #10.4.3    Level: 2    Role: D
 Verifique que el modelo esté entrenado con ruido que preserva la privacidad.

---

### 10.5 Defensa contra la extracción de modelos

Detectar y disuadir la clonación no autorizada. Se recomienda el uso de marcas de agua y el análisis de patrones de consulta.

 #10.5.1    Level: 1    Role: D
 Verifique que las pasarelas de inferencia apliquen límites de velocidad globales y por clave API ajustados al umbral de memorización del modelo.
 #10.5.2    Level: 2    Role: D/V
 Verifique que las estadísticas de entropía de consulta y pluralidad de entrada alimenten un detector de extracción automatizado.
 #10.5.3    Level: 2    Role: V
 Verifique que las marcas de agua frágiles o probabilísticas puedan demostrarse con p < 0.01 en ≤ 1 000 consultas contra un clon sospechoso.
 #10.5.4    Level: 3    Role: D
 Verifique que las claves de marca de agua y los conjuntos de activadores estén almacenados en un módulo de seguridad de hardware y se roten anualmente.
 #10.5.5    Level: 3    Role: V
 Verifique que los eventos de alerta por extracción incluyan las consultas ofensivas y estén integrados con los libros de jugadas de respuesta a incidentes.

---

### 10.6 Detección de Datos Envenenados en Tiempo de Inferencia

Identificar y neutralizar entradas con puertas traseras o envenenadas.

 #10.6.1    Level: 1    Role: D
 Verifique que las entradas pasen por un detector de anomalías (por ejemplo, STRIP, puntuación de consistencia) antes de la inferencia del modelo.
 #10.6.2    Level: 1    Role: V
 Verifique que los umbrales del detector estén ajustados en conjuntos de validación limpios/envenenados para lograr menos del 5% de falsos positivos.
 #10.6.3    Level: 2    Role: D
 Verifique que las entradas marcadas como contaminadas activan el bloqueo suave y los flujos de trabajo de revisión humana.
 #10.6.4    Level: 2    Role: V
 Verifique que los detectores sean sometidos a pruebas de resistencia con ataques de puerta trasera adaptativos y sin disparadores.
 #10.6.5    Level: 3    Role: D
 Verifique que las métricas de eficacia de detección se registren y se reevalúen periódicamente con inteligencia de amenazas actualizada.

---

### 10.7 Adaptación Dinámica de Políticas de Seguridad

Actualizaciones de políticas de seguridad en tiempo real basadas en inteligencia de amenazas y análisis de comportamiento.

 #10.7.1    Level: 1    Role: D/V
 Verifique que las políticas de seguridad puedan actualizarse dinámicamente sin reiniciar el agente, manteniendo la integridad de la versión de la política.
 #10.7.2    Level: 2    Role: D/V
 Verifique que las actualizaciones de políticas estén firmadas criptográficamente por el personal de seguridad autorizado y validadas antes de su aplicación.
 #10.7.3    Level: 2    Role: D/V
 Verifique que los cambios dinámicos en la política se registren con un historial completo de auditoría que incluya justificación, cadenas de aprobación y procedimientos de reversión.
 #10.7.4    Level: 3    Role: D/V
 Verifique que los mecanismos de seguridad adaptativa ajusten la sensibilidad de detección de amenazas según el contexto de riesgo y los patrones de comportamiento.
 #10.7.5    Level: 3    Role: D/V
 Verifique que las decisiones de adaptación de políticas sean explicables e incluyan rastros de evidencia para la revisión del equipo de seguridad.

---

### 10.8 Análisis de Seguridad Basado en Reflexión

Validación de seguridad mediante autorreflexión del agente y análisis metacognitivo.

 #10.8.1    Level: 1    Role: D/V
 Verifique que los mecanismos de reflexión del agente incluyan una autoevaluación centrada en la seguridad de las decisiones y acciones.
 #10.8.2    Level: 2    Role: D/V
 Verifique que las salidas de reflexión estén validadas para prevenir la manipulación de los mecanismos de autoevaluación por entradas adversarias.
 #10.8.3    Level: 2    Role: D/V
 Verifique que el análisis de seguridad meta-cognitivo identifique posibles sesgos, manipulaciones o compromisos en los procesos de razonamiento del agente.
 #10.8.4    Level: 3    Role: D/V
 Verifique que las advertencias de seguridad basadas en reflexión desencadenen una supervisión mejorada y posibles flujos de trabajo de intervención humana.
 #10.8.5    Level: 3    Role: D/V
 Verifique que el aprendizaje continuo a partir de reflexiones de seguridad mejora la detección de amenazas sin degradar la funcionalidad legítima.

---

### 10.9 Seguridad de Evolución y Auto-Mejora

Controles de seguridad para sistemas agentes capaces de auto-modificación y evolución.

 #10.9.1    Level: 1    Role: D/V
 Verifique que las capacidades de auto-modificación estén restringidas a áreas seguras designadas con límites de verificación formal.
 #10.9.2    Level: 2    Role: D/V
 Verifique que las propuestas de evolución pasen por una evaluación de impacto en seguridad antes de su implementación.
 #10.9.3    Level: 2    Role: D/V
 Verifique que los mecanismos de auto-mejora incluyan capacidades de reversión con verificación de integridad.
 #10.9.4    Level: 3    Role: D/V
 Verifique que la seguridad del meta-aprendizaje previene la manipulación adversarial de los algoritmos de mejora.
 #10.9.5    Level: 3    Role: D/V
 Verificar que la auto-mejora recursiva esté limitada por restricciones formales de seguridad con pruebas matemáticas de convergencia.

---

#### Referencias

MITRE ATLAS adversary tactics for ML
NIST AI Risk Management Framework 1.0, 2023
OWASP Top 10 for LLM Applications, 2025
Adversarial Training: A Survey — Zhao et al., 2024
RobustBench adversarial-robustness benchmark
Membership-Inference & Model-Inversion Risk Survey, 2025
PURIFIER: Confidence-Score Defense against MI Attacks — AAAI 2023
Model-Inversion Attacks & Defenses Survey — AI Review, 2025
Comprehensive Defense Framework Against Model Extraction — IEEE TDSC 2024
Fragile Model Watermarking Survey — 2025
Data Poisoning in Deep Learning: A Survey — Zhao et al., 2025
BDetCLIP: Multimodal Prompting Backdoor Detection — Niu et al., 2024

## 11 Protección de la Privacidad y Gestión de Datos Personales

### Objetivo de Control

Mantener rigurosas garantías de privacidad a lo largo de todo el ciclo de vida de la IA—recolección, entrenamiento, inferencia y respuesta a incidentes—de modo que los datos personales se procesen únicamente con un consentimiento claro, alcance mínimo necesario, borrado comprobable y garantías formales de privacidad.

---

### 11.1 Anonimización y Minimización de Datos

 #11.1.1    Level: 1    Role: D/V
 Verifique que los identificadores directos y cuasi-identificadores sean eliminados o hasheados.
 #11.1.2    Level: 2    Role: D/V
 Verificar que las auditorías automatizadas midan la k-anonimidad/l-diversidad y alerten cuando los umbrales caigan por debajo de la política.
 #11.1.3    Level: 2    Role: V
 Verifique que los informes de importancia de características del modelo demuestren que no hay filtración de identificadores más allá de ε = 0.01 de información mutua.
 #11.1.4    Level: 3    Role: V
 Verifique que las pruebas formales o la certificación de datos sintéticos muestran un riesgo de reidentificación ≤ 0.05 incluso bajo ataques de enlace.

---

### 11.2 Derecho al olvido y aplicación de la eliminación

 #11.2.1    Level: 1    Role: D/V
 Verifique que las solicitudes de eliminación de datos de sujetos se propaguen a conjuntos de datos sin procesar, puntos de control, incrustaciones, registros y copias de seguridad dentro de acuerdos de nivel de servicio de menos de 30 días.
 #11.2.2    Level: 2    Role: D
 Verifique que las rutinas de "desaprendizaje automático" reentrenen físicamente o aproximen la eliminación usando algoritmos de desaprendizaje certificados.
 #11.2.3    Level: 2    Role: V
 Verifique que la evaluación del modelo sombra demuestra que los registros olvidados influyen en menos del 1% de las salidas después del desaprendizaje.
 #11.2.4    Level: 3    Role: V
 Verifique que los eventos de eliminación se registren de manera inmutable y sean auditables para los reguladores.

---

### 11.3 Salvaguardas de Privacidad Diferencial

 #11.3.1    Level: 2    Role: D/V
 Verifique que los paneles de control de contabilización de pérdida de privacidad alerten cuando el ε acumulativo supere los umbrales de la política.
 #11.3.2    Level: 2    Role: V
 Verifique que las auditorías de privacidad de caja negra estimen ε̂ dentro del 10 % del valor declarado.
 #11.3.3    Level: 3    Role: V
 Verifique que las pruebas formales cubran todos los ajustes finos y embeddings posteriores al entrenamiento.

---

### 11.4 Protección contra la Limitación del Propósito y la Expansión del Alcance

 #11.4.1    Level: 1    Role: D
 Verifique que cada conjunto de datos y punto de control del modelo lleve una etiqueta de propósito legible por máquina alineada con el consentimiento original.
 #11.4.2    Level: 1    Role: D/V
 Verifique que los monitores en tiempo de ejecución detecten consultas inconsistentes con el propósito declarado y activen una negativa suave.
 #11.4.3    Level: 3    Role: D
 Verifique que las puertas de política-como-código bloqueen el redepliegue de modelos a nuevos dominios sin revisión de DPIA.
 #11.4.4    Level: 3    Role: V
 Verifique que las pruebas formales de trazabilidad demuestren que cada ciclo de vida de los datos personales permanece dentro del alcance consentido.

---

### 11.5 Gestión del Consentimiento y Seguimiento de la Base Legal

 #11.5.1    Level: 1    Role: D/V
 Verifique que una Plataforma de Gestión de Consentimiento (CMP) registre el estado de aceptación, el propósito y el período de retención por sujeto de datos.
 #11.5.2    Level: 2    Role: D
 Verifique que las API expongan tokens de consentimiento; los modelos deben validar el alcance del token antes de la inferencia.
 #11.5.3    Level: 2    Role: D/V
 Verifique que el consentimiento denegado o retirado detenga las tuberías de procesamiento dentro de las 24 horas.

---

### 11.6 Aprendizaje Federado con Controles de Privacidad

 #11.6.1    Level: 1    Role: D
 Verifique que las actualizaciones del cliente utilicen la adición de ruido de privacidad diferencial local antes de la agregación.
 #11.6.2    Level: 2    Role: D/V
 Verifique que las métricas de entrenamiento sean diferencialmente privadas y nunca revelen la pérdida de un solo cliente.
 #11.6.3    Level: 2    Role: V
 Verifique que la agregación resistente a envenenamiento (por ejemplo, Krum/Media Recortada) esté habilitada.
 #11.6.4    Level: 3    Role: V
 Verifique que las demostraciones formales demuestren un presupuesto total de ε con una pérdida de utilidad menor a 5.

---

#### Referencias

GDPR & AI Compliance Best Practices
EU Parliament Study on GDPR & AI, 2020
ISO 31700-1:2023 — Privacy by Design for Consumer Products
NIST Privacy Framework 1.1 (2025 Draft)
Machine Unlearning: Right-to-Be-Forgotten Techniques
A Survey of Machine Unlearning, 2024
Auditing DP-SGD — ArXiv 2024
DP-SGD Explained — PyTorch Blog
Purpose-Limitation for AI — IJLIT 2025
Data-Protection Considerations for AI — URM Consulting
Top Consent-Management Platforms, 2025
Secure Aggregation in DP Federated Learning — ArXiv 2024

## C12 Monitoreo, Registro y Detección de Anomalías

### Objetivo de Control

Esta sección proporciona requisitos para ofrecer visibilidad en tiempo real y forense sobre lo que el modelo y otros componentes de IA ven, hacen y devuelven, de manera que las amenazas puedan ser detectadas, clasificadas y analizadas para aprendizaje.

### C12.1 Registro de Solicitudes y Respuestas

 #12.1.1    Level: 1    Role: D/V
 Verifique que todas las solicitudes de usuario y las respuestas del modelo estén registradas con los metadatos apropiados (por ejemplo, marca de tiempo, ID de usuario, ID de sesión, versión del modelo).
 #12.1.2    Level: 1    Role: D/V
 Verifique que los registros se almacenen en repositorios seguros con control de acceso, con políticas de retención apropiadas y procedimientos de respaldo.
 #12.1.3    Level: 1    Role: D/V
 Verifique que los sistemas de almacenamiento de registros implementen cifrado en reposo y en tránsito para proteger la información sensible contenida en los registros.
 #12.1.4    Level: 1    Role: D/V
 Verifique que los datos sensibles en las indicaciones y salidas se redacten o enmascaren automáticamente antes de registrarlos, con reglas de redacción configurables para información de identificación personal (PII), credenciales e información propietaria.
 #12.1.5    Level: 2    Role: D/V
 Verifique que las decisiones de política y las acciones de filtrado de seguridad estén registradas con suficiente detalle para permitir la auditoría y la depuración de los sistemas de moderación de contenido.
 #12.1.6    Level: 2    Role: D/V
 Verifique que la integridad del registro esté protegida mediante, por ejemplo, firmas criptográficas o almacenamiento de solo escritura.

---

### C12.2 Detección de Abusos y Alertas

 #12.2.1    Level: 1    Role: D/V
 Verifique que el sistema detecte y alerte sobre patrones de jailbreak conocidos, intentos de inyección de indicaciones y entradas adversarias utilizando detección basada en firmas.
 #12.2.2    Level: 1    Role: D/V
 Verifique que el sistema se integre con las plataformas existentes de Gestión de Información y Eventos de Seguridad (SIEM) utilizando formatos y protocolos de registro estándar.
 #12.2.3    Level: 2    Role: D/V
 Verifique que los eventos de seguridad enriquecidos incluyan contexto específico de IA, como identificadores de modelos, puntajes de confianza y decisiones del filtro de seguridad.
 #12.2.4    Level: 2    Role: D/V
 Verifique que la detección de anomalías conductuales identifique patrones de conversación inusuales, intentos excesivos de reintento o comportamientos sistemáticos de sondeo.
 #12.2.5    Level: 2    Role: D/V
 Verifique que los mecanismos de alertas en tiempo real notifiquen a los equipos de seguridad cuando se detecten posibles violaciones de políticas o intentos de ataque.
 #12.2.6    Level: 2    Role: D/V
 Verifique que se incluyen reglas personalizadas para detectar patrones de amenaza específicos de IA, incluidos intentos coordinados de jailbreak, campañas de inyección de comandos y ataques de extracción de modelos.
 #12.2.7    Level: 3    Role: D/V
 Verifique que los flujos de trabajo automatizados de respuesta a incidentes puedan aislar modelos comprometidos, bloquear usuarios maliciosos y escalar eventos críticos de seguridad.

---

### C12.3 Detección de Deriva del Modelo

 #12.3.1    Level: 1    Role: D/V
 Verifique que el sistema rastree métricas básicas de rendimiento como precisión, puntuaciones de confianza, latencia y tasas de error a lo largo de las versiones del modelo y períodos de tiempo.
 #12.3.2    Level: 2    Role: D/V
 Verifique que las alertas automáticas se activen cuando las métricas de rendimiento superen los umbrales de degradación predefinidos o se desvíen significativamente de las líneas base.
 #12.3.3    Level: 2    Role: D/V
 Verifique que los monitores de detección de alucinaciones identifiquen y señalen los casos en que las salidas del modelo contienen información factualmente incorrecta, inconsistente o fabricada.

---

### C12.4 Telemetría de Rendimiento y Comportamiento

 #12.4.1    Level: 1    Role: D/V
 Verifique que las métricas operativas, incluyendo la latencia de las solicitudes, el consumo de tokens, el uso de memoria y el rendimiento, se recopilen y supervisen de manera continua.
 #12.4.2    Level: 1    Role: D/V
 Verifique que las tasas de éxito y fracaso se registren con la categorización de los tipos de errores y sus causas fundamentales.
 #12.4.3    Level: 2    Role: D/V
 Verifique que la monitorización de la utilización de recursos incluya el uso de GPU/CPU, el consumo de memoria y los requisitos de almacenamiento, con alertas en caso de superar los umbrales establecidos.

---

### C12.5 Planificación y Ejecución de la Respuesta a Incidentes de IA

 #12.5.1    Level: 1    Role: D/V
 Verifique que los planes de respuesta a incidentes aborden específicamente eventos de seguridad relacionados con la IA, incluyendo compromiso del modelo, envenenamiento de datos y ataques adversarios.
 #12.5.2    Level: 2    Role: D/V
 Verifique que los equipos de respuesta a incidentes tengan acceso a herramientas forenses específicas de IA y experiencia para investigar el comportamiento del modelo y los vectores de ataque.
 #12.5.3    Level: 3    Role: D/V
 Verifique que el análisis posterior al incidente incluya consideraciones para el reentrenamiento del modelo, actualizaciones de los filtros de seguridad y la integración de las lecciones aprendidas en los controles de seguridad.

---

### C12.5 Detección de la Degradación del Rendimiento de la IA

Monitorear y detectar la degradación en el rendimiento y la calidad del modelo de IA a lo largo del tiempo.

 #12.5.1    Level: 1    Role: D/V
 Verifique que la precisión del modelo, la exactitud, el recall y las puntuaciones F1 se monitoreen continuamente y se comparen con los umbrales base.
 #12.5.2    Level: 1    Role: D/V
 Verifique que la detección de deriva de datos monitorea cambios en la distribución de entrada que pueden afectar el rendimiento del modelo.
 #12.5.3    Level: 2    Role: D/V
 Verifique que la detección de deriva del concepto identifique cambios en la relación entre las entradas y las salidas esperadas.
 #12.5.4    Level: 2    Role: D/V
 Verifique que la degradación del rendimiento desencadene alertas automáticas e inicie los flujos de trabajo de reentrenamiento o reemplazo del modelo.
 #12.5.5    Level: 3    Role: V
 Verifique que el análisis de causa raíz de la degradación correlacione las caídas de rendimiento con cambios en los datos, problemas de infraestructura o factores externos.

---

### C12.6 Visualización de DAG y Seguridad del Flujo de Trabajo

Proteja los sistemas de visualización de flujo de trabajo contra filtraciones de información y ataques de manipulación.

 #12.6.1    Level: 1    Role: D/V
 Verifique que los datos de visualización del DAG estén sanitizados para eliminar información sensible antes del almacenamiento o la transmisión.
 #12.6.2    Level: 1    Role: D/V
 Verifique que los controles de acceso a la visualización del flujo de trabajo aseguren que solo los usuarios autorizados puedan ver las rutas de decisión del agente y los rastros de razonamiento.
 #12.6.3    Level: 2    Role: D/V
 Verifique que la integridad de los datos del DAG esté protegida mediante firmas criptográficas y mecanismos de almacenamiento a prueba de manipulaciones.
 #12.6.4    Level: 2    Role: D/V
 Verifique que los sistemas de visualización de flujos de trabajo implementen validación de entradas para prevenir ataques de inyección mediante datos manipulados de nodos o aristas.
 #12.6.5    Level: 3    Role: D/V
 Verifique que las actualizaciones en tiempo real del DAG estén limitadas en su tasa y validadas para prevenir ataques de denegación de servicio en los sistemas de visualización.

---

### C12.7 Monitoreo Proactivo del Comportamiento de Seguridad

Detección y prevención de amenazas de seguridad mediante el análisis proactivo del comportamiento de agentes.

 #12.7.1    Level: 1    Role: D/V
 Verifique que los comportamientos proactivos del agente estén validados en seguridad antes de su ejecución, integrando una evaluación de riesgos.
 #12.7.2    Level: 2    Role: D/V
 Verifique que los disparadores de iniciativa autónoma incluyan la evaluación del contexto de seguridad y la evaluación del panorama de amenazas.
 #12.7.3    Level: 2    Role: D/V
 Verifique que los patrones de comportamiento proactivo sean analizados para posibles implicaciones de seguridad y consecuencias no deseadas.
 #12.7.4    Level: 3    Role: D/V
 Verifique que las acciones proactivas críticas para la seguridad requieran cadenas de aprobación explícitas con registros de auditoría.
 #12.7.5    Level: 3    Role: D/V
 Verifique que la detección de anomalías comportamentales identifique desviaciones en los patrones de agentes proactivos que puedan indicar una posible comprometida.

---

### Referencias

NIST AI Risk Management Framework 1.0 - Manage 4.1 and 4.3
ISO/IEC 42001:2023 — AI Management Systems Requirements - Annex B 6.2.6
EU AI Act — Article 12, 13, 16 and 19 on Logging and Record-keeping

## C13 Supervisión Humana, Responsabilidad y Gobernanza

### Objetivo de Control

Este capítulo proporciona requisitos para mantener la supervisión humana y cadenas claras de responsabilidad en los sistemas de IA, garantizando la explicabilidad, transparencia y gestión ética a lo largo del ciclo de vida de la IA.

---

### C13.1 Mecanismos de Interruptor de Corte y Anulación

Proporcione rutas de apagado o reversión cuando se observe un comportamiento inseguro del sistema de IA.

 #13.1.1    Level: 1    Role: D/V
 Verifique que exista un mecanismo manual de desconexión para detener inmediatamente la inferencia y los resultados del modelo de IA.
 #13.1.2    Level: 1    Role: D
 Verifique que los controles de anulación sean accesibles únicamente para el personal autorizado.
 #13.1.3    Level: 3    Role: D/V
 Verifique que los procedimientos de reversión puedan restaurar versiones anteriores del modelo o operaciones en modo seguro.
 #13.1.4    Level: 3    Role: V
 Verifique que los mecanismos de anulación se prueben regularmente.

---

### C13.2 Puntos de control de decisión con intervención humana

Requerir aprobaciones humanas cuando las apuestas superen los umbrales de riesgo predefinidos.

 #13.2.1    Level: 1    Role: D/V
 Verifique que las decisiones de IA de alto riesgo requieran aprobación humana explícita antes de su ejecución.
 #13.2.2    Level: 1    Role: D
 Verifique que los umbrales de riesgo estén claramente definidos y que activen automáticamente los flujos de trabajo de revisión humana.
 #13.2.3    Level: 2    Role: D
 Verifique que las decisiones sensibles al tiempo tengan procedimientos de respaldo cuando no se pueda obtener la aprobación humana dentro de los plazos requeridos.
 #13.2.4    Level: 3    Role: D/V
 Verifique que los procedimientos de escalamiento definan niveles claros de autoridad para diferentes tipos de decisiones o categorías de riesgo, si corresponde.

---

### C13.3 Cadena de Responsabilidad y Auditabilidad

Registrar las acciones del operador y las decisiones del modelo.

 #13.3.1    Level: 1    Role: D/V
 Verifique que todas las decisiones del sistema de IA y las intervenciones humanas estén registradas con marcas de tiempo, identidades de usuario y la justificación de la decisión.
 #13.3.2    Level: 2    Role: D
 Verifique que los registros de auditoría no puedan ser manipulados e incluyan mecanismos de verificación de integridad.

---

### C13.4 Técnicas de IA Explicable

Importancia de características superficiales, contra-factuales y explicaciones locales.

 #13.4.1    Level: 1    Role: D/V
 Verificar que los sistemas de IA proporcionen explicaciones básicas de sus decisiones en un formato comprensible para los humanos.
 #13.4.2    Level: 2    Role: V
 Verifique que la calidad de la explicación sea validada mediante estudios de evaluación humana y métricas.
 #13.4.3    Level: 3    Role: D/V
 Verifique que las puntuaciones de importancia de características o los métodos de atribución (SHAP, LIME, etc.) estén disponibles para decisiones críticas.
 #13.4.4    Level: 3    Role: V
 Verifique que las explicaciones contrafactuales muestren cómo se podrían modificar las entradas para cambiar los resultados, si es aplicable al caso de uso y dominio.

---

### C13.5 Tarjetas de modelo y divulgaciones de uso

Mantenga las tarjetas de modelo para el uso previsto, métricas de rendimiento y consideraciones éticas.

 #13.5.1    Level: 1    Role: D
 Verifique que las tarjetas del modelo documenten los casos de uso previstos, las limitaciones y los modos de falla conocidos.
 #13.5.2    Level: 1    Role: D/V
 Verifique que se divulguen las métricas de rendimiento en los diferentes casos de uso aplicables.
 #13.5.3    Level: 2    Role: D
 Verifique que las consideraciones éticas, evaluaciones de sesgo, evaluaciones de equidad, características de los datos de entrenamiento y limitaciones conocidas de los datos de entrenamiento estén documentadas y actualizadas regularmente.
 #13.5.4    Level: 2    Role: D/V
 Verifique que las tarjetas de modelo estén controladas por versiones y se mantengan durante todo el ciclo de vida del modelo con seguimiento de cambios.

---

### C13.6 Cuantificación de Incertidumbre

Propagar puntajes de confianza o medidas de entropía en las respuestas.

 #13.6.1    Level: 1    Role: D
 Verifique que los sistemas de IA proporcionen puntuaciones de confianza o medidas de incertidumbre con sus resultados.
 #13.6.2    Level: 2    Role: D/V
 Verifique que los umbrales de incertidumbre activen una revisión humana adicional o vías alternativas de decisión.
 #13.6.3    Level: 2    Role: V
 Verifique que los métodos de cuantificación de la incertidumbre estén calibrados y validados frente a datos de referencia.
 #13.6.4    Level: 3    Role: D/V
 Verifique que la propagación de la incertidumbre se mantenga a lo largo de los flujos de trabajo de IA en múltiples pasos.

---

### C13.7 Informes de Transparencia para Usuarios

Proporcionar divulgaciones periódicas sobre incidentes, desviaciones y uso de datos.

 #13.7.1    Level: 1    Role: D/V
 Verifique que las políticas de uso de datos y las prácticas de gestión del consentimiento del usuario se comuniquen claramente a los interesados.
 #13.7.2    Level: 2    Role: D/V
 Verifique que se realicen evaluaciones de impacto de IA y que los resultados se incluyan en los informes.
 #13.7.3    Level: 2    Role: D/V
 Verifique que los informes de transparencia publicados regularmente revelen incidentes de IA y métricas operativas con un detalle razonable.

#### Referencias

EU Artificial Intelligence Act — Regulation (EU) 2024/1689 (Official Journal, 12 July 2024)
ISO/IEC 23894:2023 — Artificial Intelligence — Guidance on Risk Management
ISO/IEC 42001:2023 — AI Management Systems Requirements
NIST AI Risk Management Framework 1.0
NIST SP 800-53 Revision 5 — Security and Privacy Controls
A Unified Approach to Interpreting Model Predictions (SHAP, ICML 2017)
Model Cards for Model Reporting (Mitchell et al., 2018)
Dropout as a Bayesian Approximation: Representing Model Uncertainty in Deep Learning (Gal & Ghahramani, 2016)
ISO/IEC 24029-2:2023 — Robustness of Neural Networks — Methodology for Formal Methods
IEEE 7001-2021 — Transparency of Autonomous Systems
GDPR — Article 5 "Transparency Principle" (Regulation (EU) 2016/679)
Human Oversight under Article 14 of the EU AI Act (Fink, 2025)

## Apéndice A: Glosario

Este glosario integral proporciona definiciones de términos clave de IA, ML y seguridad utilizados en todo el AISVS para garantizar claridad y un entendimiento común.
​
Ejemplo adversarial: Una entrada deliberadamente diseñada para causar que un modelo de IA cometa un error, a menudo añadiendo perturbaciones sutiles imperceptibles para los humanos.
​
Robustez adversarial: La robustez adversarial en IA se refiere a la capacidad de un modelo para mantener su rendimiento y resistir ser engañado o manipulado por entradas maliciosas diseñadas intencionalmente para causar errores.
​
Agente: Los agentes de IA son sistemas de software que utilizan inteligencia artificial para perseguir objetivos y completar tareas en nombre de los usuarios. Demuestran razonamiento, planificación y memoria, y tienen un nivel de autonomía para tomar decisiones, aprender y adaptarse.
​
IA Agente: sistemas de IA que pueden operar con cierto grado de autonomía para alcanzar objetivos, a menudo tomando decisiones y realizando acciones sin intervención humana directa.
​
Control de acceso basado en atributos (ABAC): un paradigma de control de acceso donde las decisiones de autorización se basan en atributos del usuario, recurso, acción y entorno, evaluados en tiempo de consulta.
​
Ataque de puerta trasera: un tipo de ataque de envenenamiento de datos donde el modelo se entrena para responder de una manera específica a ciertos desencadenantes mientras se comporta normalmente en otros casos.
​
Sesgo: Errores sistemáticos en las salidas de modelos de IA que pueden conducir a resultados injustos o discriminatorios para ciertos grupos o en contextos específicos.
​
Explotación de sesgos: Una técnica de ataque que aprovecha sesgos conocidos en modelos de IA para manipular resultados o salidas.
​
Cedar: El lenguaje y motor de políticas de Amazon para permisos detallados utilizado en la implementación de ABAC para sistemas de IA.
​
Cadena de pensamiento: Una técnica para mejorar el razonamiento en modelos de lenguaje mediante la generación de pasos intermedios de razonamiento antes de producir una respuesta final.
​
Disyuntores: Mecanismos que detienen automáticamente las operaciones del sistema de IA cuando se superan ciertos umbrales de riesgo.
​
Fuga de datos: exposición no intencionada de información sensible a través de las salidas o el comportamiento del modelo de IA.
​
Envenenamiento de datos: La corrupción deliberada de los datos de entrenamiento para comprometer la integridad del modelo, a menudo para instalar puertas traseras o degradar el rendimiento.
​
Privacidad diferencial: La privacidad diferencial es un marco matemáticamente riguroso para divulgar información estadística sobre conjuntos de datos mientras se protege la privacidad de los sujetos individuales. Permite a un poseedor de datos compartir patrones agregados del grupo mientras limita la información filtrada sobre individuos específicos.
​
Embeddings: Representaciones vectoriales densas de datos (texto, imágenes, etc.) que capturan el significado semántico en un espacio de alta dimensión.
​
Explicabilidad: la explicabilidad en IA es la capacidad de un sistema de IA para proporcionar razones comprensibles por humanos para sus decisiones y predicciones, ofreciendo una visión de su funcionamiento interno.
​
IA Explicable (XAI): Sistemas de IA diseñados para proporcionar explicaciones comprensibles por humanos sobre sus decisiones y comportamientos mediante diversas técnicas y marcos.
​
Aprendizaje Federado: Un enfoque de aprendizaje automático donde los modelos se entrenan en múltiples dispositivos descentralizados que contienen muestras de datos locales, sin intercambiar los datos en sí.
​
Guardarraíles: Restricciones implementadas para evitar que los sistemas de IA generen resultados dañinos, sesgados o indeseables.
​
Alucinación – Una alucinación de IA se refiere a un fenómeno donde un modelo de IA genera información incorrecta o engañosa que no se basa en sus datos de entrenamiento ni en la realidad factual.
​
Humano en el Bucle (HITL): Sistemas diseñados para requerir supervisión, verificación o intervención humana en puntos críticos de decisión.
​
Infraestructura como Código (IaC): Gestión y aprovisionamiento de infraestructura mediante código en lugar de procesos manuales, permitiendo el escaneo de seguridad y despliegues consistentes.
​
Jailbreak: Técnicas utilizadas para eludir los mecanismos de seguridad en los sistemas de IA, especialmente en los modelos de lenguaje grande, para producir contenido prohibido.
​
Mínimos privilegios: El principio de seguridad que consiste en otorgar solo los derechos de acceso mínimos necesarios para usuarios y procesos.
​
LIME (Explicaciones Locales Interpretable e Independientes del Modelo): Una técnica para explicar las predicciones de cualquier clasificador de aprendizaje automático aproximándolo localmente con un modelo interpretable.
​
Ataque de inferencia de membresía: un ataque que tiene como objetivo determinar si un punto de datos específico fue utilizado para entrenar un modelo de aprendizaje automático.
​
MITRE ATLAS: Paisaje de amenazas adversariales para sistemas de inteligencia artificial; una base de conocimiento de tácticas y técnicas adversariales contra sistemas de IA.
​
Tarjeta de Modelo – Una tarjeta de modelo es un documento que proporciona información estandarizada sobre el rendimiento, las limitaciones, los usos previstos y las consideraciones éticas de un modelo de IA para promover la transparencia y el desarrollo responsable de la IA.
​
Extracción de Modelo: Un ataque donde un adversario consulta repetidamente un modelo objetivo para crear una copia funcionalmente similar sin autorización.
​
Inversión de modelo: un ataque que intenta reconstruir los datos de entrenamiento analizando las salidas del modelo.
​
Gestión del Ciclo de Vida del Modelo – La Gestión del Ciclo de Vida del Modelo de IA es el proceso de supervisar todas las etapas de la existencia de un modelo de IA, incluyendo su diseño, desarrollo, despliegue, monitoreo, mantenimiento y eventual retiro, para asegurar que permanezca efectivo y alineado con los objetivos.
​
Envenenamiento del modelo: Introducción de vulnerabilidades o puertas traseras directamente en un modelo durante el proceso de entrenamiento.
​
Robo/Robo de Modelo: Extraer una copia o aproximación de un modelo propietario mediante consultas repetidas.
​
Sistema Multiagente: un sistema compuesto por múltiples agentes de IA que interactúan entre sí, cada uno con capacidades y objetivos potencialmente diferentes.
​
OPA (Open Policy Agent): Un motor de políticas de código abierto que permite la aplicación unificada de políticas a lo largo de toda la pila.
​
Aprendizaje Automático Preservador de la Privacidad (PPML): Técnicas y métodos para entrenar y desplegar modelos de ML mientras se protege la privacidad de los datos de entrenamiento.
​
Inyección de indicaciones: Un ataque en el que se insertan instrucciones maliciosas en las entradas para anular el comportamiento previsto de un modelo.
​
RAG (Generación Aumentada por Recuperación): Una técnica que mejora los grandes modelos de lenguaje recuperando información relevante de fuentes externas de conocimiento antes de generar una respuesta.
​
Red-Teaming: La práctica de probar activamente los sistemas de IA simulando ataques adversariales para identificar vulnerabilidades.
​
SBOM (Lista de Materiales de Software): Un registro formal que contiene los detalles y las relaciones de la cadena de suministro de varios componentes utilizados en la construcción de software o modelos de IA.
​
SHAP (Explicaciones Aditivas de Shapley): Un enfoque basado en la teoría de juegos para explicar la salida de cualquier modelo de aprendizaje automático calculando la contribución de cada característica a la predicción.
​
Ataque a la Cadena de Suministro: Comprometer un sistema al atacar elementos menos seguros en su cadena de suministro, como bibliotecas de terceros, conjuntos de datos o modelos preentrenados.
​
Aprendizaje por transferencia: Una técnica en la que un modelo desarrollado para una tarea se reutiliza como punto de partida para un modelo en una segunda tarea.
​
Base de Datos Vectorial: Una base de datos especializada diseñada para almacenar vectores de alta dimensionalidad (incrustaciones) y realizar búsquedas de similitud de manera eficiente.
​
Escaneo de vulnerabilidades: herramientas automatizadas que identifican vulnerabilidades de seguridad conocidas en componentes de software, incluidos los marcos de IA y las dependencias.
​
Marca de agua: Técnicas para incrustar marcadores imperceptibles en contenido generado por IA para rastrear su origen o detectar la generación por IA.
​
Vulnerabilidad de día cero: una vulnerabilidad previamente desconocida que los atacantes pueden explotar antes de que los desarrolladores creen y desplieguen un parche.

## Apéndice B: Referencias

### TODO

## Apéndice C: Gobernanza y Documentación de Seguridad en IA

### Objetivo

Este apéndice proporciona los requisitos fundamentales para establecer estructuras organizativas, políticas y procesos que rijan la seguridad de la IA a lo largo del ciclo de vida del sistema.

---

### Adopción del Marco de Gestión de Riesgos de IA AC.1

Proporcionar un marco formal para identificar, evaluar y mitigar riesgos específicos de la IA a lo largo del ciclo de vida del sistema.

 #AC.1.1    Level: 1    Role: D/V
 Verifique que una metodología de evaluación de riesgos específica para IA esté documentada e implementada.
 #AC.1.2    Level: 2    Role: D
 Verifique que se realicen evaluaciones de riesgos en puntos clave del ciclo de vida de la IA y antes de cambios significativos.
 #AC.1.3    Level: 3    Role: D/V
 Verifique que el marco de gestión de riesgos esté alineado con los estándares establecidos (por ejemplo, NIST AI RMF).

---

### AC.2 Política y Procedimientos de Seguridad en IA

Definir y hacer cumplir los estándares organizacionales para el desarrollo, despliegue y operación seguros de la IA.

 #AC.2.1    Level: 1    Role: D/V
 Verificar que existan políticas de seguridad de IA documentadas.
 #AC.2.2    Level: 2    Role: D
 Verifique que las políticas se revisen y actualicen al menos anualmente y después de cambios significativos en el panorama de amenazas.
 #AC.2.3    Level: 3    Role: D/V
 Verifique que las políticas aborden todas las categorías de AISVS y los requisitos regulatorios aplicables.

---

### AC.3 Roles y Responsabilidades para la Seguridad de la IA

Establecer una responsabilidad clara para la seguridad de la IA en toda la organización.

 #AC.3.1    Level: 1    Role: D/V
 Verifique que los roles y responsabilidades de seguridad de IA estén documentados.
 #AC.3.2    Level: 2    Role: D
 Verifique que las personas responsables posean la experiencia adecuada en seguridad.
 #AC.3.3    Level: 3    Role: D/V
 Verifique que se establezca un comité de ética de IA o una junta de gobernanza para sistemas de IA de alto riesgo.

---

### AC.4 Aplicación de las Directrices Éticas para la IA

Asegurar que los sistemas de IA operen de acuerdo con los principios éticos establecidos.

 #AC.4.1    Level: 1    Role: D/V
 Verifique que existan directrices éticas para el desarrollo y despliegue de la IA.
 #AC.4.2    Level: 2    Role: D
 Verifique que existan mecanismos para detectar y reportar violaciones éticas.
 #AC.4.3    Level: 3    Role: D/V
 Verificar que se realicen revisiones éticas regulares de los sistemas de IA desplegados.

---

### AC.5 Monitoreo de Cumplimiento Regulatorio de IA

Mantener la conciencia y el cumplimiento de las normativas de IA en evolución.

 #AC.5.1    Level: 1    Role: D/V
 Verificar que existan procesos para identificar las normativas aplicables de IA.
 #AC.5.2    Level: 2    Role: D
 Verifique que se evalúe el cumplimiento de todos los requisitos regulatorios.
 #AC.5.3    Level: 3    Role: D/V
 Verificar que los cambios regulatorios desencadenen revisiones y actualizaciones oportunas en los sistemas de IA.

#### Referencias

NIST AI Risk Management Framework 1.0
ISO/IEC 42001:2023 — AI Management Systems Requirements
ISO/IEC 23894:2023 — Artificial Intelligence — Guidance on Risk Management
EU Artificial Intelligence Act — Regulation (EU) 2024/1689
ISO/IEC 24029‑2:2023 — Robustness of Neural Networks — Methodology for Formal Methods

## Apéndice D: Gobernanza y Verificación de Codificación Segura Asistida por IA

### Objetivo

Este capítulo define controles organizacionales básicos para el uso seguro y efectivo de herramientas de codificación asistida por IA durante el desarrollo de software, garantizando la seguridad y la trazabilidad a lo largo del ciclo de vida del desarrollo de software (SDLC).

---

### AD.1 Flujo de trabajo de codificación segura asistida por IA

Integre las herramientas de IA en el ciclo de vida de desarrollo de software seguro (SSDLC) de la organización sin debilitar las barreras de seguridad existentes.

 #AD.1.1    Level: 1    Role: D/V
 Verifique que un flujo de trabajo documentado describa cuándo y cómo las herramientas de IA pueden generar, refactorizar o revisar código.
 #AD.1.2    Level: 2    Role: D
 Verifique que el flujo de trabajo corresponda a cada fase del SSDLC (diseño, implementación, revisión de código, pruebas, despliegue).
 #AD.1.3    Level: 3    Role: D/V
 Verifique que se recopilen métricas (por ejemplo, densidad de vulnerabilidades, tiempo medio de detección) sobre el código producido por IA y se comparen con las bases de referencia exclusivamente humanas.

---

### AD.2 Calificación de Herramientas de IA y Modelado de Amenazas

Asegúrese de que las herramientas de codificación de IA sean evaluadas por sus capacidades de seguridad, riesgos y el impacto en la cadena de suministro antes de su adopción.

 #AD.2.1    Level: 1    Role: D/V
 Verifique que un modelo de amenaza para cada herramienta de IA identifique el uso indebido, la inversión del modelo, la filtración de datos y los riesgos de la cadena de dependencias.
 #AD.2.2    Level: 2    Role: D
 Verifique que las evaluaciones de herramientas incluyan análisis estático/dinámico de cualquier componente local y evaluación de los puntos finales SaaS (TLS, autenticación/autorización, registro).
 #AD.2.3    Level: 3    Role: D/V
 Verifique que las evaluaciones sigan un marco reconocido y se realicen nuevamente después de cambios importantes de versión.

---

### AD.3 Gestión Segura de Indicaciones y Contexto

Evitar la filtración de secretos, código propietario y datos personales al construir indicaciones o contextos para modelos de IA.

 #AD.3.1    Level: 1    Role: D/V
 Verifique que las directrices escritas prohíban enviar secretos, credenciales o datos clasificados en los indicios.
 #AD.3.2    Level: 2    Role: D
 Verifique que los controles técnicos (redacción del lado del cliente, filtros de contexto aprobados) eliminen automáticamente los elementos sensibles.
 #AD.3.3    Level: 3    Role: D/V
 Verifique que los indicios y respuestas estén tokenizados, cifrados durante la transmisión y en reposo, y que los períodos de retención cumplan con la política de clasificación de datos.

---

### AD.4 Validación del Código Generado por IA

Detectar y corregir vulnerabilidades introducidas por la salida de IA antes de que el código sea fusionado o desplegado.

 #AD.4.1    Level: 1    Role: D/V
 Verifique que el código generado por IA siempre sea sometido a una revisión humana del código.
 #AD.4.2    Level: 2    Role: D
 Verifique que los escáneres automatizados (SAST/IAST/DAST) se ejecuten en cada solicitud de extracción que contenga código generado por IA y bloqueen las fusiones en caso de hallazgos críticos.
 #AD.4.3    Level: 3    Role: D/V
 Verifique que las pruebas de fuzzing diferencial o las pruebas basadas en propiedades demuestren comportamientos críticos para la seguridad (por ejemplo, validación de entrada, lógica de autorización).

---

### AD.5 Explicabilidad y Trazabilidad de las Sugerencias de Código

Proporcionar a los auditores y desarrolladores una visión sobre por qué se hizo una sugerencia y cómo evolucionó.

 #AD.5.1    Level: 1    Role: D/V
 Verifique que los pares de indicaciones/respuestas se registren con los IDs de commit.
 #AD.5.2    Level: 2    Role: D
 Verifique que los desarrolladores puedan mostrar citas del modelo (fragmentos de entrenamiento, documentación) que respalden una sugerencia.
 #AD.5.3    Level: 3    Role: D/V
 Verifique que los informes de explicabilidad se almacenen junto con los artefactos de diseño y se referencien en las revisiones de seguridad, cumpliendo con los principios de trazabilidad de ISO/IEC 42001.

---

### AD.6 Retroalimentación continua y ajuste fino del modelo

Mejorar el rendimiento de la seguridad del modelo con el tiempo mientras se previene la deriva negativa.

 #AD.6.1    Level: 1    Role: D/V
 Verificar que los desarrolladores puedan marcar sugerencias inseguras o no conformes, y que dichas marcas sean registradas.
 #AD.6.2    Level: 2    Role: D
 Verifique que la retroalimentación agregada informe el ajuste fino periódico o la generación aumentada por recuperación con corpus de codificación segura verificados (por ejemplo, OWASP Cheat Sheets).
 #AD.6.3    Level: 3    Role: D/V
 Verifique que un entorno de evaluación de circuito cerrado ejecute pruebas de regresión después de cada afinación; las métricas de seguridad deben cumplir o superar las líneas base anteriores antes del despliegue.

---

#### Referencias

NIST AI Risk Management Framework 1.0
ISO/IEC 42001:2023 — AI Management Systems Requirements
OWASP Secure Coding Practices — Quick Reference Guide

## Apéndice E: Ejemplos de Herramientas y Marcos de Trabajo

### Objetivo

Este capítulo proporciona ejemplos de herramientas y marcos que pueden apoyar la implementación o cumplimiento de un requisito determinado de AISVS. Estos no deben considerarse como recomendaciones o respaldos por parte del equipo de AISVS o del Proyecto de Seguridad GenAI de OWASP.

---

### AE.1 Gobernanza de Datos de Entrenamiento y Gestión de Sesgos

Herramientas utilizadas para análisis de datos, gobernanza y gestión de sesgos.

 #AE.1.1    Section: 1.1
 Herramientas de Inventario de Datos: Herramientas de gestión de inventario de datos como...
 #AE.1.2    Section: 1.2
 Encriptación en tránsito Utilice TLS para aplicaciones basadas en HTTPS, con herramientas como openSSL y python's`ssl`biblioteca.

---

### AE.2 Validación de entrada del usuario

Herramientas para manejar y validar entradas de usuario.

 #AE.2.1    Section: 2.1
 Herramientas de defensa contra la inyección de prompts: Utilice herramientas de protección como NeMo de NVIDIA o Guardrails AI.

---

## Gobernanza de Datos de Entrenamiento C1 y Gestión de Sesgos

### C1.1 Procedencia de los Datos de Entrenamiento

Mantenga un inventario verificable de todos los conjuntos de datos, acepte solo fuentes confiables y registre cada cambio para garantizar la auditabilidad.

 #1.1.1    Level: 1    Role: D/V
 Verifique que se mantenga un inventario actualizado de cada fuente de datos de entrenamiento (origen, responsable/propietario, licencia, método de recopilación, restricciones de uso previstas e historial de procesamiento).

