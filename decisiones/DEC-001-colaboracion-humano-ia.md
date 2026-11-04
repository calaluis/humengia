# DEC-001 — Modelo de colaboración humano–IA

**Estado:** Boceto conceptual v0.1 aceptado para investigación y evolución; no validado empíricamente  
**Fecha:** 2026-11-04  
**Ámbito:** Principios operativos de HUMENGIA  
**Responsable de la decisión:** Mantenedor humano del proyecto  
**Relación:** [Principios fundacionales](../README.md)

## 1. Problema que queremos resolver

HUMENGIA busca desarrollar software que sirva a las personas mediante la colaboración entre profesionales humanos e inteligencias artificiales. No queremos que esa colaboración se reduzca a «el humano pide y la IA ejecuta» ni a una delegación sin control. Tampoco queremos imponer un proceso cuyo costo supere su aporte.

Necesitamos establecer cómo cooperan ambos participantes, cómo se aprovechan sus fortalezas, cómo se detectan sus errores y cómo se fundamentan las decisiones relevantes. La satisfacción de las necesidades de quien recibe la solución debe seguir siendo el criterio central. Para ello, la colaboración debe partir de la comprensión del propósito, el contexto y, cuando sean pertinentes, las capacidades, procesos y reglas del negocio del cliente. La solución apropiada puede incluir software nuevo, modificar el existente o mejorar un proceso sin construir software adicional.

### Premisa rectora de HUMENGIA

> Establecer un marco de ingeniería de software, centrado en el cliente, que permita desarrollar soluciones eficaces, eficientes y oportunas, mediante la colaboración entre profesionales humanos e inteligencia artificial, y demostrar objetivamente la calidad y el cumplimiento de los resultados entregados.

Esta premisa, publicada en el [README fundacional](../README.md), es el criterio de selección y evaluación del modelo. Las referencias externas y las decisiones técnicas están subordinadas a ella; no la reemplazan.

## 2. Alternativas consideradas

| Alternativa | Beneficio potencial | Riesgo o limitación |
| --- | --- | --- |
| Desarrollo principalmente humano con IA solo como consulta | Control cercano del proceso | Desaprovecha capacidades de automatización y exploración |
| Delegación casi completa a agentes de IA | Rapidez potencial en tareas delimitadas | Puede producir errores plausibles, desviaciones y revisiones tardías |
| Colaboración humano–IA con responsabilidades explícitas y verificación proporcional | Combina capacidades y facilita detectar errores | Exige coordinación y criterios claros para decidir cuándo intervenir |

Estas son hipótesis de trabajo, no resultados de una comparación experimental. Ninguna alternativa se declara universalmente superior.

## 3. Modelo propuesto

**Colaboración complementaria:** humanos e IA participan activamente en comprender problemas, explorar alternativas, diseñar, implementar, revisar y aprender de los resultados. Las tareas se asignan según capacidades demostradas, contexto y riesgo, no mediante roles rígidos.

**Propósito humano:** las necesidades del cliente —entendido también como persona, comunidad u organización beneficiaria— orientan prioridades y criterios de éxito. Cuando corresponda, el equipo comprende sus objetivos, capacidades, procesos actuales, restricciones y resultados esperados antes de decidir una implementación.

**Conocimiento del dominio validado:** los términos, reglas y supuestos del problema se contrastan con las personas que conocen el dominio. La IA puede detectar ambigüedades y proponer interpretaciones, pero debe distinguir lo confirmado por el cliente de las hipótesis que requieren validación.

**Responsabilidad identificable:** una persona o equipo humano conserva la responsabilidad profesional de aceptar compromisos, autorizar decisiones relevantes y validar entregas. Las salidas de la IA son propuestas o ejecuciones verificables, no autoridad automática.

**Crítica recíproca:** el humano debe poder cuestionar lo propuesto por la IA; la IA debe poder advertir contradicciones, incertidumbre, errores y riesgos de las propuestas humanas. Ninguno de los dos tiene razón por su sola condición de proponente.

**Verificación proporcionada:** la profundidad de las pruebas, documentación y revisión depende del impacto, riesgo y reversibilidad del cambio. El objetivo es evidencia útil, no formalidad por sí misma.

**Agnosticismo tecnológico y metodológico:** HUMENGIA no prescribe lenguajes, paradigmas de programación, sistemas operativos, arquitecturas, plataformas, proveedores de IA ni herramientas específicas. Tampoco exige adoptar íntegramente un marco externo: se consideran sus aportes según su utilidad para el cliente y el problema.

### Relación selectiva con conocimientos existentes

Los enfoques siguientes ofrecen conocimientos útiles cuya incorporación dependerá del contexto:

| Referente | Aporte que interesa estudiar |
| --- | --- |
| Domain-Driven Design (DDD) | Conocimiento del dominio y lenguaje compartido con el cliente |
| TOGAF y arquitectura empresarial | Relación entre objetivos, capacidades, procesos y decisiones tecnológicas |
| Gestión por procesos (BPM) y BPMN | Comprensión, análisis y medición de procesos cuando resulte pertinente |
| SDD, TDD, XP y otras prácticas | Especificación, pruebas y retroalimentación oportuna según necesidad |

Una práctica propuesta para HUMENGIA se evaluará por su **pertinencia**, **fundamentos**, **beneficio esperado**, **proporcionalidad** y **posibilidad de verificación**. La justificación bibliográfica y las limitaciones de cada referencia se reúnen en el [marco teórico exploratorio](../investigacion/marco-teorico.md).

## 4. Resolución de desacuerdos técnicos

Cuando existan alternativas incompatibles:

1. **Precisar la decisión:** identificar la necesidad del cliente, el proceso o resultado afectado cuando corresponda, las restricciones y los supuestos.
2. **Exponer opciones:** recoger alternativas humanas y de IA sin ocultar incertidumbres.
3. **Evaluar fundamentos:** contrastar las opciones con el propósito del cliente, su contexto y, según corresponda, eficacia, eficiencia, oportunidad, calidad, seguridad, mantenibilidad, costo y riesgos.
4. **Probar cuando sea razonable:** usar experimentos pequeños, prototipos, pruebas o fuentes verificables antes de comprometer una solución costosa.
5. **Decidir y registrar:** el responsable humano, con participación de quienes deban validar reglas o necesidades del dominio, deja constancia de la opción escogida, sus motivos y la evidencia disponible.
6. **Revisar ante nueva información:** actualizar o revertir la decisión cuando los resultados contradigan los supuestos.

La ausencia de evidencia suficiente debe señalarse explícitamente; no se disfraza de certeza.

## 5. Trazabilidad mínima de decisiones relevantes

Un registro de decisión debería permitir reconstruir, sin documentación innecesaria:

- **Necesidad y contexto:** problema, persona o colectivo beneficiario y, cuando resulte relevante, objetivo y proceso del cliente afectado.
- **Alternativas:** opciones consideradas y sus principales consecuencias.
- **Fundamento y procedencia:** criterios, riesgos, restricciones, fuentes y pruebas; distinguir datos confirmados por el cliente de inferencias humanas o de IA.
- **Contribución de la IA:** qué propuso, advirtió, elaboró o ejecutó cuando su participación fue relevante.
- **Validación humana:** qué revisó, corrigió, aceptó o rechazó el responsable, y con qué evidencia.
- **Responsable y fecha:** quién decidió y cuándo.
- **Resultado esperado:** qué se intenta mejorar, con qué criterios de aceptación y cómo se verificará.
- **Resultado observado:** qué ocurrió realmente, cuando exista evidencia posterior.

No toda modificación requiere un documento DEC independiente. Una explicación en una PR o un commit puede ser suficiente para cambios menores. Los campos de procedencia pueden consistir en enlaces a evidencia ya existente; no se exige duplicar registros. Para decisiones de mayor impacto se requiere una revisión proporcionada. La trazabilidad puede conectar, cuando aporte valor, objetivo del cliente, proceso, necesidad, requisito, decisión, implementación y resultado.

## 6. Cómo se demostrará el valor del modelo

Este modelo **no se considera validado** por quedar escrito en el repositorio. Deberá ponerse a prueba con proyectos y funcionalidades reales, registrando al menos:

- **Eficacia:** cumplimiento de necesidades, objetivos y criterios de aceptación acordados con el beneficiario.
- **Eficiencia:** recursos invertidos, esfuerzo humano, costo de coordinación y mantenimiento, en relación con los resultados.
- **Oportunidad:** tiempo hasta una entrega utilizable y cumplimiento de plazos relevantes para el cliente.
- **Calidad demostrable:** defectos y atributos de calidad pertinentes al contexto, verificados con pruebas y observación de uso.
- **Gobernabilidad:** posibilidad de comprender, cuestionar, corregir y auditar decisiones relevantes.

Antes de concluir que hubo mejora, se procurará acordar indicadores y, cuando sea viable, establecer una línea base del proceso o solución existente. No se exigirán métricas idénticas en todos los proyectos. Se contrastarán resultados con alternativas cuando sea razonable, evitando atribuir al marco diferencias derivadas del proyecto, equipo, modelo de IA o herramientas. Una implementación técnicamente correcta no basta por sí sola para demostrar valor para el cliente.

## 7. Límites y preguntas abiertas

- ¿Cómo graduar el rigor de una decisión según impacto, reversibilidad y verificabilidad sin crear burocracia? (Tema prioritario de DEC-002).
- ¿Qué criterios permiten delegar tareas a la IA y cuáles requieren autorización o revisión humana inmediata? (Tema prioritario de DEC-002).
- ¿Qué constituye evidencia suficiente de satisfacción del cliente, además de pruebas automatizadas?
- ¿Cómo registrar desacuerdos y aprendizajes preservando privacidad, secretos y propiedad intelectual?
- ¿Qué experimentos permitirán falsar o modificar esta propuesta?
- ¿Cuándo aporta valor estudiar capacidades y procesos del cliente, y cuándo ese análisis sería desproporcionado?
- ¿Cómo comprobar el beneficio de prácticas tomadas de otros enfoques sin confundir inspiración con adopción obligatoria?
- ¿Cómo medir eficacia, eficiencia y oportunidad sin confundir cantidad de documentación o pruebas con valor entregado?

## 8. Estado de aprobación

**Boceto conceptual v0.1 aceptado como base de investigación y evolución.** El mantenedor revisó y fusionó [PR #1](https://github.com/calaluis/humengia/pull/1) en `main` el 2026-11-04. Esta aceptación autoriza su utilización como fundamento de trabajo, **no demuestra su eficacia ni aprueba automáticamente un procedimiento operativo**. HUMENGIA conserva los cuatro principios del README; las prácticas de delegación y revisión se desarrollarán como propuestas separadas. Las referencias externas son fuentes de conocimiento, no una declaración de conformidad o certificación.
