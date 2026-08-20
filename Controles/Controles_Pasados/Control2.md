# Control 2 y Bonus PC1

*Web scraping + TF / TF-IDF*

## Importante

- Cualquier intento de plagio y/o uso de material no autorizado (IA, códigos, etc.) invalida su evaluación y obtendrá nota **0**.
- De los 4 ejercicios, deberá elegir **2 ejercicios para su Bonus** (máximo 4 puntos) y **2 ejercicios para su Control 2** (máximo 5 puntos).
- Los ejercicios del bonus deberán ser resueltos de forma **completa** — no será considerada una respuesta incompleta.

## Ejercicio 1

En base a la siguiente página: [universidadperu.com — bolsa de trabajo](https://www.universidadperu.com/trabajo-bolsa-universidad-peru.php)

Realice el scraping respectivo para reportar, en base al año **2025**:

- ¿Cuál fue el mes con la mayor cantidad de ofertas de trabajo? (indicar mes y cantidad)
- ¿Cuál es el puesto laboral más ofertado?
- ¿Cuál fue la fecha (dd/mm/yyyy) en la que se ofertaron más trabajos?
- Listar todos los correos electrónicos incluidos en las ofertas de trabajo.

## Ejercicio 2

En base a **todos los años históricos** de la misma página:

- ¿Cuál es el año con la mayor cantidad de ofertas de trabajo?
- Reportar el puesto más ofertado.

## Ejercicio 3

La siguiente página contiene un ranking de las 250 mejores películas de todos los tiempos: [IMDb Top 250](https://www.imdb.com/es-es/chart/top/?ref_=nv_mv_250)

Obtenga la siguiente información de cada película:

- Nombre
- Año
- Puntuación
- Duración
- Categorías
- Resumen

Toda la información debe exportarse en un archivo TXT o CSV con el nombre `top250.txt` / `top250.csv`.

## Ejercicio 4

- Vectorice cada una de las descripciones (resumen) de las películas, usando **TF** y **TF-IDF** — obtendrá 2 feature vectors por película.
- Por cada categoría, obtenga el promedio de los feature vectors de las películas que pertenecen a ella. Debería obtener 2 promedios: uno con TF y otro con TF-IDF.
- Implemente una función que reciba la descripción (resumen) de una película y retorne las 3 categorías a las que pertenece, en base a las 3 distancias menores entre el feature vector de la descripción de entrada y los feature vectors promedio obtenidos en el paso anterior.
