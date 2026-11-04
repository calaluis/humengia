# HUMENGIA v0.1 — Propuesta integral para validación

**Estado:** Propuesta de ingeniería completa para revisión; **pendiente de validación práctica**.  
**Alcance:** Ingeniería de software centrada en el cliente, mediante colaboración humano–IA.  
**Naturaleza:** Modelo operativo adaptable, no estándar, certificación ni metodología de otro autor.  
**Fundamentos:** [README](./README.md) · [DEC-001](./decisiones/DEC-001-colaboracion-humano-ia.md) · [DEC-002](./decisiones/DEC-002-delegacion-revision-humano-ia.md) · [Marco teórico](./investigacion/marco-teorico.md).

## 1. Premisa rectora

> Establecer un marco de ingeniería de software, centrado en el cliente, que permita desarrollar soluciones eficaces, eficientes y oportunas, mediante la colaboración entre profesionales humanos e inteligencia artificial, y demostrar objetivamente la calidad y el cumplimiento de los resultados entregados.

Esta premisa es la referencia de toda decisión HUMENGIA. El cliente es quien necesita o recibe valor de la solución, exista o no una transacción comercial.

En HUMENGIA:

- **Eficacia** significa resolver necesidades y cumplir criterios acordados, no solamente terminar funcionalidades.
- **Eficiencia** significa obtener ese resultado con uso justificado de tiempo y recursos, **incluyendo el costo de interactuar y revisar a la IA**.
- **Oportunidad** significa entregar valor cuando es necesario, no limitarse a generar código rápidamente.
- **Calidad demostrable** significa comprobar atributos pertinentes del producto y, cuando corresponda, resultados en el contexto real de uso.

## 2. Qué es HUMENGIA y qué no es

**Es:** una propuesta de colaboración para comprender problemas, decidir, construir, verificar y aprender, con roles humanos responsables, aportes de IA identificables y evidencia proporcional al riesgo.

**No es:** una nueva tecnología, un orquestador de agentes, un lenguaje, un conjunto universal de documentos, una adopción de DDD o TOGAF, ni la promesa de que usar IA siempre mejora la productividad.

Se aprovechan selectivamente conocimientos de ingeniería de requisitos, dominio, arquitectura empresarial, procesos, pruebas y experimentación **cuando ayudan al propósito del cliente**. No son etapas ni herramientas obligatorias.

La solución adecuada puede ser modificar software existente, crear software nuevo o recomendar un cambio de proceso sin desarrollo nuevo. El modelo se aplica de manera proporcional al contexto.

## 3. Participantes y responsabilidades

| Participante | Responsabilidad o contribución |
| --- | --- |
| Cliente / beneficiario o representante | Explicar la necesidad, aportar contexto, confirmar reglas del negocio y valorar el resultado. No se atribuyen aprobaciones inexistentes. |
| Profesional humano responsable | Precisar objetivos, seleccionar alternativas, delimitar permisos, evaluar riesgos, aprobar decisiones relevantes y responsabilizarse por compromisos y entregas. |
| IA colaboradora | Analizar, preguntar, detectar ambigüedades, proponer alternativas, producir artefactos, verificar y advertir problemas dentro del alcance autorizado. Sus afirmaciones se contrastan. |
| Revisor independiente, si existe | Cuestionar supuestos y revisar evidencia. La participación de otra IA no equivale a una revisión humana independiente. |

Los roles pueden coincidir en una persona en proyectos pequeños; esa limitación debe declararse al evaluar los resultados. Humano e IA pueden alternar iniciativa y criticar propuestas recíprocamente, pero **la IA no autoriza por sí sola acciones de riesgo ni confirma reglas en nombre del cliente**.

## 4. Ciclo operativo mínimo: de necesidad a resultado observado

El ciclo es **iterativo y no secuencial de manera rígida**. Se puede volver a cualquier actividad cuando surge información nueva; la colaboración humano–IA ocurre durante todo el recorrido.

| Actividad | Pregunta que debe quedar contestada | Evidencia suficiente posible |
| --- | --- | --- |
| **A. Comprender** | ¿Qué problema tiene el cliente, para quién y por qué importa? ¿Qué sabemos y qué suponemos? | Necesidad, contexto, regla confirmada y criterio observable de aceptación |
| **B. Elegir** | ¿Qué alternativa, alcance y nivel de control tienen mejor fundamento y proporción? | Justificación breve, riesgo, responsable, criterios de verificación |
| **C. Construir** | ¿Podemos entregar el incremento más pequeño que produzca o permita observar valor? | Código, diseño, prueba, prototipo o cambio necesario; procedencia del aporte |
| **D. Verificar** | ¿Qué pruebas y revisión respaldan la corrección y seguridad del cambio? | Resultado de pruebas, análisis, demostración o validación pertinente |
| **E. Contrastar** | ¿El resultado satisface la necesidad y llega oportunamente? ¿Qué cambió respecto de la situación inicial? | Aceptación real, medición, observaciones y defectos relevantes |
| **F. Aprender** | ¿Qué debemos mantener, corregir o descartar, incluso del propio HUMENGIA? | Decisión posterior, cambio de hipótesis, incidencia o mejora registrada |

**Criterio práctico:** para una tarea pequeña, una PR con contexto, decisión y pruebas puede contener toda la evidencia. No hay obligación de producir seis documentos ni seis reuniones. Para tareas complejas o peligrosas puede ser necesario explicitar más.

## 5. Cómo se trabaja con IA sin perder el control

Antes de ejecutar una tarea, el responsable humano define **objetivo, límites, permisos y criterios de éxito**. La IA puede proponer una clasificación de riesgo o señalar una mayor; **solo un responsable humano puede confirmar y reducir el nivel de control** con fundamento. Si aparece un riesgo nuevo, se suspenden las acciones afectadas y se reevalúan.

Se utiliza el modelo cualitativo de [DEC-002](./decisiones/DEC-002-delegacion-revision-humano-ia.md):

- **N1 — Supervisión ligera:** bajo impacto, reversión sencilla y verificación fiable; ejecución dentro de un entorno y alcance autorizado.
- **N2 — Revisión previa:** incertidumbre o riesgo moderado; revisión humana de cambios y evidencia antes de integrar o liberar.
- **N3 — Autorización previa:** consecuencias elevadas o difícil control; aprobación del alcance antes de actuar, medidas preventivas y comprobación reforzada.

Se considera la dimensión más exigente entre **impacto (I), dificultad de reversión (R) y dificultad de verificación (V)**, sin promediar. La matriz es una **hipótesis operativa**: debe ser evaluada y revisada con el piloto.

No se autorizan implícitamente accesos a secretos, despliegues productivos, operaciones irreversibles ni actuaciones sobre hardware o datos sensibles. Las reglas y permisos existentes en cada proyecto **prevalecen**.

## 6. Evidencia y procedencia, sin formularios redundantes

Un cambio relevante debe permitir contestar:

1. **Necesidad:** ¿qué problema o compromiso del cliente atiende?
2. **Decisión:** ¿qué se eligió, qué se descartó y por qué?
3. **Contribución de IA:** ¿qué propuso, cuestionó, generó o ejecutó realmente?
4. **Intervención humana:** ¿qué confirmó, corrigió, rechazó o autorizó la persona responsable?
5. **Verificación:** ¿qué prueba, fuente o comprobación respalda la conclusión?
6. **Resultado:** ¿qué se obtuvo y qué evidencia de satisfacción o fallo existe?

**Una PR, incidencia, registro de prueba o acta existente puede ser suficiente**. DEC-002 contiene la definición operativa más detallada de esos campos; DEC-001 conserva el principio conceptual. Registrar la referencia a evidencias es preferible a duplicar su contenido; no se requieren transcripciones completas de conversaciones ni secretos.

### Evidencia orientativa por nivel

| Nivel | Mínimo orientativo; ajustar al tipo de trabajo |
| --- | --- |
| N1 | Resultado verificable y revisión ligera; pruebas automáticas cuando existan |
| N2 | Revisión humana documentada y evidencia de aceptación de los criterios antes de integrar o liberar |
| N3 | Autorización previa documentada, riesgos y medidas preventivas o de contingencia, validación reforzada antes y, cuando corresponda, después de liberar |

No se promete seguridad por completar campos. Si una acción es irreversible, la ausencia de un plan de reversión debe reconocerse y tratarse mediante prevención y autorización, no inventar una reversión.

## 7. Cómo determinar si HUMENGIA aporta valor

Antes del piloto se documentan: **unidad de trabajo**, problema, criterio de aceptación, alternativa o línea base comparable, contexto y medidas; se registra tanto lo que mejora como lo que empeora.

| Criterio | Observación posible |
| --- | --- |
| Eficacia | Necesidades y criterios aceptados por el beneficiario; incumplimientos y retrabajo |
| Eficiencia | Tiempo total invertido, incluyendo coordinación, prompts, revisión, correcciones y controles |
| Oportunidad | Tiempo hasta un resultado utilizable y cumplimiento de la necesidad temporal |
| Calidad | Pruebas relevantes, defectos, incidentes, estabilidad y observaciones en el contexto disponible |
| Trazabilidad | Si otra persona puede reconstruir decisiones y fuentes sin información ficticia |
| Sobrecarga | Tiempo o pasos añadidos por HUMENGIA y su utilidad percibida y observada |

**No serán indicadores de éxito por sí solos**: cantidad de documentos, líneas de código, prompts, agentes, pruebas ejecutadas o archivos cambiados.

Si el modelo aumenta costos sin aportar beneficios pertinentes, omite riesgos relevantes o dificulta entregar a tiempo, deberá corregirse o descartarse parcialmente. Registrar tanto resultados favorables como desfavorables.

## 8. Criterios para dar por terminada esta propuesta (antes del piloto)

HUMENGIA v0.1 estará **lista para ensayarse**, sin afirmar validación científica, cuando su revisión humana confirme que:

- La premisa y los cuatro principios están preservados sin cambios de significado.
- Se identifica a quién sirve, quién decide, qué propone o ejecuta la IA y cuáles son sus límites.
- El ciclo A–F permite aplicar el modelo a una necesidad real sin imponer herramientas ni documentación adicional obligatoria.
- Hay criterios operativos de delegación, revisión, escalamiento, autorización y detención ante riesgos.
- La procedencia y la evidencia pueden registrarse con artefactos ya existentes.
- Existen criterios observables de eficacia, eficiencia, oportunidad, calidad y sobrecarga.
- Están expresadas las condiciones en las que HUMENGIA **no aporta valor** o requiere ajustes.
- El caso piloto y sus límites se acuerdan antes de aplicarlo.

**Propuesta terminada ≠ propuesta demostrada.** El primer estado significa que el procedimiento ya puede ejecutarse y examinarse; el segundo requerirá evidencia real y, para afirmaciones generalizables, estudios adicionales.

## 9. Diseño mínimo del piloto (ejecución posterior)

La validación inicial debe hacerse en **un proyecto de ingeniería de software real y existente**, eligiendo una necesidad legítima y un incremento acotado:

1. **Línea base:** documentar qué hace hoy el equipo, qué restricciones vigentes tiene y qué evidencia ya genera, sin alterar su proceso.
2. **Selección segura:** escoger una actividad limitada, preferentemente reversible, con pruebas disponibles y permisos explícitos; no usar una modificación crítica como primera prueba.
3. **Aplicación:** ejecutar un incremento con HUMENGIA; conservar decisiones, aportes humano–IA, revisión y pruebas en herramientas ya utilizadas por el proyecto.
4. **Observación:** medir tiempo total, cumplimiento, defectos, evidencia y sobrecarga frente a una referencia razonable.
5. **Revisión:** registrar qué fue útil, qué falló y qué debe cambiar antes de un segundo ensayo.

No se cambiarán políticas, puertas de seguridad, derechos de acceso ni requisitos del proyecto piloto en nombre de HUMENGIA. **El caso de estudio no autoriza despliegues ni actividades físicas.** Si el repositorio es privado, las evidencias internas permanecerán privadas; cualquier publicación externa será agregada o anonimizada y requerirá aprobación.

Una sola experiencia sirve para comprobar **viabilidad y encontrar defectos del modelo**, no para acreditar superioridad universal ni causalidad.

## 10. Estado y decisión pendiente

**Esta es la propuesta de diseño HUMENGIA v0.1 para revisión.** Reúne el uso práctico del modelo y deja el respaldo conceptual en los documentos enlazados. Su integración en `main` significará **autorizar un ensayo controlado**, nunca afirmar que HUMENGIA ha quedado demostrado.

La revisión puede reducir, modificar o eliminar componentes que no aporten a la premisa. Tras cerrar esta propuesta, **la prioridad deja de ser ampliar la documentación y pasa a producir evidencia de un caso real**.
