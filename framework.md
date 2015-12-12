Framework
=========

*Un framework es una aplicación semicompleta y reusable que puede ser especializada para producir aplicaciones especializadas. Es un conjunto de clases concretas y abstractas que cooperan entre ellas y que incorporan un diseño abstracto de soluciones para una familia de problemas relacionados.
Instanciar/especializar un framework es completar/configurar sus hotspot para obtener una aplicación particular. A esas modificaciones se las llama incremento.
Una característica importante de los frameworks es que los métodos definidos por el usuario para adaptar el framework generalmente van a ser llamados desde el framwork, y no desde el código de la aplicación del usuario (inversión de control). El framwork tiene el rol de programa principal, coordinando y secuenciando la actividad de la aplicación.*

Inversión de control
--------------------

*Es la característica principal de la arquitectura en tiempo de ejecución de un framework. Se manifiesta en los hotspots invocando a sus hooks methods. Permite al framework, determinar qué conjunto de métodos de la aplicación invocar en respuesta a eventos externos.*

> **Hotspots:** son las partes del framework donde ocurre la adaptación. Representan las partes donde los programadores, usando el framework, agregan su propio código con una funcionalidad específica para su proyecto. Los hotspot se corresponden muy fuertemente con los métodos/objetos gancho. Por lo general, un hotspot indica que hay que agregar un template y sus correspondientes métodos/objetos gancho. Whitebox y blackbox son dos tipos de hotspots.
> **Frozenspots:** partes del framework que no cambian. Es el código ya implementado que llama a los hotspots.

