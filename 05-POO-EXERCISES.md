Aquí tienes **10 ejercicios para practicar Programación Orientada a Objetos (POO) en Kotlin**. Son progresivos y cubren clases, herencia, interfaces, abstracción, y más:

---

## 📝 Ejercicios de POO en Kotlin

1. **Crear una clase simple**
   Crea una clase `Libro` con propiedades `titulo` y `autor`. Instancia un objeto y muestra sus propiedades.

2. **Constructor secundario**
   Añade un constructor secundario a la clase `Libro` que solo reciba el título y ponga el autor como "Desconocido".

3. **Métodos en clase**
   Añade un método `descripcion()` a `Libro` que devuelva una cadena con título y autor.

4. **Herencia básica**
   Crea una clase base `Vehiculo` con una función `arrancar()`. Luego crea una clase `Coche` que herede de `Vehiculo` y sobrescriba `arrancar()` con un mensaje específico.

5. **Clases abstractas**
   Define una clase abstracta `Empleado` con una función abstracta `calcularSalario()`. Crea una subclase `EmpleadoTiempoCompleto` que implemente esa función.

6. **Interfaces**
   Crea una interfaz `Volador` con un método `volar()`. Implementa esta interfaz en una clase `Avion` que imprima un mensaje al volar.

7. **Propiedades con getter y setter personalizados**
   En una clase `CuentaBancaria` crea una propiedad `saldo` con un setter que no permita valores negativos.

8. **Clases de datos (data class)**
   Crea una `data class` llamada `Punto` con propiedades `x` e `y`. Crea dos instancias y comprueba si son iguales.

9. **Clase sellada (sealed class)**
   Crea una clase sellada `ResultadoOperacion` con subclases `Exito` y `Fallo`. Usa un `when` para manejar ambos casos.

10. **Objeto singleton**
    Define un objeto singleton `Configuracion` que almacene una propiedad `idioma` y un método para cambiarlo.

---



Aquí tienes las **soluciones para los 10 ejercicios de POO en Kotlin**, explicadas y con código funcional:

---

## 📝 Soluciones Ejercicios POO Kotlin

---

### 1. Crear una clase simple

```kotlin
class Libro(val titulo: String, val autor: String)

val libro = Libro("El Quijote", "Miguel de Cervantes")
println("Título: ${libro.titulo}, Autor: ${libro.autor}")
```

---

### 2. Constructor secundario

```kotlin
class Libro(val titulo: String, val autor: String) {
    constructor(titulo: String) : this(titulo, "Desconocido")
}

val libro1 = Libro("El Quijote")
val libro2 = Libro("1984", "George Orwell")
println("${libro1.titulo} - ${libro1.autor}")  // El Quijote - Desconocido
println("${libro2.titulo} - ${libro2.autor}")  // 1984 - George Orwell
```

---

### 3. Métodos en clase

```kotlin
class Libro(val titulo: String, val autor: String) {
    fun descripcion(): String {
        return "$titulo, escrito por $autor"
    }
}

val libro = Libro("El Quijote", "Miguel de Cervantes")
println(libro.descripcion())
```

---

### 4. Herencia básica

```kotlin
open class Vehiculo {
    open fun arrancar() {
        println("El vehículo está arrancando")
    }
}

class Coche : Vehiculo() {
    override fun arrancar() {
        println("El coche está arrancando")
    }
}

val miCoche = Coche()
miCoche.arrancar()
```

---

### 5. Clases abstractas

```kotlin
abstract class Empleado {
    abstract fun calcularSalario(): Double
}

class EmpleadoTiempoCompleto(val salarioBase: Double) : Empleado() {
    override fun calcularSalario(): Double {
        return salarioBase
    }
}

val empleado = EmpleadoTiempoCompleto(2000.0)
println("Salario: ${empleado.calcularSalario()}")
```

---

### 6. Interfaces

```kotlin
interface Volador {
    fun volar()
}

class Avion : Volador {
    override fun volar() {
        println("El avión está volando")
    }
}

val avion = Avion()
avion.volar()
```

---

### 7. Getter y setter personalizados

```kotlin
class CuentaBancaria {
    var saldo: Double = 0.0
        set(value) {
            if (value >= 0) field = value
            else println("El saldo no puede ser negativo")
        }
}

val cuenta = CuentaBancaria()
cuenta.saldo = 100.0
println(cuenta.saldo)  // 100.0
cuenta.saldo = -50.0   // El saldo no puede ser negativo
println(cuenta.saldo)  // 100.0
```

---

### 8. Data class

```kotlin
data class Punto(val x: Int, val y: Int)

val p1 = Punto(1, 2)
val p2 = Punto(1, 2)
val p3 = Punto(3, 4)

println(p1 == p2)  // true
println(p1 == p3)  // false
```

---

### 9. Clase sellada (sealed class)

```kotlin
sealed class ResultadoOperacion

class Exito(val mensaje: String) : ResultadoOperacion()
class Fallo(val error: String) : ResultadoOperacion()

fun manejarResultado(resultado: ResultadoOperacion) {
    when (resultado) {
        is Exito -> println("Éxito: ${resultado.mensaje}")
        is Fallo -> println("Fallo: ${resultado.error}")
    }
}

val res1 = Exito("Operación completada")
val res2 = Fallo("Error inesperado")

manejarResultado(res1)
manejarResultado(res2)
```

---

### 10. Objeto singleton

```kotlin
object Configuracion {
    var idioma: String = "es"

    fun cambiarIdioma(nuevoIdioma: String) {
        idioma = nuevoIdioma
        println("Idioma cambiado a $idioma")
    }
}

Configuracion.cambiarIdioma("en")
println(Configuracion.idioma)
```

---
