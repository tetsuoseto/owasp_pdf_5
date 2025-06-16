# Seguridad de Infraestructura, Configuración y Despliegue de C4

## Objetivo de Control

La infraestructura de IA debe ser reforzada contra la escalada de privilegios, la manipulación de la cadena de suministro y el movimiento lateral mediante una configuración segura, aislamiento en tiempo de ejecución, tuberías de despliegue confiables y monitoreo integral. Solo los componentes y configuraciones de infraestructura autorizados y validados llegan a producción a través de procesos controlados que mantienen la seguridad, integridad y capacidad de auditoría.

Objetivo principal de seguridad: Solo los componentes de infraestructura firmados criptográficamente y escaneados en busca de vulnerabilidades llegan a producción mediante tuberías de validación automatizadas que hacen cumplir las políticas de seguridad y mantienen registros de auditoría inmutables.

---

## C4.1 Aislamiento del Entorno de Ejecución

Prevenir fugas de contenedores y escalada de privilegios mediante primitivas de aislamiento a nivel kernel y controles de acceso obligatorios.

|   #   | Description                                                                                                                                                                                                                                                      | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.1.1 | Verifique que todos los contenedores de IA eliminen TODAS las capacidades de Linux excepto CAP_SETUID, CAP_SETGID y las capacidades explícitamente requeridas documentadas en las líneas base de seguridad.                                                      |   1   | D/V  |
| 4.1.2 | Verifique que los perfiles seccomp bloqueen todos los syscalls excepto aquellos en las listas blancas preaprobadas, con violaciones que terminan el contenedor y generan alertas de seguridad.                                                                   |   1   | D/V  |
| 4.1.3 | Verifique que las cargas de trabajo de IA se ejecuten con sistemas de archivos raíz de solo lectura, tmpfs para datos temporales y volúmenes nombrados para datos persistentes con opciones de montaje no ejecutables (noexec) aplicadas.                        |   2   | D/V  |
| 4.1.4 | Verifique que la monitorización en tiempo real basada en eBPF (Falco, Tetragon o equivalente) detecte intentos de escalamiento de privilegios y termine automáticamente los procesos infractores dentro de los requisitos de tiempo de respuesta organizacional. |   2   | D/V  |
| 4.1.5 | Verifique que las cargas de trabajo de IA de alto riesgo se ejecuten en entornos aislados por hardware (Intel TXT, AMD SVM o nodos dedicados bare-metal) con verificación de atestación.                                                                         |   3   | D/V  |

---

## C4.2 Canalizaciones Seguras de Construcción y Despliegue

Asegure la integridad criptográfica y la seguridad de la cadena de suministro mediante compilaciones reproducibles y artefactos firmados.

|   #   | Description                                                                                                                                                                                                                                           | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.2.1 | Verifique que la infraestructura como código se escanee con herramientas (tfsec, Checkov o Terrascan) en cada confirmación, bloqueando las fusiones con hallazgos de gravedad CRÍTICA o ALTA.                                                         |   1   | D/V  |
| 4.2.2 | Verifique que las compilaciones de contenedores sean reproducibles con hashes SHA256 idénticos en todas las compilaciones y genere atestados de procedencia de nivel SLSA 3 firmados con Sigstore.                                                    |   1   | D/V  |
| 4.2.3 | Verifique que las imágenes de contenedores incorporen SBOMs CycloneDX o SPDX y estén firmadas con Cosign antes de ser enviadas al registro, rechazando las imágenes no firmadas en el despliegue.                                                     |   2   | D/V  |
| 4.2.4 | Verifique que las canalizaciones CI/CD utilicen tokens OIDC provenientes de HashiCorp Vault, roles IAM de AWS o identidad administrada de Azure, con una duración que no exceda los límites establecidos por la política de seguridad organizacional. |   2   | D/V  |
| 4.2.5 | Verifique que las firmas Cosign y la proveniencia SLSA se validen durante el proceso de implementación antes de la ejecución del contenedor y que los errores de verificación provoquen la falla de la implementación.                                |   2   | D/V  |
| 4.2.6 | Verifique que los entornos de compilación se ejecuten en contenedores efímeros o máquinas virtuales sin almacenamiento persistente y con aislamiento de red de las VPC de producción.                                                                 |   2   | D/V  |

---

## C4.3 Seguridad de Red y Control de Acceso

Implemente redes de confianza cero con políticas de denegación predeterminadas y comunicaciones cifradas.

|   #   | Description                                                                                                                                                                                                                       | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.3.1 | Verifique que las NetworkPolicies de Kubernetes o cualquier equivalente implementen una política de denegación predeterminada para ingreso/egreso con reglas explícitas de permiso para los puertos necesarios (443, 8080, etc.). |   1   | D/V  |
| 4.3.2 | Verifique que SSH (puerto 22), RDP (puerto 3389) y los extremos de metadatos en la nube (169.254.169.254) estén bloqueados o requieran autenticación basada en certificados.                                                      |   1   | D/V  |
| 4.3.3 | Verifique que el tráfico de salida sea filtrado a través de proxies HTTP/HTTPS (Squid, Istio o puertas de enlace NAT en la nube) con listas de permitidos de dominios y que las solicitudes bloqueadas sean registradas.          |   2   | D/V  |
| 4.3.4 | Verifique que la comunicación entre servicios utilice TLS mutuo con certificados rotados según la política organizacional y que la validación de certificados sea obligatoria (sin usar opciones de omisión de verificación).     |   2   | D/V  |
| 4.3.5 | Verifique que la infraestructura de IA funcione en VPCs/VNets dedicados sin acceso directo a internet y se comunique únicamente a través de gateways NAT o hosts bastión.                                                         |   2   | D/V  |

---

## C4.4 Gestión de Secretos y Claves Criptográficas

Proteja las credenciales mediante almacenamiento respaldado por hardware y rotación automatizada con acceso de confianza cero.

|   #   | Description                                                                                                                                                                                                                | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.4.1 | Verifique que los secretos estén almacenados en HashiCorp Vault, AWS Secrets Manager, Azure Key Vault o Google Secret Manager con cifrado en reposo usando AES-256.                                                        |   1   | D/V  |
| 4.4.2 | Verifique que las claves criptográficas se generen en HSMs de Nivel 2 FIPS 140-2 (AWS CloudHSM, Azure Dedicated HSM) con rotación de claves según la política criptográfica organizacional.                                |   1   | D/V  |
| 4.4.3 | Verifique que la rotación de secretos esté automatizada con despliegue sin tiempo de inactividad y rotación inmediata activada por cambios de personal o incidentes de seguridad.                                          |   2   | D/V  |
| 4.4.4 | Verifique que las imágenes de contenedores sean escaneadas con herramientas (GitLeaks, TruffleHog o detect-secrets) bloqueando las compilaciones que contengan claves API, contraseñas o certificados.                     |   2   | D/V  |
| 4.4.5 | Verifique que el acceso secreto de producción requiera MFA con tokens de hardware (YubiKey, FIDO2) y quede registrado mediante registros de auditoría inmutables con identidades de usuario y marcas de tiempo.            |   2   | D/V  |
| 4.4.6 | Verifique que los secretos se inyecten a través de secretos de Kubernetes, volúmenes montados o contenedores de inicialización y asegúrese de que los secretos nunca estén incrustados en variables de entorno o imágenes. |   2   | D/V  |

---

## C4.5 Sandboxing y Validación de Cargas de Trabajo de IA

Aísle los modelos de IA no confiables en entornos seguros con un análisis exhaustivo del comportamiento.

|   #   | Description                                                                                                                                                                                                                                      | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 4.5.1 | Verifique que los modelos de IA externos se ejecuten en gVisor, microVMs (como Firecracker, CrossVM) o contenedores Docker con las opciones --security-opt=no-new-privileges y --read-only.                                                      |   1   | D/V  |
| 4.5.2 | Verifique que los entornos sandbox no tengan conectividad de red (--network=none) o solo acceso a localhost, con todas las solicitudes externas bloqueadas por reglas de iptables.                                                               |   1   | D/V  |
| 4.5.3 | Verifique que la validación del modelo de IA incluya pruebas automáticas de red-team con cobertura de prueba definida organizacionalmente y análisis conductual para la detección de puertas traseras.                                           |   2   | D/V  |
| 4.5.4 | Verifique que antes de que un modelo de IA sea promovido a producción, sus resultados en el entorno aislado (sandbox) estén firmados criptográficamente por personal de seguridad autorizado y almacenados en registros de auditoría inmutables. |   2   | D/V  |
| 4.5.5 | Verifique que los entornos sandbox se destruyan y se recrean a partir de imágenes maestras entre evaluaciones, con una limpieza completa del sistema de archivos y la memoria.                                                                   |   2   | D/V  |

---

## C4.6 Monitoreo de Seguridad de la Infraestructura

Escanee y monitoree continuamente la infraestructura con remediación automatizada y alertas en tiempo real.

|   #   | Description                                                                                                                                                                                                                             | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.6.1 | Verifique que las imágenes del contenedor se escaneen según los horarios organizacionales, con vulnerabilidades CRÍTICAS que bloqueen la implementación basándose en los umbrales de riesgo organizacional.                             |   1   | D/V  |
| 4.6.2 | Verifique que la infraestructura cumpla con los CIS Benchmarks o los controles NIST 800-53 según los umbrales de cumplimiento definidos por la organización y que incluya la remediación automatizada para las verificaciones fallidas. |   1   | D/V  |
| 4.6.3 | Verifique que las vulnerabilidades de alta gravedad estén parcheadas según los cronogramas de gestión de riesgos organizacionales, con procedimientos de emergencia para las CVE activamente explotadas.                                |   2   | D/V  |
| 4.6.4 | Verifique que las alertas de seguridad se integren con plataformas SIEM (Splunk, Elastic o Sentinel) utilizando formatos CEF o STIX/TAXII con enriquecimiento automatizado.                                                             |   2   |  V   |
| 4.6.5 | Verifique que las métricas de infraestructura se exporten a los sistemas de monitoreo (Prometheus, DataDog) con paneles de SLA y reportes ejecutivos.                                                                                   |   3   |  V   |
| 4.6.6 | Verifique que el desvío de configuración sea detectado usando herramientas (Chef InSpec, AWS Config) según los requisitos de monitoreo organizacional, con reversión automática para cambios no autorizados.                            |   2   | D/V  |

---

## C4.7 Gestión de Recursos de Infraestructura de IA

Prevenir ataques de agotamiento de recursos y garantizar una asignación justa de recursos mediante cuotas y monitoreo.

|   #   | Description                                                                                                                                                                                                                                         | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.7.1 | Verifique que la utilización de GPU/TPU sea monitoreada con alertas activadas en los umbrales definidos por la organización y que se active el escalado automático o el balanceo de carga según las políticas de gestión de capacidad.              |   1   | D/V  |
| 4.7.2 | Verificar que las métricas de la carga de trabajo de IA (latencia de inferencia, rendimiento, tasas de error) se recopilen de acuerdo con los requisitos de monitoreo organizacionales y se correlacionen con la utilización de la infraestructura. |   1   | D/V  |
| 4.7.3 | Verifique que los ResourceQuotas de Kubernetes o equivalentes limiten los workloads individuales de acuerdo con las políticas organizativas de asignación de recursos, con límites estrictos aplicados.                                             |   2   | D/V  |
| 4.7.4 | Verifique que la supervisión de costos rastree el gasto por carga de trabajo/inquilino con alertas basadas en los umbrales presupuestarios organizacionales y controles automatizados para excedentes de presupuesto.                               |   2   |  V   |
| 4.7.5 | Verifique que la planificación de capacidad utilice datos históricos con períodos de pronóstico definidos por la organización y aprovisionamiento automatizado de recursos basado en patrones de demanda.                                           |   3   |  V   |
| 4.7.6 | Verifique que el agotamiento de recursos active los disyuntores de acuerdo con los requisitos de respuesta organizacional, incluyendo la limitación de tasa basada en políticas de capacidad y el aislamiento de la carga de trabajo.               |   2   | D/V  |

---

## C4.8 Controles de Separación de Entornos y Promoción

Implemente límites estrictos en el entorno con puertas automáticas de promoción y validación de seguridad.

|   #   | Description                                                                                                                                                                                                                                                             | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.8.1 | Verifique que los entornos de desarrollo/prueba/producción se ejecuten en VPCs/VNets separadas sin roles IAM compartidos, grupos de seguridad ni conectividad de red.                                                                                                   |   1   | D/V  |
| 4.8.2 | Verifique que la promoción del entorno requiera la aprobación de personal autorizado definido organizacionalmente, con firmas criptográficas y registros de auditoría inmutables.                                                                                       |   1   | D/V  |
| 4.8.3 | Verifique que los entornos de producción bloqueen el acceso SSH, deshabiliten los puntos finales de depuración y requieran solicitudes de cambio con requisitos de aviso previo organizacional, excepto en emergencias.                                                 |   2   | D/V  |
| 4.8.4 | Verifique que los cambios en la infraestructura como código requieran revisión por pares con pruebas automatizadas y escaneo de seguridad antes de fusionarlos en la rama principal.                                                                                    |   2   | D/V  |
| 4.8.5 | Verifique que los datos no pertenecientes a producción estén anonimizados según los requisitos de privacidad organizacional, generación de datos sintéticos o enmascaramiento completo de datos con eliminación de información personal identificable (PII) verificada. |   2   | D/V  |
| 4.8.6 | Verifique que las puertas de promoción incluyan pruebas de seguridad automatizadas (SAST, DAST, escaneo de contenedores) con cero hallazgos CRÍTICOS requeridos para la aprobación.                                                                                     |   2   | D/V  |

---

## C4.9 Respaldo y Recuperación de Infraestructura

Asegure la resiliencia de la infraestructura mediante copias de seguridad automáticas, procedimientos de recuperación probados y capacidades de recuperación ante desastres.

|   #   | Description                                                                                                                                                                                                                                   | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.9.1 | Verificar que las configuraciones de infraestructura estén respaldadas según los cronogramas de respaldo organizacionales hacia regiones geográficamente separadas, implementando la estrategia de respaldo 3-2-1.                            |   1   | D/V  |
| 4.9.2 | Verifique que los sistemas de respaldo funcionen en redes aisladas con credenciales separadas y almacenamiento air-gapped para protección contra ransomware.                                                                                  |   2   | D/V  |
| 4.9.3 | Verifique que los procedimientos de recuperación sean probados y validados mediante pruebas automatizadas de acuerdo con los cronogramas organizacionales, cumpliendo con los objetivos de RTO y RPO según los requisitos de la organización. |   2   |  V   |
| 4.9.4 | Verifique que la recuperación ante desastres incluya manuales específicos para IA con restauración de pesos de modelos, reconstrucción de clústeres GPU y mapeo de dependencias de servicios.                                                 |   3   |  V   |

---

## C4.10 Cumplimiento y Gobernanza de Infraestructura

Mantenga el cumplimiento normativo mediante la evaluación continua, la documentación y los controles automatizados.

|   #    | Description                                                                                                                                                                                               | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.10.1 | Verifique que el cumplimiento de la infraestructura se evalúe según los cronogramas organizacionales contra los controles SOC 2, ISO 27001 o FedRAMP, con recopilación automatizada de evidencia.         |   2   | D/V  |
| 4.10.2 | Verifique que la documentación de la infraestructura incluya diagramas de red, mapas de flujo de datos y modelos de amenazas actualizados conforme a los requisitos de gestión del cambio organizacional. |   2   |  V   |
| 4.10.3 | Verifique que los cambios en la infraestructura se sometan a una evaluación automatizada del impacto de cumplimiento con flujos de trabajo de aprobación regulatoria para modificaciones de alto riesgo.  |   3   | D/V  |

---

## C4.11 Seguridad del Hardware de IA

Componentes de hardware específicos para IA seguros, incluyendo GPUs, TPUs y aceleradores especializados de IA.

|   #    | Description                                                                                                                                                                                                 | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.11.1 | Verifique que el firmware del acelerador de IA (BIOS de GPU, firmware de TPU) esté verificado con firmas criptográficas y se actualice según los cronogramas de gestión de parches de la organización.      |   2   | D/V  |
| 4.11.2 | Verifique que antes de la ejecución de la carga de trabajo, la integridad del acelerador de IA sea validada mediante atestación de hardware utilizando TPM 2.0, Intel TXT o AMD SVM.                        |   2   | D/V  |
| 4.11.3 | Verifique que la memoria de la GPU esté aislada entre las cargas de trabajo utilizando SR-IOV, MIG (GPU Multi-Instancia) o una partición de hardware equivalente con saneamiento de memoria entre trabajos. |   2   | D/V  |
| 4.11.4 | Verifique que la cadena de suministro de hardware de IA incluya la verificación de procedencia con certificados del fabricante y la validación de empaques a prueba de manipulaciones.                      |   3   |  V   |
| 4.11.5 | Verifique que los módulos de seguridad de hardware (HSM) protejan los pesos del modelo de IA y las claves criptográficas con certificación FIPS 140-2 Nivel 3 o Common Criteria EAL4+.                      |   3   | D/V  |

---

## C4.12 Infraestructura de IA en el Borde y Distribuida

Despliegues de IA distribuida segura que incluyen computación en el borde, aprendizaje federado y arquitecturas multisede.

|   #    | Description                                                                                                                                                                                                                        | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.12.1 | Verifique que los dispositivos de IA en el borde se autentiquen con la infraestructura central utilizando TLS mutuo con certificados de dispositivo que se roten conforme a la política organizacional de gestión de certificados. |   2   | D/V  |
| 4.12.2 | Verifique que los dispositivos perimetrales implementen arranque seguro con firmas verificadas y protección contra retrocesos para evitar ataques de degradación del firmware.                                                     |   2   | D/V  |
| 4.12.3 | Verifique que la coordinación de IA distribuida utilice algoritmos de consenso tolerantes a fallos bizantinos con validación de participantes y detección de nodos maliciosos.                                                     |   3   | D/V  |
| 4.12.4 | Verifique que la comunicación de borde a nube incluya limitación de ancho de banda, compresión de datos y capacidades de operación sin conexión con almacenamiento local seguro.                                                   |   3   | D/V  |

---

## C4.13 Seguridad de Infraestructura Multi-Nube e Híbrida

Asegure las cargas de trabajo de IA en varios proveedores de nube y en implementaciones híbridas de nube y local.

|   #    | Description                                                                                                                                                                                                         | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.13.1 | Verifique que las implementaciones de IA multi-nube utilicen federación de identidad agnóstica a la nube (OIDC, SAML) con gestión centralizada de políticas entre proveedores.                                      |   2   | D/V  |
| 4.13.2 | Verifique que la transferencia de datos entre nubes utilice cifrado de extremo a extremo con claves gestionadas por el cliente y que se apliquen controles de residencia de datos según la jurisdicción.            |   2   | D/V  |
| 4.13.3 | Verifique que las cargas de trabajo de IA en la nube híbrida implementen políticas de seguridad consistentes tanto en entornos locales como en la nube, con monitoreo y alertas unificados.                         |   2   | D/V  |
| 4.13.4 | Verifique que la prevención del bloqueo del proveedor en la nube incluya infraestructura portátil como código, API estandarizadas y capacidades de exportación de datos con herramientas de conversión de formatos. |   3   |  V   |
| 4.13.5 | Verifique que la optimización de costos multicloud incluya controles de seguridad que prevengan la proliferación de recursos, así como cargos no autorizados por transferencia de datos entre nubes.                |   3   |  V   |

---

## C4.14 Automatización de Infraestructura y Seguridad GitOps

Automatización segura de infraestructuras y flujos de trabajo GitOps para la gestión de infraestructuras de IA.

|   #    | Description                                                                                                                                                                                                                            | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.14.1 | Verifique que los repositorios GitOps requieren commits firmados con claves GPG y reglas de protección de ramas que eviten los push directos a las ramas principales.                                                                  |   2   | D/V  |
| 4.14.2 | Verifique que la automatización de la infraestructura incluya detección de desviaciones con capacidades automáticas de remediación y reversión activadas según los requisitos de respuesta organizacional para cambios no autorizados. |   2   | D/V  |
| 4.14.3 | Verifique que el aprovisionamiento automatizado de infraestructura incluya la validación de la política de seguridad con bloqueo del despliegue para configuraciones no conformes.                                                     |   2   | D/V  |
| 4.14.4 | Verifique que los secretos de automatización de infraestructura se gestionen a través de operadores de secretos externos (External Secrets Operator, Bank-Vaults) con rotación automática.                                             |   2   | D/V  |
| 4.14.5 | Verifique que la infraestructura de autocuración incluya la correlación de eventos de seguridad con respuesta automatizada a incidentes y flujos de trabajo de notificación a las partes interesadas.                                  |   3   |  V   |

---

## C4.15 Seguridad de Infraestructura Resistente a la Computación Cuántica

Prepare la infraestructura de IA para las amenazas de la computación cuántica mediante criptografía post-cuántica y protocolos seguros frente a la computación cuántica.

|   #    | Description                                                                                                                                                                                                       | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.15.1 | Verifique que la infraestructura de IA implemente algoritmos criptográficos post-cuánticos aprobados por el NIST (CRYSTALS-Kyber, CRYSTALS-Dilithium, SPHINCS+) para el intercambio de claves y firmas digitales. |   3   | D/V  |
| 4.15.2 | Verifique que los sistemas de distribución de claves cuánticas (QKD) estén implementados para comunicaciones de IA de alta seguridad con protocolos de gestión de claves seguros contra la computación cuántica.  |   3   | D/V  |
| 4.15.3 | Verifique que los marcos de agilidad criptográfica permitan una migración rápida a nuevos algoritmos post-cuánticos con una rotación automatizada de certificados y claves.                                       |   3   | D/V  |
| 4.15.4 | Verifique que el modelado de amenazas cuánticas evalúe la vulnerabilidad de la infraestructura de IA a ataques cuánticos con cronogramas de migración documentados y evaluaciones de riesgos.                     |   3   |  V   |
| 4.15.5 | Verifique que los sistemas criptográficos híbridos clásico-cuánticos proporcionen una defensa en profundidad durante el período de transición cuántica con monitoreo de rendimiento.                              |   3   | D/V  |

---

## C4.16 Computación Confidencial y Recintos Seguros

Proteja las cargas de trabajo de IA y los pesos del modelo utilizando entornos de ejecución de confianza basados en hardware y tecnologías de computación confidencial.

|   #    | Description                                                                                                                                                                           | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.16.1 | Verifique que los modelos de IA sensibles se ejecuten dentro de enclaves Intel SGX, AMD SEV-SNP o ARM TrustZone con memoria encriptada y verificación de atestación.                  |   3   | D/V  |
| 4.16.2 | Verifique que los contenedores confidenciales (Kata Containers, gVisor con computación confidencial) aislan las cargas de trabajo de IA con cifrado de memoria aplicado por hardware. |   3   | D/V  |
| 4.16.3 | Verifique que la atestación remota valide la integridad del enclave antes de cargar modelos de IA con una prueba criptográfica de la autenticidad del entorno de ejecución.           |   3   | D/V  |
| 4.16.4 | Verifique que los servicios confidenciales de inferencia de IA eviten la extracción del modelo mediante computación cifrada con pesos del modelo sellados y ejecución protegida.      |   3   | D/V  |
| 4.16.5 | Verifique que la orquestación del entorno de ejecución confiable gestione el ciclo de vida del enclave seguro con atestación remota y canales de comunicación cifrados.               |   3   | D/V  |
| 4.16.6 | Verifique que la computación multipartita segura (SMPC) permite el entrenamiento colaborativo de IA sin exponer conjuntos de datos individuales ni parámetros del modelo.             |   3   | D/V  |

---

## C4.17 Infraestructura de Conocimiento Cero

Implementar sistemas de prueba de conocimiento cero para la verificación y autenticación de IA que preserven la privacidad sin revelar información sensible.

|   #    | Description                                                                                                                                                                                                       | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.17.1 | Verifique que las pruebas de conocimiento cero (ZK-SNARKs, ZK-STARKs) confirmen la integridad del modelo de IA y la procedencia del entrenamiento sin exponer los pesos del modelo ni los datos de entrenamiento. |   3   | D/V  |
| 4.17.2 | Verifique que los sistemas de autenticación basados en ZK permiten la verificación de usuario preservando la privacidad para servicios de IA sin revelar información relacionada con la identidad.                |   3   | D/V  |
| 4.17.3 | Verifique que los protocolos de intersección privada de conjuntos (PSI) permiten la coincidencia segura de datos para la inteligencia artificial federada sin exponer los conjuntos de datos individuales.        |   3   | D/V  |
| 4.17.4 | Verifique que los sistemas de aprendizaje automático de conocimiento cero (ZKML) permitan inferencias de IA verificables con prueba criptográfica de cálculo correcto.                                            |   3   | D/V  |
| 4.17.5 | Verifique que los ZK-rollups proporcionan un procesamiento de transacciones de IA escalable y que preserva la privacidad, con verificación por lotes y reducción de la carga computacional.                       |   3   | D/V  |

---

## C4.18 Prevención de ataques por canal lateral

Proteja la infraestructura de IA contra ataques de canal lateral basados en tiempo, energía, electromagnetismo y caché que podrían filtrar información sensible.

|   #    | Description                                                                                                                                                                                  | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.18.1 | Verifique que el tiempo de inferencia de IA esté normalizado utilizando algoritmos de tiempo constante y relleno para prevenir ataques de extracción de modelos basados en el tiempo.        |   3   | D/V  |
| 4.18.2 | Verifique que la protección contra el análisis de potencia incluya la inyección de ruido, el filtrado de la línea de alimentación y patrones de ejecución aleatorios para el hardware de IA. |   3   | D/V  |
| 4.18.3 | Verifique que la mitigación de canales laterales basada en caché utilice particionamiento de caché, aleatorización e instrucciones de vaciado para prevenir la filtración de información.    |   3   | D/V  |
| 4.18.4 | Verifique que la protección contra emanaciones electromagnéticas incluya blindaje, filtrado de señales y procesamiento aleatorizado para prevenir ataques al estilo TEMPEST.                 |   3   | D/V  |
| 4.18.5 | Verifique que las defensas contra canales laterales microarquitectónicos incluyan controles de ejecución especulativa y ofuscación de patrones de acceso a la memoria.                       |   3   | D/V  |

---

## C4.19 Seguridad de Hardware Neuromórfico y de IA Especializada

Asegurar arquitecturas emergentes de hardware de IA que incluyen chips neuromórficos, FPGAs, ASICs personalizados y sistemas de computación óptica.

|   #    | Description                                                                                                                                                                                    | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.19.1 | Verifique que la seguridad del chip neuromórfico incluya cifrado de patrones de picos, protección del peso sináptico y validación basada en hardware de la regla de aprendizaje.               |   3   | D/V  |
| 4.19.2 | Verifique que los aceleradores de IA basados en FPGA implementen cifrado de bitstream, mecanismos anti-manipulación y carga de configuración segura con actualizaciones autenticadas.          |   3   | D/V  |
| 4.19.3 | Verifique que la seguridad personalizada del ASIC incluya procesadores de seguridad en chip, raíz de confianza de hardware y almacenamiento seguro de claves con detección de manipulaciones.  |   3   | D/V  |
| 4.19.4 | Verifique que los sistemas de computación óptica implementen cifrado óptico seguro frente a la computación cuántica, conmutación fotónica segura y procesamiento protegido de señales ópticas. |   3   | D/V  |
| 4.19.5 | Verifique que los chips de IA híbridos analógico-digital incluyan computación analógica segura, almacenamiento protegido de ponderaciones y conversión autenticada de analógico a digital.     |   3   | D/V  |

---

## C4.20 Infraestructura de Computación que Preserva la Privacidad

Implementar controles de infraestructura para el cálculo preservador de la privacidad con el fin de proteger datos sensibles durante el procesamiento y análisis de IA.

|   #    | Description                                                                                                                                                                                                                                  | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.20.1 | Verifique que la infraestructura de cifrado homomórfico permita el cálculo cifrado en cargas de trabajo sensibles de IA con verificación criptográfica de integridad y monitoreo del rendimiento.                                            |   3   | D/V  |
| 4.20.2 | Verifique que los sistemas de recuperación privada de información permitan consultas a bases de datos sin revelar los patrones de consulta, mediante la protección criptográfica de los patrones de acceso.                                  |   3   | D/V  |
| 4.20.3 | Verifique que los protocolos de computación multipartita segura permiten una inferencia de IA que preserva la privacidad sin exponer las entradas individuales ni los cálculos intermedios.                                                  |   3   | D/V  |
| 4.20.4 | Verifique que la gestión de claves que preserva la privacidad incluya generación distribuida de claves, criptografía umbral y rotación segura de claves con protección respaldada por hardware.                                              |   3   | D/V  |
| 4.20.5 | Verifique que el rendimiento del cálculo que preserva la privacidad esté optimizado mediante agrupación por lotes, almacenamiento en caché y aceleración por hardware, manteniendo al mismo tiempo las garantías de seguridad criptográfica. |   3   | D/V  |

---

## C4.15 Marco de Agente para la Integración en la Nube, Seguridad y Despliegue Híbrido

Controles de seguridad para marcos de agentes integrados en la nube con arquitecturas híbridas locales/nube.

|   #    | Description                                                                                                                                         | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.15.1 | Verifique que la integración del almacenamiento en la nube utilice cifrado de extremo a extremo con gestión de claves controlada por el agente.     |   1   | D/V  |
| 4.15.2 | Verifique que los límites de seguridad en la implementación híbrida estén claramente definidos con canales de comunicación encriptados.             |   2   | D/V  |
| 4.15.3 | Verifique que el acceso a los recursos en la nube incluya verificación de confianza cero con autenticación continua.                                |   2   | D/V  |
| 4.15.4 | Verifique que los requisitos de residencia de datos se cumplan mediante la atestación criptográfica de las ubicaciones de almacenamiento.           |   3   | D/V  |
| 4.15.5 | Verifique que las evaluaciones de seguridad del proveedor de la nube incluyan modelado de amenazas específico para agentes y evaluación de riesgos. |   3   | D/V  |

---

## Referencias

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

