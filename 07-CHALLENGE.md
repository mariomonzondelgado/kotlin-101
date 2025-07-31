Aquí tienes una **mini práctica/mini reto** diseñada especialmente para reforzar los tres bloques que ya has visto: **Sintaxis básica, POO, y Lambdas con funciones de orden superior**.

---

## ✅ **Mini Reto Kotlin – "Gestor de Tareas"**

### 🧠 Objetivo:

Crear un pequeño sistema que permita gestionar una lista de tareas usando clases, objetos, lambdas y estructuras básicas de Kotlin.

---

### 🎯 Requisitos:

#### 1. **Modelo de datos con POO**

* Crea una clase `Tarea` con las siguientes propiedades:

  * `titulo: String`
  * `descripcion: String`
  * `completada: Boolean` (inicialmente `false`)

* Agrega una función `marcarComoCompletada()`.

#### 2. **Gestor de tareas**

* Crea una clase `GestorTareas` con:

  * Una lista mutable de tareas
  * Funciones:

    * `agregarTarea(tarea: Tarea)`
    * `mostrarTareas(filtro: (Tarea) -> Boolean)`
    * `aplicarAccionEnTodas(accion: (Tarea) -> Unit)`

#### 3. **Uso del sistema (main)**

En tu `fun main()`:

* Crea un `GestorTareas`
* Agrega 3 tareas
* Usa una lambda para mostrar solo las tareas pendientes
* Usa otra lambda para marcar todas como completadas
* Vuelve a mostrar todas las tareas usando `mostrarTareas { true }`

---

### 📌 Ejemplo esperado:

```kotlin
Tarea: Comprar pan - Pendiente
Tarea: Llamar al cliente - Pendiente
Tarea: Hacer ejercicio - Pendiente

--- Marcando todas como completadas ---

Tarea: Comprar pan - Completada
Tarea: Llamar al cliente - Completada
Tarea: Hacer ejercicio - Completada
```

---

### 🧩 Bonus (opcional):

* Usa `data class` para `Tarea`.
* Usa `when` o `if` como expresión para mostrar si está completada o no.
* Agrega una función de orden superior que reciba una operación y la aplique solo sobre las tareas no completadas.

---

## Solución Ejemplo

Aquí tienes una **solución ejemplo** para el reto “Gestor de Tareas” en Kotlin que incluye sintaxis básica, POO, funciones de orden superior y lambdas:

```kotlin
// Data class para representar una tarea
data class Tarea(
    val titulo: String,
    val descripcion: String,
    var completada: Boolean = false
) {
    fun marcarComoCompletada() {
        completada = true
    }
}

// Clase para gestionar tareas
class GestorTareas {
    private val tareas = mutableListOf<Tarea>()

    fun agregarTarea(tarea: Tarea) {
        tareas.add(tarea)
    }

    // Muestra tareas según un filtro recibido (lambda)
    fun mostrarTareas(filtro: (Tarea) -> Boolean) {
        tareas.filter(filtro).forEach { tarea ->
            val estado = if (tarea.completada) "Completada" else "Pendiente"
            println("Tarea: ${tarea.titulo} - $estado")
        }
    }

    // Aplica una acción recibida a todas las tareas
    fun aplicarAccionEnTodas(accion: (Tarea) -> Unit) {
        tareas.forEach(accion)
    }
}

fun main() {
    val gestor = GestorTareas()

    // Agregar tareas
    gestor.agregarTarea(Tarea("Comprar pan", "Comprar pan para el desayuno"))
    gestor.agregarTarea(Tarea("Llamar al cliente", "Confirmar la reunión"))
    gestor.agregarTarea(Tarea("Hacer ejercicio", "Correr 5 km"))

    println("Tareas pendientes:")
    gestor.mostrarTareas { !it.completada }

    println("\n--- Marcando todas como completadas ---\n")
    gestor.aplicarAccionEnTodas { it.marcarComoCompletada() }

    println("Todas las tareas:")
    gestor.mostrarTareas { true }
}
```
