Refactoring
===========

Es el proceso a través del cual se cambia un sistema de software mejorando la organización, legibilidad, adaptabilidad y mantenibilidad del código luego que ha sido escrito. No altera el comportamiento externo del sistema, pero si mejora su estructura interna.
* Facilita la incorporación de nuevo código.
* Permite agregar patrones después de haber escrito el programa.
* Permite transformar un programa en framework.
* Mejora la comprensión del código.

¿En qué consiste?
----------------

Realizar un refactoring implica eliminar duplicaciones, simplificar lógicas complejas, clarificar códigos, etc. A través de cambios pequeños.
Hacer muchos cambios pequeños es más fácil y más seguro que un gran cambio. Cada cambio pequeño pone en evidencia otros cambios necesarios.
Es de suma importancia testear después de cada cambio a medida que vamos aplicando algún refactoring, para evitar que este rompa su principal premisa que es la de mantener el comportamiento observable de la clase que está siendo refactorizada.

¿Cuándo refactorizar?
---------------------

- Un nuevo requerimiento se vea difícil de implementar
- Una nueva funcionalidad agregada produjo código feo
- Se hace difícil interpretar el código

Catálogo
--------

Se realiza refactoring de código identificando los "malos olores" del mismo y arreglándolos utilizando las siguientes técnicas:

### Extract method

*Se aplica cuando se tiene métodos largos y/o muy comentados. Ayuda a incrementar reuso y legibilidad.*

#### Mecánica:

* crear un nuevo método cuyo nombre explique su propósito
* copiar el código a extraer en el nuevo método
* revisar las variables locales del original. Si alguna se usa sólo en el código extraído, se mueve su declaración
* revisar si alguna variable local es modificada por el código extraído. Si es solo una, se trata como query y se asigna. Si hay más de una no se puede extraer
* pasar como parámetro las variables que el método nuevo lee
* compilar
* reemplazar código en método original por llamada
* compilar

### Change name of variables

*Los nombres de variables adecuados aumentan la claridad y la interpretación del código*

### Move method

*Un método esta usando o usará muchos servicios que están definidos en una clase diferente a la suya (feature envy).*

#### Mecánica:

* revisar otros atributos y métodos en la clase original
* chequear subclases y superclases
* declarar el método en la clase destino
* copiar y ajustar el código; chequear manejo de excepciones
* convertir el método original en una delegación
* compilar y testear
* decidir si eliminar el método original, si es así hay que eliminar las referencias
* compilar y testear

### Replace temp with query

*Se utiliza para quitar las variables temporales que, al ser locales, fomentan métodos largos. Además, nos permite usar una expresión desde otros métodos. Se aplica antes de realizar un extract method.*

#### Mecánica:

* encontrar las variables temporales con una sola asignación
* extraer el lado derecho de la asignación
* reemplazar todas las referencias de la variable temporal por el nuevo método
* eliminar la declaración de la variable temporal y las asignaciones
* compilar y testear

### Replace condicional with polymorfism

*Cuando se tiene un condicional que derivan en sentencias con distintos comportamientos.*

#### Mecánica:

* mover la sentencia swich a la superclase de la jerarquía
* copiar una rama del case en su correspondiente subclase
* compilar y testear
* repetirlo para cara rama del case
* reemplazar la sentencia case por el método abstracto

### Inline method

*Se utiliza cuando el cuerpo del método es tan claro como su nombre.*

#### Mecánica:

* Insertar el cuerpo del método en el cuerpo de los que lo invocan y borrar el método

### Pull up method

*Se utiliza cuando las subclases tienen métodos que realizan una tarea similar.*

#### Mecánica:

* Hacer que los métodos similares hagan exactamente lo mismo
* Mover los métodos a la superclase

### Pull down method

*Se utiliza cuando un método en la superclase sólo es usado por una de sus subclases*

#### Mecánica:

* Mueve este comportamiento a la subclase que lo utiliza

Clasificación según solución para malos olores
----------------------------------------------

* **Código duplicado:**
  - extract method
  - pull up method
  - form template method
* **Métodos largos:**
  - extract method
  - decompose conditional
  - replace temp with query
* **Clases grandes:**
  - extact class
  - extract subclass
* **Muchos parámetros:**
  - replace parameter with method
  - introduce parameter object
* **Cambios divergentes:**
  - extract method
* **Envidia de atributo:**
  - move method
* **Sentencias switch:**
  - replace conditional with polymorfism
* **Lazy class:**
  - inline class
* **Middle man:**
  - remove middle man
* **Inappropiate intimacy:**
  - move method field
* **Data class:**
  - move method
