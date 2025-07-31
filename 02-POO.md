## 🧾 **KOTLIN CHEATSHEET – Programación Orientada a Objetos**

---

### 🔹 CLASES Y OBJETOS

```kotlin
// Clase con constructor primario
class Persona(val nombre: String, var edad: Int) {
    fun saludar() {
        println("Hola, soy $nombre y tengo $edad años")
    }
}

// Crear objeto
val persona = Persona("Mario", 30)
persona.saludar()
```

---

### 🔹 CONSTRUCTOR SECUNDARIO

```kotlin
class Coche(val marca: String) {
    var modelo: String = ""

    constructor(marca: String, modelo: String) : this(marca) {
        this.modelo = modelo
    }
}
```

---

### 🔹 HERENCIA

```kotlin
// La clase base debe ser abierta (open)
open class Animal(val nombre: String) {
    open fun hacerSonido() {
        println("$nombre hace un sonido")
    }
}

class Perro(nombre: String) : Animal(nombre) {
    override fun hacerSonido() {
        println("$nombre dice: Guau!")
    }
}

val perro = Perro("Firulais")
perro.hacerSonido()
```

---

### 🔹 INTERFACES

```kotlin
interface Volador {
    fun volar()
}

class Pajaro : Volador {
    override fun volar() {
        println("El pájaro está volando")
    }
}
```

> ✅ **Nota**: Las interfaces pueden tener implementaciones por defecto en Kotlin.

```kotlin
interface Nadador {
    fun nadar() {
        println("Nadando...")
    }
}
```

---

### 🔹 MODIFICADORES DE CLASES

| Modificador | Descripción                                                                                            |
| ----------- | ------------------------------------------------------------------------------------------------------ |
| `open`      | Permite que la clase o método pueda ser heredado o sobrescrito.                                        |
| `final`     | Por defecto en Kotlin. No se puede sobrescribir (equivalente a no usar `open`).                        |
| `abstract`  | No se puede instanciar. Puede tener funciones sin implementar.                                         |
| `sealed`    | Clase sellada. Solo puede ser heredada por clases definidas en el mismo archivo.                       |
| `data`      | Clase de datos. Se usa para contener información (`toString`, `equals`, `hashCode`, etc. automáticos). |
| `object`    | Singleton. Crea una única instancia automáticamente.                                                   |

---

### 🔹 CLASE ABSTRACTA

```kotlin
abstract class Figura {
    abstract fun calcularArea(): Double
}

class Circulo(val radio: Double) : Figura() {
    override fun calcularArea(): Double = Math.PI * radio * radio
}
```

---

### 🔹 CLASE SELLADA (`sealed`)

```kotlin
sealed class Resultado

class Exito(val datos: String) : Resultado()
class Error(val mensaje: String) : Resultado()

fun manejar(resultado: Resultado) = when (resultado) {
    is Exito -> println("Datos: ${resultado.datos}")
    is Error -> println("Error: ${resultado.mensaje}")
}
```

---

### 🔹 OBJETOS Y SINGLETONS

```kotlin
object Logger {
    fun log(mensaje: String) {
        println("LOG: $mensaje")
    }
}

Logger.log("Aplicación iniciada")
```

---

### 🔹 CLASE DE DATOS (`data class`)

```kotlin
data class Usuario(val nombre: String, val edad: Int)

val user = Usuario("Mario", 30)
println(user) // Usuario(nombre=Mario, edad=30)
```

