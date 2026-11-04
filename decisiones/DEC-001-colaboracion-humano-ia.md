# DEC-001 — Modelo de colaboración humano–IA

**Estado:** Propuesta para discusión (no aprobada)  
**Fecha:** 2026-11-04  
**Ámbito:** Principios operativos de HUMENGIA  
**Responsable de la decisión:** Mantenedor humano del proyecto, tras su revisión  
**Relación:** [Principios fundacionales](../README.md)

## 1. Problema que queremos resolver

HUMENGIA busca desarrollar software que sirva a las personas mediante la colaboración entre profesionales humanos e inteligencias artificiales. No queremos que esa colaboración se reduzca a «el humano pide y la IA ejecuta» ni a una delegación sin control. Tampoco queremos imponer un proceso cuyo costo supere su aporte.

Necesitamos establecer cómo cooperan ambos participantes, cómo se aprovechan sus fortalezas, cómo se detectan sus errores y cómo se fundamentan las decisiones relevantes. La satisfacción de las necesidades de quien recibe la solución debe seguir siendo el criterio central.

## 2. Alternativas consideradas

| Alternativa | Beneficio potencial | Riesgo o limitación |
| --- | --- | --- |
| Desarrollo principalmente humano con IA solo como consulta | Control cercano del proceso | Desaprovecha capacidades de automatización y exploración |
| Delegación casi completa a agentes de IA | Rapidez potencial en tareas delimitadas | Puede producir errores plausibles, desviaciones y revisiones tardías |
| Colaboración humano–IA con responsabilidades explícitas y verificación proporcional | Combina capacidades y facilita detectar errores | Exige coordinación y criterios claros para decidir cuándo intervenir |

Estas son hipótesis de trabajo, no resultados de una comparación experimental. Ninguna alternativa se declara universalmente superior.

## 3. Modelo propuesto

**Colaboración complementaria:** humanos e IA participan activamente en comprender problemas, explorar alternativas, diseñar, implementar, revisar y aprender de los resultados. Las tareas se asignan según capacidades demostradas, contexto y riesgo, no mediante roles rígidos.

**Propósito humano:** las necesidades del cliente —entendido también como persona, comunidad u organización beneficiaria— orientan prioridades y criterios de éxito.

**Responsabilidad identificable:** una persona o equipo humano conserva la responsabilidad profesional de aceptar compromisos, autorizar decisiones relevantes y validar entregas. Las salidas de la IA son propuestas o ejecuciones verificables, no autoridad automática.

**Crítica recíproca:** el humano debe poder cuestionar lo propuesto por la IA; la IA debe poder advertir contradicciones, incertidumbre, errores y riesgos de las propuestas humanas. Ninguno de los dos tiene razón por su sola condición de proponente.

**Verificación proporcionada:** la profundidad de las pruebas, documentación y revisión depende del impacto, riesgo y reversibilidad del cambio. El objetivo es evidencia útil, no formalidad por sí misma.

## 4. Resolución de desacuerdos técnicos

Cuando existan alternativas incompatibles:

1. **Precisar la decisión:** identificar la necesidad, las restricciones y los supuestos.
2. **Exponer opciones:** recoger alternativas humanas y de IA sin ocultar incertidumbres.
3. **Evaluar fundamentos:** contrastar eficacia, eficiencia, oportunidad, seguridad, mantenibilidad, costo y riesgos según corresponda.
4. **Probar cuando sea razonable:** usar experimentos pequeños, prototipos, pruebas o fuentes verificables antes de comprometer una solución costosa.
5. **Decidir y registrar:** el responsable humano deja constancia de la opción escogida, sus motivos y la evidencia disponible.
6. **Revisar ante nueva información:** actualizar o revertir la decisión cuando los resultados contradigan los supuestos.

La ausencia de evidencia suficiente debe señalarse explícitamente; no se disfraza de certeza.

## 5. Trazabilidad mínima de decisiones relevantes

Un registro de decisión debería permitir reconstruir, sin documentación innecesaria:

- **Necesidad:** problema y persona o colectivo beneficiario.
- **Alternativas:** opciones consideradas y sus principales consecuencias.
- **Fundamento:** criterios, riesgos, restricciones, referencias o pruebas utilizadas.
- **Responsable y fecha:** quién tomó la decisión y cuándo.
- **Resultado esperado:** qué se intenta mejorar y cómo se verificará.
- **Resultado observado:** qué ocurrió realmente, cuando exista evidencia posterior.

No toda modificación requiere un documento DEC independiente. Una explicación en una PR o un commit puede ser suficiente para cambios menores; decisiones de mayor impacto pueden necesitar análisis y aprobación explícitos.

## 6. Cómo se demostrará el valor del modelo

Este modelo **no se considera validado** por quedar escrito en el repositorio. Deberá ponerse a prueba con proyectos y funcionalidades reales, registrando al menos:

- Satisfacción de necesidades y criterios de aceptación del beneficiario.
- Tiempo hasta disponer de una entrega utilizable y oportuna.
- Defectos encontrados antes y después de la entrega.
- Esfuerzo humano, costo de coordinación y mantenimiento.
- Facilidad para comprender, corregir y auditar las decisiones.

Se contrastarán los resultados con alternativas existentes cuando sea viable, sin atribuir a la metodología diferencias que puedan provenir del proyecto, equipo, modelo de IA o herramientas.

## 7. Límites y preguntas abiertas

- ¿Cómo graduar el rigor de una decisión según su riesgo sin crear burocracia?
- ¿Qué criterios permiten delegar tareas a la IA y cuáles requieren revisión humana inmediata?
- ¿Qué constituye evidencia suficiente de satisfacción del cliente, además de pruebas automatizadas?
- ¿Cómo registrar desacuerdos y aprendizajes preservando privacidad, secretos y propiedad intelectual?
- ¿Qué experimentos permitirán falsar o modificar esta propuesta?

## 8. Estado de aprobación

**Pendiente de discusión y decisión humana.** Esta propuesta no modifica automáticamente los cuatro principios del README, no establece una certificación ni obliga a adoptar un proveedor o herramienta. Su integración a `main` requerirá revisión y aprobación del mantenedor de HUMENGIA.
