Framework
=========

*Un framework es una aplicación semicompleta y reusable que puede ser especializada para producir aplicaciones especializadas. Es un conjunto de clases concretas y abstractas que cooperan entre ellas y que incorporan un diseño abstracto de soluciones para una familia de problemas relacionados.
Instanciar/especializar un framework es completar/configurar sus hotspot para obtener una aplicación particular. A esas modificaciones se las llama incremento.
Una característica importante de los frameworks es que los métodos definidos por el usuario para adaptar el framework generalmente van a ser llamados desde el framwork, y no desde el código de la aplicación del usuario (inversión de control). El framwork tiene el rol de programa principal, coordinando y secuenciando la actividad de la aplicación.*

Inversión de control
--------------------

*Es la característica principal de la arquitectura en tiempo de ejecución de un framework. Se manifiesta en los hotspots invocando a sus hooks methods. Permite al framework, determinar qué conjunto de métodos de la aplicación invocar en respuesta a eventos externos.*

Hot spots
--------

*Son las partes del framework donde ocurre la adaptación. Representan las partes donde los programadores, usando el framework, agregan su propio código con una funcionalidad específica para su proyecto. Los hotspot se corresponden muy fuertemente con los métodos/objetos gancho. Por lo general, un hotspot indica que hay que agregar un template y sus correspondientes métodos/objetos gancho. Whitebox y blackbox son dos tipos de hotspots.*

> Whitebox
Los hot spot de este tipo son los que están implementados utilizando herencia o subclasificación.


> Blackbox
Los hot spot de este tipo son los que están implementados utilizando composición.

Frozen spots
-----------

*Partes del framework que no cambian. Es el código ya implementado que llama a los hotspots.*

Clasificación
-------------

*Los frameworks también puede ser clasificados como _de caja negra_ o _de caja blanca_:*

> **De caja blanca:** dependen fuertemente de características orientadas a objetos como la herencia y el binding dinámico para proveer extensibilidad. Esto lo realiza heredando clases base y redefiniendo métodos gancho (hooks). Estos tipos de frameworks requieren que el desarrollador conozca intimamente los detalles de la estructura interna del framework.

> **De caja negra:** soporta extensibilidad vía la definición de interfaces para componentes que pueden ser enchufados al framework por composición de objetos. Esto lo realiza definiendo componentes que cumplen con uan interfaz determinada e integrando dichos componentes en el framework. Para su uso requiere estudiar librerías de componentes y sus configuraciones.

En general, los frameworks de caja negra son más fáciles de usar que los de caja blanca. Sin embargo, los frameworks de caja negra son más difíciles de desarrollar y por lo tanto menos flexibles.

Tipos de frameworks
-------------------

### De infraestructura

* Atacan problemas generales del desarrollo de software, que por lo general no son percibidos completamente por el usuario de la aplicación.
* Algunos de los focos de este tipo de frameworks son: interfaces de usuario, seguridad, contenedores de aplicación, procesamiento de imágenes, procesamiento de lenguaje, comunicaciones.
* Estos frameworks ofrecen una infraestructura portable y eficiente sobre la cual construir una gran variedad de aplicaciones.
* Es común que se los incluya como parte de plataformas de desarrollo.

### De integración

* Se utilizan comúnmente para integrar componentes de aplicación distribuida, por ejemplo, la base de datos con la aplicación y ésta con su cliente liviano.
* Los frameworks de integración o middleware están diseñados para incrementar la capacidad de los desarrolladores de modularizar, reusar y extender su infraestructura de software para que trabaje transparentemente en un ambiente distribuido.
* Ejemplos: ORB, ORM, Message Oriented Middleware

### Enterprise

* Estos frameworks atacan dominios de aplicación amplios que son pilares fundamentales de las actividades de las empresas.
* Ejemplos de frameworks enterprise son aquellos en el dominio y ERP (Enterprise Resource Planning), CRM (Customer Relationship Management), Gestión de documentos, Cálculos financieros.
* Los problemas que atacan derivan directamente de las necesidades de los usuarios de las aplicaciones y por tanto hacen que el retorno de la inversión sea más evidente y justificado.
* Puede encapsular el conocimiento y experiencia de muchos años de una empresa, transformándose en la clave de su ventaja competitiva y su más preciado capital
