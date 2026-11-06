# DEC-002 — Delegación, revisión y responsabilidad humano–IA

**Estado:** Propuesta operativa v0.1 para discusión; no aprobada ni validada empíricamente  
**Fecha:** 2026-11-04  
**Responsable de aceptación:** Mantenedor humano de HUMENGIA  
**Relación:** [Premisa y principios](../README.md) · [DEC-001](./DEC-001-colaboracion-humano-ia.md) · [Marco teórico exploratorio](../investigacion/marco-teorico.md)

## 1. Decisión a explorar

¿Cómo decidir **qué puede hacer la IA**, **qué debe revisar una persona**, **cuándo debe intervenir** y **qué evidencia es suficiente**, sin que el control se vuelva una carga que perjudique los resultados?

Se propone un mecanismo ligero para equipos de ingeniería de software que trabajen con IA. No presupone una herramienta, agente, modelo, lenguaje, metodología o proveedor concreto. Su valor se juzgará por la **eficacia, eficiencia, oportunidad y calidad demostrada** de las soluciones entregadas al cliente.

**Alcance:** actividades de ingeniería de software (análisis, diseño, implementación, pruebas, despliegue y mantenimiento) y decisiones vinculadas con necesidades y procesos del cliente. No pretende reemplazar la dirección del negocio, el consentimiento del cliente, las responsabilidades profesionales ni un marco general de arquitectura empresarial.

## 2. Principios operativos propuestos

1. **Delegar según evidencia y contexto, no por entusiasmo tecnológico.** La autonomía concedida a la IA depende de lo que puede comprobarse y revertirse.
2. **Conservar responsabilidades humanas identificables.** El humano define objetivos, límites y criterios de aceptación; autoriza acciones de consecuencias relevantes y asume los compromisos con el cliente.
3. **Permitir crítica recíproca.** La IA puede cuestionar supuestos humanos y el humano puede rechazar la propuesta de IA; ambos deben aportar fundamentos.
4. **No atribuir conocimiento a quien no lo confirmó.** Una hipótesis generada por IA no se registra como regla aceptada por cliente o experto de dominio hasta verificarla.
5. **Minimizar la carga de control.** Reutilizar pruebas, PR, commits, incidencias y registros existentes como evidencia; agregar documentos solo cuando sea necesario para comprender o decidir.
6. **Revisar el modelo cuando falle.** La clasificación y los niveles aquí descritos son hipótesis de diseño, no umbrales científicamente validados.
7. **Conservar aportes constructivos con consecuencias.** Una propuesta, objeción, corrección o alternativa relevante para el trabajo presente o futuro debe quedar referenciada donde se toman decisiones, aunque finalmente se descarte. No se trata de registrar cada pensamiento ni de multiplicar documentos.

## 3. Tres dimensiones para graduar el control

Cada actividad o cambio se clasifica de modo **cualitativo**:

| Dimensión | Bajo / favorable | Medio | Alto / desfavorable |
| --- | --- | --- | --- |
| **Impacto potencial (I)** | Consecuencias limitadas; no afecta a usuarios, datos críticos o compromisos externos | Afecta funcionalidad, procesos, integraciones o servicio recuperable | Puede comprometer seguridad, privacidad, integridad de datos, continuidad, obligaciones o a personas |
| **Dificultad de reversión (R)** | Revertible fácilmente, con respaldo y procedimiento ensayado cuando corresponde | Reversión posible con esfuerzo o interrupciones acotadas | Reversión incierta, costosa o imposible; efectos persistentes |
| **Dificultad de verificación (V)** | Comprobaciones fiables y ejecutables disponibles; resultado observable | Evidencia parcial o dependencia de validaciones manuales | Resultado difícil de comprobar, información insuficiente o validación tardía |

**Regla orientativa inicial:** partir del nivel más exigente señalado por cualquiera de las tres dimensiones; **no promediar** ni permitir que dos factores favorables oculten uno crítico. Escalar si hay incertidumbre significativa, dependencia externa, permisos amplios o información sensible.

La matriz orienta una conversación técnica; no sustituye el juicio del responsable ni las políticas de seguridad del cliente. No asignamos puntuaciones numéricas ni pesos arbitrarios sin experimentación.

## 4. Niveles de delegación y revisión

| Nivel | Situación orientativa | Acción permitida a IA | Intervención humana y evidencia |
| --- | --- | --- | --- |
| **N1 — Supervisión ligera** | Bajo impacto, reversión y verificación sencillas | Proponer y ejecutar **en entorno controlado y dentro del alcance autorizado** | Revisión de resultado y verificaciones automatizadas o evidencia equivalente; registrar solo lo relevante |
| **N2 — Revisión antes de integrar** | Cualquier dimensión media o incertidumbre relevante | Analizar, proponer e implementar en rama, sandbox o ambiente aislado | Revisión humana de decisiones y pruebas antes de fusionar, desplegar o compartir cambios con el cliente |
| **N3 — Autorización previa y verificación reforzada** | Cualquier dimensión alta; efectos sensibles o irreversibles | Investigar y proponer alternativas; ejecutar únicamente acciones expresamente autorizadas y acotadas | Aprobar alcance y riesgos **antes de actuar**; validar con controles apropiados y, cuando corresponda, con expertos o cliente; autorizar liberación explícitamente |

**Nunca autoriza por defecto:** uso de credenciales sin permiso, difusión de datos confidenciales, cambios irreversibles, acciones en producción, decisiones legalmente reservadas a personas o aceptación de reglas de negocio en nombre del cliente. Las autorizaciones explícitas y restricciones del entorno prevalecen sobre cualquier nivel.

**Autoridad de clasificación:** la IA y cualquier integrante humano pueden proponer un nivel o solicitar elevarlo. **Solo el responsable humano confirma la clasificación y puede reducirla**, registrando el fundamento y las evidencias de control. Una clasificación sugerida por IA no autoriza ejecución. Si surge un riesgo mayor o desconocido, se detienen las acciones afectadas hasta la reevaluación humana.

### Evidencia orientativa por nivel

| Nivel | Evidencia proporcionada |
| --- | --- |
| N1 | Comprobación apropiada al trabajo y revisión ligera; automatizar pruebas cuando existan |
| N2 | Revisión humana documentada de la decisión y evidencia de cumplimiento antes de integrar o liberar |
| N3 | Autorización humana previa, análisis de riesgos, prevención o contingencia cuando corresponda y verificación reforzada |

En una actividad irreversible no se debe fingir un plan de reversión: se necesitan controles preventivos, análisis de alternativas y autorización expresa.

## 5. Preguntas de control mínimas

Antes de delegar o integrar, cuando sea pertinente:

1. **¿Para quién y para qué?** ¿Qué necesidad y criterio de aceptación se busca satisfacer?
2. **¿Qué se ha confirmado?** Separar datos/reglas validados por el cliente de supuestos del humano o de IA.
3. **¿Qué puede fallar?** Identificar impacto, reversibilidad y verificabilidad.
4. **¿Quién puede hacer qué?** Delimitar herramientas, datos, permisos, entorno, condiciones de detención y responsable humano.
5. **¿Cómo sabremos que funcionó?** Precisar **qué afirmación** se intenta demostrar, acordar evidencia proporcional a ella y distinguir resultado técnico de valor entregado al cliente.
6. **¿Cómo se sale de un bloqueo?** Registrar solución o alternativas, siguiente acción, responsable, dependencias y criterio verificable de desbloqueo, o explicar por qué se detiene.
7. **¿Qué merece conservarse?** Registrar las aportaciones constructivas que puedan afectar decisiones, riesgos, implementación o seguimiento, indicando su estado y procedencia.

Si el riesgo o la incertidumbre cambian durante la tarea, se detiene la acción potencialmente dañina y se vuelve a clasificar antes de continuar.

### Correspondencia entre afirmación y evidencia (propuesta R1)

La prueba exigida depende de **lo que se afirma**, no automáticamente de la complejidad del sistema en su conjunto:

| Afirmación | Evidencia pertinente, según el caso | Lo que no demuestra por sí sola |
| --- | --- | --- |
| **Componente**: una regla o función se comporta correctamente | Prueba unitaria, propiedades, regresión o mutación controlada | Que la integración o el producto completo funcionen |
| **Integración**: varios componentes o sistemas intercambian datos correctamente | Prueba integrada, contrato, traza o emulación que ejecute los componentes reales | Fidelidad del entorno físico o satisfacción del cliente |
| **Sistema en contexto de uso**: la solución funciona donde debe operar | Demostración representativa, prueba de aceptación, medición o prueba física autorizada cuando sea necesaria | Que el cliente haya recibido todo el valor prometido |
| **Resultado para el cliente**: la necesidad acordada quedó resuelta | Criterio observable de uso/entrega, aceptación competente y limitaciones documentadas | Mejoras generales de productividad por utilizar IA |
| **Eficacia de HUMENGIA**: este modo de colaboración mejora resultados | Indicadores, costos y contraste razonable con alternativas o línea base, incluyendo resultados desfavorables | Generalización causal a otros contextos a partir de un solo caso |

Un ensayo parcial puede aprobarse **en su propio alcance** sin exigir una prueba superior que todavía no sea posible, pero no se le atribuye el resultado superior. En cambios físicos o críticos prevalecen siempre los permisos, controles y puertas de seguridad del proyecto; la proporcionalidad no los rebaja. Si no hay evidencia suficiente, se indica **pendiente**, **bloqueado** o **no concluyente**, no «validado».

## 6. Procedencia de decisiones: registro ligero

Para decisiones relevantes, registrar en una PR, incidencia, commit, acta o DEC existente:

| Campo | Contenido esperado |
| --- | --- |
| **Necesidad / decisión** | Contexto, beneficiario y alternativa escogida |
| **Contribución de IA** | Propuestas, cuestionamientos, artefactos o acciones específicas; indicar cuando no intervino |
| **Contribución humana** | Supuestos, correcciones, validaciones y rechazos razonados |
| **Fuentes y estado del conocimiento** | Evidencia, información confirmada por cliente o experto, hipótesis pendientes |
| **Riesgo y revisión** | Nivel propuesto, fundamento, verificación realizada y excepciones aprobadas |
| **Responsable y autorización** | Persona que decide, momento y límites de autorización |
| **Resultado y seguimiento** | Pruebas, aceptación, impacto observado, problemas y correcciones posteriores |

**Ejemplo breve (hipotético):** «La IA propuso permitir dos postulaciones por oferta; el ingeniero detectó ambigüedad; el responsable del proceso confirmó una sola postulación activa por candidato y oferta; se añadió prueba del caso duplicado; responsable X aprobó la decisión». Sin esa confirmación, la regla quedaría pendiente.

**Trazabilidad constructiva (propuesta R3):** registrar donde se trabaja —issue, PR, decisión o registro existente— las observaciones, hipótesis, alternativas, críticas y pruebas **que puedan cambiar una decisión o guiar trabajo futuro**, incluso si se rechazan o contradicen una predicción de la IA. Conservar al menos el aporte, su procedencia, fundamento o evidencia, estado (**propuesto, aprobado/rechazado, implementado, comprobado o pendiente**, según corresponda) y siguiente acción si existe. **Que una idea esté escrita no la convierte en aprobación humana ni en hecho demostrado.**

Si se descubre un bloqueo, enlazar desde ese mismo registro la alternativa elegida, quién decide, cómo se comprobará el desbloqueo y qué sigue pendiente de entregar al beneficiario. Conservar el error y su corrección sin reescribir retrospectivamente la predicción inicial.

No se exige guardar conversaciones completas, razonamientos privados, prompts internos, ideas triviales, datos sensibles ni secretos; se conserva únicamente evidencia pertinente, con enlaces cuando exista. Evitar registros paralelos que dupliquen una misma decisión.

## 7. Uso experimental en HUMENGIA

El propio proyecto puede ser un **piloto de viabilidad** del registro de procedencia: permite observar si es posible reconstruir cambios y decisiones, el tiempo requerido y las omisiones encontradas. **No demuestra por sí solo ganancias de productividad ni calidad en proyectos de clientes.**

### Aprendizajes exploratorios observados

En una aplicación piloto surgieron tres tipos de corrección del procedimiento: ajustar una exigencia de prueba al **alcance de la afirmación**, distinguir cobertura nueva de cobertura ya existente tras una predicción parcialmente refutada y evitar que propuestas de solución queden fuera del registro de decisiones. También se observó que un control técnico aprobado **no equivale** a un producto utilizable.

Estas observaciones motivan R1 y R3, **no acreditan** que HUMENGIA mejore productividad, calidad o resultados en general. La evidencia específica permanece en su proyecto de origen; cualquier relato público de pilotos debe ser agregado o anonimizado y no divulgar datos, enlaces ni artefactos privados sin autorización. La procedencia, los límites y las propuestas derivadas se reúnen en el [registro exploratorio de pilotos](../investigacion/registro-pilotos.md), sin duplicar evidencias internas.

### Primera aplicación sugerida

- Revisar retrospectivamente PR #1 y PR #2, y documentar aportes del fundador, propuestas de ChatGPT y crítica de Claude **solo cuando exista evidencia en la conversación o el historial**.
- Utilizar esta plantilla mínima en la revisión de DEC-002, registrando desacuerdos reales y tiempo aproximado de la tarea, sin inventar duraciones ni aprobaciones.
- Aplicar la clasificación I/R/V a una actividad pequeña y reversible; observar si las restricciones y revisiones fueron proporcionadas.
- Identificar casos donde el modelo bloquea demasiado o deja riesgos sin atender y registrar el ajuste necesario.

### Hipótesis relacionadas (para investigar)

- **H06:** delegación condicionada por riesgos y capacidad comprobable podría reducir correcciones tardías.
- **H07:** revisión proporcional podría evitar defectos importantes con menor sobrecarga que revisión exhaustiva.
- **H08:** procedencia de aportes de IA y validación humana podría mejorar auditabilidad con costo razonable.
- **H09:** el aporte neto de la IA podría variar de signo según tarea, herramienta y contexto.

Los identificadores H06–H09 corresponden a una **actualización propuesta en una PR documental independiente**. Si esa PR no se integra, los identificadores deberán reconciliarse antes de adoptar DEC-002.

## 8. Cómo evaluar si la propuesta sirve

Antes de un ensayo, definir el caso, participantes, alternativa comparativa y criterios de aceptación. Registrar, donde sea razonable:

- **Eficacia:** requisitos y necesidades satisfechos, además de ambigüedades detectadas antes del retrabajo.
- **Eficiencia:** tiempo humano total —preparación, interacción, revisión, corrección y documentación— y recursos utilizados.
- **Oportunidad:** tiempo hasta resultado utilizable, no solo tiempo de generación de código.
- **Calidad y riesgo:** defectos, incidencias evitadas o producidas, verificación lograda y severidad de fallos.
- **Costo del mecanismo:** esfuerzo de clasificación, revisión y registro; omisiones y errores de clasificación.

Un caso propio puede demostrar factibilidad y revelar problemas, pero **no justifica generalizar eficacia** a equipos, modelos o industrias diferentes. Para comparar efectividad se requerirán tareas, equipos y condiciones suficientemente comparables.

## 9. Alternativas y decisiones pendientes

| Alternativa | Motivo para considerar / descartar provisionalmente |
| --- | --- |
| Revisar todo exhaustivamente | Control predecible, pero costo alto incluso en tareas triviales |
| Delegar sin clasificación | Menor trabajo inicial, pero puede esconder riesgos difíciles de detectar |
| Clasificación cualitativa I/R/V + niveles N1–N3 | Propuesta inicial: explicable, adaptable y susceptible de refutación |

**Todavía debe resolverse en revisión:** ¿hay actividades que requieren un escalamiento directo a N3 independientemente de I/R/V? ¿Qué evidencia mínima es suficiente por nivel? ¿Cómo se adapta a distintos tamaños de equipo y a clientes con políticas propias? ¿Cuáles son los criterios para detener una ejecución autónoma?

## 10. Estado de aprobación y límites

**DEC-002 integra la [propuesta operativa HUMENGIA v0.1](../PROPUESTA-HUMENGIA-v0.1.md) y es una propuesta para discusión.** No autoriza por sí misma automatizaciones ni intervenciones en sistemas de terceros, no modifica la premisa del README y no reemplaza DEC-001. Su utilidad y proporcionalidad deben contrastarse con casos reales antes de convertirla en práctica estable. El mantenedor decidirá si acepta la propuesta, solicita correcciones o la descarta.

**Estado de las reglas R1–R4:** permanecen **propuestas pendientes de decisión humana** durante la revisión de la [PR #6](https://github.com/calaluis/humengia/pull/6). Una aprobación y fusión explícita las adoptaría **solo para ensayo controlado**, sin afirmar validación empírica, superioridad causal ni autorización adicional para acciones de riesgo. La decisión y los resultados posteriores se registrarán en la [Issue #5](https://github.com/calaluis/humengia/issues/5) y en el registro de pilotos, según corresponda.

Su relación con DDD, TOGAF, BPM y otras disciplinas es **selectiva y orientada por el problema**; el objetivo sigue siendo ingeniería de software centrada en el cliente mediante colaboración humana e IA, no un marco universal de dirección de empresas.
