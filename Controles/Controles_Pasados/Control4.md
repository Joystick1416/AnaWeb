# Control 4

*Grafos web — PageRank y HITS*

1. Defina una wiki de inicio.
2. Realice el scraping respectivo y obtenga todas las URLs que dirigen a otra wiki.
3. Repita el procedimiento con las wikis obtenidas en el paso 2.
4. Construya la matriz de adyacencia con toda la información recolectada.
5. En base a los algoritmos **PageRank** y **HITS**, obtenga las top 20 wikis más relevantes según: PageRank, autoridad y *hubs*. Realice *N* iteraciones hasta alcanzar convergencia — se considera alcanzada cuando los valores de una iteración son iguales a los de la anterior, o cuando la distancia euclidiana entre ambos es menor que una tolerancia (defina la tolerancia con un valor pequeño).
6. Finalmente, reporte cuáles son las páginas que se encuentran en los 3 rankings finales (PageRank, autoridad, hubs).
