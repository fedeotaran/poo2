Patrones
========

Adapter
-------

*Convierte la interfaz de una clase en otra interfaz que es la que esperan los clientes. Permite que cooperen clases que de otra forma no podrían por tener interfaces incompatibles.*

### Aplicabilidad

* Se quiere usar una clase existente y su interfaz no concuerda con la que necesita.
* Se quiere crear una clase reutilizable que coopere con clases no relacionadas o que no han sido previstas, es decir, clases que no tienen por qué tener interfaces compatibles.
* Es necesario usar varias subclases existentes, pero no resulta práctico adaptar su interfaz heredando de cada una de ellas. Un adaptador de objetos puede adaptar la interfaz de su clase padre.

Compisite
---------

*Compone objetos en estructuras de árbol para representar jerarquías de parte-todo. Permite que los clientes traten de manera iniforme a los objetos individuales y a los compuestos.*

### Aplicabilidad

* Quiera representar jerarquías de objetos parte-todo.
* Quiera que los clientes sean capases de obviar las diferencias entre composiciones de objetos y los objetos individuales. Los clientes tratarán a todos los objetos de la estructura compuesta de manera uniforme.

Decorator
---------

*Asigna responsabilidades adicionales a un objeto dinámicamente, proporcionando una alternativa flexible a la herencia para extender la funcionalidad.*

### Aplicabilidad

* Para añadir objetos individuales de forma dinámica y transparente, es decir, sin afectar a otros objetos.
* Para responsabilidades que pueden ser retiradas.
* Cuando la extensión mediante la herencia no es viable. A veces es posible tener un gran número de extensiones independientes, produciéndose una explosión de subclases para permitir todas las combinaciones. O puede ser que una definición de una clase esté oculta o que no esté disponible para ser heredada.

Observer
--------
*Define una dependencia de uno-a-muchos entre objetos, de forma que cuando un objeto cambie de estado se notifique y se actualicen automáticamente todos los objetos que dependen de él.*

### Aplicabilidad

* Cuando una abstracción tiene dos aspectos y uno depende del otro. Excapsular estos aspectos en objetos separados permite modificarlos y reutilizarlos de forma independiente.
* Cuando un cambio en un objeto requiere cambiar otros, y no sabemos cuántos objetos necesitan cambiarse.
* Cuando un objeto debería ser capaz de notificar a otros sin hacer suposiciones sobre quiénes son dichos objetos. En otras palabras, cuando no queremos que estos objetos estén fuertemente acoplados.

State
-----

*Permite que un objeto modifique su comportamiento cada vez que cambie su estado interno. Parecera que cambia la clase del objeto.*

### Aplicabilidad

* El comportamiento de un objeto depende de su estado, y debe cambiar en tiempo de ejecucion dependiendo de ese estado.
* Las operaciones tiene largas sentencias condicionales con multiples ramas que dependen del estado del objeto. Este estado, se suele representar por una o mas constantes enumeradas. Muchas veces son varias las operaciones que contienen esta misma estructura condicional. Este patron pone cada rama de la condicion en una clase aparte.

