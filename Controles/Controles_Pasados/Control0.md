# Control 0

*Algoritmia — manipulación de dígitos*

## Números similares

**Definición:** dos números enteros positivos *a* y *b* (con *a* < *b*) son **similares** si es posible obtener *b* a partir de mover algunos dígitos de atrás hacia adelante de *a*, sin cambiar el orden entre ellos.

> Ambos números deben tener la misma cantidad de dígitos, y ninguno puede empezar con el dígito 0.

**Ejemplo:** 12345 y 34512 son números similares, ya que 34512 se obtiene moviendo los últimos 3 dígitos de 12345 hacia adelante.

### N1

Implemente una función que reciba dos números enteros positivos *a* y *b*, y retorne si son similares.

Ejemplos de números similares: `(12, 21)`, `(756, 675)`, `(12345, 34512)`

### N2

Implemente una función que reciba dos números enteros positivos *A* y *B* (ambos con la misma cantidad de dígitos), y retorne la cantidad de parejas de números similares (*n*, *m*) que existen dentro del intervalo *A* ≤ *n* < *m* ≤ *B*.

**Ejemplos:**

| A | B | Parejas similares |
|---|---|---|
| 1 | 9 | 0 |
| 10 | 40 | 3 |
| 100 | 500 | 156 |
| 1111 | 2222 | 287 |

### N3

El archivo `entrada.txt` contiene 50 parejas de números *A* y *B* (una pareja por línea). En base a ese archivo, genere el archivo `salida.txt`, donde cada línea indique la cantidad de parejas de números similares encontradas para esa pareja.

**Formato esperado (`salida.txt`):**

```
Entrada 1: 20 parejas
Entrada 2: 0 parejas
...
Entrada 50: 145 parejas
```
