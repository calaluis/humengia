# DEC-003 — Continuidad tecnológica en proyectos existentes

**Estado:** Propuesta operativa v0.1 para revisión humana; no validada empíricamente  
**Fecha:** 2026-11-07  
**Ámbito:** Evolución, mantenimiento y ampliación de proyectos existentes con colaboración humano–IA  
**Responsable de aceptación:** Mantenedor humano de HUMENGIA  
**Relación:** [Principios fundacionales](../README.md) · [DEC-001](./DEC-001-colaboracion-humano-ia.md) · [DEC-002](./DEC-002-delegacion-revision-humano-ia.md) · [Propuesta HUMENGIA v0.1](../PROPUESTA-HUMENGIA-v0.1.md)

## 1. Problema

HUMENGIA es tecnológicamente agnóstico: no prescribe un lenguaje, framework, runtime o plataforma universal. Esa neutralidad del marco puede interpretarse erróneamente como libertad para introducir una tecnología nueva dentro de un proyecto existente cuando una IA la considera más cómoda, rápida o familiar.

En mantenimiento y evolución, una decisión de ese tipo puede crear un segundo runtime, duplicar herramientas de pruebas y despliegue, aumentar dependencias y conocimientos necesarios para operar el sistema, fragmentar la observabilidad y elevar el costo de mantenimiento sin que el cliente haya solicitado ese cambio arquitectónico.

La continuidad tecnológica debe, por tanto, formar parte de los límites que la IA identifica antes de implementar.

## 2. Decisión

**CT-1 — Continuidad tecnológica.** Cuando un proyecto existente está construido sobre una tecnología o ecosistema determinado, HUMENGIA debe respetar esa base durante su evolución, corrección, mantenimiento y ampliación.

La regla comprende no solo el código funcional del producto, sino también los artefactos mantenibles asociados al proyecto:

- herramientas internas y utilidades operativas;
- scripts;
- automatizaciones;
- pruebas y harnesses;
- componentes de build, integración o soporte;
- servicios o componentes auxiliares que pasen a formar parte del mantenimiento del sistema.

Si el proyecto ya es deliberadamente políglota, se respetan los límites y tecnologías que ya forman parte de su arquitectura; la regla impide introducir **un ecosistema adicional** por conveniencia no autorizada.

**No constituye justificación suficiente** la preferencia del agente, la rapidez de implementación, la disponibilidad de una librería conocida, la comodidad de generar código en otro lenguaje ni una limitación de la propia IA.

## 3. Excepción

La excepción operativa de esta decisión es explícita:

> Si el cliente o responsable competente decide que el sistema o subsistema debe construirse desde cero, la selección tecnológica vuelve a ser una decisión de arquitectura y puede evaluarse sin quedar obligada por el stack anterior.

La IA no puede inferir por sí sola que una tarea equivale a una reconstrucción desde cero ni usar una herramienta auxiliar para eludir esta regla. La decisión debe provenir del cliente o del responsable humano competente y quedar trazable cuando tenga consecuencias relevantes.

## 4. Gate previo a implementar

Antes de introducir o modificar código mantenible, la IA y el responsable aplican este control:

1. **Identificar el stack existente.** Revisar solución/proyecto, manifiestos, dependencias, build, pruebas, documentación y tooling ya adoptado.
2. **Clasificar la propuesta.** Determinar si la implementación permanece dentro del ecosistema existente o agrega lenguaje, runtime, framework o plataforma mantenible nueva.
3. **Aplicar continuidad.**
   - Si permanece dentro del stack existente, continuar con los controles de riesgo y verificación normales.
   - Si agrega un ecosistema nuevo y no existe decisión explícita de reconstrucción desde cero, **detener la implementación** y rediseñar la solución dentro del stack existente.
   - Si existe decisión explícita de reconstrucción desde cero, tratar la selección tecnológica como una nueva decisión arquitectónica con fundamentos, alternativas y evidencia proporcionales.
4. **No usar tooling como excepción implícita.** Que un componente sea llamado “script”, “herramienta auxiliar”, “prueba” o “automatización” no lo excluye del gate si queda como parte mantenible del proyecto.
5. **Registrar solo cuando aporte valor.** Una PR, issue, commit o DEC existente puede bastar para dejar constancia del stack identificado, una excepción autorizada o una decisión arquitectónica; no se exige documentación duplicada.

## 5. Relación con otras decisiones HUMENGIA

- **DEC-001 — Agnosticismo tecnológico:** HUMENGIA no impone un stack universal. CT-1 aclara que esa neutralidad del marco no sustituye las restricciones y decisiones tecnológicas de un proyecto existente.
- **DEC-002 — Delegación y revisión:** introducir un ecosistema nuevo es una decisión que la IA no puede autorizar por conveniencia. Si aparece durante una tarea, se detiene la acción afectada y se eleva al responsable humano, aplicando I/R/V y las políticas del proyecto.
- **Reglas del cliente y del proyecto:** continúan prevaleciendo. CT-1 no obliga a migrar componentes heterogéneos que ya formen parte legítima de la arquitectura ni autoriza reescrituras.

## 6. Criterios de verificación

Una revisión de continuidad tecnológica debe poder responder:

- ¿Se identificó correctamente el stack que el proyecto ya usa y mantiene?
- ¿El cambio introduce un lenguaje, runtime, framework o plataforma adicional?
- ¿La nueva tecnología era realmente parte de la arquitectura existente?
- Si se sale del stack, ¿existe una decisión explícita del cliente de reconstruir desde cero?
- ¿Se intentó justificar la desviación solo por comodidad, rapidez o preferencia del agente?
- ¿Scripts, pruebas y tooling mantenible respetan el mismo criterio?
- ¿La excepción, si existe, quedó tratada como decisión arquitectónica y no como hecho implícito?

## 7. Hipótesis y límites

CT-1 es una regla operativa propuesta para reducir fragmentación y costo accidental en proyectos existentes. Su utilidad deberá observarse en casos reales y puede requerir ajustes si impide una solución necesaria o produce sobrecarga desproporcionada.

Esta decisión **no afirma** que una tecnología existente sea siempre la mejor tecnología posible, ni que los proyectos deban permanecer indefinidamente en su stack original. Establece quién puede autorizar la ruptura de continuidad y evita que una IA la produzca unilateralmente durante una tarea de mantenimiento.

## 8. Estado de aprobación

Esta DEC queda propuesta para revisión humana mediante PR. Su integración en `main` significará aceptar CT-1 para experimentación controlada dentro de HUMENGIA; no demostrará por sí sola una mejora causal de calidad, productividad o mantenibilidad.
