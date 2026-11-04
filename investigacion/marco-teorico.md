# Marco teórico de HUMENGIA — Investigación inicial v0.1

> **Estado:** revisión exploratoria v0.1 integrada para investigación y evolución; no constituye validación de HUMENGIA. **Fecha:** 2026-11-04.  
> **Naturaleza:** revisión exploratoria y selectiva de literatura; **no** revisión sistemática, estándar, certificación ni demostración de eficacia.  
> **Documentos relacionados:** [visión y principios](../README.md) · [DEC-001 — Colaboración humano–IA](../decisiones/DEC-001-colaboracion-humano-ia.md).

## 1. Premisa y límites

La premisa fundacional de HUMENGIA es:

> Establecer un marco de ingeniería de software, centrado en el cliente, que permita desarrollar soluciones eficaces, eficientes y oportunas, mediante la colaboración entre profesionales humanos e inteligencia artificial, y demostrar objetivamente la calidad y el cumplimiento de los resultados entregados.

Se entiende **cliente** como quien necesita o recibe el valor de una solución, exista o no una relación comercial.

**Regla de independencia:** HUMENGIA es agnóstico respecto de tecnologías, arquitecturas, proveedores, lenguajes de programación y metodologías. DDD, TOGAF, BPM, normas ISO, SDD, TDD y otras prácticas son **referencias para analizar críticamente**, no componentes obligatorios ni marcos que debamos reproducir. El valor esperado para el cliente y la evidencia disponible determinan qué conviene utilizar.

El ámbito principal sigue siendo la **ingeniería de software**. Comprender estrategia, capacidades y procesos de negocio sirve para determinar qué problema resolver y cómo evaluar el valor obtenido; no convierte automáticamente a HUMENGIA en un marco integral de arquitectura empresarial ni en un sistema de gestión de procesos.

## 2. Criterio de lectura de fuentes y nivel de evidencia

Este documento diferencia:

- **Antecedente documentado:** concepto atribuido a una publicación, estándar o institución consultable, con referencia verificable.
- **Inferencia para HUMENGIA:** relación razonada entre ese conocimiento y nuestra premisa. No debe atribuirse al autor de la fuente como si este hubiera formulado HUMENGIA.
- **Hipótesis propia:** afirmación sobre beneficios o efectividad todavía no contrastada de forma suficiente en nuestro contexto.
- **Decisión adoptada:** compromiso del proyecto documentado y aceptado por el mantenedor; no equivale a validación empírica.

La presente investigación **no** ha realizado una búsqueda bibliográfica exhaustiva, evaluación formal de sesgos ni lectura íntegra de todas las obras de acceso restringido. En particular, para las normas ISO se usa la descripción pública de su alcance, no una reproducción de sus cláusulas. Las referencias deben ampliarse o corregirse cuando se revisen las fuentes completas.

## 3. Fundamentos seleccionados

### 3.1. Propósito humano, necesidades y requisitos

**Antecedentes.** ISO 9241-210:2019 describe requisitos y recomendaciones para el diseño centrado en las personas de sistemas interactivos [F01]. ISO/IEC/IEEE 29148:2018 trata los procesos de ingeniería de requisitos para sistemas, software y servicios [F02].

**Lectura para HUMENGIA.** Entender las necesidades y el contexto de uso antecede a la elección tecnológica. Los requisitos deben poder relacionarse con resultados comprensibles para el beneficiario. Una implementación que satisface pruebas técnicas, pero no una necesidad validada, no demuestra por sí sola eficacia.

**Límite.** El alcance de ISO 9241-210 es el diseño de sistemas interactivos; no se usa como respaldo universal de todas las actividades de ingeniería ni se declara conformidad con la norma.

### 3.2. Arquitectura empresarial y alineación con el cliente

**Antecedente.** TOGAF, 10.ª edición, contiene un método de desarrollo de arquitectura empresarial (ADM) y orientación para adaptarlo a diferentes contextos [F03].

**Lectura para HUMENGIA.** La relación entre objetivos de la organización, capacidades, procesos, información, aplicaciones y decisiones tecnológicas puede ayudar a delimitar el problema y evitar optimizaciones técnicas desconectadas del propósito del cliente.

**Selección crítica.** Aprovechar preguntas y perspectivas de arquitectura empresarial **no implica** exigir el ciclo completo del ADM, sus artefactos, una certificación ni un modelo de arquitectura empresarial para proyectos pequeños. El análisis del contexto debe ser proporcional al alcance y al riesgo.

### 3.3. Procesos de negocio y valor entregado

**Antecedentes.** El documento explicativo de ISO sobre el enfoque por procesos en ISO 9001:2015 describe actividades relacionadas que transforman entradas en resultados y plantea controles proporcionales al contexto y riesgo [F04]. BPMN 2.0.2, publicado por OMG, define una notación de modelado de procesos para facilitar la comprensión entre participantes del negocio y técnicos [F05]. APQC ofrece un marco de clasificación de procesos (PCF) adaptable a organizaciones [F06].

**Lectura para HUMENGIA.** En problemas donde existen procesos organizacionales, resulta útil identificar el estado actual, el resultado deseado, las personas involucradas, las restricciones y las medidas de desempeño. Antes de automatizar una actividad conviene verificar si debe mantenerse, simplificarse o eliminarse.

**Selección crítica.** No todo proyecto requiere diagramas BPMN, inventarios exhaustivos ni una clasificación APQC. Estas técnicas se justifican solo si ayudan a comprender, decidir o verificar mejoras.

### 3.4. Conocimiento del dominio y lenguaje compartido

**Antecedentes.** Eric Evans publicó *Domain-Driven Design: Tackling Complexity in the Heart of Software* en 2003 [F07]. Las explicaciones de Martin Fowler sobre *Ubiquitous Language* y *Bounded Context* destacan el vocabulario compartido con expertos del dominio y los límites donde un modelo conserva un significado consistente [F08, F09].

**Lectura para HUMENGIA.** Cliente, experto, ingeniero e IA necesitan distinguir términos definidos, reglas confirmadas, suposiciones y ambigüedades. Una IA puede detectar inconsistencias o proponer interpretaciones, pero no convertir una inferencia en una regla de negocio atribuida al cliente.

**Selección crítica.** El valor de comprender el dominio no requiere imponer todos los patrones tácticos de DDD (por ejemplo, agregados, repositorios o estructuras de objetos). La complejidad del problema debe justificar el modelado y la implementación elegidos.

### 3.5. Colaboración entre humanos e inteligencia artificial

**Antecedentes.** Horvitz estudió en 1999 la *iniciativa mixta* en interfaces, combinando automatización y control humano [F10]. Dellermann y colaboradores abordaron en 2019 la *inteligencia híbrida* y la complementariedad entre personas y máquinas [F11]. Amershi y colaboradores propusieron y evaluaron 18 guías de interacción humano–IA para productos con IA [F12].

**Lectura para HUMENGIA.** Estos trabajos permiten formular un modelo donde humanos e IA aportan propuestas, detectan errores, expresan incertidumbre y se complementan, mientras las responsabilidades profesionales y los compromisos con el cliente son identificables.

**Límite de la evidencia.** Los estudios citados **no prueban** que un flujo de ingeniería de software HUMENGIA mejore productividad, calidad o satisfacción del cliente. Algunos investigan interfaces y productos con IA, no específicamente equipos de desarrollo de software. Su relación con DEC-001 es conceptual y requiere validación independiente.

### 3.6. Calidad, eficacia, eficiencia, oportunidad y verificación empírica

**Antecedentes.** ISO/IEC 25010:2023 presenta un modelo de calidad de producto; ISO/IEC 25019:2023, uno de calidad en uso [F13, F14]. Basili formuló el enfoque *Goal–Question–Metric* (GQM) para vincular objetivos, preguntas y métricas [F15]. Wohlin y colaboradores ofrecen fundamentos para planificar y evaluar estudios empíricos en ingeniería de software [F16].

**Lectura para HUMENGIA.** Una entrega puede tener buenas propiedades técnicas sin aportar suficiente valor en su contexto real. La evaluación debe distinguir:

- **Eficacia:** grado en que se satisfacen necesidades y objetivos acordados.
- **Eficiencia:** recursos necesarios para alcanzar resultados, considerando trabajo humano, coordinación, operación y mantenimiento.
- **Oportunidad:** disponibilidad del resultado cuando el beneficiario lo necesita; no equivale simplemente a programar más rápido.
- **Calidad del producto:** atributos técnicos pertinentes, definidos y comprobados de forma contextual.
- **Calidad en uso:** consecuencias de usar la solución en un contexto concreto, contrastadas con la experiencia y los objetivos del beneficiario.

Estas definiciones constituyen una **interpretación operativa inicial de HUMENGIA**, no una transcripción literal de ISO. Debemos acordar medidas y métodos de observación apropiados para cada caso, evitando equiparar cantidad de documentos, líneas de código o pruebas con valor entregado.

## 4. Relación entre fundamentos y principios del README

| Principio fundacional | Antecedentes potencialmente pertinentes | Aporte seleccionado; no adopción automática |
| --- | --- | --- |
| I. Propósito humano | Diseño centrado en las personas [F01]; requisitos [F02]; procesos [F04] | Comprender a quién sirve la solución y su contexto |
| II. Colaboración complementaria | Iniciativa mixta [F10]; inteligencia híbrida [F11]; interacción humano–IA [F12] | Combinar capacidades, hacer explícita la incertidumbre y mantener responsabilidades humanas |
| III. Ingeniería demostrable | Calidad de producto y uso [F13, F14]; GQM [F15]; experimentación [F16] | Establecer resultados esperados y observar cumplimiento real |
| IV. Decisiones fundamentadas y trazables | Requisitos [F02]; dominio [F07–F09]; experimentación [F16] | Contrastar alternativas, registrar motivos y revisar consecuencias |

La **alineación con objetivos, capacidades y procesos** y el **agnosticismo tecnológico/metodológico** son criterios transversales derivados de la premisa y de DEC-001. Este documento **no propone ni aprueba automáticamente un quinto principio**.

## 5. Filtro para adoptar conocimientos de otros enfoques

Antes de recomendar una práctica concreta:

1. **Pertinencia:** ¿qué necesidad del cliente o decisión del proyecto resuelve?
2. **Fundamento:** ¿qué fuente, razonamiento o experiencia la respalda y con qué límites?
3. **Beneficio esperado:** ¿qué mejora plausible aporta a eficacia, eficiencia, oportunidad o calidad?
4. **Proporcionalidad:** ¿cuál es su costo, complejidad, riesgo y reversibilidad?
5. **Verificabilidad:** ¿cómo observaríamos su utilidad y qué resultado obligaría a reconsiderarla?

**Posibles salidas:** adoptar bajo condiciones explícitas; ensayar como hipótesis; posponer por falta de evidencia; o descartar por falta de pertinencia. Ningún nombre reconocido sustituye esta evaluación.

## 6. Agenda inicial de hipótesis comprobables

Estas son **hipótesis propuestas**, no resultados demostrados. Mantenemos los identificadores H01–H05 para preservar trazabilidad; añadimos hipótesis específicas sobre la contribución y el control de IA, que pasan a ser la prioridad experimental.

### 6.1. Colaboración humano–IA (prioridad)

| ID | Hipótesis a poner a prueba | Observaciones sugeridas |
| --- | --- | --- |
| H01 | La crítica recíproca humano–IA detecta ambigüedades relevantes frente a una modalidad comparativa definida | Ambigüedades confirmadas; retrabajo; tiempo de revisión |
| H04 | Un vocabulario de dominio contrastado por humanos e IA disminuye las interpretaciones erróneas frente a interacción no estructurada | Errores de interpretación; reglas confirmadas por cliente; costo de validación |
| H06 | Delegación diferenciada por riesgo y capacidad comprobable disminuye correcciones tardías respecto de delegación uniforme | Incidentes; retrabajo; tiempo humano de supervisión |
| H07 | Una revisión proporcional al impacto, reversibilidad y verificabilidad evita errores importantes con menor sobrecarga que la revisión exhaustiva | Defectos relevantes; costo total de revisión; fallos no detectados |
| H08 | Registrar procedencia de aportes de IA y validaciones humanas mejora la auditabilidad de decisiones sin una carga desproporcionada | Reconstrucción independiente de decisiones; minutos de registro; omisiones |
| H09 | La colaboración humano–IA aporta beneficios netos en ciertos contextos, pero puede aumentar el tiempo total en otros | Tiempo total incluyendo instrucciones, revisión y corrección; calidad; experiencia del equipo |

Las comparaciones deberán especificar equipo, tarea, herramientas, criterios de calidad y alternativa de referencia. El uso de IA no constituye por sí mismo una mejora demostrada.

### 6.2. Fundamentos de ingeniería y contexto (hipótesis de apoyo)

| ID | Hipótesis a poner a prueba | Observaciones posibles |
| --- | --- | --- |
| H02 | Analizar objetivos y procesos del cliente de forma proporcionada mejora el ajuste de la solución | Aceptación; retrabajo; costo del análisis |
| H03 | Seleccionar prácticas por pertinencia y riesgo reduce sobrecarga sin empeorar calidad | Trabajo no productivo; defectos; mantenimiento |
| H05 | Medir resultados ligados a objetivos aporta mejor información que medir solo actividad | Utilidad de indicadores; decisiones revisadas; cumplimiento de objetivos |

Estas hipótesis de apoyo serían relevantes incluso sin IA. Se estudian para no perder el propósito de ingeniería centrada en el cliente, **pero no se presentan como el diferenciador específico de HUMENGIA**.

**Protocolo mínimo recomendado, sujeto a diseño posterior:** precisar población y contexto; especificar intervención y comparación; acordar criterios con el beneficiario; registrar línea base cuando sea viable; observar resultados y costos; documentar incidentes, cambios de alcance y factores de confusión; exponer limitaciones. Para afirmaciones causales fuertes se necesitarán diseños y tamaños de muestra adecuados; un único caso ilustrativo no basta para validación general.

## 7. Límites éticos, metodológicos y jurídicos

- No sustituir el juicio ni la aceptación del cliente con inferencias de IA.
- No divulgar información confidencial ni datos personales del cliente para conseguir evidencia.
- No inventar citas, métricas, aprobaciones, resultados o cumplimiento normativo.
- No declarar HUMENGIA conforme a ISO, TOGAF, BPMN u otros estándares por el solo hecho de citarlos.
- Respetar derechos de autor de libros y normas: utilizar referencias bibliográficas, resúmenes originales y enlaces, no copiar textos protegidos extensos.
- No asumir que la evidencia obtenida en un proveedor, industria o modelo de IA se generaliza automáticamente.

## 8. Bibliografía inicial verificada

Las fuentes están ordenadas por temática, no por jerarquía. Los enlaces a páginas oficiales o editoriales permiten comprobar al menos metadatos y alcance. Los textos completos pueden requerir acceso legítimo.

**Personas, requisitos y procesos**

- **[F01]** ISO. (2019). *ISO 9241-210:2019 — Human-centred design for interactive systems*. [Ficha oficial](https://www.iso.org/standard/77520.html).
- **[F02]** ISO/IEC/IEEE. (2018). *29148:2018 — Requirements engineering*. [Ficha oficial](https://www.iso.org/standard/72089.html). Edición vigente según ficha consultada el 2026-11-04; puede ser reemplazada.
- **[F03]** The Open Group. (2022). *The TOGAF Standard, 10th Edition — Architecture Development Method*. [Ficha bibliográfica del libro](https://books.google.com/books/about/The_TOGAF_Standard_10th_Edition_Architec.html?id=-5RsEAAAQBAJ); [entidad de The Open Group sobre la 10.ª edición](https://www.opengroup.co.za/togaf-standard-10th-edition).
- **[F04]** ISO/TC 176/SC 2. (2015). *The Process Approach in ISO 9001:2015*. [Documento explicativo oficial](https://www.iso.org/iso/iso9001_2015_process_approach.pdf). Es una guía explicativa, no el texto completo de la norma.
- **[F05]** Object Management Group. (2014). *Business Process Model and Notation (BPMN), Version 2.0.2*. [Especificación oficial](https://www.omg.org/spec/BPMN/2.0.2).
- **[F06]** APQC. *Process Classification Framework (PCF)*. [Portal institucional de marcos de procesos](https://www.apqc.org/process-frameworks). La clasificación se menciona como referencia, no como requisito.

**Dominio y modelos**

- **[F07]** Evans, E. (2003). *Domain-Driven Design: Tackling Complexity in the Heart of Software*. Addison-Wesley. ISBN 978-0-321-12521-7. [Editorial](https://www.informit.com/store/domain-driven-design-tackling-complexity-in-the-heart-9780321125217).
- **[F08]** Fowler, M. *Ubiquitous Language*. [Artículo](https://martinfowler.com/bliki/UbiquitousLanguage.html).
- **[F09]** Fowler, M. *Bounded Context*. [Artículo](https://martinfowler.com/bliki/BoundedContext.html).

**Colaboración humano–IA**

- **[F10]** Horvitz, E. (1999). *Principles of Mixed-Initiative User Interfaces*. CHI '99, 159–166. DOI: [10.1145/302979.303030](https://doi.org/10.1145/302979.303030).
- **[F11]** Dellermann, D.; Ebel, P.; Söllner, M.; Leimeister, J. M. (2019). *Hybrid Intelligence*. *Business & Information Systems Engineering*, 61(5), 637–643. DOI: [10.1007/s12599-019-00595-2](https://doi.org/10.1007/s12599-019-00595-2). [Registro universitario](https://alexandria.unisg.ch/entities/publication/07deb4e4-fb32-449e-99b1-91a7499b9f5c).
- **[F12]** Amershi, S. et al. (2019). *Guidelines for Human-AI Interaction*. CHI 2019. DOI: [10.1145/3290605.3300233](https://doi.org/10.1145/3290605.3300233). [Microsoft Research](https://www.microsoft.com/en-us/research/publication/guidelines-for-human-ai-interaction/).

**Calidad y evaluación**

- **[F13]** ISO/IEC. (2023). *25010:2023 — Product quality model*. [Ficha oficial](https://www.iso.org/standard/78176.html).
- **[F14]** ISO/IEC. (2023). *25019:2023 — Quality-in-use model*. [Ficha oficial](https://www.iso.org/standard/78177.html).
- **[F15]** Basili, V. R. (1992). *Software Modeling and Measurement: The Goal/Question/Metric Paradigm*. University of Maryland, CS-TR-2956, UMIACS-TR-92-96. [Repositorio universitario](https://drum.lib.umd.edu/items/8119803a-362b-42ec-b6ce-2311713e7236).
- **[F16]** Wohlin, C.; Runeson, P.; Höst, M.; Ohlsson, M. C.; Regnell, B.; Wesslén, A. (2012). *Experimentation in Software Engineering*. Springer. DOI: [10.1007/978-3-642-29044-2](https://doi.org/10.1007/978-3-642-29044-2).

## 9. Próximos asuntos a investigar

1. Examinar críticamente investigaciones específicas sobre **equipos de ingeniería de software** que trabajan con IA, incluyendo resultados favorables, desfavorables o inconclusos; distinguir productividad percibida y medida. Revisar experimentos de Peng et al. (2023), METR (2025 y actualizaciones posteriores) e informes DORA 2024–2025 antes de extraer conclusiones.
2. Contrastar GQM con medidas de resultados del negocio y calidad en uso; diseñar indicadores modestos y auditables.
3. Evaluar el aporte real de arquitectura empresarial y modelado de procesos en proyectos de distinta complejidad.
4. Investigar sesgos, límites de autonomía, seguridad, privacidad y responsabilidad profesional de la colaboración con agentes.
5. Formular un protocolo de investigación que permita comparar alternativas sin asumir de antemano que HUMENGIA será superior.

**Estado al cierre:** revisión exploratoria v0.1 aceptada como base de investigación mediante [PR #2](https://github.com/calaluis/humengia/pull/2), fusionada el 2026-11-04. Su integración no valida las hipótesis ni sustituye una revisión sistemática. Las propuestas operativas futuras requieren decisiones y contrastación propias.
