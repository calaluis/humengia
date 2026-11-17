# DFT — Fundamentos y diseño del piloto

**Estado.** Práctica opcional para propiedades críticas, adoptada por decisión del mantenedor. La evidencia experimental se limita al piloto reportado.  
**Trazabilidad.** [Issue #10](https://github.com/calaluis/humengia/issues/10) · [Ejecución del piloto](https://github.com/calaluis/humengia/issues/10#issuecomment-6938061723) · [Decisión del mantenedor](https://github.com/calaluis/humengia/issues/10#issuecomment-6938108671) · [Marco teórico](./marco-teorico.md) · [Registro exploratorio de pilotos](./registro-pilotos.md).

La **Demostración Funcional Trazable (DFT)** es una práctica de HUMENGIA para documentar cómo se verifica una propiedad crítica del software. Reúne una afirmación acotada, sus premisas, el origen del resultado esperado, una prueba reproducible y la evidencia que justifica la conclusión.

## Respaldo normativo y antecedentes

| Elemento | Referencia y alcance |
| --- | --- |
| Oráculo de prueba | **ISO/IEC/IEEE 29119-1:2022, §4.1.10**. Una especificación, un experto u otra fuente puede servir para determinar el veredicto. El oráculo también puede ser una condición comprobable. Para la DFT, **derivación independiente** significa obtener el resultado esperado sin reutilizar la lógica productiva que se evalúa. La independencia del §4.1.11 se refiere a la separación entre quienes prueban y quienes desarrollan. [Ficha ISO](https://www.iso.org/standard/81291.html) · [Plataforma de consulta ISO](https://www.iso.org/obp/ui/#iso:std:iso-iec-ieee:29119:-1:ed-2:v1:en). |
| Prueba diferencial o *back-to-back* | **ISO/IEC/IEEE 29119-1:2022, §§3.10 y 4.4.9**. Una implementación alternativa genera resultados esperados con las mismas entradas. Weyuker describió en 1982 el **pseudo-oráculo**, un programa escrito de forma independiente para la misma especificación. Barr y otros revisaron varios tipos de oráculos en 2015. [Weyuker, 1982](https://doi.org/10.1093/comjnl/25.4.465) · [Barr et al., 2015](https://doi.org/10.1109/TSE.2014.2372785). |
| Prueba metamórfica | **ISO/IEC/IEEE 29119-1:2022, §§3.48–3.49**. Se genera un caso a partir de otro y se comprueba cómo la transformación de la entrada debe afectar la salida. Chen, Cheung y Yiu documentaron este enfoque en 1998. [Informe técnico HKUST-CS98-01](https://cse.hkust.edu.hk/faculty/scc/publ/CS98-01-metamorphictesting.pdf). |
| Documentación trazable | **ISO/IEC/IEEE 29119-3:2021, §§8.2.7, 8.3, 8.4 y 8.9**. Los apartados abarcan trazabilidad del modelo de prueba, especificación del caso y del procedimiento, resultados observados y veredicto. [Ficha ISO](https://www.iso.org/standard/79429.html) · [Vista previa ANSI](https://webstore.ansi.org/preview-pages/ISO/preview_ISO%2BIEC%2BIEEE%2B29119-3-2021.pdf). |
| Afirmación, argumento y evidencia | **ISO/IEC/IEEE 15026-2:2022, §3.1.1**. La definición de caso de aseguramiento vincula una afirmación, un argumento y evidencia dentro de un contexto. Sirve de antecedente estructural para la DFT. [Ficha ISO](https://www.iso.org/standard/80625.html) · [Vista previa](https://assets.vde-verlag.de/iec-normen/preview-pdf/info_isoiecieee15026-2%7Bed2.0%7Den.pdf). |
| Sensibilidad ante defectos | Las **pruebas de mutación** evalúan si una prueba detecta cambios deliberados en el programa. El piloto propone introducir un solo defecto de orden para observar si el veredicto cambia. [Jia y Harman, 2011](https://doi.org/10.1109/TSE.2010.62). |

Estas referencias fundamentan los componentes. Esta revisión documental se limita a las definiciones y apartados consultados. Una declaración de conformidad requeriría una evaluación específica de los requisitos aplicables.

## Diseño de referencia del piloto sintético sobre saldos

**Propiedades.** Con un saldo inicial fijo, los mismos movimientos con sus importes firmados y sus multiplicidades y aritmética exacta, cualquier permutación conserva el saldo final. Cada saldo intermedio depende de los movimientos ya aplicados. La prueba del orden requiere que el contrato establezca el criterio de desempate. El supuesto de la primera propiedad excluye reglas por las cuales el orden cambie qué movimientos se aceptan o sus importes.

$$
S_0 + \sum_{i=1}^{n} m_i = S_0 + \sum_{i=1}^{n} m_{\pi(i)}
$$

Cualquier permutación se puede formar mediante intercambios de elementos adyacentes. La asociatividad permite reagrupar un par de movimientos consecutivos y la conmutatividad conserva su suma al intercambiarlos. Por composición, el saldo final se conserva para cualquier permutación. Esta demostración justifica la propiedad del modelo matemático. Los resultados de las ejecuciones sustentan afirmaciones sobre el comportamiento observado en los casos probados.

**Datos y oráculo.** Saldo inicial de $100. El movimiento ID 10 abona $30 y el ID 20 carga $10. Ambos tienen la misma fecha y hora. La regla del ejemplo desempata por ID ascendente. El cálculo manual da **$130 → $120** con cualquier orden de entrada. Si la variante defectuosa omite el desempate y conserva el orden de entrada inverso, produce **$90 → $120**. Las cifras son resultados esperados del diseño de referencia.

1. Ejecutar las dos permutaciones de entrada con la implementación de referencia. Registrar el orden observado, los saldos intermedios y el saldo final.
2. Repetir con la variante que omite el desempate. Comprobar si la relación metamórfica del saldo final se conserva y si el oráculo de la secuencia detecta la discrepancia.
3. Ejecutar también las pruebas habituales sobre las mismas versiones. Registrar cuáles detectan el defecto y cuánto cuesta preparar y mantener el caso. Si la suite habitual ya verifica la misma propiedad, evaluar el aporte adicional de la DFT en la explicación y en la trazabilidad. Registrar el veredicto que se observe y su alcance.

## Resultados del piloto

El ensayo adaptó el diseño al contrato de una ruta de servicio de un libro mayor, que ordena los comprobantes del mismo día y grupo por número natural. En la primera ronda, la DFT detectó la comparación textual, que puso «10» antes de «2». La omisión del orden por número quedó enmascarada para la DFT porque el orden por ID daba la misma secuencia. En la segunda ronda, se mantuvieron los movimientos y se eligieron IDs en orden contrario al de los números. La variante de omisión produjo **90 → 120** con ambos órdenes de inserción, frente a **130 → 120** del original.

La suite preexistente seleccionada detectó ambas variantes. El saldo final fue **120** en todos los casos. La DFT aportó trazabilidad del cálculo esperado y mostró por qué los datos deben hacer que la regla bajo prueba y el criterio de respaldo den resultados diferentes. El [registro de ambas rondas](https://github.com/calaluis/humengia/issues/10#issuecomment-6938061723) recoge los veredictos y el esfuerzo informado. El alcance se limita al caso sintético y la ruta de servicio ensayada. La aceptación desde la interfaz requiere la evidencia prevista por UI-1.

## Cuándo aplicarla

La [decisión del mantenedor](https://github.com/calaluis/humengia/issues/10#issuecomment-6938108671) adopta la **DFT como práctica opcional para propiedades críticas**, cuando aporte una derivación del resultado esperado que haga falta documentar o ayude a diseñar datos que distingan un defecto concreto.

La estructura se puede adaptar al nivel de prueba y al riesgo. El oráculo independiente conviene para cálculos y reglas críticas. Una prueba metamórfica requiere una relación esperada entre ejecuciones. La mutación mide la sensibilidad de la prueba a un defecto deliberado. En rendimiento, el criterio puede ser un umbral bajo carga y entorno definidos, con mediciones repetidas. Para declarar disponible una capacidad de usuario, la [regla UI-1 de DEC-004](../decisiones/DEC-004-aceptacion-funcional-interfaz.md#2-regla-propuesta) pide comprobar el recorrido completo desde la interfaz autorizada y su resultado observable.

Para documentar la DFT puede bastar una ficha breve en el artefacto existente. **Afirmación y enlace al requisito · Premisas · Origen y derivación del esperado · Datos y pasos reproducibles · Resultado observado y evidencia · Veredicto y límites.** En una prueba rutinaria, un resultado esperado y observado puede ser respaldo suficiente.
