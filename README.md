# 🎮 Análisis Estadístico de Ventas de Videojuegos por Plataforma

> **Autor:** Xiomara Suescun Naizaque | Data Analyst Junior  
> **Herramientas:** Python · Pandas · NumPy · Matplotlib · SciPy  
> **Tipo de análisis:** Data Cleaning + EDA + Pruebas de Hipótesis

---

## 📌 Contexto y Objetivo

La industria de los videojuegos es altamente competitiva y dinámica. Este proyecto analiza datos históricos de ventas globales de videojuegos por plataforma, género y región, con el objetivo de identificar los factores que determinan el éxito comercial de un juego y proyectar tendencias para apoyar decisiones de inversión en títulos y plataformas.

---

## 🗂️ Dataset

| Columna | Descripción |
|--------|-------------|
| `name` | Nombre del videojuego |
| `platform` | Plataforma (PS4, X360, XOne, etc.) |
| `year_of_release` | Año de lanzamiento |
| `genre` | Género del juego |
| `na_sales` | Ventas en Norteamérica (millones) |
| `eu_sales` | Ventas en Europa (millones) |
| `jp_sales` | Ventas en Japón (millones) |
| `critic_score` | Puntuación de críticos |
| `user_score` | Puntuación de usuarios |
| `rating` | Clasificación ESRB |

---

## 🔧 Metodología

**Paso 1 — Descripción de los datos**  
Carga y exploración inicial del dataset para entender su estructura, tipos de datos y valores ausentes.

**Paso 2 — Preprocesamiento (Data Cleaning)**  
- Conversión de `year_of_release` de float a `Int64`
- Valores `'tbd'` en `user_score` reemplazados con `NaN` y convertidos a `float`
- Valores ausentes en `rating` reemplazados con `'RP'` (Rating Pending)
- Creación de columna `total_sales` = suma de ventas por región

**Paso 3 — Análisis Exploratorio (EDA)**  
Visualizaciones y métricas sobre lanzamientos por año, ventas por plataforma, correlación con puntuaciones y distribución por género.

**Paso 4 — Perfil de usuario por región**  
Análisis de preferencias de plataforma, género y clasificación ESRB por región (NA, EU, JP).

**Paso 5 — Pruebas de Hipótesis**  
Pruebas estadísticas con `scipy.stats` para validar diferencias en calificaciones entre plataformas y géneros.

---

## 📊 Hallazgos Principales

### 📅 Lanzamientos y ciclo de vida de plataformas
- Los años con mayor cantidad de juegos lanzados fueron **2007 y 2008**
- Las plataformas tienen un **ciclo de vida aproximado de 5 años**
- Se filtró el dataset desde **2012 en adelante** para construir un modelo predictivo relevante

### 🏆 Plataformas y ventas
- **PS4** fue la plataforma con mayores ventas globales en el período analizado, aunque comenzó a declinar en el primer semestre de **2015**
- **X360** registró el mayor número de ventas en el modelo filtrado (2012-2016)
- La puntuación de críticos en PS4 muestra correlación positiva con las ventas a partir del rango **60-80**
- En X360 la correlación aumenta entre **50 y 70**, y disminuye en puntajes superiores a 80

### 🌍 Perfil de usuario por región
- **Norteamérica (NA):** domina en géneros Action, Shooter y Sports
- **Europa (EU):** preferencias similares a NA con ligeras variaciones en Sports
- **Japón (JP):** el género **Role-Playing** es estable en las 3 regiones; en Action, Shooter, Sports y Misc las ventas de JP se ven afectadas por NA y EU
- Para los ratings **M, E, E10+ y T**, JP se ve impactado por NA y EU; el rating **RP** es estable en las 3 regiones

### 🎯 Géneros más vendidos
- 🥇 **Shooter** — género con mayores ventas globales
- 🥈 **Action** — segundo género más popular
- 🥉 **Sports** — tercer lugar en ventas
- 📉 **Adventure** — género con las ventas más bajas

### 🧪 Pruebas de Hipótesis
| Hipótesis | Resultado |
|-----------|-----------|
| Las calificaciones promedio de usuarios de **Xbox One y PC son iguales** | ✅ No se rechaza — las calificaciones son estadísticamente similares |
| Las calificaciones promedio de usuarios de **Action y Sports son diferentes** | ✅ Se rechaza — existe diferencia estadísticamente significativa |

---

## 💡 Recomendaciones

1. **Invertir en PS4 y XOne** — son las plataformas con mayor proyección de ventas en el período analizado
2. **Priorizar el género Shooter y Action** — dominan en las regiones de mayor volumen (NA y EU)
3. **Desarrollar contenido Role-Playing para Japón** — es el único género con ventas estables en las 3 regiones simultáneamente
4. **Considerar la puntuación de críticos** — una puntuación entre 60-80 tiene correlación positiva con ventas; es un indicador clave de desempeño comercial
5. **Adaptar estrategias por región** — los géneros y ratings más exitosos varían significativamente entre NA/EU y JP

---

## ✅ Conclusión

El análisis revela que el éxito comercial de un videojuego depende de una combinación de plataforma, género y región. PS4 lideró las ventas globales en el período analizado, con North America concentrando el mayor volumen gracias al género Action. Japón muestra un comportamiento independiente, con preferencia marcada por el Role-Playing. Las pruebas estadísticas confirman que las calificaciones de usuarios varían de forma significativa entre géneros, pero no entre plataformas como Xbox One y PC — un dato relevante para decisiones de desarrollo y distribución.

---

## 📁 Estructura del Proyecto
📦 Statistical-Analysis-of-Video-Game-Sales-by-Platform

┣ 📓 video_games.ipynb    # Análisis completo en Python

┣ 📄 README.md            # Resumen ejecutivo del proyecto