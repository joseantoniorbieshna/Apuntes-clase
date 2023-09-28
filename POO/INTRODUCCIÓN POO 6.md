### INTERFACES
Al tener problemas con herencia múltiple, ya que dan muchas ambigüedades. Java decidió usar interfaces, que es una semi-herencia múltiple.
**Las interfaces son clases abstractas puras** que no contienen ningún atributo ni la definición de ningún método, sólo contienen métodos abstractos. Puede ser clases padre de clase u otra interfaces.

- Todos los métodos de la interfaz, son públicos. Al ser así, no es necesario poner public, ya que son public de per se.

**Limitaciones:**
- Una interfaz NO puede heredar de una clase(si de otra interfaz)
- Una clase, puede heredar de una clase por extensión, y puede heredar de varias clases por implementación
- La herencia por extensión NO disfruta de herencia múltiple, pero por implementación SI

**clase final:** no permiten ningún tipo de herencia posterior.
**método final:** no permiten ningún tipo de redefinición posterior.

La herencia favorece, la Integridad de la arquitectura del software y favorece la lectura del software.
Es muy útil ya que reutilizas el código.
 ![[Pasted image 20230927215653.png]]
#### POLIMORFISMO (Muchas formas)
**Polimorfismo:** Es una simple relajación del sistema de tipos, donde cualquier referencia que declares, puede ser de esa clase de la que ha sido declarada, o de cualquier de sus derivadas.

**Tipos de lenguaje de programación:**
- **universo cerrado:** Si un clase hereda de x clases, solo podrá utilizar las cosas de esas clases.
- **universo abierto:** Podrías llamar a cualquier función pero te crashearía en tiempo de ejecución.

**Ejemplo:** No se contempla que un periquito se convierta en un cuervo, ni que un periquito sea un periquito y un cuervo a la vez. Lo único que se contempla es que una referencia a Animal apunte a un periquito o un cuervo.

**Comportamiento:** Cuando se lanza un mensaje a un objeto a través de una referencia polimórfica, se ejecuta el método prescrito en la clase dl objeto que recibe el mensaje.
![[Pasted image 20230928095239.png]]

**Limitaciones:** 
cuando se lanza un mensaje a un objeto a través de una **referencia polimórfica,** éste **debe estar contemplado en la interfaz de de la clase** de la que se declaró la referencia sin contemplar los posibles métodos añadidos el a clase de objetos apuntados.

Ejemplo: si a una referencia tipo animal, le digo que apunte a un periquito podría solo lanzar mensajes a los objetos de la clase animal, pero no de la clase periquito.

**Formación del polimorfismo**
**Enlace:** es la asociación entre un elemento de un lenguaje de programación y una de sus características.
Hay 2 tipos:
- **Enlace estático:** Es aquel que puedo resolver analizando el código, es decir en tiempo de compilación.
- **Enlace dinámico:** aquel que no se puede resolver analizando el código sino que se resuelve en tiempo de ejecución.

2:24:15