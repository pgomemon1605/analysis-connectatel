# 📊 Análisis ConnectaTel | Segmentación y comportamiento de clientes

## 📌 Descripción del proyecto

Análisis exploratorio de datos de **ConnectaTel**, una empresa de telecomunicaciones con operaciones en México y Colombia, utilizando Python para comprender el comportamiento de sus clientes durante 2024.

El proyecto busca identificar patrones de consumo, detectar inconsistencias en los datos, segmentar usuarios y generar recomendaciones comerciales que contribuyan a mejorar la oferta de servicios y la experiencia del cliente.

**Proyecto desarrollado como parte de mi formación en Data Analytics con TripleTen.**

## 🎯 Objetivos

- Explorar y limpiar información de clientes, planes y actividades de consumo.
- Identificar valores faltantes, sentinels y registros inconsistentes.
- Analizar la distribución de llamadas, mensajes y minutos acumulados.
- Detectar valores atípicos mediante boxplots y el método IQR.
- Segmentar clientes por edad y nivel de uso.
- Traducir los resultados en insights y recomendaciones comerciales.

## 🛠️ Herramientas utilizadas

- **Python:** lenguaje principal del análisis.
- **Pandas:** carga, limpieza, transformación y agrupación de datos.
- **NumPy:** operaciones numéricas y segmentación mediante condiciones.
- **Matplotlib y Seaborn:** visualización de distribuciones, histogramas y boxplots.
- **Google Colab / Jupyter Notebook:** desarrollo y documentación del análisis.
- **GitHub:** publicación y control de versiones del proyecto.

## 📂 Datos analizados

Se trabajó con tres datasets:

| Dataset | Información |
|---|---|
| `plans.csv` | Características y beneficios de los planes comerciales |
| `users_latam.csv` | Información demográfica, plan contratado y abandono de clientes |
| `usage.csv` | Registros de llamadas, mensajes y consumo |

**Volumen analizado:** 4.000 usuarios y 40.000 registros de actividad.

## 🔎 Metodología

**1. Exploración inicial:** revisión de estructuras, tipos de datos y estadísticas descriptivas.

**2. Diagnóstico de calidad:** identificación de nulos, valores inválidos, sentinels y fechas fuera del periodo analizado.

**3. Limpieza:** corrección de edades inválidas, estandarización de ciudades y tratamiento de fechas fuera de rango.

**4. Agregación por usuario:** construcción de métricas de cantidad de mensajes, llamadas y minutos acumulados.

**5. Visualización y detección de outliers:** análisis de distribuciones mediante histogramas, boxplots y límites IQR.

**6. Segmentación:** clasificación de clientes según edad y frecuencia de uso.

**7. Análisis ejecutivo:** interpretación de resultados y formulación de recomendaciones para el negocio.

## 📈 Principales hallazgos

### 1. Calidad de datos

- Se encontraron edades inválidas representadas por `-999`, que afectaban las estadísticas.
- El **14,13 % de los usuarios** quedó sin ciudad identificada después de estandarizar los valores faltantes.
- Se detectaron **40 fechas de registro fuera del periodo de estudio**.
- Se identificaron **28 eventos con valores en campos inesperados** para su tipo de actividad.
- Los nulos de duración y longitud de mensajes se explican principalmente por la estructura de los registros de llamadas y mensajes.

### 2. Perfil de clientes

- Edad promedio corregida: **48,14 años**.
- Plan Básico: **64,88 %** de los clientes.
- Plan Premium: **35,13 %** de los clientes.
- El nivel de uso predominante es **Uso medio**, con aproximadamente el 73 % de la base, según la visualización de segmentos.

### 3. Comportamiento de consumo

Entre los usuarios con actividad registrada:

| Indicador | Promedio |
|---|---:|
| Mensajes por usuario | 5,52 |
| Llamadas por usuario | 4,48 |
| Minutos acumulados por usuario | 22,84 |

Los minutos de llamada presentan una distribución sesgada hacia la derecha, con algunos usuarios que alcanzan **155,69 minutos acumulados**.

### 4. Valores atípicos

Se identificaron outliers superiores en mensajes, llamadas y minutos acumulados. Se decidió conservarlos, debido a que podrían representar comportamientos legítimos de usuarios con mayor actividad.

## 💡 Insights y recomendaciones comerciales

| Hallazgo | Recomendación para ConnectaTel |
|---|---|
| Predominio de usuarios de Uso medio | Evaluar beneficios de fidelización y estrategias que fortalezcan el aprovechamiento de los servicios |
| Segmento de Bajo uso | Investigar posibles barreras de consumo y probar campañas de activación |
| Segmento de Alto uso | Evaluar paquetes adicionales de llamadas o mensajes según necesidades verificadas |
| Consumos extremos de minutos | Analizar si algunos clientes requieren planes más flexibles |
| Mayor participación del plan Básico | Evaluar oportunidades de fidelización y migración a Premium cuando exista una necesidad real |
| Datos geográficos incompletos | Mejorar los procesos de captura y validación de información |
| Diferentes grupos de edad | Profundizar en el cruce entre edad, consumo y plan antes de diseñar ofertas específicas |

Estas recomendaciones representan **oportunidades e hipótesis comerciales derivadas del análisis descriptivo**, no resultados de intervenciones ya implementadas.

## ⚠️ Limitaciones del análisis

- La información de consumo corresponde al periodo registrado en el dataset, por lo que las métricas no deben interpretarse como promedios mensuales.
- Se requiere analizar ingresos, costos y abandono para identificar los segmentos de mayor rentabilidad y riesgo de churn.
- Los porcentajes por nivel de uso son aproximaciones visuales que deben confirmarse antes de utilizarlos como indicadores definitivos.
- Se identificó un usuario sin métricas agregadas de consumo cuya clasificación requiere revisión.

## 📓 Notebook del proyecto

**[Ver el análisis completo en Python](./S7_Version_Estudiante_Project_ConnectaTel.ipynb)**

El Notebook contiene el proceso de exploración, limpieza, transformación, visualización, segmentación y análisis ejecutivo.

**Nota de reproducibilidad:** algunas rutas de carga originales (`/datasets/`) pertenecen al entorno de aprendizaje de TripleTen. Para ejecutar el proyecto en otro entorno, es necesario disponer de los datasets autorizados y ajustar las rutas correspondientes.

## ✅ Conclusión

Este proyecto demuestra la aplicación de Python al ciclo de análisis de datos: desde la revisión de calidad y preparación de la información hasta la identificación de patrones y formulación de recomendaciones orientadas al negocio.

El principal aprendizaje es que **el valor del análisis no está solamente en generar estadísticas o visualizaciones, sino en interpretar los resultados y convertirlos en oportunidades de decisión fundamentadas en evidencia**.
