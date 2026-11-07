# DEC-004 — Aceptación funcional desde la interfaz de usuario (UI-1)

**Estado:** Propuesta para revisión humana; no adoptada ni validada empíricamente  
**Fecha:** 2026-11-07  
**Ámbito:** Aplicaciones web, de escritorio y móviles con interacción usuaria  
**Responsable de aceptación:** Mantenedor humano de HUMENGIA  
**Relación:** [Principios fundacionales](../README.md) · [Propuesta HUMENGIA v0.1](../PROPUESTA-HUMENGIA-v0.1.md) · [Issue #8](https://github.com/calaluis/humengia/issues/8)

## 1. Problema observado

Un incremento puede tener servicios, controladores, persistencia, pruebas automatizadas y resultados técnicos correctos, pero seguir sin estar disponible para quien utiliza la aplicación. Una navegación inexistente, inaccesible o deshabilitada impide completar el trabajo, aunque el código subyacente funcione.

La observación de origen se comunica como aprendizaje generalizable; **no se publica ni se da por verificada en este repositorio evidencia de proyectos privados**.

## 2. Regla propuesta

**UI-1 — Aceptación funcional desde la interfaz.** En aplicaciones destinadas a utilizarse mediante una interfaz de usuario —web, escritorio o móvil— una funcionalidad **no debe declararse terminada como capacidad operativa para el cliente** hasta que el usuario autorizado pueda ejecutar el flujo acordado de extremo a extremo a través de esa interfaz y comprobar su resultado.

Se debe distinguir explícitamente entre:

1. **Implementación interna:** clases, servicios, controladores y datos desarrollados.
2. **Verificación técnica:** pruebas de componentes, integración, seguridad y otras comprobaciones pertinentes.
3. **Capacidad efectiva de uso:** operación completa desde la interfaz usuaria, según el propósito y los permisos acordados.

Los dos primeros hitos pueden aprobarse como incrementos parciales, **sin equivaler** al tercero.

## 3. Criterios observables de aceptación

Para el flujo incluido en el alcance de cada incremento:

- **Accesibilidad y entrada:** el usuario autorizado puede alcanzar la función desde la navegación o recorrido normal, sin operaciones exclusivas de desarrolladores.
- **Operación completa:** las acciones previstas se realizan desde la interfaz sin requerir SQL, scripts ni herramientas de desarrollo.
- **Interacción y permisos:** captura, consultas, cambios, confirmaciones, controles de acceso y validaciones corresponden al contrato de uso.
- **Retroalimentación:** el usuario comprende el resultado, progreso relevante, errores y la forma de corregirlos.
- **Efecto comprobable:** la acción persiste o produce el efecto previsto y este puede verificarse desde la experiencia de uso.
- **Validación pertinente:** se demuestra el recorrido en la plataforma aplicable; cuando se requiera criterio de negocio, debe validarlo el cliente o un experto competente, sin sustituirlo por una afirmación de la IA.

Una opción de menú visible pero deshabilitada o sin comportamiento real **no** prueba funcionalidad operativa. Tampoco el éxito de la batería de pruebas permite inferir una aceptación de usuario no realizada.

## 4. Alcance y límites

- Se aplica a **web, escritorio y móvil**, sin exigir un framework, tecnología, diseño visual o mecanismo de pruebas específico.
- Las interfaces pueden incluir formas de interacción asistida o accesible; el criterio es la capacidad de operar para el público previsto, no una modalidad visual única.
- Los sistemas cuyo contrato de uso es una **API, CLI u otra interfaz no gráfica** deben evaluarse por su interfaz contractual correspondiente. No se les impone artificialmente una UI gráfica.
- La demostración funcional **complementa**, no reemplaza, seguridad, pruebas técnicas y corrección del dominio.
- No exige entregar toda la aplicación de una vez: la aceptación se refiere al **incremento y recorrido explícitamente comprometidos**. Componentes internos pueden darse por terminados en calidad de tales, no como funciones de usuario.
- Se aprovechan pruebas y evidencias ya existentes, sin convertir cada entrega en una nueva auditoría o documento obligatorio.

## 5. Aplicación a la revisión HUMENGIA

En las actividades **Construir, Verificar y Contrastar** del ciclo HUMENGIA, incluir para incrementos con interfaz las preguntas:

1. ¿Qué recorrido debe poder ejecutar el usuario final?
2. ¿Se puede iniciar y completar enteramente desde la interfaz autorizada?
3. ¿Se observaron las validaciones, los permisos, la respuesta al usuario y el resultado persistente?
4. ¿Quién verificó el recorrido y con qué evidencia?
5. Si solo se ha probado el backend, ¿se presenta honradamente como **componente verificado** y no como funcionalidad disponible?

La evidencia puede ser una prueba de aceptación, demostración, grabación o registro breve dentro de la PR existente. Ningún formato adicional es obligatorio.

## 6. Relación con HUMENGIA

Esta propuesta concreta el principio de **Propósito humano**, la **Ingeniería demostrable** y la distinción de R4 entre artefacto implementado, comportamiento técnico probado y capacidad efectiva de uso. No reemplaza las decisiones existentes ni modifica los niveles N1–N3.

## 7. Estado de decisión

La regla UI-1 queda propuesta en [Issue #8](https://github.com/calaluis/humengia/issues/8) para revisión humana.

**La creación o eventual fusión de esta DEC no demuestra por sí misma beneficios empíricos.** Si se aprueba, la regla quedará adoptada para experimentación controlada y deberá contrastarse con resultados de uso, efectos no deseados y sobrecarga. No autoriza cambios en otros proyectos ni declara aprobaciones de clientes inexistentes.
