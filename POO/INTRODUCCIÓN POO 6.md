### INTERFACES
Al tener problemas con herencia múltiple, ya que dan muchas ambigüedades. Java decidió usar interfaces, que es una semi-herencia múltiple.
**Las interfaces son clases abstractas puras** que no contienen ningún atributo ni la definición de ningún método, sólo contienen métodos abstractos. Puede ser clases padre de clase u otra interfaces.

- Todos los métodos de la interfaz, son públicos. Al ser así, no es necesario poner public, ya que son public de per se.

Limitaciones:
- Una interfaz NO puede heredar de una clase(si de otra interfaz)
- Una clase, puede heredar de una clase por extensión, y puede heredar de varias clases por implementación
- La herencia por extensión NO disfruta de herencia múltiple, pero por implementación SI

**clase final:** no permiten ningún tipo de herencia posterior.
**método final:** no permiten ningún tipo de redefinición posterior.

La herencia favorece, la Integridad de la arquitectura del software y favorece la lectura del software.
Es muy útil ya que reutilizas el código.
 ![[Pasted image 20230927215653.png]]
#### POLIMORFISMO (Muchas formas)
Es una simple relajación del sistema de tipos, donde cualquier referencia que declares, puede ser de esa clase de la que ha sido declarada, o de cualquier de sus padres.

2:00:00