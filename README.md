# ⚽ Scouting de Delanteros | Top 5 Ligas Europeas (2024-2025)

## 🎯 Objetivo

Identificar delanteros con alto rendimiento ofensivo en las 5 grandes ligas europeas mediante métricas avanzadas y técnicas de machine learning, con el fin de detectar perfiles potencialmente infravalorados.

---

## 📊 Datos

- Fuente: Dataset de jugadores de las Top 5 ligas europeas (2024/25)
- Nivel: Estadísticas agregadas por jugador
- Variables utilizadas:
  - Goles (Gls), Asistencias (Ast), G+A
  - xG, xAG, npxG
  - Métricas por 90 minutos
  - Progresión (PrgC, PrgP, PrgR)

---

## ⚙️ Metodología

El pipeline de análisis sigue los siguientes pasos:

1. **Limpieza de datos**
   - Eliminación de porteros
   - Conversión de variables numéricas
   - Filtrado por experiencia (> 9 partidos completos)

2. **Definición de atacante**
   - Clasificación binaria: FW, LW, RW

3. **Selección de variables**
   - Regresión logística para identificar variables más relevantes
   - Evaluación mediante ROC AUC

4. **Reducción de multicolinealidad**
   - Eliminación de variables altamente correlacionadas (> 0.85)

5. **Clustering (KMeans)**
   - Segmentación de delanteros puros (FW)
   - Selección óptima de clusters mediante silhouette score

6. **Construcción de score ofensivo**
   - Estandarización de variables clave
   - Media de métricas ofensivas por jugador

---

## 🧠 Resultados

- Identificación de distintos perfiles ofensivos
- Detección de un cluster con mayor rendimiento ofensivo
- Generación de un ranking final de delanteros basado en un score compuesto

---

## 📁 Estructura del proyecto
scouting-delanteros/
│
├── 01_pipeline.ipynb
├── 02_informe.pdf
├── ranking_delanteros_final.csv
├── data/
│ └── top5-players24-25.csv
└── README.md

---

## ▶️ Reproducibilidad

Para ejecutar el proyecto:

1. Clonar el repositorio o descargar los archivos
2. Instalar dependencias:

```bash
pip install pandas numpy matplotlib seaborn scikit-learn

## 👤 Author

Yeray Martínez  
Master in Big Data & Artificial Intelligence
