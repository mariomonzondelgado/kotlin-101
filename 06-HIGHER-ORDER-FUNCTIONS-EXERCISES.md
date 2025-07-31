Aquí tienes 10 ejercicios para practicar **Funciones de Orden Superior y Lambdas en Kotlin**, ideales para profundizar en estos conceptos:

---

## 📝 Ejercicios: Funciones de Orden Superior y Lambdas en Kotlin

1. **Función que recibe otra función**
   Crea una función `ejecutarOperacion` que reciba dos números y una función que opere con ellos (por ejemplo suma o resta). Devuelve el resultado.

2. **Lambda con un parámetro implícito (`it`)**
   Usa una lista de enteros y filtra los números pares con `filter` y una lambda que use `it`.

3. **Función que devuelve una función**
   Crea una función `crearMultiplicador` que reciba un número `factor` y devuelva una función que multiplique su argumento por ese factor.

4. **Uso de `map` con lambda**
   Transforma una lista de strings a una lista con las longitudes de cada string usando `map`.

5. **Combina `filter` y `map`**
   Dada una lista de números, filtra los impares y luego mapea cada uno al cuadrado de su valor.

6. **Usar `forEach` con lambda**
   Imprime cada elemento de una lista de nombres usando `forEach` y una lambda.

7. **Usar `reduce` para sumar**
   Usa `reduce` para calcular la suma de todos los elementos en una lista de enteros.

8. **Función inline**
   Crea una función inline que reciba un bloque y lo ejecute 3 veces.

9. **Lambda como parámetro con retorno booleano**
   Crea una función `contarElementos` que reciba una lista y un predicado (función que devuelve boolean) y retorne cuántos elementos cumplen ese predicado.

10. **Extensión con función lambda**
    Crea una función de extensión para `String` llamada `repetirNVeces` que reciba un entero `n` y devuelva el string repetido `n` veces.

---

Claro, Mario, aquí tienes las **soluciones detalladas** para los 10 ejercicios sobre funciones de orden superior y lambdas en Kotlin:

---

## 📝 Soluciones Funciones de Orden Superior y Lambdas

---

### 1. Función que recibe otra función

```kotlin
fun ejecutarOperacion(a: Int, b: Int, operacion: (Int, Int) -> Int): Int {
    return operacion(a, b)
}

// Uso:
val suma = ejecutarOperacion(5, 3) { x, y -> x + y }
val resta = ejecutarOperacion(5, 3) { x, y -> x - y }
println(suma)  // 8
println(resta)  // 2
```

---

### 2. Lambda con parámetro implícito `it`

```kotlin
val numeros = listOf(1, 2, 3, 4, 5, 6)
val pares = numeros.filter { it % 2 == 0 }
println(pares)  // [2, 4, 6]
```

---

### 3. Función que devuelve una función

```kotlin
fun crearMultiplicador(factor: Int): (Int) -> Int {
    return { numero -> numero * factor }
}

val multiplicarPorTres = crearMultiplicador(3)
println(multiplicarPorTres(10))  // 30
```

---

### 4. Uso de `map` con lambda

```kotlin
val palabras = listOf("Kotlin", "Java", "Swift")
val longitudes = palabras.map { it.length }
println(longitudes)  // [6, 4, 5]
```

---

### 5. Combina `filter` y `map`

```kotlin
val numeros = listOf(1, 2, 3, 4, 5, 6)
val imparesAlCuadrado = numeros.filter { it % 2 != 0 }.map { it * it }
println(imparesAlCuadrado)  // [1, 9, 25]
```

---

### 6. Usar `forEach` con lambda

```kotlin
val nombres = listOf("Ana", "Luis", "Carlos")
nombres.forEach { println(it) }
```

---

### 7. Usar `reduce` para sumar

```kotlin
val numeros = listOf(1, 2, 3, 4, 5)
val suma = numeros.reduce { acc, num -> acc + num }
println(suma)  // 15
```

---

### 8. Función inline que ejecuta un bloque 3 veces

```kotlin
inline fun repetirTresVeces(bloque: () -> Unit) {
    repeat(3) {
        bloque()
    }
}

repetirTresVeces {
    println("Hola!")
}
```

---

### 9. Lambda con retorno booleano para contar elementos

```kotlin
fun <T> contarElementos(lista: List<T>, predicado: (T) -> Boolean): Int {
    return lista.count(predicado)
}

val numeros = listOf(1, 2, 3, 4, 5, 6)
val cantidadPares = contarElementos(numeros) { it % 2 == 0 }
println(cantidadPares)  // 3
```

---

### 10. Extensión para repetir string N veces

```kotlin
fun String.repetirNVeces(n: Int): String {
    return this.repeat(n)
}

println("Hola ".repetirNVeces(3))  // Hola Hola Hola 
```

---
