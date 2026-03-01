# Análisis y Dashbaord de Sismicidad en Colombia (Acosta & Camargo)

Este proyecto es un análisis integral de la sismicidad en Colombia (2010 - 2026) utilizando técnicas de aprendizaje no supervisado (K-Means Clustering) para identificar patrones tectónicos y crear un panel de visualización interactivo.

## 🚀 Lo que hemos logrado

A lo largo de este proyecto, hemos desarrollado una solución de extremo a extremo para el análisis sísmico:

1. **Recopilación y Limpieza de Datos:** 
   - Extracción de datos geoespaciales y sísmicos directamente desde la API del USGS.
   - Filtrado inteligente de "microrruido" sísmico (sismos de muy baja magnitud que ensucian visualmente los patrones tectónicos), quedándonos con **2,971 eventos sísmicos significativos**. Esta decisión metodológica permite que los algoritmos de clustering identifiquen de manera mucho más nítida las estructuras geológicas principales (como los nidos sísmicos y las fallas superficiales).

2. **Modelado Avanzado (Clustering K-Means):**
   - Estandarización de variables clave (Latitud, Longitud, Profundidad).
   - Aplicación de K-Means con $K=5$, una elección justificada tanto por el Método del Codo y la métrica Silhouette, como por la coherencia geológica del país (separando claramente, por ejemplo, el Nido de Bucaramanga de las zonas de subducción del Pacífico).

3. **Notebook de Experimentación (`taller1.ipynb`):**
   - Un pipeline completo en Jupyter Notebook que guía a través del Análisis Exploratorio de Datos (EDA), Preparación, Modelado y Evaluación.
   - Incluye mapeo dinámico e inteligente que nombra los clústeres no por su ID algorítmico, sino por sus características espaciales y de profundidad reales.

4. **Dashboard Interactivo (`dashboard.py`):**
   - Una aplicación web en Streamlit rica en interactividad.
   - **Estructura Tridimensional:** Un mapa 3D que permite visualizar la profundidad real de los nidos sísmicos (como la inmersión de la placa de Nazca bajo la placa Sudamericana).
   - **Diagnóstico Regional (Snake Plot):** Gráficos avanzados para comparar perfiles y métricas sísmicas entre las diferentes zonas identificadas.
   - **Presupuesto y Contexto Institucional:** Comparativas de presupuesto (2025) entre el SGC (Servicio Geológico Colombiano) y la UNGRD.

## 📁 Estructura del Proyecto

- `dashboard.py`: Aplicación principal de Streamlit.
- `taller1.ipynb`: Notebook con el proceso analítico paso a paso.
- `reporte.md`: Reporte ejecutivo con hallazgos clave, interpretaciones geológicas y justificaciones metodológicas.
- `data/`: Directorio que contiene los datos descargados, procesados y los perfiles de los clústeres (`clustered_data.csv`, `cluster_profile.csv`).

## 🛠️ Cómo Ejecutar el Dashboard

1. Abre una terminal.
2. Navega al directorio del proyecto (`Camargo_Miguel_Taller1`).
3. Ejecuta el siguiente comando:
   ```bash
   streamlit run dashboard.py
   ```
