### HERENCIA
**La herencia** en todos los ámbitos (derecho, biología,...) tiene connotaciones de trasmisión.

**En POO** es la transmisión de la vista pública(métodos públicos) y de la vista privada (métodos privados y definición de los métodos) de una clase a otra.
(sería como un copy paste dinámico, se transmite el código sin necesidad de copiarlo)

**Clase padre / base / superclase(obsoleto):** Es La clase que transmite sus atributo y sus métodos
**Clase hija / derivada / subclase:** Es la clase a la que se le trasmiten los atributos y métodos.

**La relación de herencia:**
 - es una relación binaria entre clases
 - si existe una relación de herencia, no es necesario que exista una colaboración entre los objetos de sus clases aunque tampoco lo impide
 - los objetos de la clase de una relación de herencia son, a priori, independientes

Existen otros tipos de relaciones, **Las relaciones de composición, asociación y dependencia** son relaciones binarias que surgen de la colaboración entre objetos

**Tipos de relación de herencia:**
- Herencia simple: cuando una clase derivada hereda de una única clase base.
- Herencia múltiple: cuando una clase derivada hereda de varias clases base.
	(Tiene ambigüedades ya que pude existir el mismo nombre de atributo o método en las dos clase base, y hay que resolverlas dichas ambigüedades. En java, está capado la herencia múltiple)


### JERARQUIAS DE CLASIFICACIÓN
Son aquellas, donde cada nodo(clase) de la jerarquía de herencia establece un dominio de elementos(un conjunto de objetos) incluido en el dominio de los nodos padre e incluye a los dominios de cada nodo hijo.
Ejemplo: Animal, Vertebrado, Invertebrado....

Cada una de las clases en la jerarquía de clasificación, solo tiene que escribir en lo que se especializa, ya que lo demás lo hereda

**Características:**
- Son subjetivas
- contemplan elementos que son difícilmente categorizadles
- dificultad para establecer una clasificación "perfecta"
- Esqueleto fundamental de un programa junto con la jerarquía de composición

Reglas de construcción:
- Regla de Generalización / Especialización: cuando existen unas características específicas de un subconjunto de elementos dentro un determinado conjunto más amplio, que pese a que mantienen las características esencial e identificativa del conjunto al que pertenecen, también son lo suficientemente relevantes como para ser rasgos distintivos de dicho subconjunto de elementos.
- Regla ¿Es un?(ISA en ingles): responder afirmativamente que un objeto de la clase hija es un objeto de la clase padre.
	Ejemplo: Un cerdo es un animal.


### HERENCIA POR EXTENSIÓN
Class ClaseDerivada extends ClaseBase{
	\<Atributos añadidos\>
	...
	\<Métodos añadidos\>
}
![[Pasted image 20230923203629.png]]
El padre tiene todos los métodos y atributos que tiene la clase Abuela, y a su vez, la clase hija, tiene todos los métodos y atributos del padre y a su vez lo de la abuela.

Especialización por adición de atributos y/o métodos:
- Los atributos en la clase hija tiene las mismas reglas sintácticas y semánticas que una clase que no sea derivada
- los métodos añadidos de una clase hija tienen las mismas reglas semánticas que una clase que no sea derivada excepto que **no tienen accesos a los atributos y métodos privados transmitidos por el padre.**
Si dejaras público los atributos en la clase padre, y las clase hija, usa dichos atributos. En el momento que cambies los atributos por necesidad, habría una oleada de mantenimiento en las clases hijas también. Por eso es recomendable quedarlos privado.

**Implicaciones sobre los objetos:**
- Los objetos de la clase padre NO sufre ninguna alteración por la presencie a de la clase derivada
- Los objetos de la clase hija:
	- Tienen todos los atributos transmitidos desde la clase padre junto con los atributos añadidos en la clase hija.
	- Responden a mensajes que corresponden con los métodos públicos transmitidos desde la clase padre junto con los métodos públicos añadidos en la clase derivada.

**Visibilidad pública:**
En caso de que **la clase padre** no transmita **los métodos públicos necesarios para manipulas atributos privados en la clase derivada**, porque la clase por si misma, no tenga la necesidad de hacerlo, **añadir dichos métodos públicos a la clase padre NO es una solución**, esto rompe el principio de encapsulación.
(ya que los objetos de la clase padre dan a conocer mas allá de lo que se le solicitaba previamente a la existencia de la clase derivada)

SOLUCION
**Visibilidad protected:** Los miembros(atributos y/o métodos) son accesibles en la implantación de la clase y en cualquier clase derivada.

En el libro de C++ de Stroustrup, dice que aunque el lenguaje permita más, deberíamos seguir estas reglas:
- los atributos deben ser **privado**
- **getter y setter:** protected y cuando haga falta públicos
- **métodos:** públicos, protected o privado.


En caso de que hubiera puesto atributos protected, es decir dentro de los métodos de la clase derivada, tiene acceso a los atributos transmitidos, a los atributos añadidos, a los parámetros del método y a las declaraciones locales(Ley flexible de demeter)

**IMPLICACION:** desbordamiento dado que si se modifica la implantación de la clase padre **SI repercute sobre la implantación de la clase hija** y se obtiene su máximo acoplamiento entre ambas clases.


**Especialización por redefinición de métodos:**
Es cuando sobrescribes la codificación de un método de la clase padre en la clase derivada.
- Esto sucede siempre y cuando la cabecera del método sea exactamente igual, aunque su visibilidad puede ampliarse.
- Conlleva a que la clase padre tiene un comportamiento para ese método y la derivada otro comportamiento.

### PALABRA RESERVADA SUPER
**super**, es una referencia constante que guarda la dirección del objeto que recibe el mensaje correspondiente al método que se está redefiniendo, pero con el comportamiento de la clase padre.
### CLASE OBJECT
**Toda clase no derivada hereda de la clase predefinida Object**, que proporciona un conjunto de métodos comunes a todas las clases, algunos de ellos susceptibles de ser redefinidos en cualquier clase de la manera oportuna.

### CLASES ABSTRACTAS
Clases Abstractas: Son clases NO instanciadles que surgen del factor común del código de otras clases con atributos comunes, métodos comunes y/o cabeceras de métodos comunes sin definición. 
Síntesis: abstract class /<ClaseAbstracta/>


En cambio las clases concretas: Surgen de la descripción de los atributos y métodos que definen el comportamiento de un cierto conjunto de objetos homogéneos.
### UTILIZACION DE CENTINELA EN CENTINELA
Es una optimización para buscar elementos en una lista. 
Añade un elemento al final de una lista. En vez de comprobar que no se salga de la lista, le dices que siga iterándola mientras no sea ese elemento que buscas(ya que mínimo está en la última posición). Al finalizar el bucle, compruebas si el encontrado es diferente al **puntero** de la última posición, si te da que es el mismo, pues no lo ha encontrado, ya que llegó al final de la lista. Importante quitar dicho elemento del final de la lista cuando termines.

(según el ejemplo del video pasa de complejidad algorítmica 3n a 2n, es decir más eficiente)

**Ejemplo de bucle centinela:** bucle donde pides un número, y mientras sea diferente de 0 sigues entrando

