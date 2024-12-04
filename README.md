
# Análisis de datos de viajes compartidos

## Descripción del proyecto
Estás trabajando como analista para **Zuber**, una nueva empresa de viajes compartidos que se está lanzando en Chicago. Tu tarea es encontrar patrones en la información disponible. Quieres comprender las preferencias de los pasajeros y el impacto de los factores externos en los viajes.

Al trabajar con una base de datos, analizarás los datos de los competidores y probarás una hipótesis sobre el impacto del clima en la frecuencia de los viajes.

## Descripción de los datos
Tienes dos archivos CSV disponibles:

1. `/datasets/project_sql_result_01.csv`: Contiene los siguientes datos:
   - `company_name`: Nombre de la empresa de taxis.
   - `trips_amount`: Número de viajes de cada compañía de taxis el 15 y 16 de noviembre de 2017.

2. `/datasets/project_sql_result_04.csv`: Contiene los siguientes datos:
   - `dropoff_location_name`: Barrios de Chicago donde finalizaron los viajes.
   - `average_trips`: Promedio de viajes que terminaron en cada barrio en noviembre de 2017.

---

## Resultados de la hipótesis para las varianzas

- **Estadístico de Levene**: `0.38853489683656073`
- **Valor p**: `0.5332038671974493`
- **Conclusión**: No se rechaza la hipótesis nula; las varianzas son iguales.

## Resultados de la hipótesis para las medias

- **T-statistic**: `-6.946177714041499`
- **P-value**: `0.5332038671974493`
- **Conclusión**: No podemos rechazar la hipótesis nula; no hay evidencia suficiente para afirmar que las medias son diferentes.

---

### Explicación de las hipótesis

#### ¿Cómo planteaste las hipótesis nula y alternativa?

- **Hipótesis Nula (H₀)**: Las medias de ambos grupos son iguales, al menos estadísticamente.
- **Hipótesis Alternativa (H₁)**: Las medias de ambos grupos no son iguales o no son significativamente iguales.

Adicionalmente, los resultados muestran que las varianzas tienen valores muy cercanos, lo que respalda la igualdad asumida en H₀.

#### ¿Qué criterio usaste para probar las hipótesis y por qué?

1. **Nivel de significancia**: Se tomó un valor de alpha = `0.05`.
2. **Métodos utilizados**:
   - **Varianzas**: Se utilizó el método `stats.levene` de la librería `scipy` para calcular el estadístico de Levene y el p-valor, lo que permitió comparar las varianzas de las muestras.
   - **Medias**: Se utilizó el método `ttest.ind` de la librería `scipy`, que calcula el estadístico t y el p-valor para muestras independientes, permitiendo comparar las medias de los dos grupos.

---
