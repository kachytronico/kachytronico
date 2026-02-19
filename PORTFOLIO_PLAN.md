# PORTFOLIO_PLAN.md

Plan de portfolio con dos rutas complementarias: Data Engineering y Applied ML/XAI en diabetes education.

## Ruta A: Data Engineering en salud/ONG/educación

### Objetivo
Demostrar capacidad para diseñar pipelines confiables, trazables y reproducibles con datos de salud/educación de fuentes públicas.

### Mini-proyecto A1: diabetes-data-pipeline
Entregables:
- Ingesta de datos (CSV/API) con validación de esquema.
- ETL con limpieza, estandarización y control de nulos/duplicados.
- Salida en formato analítico (Parquet/CSV curado) + reporte de calidad.
- CI con lint y tests básicos.

Checklist de calidad:
- [ ] README con objetivo, arquitectura y modo de ejecución.
- [ ] Pruebas mínimas para transformaciones críticas.
- [ ] Versionado de datos/documentación de fuentes.
- [ ] Reglas de calidad automatizadas (tipos, rangos, faltantes).
- [ ] Ejecución reproducible con un comando documentado.

### Mini-proyecto A2: health-education-indicators-mart
Entregables:
- Modelo de datos analítico (tablas limpias para consumo BI).
- Diccionario de datos y reglas de negocio documentadas.
- Consultas SQL de ejemplo para métricas educativas/preventivas.
- Dashboard base con indicadores clave.

Checklist de calidad:
- [ ] Definiciones de métricas claras y consistentes.
- [ ] SQL legible y revisable.
- [ ] Dataset y dashboard sincronizados por versión.
- [ ] Control de calidad en carga incremental.
- [ ] Evidencia de revisión técnica en PR.

## Ruta B: Applied ML/XAI en diabetes education

### Objetivo
Construir prototipos de IA explicable orientados a educación en diabetes y prevención, priorizando interpretabilidad y comunicación clara.

### Mini-proyecto B1: diabetes-glucose-pattern-explainer
Entregables:
- Modelo de predicción a corto plazo de patrón glucémico (orientativo).
- Capa de explicabilidad (global/local) para variables relevantes.
- Dashboard educativo con visualizaciones comprensibles.
- Informe de limitaciones y supuestos.

Checklist de calidad:
- [ ] Separación clara entre datos, entrenamiento y evaluación.
- [ ] Métricas reportadas con contexto no clínico.
- [ ] Explicaciones interpretables para público no técnico.
- [ ] Pruebas mínimas de pipeline y consistencia de features.
- [ ] Aviso visible: uso educativo/investigación, no clínico.

### Mini-proyecto B2: diabetes-prevention-risk-educator
Entregables:
- Estimación orientativa de riesgo de T2 para fines educativos.
- Módulo de recomendaciones en lenguaje claro.
- Recursos enlazados sobre hábitos y prevención.
- Evaluación básica de calibración y claridad de salida.

Checklist de calidad:
- [ ] Texto comprensible y no alarmista.
- [ ] Explicación de factores de riesgo usados por el modelo.
- [ ] Validaciones de entrada y manejo de errores.
- [ ] Pruebas de salida para casos de ejemplo.
- [ ] Aviso legal y ético en README y UI.

## Prioridad de ejecución
1. diabetes-data-pipeline
2. diabetes-glucose-pattern-explainer
3. health-education-indicators-mart
4. diabetes-prevention-risk-educator

## Criterios globales de calidad del portfolio
- Reproducibilidad: entorno y pasos de ejecución documentados.
- Calidad mínima: lint, tests básicos y CI activo.
- Trazabilidad: fuentes, supuestos y cambios documentados.
- Comunicación: README orientado a reclutadores y personas no técnicas.
- Ética: declaración explícita de uso no clínico en proyectos de diabetes.
