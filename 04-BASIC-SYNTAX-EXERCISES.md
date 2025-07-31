Aquí tienes **10 ejercicios prácticos para reforzar la sintaxis básica de Kotlin** (variables, tipos, funciones, condiciones y bucles):

---

## 📝 Ejercicios Sintaxis Básica Kotlin

1. **Variables y tipos**
   Declara una variable inmutable `nombre` de tipo `String` con tu nombre, y una variable mutable `edad` de tipo `Int` con tu edad. Luego, imprime un mensaje que combine ambas.

2. **Funciones básicas**
   Crea una función llamada `saludar` que reciba un parámetro `nombre` y retorne un saludo en formato `"Hola, [nombre]!"`. Llama a la función con tu nombre y muestra el resultado.

3. **Condicional if-else**
   Escribe una función `esMayorDeEdad` que reciba un entero `edad` y retorne `"Mayor de edad"` si es 18 o más, o `"Menor de edad"` si es menor.

4. **Expresión if como valor**
   Declara una variable `mensaje` que guarde el resultado de un `if` expresado como valor, que evalúe si un número dado es positivo, negativo o cero, y devuelva un mensaje descriptivo.

5. **When básico**
   Crea una función `clasificarDia` que reciba un entero del 1 al 7 y retorne el nombre del día de la semana usando `when`. Si el número está fuera del rango, retorna `"Día inválido"`.

6. **Bucle for con rango**
   Escribe un bucle `for` que imprima los números del 10 al 1 en orden descendente usando `downTo`.

7. **Bucle for con colección**
   Crea una lista de cinco frutas y usa un `for` para imprimir cada fruta en mayúsculas.

8. **While básico**
   Usa un `while` para imprimir los números pares del 2 al 20.

9. **Función con parámetros y retorno**
   Crea una función `multiplicar` que reciba dos números `Int` y retorne su producto. Luego, llama a la función y muestra el resultado.

10. **String templates**
    Declara variables `producto` y `precio`, luego imprime un mensaje usando templates de cadena que diga, por ejemplo, `"El producto [producto] cuesta [precio] euros."`.

---




## 📝 Soluciones Ejercicios Sintaxis Básica Kotlin

---

### 1. Variables y tipos

```kotlin
val nombre: String = "Mario"
var edad: Int = 30

println("Hola, mi nombre es $nombre y tengo $edad años")
```

---

### 2. Funciones básicas

```kotlin
fun saludar(nombre: String): String {
    return "Hola, $nombre!"
}

println(saludar("Mario"))
```

---

### 3. Condicional if-else

```kotlin
fun esMayorDeEdad(edad: Int): String {
    return if (edad >= 18) "Mayor de edad" else "Menor de edad"
}

println(esMayorDeEdad(20))  // Mayor de edad
println(esMayorDeEdad(15))  // Menor de edad
```

---

### 4. Expresión if como valor

```kotlin
val numero = -5
val mensaje = if (numero > 0) "Positivo" else if (numero < 0) "Negativo" else "Cero"

println(mensaje)  // Negativo
```

---

### 5. When básico

```kotlin
fun clasificarDia(dia: Int): String {
    return when(dia) {
        1 -> "Lunes"
        2 -> "Martes"
        3 -> "Miércoles"
        4 -> "Jueves"
        5 -> "Viernes"
        6 -> "Sábado"
        7 -> "Domingo"
        else -> "Día inválido"
    }
}

println(clasificarDia(3))  // Miércoles
println(clasificarDia(9))  // Día inválido
```

---

### 6. Bucle for con rango

```kotlin
for (i in 10 downTo 1) {
    println(i)
}
```

---

### 7. Bucle for con colección

```kotlin
val frutas = listOf("manzana", "plátano", "pera", "naranja", "uva")

for (fruta in frutas) {
    println(fruta.uppercase())
}
```

---

### 8. While básico

```kotlin
var num = 2
while (num <= 20) {
    println(num)
    num += 2
}
```

---

### 9. Función con parámetros y retorno

```kotlin
fun multiplicar(a: Int, b: Int): Int {
    return a * b
}

println(multiplicar(5, 7))  // 35
```

---

### 10. String templates

```kotlin
val producto = "Camiseta"
val precio = 19.99

println("El producto $producto cuesta $precio euros.")
```


