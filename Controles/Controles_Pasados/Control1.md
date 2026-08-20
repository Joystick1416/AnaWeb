# Control 1

*Algoritmia — programación dinámica y teoría de números*

## Ejercicio 1 — *(2.5 pts.)*

Suponga que se encuentra subiendo las escaleras dentro de uno de los edificios de la universidad, y que para llegar al último piso debe subir *N* escalones. Puede subir escalón por escalón (de 1 en 1), o avanzar de 2 en 2 escalones. ¿De cuántas maneras distintas podrá llegar al último piso?

Implemente una función que reciba como entrada una lista *L*, representando a *M* edificios dentro de una universidad (cada edificio tiene *N* escalones). Su función debe retornar una lista *O*, conteniendo *M* números naturales que representan la cantidad de maneras distintas que tiene un alumno para llegar a la cima de cada uno de los edificios en *L*.

**Ejemplos:**
- Si un edificio solo cuenta con *N* = 1 escalón, entonces solo tiene una manera de llegar a la cima.
- Si un edificio cuenta con *N* = 2 escalones, entonces tendrá 2 maneras de llegar a la cima (ir de 1 en 1, o subir directamente los 2 escalones).

**Importante:**
- El número de edificios en una universidad: 1 ≤ *M* ≤ 10
- El número de escalones de un edificio: 0 ≤ *N* ≤ 10³

## Ejercicio 2 — *(2.5 pts.)*

Implemente una función que reciba como entrada un número natural *N*, y retorne la cantidad de números primos menores que *N*. Recuerde que los números primos son aquellos que solamente son divisibles entre 1 y el mismo número.

**Ejemplos:**
- Sea *N* = 10, su función deberá retornar **4**, dado que existen 4 números primos menores que 10: 2, 3, 5, 7.
- Sea *N* = 0, su función deberá retornar **0**, dado que no existen números primos menores que 0.

**Importante:**
- 0 ≤ *N* ≤ 10⁷
- Para cualquier valor de *N*, su función deberá retornar la respuesta en un tiempo no mayor a 10 segundos; de lo contrario, obtendrá solamente 1 punto.
