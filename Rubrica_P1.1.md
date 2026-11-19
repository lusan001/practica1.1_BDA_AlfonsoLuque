# Rúbrica pública — Práctica P1.1 (evaluación por CE)

**Big Data aplicado (5075)** · **GitHub Classroom** · **Corrección manual**. Este documento es Markdown estándar y contiene descriptores concretos para los cuatro niveles.

**Importante:** la nota global orientativa de P1.1 no sustituye a las notas específicas de los CE. Cada indicador se asigna a un único CE, sin duplicidades.

| CE | Indicadores | Máximo | Cálculo de nota del CE sobre 10 |
|---|---|---:|---|
| 1.a | 1.1, 3.2 | 2,0 | subtotal / 2,0 × 10 |
| 1.c | 4.1, 4.2, 4.3 | 2,5 | subtotal / 2,5 × 10 |
| 2.a | 1.2, 1.3 | 1,6 | subtotal / 1,6 × 10 |
| 2.d | 3.1 | 0,9 | subtotal / 0,9 × 10 |
| 3.a | 2.1 | 0,6 | subtotal / 0,6 × 10 |
| 3.b | 2.2 | 0,8 | subtotal / 0,8 × 10 |
| 3.c | 2.3 | 1,2 | subtotal / 1,2 × 10 |
| 3.d | 2.4 | 0,4 | subtotal / 0,4 × 10 |
| **Total** | **12 indicadores** | **10,0** | **8 notas CE separadas** |

## 1. Niveles de desempeño y rúbricas


La práctica se califica de **0 a 10 puntos**, mediante la revisión de la memoria técnica y las evidencias depositadas en el repositorio de Classroom 50. **No se utilizará autocorrección automática.** Los cuatro hitos tienen un máximo de 2,5, 3,0, 2,0 y 2,5 puntos, respectivamente.

La rúbrica distingue **cuatro niveles de desempeño por cada indicador**, con puntuaciones explícitas. En cada fila se asigna **una sola puntuación**, correspondiente al nivel mejor acreditado en la entrega. La nota total resulta de sumar los puntos de las doce filas. No se puntúa por contar palabras clave ni por incluir una captura sin interpretar lo que muestra.

> **Cómo utilizar la rúbrica**
> - **Nivel 4, excelente:** ejecución o análisis completo, técnicamente correcto y bien justificado.
> - **Nivel 3, adecuado:** se alcanza el propósito del indicador, con alguna omisión o imprecisión menor.
> - **Nivel 2, parcial:** existen evidencias o ideas correctas, pero faltan aspectos relevantes o la interpretación es incompleta.
> - **Nivel 1, insuficiente:** falta la evidencia necesaria, no se responde o la respuesta presenta errores que impiden acreditar el aprendizaje.
>
> Las puntuaciones representan anclajes de corrección. Para reconocer trabajos situados entre dos descriptores, el profesor puede asignar una **puntuación intermedia**, sin superar el máximo de la fila, y dejar una breve justificación. La ausencia de una captura concreta no implica automáticamente cero cuando el mismo hecho está acreditado por otra evidencia verificable.
>
### 4.1 Rúbrica del hito 1. Arquitectura de HDFS y disponibilidad (2,5 puntos)

| Indicador | Nivel 4 · Excelente | Nivel 3 · Adecuado | Nivel 2 · Parcial | Nivel 1 · Insuficiente |
|---|---|---|---|---|
| **1.1. Lectura, metadatos y ubicación de bloques · CE 1.a** (máx. **0,9**) | **0,9**. Identifica B4 y B5, sus ubicaciones y el factor 3; describe correctamente la consulta al NameNode y la lectura directa desde DataNodes, diferenciando metadatos y contenido. | **0,7**. Reconstruye correctamente el archivo y el flujo de lectura, con alguna omisión menor sobre ubicaciones o funciones de los nodos. | **0,4**. Identifica algunos bloques o nodos, pero confunde parte del recorrido de datos o explica de forma incompleta el papel del NameNode. | **0**. No identifica los bloques del archivo o atribuye al NameNode la transferencia habitual de los datos sin corregir el error. |
| **1.2. Caída de los nodos 1 y 4 · CE 2.a** (máx. **1,0**) | **1,0**. Analiza los dos archivos bloque a bloque, identifica las réplicas supervivientes, concluye si son legibles y distingue pérdida de réplicas, disponibilidad y reconstrucción de redundancia. | **0,75**. Concluye correctamente la disponibilidad de ambos archivos y justifica la mayor parte de las ubicaciones; presenta alguna imprecisión menor en la recuperación de réplicas. | **0,5**. Reconoce parte de las réplicas disponibles, pero omite un bloque o confunde disponibilidad con mantenimiento del factor de replicación. | **0**. No analiza ambos archivos o afirma pérdidas o recuperaciones incompatibles con el esquema sin justificación. |
| **1.3. Localidad de los datos (B5) · CE 2.a** (máx. **0,6**) | **0,6**. Identifica nodos 1, 3 y 4 y explica cómo un motor que admita planificación por localidad puede preferir ejecutar allí, sin presentarlo como garantía universal. | **0,45**. Identifica los nodos correctos y explica la ventaja de proximidad, aunque omite algún matiz sobre la planificación. | **0,25**. Menciona parcialmente las ubicaciones o define localidad de forma genérica sin relacionarla bien con B5. | **0**. No localiza B5 ni explica el principio de localidad. |

**Subtotal máximo del hito 1: 2,5 puntos.**

### 4.2 Rúbrica del hito 2. Integridad y tolerancia a fallos (3,0 puntos)

| Indicador | Nivel 4 · Excelente | Nivel 3 · Adecuado | Nivel 2 · Parcial | Nivel 1 · Insuficiente |
|---|---|---|---|---|
| **2.1. Estado inicial, bloques y replicación · CE 3.a** (máx. **0,6**) | **0,6**. Documenta `dfsadmin`, `fsck` y `du`, distingue bloque lógico, réplicas físicas y capacidad utilizada, y explica correctamente por qué un archivo pequeño no reserva 128 MiB por réplica. | **0,45**. Aporta las comprobaciones y distingue tamaño lógico y replicación, con alguna omisión en el análisis. | **0,25**. Aporta salidas parciales o confunde alguna magnitud, pero reconoce el estado básico del clúster. | **0**. No acredita el estado del clúster o interpreta incorrectamente los conceptos principales. |
| **2.2. Interrupción y recuperación de lectura · CE 3.b** (máx. **0,8**) | **0,8**. Detiene y restaura un DataNode, presenta evidencias de lectura, compara SHA-256, explica el uso de una réplica alternativa y relaciona el riesgo de integridad con el volumen de bloques/datos. | **0,6**. Realiza la prueba y documenta recuperación o fallo con una explicación mayormente correcta; falta alguna evidencia secundaria. | **0,35**. Ejecuta parte de la prueba, pero no acredita adecuadamente la integridad del archivo o confunde un aviso de conexión con un fallo definitivo. | **0**. No documenta la prueba ni aporta un análisis técnico suficiente. |
| **2.3. Corrupción física controlada y diagnóstico · CE 3.c** (máx. **1,2**) | **1,2**. Identifica el bloque real y su réplica, distingue archivo de datos y `.meta`, comprueba las condiciones de seguridad, reconoce la verificación mediante checksums de HDFS (distinta de SHA-256), altera únicamente la réplica de ensayo y analiza registros y lectura posterior. | **0,9**. Documenta las operaciones seguras y los resultados principales, con alguna omisión en metadatos, checksums o diagnóstico. | **0,5**. Localiza el bloque o aporta verificaciones parciales, pero el análisis de la corrupción es limitado; o detiene justificadamente la prueba ante un riesgo real y documenta las comprobaciones efectuadas. | **0**. No identifica el bloque ni aporta verificaciones útiles; o modifica indiscriminadamente bloques, originales o archivos `.meta` incumpliendo las precauciones. |
| **2.4. Integridad, disponibilidad y reconstrucción · CE 3.d** (máx. **0,4**) | **0,4**. Distingue las funciones previas de cliente, NameNode y DataNode y sitúa correctamente la verificación de checksums; diferencia detección de corrupción, lectura sana y reposición de redundancia. | **0,3**. Diferencia correctamente los procesos, aunque falta algún matiz sobre la reparación. | **0,15**. Reconoce parte de la diferencia, pero utiliza indistintamente integridad, disponibilidad y reparación. | **0**. Identifica erróneamente `fsck` con una reparación automática o no aporta conclusiones. |

**Subtotal máximo del hito 2: 3,0 puntos.**

> **Incidencias en el experimento de corrupción**
> No se exige provocar una alteración cuando falten las condiciones de seguridad indicadas en el laboratorio. Si el alumno interrumpe justificadamente el procedimiento, el profesor valorará las verificaciones efectivamente realizadas, el diagnóstico del impedimento y la argumentación técnica. **No se asignará el máximo automáticamente por detener la prueba**, pero tampoco se penalizará que se haya evitado una manipulación insegura. Las advertencias o estados concretos de `fsck` pueden variar y no constituyen por sí solos un requisito de calificación.
>
### 4.3 Rúbrica del hito 3. Almacenamiento de objetos con MinIO (2,0 puntos)

| Indicador | Nivel 4 · Excelente | Nivel 3 · Adecuado | Nivel 2 · Parcial | Nivel 1 · Insuficiente |
|---|---|---|---|---|
| **3.1. Operaciones y comprobación del objeto · CE 2.d** (máx. **0,9**) | **0,9**. Configura `mc`, crea o reutiliza el bucket, conserva el CSV original con la clave indicada, acredita existencia/metadatos mediante `mc stat` y explica por qué aplazar su explotación mantiene opciones de uso posteriores. | **0,7**. Realiza correctamente el almacenamiento y aporta evidencias suficientes, con alguna omisión menor en la documentación. | **0,4**. Configura parte del acceso o sube el objeto, pero faltan comprobaciones claras de ruta y metadatos. | **0**. No acredita el almacenamiento del objeto en MinIO. |
| **3.2. Modelo S3 y comparación con HDFS · CE 1.a** (máx. **1,1**) | **1,1**. Distingue alias, bucket y clave; explica correctamente la semántica del prefijo, compara modelos de acceso y organización con HDFS y razona su aplicación al contexto empresarial. | **0,8**. Explica las diferencias esenciales con ejemplos, aunque omite algún matiz de consistencia o comparación. | **0,45**. Reconoce algunos conceptos, pero confunde alias, carpetas y claves o presenta una comparación superficial. | **0**. Confunde los elementos básicos del almacenamiento de objetos o no aporta razonamiento. |

**Subtotal máximo del hito 3: 2,0 puntos.**

### 4.4 Rúbrica del hito 4. CSV y Parquet (2,5 puntos)

| Indicador | Nivel 4 · Excelente | Nivel 3 · Adecuado | Nivel 2 · Parcial | Nivel 1 · Insuficiente |
|---|---|---|---|---|
| **4.1. Generación y conversión de datos · CE 1.c** (máx. **0,7**) | **0,7**. Genera el CSV de 100.000 transacciones, produce Parquet con compresión ZSTD y documenta de forma reproducible los comandos y archivos resultantes. | **0,5**. Obtiene correctamente ambos formatos, con pequeñas omisiones de evidencias o reproducibilidad. | **0,25**. Acredita solo una parte de la preparación o no justifica adecuadamente el formato resultante. | **0**. No demuestra que se hayan generado los archivos solicitados. |
| **4.2. Tamaños, bloques y cálculo de reducción · CE 1.c** (máx. **1,0**) | **1,0**. Presenta mediciones reales de ambos formatos, tamaños lógicos y replicados, número de bloques y ubicaciones; calcula correctamente la reducción usando unidades coherentes. | **0,75**. Completa las mediciones esenciales y calcula la reducción, con alguna omisión menor o redondeo poco claro. | **0,4**. Aporta una comparación parcial o mezcla unidades y tamaños, pero permite identificar al menos algunas diferencias reales. | **0**. No aporta mediciones verificables o sustituye los resultados por cifras inventadas. |
| **4.3. Interpretación de formatos y resultados · CE 1.c** (máx. **0,8**) | **0,8**. Explica con propiedad la organización columnar, el tipado, la codificación y ZSTD; distingue reducción de tamaño de rendimiento de consulta y plantea qué habría que medir para comparar consultas. | **0,6**. Interpreta correctamente el menor o mayor tamaño y distingue ocupación de rendimiento, con alguna explicación técnica incompleta. | **0,3**. Explica de manera genérica la compresión o supone que un archivo más pequeño implica siempre consultas más rápidas. | **0**. No interpreta las mediciones o presenta conclusiones técnicas incompatibles con los datos. |

**Subtotal máximo del hito 4: 2,5 puntos.**

### 4.5 Hoja de puntuación del profesor

Esta tabla permite registrar la nota de cada indicador sin duplicar puntuaciones. Puede copiarse a una hoja de cálculo o emplearse directamente durante la revisión del repositorio.

| Indicador | Máximo | Puntuación asignada |
|---|---:|---:|
| 1.1. Lectura y bloques | 0,9 | |
| 1.2. Disponibilidad ante fallos | 1,0 | |
| 1.3. Localidad del dato | 0,6 | |
| **Subtotal hito 1** | **2,5** | |
| 2.1. Estado y replicación | 0,6 | |
| 2.2. Interrupción de un DataNode | 0,8 | |
| 2.3. Corrupción controlada | 1,2 | |
| 2.4. Interpretación de integridad y reparación | 0,4 | |
| **Subtotal hito 2** | **3,0** | |
| 3.1. Operaciones con MinIO | 0,9 | |
| 3.2. Modelo S3 y comparación | 1,1 | |
| **Subtotal hito 3** | **2,0** | |
| 4.1. Generación y conversión | 0,7 | |
| 4.2. Mediciones y cálculos | 1,0 | |
| 4.3. Interpretación de formatos | 0,8 | |
| **Subtotal hito 4** | **2,5** | |
| **CALIFICACIÓN TOTAL** | **10,0** | |

**Criterio general de corrección:** se valorarán la correspondencia entre las evidencias y los resultados reales, la precisión técnica, la interpretación y la justificación. Los archivos y las capturas sirven para acreditar el trabajo, pero no sustituyen al razonamiento. Classroom 50 se utiliza para distribuir la actividad y gestionar su entrega; **la nota la asignará el profesor**, no GitHub Actions.
