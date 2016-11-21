Tarea: Investigacion 20-Nov-16
=======

 Nombre      | NUA:         |          Curso       |
 ------------- |:-------------:|:---------:|
 Juan Daniel Téllez Ponce     | 144666 | Aplicaciones Mobiles |
 

>El alumno realizara una investigación sobre los siguientes puntos:
* Arquitectura Model View Presenter Vs. Model View Controller
* Arquitectura CLEAN (Uncle Bob)
* Biblioteca EventBus

 
#Arquitectura Model View Presenter y similitudes con Model View Controller:

* ¿Qué es el MVP?

El patrón MVP permite separar la capa de presentación de la lógica de la misma, de tal forma que todo lo relacionado con cómo funciona la interfaz queda separado del cómo representarlo en pantalla. Idealmente el patrón MVP permitiría conseguir que una misma lógica pudiera tener vistas totalmente diferentes e intercambiables.

* ¿Por qué usar MVP?

En Android tenemos un problema derivado del hecho de que las actividades en Android están íntimamente acopladas tanto con la interfaz como con las mecánicas de acceso a datos. Hasta tal punto que existen clases como el CursorAdapter, que mezclan los adaptadores, que son parte de la vista, con los cursores, algo que debería estar relegado a lo más profundo de la capa de acceso a datos. 
El MVP independiza la vista de la forma de conseguir esos datos. Nos divide la aplicación en, al menos, tres capas distintas, pudiendo además testear cada una de ellas de forma independiente.

* Comparando con MVC:

El MVP (Model View Presenter) es un patrón derivado del conocido MVC (Model View Controller), que de un tiempo a esta parte está cobrando gran importancia en el desarrollo de aplicaciones Android. Cada vez hay más gente hablando del tema, pero sin embargo muy poca información fiable y estructurada. El controlador es responsable de determinar qué vista se visualiza en respuesta a cualquier acción incluso cuando se carga la aplicación. Esto difiere de MVP en que las acciones a través de la ruta Vista al presentador. En MVC, cada acción en la vista se correlaciona con una llamada a un controlador, junto con una acción. En la web cada acción implica una llamada a un URL en el otro lado de la cual hay un controlador que responde. Una vez que el controlador ha completado el proceso, se le devolverá el punto de vista correcto.

#Arquitectura CLEAN (Uncle Bob)

Surge con la problemática que en la mayoría de los desarrollos en los cuales existe un framework se encuentra más código que lo representa, en lugar del problema que está resolviendo, es decir la idea es centrarse en lo que tiene que hacer la aplicación como tal y es por ello que dice que debemos de pensar en él framework como el mecanismo de paso de mensajes hacia nuestro software, el cual se debe mirar como una herramienta o plugin de lo que queremos realizar.
El autor dice en varias de sus charlas que más que una arquitectura sólo son una serie de condiciones que se deben cumplir para que una arquitectura de considere ”clean”, solo son una serie de reglas que lo único que van a hacer es dividir el software en capas.

![clean_archi](https://cloud.githubusercontent.com/assets/21039708/20472264/dbc9276e-af7d-11e6-8fa6-af7dbd6753b9.png)

* Beneficios de usar la Arquitectura CLEAN Android:

Existe una cantidad muy grande de diversas arquitecturas algunas en las cuales Uncle Bob se ha basado son Hexagonal Architecture, Onion Architecture, Screaming Architecture y lo importante es que cada una de ellas varía en sus detalles de implementación pero todas son similares y tienen el mismo objetivo separar en capas nuestro software con la finalidad de darle flexibilidad.

Las principales aportaciones que esta arquitectura seguirá motivando son:

-Independiente de frameworks

-Testable

-Independendiente de nuestra UI

-Independendiente de nuestra DB

-Independendiente de cualquier herramienta externa


![android_archi](https://cloud.githubusercontent.com/assets/21039708/20472338/8dc2bc3c-af7e-11e6-8609-64ee87d78940.png)

#EventBust

EventBus permite la publicación-suscripción al estilo de comunicación entre los componentes sin necesidad de los componentes para registrar de manera explícita entre sí (y por lo tanto ser conscientes el uno del otro). Está diseñado exclusivamente para sustituir a la distribución tradicional de Java en proceso de sucesos mediante registro explícito. Es no un sistema de publicación-suscripción de propósito general, ni se pretende para la comunicación entre procesos.

![eventbus-publish-subscribe](https://cloud.githubusercontent.com/assets/21039708/20472418/4435216c-af7f-11e6-8e8f-581b63eefca5.png)

* Como radica en nuestra APP la biblioteca EventBust:

Para detectar un sabor específico de evento (por ejemplo, un CustomerChangeEvent):
>>En los eventos tradicionales de Java: implementar una interfaz definida con el evento - como CustomerChangeEventListener.

>>Con EventBus: crear un método que acepta CustomerChangeEventcomo su único argumento, con la marca de la @Subscribeanotación.

  Para registrar sus métodos de detectores con los productores de eventos:
>>En los eventos tradicionales de Java: pasar su objeto a cada productor del registerCustomerChangeEventListenermétodo. Estos métodos son raramente definen en las interfaces comunes, lo que además de conocer cada productor sea posible, también debe conocer su tipo.

>>Con EventBus: pasar el objeto en el EventBus.register(Object)método en un EventBus. Tendrá que asegurarse de que su objeto comparte una EventBusinstancia con los productores de eventos.

  Para escuchar para un supertipo evento común (por ejemplo, EventObjecto Object):
>>En los eventos tradicionales de Java: no es fácil.

>>Con EventBus: eventos se distribuyen automáticamente a los oyentes de cualquier supertipo, lo que permite a los oyentes para tipos de interfaz o "comodín" para los oyentes Object.

  Para escuchar y detectar eventos que fueron enviadas sin oyentes:
>>En los eventos tradicionales de Java: agregar código para cada método de despacho de eventos (tal vez usando AOP).

>>Con EventBus: suscribirse DeadEvent. El EventBusle notificará de cualquier evento que se contabilizaron pero no entregados. (Útil para la depuración.)


