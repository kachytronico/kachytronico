# PORTFOLIO_PLAN.md — Plan de posicionamiento

Dos rutas de posicionamiento para construir un portfolio junior sólido
en Data/AI con enfoque en impacto social.

---

## Ruta A — Data Engineering / Analytics para sector social

### Objetivo de posicionamiento
Perfil: *Data Engineer / Data Analyst junior* para ONGs, administraciones públicas
o empresas del tercer sector que necesiten transformar datos en decisiones.

### Proyecto A-1 · Dashboard de indicadores sociales

**Descripción**
Pipeline completo de ingestión → limpieza → agregación → visualización
de indicadores sociales públicos (p. ej., datos del INE, Eurostat o portales open data municipales).

**Entregables mínimos**
- [ ] Script de descarga / ingestión de datos (API o CSV)
- [ ] Notebook de exploración y limpieza con pandas
- [ ] Dashboard interactivo con Streamlit o similar
- [ ] README con fuente de datos, instrucciones de ejecución y capturas

**Estructura de repo sugerida**
```
social-data-dashboard/
├── data/               # datos de muestra (no datos sensibles)
├── notebooks/          # exploración y limpieza
├── src/
│   ├── ingest.py
│   ├── transform.py
│   └── dashboard.py
├── tests/
│   └── test_transform.py
├── Dockerfile
├── requirements.txt
└── README.md
```

**Checklist de calidad**
- [ ] Datos de muestra incluidos o instrucciones claras para obtenerlos
- [ ] Tests de esquema de datos (mínimo: columnas y tipos esperados)
- [ ] GitHub Actions: lint (flake8/ruff) + tests en cada PR
- [ ] Sin credenciales ni datos personales en el repo
- [ ] Sección "Limitaciones y próximos pasos" en el README

---

### Proyecto A-2 · ETL con PySpark para fuentes del sector social

**Descripción**
Pipeline ETL escalable que consolida múltiples fuentes heterogéneas
(CSV, JSON, API REST) de organizaciones sociales en un esquema analítico unificado.

**Entregables mínimos**
- [ ] Jobs de PySpark para extracción, transformación y carga
- [ ] Esquema de datos documentado (campo, tipo, descripción)
- [ ] Tests unitarios de las transformaciones principales
- [ ] README con diagrama de flujo de datos (puede ser ASCII)

**Estructura de repo sugerida**
```
spark-etl-social/
├── jobs/
│   ├── extract.py
│   ├── transform.py
│   └── load.py
├── tests/
│   └── test_transform.py
├── schemas/
│   └── output_schema.json
├── docker-compose.yml
├── requirements.txt
└── README.md
```

**Checklist de calidad**
- [ ] Docker Compose con Spark standalone para desarrollo local
- [ ] Tests con datos sintéticos (sin datos reales de personas)
- [ ] GitHub Actions: lint + tests
- [ ] Documentación del esquema de salida
- [ ] Sección de rendimiento aproximado (filas procesadas, tiempo)

---

## Ruta B — Applied ML / NLP para accesibilidad

### Objetivo de posicionamiento
Perfil: *ML Engineer / NLP Engineer junior* para proyectos de accesibilidad,
lectura fácil, comunicación aumentativa o adaptación de contenidos educativos.

### Proyecto B-1 · Simplificación automática de textos (Lectura Fácil)

**Descripción**
Prototipo de NLP que toma un texto en español y genera una versión
simplificada siguiendo principios de Lectura Fácil (frases cortas,
vocabulario básico, estructura clara).

**Entregables mínimos**
- [ ] Dataset de pares (texto original → texto simplificado) con fuentes abiertas
- [ ] Baseline con reglas heurísticas (longitud de frase, sustitución léxica)
- [ ] Comparación con modelo preentrenado (p. ej., mT5 o similar via HuggingFace)
- [ ] Métricas: BLEU, SARI y legibilidad (índice Flesch-Szigriszt en español)
- [ ] README con motivación, datos y resultados

**Estructura de repo sugerida**
```
easy-read-nlp/
├── data/
│   └── samples/        # ejemplos públicos, sin datos personales
├── notebooks/
│   ├── 01_eda.ipynb
│   └── 02_baseline.ipynb
├── src/
│   ├── preprocess.py
│   ├── baseline.py
│   └── metrics.py
├── tests/
│   └── test_metrics.py
├── requirements.txt
└── README.md
```

**Checklist de calidad**
- [ ] Datos de muestra reproducibles (seed fijo o datos públicos enlazados)
- [ ] Métricas automáticas calculadas y guardadas en `results/`
- [ ] GitHub Actions: lint + tests
- [ ] Sin PII en datos ni en código
- [ ] Sección de sesgo y limitaciones del modelo en el README

---

### Proyecto B-2 · Clasificador de barreras de accesibilidad

**Descripción**
Modelo de clasificación (scikit-learn) que, dado el texto descriptivo
de un recurso educativo o servicio, predice qué tipo de barreras
de accesibilidad puede presentar (visual, auditiva, cognitiva, motora).

**Entregables mínimos**
- [ ] Dataset etiquetado (puede ser sintético o de fuentes abiertas)
- [ ] Pipeline de scikit-learn: vectorización + clasificador
- [ ] Evaluación con cross-validation y matriz de confusión
- [ ] Script de inferencia por línea de comandos
- [ ] README con descripción de clases y métricas obtenidas

**Estructura de repo sugerida**
```
ml-accesibilidad/
├── data/
│   └── dataset.csv     # datos de muestra etiquetados
├── notebooks/
│   └── 01_eda_and_model.ipynb
├── src/
│   ├── train.py
│   ├── predict.py
│   └── evaluate.py
├── models/
│   └── .gitkeep        # modelos generados localmente, no versionados
├── tests/
│   └── test_pipeline.py
├── requirements.txt
└── README.md
```

**Checklist de calidad**
- [ ] Seed fijo para reproducibilidad (`random_state` en todos los pasos)
- [ ] Modelo no versionado en git (añadir `models/*.pkl` a `.gitignore`)
- [ ] Tests: al menos prueba de que el pipeline entrena y predice sin errores
- [ ] GitHub Actions: lint + tests
- [ ] Métricas reportadas por clase (precision / recall / F1)
- [ ] Sección de limitaciones y posibles sesgos en el README

---

## Checklist general para ambas rutas

- [ ] Cada repo tiene su propio README con: objetivo, datos, instrucciones, limitaciones
- [ ] Cada repo tiene GitHub Actions configurado (lint + tests básicos)
- [ ] Ningún repo contiene credenciales, datos personales ni datos del curso
- [ ] Los 4–6 mejores repos están fijados en el perfil de GitHub
- [ ] Los repos de tareas del curso permanecen privados
- [ ] El README de perfil (este repositorio) enlaza los repos cuando estén listos
