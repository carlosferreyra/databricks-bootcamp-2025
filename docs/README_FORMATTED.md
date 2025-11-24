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
- **Herramientas:** Databricks Community Edition (DCE).

## 2. Prerrequisitos y Logística

- **Prerrequisitos del Estudiante:** Entendimiento básico de SQL (SELECT, WHERE, GROUP BY) y Python
  (variables, funciones, estructuras de datos).
- **Prerrequisitos del Instructor:**
  1. Un dataset público de Argentina previamente validado (ej. de datos.gob.ar), guardado como un
     archivo CSV "sucio" (con datos desordenados).
  2. Una versión completa de los notebooks del laboratorio para usar como referencia ("Answer key").
  3. Presentaciones (slides) para la Clase 1 y la Clase 4.
- **Nota Importante:** Las sesiones prácticas de 1 hora son _sprints_. Se proveerá a los estudiantes
  notebooks "iniciales" con instrucciones y código base (boilerplate) para asegurar que puedan
  completar las tareas principales dentro del tiempo asignado.

## 3. Plan Detallado Clase por Clase

### Clase 1: El "Por qué" y el Entorno de Trabajo (Teoría y Configuración)

- **Duración:** 1 hora
- **Objetivo:** Entender el problema central que resuelve Databricks y lograr que todos los
  estudiantes configuren su entorno práctico.
- **Agenda:**
  - **[00:00 - 00:20] El Problema Central (Teoría):**
    - El viejo mundo: Data Warehouses (estructurados, rápidos, rígidos) vs. Data Lakes (no
      estructurados, baratos, lentos/desordenados).
    - El problema de los "dos silos": ¿Por qué los equipos de BI (Business Intelligence) y de IA
      (Inteligencia Artificial) no pueden trabajar juntos?
  - **[00:20 - 00:30] La Solución (Teoría):**
    - El **Databricks Lakehouse**: Lo mejor de ambos mundos.
    - La tecnología central: Apache Spark (el motor) y Delta Lake (el formato de almacenamiento).
  - **[00:30 - 00:50] Laboratorio 0: Configuración de Cuenta (Práctica Guiada):**
    - Instructor comparte pantalla en vivo.
    - Los estudiantes siguen los pasos para crear sus cuentas en **Databricks Community Edition
      (DCE)**.
    - **Identificación de Talento:** Notar qué estudiantes resuelven esto rápido y ayudan a otros en
      el chat.
  - **[00:50 - 01:00] Laboratorio 0: Tour del Workspace (Práctica Guiada):**
    - Creación del primer clúster (explicar brevemente qué es un clúster).
    - Creación y ejecución del primer notebook (%sql SELECT "Hola Mundo").
- **Entregable:** Todos los estudiantes tienen una cuenta DCE funcional, un clúster corriendo y han
  ejecutado su primer notebook.

---

### Clase 2: La "Ingesta" - Construyendo la Capa Bronce (Práctica)

- **Duración:** 1 hora
- **Objetivo:** Ingestar datos crudos y desordenados en una tabla Delta confiable y versionada.
- **Agenda:**

  - **[00:00 - 00:10] Repaso y Teoría:**
    - La **Arquitectura Medallion**: El concepto más importante (Bronce, Plata, Oro).
    - Objetivo de hoy: Construir la **Capa Bronce** (una copia cruda y versionada de la fuente).
  - **[00:10 - 00:55] Laboratorio 1: De CSV a Delta (Manos a la obra):**
    - **Paso 1:** Subir el dataset público de Argentina (CSV) al Sistema de Archivos de Databricks
      (DBFS).
    - **Paso 2:** Usar un notebook de PySpark para leer el CSV en un DataFrame, infiriendo el
      esquema.
    - **Paso 3:** Usar display(df) para mostrar los datos. Señalar el "desorden": valores nulos,
      tipos de datos incorrectos, strings sucios.
    - **Paso 4:** Escribir el DataFrame crudo en una tabla **Delta Lake** llamada bronze_raw_data.
    - **Paso 5:** Discutir _por qué_ esto es mejor que un CSV (Transacciones ACID, Time Travel).
      Mostrar el DESCRIBE HISTORY de la tabla.
  - **[00:55 - 01:00] Q&A y Avance:**
    - "Nuestros datos están en el Lakehouse, pero siguen sucios. Lo siguiente es limpiarlos."

- **Entregable:** Una tabla Delta bronze_raw_data en el workspace de cada estudiante.
- **Identificación de Talento (Data Engineer):** ¿Quién entendió el "por qué" de Delta Lake? ¿Quién
  terminó el notebook rápido y empezó a explorar los datos por su cuenta?

---

### Clase 3: La "Transformación" - Capas Plata y Oro (Práctica)

- **Duración:** 1 hora
- **Objetivo:** Transformar datos crudos en tablas limpias y agregadas, listas para BI e IA.
- **Agenda:**
  - **[00:00 - 00:05] Repaso y Teoría:**
    - **Capa Plata (Silver):** Datos limpios, validados y enriquecidos.
    - **Capa Oro (Gold):** Datos agregados a nivel de negocio para reportes.
  - **[00:05 - 00:55] Laboratorio 2: Construyendo Tablas Silver y Gold (Manos a la obra):**
    - **Paso 1 (Silver):** Leer la tabla bronze_raw_data usando Spark SQL.
    - **Paso 2 (Silver):** Aplicar transformaciones: CAST para corregir tipos, manejar valores NULL,
      y filtrar registros erróneos.
    - **Paso 3 (Silver):** Escribir los datos limpios en una nueva tabla Delta llamada
      silver_clean_data.
    - **Paso 4 (Gold):** Leer la tabla silver_clean_data.
    - **Paso 5 (Gold):** Aplicar una agregación de negocio (ej. GROUP BY provincia, anio y
      COUNT(eventos)).
    - **Paso 6 (Gold):** Escribir los datos agregados en una tabla gold_summary_report.
    - **Paso 7 (Serving):** Correr un SELECT \* sobre la tabla gold_summary_report y usar el botón
      nativo de Visualize para crear un gráfico de barras o un mapa simple.
  - **[00:55 - 01:00] Q&A:**
    - "Acabamos de construir un pipeline de datos completo, de punta a punta, manualmente."
- **Entregable:** Tablas silver limpias y gold agregadas, con una visualización simple.
- **Identificación de Talento (Analista/Científico):** ¿Quién fue rápido con las queries SQL? ¿Quién
  experimentó con diferentes visualizaciones? ¿Quién hizo preguntas perspicaces sobre los datos en
  sí?

### **Clase 4: Producción, Costos y el “Takehome Challenge”**

- **Duración**: 1 hora
- **Objetivo:** Entender cómo llevar un proyecto a la realidad (costos/arquitectura) y lanzar el
  desafío final de evaluación.
- **Agenda:**
  - **[00:00 - 00:20] Recap & Demo del Pipeline (El "Gold Standard")**
    - **Actividad:** Repaso rápido del pipeline construido en la Clase 3 (Bronce → Plata → Oro).
    - **Enfoque:** Usar este pipeline manual como la "Demo" de lo que se espera que logren los
      alumnos. Resaltar las mejores prácticas aplicadas (limpieza, esquema, agregación).
    - **Mensaje clave:** "Esto funciona manualmente, pero ¿cómo escala en una empresa real?"
  - **[00:20 - 00:40] Teoría: Arquitectura de Producción y Presupuestos**
    - **El Salto a Premium (Teórico):** Explicar conceptualmente herramientas como _Delta Live
      Tables_ y _Jobs_ sin depender de una demo en vivo (dadas las limitaciones de Community
      Edition). Usar slides para mostrar la diferencia visual y operativa entre correr un notebook
      manual vs. orquestado.
    - **Takeaway:** En el mundo real, la ingeniería de datos no es solo código, es costo-eficiencia.
  - **[00:40 - 00:55] Lanzamiento del "Takehome Challenge"**
    - **Concepto:** "Ahora es su turno. Mismo problema, distintos datos."
    - **El Desafío:** Proveer un dataset diferente y pedirles que repliquen la arquitectura
      Medallion.
    - **Reglas:**
      - Debe correr en Databricks Community Edition.
      - Debe tener las 3 capas claras (Bronze, Silver, Gold).
      - **Bonus:** Incluir una estimación teórica de cuánto costaría correrlo diariamente (usando lo
        aprendido en el bloque anterior).
  - **[00:55 - 01:00] Cierre y Próximos Pasos**
    - Instrucciones de entrega (ej. exportar notebooks como .dbc o HTML).
    - Definición del _deadline_ para el challenge.
- **Entregable:** Ninguno.
- **Identificación de Talento:**
  - "Takehome Challenge" lanzado oficialmente a los estudiantes.
  - Instrucciones claras sobre la metodología de evaluación y el _deadline_.

---

## 4. Detalle del Challenge (Takehome) Propuesto

- Para evaluar a los candidatos, el ejercicio debe ser equivalente en dificultad al visto en clase,
  pero requerir análisis propio.
- **Dataset del Challenge (Opciones):**

  - **Opción A (Nativo - Recomendada):** Usar /databricks-datasets/nyctaxi (Taxis de Nueva York) o
    /databricks-datasets/learning/flights (Vuelos).
  - _Ventaja:_ Ya está montado en el entorno, los alumnos no necesitan subir archivos y elimina
    problemas de carga/internet.
  - **Opción B (Local):** Otro CSV de datos.gob.ar (ej. Precios cuidados o Vacunación).
  - _Ventaja:_ Mantiene la temática local, pero requiere carga manual.

### Consigna para el candidato

"Como Ingeniero de Datos Junior, se te ha asignado el dataset de **[Vuelos/Taxis]**. Tu tarea es:

- **Ingestar** los datos crudos.
- **Limpiarlos** eliminando registros cancelados o nulos (Capa Silver).
- **Generar una tabla agregada** (Capa Gold) que muestre el top 10 de aerolíneas/zonas con mayor
  tráfico mensual.
- **Estimación:** Calcula el costo mensual teórico de este proceso asumiendo que tarda 30 minutos en
  ejecutarse diariamente en un Job Cluster estándar."
