# 🚦 Movilidad Urbana y Productividad Económica en Latinoamérica

![Python](https://img.shields.io/badge/Python-3.10-blue?logo=python)
![Pandas](https://img.shields.io/badge/Pandas-2.0-150458?logo=pandas)
![Seaborn](https://img.shields.io/badge/Seaborn-Visualizaci%C3%B3n-3776AB)
![Status](https://img.shields.io/badge/Status-Completado-brightgreen)

## 📌 Descripción del proyecto

Análisis que evalúa cómo la **movilidad urbana** (congestión, tiempos de traslado) se relaciona
con la **productividad económica** (PIB per cápita) en las principales ciudades de
Latinoamérica y el mundo, combinando datos de tráfico en tiempo real con indicadores económicos.

## 🎯 Objetivos

- Explorar y limpiar datos de tráfico (TomTom Traffic Index) e indicadores económicos (OECD Cities)
- Estandarizar, unir y consolidar ambas fuentes de datos a nivel ciudad-año
- Analizar visualmente la relación entre congestión vehicular y PIB per cápita
- Identificar ciudades atípicas y priorizar oportunidades de inversión en infraestructura

## 🗂️ Fuente de los datos

- **Tráfico:** TomTom Traffic Index (`tomtom_traffic.csv`)
- **Economía:** OECD Cities (`oecd_city_economy.csv`)
- **Periodo analizado:** 2024
- **Cobertura:** 30 ciudades, 24 países

## 🛠️ Herramientas utilizadas

| Herramienta | Uso |
|---|---|
| Python (Pandas, NumPy) | Carga, limpieza, transformación y unión de datasets |
| Matplotlib / Seaborn | Boxplots, histogramas y gráficos comparativos |
| Jupyter Notebook | Desarrollo del análisis completo |

## 🔍 Metodología

1. **Carga y exploración inicial** de ambos datasets, identificando tipos de dato incorrectos
2. **Limpieza y estandarización**: nombres de columnas a `snake_case`, conversión de fechas a
   `datetime`, limpieza de formatos numéricos con separadores europeos (PIB, desempleo, población)
3. **Filtrado y agregación**: extracción del año y cálculo de promedios de tráfico por ciudad
4. **Unión de datasets** (`merge` tipo INNER) por ciudad y año para combinar movilidad y economía
5. **Visualización**: boxplot de retrasos por atascos, histograma de PIB per cápita, y
   comparativa de barras entre congestión y PIB por ciudad
6. **Exportación** del dataset limpio y consolidado a CSV

## 📈 Hallazgos clave

![Comparativa tráfico vs PIB](img/comparativa_trafico_pib.png)

- 🔑 **No existe una relación lineal directa** entre movilidad urbana y productividad económica —
  el patrón observado es más bien de **"desarrollo desigual"** que de correlación simple
- 🚨 **Ciudad de México** es el caso más crítico: presenta el `jams_delay` más alto de todo el
  dataset (2,833), muy por encima de ciudades con economías más grandes, mientras su PIB per
  cápita es significativamente menor al de ciudades con menos tráfico
- 🔄 **Ciudades como Abu Dhabi** muestran el patrón opuesto: PIB per cápita muy elevado con
  niveles de congestión relativamente altos, evidenciando que la riqueza no elimina el problema
- 🏙️ La congestión parece estar más ligada a la **falta de infraestructura de transporte masivo**
  que al nivel de ingresos de la ciudad

## 💡 Recomendaciones de negocio

- **Ciudad de México** surge como la ciudad prioritaria para inversión urgente en infraestructura
  de transporte, dado su índice de congestión extremo combinado con productividad inferior a la
  esperada
- **Bogotá y Lima** muestran un patrón similar (aunque de menor magnitud) y deberían considerarse
  como siguientes candidatas de análisis e inversión
- Validar estas conclusiones con un análisis de correlación formal y series temporales de años
  adicionales antes de tomar decisiones de inversión definitivas

## 📁 Estructura del repositorio

```
movilidad-economia-latam/
├── data/
│   ├── tomtom_traffic.csv
│   ├── oecd_city_economy.csv
│   └── ladb_mobility_economy_2024_clean.csv
├── notebooks/
│   └── mobility_economy_project.ipynb
├── img/
│   └── comparativa_trafico_pib.png
├── requirements.txt
└── README.md
```

## ▶️ Cómo reproducir este análisis

```bash
git clone https://github.com/tu-usuario/movilidad-economia-latam.git
cd movilidad-economia-latam
pip install -r requirements.txt
jupyter notebook notebooks/mobility_economy_project.ipynb
```

## 👤 Autor

**Tu Nombre**
[LinkedIn](https://linkedin.com/in/tu-usuario) · [Portafolio](https://tu-portafolio.com)
