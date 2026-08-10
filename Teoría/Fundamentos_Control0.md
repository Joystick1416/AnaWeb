# Fundamentos básicos — Control 0

Repaso de los conceptos de programación necesarios antes de resolver el Control 0 (números similares). Cada sección tiene teoría paso a paso + un ejemplo breve (input → output).

---

## 1. Manipulación de dígitos como string

### Idea
Cuando un problema habla de "mover dígitos", "rotar dígitos" o "invertir dígitos", casi nunca conviene resolverlo con aritmética (`%`, `//`). Es mucho más simple convertir el número a texto y usar las herramientas de manejo de strings.

### Paso a paso
1. Convertir el número a string: `s = str(numero)`.
2. Ahora `s` es indexable: `s[0]` es el primer dígito, `s[-1]` el último.
3. Slicing `s[i:j]` extrae una porción del string sin necesidad de loops.
4. Concatenar partes con `+` arma el nuevo número como string.
5. Si necesitas el resultado como entero de nuevo: `int(nuevo_s)`.

### Ejemplo
**Input:** `numero = 12345`, mover los últimos 3 dígitos al frente.

```python
s = str(12345)      # "12345"
resultado = s[-3:] + s[:-3]   # "345" + "12"
```

**Output:** `"34512"`

---

## 2. El truco de "rotación de strings"

### Idea
Para el Control 0 necesitas saber si `b` se puede obtener rotando los dígitos de `a`. En vez de probar manualmente cada posible rotación con un loop, existe un truco clásico de algoritmia:

> `b` es una rotación de `a` **si y solo si**:
> 1. `a` y `b` tienen la misma longitud, **y**
> 2. `b` es substring de `a + a` (a concatenado consigo mismo).

### Por qué funciona
Al duplicar `a` (`a+a`), quedan "escritas" en ese string **todas** las rotaciones posibles de `a`, una detrás de otra. Si `b` aparece ahí dentro, es porque coincide con alguna de esas rotaciones.

### Paso a paso
1. Convertir ambos números a string: `sa = str(a)`, `sb = str(b)`.
2. Verificar que tengan la misma longitud (`len(sa) == len(sb)`); si no, no pueden ser similares.
3. Construir `doble = sa + sa`.
4. Verificar si `sb in doble`.
5. Si es `True`, son similares.

### Ejemplo
**Input:** `a = 12345`, `b = 34512`

```python
sa, sb = "12345", "34512"
len(sa) == len(sb)        # True
doble = sa + sa           # "1234512345"
sb in doble                # "34512" está en "1234512345" -> True
```

**Output:** `True` (son números similares)

---

## 3. Fuerza bruta vs. agrupar por clase de equivalencia

### Idea
No es lo mismo **comparar** dos números (N1) que **contar cuántos pares similares hay** dentro de un rango grande (N2). Comparar cada número contra todos los demás es fuerza bruta y se vuelve lento cuando el rango crece.

La alternativa: en vez de comparar pares, agrupa los números según una "forma canónica" que sea igual para todas sus rotaciones (por ejemplo, la rotación que queda más pequeña alfabéticamente). Todos los números de un mismo grupo son similares entre sí por definición, así que no hace falta compararlos uno por uno.

### Paso a paso
1. Para cada número del rango, calcular todas sus rotaciones posibles.
2. Elegir la rotación mínima (la "menor" como string) como el identificador del grupo.
3. Agrupar los números por ese identificador (por ejemplo, en un diccionario `{identificador: cantidad}`).
4. Por cada grupo con `k` números, la cantidad de pares similares que aporta es la combinación `C(k, 2) = k*(k-1)/2` (elegir 2 de esos k, sin importar el orden).
5. Sumar los aportes de todos los grupos = respuesta total.

### Ejemplo
**Input:** rango `[121, 211, 112, 999]`

```python
# rotaciones mínimas:
# 121 -> min("121","211","112") = "112"
# 211 -> min("211","112","121") = "112"
# 112 -> min("112","121","211") = "112"
# 999 -> min("999") = "999"

grupos = {"112": 3, "999": 1}
# grupo "112" tiene k=3 -> C(3,2) = 3 pares
# grupo "999" tiene k=1 -> C(1,2) = 0 pares
```

**Output:** `3` pares similares en total (en vez de comparar 4×4 casos con fuerza bruta)

---

## 4. Complejidad temporal (por qué importa)

### Idea
La complejidad temporal mide cómo crece el tiempo de ejecución a medida que crece el tamaño del input. No basta con que un algoritmo dé la respuesta correcta: si tarda demasiado con inputs grandes, no sirve.

### Paso a paso para evaluar si tu solución alcanza
1. Identifica el tamaño del input (por ejemplo, el ancho del rango `B - A`).
2. Estima cuántas operaciones hace tu algoritmo en el peor caso.
   - Comparar cada número contra todos los demás → aproximadamente `n²` operaciones.
   - Agrupar por clase de equivalencia (sección 3) → aproximadamente `n` operaciones (una pasada).
3. Si `n` puede ser grande (miles o millones), un algoritmo `n²` puede tardar demasiado, mientras uno `n` sigue siendo rápido.
4. Regla práctica: si el enunciado corre muchos casos de prueba (como los 50 pares de N3) o menciona límites de tiempo, sospecha que la fuerza bruta no alcanza.

### Ejemplo
**Input:** rango con `n = 10 000` números

```text
Fuerza bruta (comparar todo par):      ~10 000² = 100 000 000 operaciones
Agrupar por clase de equivalencia:     ~10 000 operaciones
```

**Output:** la segunda solución es ~10 000 veces más rápida para el mismo resultado.

---

## 5. Manejo de archivos (lectura y escritura)

### Idea
N3 pide leer pares de números desde `entrada.txt` (uno por línea) y escribir los resultados en `salida.txt` con un formato específico. En Python esto se hace con el manejador de contexto `with open(...)`.

### Paso a paso
1. Abrir el archivo de entrada en modo lectura: `with open("entrada.txt") as f:`.
2. Leer todas las líneas: `lineas = f.readlines()` (o iterar línea por línea con `for linea in f:`).
3. Por cada línea, quitar espacios/saltos de línea (`linea.strip()`) y separar los dos números (`linea.split()`), convirtiéndolos a `int`.
4. Procesar cada par con tu función (por ejemplo, la de la sección 3).
5. Abrir el archivo de salida en modo escritura: `with open("salida.txt", "w") as f:`.
6. Escribir una línea por resultado, respetando el formato exacto pedido (`f.write(f"Entrada {i}: {resultado} parejas\n")`).

### Ejemplo
**Input** (`entrada.txt`):
```
10 40
100 500
```

```python
with open("entrada.txt") as f:
    pares = [tuple(map(int, linea.split())) for linea in f]
# pares = [(10, 40), (100, 500)]

with open("salida.txt", "w") as f:
    for i, (a, b) in enumerate(pares, start=1):
        resultado = contar_pares_similares(a, b)  # función de la sección 3
        f.write(f"Entrada {i}: {resultado} parejas\n")
```

**Output** (`salida.txt`):
```
Entrada 1: 3 parejas
Entrada 2: 156 parejas
```

---

## Resumen rápido

| Concepto | Para qué sirve en Control 0 |
|---|---|
| Dígitos como string | Base para representar y rotar números |
| Truco de rotación (`b in a+a`) | Resolver N1 (comparar 2 números) |
| Agrupar por clase de equivalencia + combinatoria | Resolver N2 de forma eficiente (contar pares) |
| Complejidad temporal | Saber si tu solución de N2 va a ser lo bastante rápida |
| Manejo de archivos | Resolver N3 (entrada.txt → salida.txt) |
