Patrones
========

¿Qué es un patrón de diseño?
Cada patrón describe un problema que ocurre una y otra vez en un contexto y su solución, de tal modo que se pueda aplicar esta solución miles de veces, sin hacer lo mismo dos veces.
Un patrón tiene cuatro elementos esenciales:

1. El *nombre del patrón*, que permite describir un problema de diseño junto con sus soluciones y consecuencias. 
2. El *problema*, que describe cuándo aplicar el patrón, explica el problema y su contexto. A veces el problema incluye una serie de condiciones que deben darse para que tenga sentido aplicar el patrón.
3. La *solución*, que describe los elementos que constituyen el diseño, sus relaciones, responsabilidades y colaboraciones. La solución no describe un diseño o una implementación en concreto, sino que un patrón es más bien como una plantilla que puede aplicarse en muchas situaciones diferentes.
4. Las *consecuencias*, son los resultados así como las ventajas e inconvenientes de aplicar el patrón. Son fundamentales para evaluar las alternativas de diseño y comprender los costes y beneficios de aplicar el patrón. Las consecuencias incluyen su impacto sobre la flexibilidad, extensibilidad y portabilidad de un sistema.


El patrón identifica las clases de instancias principales, sus roles y colaboraciones, y la distribución de responsabilidades. Cada patrón de diseño se centra en un problema concreto, describiendo cuándo aplicarlo y si tiene sentido hacerlo teniendo en cuenta otras restricciones de diseño, así como las consecuencias y las ventajas e inconvenientes de su uso.

Descripción de los patrones de diseño
Cada patrón de diseño se divide en las secciones de acuerdo a la siguiente plantila:
* Nombre del patrón y clasificación.
* Propósito: responde las cuestiones de qué hace el patrón, en qué se basa, y cuál es el problema concreto de diseño que resuelve.
* También conocido como.
* Motivación: un escenario que ilustra un problema de diseño y cómo las estructuras de clases y objetos del patrón resuelven el problema.
* Aplicabilidad: responde a las preguntras de en qué situaciones se pueden aplicar, qué ejemplos hay de malos diseños que el patrón puede resolver, y cómo se pueden reconocer dichas situaciones.
* Estructura: representación gráfica de las clases del patrón.
* Participantes: las clases y objetos participantes en el patrón de diseño, junto con sus responsabilidades.
* Colaboraciones: cómo colaboran los participantes para llevar a cabo sus responsabilidades.
* Consecuencias: responde a ¿cómo consigue el patrón sus objetivos? ¿cuáles son las ventajas, inconvenientes y los resultados de usar el patrón? ¿qué aspectos de la estructura del sistema se pueden modificar de forma independiente?
* Implementación: ¿cuáles son las dificultades, trucos o técnicas que deberíamos tener en cuenta a la hora de aplicar el patrón? ¿hay cuestiones específicas del lenguaje?

Singleton
---------

*Garantiza que una clase sólo tenga una instancia, y proporciona un punto de acceso global a ella.*

### Aplicabilidad

* Deba haber exactamente una instancia de una clase, y ésta debe ser accesible a los clientes desde un punto de acceso conocido.
* La única instancia debería ser extensible mediante herencia, y los clientes deberían ser capaces de usar una instancia extendida sin modificar su código.

![singleton](/images/singleton.png)

Adapter
-------

*Convierte la interfaz de una clase en otra interfaz que es la que esperan los clientes. Permite que cooperen clases que de otra forma no podrían por tener interfaces incompatibles.*

### Aplicabilidad

* Se quiere usar una clase existente y su interfaz no concuerda con la que necesita.
* Se quiere crear una clase reutilizable que coopere con clases no relacionadas o que no han sido previstas, es decir, clases que no tienen por qué tener interfaces compatibles.
* Es necesario usar varias subclases existentes, pero no resulta práctico adaptar su interfaz heredando de cada una de ellas. Un adaptador de objetos puede adaptar la interfaz de su clase padre.

![adapter](/images/adapter.png)

Composite
---------

*Compone objetos en estructuras de árbol para representar jerarquías de parte-todo. Permite que los clientes traten de manera uniforme a los objetos individuales y a los compuestos.*

### Aplicabilidad

* Quiera representar jerarquías de objetos parte-todo.
* Quiera que los clientes sean capaces de obviar las diferencias entre composiciones de objetos y los objetos individuales. Los clientes tratarán a todos los objetos de la estructura compuesta de manera uniforme.

![composite](/images/composite.png)

Decorator
---------

*Asigna responsabilidades adicionales a un objeto dinámicamente, proporcionando una alternativa flexible a la herencia para extender la funcionalidad.*

### Aplicabilidad

* Para añadir objetos individuales de forma dinámica y transparente, es decir, sin afectar a otros objetos.
* Para responsabilidades que pueden ser retiradas.
* Cuando la extensión mediante la herencia no es viable. A veces es posible tener un gran número de extensiones independientes, produciéndose una explosión de subclases para permitir todas las combinaciones. O puede ser que una definición de una clase esté oculta o que no esté disponible para ser heredada.

### Consecuencias
+ Permite mayor flexibilidad que la herencia: se puede agregar o quitar comportamiento dinámicamente, en cambio con herencia esto se decide estáticamente.
+ Permite agregar funcionalidad incrementalmente.
- Mayor cantidad de objetos.

![decorator](/images/decorator.png)

Observer
--------

*Define una dependencia de uno-a-muchos entre objetos, de forma que cuando un objeto cambie de estado se notifique y se actualicen automáticamente todos los objetos que dependen de él.*

### Aplicabilidad

* Cuando una abstracción tiene dos aspectos y uno depende del otro. Encapsular estos aspectos en objetos separados permite modificarlos y reutilizarlos de forma independiente.
* Cuando un cambio en un objeto requiere cambiar otros, y no sabemos cuántos objetos necesitan cambiarse.
* Cuando un objeto debería ser capaz de notificar a otros sin hacer suposiciones sobre quiénes son dichos objetos. En otras palabras, cuando no queremos que estos objetos estén fuertemente acoplados.

![observer](/images/observer.png)

State
-----

*Permite que un objeto modifique su comportamiento cada vez que cambie su estado interno. Parecerá que cambia la clase del objeto.*

### Aplicabilidad

* El comportamiento de un objeto depende de su estado, y debe cambiar en tiempo de ejecución dependiendo de ese estado.
* Las operaciones tiene largas sentencias condicionales con múltiples ramas que dependen del estado del objeto. Este estado, se suele representar por una o mas constantes enumeradas. Muchas veces son varias las operaciones que contienen esta misma estructura condicional. Este patrón pone cada rama de la condición en una clase aparte.

![state](/images/state.png)

Strategy
--------

*Define una familia de algoritmos, encapsula cada uno de ellos y los hace intercambiables. Permite que un algoritmo varíe independientemente de los clientes que lo usan*

### Aplicabilidad

* Muchas clases relacionadas difieren sólo en su comportamiento. Las estrategias permiten configurar una clase con un determinado comportamiento de entre muchos posibles.
* Se necesitan distintas variantes de un algoritmo. Por ejemplo, podríamos definir algoritmos que reflejasen distintas soluciones de compromiso entre tiempo y espacio. Pueden usarse estrategias cuando estas variantes se implementan como una jerarquía de clases de algoritmos.
* Un algoritmo usa datos que los clientes no deberían conocer. Úsese el patrón Strategy para evitar exponer estructuras de datos complejas y dependientes del algoritmo.
* Una clase define muchos comportamientos, y éstos se representan como múltiples sentencias condicionales en sus operaciones. En vez de tener muchos condicionales, podemos mover las ramas de éstos a su propia clase Estrategia.

![strategy](/images/strategy.png)

Template method
---------------

*Define en una operación el esqueleto de un algoritmo, delegando en las subclases algunos de sus pasos. Permite que las subclases redefinan ciertos pasos de un algoritmo sin cambiar su estructura.*

### Aplicabilidad

* Para implementar las partes de un algoritmo que no cambian y dejar que sean las subclases quienes implementen el comportamiento que puede variar.
* Cuando el comportamiento repetido de varias subclases debería factorizarse y ser localizado en una clase común para evitar el código duplicado. Ésta es una buena idea de "refactorizar para generalizar". Primero se identifican las diferencias en el código existente, luego se separan dichas diferencias en nuevas operaciones. Por último, se sustituye el código que cambia por un método que llama a una de estas nuevas operaciones.
* Para controlar las extensiones de las subclases. Podemos definir un método plantilla que llame a operaciones "de enganche" en determinados puntos, permitiendo así las extensiones sólo en esos puntos.

![template_method](/images/template.png)

State vs. Strategy
------------------

* Tienen el mismo diagrama de clases y la misma idea de delegación.
* Pero:
  * En el State, el estado es privado del objeto, ningún otro objeto sabe de él. En cambio, en el Strategy, el estado suele setearse por el cliente, que debe conocer las posibles estrategias concretas.
  * Un State define una máquina de estados con sus transiciones.
  * Cada State puede definir muchos mensajes. En cambio, un Strategy suele tener un único mensaje público.
  * Los State concretos se conocen entre sí, mientras que los Strategy concretos no.

Adapter (wrappers) vs. Decorator
--------------------------------
* Ambos patrones "decoran" el objeto para cambiarlo.
* Decorator *preserva* la interfaz del objeto para el cliente. En cambio el Adapter *convierte* la interfaz del objeto para el cliente.
* Los Decorator pueden y suelen anidarse, los Adapter no se anidan.

Decorator vs. Strategy
----------------------

* Ambos permiten cambiar el comportamiento de un objeto.
* Pero:
  * El Decorator cambia el envoltorio, y el Strategy cambia el objeto internamente.
  * El componente no conoce quien o quienes lo decoran. Con Strategy, el componente debe conocer a sus posibles estrategias, lo que lo hace menos extensible.
  * El protocolo de Decorator debe ser igual al de su componente. En el Strategy puede ser otro protocolo. Entonces, Strategy conviene cuando la clase Component es muy pesada.
