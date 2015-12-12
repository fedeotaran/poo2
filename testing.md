Testing
=======

TDD (testing development driven)
--------------------------------

* Combina test first development: escribir el test antes del código que va a pasar el test.
* Refactoring

### Objetivo

* Pensar en el diseño y que se espera de cada requerimiento antes de escribir el código
* Escribir código limpio que funcione (como técnica de programación)

### ¿Por qué no dejar testing para el final?

* Para conocer cual es el final, de que otra manera podemos saber cuando terminamos.
* Para mantener bajo control un proyecto con restricciones de tiempo ajustadas.
* Para refactorizar rápido.

### Filosofía de TDD

* Vuelco completo al desarrollo de software tradicional. Se escriben los test y después el código.
* Se escriben test funcionales para capturar use cases que se validan automáticamente.
* Se escriben test de unidad para enfocarse en pequeñas partes a la vez y aislar los errores.
* No agregar funcionalidad hasta que no haya un test que no pasa porque esa funcionalidad no existe.
* Una vez escrito el test, se codifica lo necesario para que el todo el test suite pase.
* Pequeños pasos: un test, un poco de código.
* Una vez que los test pasan se refactoriza para asegurar que se mantenga una buena calidad en el código.

### Algunas reglas de TDD

* Diseñar incrementalmente: teniendo código que funciona como feedback para ayudar en las decisiones entre iteraciones.
* Los programadores escriben sus propios test: no es efectivo tener que esperar a otro que los escriba por ellos.
* El diseño debe consistir de componentes altamente cohesivos y desacoplados entre si: facilita el testing y mejora la evolución y mantenimiento del sistema.

Tipos de test
-------------

* Test de unidad
* Test funcional (de aceptación)
* Test de integración
* Test de regresión

Test Unit (xunit)
-----------------

* Testeo de la mínima unidad de ejecución. En POO La mínima unidad es un método.
* Objetivo: aislar cada parte de un programa y mostrar que funciona correctamente.
* Escritos desde la perspectiva de un programador.
* Cada test confirma que un método produce el output esperado ante un input conocido.
* Es como un contrato escrito de lo que esa unidad tiene que satisfacer.

### Pros y contras

[+] Facilita cambios
[+] Simplifica la integración
[+] Documenta cada unidad

[-] No encuentra todos los errores.
[-] Puede no encontrar la ausencia de errores.
[-] Puede no encontrar problemas de integración o de performance.

### Partes de un test de unidad

**Fase 1: Fixture setup**
Preparar todo lo necesario para testear el comportamiento del SUT.
**Fase 2: Excersice**
Interactuar con el SUT para ejercitar el comportamiento que se intenta verificar.
**Fase 3: Check**
Comprobar si los resultados obtenido son los esperados, es decir, si el test tuvo éxito o falló.
**Fase 4: Teardown**
Limpiar los objetos creados para durante la ejecución del test.

### Independencia de tests

*Mientras mayor sea la dependencia entre los test menos exacta será la información acerca de un fallo en particular. Si tenemos test que dependen de otros, los cambios introducidos en estos últimos afectarán a los primeros. Al hacer los test independientes los fallos indicarán información mucho más útil y los test serán mas confiables.*

### Mocks object

*Son simuladores que imitan el comportamiento de otros objetos de manera controlada*

> **¿Cuándo usar mock objects?**
Cuando el objeto real es un objeto complejo que:
  - retorna resultados no determinístico
  - tiene estados que son difíciles de reproducir
  - es lento
  - todavía no existe
  - tiene dependencias con otros objetos y necesita ser aislado para testearlo como unidad
