# PORTFOLIO_PLAN.md — Plan de posicionamiento profesional

Dos rutas de posicionamiento para un perfil junior en Data/AI con foco en impacto social.

---

## Ruta A — Data Engineering / Analytics para el sector social

### Objetivo de posicionamiento
Demostrar capacidad para construir pipelines de datos robustos y análisis reproducibles sobre datos sociales reales (educación, exclusión, servicios sociales), con calidad de producción mínima viable.

---

### Proyecto A-1: `social-data-pipeline`

**Descripción**: Pipeline ETL end-to-end sobre un dataset de indicadores de exclusión social o servicios sociales públicos (p. ej., datos del INE, Ministerio de Derechos Sociales o Eurostat).

**Entregables mínimos**:
- Ingesta desde fuente pública (CSV / API) con validación de esquema.
- Transformaciones con pandas o PySpark (limpieza, normalización, aggregations).
- Capa de salida: Parquet + informe HTML generado automáticamente.
- Tests de calidad de datos con `pytest` o `great_expectations` básico.
- CI con GitHub Actions (lint + tests en cada PR).

**Estructura de repo**:
```
social-data-pipeline/
├── data/               # datos de muestra o instrucciones de descarga
├── src/
│   ├── ingest.py
│   ├── transform.py
│   └── report.py
├── tests/
│   └── test_transform.py
├── notebooks/          # EDA exploratoria (opcional)
├── .github/workflows/  # CI pipeline
├── Dockerfile
├── requirements.txt
└── README.md
```

**Checklist de calidad**:
- [ ] README explica propósito, instalación y cómo ejecutar el pipeline.
- [ ] Datos sensibles NO incluidos en el repo (usar `.gitignore` y muestras anónimas).
- [ ] Al menos 3 tests que validen transformaciones clave.
- [ ] Pipeline ejecutable con un solo comando (`make run` o `docker compose up`).
- [ ] Lint pasa sin errores (`ruff` o `flake8`).
- [ ] Notebook de EDA con conclusiones en lenguaje natural.

---

### Proyecto A-2: `inclusive-edu-analytics`

**Descripción**: Análisis exploratorio y dashboard sobre datos educativos públicos (p. ej., estadísticas de necesidades educativas especiales, abandono escolar, recursos por comunidad autónoma).

**Entregables mínimos**:
- Notebook Jupyter con EDA completo: distribuciones, tendencias temporales, mapas o gráficos de barras.
- Al menos una visualización interactiva (Plotly o similar).
- Resumen ejecutivo en el README orientado a responsables de políticas educativas.
- Export de figuras en `/outputs`.

**Estructura de repo**:
```
inclusive-edu-analytics/
├── data/               # dataset de muestra o enlace a fuente
├── notebooks/
│   ├── 01_eda.ipynb
│   └── 02_visualizations.ipynb
├── outputs/            # figuras exportadas
├── src/
│   └── utils.py        # funciones de limpieza reutilizables
├── tests/
│   └── test_utils.py
├── requirements.txt
└── README.md
```

**Checklist de calidad**:
- [ ] Fuente de datos claramente citada con licencia.
- [ ] Notebooks ejecutables de arriba a abajo sin errores (`nbconvert --execute`).
- [ ] Funciones de utilidad testadas con `pytest`.
- [ ] Conclusiones del análisis escritas en el README (mínimo 3 hallazgos).
- [ ] Visualizaciones accesibles: paletas de colores aptas para daltonismo.
- [ ] CI ejecuta los tests en cada push.

---

## Ruta B — Applied ML / NLP para accesibilidad

### Objetivo de posicionamiento
Demostrar capacidad para construir prototipos de ML/NLP aplicados a necesidades reales de personas con diversidad funcional o dificultades comunicativas, con código limpio y reproducible.

---

### Proyecto B-1: `aac-nlp-tool`

**Descripción**: Prototipo de herramienta NLP para apoyar la comunicación aumentativa y alternativa (CAA). Por ejemplo: sugerencia de pictogramas a partir de texto libre, simplificación automática de textos, o clasificador de intención para sistemas AAC.

**Entregables mínimos**:
- Script o aplicación CLI que toma texto como input y devuelve sugerencias/simplificaciones.
- Modelo fine-tuned o uso de modelo preentrenado (HuggingFace Transformers / spaCy) con justificación de elección.
- Evaluación cuantitativa básica (accuracy, BLEU o métrica adecuada) sobre un conjunto de prueba.
- Documentación del caso de uso y limitaciones conocidas del modelo.

**Estructura de repo**:
```
aac-nlp-tool/
├── data/
│   ├── samples/        # ejemplos de entrada/salida (no datos personales)
│   └── README.md       # descripción de datos y cómo obtenerlos
├── src/
│   ├── model.py        # carga y uso del modelo
│   ├── preprocess.py
│   └── evaluate.py
├── tests/
│   └── test_preprocess.py
├── notebooks/
│   └── 01_exploration.ipynb
├── .github/workflows/
├── Dockerfile
├── requirements.txt
└── README.md
```

**Checklist de calidad**:
- [ ] README describe el problema real que resuelve la herramienta y para quién.
- [ ] No se incluyen datos personales ni imágenes de personas reales.
- [ ] Limitaciones y sesgos del modelo documentados explícitamente.
- [ ] Tests cubren al menos las funciones de preprocesamiento.
- [ ] Instrucciones para reproducir resultados de evaluación.
- [ ] Modelo descargable (HuggingFace Hub u otro) o instrucciones de entrenamiento.
- [ ] CI pasa lint y tests en cada PR.

---

### Proyecto B-2: `ml-reproducible-template`

**Descripción**: Plantilla de proyecto ML lista para usar, pensada para proyectos de impacto social. Incluye estructura de carpetas, Dockerfile, GitHub Actions, configuración de lint y estructura de tests.

**Entregables mínimos**:
- Repositorio plantilla en GitHub (usar la función "Template repository").
- Ejemplo end-to-end funcional: clasificador simple con scikit-learn sobre dataset público.
- Dockerfile que construye el entorno sin errores.
- GitHub Actions: lint + tests + (opcional) build de imagen Docker.
- README detallado con instrucciones de uso de la plantilla.

**Estructura de repo**:
```
ml-reproducible-template/
├── data/
│   └── .gitkeep
├── src/
│   ├── train.py
│   ├── predict.py
│   └── utils.py
├── tests/
│   ├── test_train.py
│   └── test_utils.py
├── notebooks/
│   └── exploration.ipynb
├── .github/
│   └── workflows/
│       └── ci.yml
├── Dockerfile
├── docker-compose.yml
├── pyproject.toml          # o requirements.txt + setup.cfg
├── Makefile                # comandos: make train, make test, make lint
└── README.md
```

**Checklist de calidad**:
- [ ] `make test` ejecuta todos los tests sin errores.
- [ ] `docker compose up` levanta el entorno correctamente.
- [ ] `make lint` pasa sin warnings.
- [ ] README incluye sección "Cómo usar esta plantilla" paso a paso.
- [ ] Ejemplo funcional con un dataset real (Iris, datos del INE, etc.).
- [ ] `.gitignore` cubre modelos entrenados, datos grandes y artefactos de build.
- [ ] Etiquetado como "Template repository" en GitHub.

---

## Notas generales de posicionamiento

- **Prioridad**: Publicar primero los proyectos A-1 y B-2, ya que tienen el mayor impacto de señal técnica para empleadores.
- **Visibilidad**: Pinear los 4–5 repos más representativos en el perfil de GitHub.
- **Privacidad**: Mantener privados todos los repos de tareas del curso; solo publicar trabajo propio con documentación completa.
- **Iteración**: Es mejor un proyecto pequeño bien documentado que uno grande a medias. Aplica el principio de MVP también al portfolio.
