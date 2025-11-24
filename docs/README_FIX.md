# Sugerencias de Mejora para el Bootcamp de Databricks

## ⚠️ Actualización Importante

**Databricks Community Edition está siendo reemplazado por Databricks Free Edition.**

- **Nuevo enlace**: <https://www.databricks.com/learn/free-edition>
- **Migración**: Community Edition sigue funcionando pero es legacy. Se recomienda migrar a Free
  Edition.
- **Cambios en el README.md original**: Reemplazar todas las referencias de "Community Edition
  (DCE)" por "Free Edition" en:
  - Línea 14: Herramientas
  - Línea 47-48: Lab 0 setup
  - Línea 54: Entregables
  - Línea 136: Requisitos del challenge

## 📋 Resumen de Mejoras Propuestas

Este documento contiene sugerencias para mejorar el plan del bootcamp, incluyendo:

1. **Enlaces directos** a recursos y secciones de la plataforma Databricks
2. **Mejoras de contenido** para cada clase
3. **Estructura de directorios** sugerida para el repositorio

---

## 🔗 Enlaces y Recursos de Databricks a Incluir

### Enlaces Principales del Bootcamp

#### Para el Instructor

- **Databricks Free Edition**: <https://www.databricks.com/learn/free-edition>
- **Documentación Oficial**: <https://docs.databricks.com/>
- **Delta Lake Docs**: <https://docs.delta.io/latest/index.html>
- **Apache Spark Guide**: <https://spark.apache.org/docs/latest/>

#### Recursos de Aprendizaje

- **Databricks Academy**: <https://www.databricks.com/learn/training/home>
- **Delta Lake Quickstart**: <https://docs.databricks.com/delta/quick-start.html>
- **Medallion Architecture**: <https://www.databricks.com/glossary/medallion-architecture>
- **DBFS (Databricks File System)**: <https://docs.databricks.com/dbfs/index.html>

#### Datasets Públicos Argentinos

- **Portal de Datos Abiertos**: <https://datos.gob.ar/>
- **Datasets recomendados**:
  - Vacunación COVID-19:
    <https://datos.gob.ar/dataset/salud-covid-19-casos-registrados-republica-argentina>
  - Precios Cuidados: <https://datos.gob.ar/dataset/produccion-precios-cuidados>
  - Compras Públicas: <https://datos.gob.ar/dataset/hacienda-compras-publicas>

### Enlaces para Incluir en Clase 1

**Teoría - El Problema Central:**

- Data Warehouses vs Data Lakes: <https://www.databricks.com/glossary/data-warehouse>
- Lakehouse Architecture: <https://www.databricks.com/product/data-lakehouse>
- Apache Spark Overview: <https://docs.databricks.com/getting-started/spark/index.html>

**Lab 0 - Setup:**

- Free Edition Signup: <https://www.databricks.com/learn/free-edition>
- Cluster Configuration Guide: <https://docs.databricks.com/clusters/configure.html>
- Workspace Guide: <https://docs.databricks.com/workspace/index.html>
- Notebooks Tutorial: <https://docs.databricks.com/notebooks/index.html>

### Enlaces para Incluir en Clase 2

**Teoría - Medallion Architecture:**

- Medallion Architecture Pattern: <https://www.databricks.com/glossary/medallion-architecture>
- Delta Lake Introduction: <https://docs.databricks.com/delta/index.html>
- ACID Transactions: <https://docs.databricks.com/delta/concurrency-control.html>

**Lab 1 - Bronze Layer:**

- Upload Data to DBFS: <https://docs.databricks.com/dbfs/upload-download.html>
- Read CSV Files: <https://docs.databricks.com/external-data/csv.html>
- Delta Lake Quickstart: <https://docs.databricks.com/delta/quick-start.html>
- Time Travel: <https://docs.databricks.com/delta/history.html>
- DESCRIBE HISTORY:
  <https://docs.databricks.com/sql/language-manual/sql-ref-syntax-aux-describe-history.html>

### Enlaces para Incluir en Clase 3

**Teoría - Silver & Gold Layers:**

- Data Transformation Best Practices: <https://docs.databricks.com/optimizations/index.html>
- SQL Reference: <https://docs.databricks.com/sql/language-manual/index.html>
- Data Quality Checks: <https://docs.databricks.com/delta/delta-constraints.html>

**Lab 2 - Transformations:**

- Spark SQL Functions: <https://docs.databricks.com/sql/language-manual/sql-ref-functions.html>
- Data Cleaning Patterns: <https://docs.databricks.com/optimizations/spark-ui-guide/index.html>
- Visualizations: <https://docs.databricks.com/visualizations/index.html>
- Built-in Visualizations: <https://docs.databricks.com/notebooks/visualizations/index.html>

### Enlaces para Incluir en Clase 4

**Teoría - Production:**

- Delta Live Tables: <https://docs.databricks.com/delta-live-tables/index.html>
- Workflows & Jobs: <https://docs.databricks.com/workflows/index.html>
- Cost Management: <https://docs.databricks.com/administration-guide/account-settings/usage.html>
- Pricing Calculator: <https://databricks.com/product/pricing>

**Challenge Resources:**

- Sample Datasets: <https://docs.databricks.com/discover/databricks-datasets.html>
- NYC Taxi Dataset: `/databricks-datasets/nyctaxi/`
- Flights Dataset: `/databricks-datasets/learning-spark-v2/flights/`
- Export Notebooks: <https://docs.databricks.com/notebooks/notebook-export-import.html>

---

## 💡 Sugerencias de Mejora por Clase

### Clase 1: Mejoras Sugeridas

**Teoría - El Problema Central [00:00 - 00:20]:**

- ✅ **Agregar**: Un diagrama visual comparando Data Warehouse vs Data Lake vs Lakehouse
- ✅ **Incluir**: Caso de uso real argentino (ej: "¿Cómo analiza Mercado Libre sus datos de compras
  Y entrena modelos de recomendación?")
- ✅ **Mencionar**: El costo de mantener dos plataformas separadas

**Lab 0 - Configuración [00:30 - 00:50]:**

- ✅ **Agregar**: Un notebook "template" pre-cargado con instrucciones paso a paso
- ✅ **Incluir**: Troubleshooting común (verificación de email, problemas de región)
- ✅ **Preparar**: Un video de backup de 5 minutos mostrando el setup completo

**Entregables adicionales sugeridos:**

- Checklist de verificación: "✓ Cuenta creada, ✓ Cluster corriendo, ✓ Notebook ejecutado"
- Link a canal de Slack/Discord para soporte peer-to-peer

### Clase 2: Mejoras Sugeridas

**Repaso y Teoría [00:00 - 00:10]:**

- ✅ **Agregar**: Diagrama de la Medallion Architecture con ejemplos de cada capa
- ✅ **Explicar**: Por qué se llama "Bronce" (datos crudos, sin procesar, como el metal sin refinar)
- ✅ **Mostrar**: Un ejemplo real de un pipeline en producción

**Lab 1 - Bronze Layer [00:10 - 00:55]:**

- ✅ **Mejorar Paso 1**: Proveer el CSV ya pre-cargado en DBFS para ahorrar tiempo (opcionalmente
  enseñar cómo subirlo)
- ✅ **Agregar en Paso 3**: Ejercicio guiado: "Identifica 3 problemas de calidad en estos datos"
- ✅ **Mejorar Paso 5**: Agregar comando de verificación: `SELECT COUNT(*) FROM bronze_raw_data`
- ✅ **Agregar Paso Extra**: Mostrar `DESCRIBE DETAIL bronze_raw_data` para ver metadata de la tabla

**Código de ejemplo a incluir en el notebook:**

```python
# Verificar la escritura exitosa
display(spark.sql("SELECT COUNT(*) as total_registros FROM bronze_raw_data"))

# Explorar el historial de la tabla
display(spark.sql("DESCRIBE HISTORY bronze_raw_data"))

# Time Travel - ver la tabla en una versión anterior
display(spark.sql("SELECT * FROM bronze_raw_data VERSION AS OF 0 LIMIT 10"))
```

### Clase 3: Mejoras Sugeridas

**Repaso [00:00 - 00:05]:**

- ✅ **Agregar**: Quick quiz de 2 preguntas para reactivar conocimientos
- ✅ **Mostrar**: El flujo completo: Bronze → Silver → Gold con flechas y transformaciones

**Lab 2 - Silver & Gold [00:05 - 00:55]:**

- ✅ **Mejorar**: Dividir en dos notebooks separados (uno para Silver, otro para Gold) para mejor
  organización
- ✅ **Agregar validaciones**: Usar constraints de Delta Lake para asegurar calidad
- ✅ **Incluir métricas**: COUNT antes y después de la limpieza para mostrar impacto
- ✅ **Bonus**: Agregar una tabla de auditoría que registre las transformaciones aplicadas

**Código sugerido para agregar:**

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

-- Gold: Agregar constraints
CREATE OR REPLACE TABLE gold_summary_report (
    provincia STRING NOT NULL,
    anio INT NOT NULL,
    total_eventos LONG NOT NULL,
    CONSTRAINT valid_year CHECK (anio >= 2000 AND anio <= 2030)
);
```

**Visualización:**

- ✅ **Agregar**: Instrucciones específicas para cada tipo de gráfico (barras, líneas, mapas)
- ✅ **Incluir**: Ejemplos de insights que se pueden obtener de los datos

### Clase 4: Mejoras Sugeridas

**Recap & Demo [00:00 - 00:20]:**

- ✅ **Agregar**: Métricas del pipeline (tiempo de ejecución, datos procesados, calidad)
- ✅ **Mostrar**: Cómo se vería este mismo pipeline en un DAG (Directed Acyclic Graph)
- ✅ **Incluir**: Checklist de "Production Readiness"

**Teoría de Producción [00:20 - 00:40]:**

- ✅ **Agregar**: Tabla comparativa de costos aproximados
- ✅ **Incluir**: Ejemplo de cálculo de costos paso a paso
- ✅ **Mostrar**: Screenshots de Delta Live Tables y Jobs (aunque no puedan usarlos en Free Edition)
- ✅ **Mencionar**: Alternativas para automatizar en Free Edition (ej: Airflow externo)

**Ejemplo de contenido a agregar:**

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

**Takehome Challenge [00:40 - 00:55]:**

- ✅ **Agregar**: Rúbrica de evaluación clara con puntos específicos
- ✅ **Incluir**: Criterios de bonus (ej: tests unitarios, documentación, optimizaciones)
- ✅ **Proveer**: Template de entrega con secciones predefinidas

### Rúbrica de Evaluación Sugerida

```markdown
## Criterios de Evaluación del Challenge (100 puntos)

### Funcionalidad Técnica (60 puntos)

- [ ] Bronze Layer funcional (20 pts)
  - Datos cargados correctamente
  - Tabla Delta creada
  - Time Travel habilitado
- [ ] Silver Layer con limpieza (20 pts)
  - Tipos de datos corregidos
  - Manejo de nulos
  - Filtrado de datos inválidos
- [ ] Gold Layer con agregaciones (20 pts)
  - Agregación correcta
  - Visualización incluida
  - Insights documentados

### Calidad de Código (20 puntos)

- [ ] Código limpio y comentado (10 pts)
- [ ] Nomenclatura consistente (5 pts)
- [ ] Uso de buenas prácticas SQL/PySpark (5 pts)

### Análisis de Negocio (20 puntos)

- [ ] Estimación de costos realista (10 pts)
- [ ] Insights relevantes sobre los datos (5 pts)
- [ ] Documentación clara (5 pts)

### Bonus (hasta 20 puntos extra)

- [ ] Tests de calidad de datos (+5 pts)
- [ ] Manejo de errores robusto (+5 pts)
- [ ] Optimizaciones de performance (+5 pts)
- [ ] Documentación excepcional (+5 pts)
```

---

## 📁 Estructura de Directorios Sugerida

### Propuesta de Organización del Repositorio

```
databricks-bootcamp-2025/
│
├── README.md                           # Descripción principal del bootcamp
├── LICENSE                             # Licencia del proyecto
├── .gitignore                          # Archivos a ignorar en git
│
├── docs/                               # Documentación completa
│   ├── README.md                       # Plan completo del bootcamp (actual)
│   ├── README_BACKUP.md                # Backup del readme original
│   ├── setup-guide.md                  # Guía detallada de setup
│   ├── troubleshooting.md              # Soluciones a problemas comunes
│   ├── resources.md                    # Lista completa de recursos y enlaces
│   ├── glossary.md                     # Glosario de términos técnicos
│   └── assets/                         # Recursos visuales
│       ├── diagrams/
│       │   ├── medallion-architecture.png
│       │   ├── lakehouse-vs-warehouse.png
│       │   └── pipeline-flow.png
│       └── screenshots/
│           ├── cluster-creation.png
│           ├── notebook-interface.png
│           └── visualization-example.png
│
├── slides/                             # Presentaciones para las clases
│   ├── clase-1-introduccion.pdf
│   ├── clase-1-introduccion.pptx
│   ├── clase-4-produccion.pdf
│   └── clase-4-produccion.pptx
│
├── notebooks/                          # Notebooks organizados por clase
│   │
│   ├── clase-1-setup/
│   │   ├── 00-lab-checklist.md
│   │   ├── 01-hello-world.py
│   │   └── 01-hello-world.sql
│   │
│   ├── clase-2-bronze/
│   │   ├── 01-lab-bronze-starter.py        # Notebook inicial para estudiantes
│   │   ├── 01-lab-bronze-solution.py       # Solución completa (answer key)
│   │   ├── 02-bronze-exploration.sql       # Queries SQL de exploración
│   │   └── README.md                       # Instrucciones del lab
│   │
│   ├── clase-3-silver-gold/
│   │   ├── 01-lab-silver-starter.py
│   │   ├── 01-lab-silver-solution.py
│   │   ├── 02-lab-gold-starter.py
│   │   ├── 02-lab-gold-solution.py
│   │   ├── 03-visualizations.sql
│   │   └── README.md
│   │
│   ├── clase-4-challenge/
│   │   ├── challenge-instructions.md       # Instrucciones detalladas del challenge
│   │   ├── challenge-template.py           # Template para empezar
│   │   ├── evaluation-rubric.md            # Rúbrica de evaluación
│   │   └── example-submission/             # Ejemplo de entrega esperada
│   │       ├── bronze-layer.py
│   │       ├── silver-layer.py
│   │       ├── gold-layer.py
│   │       ├── cost-estimation.md
│   │       └── insights.md
│   │
│   └── extras/                         # Material adicional opcional
│       ├── advanced-optimizations.py
│       ├── delta-live-tables-demo.sql
│       └── testing-patterns.py
│
├── data/                               # Datasets para el bootcamp
│   ├── sample-data/
│   │   ├── argentina-dataset-v1.csv    # Dataset principal (sucio)
│   │   ├── argentina-dataset-clean.csv # Versión limpia (para referencia)
│   │   └── README.md                   # Descripción de los datasets
│   │
│   ├── challenge-data/
│   │   ├── challenge-dataset-option-a.csv
│   │   ├── challenge-dataset-option-b.csv
│   │   └── README.md                   # Instrucciones y descripción
│   │
│   └── dbfs-upload-scripts/            # Scripts para subir datos a DBFS
│       ├── upload-to-dbfs.py
│       └── verify-upload.py
│
├── solutions/                          # Soluciones completas (privado/instructor)
│   ├── clase-2-complete-pipeline.py
│   ├── clase-3-complete-pipeline.py
│   └── challenge-reference-solution/
│       ├── bronze-layer-solution.py
│       ├── silver-layer-solution.py
│       ├── gold-layer-solution.py
│       └── analysis-report.md
│
├── scripts/                            # Scripts de utilidad
│   ├── setup/
│   │   ├── verify-environment.py       # Verifica que todo esté configurado
│   │   ├── create-dbfs-folders.py      # Crea estructura de carpetas en DBFS
│   │   └── test-connection.py          # Test de conexión a Databricks
│   │
│   ├── validation/
│   │   ├── validate-bronze.py          # Valida la capa bronze
│   │   ├── validate-silver.py          # Valida la capa silver
│   │   ├── validate-gold.py            # Valida la capa gold
│   │   └── check-challenge-submission.py
│   │
│   └── utilities/
│       ├── data-quality-checks.py
│       ├── cost-calculator.py          # Calculadora de costos
│       └── export-notebooks.sh         # Script para exportar notebooks
│
├── config/                             # Configuraciones
│   ├── cluster-config.json             # Configuración recomendada de cluster
│   ├── pipeline-config.yaml            # Configuración del pipeline
│   └── databricks-connect.ini          # Config para Databricks Connect (opcional)
│
├── tests/                              # Tests automatizados
│   ├── test_bronze_layer.py
│   ├── test_silver_layer.py
│   ├── test_gold_layer.py
│   └── test_data_quality.py
│
├── submissions/                        # Carpeta para entregas de estudiantes
│   ├── README.md                       # Instrucciones de entrega
│   └── .gitkeep
│
└── instructor-notes/                   # Notas privadas para instructores
    ├── timing-tips.md                  # Tips de timing para cada clase
    ├── common-questions.md             # Preguntas frecuentes y respuestas
    ├── talent-identification.md        # Guía para identificar talento
    ├── feedback-template.md            # Template para feedback a estudiantes
    └── post-bootcamp-followup.md       # Seguimiento post-bootcamp
```

### Descripción de Carpetas Principales

#### `/docs` - Documentación

- Toda la documentación teórica y guías
- Diagramas y recursos visuales
- Glosario y referencias

#### `/slides` - Presentaciones

- Slides para Clase 1 (teoría)
- Slides para Clase 4 (producción)
- Formato PDF y editable

#### `/notebooks` - Material Práctico

- **Organizados por clase**: Cada clase tiene su carpeta
- **Starter vs Solution**: Notebooks iniciales para estudiantes y soluciones completas
- **README por lab**: Instrucciones específicas en cada carpeta

#### `/data` - Datasets

- **sample-data**: Dataset principal para clases 2 y 3
- **challenge-data**: Datasets alternativos para el challenge
- **Scripts de carga**: Automatización para subir a DBFS

#### `/solutions` - Respuestas (Solo Instructor)

- Soluciones completas de todos los labs
- Referencia para el challenge
- Ideal para tener en un branch separado o repo privado

#### `/scripts` - Automatización

- **setup**: Scripts de configuración inicial
- **validation**: Scripts para validar el trabajo de estudiantes
- **utilities**: Herramientas útiles (calculadora de costos, etc.)

#### `/config` - Configuraciones

- Configuración recomendada de clusters
- Configs para herramientas adicionales

#### `/tests` - Testing

- Tests automatizados para validar calidad
- Útil para enseñar buenas prácticas

#### `/submissions` - Entregas

- Carpeta donde los estudiantes pueden hacer fork y PR
- Organizada por estudiante

#### `/instructor-notes` - Guía del Instructor

- Tips de timing
- Identificación de talento
- Templates de feedback

---

## 🎯 Mejoras Adicionales Sugeridas

### 1. Pre-Bootcamp

- ✅ **Email de bienvenida** con checklist de preparación
- ✅ **Video de 5 minutos** explicando qué esperar
- ✅ **Encuesta pre-bootcamp** para evaluar nivel inicial

### 2. Durante el Bootcamp

- ✅ **Canal de Slack/Discord** para soporte en tiempo real
- ✅ **Breakout rooms** para trabajo en grupos pequeños
- ✅ **Sistema de "puntos"** para gamificar la participación
- ✅ **Quick polls** para verificar comprensión en tiempo real

### 3. Post-Bootcamp

- ✅ **Encuesta de feedback** detallada
- ✅ **Certificado de participación** (PDF personalizado)
- ✅ **Sesión de Office Hours** opcional para preguntas del challenge
- ✅ **Lista de recursos** para continuar aprendiendo
- ✅ **Invitación a comunidad** de alumni

### 4. Material de Apoyo Extra

- ✅ **Cheat sheet** de comandos Spark SQL y PySpark
- ✅ **Video cortos** (2-3 min) explicando conceptos clave
- ✅ **FAQ** actualizado basado en preguntas recurrentes
- ✅ **Casos de uso reales** de empresas argentinas usando Databricks

### 5. Mejoras de Evaluación

- ✅ **Auto-validación**: Scripts que los estudiantes puedan correr para verificar su progreso
- ✅ **Peer review**: Que los estudiantes revisen el trabajo de un compañero
- ✅ **Presentaciones cortas**: Top 3 estudiantes presentan su solución del challenge (5 min c/u)

---

## 📚 Recursos Adicionales Recomendados

### Para Instructores

1. **Databricks Educator Resources**: <https://www.databricks.com/learn/training/educator-resources>
2. **Community Forums**: <https://community.databricks.com/>
3. **Medium - Databricks Blog**: <https://medium.com/tag/databricks>

### Para Estudiantes

1. **Interactive SQL Tutorial**: <https://docs.databricks.com/sql/language-manual/index.html>
2. **PySpark Cheat Sheet**:
   <https://spark.apache.org/docs/latest/api/python/getting_started/quickstart.html>
3. **Delta Lake Tutorial**: <https://delta.io/learn/tutorials/>

### Datasets Argentinos Adicionales

1. **Transporte Público Buenos Aires**: <https://data.buenosaires.gob.ar/>
2. **Meteorología Nacional**: <https://www.smn.gob.ar/>
3. **INDEC - Estadísticas**: <https://www.indec.gob.ar/>

---

## ✅ Checklist de Implementación

### Antes del Bootcamp

- [ ] Crear estructura de carpetas según lo sugerido
- [ ] Subir datasets a DBFS
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
- [ ] Enviar certificados
- [ ] Identificar top performers para seguimiento
- [ ] Actualizar material basado en feedback
- [ ] Programar Office Hours si es necesario

---

## 💭 Conclusiones

Este plan de bootcamp es sólido y bien estructurado. Las mejoras sugeridas se enfocan en:

1. **Accesibilidad**: Enlaces directos para facilitar el acceso a recursos
2. **Claridad**: Mejor estructura de archivos y documentación
3. **Profundidad**: Más ejemplos de código y validaciones
4. **Evaluación**: Rúbricas claras y objetivas
5. **Seguimiento**: Sistema de identificación de talento más estructurado

La estructura de directorios propuesta permite:

- 📂 Organización clara por clase y tipo de contenido
- 🔄 Fácil navegación para estudiantes e instructores
- 📈 Escalabilidad para agregar más contenido
- 🎯 Separación clara entre material de estudiante e instructor
- ✅ Validación automatizada del progreso

**Próximos pasos recomendados:**

1. Implementar la estructura de directorios
2. Crear los notebooks starter con TODOs claros
3. Preparar las soluciones completas
4. Diseñar las slides con los diagramas sugeridos
5. Configurar el sistema de comunicación
6. Hacer un dry-run completo del bootcamp

¡Mucho éxito con el bootcamp! 🚀
