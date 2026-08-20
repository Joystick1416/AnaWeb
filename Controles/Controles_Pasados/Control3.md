# Control 3

*Web scraping + clasificación de texto*

## Pregunta 1

En base a la siguiente URL: [resultadoshistorico.onpe.gob.pe/EG2021](https://resultadoshistorico.onpe.gob.pe/EG2021/)

Reporte cuál ha sido el local de votación en el distrito de Jesús María que ha tenido la mayor cantidad de mesas electorales.

## Pregunta 2

1. Recolectar 120 wikis de 2 categorías/clases distintas (60 de cada una).
2. Separar de forma aleatoria 50 wikis para *train* y 10 wikis para *test* (de cada categoría).
3. Realizar una limpieza básica: minúsculas y sin signos de puntuación.
4. Vectorizar usando su implementación de TF y TF-IDF, con y sin top-N (modo 1, modo 2).
5. Por cada vectorizador, encontrar los feature vectors (FV) promedio de cada categoría/clase.
6. Finalmente, para las 20 wikis extra (10 de cada clase): limpiar, vectorizar y medir la distancia de coseno con los FV representativos, para indicar cuál es el mejor vectorizador.
