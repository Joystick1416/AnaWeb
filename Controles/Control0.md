Números similares
𝑎 𝑏
 y

Dos números enteros positivos

 son similares si:

𝑎 < 𝑏

Podemos obtener

𝑏

 a partir de mover algunos dígitos de atrás hacia adelante de

𝑎
 (sin cambiar el orden).

Por ejemplo, 12345 y 34512 son números similares dado que podemos obtener 34512 moviendo los últimos 3 dígitos de atrás hacia adelante de
0
.
12345. Es importante notar que los números

 tienen la misma cantidad de dígios. Además, ninguno de los números empezará con dígitos

𝑎 𝑏
 y

N1

Implementar una función que tenga como entrada dos números enteros positivos

𝑎 𝑏
 y

, luego retorne si son similares.

Ejemplos de números similares:

(12, 21), (756, 675), (12345, 34512)

N2

Implementar una función que tenga como entrada dos números enteros positivos
cantidad de parejas de números similares

 que existen dentro de

(𝑛, 𝑚)

 y

𝐴 𝐵
 y
𝐴 𝐵 (𝐴 ≤ 𝑛 < 𝑚 ≤ 𝐵)

.

 ambos con la misma cantidad de dígitos, luego retorne la

Por ejempo:

Sea A = 1 y B = 9, la cantidad de parejas de números similares dentro de ese intervalo es 0.
Sea A = 10 y B = 40, la cantidad de parejas de números similares dentro de ese intervalo es 3.
Sea A = 100 y B = 500, la cantidad de parejas de números similares dentro de ese intervalo es 156
Sea A = 1111 y B = 2222, la cantidad de parejas de números similares dentro de ese intervalo es 287.

N3

El archivo entrada.txt contiene 50 parejas de números:
cada línea indique la cantidad de parejas de números similares, su archivo debe tener el formato:

𝐴 𝐵
 y

 (una pareja en cada línea), en base a ese archivo genere el archivo salida.txt donde

Entrada 1: 20 parejas

Entrada 2: 0 parejas

...

Entrada 50: 145 parejas

