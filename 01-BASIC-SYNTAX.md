## 🧾 **KOTLIN CHEATSHEET – Sintaxis Básica**

---

### 🔹 VARIABLES

```kotlin
val nombre = "Mario"      // Inmutable (como final en Java)
var edad = 30             // Mutable

// Con tipo explícito
val ciudad: String = "Madrid"
var altura: Double = 1.75
```

---

### 🔹 TIPOS DE DATOS

| Tipo      | Descripción       | Ejemplo          |
| --------- | ----------------- | ---------------- |
| `Int`     | Entero            | `val x = 42`     |
| `Double`  | Decimal (64 bits) | `val pi = 3.14`  |
| `Float`   | Decimal (32 bits) | `val f = 2.5f`   |
| `Long`    | Entero largo      | `val l = 100L`   |
| `Boolean` | Verdadero/falso   | `val ok = true`  |
| `Char`    | Carácter          | `val c = 'A'`    |
| `String`  | Cadena de texto   | `val s = "Hola"` |

---

### 🔹 FUNCIONES

```kotlin
// Función normal
fun saludar(nombre: String): String {
    return "Hola, $nombre"
}

// Función simplificada (expresión única)
fun cuadrado(n: Int) = n * n

// Función sin retorno (Unit)
fun imprimirMensaje(mensaje: String): Unit {
    println(mensaje)
}
```

---

### 🔹 CONDICIONES

```kotlin
val edad = 20

// If tradicional
if (edad >= 18) {
    println("Mayor de edad")
} else {
    println("Menor de edad")
}

// If como expresión
val resultado = if (edad >= 18) "Mayor" else "Menor"

// When (como switch en otros lenguajes)
val nota = 8
val calificacion = when (nota) {
    10 -> "Matrícula"
    in 9..9 -> "Sobresaliente"
    in 7..8 -> "Notable"
    in 5..6 -> "Aprobado"
    else -> "Suspenso"
}
```

---

### 🔹 BUCLES

```kotlin
// For (recorriendo una lista)
val lista = listOf("a", "b", "c")
for (letra in lista) {
    println(letra)
}

// For con rangos
for (i in 1..5) {
    println(i) // 1 2 3 4 5
}

for (i in 10 downTo 1 step 2) {
    println(i) // 10 8 6 4 2
}

// While
var contador = 0
while (contador < 5) {
    println(contador)
    contador++
}

// Do-while
do {
    println("Ejecuta al menos una vez")
} while (false)
```

---

### 🔹 EXTRA: STRINGS Y PLANTILLAS

```kotlin
val nombre = "Mario"
val edad = 30
val mensaje = "Hola, me llamo $nombre y tengo $edad años"
```

