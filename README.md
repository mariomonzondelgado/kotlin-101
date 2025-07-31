# kotlin-101

Aquí tienes una **lista estructurada de conceptos de Kotlin** que debes dominar para pasar de un perfil **Junior a Senior** como desarrollador de aplicaciones Android nativas usando **Kotlin y Jetpack Compose**. La he dividido en 3 niveles para que te sirva como guía progresiva:

---

### 🟢 **Nivel 1 – Fundamentos Sólidos (ya deberías tenerlos claros como Junior)**

1. **Sintaxis básica de Kotlin**
   Variables (`val`, `var`), tipos, funciones, condiciones, bucles.

2. **Programación orientada a objetos**
   Clases, objetos, herencia, interfaces, modificadores (`open`, `abstract`, `sealed`).

3. **Funciones de orden superior y lambdas**
   Uso de funciones como parámetros, expresiones lambda, `it`, etc.

4. **Colecciones**
   Listas, mapas, sets y sus operaciones (`map`, `filter`, `reduce`, etc.).

5. **Null safety**
   Operadores `?`, `?:`, `!!`, `let`, `also`, `apply`, `run`, `with`.

6. **Corutinas (nivel básico)**
   Lanzamiento de corutinas (`GlobalScope`, `lifecycleScope`), `suspend`.

---

### 🟡 **Nivel 2 – Intermedio (puente hacia perfil Semi-Senior)**

7. **Funciones inline, crossinline y noinline**
   Optimización y control del comportamiento de funciones de orden superior.

8. **Delegación y `by` keyword**
   Uso de propiedades delegadas (`lazy`, `observable`, `vetoable`, etc.).

9. **Extensiones de funciones y propiedades**
   Modularidad y reutilización de código.

10. **Scope functions a profundidad**
    Diferencias sutiles entre `let`, `apply`, `run`, `with`, `also`.

11. **Tipos genéricos y reificación (`reified`)**
    Programación genérica, constraints y uso con funciones inline.

12. **Corutinas avanzadas**
    `Job`, `Deferred`, `Dispatchers`, `withContext`, manejo de excepciones en `Flow`.

13. **Kotlin Flow**
    Operadores (`map`, `flatMap`, `catch`, `collect`, `onEach`), cold vs hot flows.

14. **Typealias y sealed classes**
    Para representar jerarquías controladas y mejorar legibilidad.

---

### 🔴 **Nivel 3 – Avanzado (perfil Senior)**

15. **Domain Specific Languages (DSLs) en Kotlin**
    Creación de mini-lenguajes internos (`@DslMarker`, builders).

16. **Annotations y metaprogramación básica**
    Uso de `@Target`, `@Retention`, `@Repeatable`, y creación de anotaciones personalizadas.

17. **Reflection (`kClass`, `KProperty`, `KFunction`)**
    Inspección y modificación de clases en tiempo de ejecución.

18. **Multi-platform Kotlin (KMP)**
    Compartición de lógica entre Android, iOS, y otras plataformas.

19. **Interop con Java**
    Uso de `@JvmName`, `@JvmStatic`, `@JvmOverloads`, `@Throws`.

20. **Performance y análisis de bytecode**
    Uso de herramientas como `kotlinx.benchmark`, `javap`, análisis del compilador.

21. **Code Style, Clean Code y Testing en Kotlin**
    Naming, extensiones reutilizables, pruebas con `MockK`, `Kotest`, `Turbine`.

22. **Estrategias de inmutabilidad y diseño funcional**
    Programación funcional con `Result`, `Either`, `fold`, composición de funciones puras.

---

### 🧠 Consejo adicional:

Para consolidar tu nivel senior, no basta con saber Kotlin. Debes **aplicarlo bien dentro de un stack moderno Android**, combinándolo con:

* **Arquitecturas limpias** (Clean Architecture, MVI, MVVM).
* **DI con Hilt o Koin**.
* **Jetpack Compose con patrones declarativos bien aplicados**.
* **Dominio de testing (Unit, UI, integración).**

---

¿Quieres que prepare una hoja de ruta completa con recursos y ejercicios para dominar estos puntos?
