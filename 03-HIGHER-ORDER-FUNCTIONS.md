## 🧾 **KOTLIN CHEATSHEET – Funciones de Orden Superior y Lambdas**

---

### 🔹 ¿QUÉ ES UNA FUNCIÓN DE ORDEN SUPERIOR?

Una **función de orden superior** es una que:

* **Recibe una función como parámetro**, o
* **Devuelve una función como resultado**

```kotlin
fun operar(a: Int, b: Int, operacion: (Int, Int) -> Int): Int {
    return operacion(a, b)
}

// Uso:
val suma = operar(2, 3) { x, y -> x + y }
println(suma) // 5
```

---

### 🔹 LAMBDAS BÁSICAS

```kotlin
val saludar: () -> Unit = { println("Hola") }
val cuadrado: (Int) -> Int = { it * it }

saludar()
println(cuadrado(4)) // 16
```

> ✅ `it` es el **nombre implícito** del único parámetro si no se nombra.

---

### 🔹 LAMBDAS CON PARÁMETROS NOMBRADOS

```kotlin
val sumar = { x: Int, y: Int -> x + y }
println(sumar(3, 4)) // 7
```

---

### 🔹 FUNCIONES COMO PARÁMETROS

```kotlin
fun aplicarOperacion(x: Int, y: Int, op: (Int, Int) -> Int): Int {
    return op(x, y)
}

val resultado = aplicarOperacion(10, 5) { a, b -> a - b }
println(resultado) // 5
```

---

### 🔹 FUNCIONES QUE DEVUELVEN FUNCIONES

```kotlin
fun multiplicador(factor: Int): (Int) -> Int {
    return { x -> x * factor }
}

val porDos = multiplicador(2)
println(porDos(6)) // 12
```

---

### 🔹 TIPOS FUNCIONALES

```kotlin
val f1: () -> Unit                 // Sin parámetros, sin retorno
val f2: (Int) -> Int              // Un Int, retorna Int
val f3: (Int, Int) -> Boolean     // Dos Int, retorna Boolean
```

---

### 🔹 FUNCIONES INLINE

```kotlin
inline fun medirTiempo(bloque: () -> Unit) {
    val inicio = System.currentTimeMillis()
    bloque()
    val fin = System.currentTimeMillis()
    println("Tiempo: ${fin - inicio} ms")
}

// Uso:
medirTiempo {
    Thread.sleep(500)
}
```

---

### 🔹 FUNCIONES DE EXTENSIÓN CON LAMBDAS

```kotlin
fun String.procesar(transform: (String) -> String): String {
    return transform(this)
}

val resultado = "Mario".procesar { it.uppercase() }
println(resultado) // MARIO
```

---

### 🔹 FUNCIONES DE COLECCIONES CON LAMBDAS

```kotlin
val lista = listOf(1, 2, 3, 4, 5)

val pares = lista.filter { it % 2 == 0 }       // [2, 4]
val cuadrados = lista.map { it * it }          // [1, 4, 9, 16, 25]
val suma = lista.reduce { acc, i -> acc + i }  // 15
```

---

### 🧠 PUNTOS CLAVE

✅ Usa `it` cuando haya solo un parámetro.
✅ Usa `::nombreFuncion` para pasar funciones existentes como referencia.
✅ Las lambdas pueden ser expresiones o bloques.
✅ Kotlin favorece la **programación funcional** en muchos aspectos del SDK (por ejemplo, `LiveData.observe`, `setOnClickListener { }`, etc.).