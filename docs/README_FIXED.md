# Plan de Ejecución del Bootcamp: Introducción al Lakehouse de Databricks

## 1. Resumen Ejecutivo

- **Título del Bootcamp:** Introducción al Lakehouse de Databricks
- **Duración Total:** 4 horas (divididas en 4 clases de 1 hora).
- **Audiencia Objetivo:** Estudiantes técnicos con conocimientos fundamentales de SQL y Python.
- **Objetivo Principal:** Enseñar a los estudiantes los problemas fundamentales de los datos
  modernos (el "Por qué") y cómo la plataforma Databricks Lakehouse los resuelve (el "Qué"). Los
  estudiantes obtendrán experiencia práctica construyendo un pipeline de datos fundacional.
- **Objetivo de Negocio:** Identificar estudiantes de alto potencial para reclutamiento, observando
  sus habilidades de resolución de problemas, aptitud técnica y nivel de participación durante los
  laboratorios prácticos.
- **Herramientas:** Databricks Free Edition.
- **Recursos:**
  - [Databricks Free Edition](https://www.databricks.com/learn/free-edition)
  - [Documentación Oficial](https://docs.databricks.com/)
  - [Delta Lake Docs](https://docs.delta.io/latest/index.html)
  - [Medallion Architecture](https://www.databricks.com/glossary/medallion-architecture)

## 2. Prerrequisitos y Logística

- **Prerrequisitos del Estudiante:** Entendimiento básico de SQL (SELECT, WHERE, GROUP BY) y Python
  (variables, funciones, estructuras de datos).
- **Prerrequisitos del Instructor:**
  1. Un dataset público de Argentina previamente validado (ej. de
     [datos.gob.ar](https://datos.gob.ar/)), guardado como un archivo CSV "sucio" (con datos
     desordenados).
  2. Una versión completa de los notebooks del laboratorio para usar como referencia ("Answer key").
  3. Presentaciones (slides) para la Clase 1 y la Clase 4.
  4. Video de backup (5 minutos) mostrando el setup completo.
- **Nota Importante:** Las sesiones prácticas de 1 hora son _sprints_. Se proveerá a los estudiantes
  notebooks "iniciales" con instrucciones y código base (boilerplate) para asegurar que puedan
  completar las tareas principales dentro del tiempo asignado.

## 3. Plan Detallado Clase por Clase

### Clase 1: El "Por qué" y el Entorno de Trabajo (Teoría y Configuración)

- **Duración:** 1 hora
- **Objetivo:** Entender el problema central que resuelve Databricks y lograr que todos los
  estudiantes configuren su entorno práctico.
- **Recursos de la Clase:**
  - [Data Warehouses vs Data Lakes](https://www.databricks.com/glossary/data-warehouse)
  - [Lakehouse Architecture](https://www.databricks.com/product/data-lakehouse)
  - [Apache Spark Overview](https://docs.databricks.com/getting-started/spark/index.html)
- **Agenda:**
  - **[00:00 - 00:20] El Problema Central (Teoría):**
    - El viejo mundo: Data Warehouses (estructurados, rápidos, rígidos) vs. Data Lakes (no
      estructurados, baratos, lentos/desordenados).
    - El problema de los "dos silos": ¿Por qué los equipos de BI (Business Intelligence) y de IA
      (Inteligencia Artificial) no pueden trabajar juntos?
    - **💡 Mejora:** Incluir diagrama visual comparando las tres arquitecturas.
    - **💡 Mejora:** Caso de uso real argentino (ej: "¿Cómo analiza Mercado Libre sus datos de
      compras Y entrena modelos de recomendación?")
    - **💡 Mejora:** Mencionar el costo de mantener dos plataformas separadas.
  - **[00:20 - 00:30] La Solución (Teoría):**
    - El **Databricks Lakehouse**: Lo mejor de ambos mundos.
    - La tecnología central: Apache Spark (el motor) y Delta Lake (el formato de almacenamiento).
  - **[00:30 - 00:50] Laboratorio 0: Configuración de Cuenta (Práctica Guiada):**
    - Instructor comparte pantalla en vivo.
    - Los estudiantes siguen los pasos para crear sus cuentas en **Databricks Free Edition**.
    - **Recursos:**
      - [Free Edition Signup](https://www.databricks.com/learn/free-edition)
      - [Cluster Configuration Guide](https://docs.databricks.com/clusters/configure.html)
      - [Workspace Guide](https://docs.databricks.com/workspace/index.html)
    - **💡 Mejora:** Proveer notebook "template" con instrucciones paso a paso.
    - **💡 Mejora:** Incluir troubleshooting común (verificación de email, problemas de región).
    - **Identificación de Talento:** Notar qué estudiantes resuelven esto rápido y ayudan a otros en
      el chat.
  - **[00:50 - 01:00] Laboratorio 0: Tour del Workspace (Práctica Guiada):**
    - Creación del primer clúster (explicar brevemente qué es un clúster).
    - Creación y ejecución del primer notebook (%sql SELECT "Hola Mundo").
    - **Recurso:** [Notebooks Tutorial](https://docs.databricks.com/notebooks/index.html)
- **Entregable:** Todos los estudiantes tienen una cuenta Free Edition funcional, un clúster
  corriendo y han ejecutado su primer notebook.
- **💡 Checklist de verificación:**
  - ✓ Cuenta creada
  - ✓ Cluster corriendo
  - ✓ Notebook ejecutado
  - ✓ Acceso al canal de soporte (Slack/Discord)

---

### Clase 2: La "Ingesta" - Construyendo la Capa Bronce (Práctica)

- **Duración:** 1 hora
- **Objetivo:** Ingestar datos crudos y desordenados en una tabla Delta confiable y versionada.
- **Recursos de la Clase:**
  - [Medallion Architecture Pattern](https://www.databricks.com/glossary/medallion-architecture)
  - [Delta Lake Introduction](https://docs.databricks.com/delta/index.html)
  - [ACID Transactions](https://docs.databricks.com/delta/concurrency-control.html)
  - [Time Travel](https://docs.databricks.com/delta/history.html)
- **Agenda:**

  - **[00:00 - 00:10] Repaso y Teoría:**
    - La **Arquitectura Medallion**: El concepto más importante (Bronce, Plata, Oro).
    - Objetivo de hoy: Construir la **Capa Bronce** (una copia cruda y versionada de la fuente).
    - **💡 Mejora:** Mostrar diagrama de la Medallion Architecture con ejemplos de cada capa.
    - **💡 Mejora:** Explicar por qué se llama "Bronce" (datos crudos, sin procesar, como el metal
      sin refinar).
  - **[00:10 - 00:55] Laboratorio 1: De CSV a Delta (Manos a la obra):**

    - **Recursos:**
      - [Upload Data to DBFS](https://docs.databricks.com/dbfs/upload-download.html)
      - [Read CSV Files](https://docs.databricks.com/external-data/csv.html)
      - [Delta Lake Quickstart](https://docs.databricks.com/delta/quick-start.html)
    - **Paso 1:** Subir el dataset público de Argentina (CSV) al Sistema de Archivos de Databricks
      (DBFS).
      - **💡 Mejora:** Proveer el CSV ya pre-cargado en DBFS para ahorrar tiempo.
    - **Paso 2:** Usar un notebook de PySpark para leer el CSV en un DataFrame, infiriendo el
      esquema.
    - **Paso 3:** Usar display(df) para mostrar los datos. Señalar el "desorden": valores nulos,
      tipos de datos incorrectos, strings sucios.
      - **💡 Mejora:** Ejercicio guiado: "Identifica 3 problemas de calidad en estos datos"
    - **Paso 4:** Escribir el DataFrame crudo en una tabla **Delta Lake** llamada bronze_raw_data.
    - **Paso 5:** Discutir _por qué_ esto es mejor que un CSV (Transacciones ACID, Time Travel).
      Mostrar el DESCRIBE HISTORY de la tabla.
      - **💡 Mejora:** Agregar comando de verificación:

    ```python
    # Verificar la escritura exitosa
    display(spark.sql("SELECT COUNT(*) as total_registros FROM bronze_raw_data"))

    # Explorar el historial de la tabla
    display(spark.sql("DESCRIBE HISTORY bronze_raw_data"))

    # Time Travel - ver la tabla en una versión anterior
    display(spark.sql("SELECT * FROM bronze_raw_data VERSION AS OF 0 LIMIT 10"))

    # Ver metadata de la tabla
    display(spark.sql("DESCRIBE DETAIL bronze_raw_data"))
    ```

  - **[00:55 - 01:00] Q&A y Avance:**
    - "Nuestros datos están en el Lakehouse, pero siguen sucios. Lo siguiente es limpiarlos."

- **Entregable:** Una tabla Delta bronze_raw_data en el workspace de cada estudiante.
- **Identificación de Talento (Data Engineer):** ¿Quién entendió el "por qué" de Delta Lake? ¿Quién
  terminó el notebook rápido y empezó a explorar los datos por su cuenta?

---

### Clase 3: La "Transformación" - Capas Plata y Oro (Práctica)

- **Duración:** 1 hora
- **Objetivo:** Transformar datos crudos en tablas limpias y agregadas, listas para BI e IA.
- **Recursos de la Clase:**
  - [Data Transformation Best Practices](https://docs.databricks.com/optimizations/index.html)
  - [SQL Reference](https://docs.databricks.com/sql/language-manual/index.html)
  - [Data Quality Checks](https://docs.databricks.com/delta/delta-constraints.html)
  - [Spark SQL Functions](https://docs.databricks.com/sql/language-manual/sql-ref-functions.html)
  - [Visualizations](https://docs.databricks.com/visualizations/index.html)
- **Agenda:**

  - **[00:00 - 00:05] Repaso y Teoría:**
    - **Capa Plata (Silver):** Datos limpios, validados y enriquecidos.
    - **Capa Oro (Gold):** Datos agregados a nivel de negocio para reportes.
    - **💡 Mejora:** Quick quiz de 2 preguntas para reactivar conocimientos.
    - **💡 Mejora:** Mostrar el flujo completo: Bronze → Silver → Gold con flechas y
      transformaciones.
  - **[00:05 - 00:55] Laboratorio 2: Construyendo Tablas Silver y Gold (Manos a la obra):**

    - **Paso 1 (Silver):** Leer la tabla bronze_raw_data usando Spark SQL.
    - **Paso 2 (Silver):** Aplicar transformaciones: CAST para corregir tipos, manejar valores NULL,
      y filtrar registros erróneos.
    - **Paso 3 (Silver):** Escribir los datos limpios en una nueva tabla Delta llamada
      silver_clean_data.
      - **💡 Mejora:** Agregar métricas de calidad:

    ```sql
    -- Silver: Agregar métricas de calidad
    CREATE OR REPLACE TABLE silver_clean_data AS
    SELECT
        *,
        CURRENT_TIMESTAMP() as processed_at,
        'v1.0' as pipeline_version
    FROM bronze_raw_data
    WHERE campo_importante IS NOT NULL
      AND fecha >= '2020-01-01';

    -- Verificar mejora de calidad
    SELECT
        'Bronze' as capa,
        COUNT(*) as registros,
        COUNT(DISTINCT campo_clave) as unicos
    FROM bronze_raw_data
    UNION ALL
    SELECT
        'Silver' as capa,
        COUNT(*) as registros,
        COUNT(DISTINCT campo_clave) as unicos
    FROM silver_clean_data;
    ```

    - **Paso 4 (Gold):** Leer la tabla silver_clean_data.
    - **Paso 5 (Gold):** Aplicar una agregación de negocio (ej. GROUP BY provincia, anio y
      COUNT(eventos)).
    - **Paso 6 (Gold):** Escribir los datos agregados en una tabla gold_summary_report.
      - **💡 Mejora:** Agregar constraints para asegurar calidad:

    ```sql
    -- Gold: Agregar constraints
    CREATE OR REPLACE TABLE gold_summary_report (
        provincia STRING NOT NULL,
        anio INT NOT NULL,
        total_eventos LONG NOT NULL,
        CONSTRAINT valid_year CHECK (anio >= 2000 AND anio <= 2030)
    );
    ```

    - **Paso 7 (Serving):** Correr un SELECT \* sobre la tabla gold_summary_report y usar el botón
      nativo de Visualize para crear un gráfico de barras o un mapa simple.
      - **💡 Mejora:** Incluir instrucciones específicas para cada tipo de gráfico.

  - **[00:55 - 01:00] Q&A:**
    - "Acabamos de construir un pipeline de datos completo, de punta a punta, manualmente."

- **Entregable:** Tablas silver limpias y gold agregadas, con una visualización simple.
- **Identificación de Talento (Analista/Científico):** ¿Quién fue rápido con las queries SQL? ¿Quién
  experimentó con diferentes visualizaciones? ¿Quién hizo preguntas perspicaces sobre los datos en
  sí?

---

### Clase 4: Producción, Costos y el "Takehome Challenge"

- **Duración**: 1 hora
- **Objetivo:** Entender cómo llevar un proyecto a la realidad (costos/arquitectura) y lanzar el
  desafío final de evaluación.
- **Recursos de la Clase:**
  - [Delta Live Tables](https://docs.databricks.com/delta-live-tables/index.html)
  - [Workflows & Jobs](https://docs.databricks.com/workflows/index.html)
  - [Cost Management](https://docs.databricks.com/administration-guide/account-settings/usage.html)
  - [Pricing Calculator](https://databricks.com/product/pricing)
- **Agenda:**

  - **[00:00 - 00:20] Recap & Demo del Pipeline (El "Gold Standard")**
    - **Actividad:** Repaso rápido del pipeline construido en la Clase 3 (Bronce → Plata → Oro).
    - **Enfoque:** Usar este pipeline manual como la "Demo" de lo que se espera que logren los
      alumnos. Resaltar las mejores prácticas aplicadas (limpieza, esquema, agregación).
    - **💡 Mejora:** Mostrar métricas del pipeline (tiempo de ejecución, datos procesados, calidad).
    - **💡 Mejora:** Mostrar cómo se vería este mismo pipeline en un DAG (Directed Acyclic Graph).
    - **Mensaje clave:** "Esto funciona manualmente, pero ¿cómo escala en una empresa real?"
  - **[00:20 - 00:40] Teoría: Arquitectura de Producción y Presupuestos**

    - **El Salto a Premium (Teórico):** Explicar conceptualmente herramientas como _Delta Live
      Tables_ y _Jobs_ sin depender de una demo en vivo (dadas las limitaciones de Free Edition).
      Usar slides para mostrar la diferencia visual y operativa entre correr un notebook manual vs.
      orquestado.
    - **💡 Mejora:** Incluir tabla comparativa de costos aproximados.
    - **💡 Mejora:** Ejemplo de cálculo de costos paso a paso:

    ```
    📊 Estimación de Costos Mensuales (Ejemplo)

    Supuestos:
    - Pipeline corre 1x por día (30 veces/mes)
    - Duración promedio: 30 minutos
    - Cluster: Standard_DS3_v2 (1 driver + 2 workers)
    - Precio DBU: ~$0.20/DBU
    - DBUs por hora: 3

    Cálculo:
    - Horas mensuales: 30 días × 0.5 horas = 15 horas
    - DBUs consumidos: 15 horas × 3 DBUs/hora = 45 DBUs
    - Costo estimado: 45 DBUs × $0.20 = $9/mes

    💡 Factores que afectan el costo:
    - Tamaño del cluster
    - Frecuencia de ejecución
    - Tiempo de procesamiento
    - Tipo de instancia (spot vs on-demand)
    ```

    - **💡 Mejora:** Mostrar screenshots de Delta Live Tables y Jobs.
    - **Takeaway:** En el mundo real, la ingeniería de datos no es solo código, es costo-eficiencia.

  - **[00:40 - 00:55] Lanzamiento del "Takehome Challenge"**
    - **Concepto:** "Ahora es su turno. Mismo problema, distintos datos."
    - **El Desafío:** Proveer un dataset diferente y pedirles que repliquen la arquitectura
      Medallion.
    - **Recursos:**
      - [Sample Datasets](https://docs.databricks.com/discover/databricks-datasets.html)
      - [Export Notebooks](https://docs.databricks.com/notebooks/notebook-export-import.html)
    - **Reglas:**
      - Debe correr en Databricks Free Edition.
      - Debe tener las 3 capas claras (Bronze, Silver, Gold).
      - **Bonus:** Incluir una estimación teórica de cuánto costaría correrlo diariamente (usando lo
        aprendido en el bloque anterior).
    - **💡 Rúbrica de Evaluación (100 puntos):**
      - **Funcionalidad Técnica (60 pts):**
        - Bronze Layer funcional (20 pts)
        - Silver Layer con limpieza (20 pts)
        - Gold Layer con agregaciones (20 pts)
      - **Calidad de Código (20 pts):**
        - Código limpio y comentado (10 pts)
        - Nomenclatura consistente (5 pts)
        - Buenas prácticas SQL/PySpark (5 pts)
      - **Análisis de Negocio (20 pts):**
        - Estimación de costos realista (10 pts)
        - Insights relevantes (5 pts)
        - Documentación clara (5 pts)
      - **Bonus (hasta 20 pts extra):**
        - Tests de calidad de datos (+5 pts)
        - Manejo de errores robusto (+5 pts)
        - Optimizaciones de performance (+5 pts)
        - Documentación excepcional (+5 pts)
  - **[00:55 - 01:00] Cierre y Próximos Pasos**
    - Instrucciones de entrega (ej. exportar notebooks como .dbc o HTML).
    - Definición del _deadline_ para el challenge.
    - **💡 Mejora:** Mencionar recursos para continuar aprendiendo:
      - [Databricks Academy](https://www.databricks.com/learn/training/home)
      - [Community Forums](https://community.databricks.com/)

- **Entregable:** Ninguno en clase.
- **Identificación de Talento:**
  - "Takehome Challenge" lanzado oficialmente a los estudiantes.
  - Instrucciones claras sobre la metodología de evaluación y el _deadline_.

---

## 4. Detalle del Challenge (Takehome) Propuesto

- Para evaluar a los candidatos, el ejercicio debe ser equivalente en dificultad al visto en clase,
  pero requerir análisis propio.
- **Dataset del Challenge (Opciones):**

  - **Opción A (Nativo - Recomendada):** Usar /databricks-datasets/nyctaxi (Taxis de Nueva York) o
    /databricks-datasets/learning-spark-v2/flights (Vuelos).
  - _Ventaja:_ Ya está montado en el entorno, los alumnos no necesitan subir archivos y elimina
    problemas de carga/internet.
  - **Opción B (Local):** Otro CSV de datos.gob.ar (ej. Precios cuidados o Vacunación).
  - _Ventaja:_ Mantiene la temática local, pero requiere carga manual.
  - **Datasets Sugeridos:**
    - [Vacunación COVID-19](https://datos.gob.ar/dataset/salud-covid-19-casos-registrados-republica-argentina)
    - [Precios Cuidados](https://datos.gob.ar/dataset/produccion-precios-cuidados)
    - [Compras Públicas](https://datos.gob.ar/dataset/hacienda-compras-publicas)

### Consigna para el candidato

"Como Ingeniero de Datos Junior, se te ha asignado el dataset de **[Vuelos/Taxis]**. Tu tarea es:

- **Ingestar** los datos crudos (Capa Bronze).
- **Limpiarlos** eliminando registros cancelados o nulos (Capa Silver).
- **Generar una tabla agregada** (Capa Gold) que muestre el top 10 de aerolíneas/zonas con mayor
  tráfico mensual.
- **Visualización:** Crear al menos un gráfico que muestre insights relevantes del negocio.
- **Estimación:** Calcula el costo mensual teórico de este proceso asumiendo que tarda 30 minutos en
  ejecutarse diariamente en un Job Cluster estándar.
- **Documentación:** Incluir un breve informe (1-2 páginas) explicando:
  - Decisiones técnicas tomadas
  - Problemas de calidad encontrados y cómo se resolvieron
  - Insights descubiertos en los datos
  - Cálculo detallado de costos

**Formato de Entrega:**

- Notebooks exportados (.dbc o .html)
- Documento de análisis (PDF o Markdown)
- Plazo: [Especificar fecha límite]"

---

## 5. Recursos Adicionales

### Para Instructores

- [Databricks Educator Resources](https://www.databricks.com/learn/training/educator-resources)
- [Community Forums](https://community.databricks.com/)

### Para Estudiantes

- [Interactive SQL Tutorial](https://docs.databricks.com/sql/language-manual/index.html)
- [PySpark Cheat Sheet](https://spark.apache.org/docs/latest/api/python/getting_started/quickstart.html)
- [Delta Lake Tutorial](https://delta.io/learn/tutorials/)

### Datasets Argentinos Adicionales

- [Transporte Público Buenos Aires](https://data.buenosaires.gob.ar/)
- [Portal de Datos Abiertos](https://datos.gob.ar/)

---

## 6. Checklist de Implementación

### Antes del Bootcamp

- [ ] Crear estructura de carpetas del repositorio
- [ ] Subir datasets a DBFS o preparar enlaces
- [ ] Preparar notebooks starter y solution
- [ ] Crear slides para Clase 1 y 4
- [ ] Preparar video de backup del setup
- [ ] Configurar canal de comunicación (Slack/Discord)
- [ ] Enviar email de bienvenida con checklist

### Durante Cada Clase

- [ ] Compartir enlaces relevantes en el chat
- [ ] Monitorear progreso de estudiantes
- [ ] Tomar notas sobre quién destaca
- [ ] Documentar preguntas frecuentes
- [ ] Recopilar feedback rápido

### Después del Bootcamp

- [ ] Enviar encuesta de feedback
- [ ] Evaluar challenges con la rúbrica
- [ ] Enviar certificados de participación
- [ ] Identificar top performers para seguimiento
- [ ] Actualizar material basado en feedback
- [ ] Programar Office Hours si es necesario

---

## 7. Mejoras Post-Bootcamp

### Seguimiento

- Encuesta de feedback detallada
- Certificado de participación personalizado
- Sesión de Office Hours opcional para preguntas del challenge
- Lista de recursos para continuar aprendiendo
- Invitación a comunidad de alumni

### Material de Apoyo Extra

- Cheat sheet de comandos Spark SQL y PySpark
- Videos cortos (2-3 min) explicando conceptos clave
- FAQ actualizado basado en preguntas recurrentes
- Casos de uso reales de empresas usando Databricks

---

**Versión:** 2.0 (Actualizada con Free Edition y mejoras sugeridas) **Última actualización:**
Noviembre 2025
