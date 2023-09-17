### POO
La programación orientada a objetos es un nuevo equilibrio en condiciones de igualdad entre los procesos y datos


#### Las bases de la programación a objeto son:
**Abstracción:** Proceso mental de extracción de características esenciales de algo, ignorando los detalles superfluos.

**Encapsulación:** Proceso por el que se ocultan los detalles del **soporte** de las características de abstracción.
[[Ejemplos#^260eec|Ejemplos]]

**Modularización:** Proceso de descomposición de un sistema en un conjunto de módulos ("Piezas") poco acopladas(independientes) y cohesivas (con significado propio)
[[Ejemplos#^eb1b7e|Ejemplos]]

**Jerarquización:** Proceso de estructuración por el que se produce una organización(jerarquía) de un conjunto de elementos en grados o niveles de responsabilidad, de incumbencia o de composición entre otros.
(Se recomienda que la jerarquización la hagas análoga al mundo real)
Ejemplos:
![[Pasted image 20230914140313.png]]
![[Pasted image 20230914140444.png]]
#### Véase también:
**Acoplamiento:** Es la medida de fuerza de las asociación establecida por una conexión entre un módulo (un modulo puede ser una clase o un paquete) y otro.

**Cohesión:** La cohesión mide el grado de conectividad entre los elementos de un solo módulo.


## Evolución de los lenguajes
![[Pasted image 20230914145352.png]]

Si comparamos las bases de
![[Pasted image 20230915144443.png]]

Donde TAD's son tipos abstractos de datos (igual que una clase pero sin herencia ni polimorfismos).


Esta evolución se ha dado para mejorar la abstracción, encapsulación, modularizarían y jerarquía.

Lheman y Belady se dieron cuenta de dos leyes muy importante:

**Ley del cambio continuo:** Un programa que se usa en un ámbito del mundo real, necesariamente debe cambiar o convertirse cada vez en menos útil.

**Ley de la complejidad creciente:** Debido a que los programas cambian por evolución, su estructura se convierte en más compleja a menos que se hagan esfuerzos activos para evitar este fenómeno.
[[Ejemplos#^bdf637|Ejemplo]]

El software, tiene las siguientes implicaciones:

- El incremento de abstracción, encapsulación, modularización y jerarquía aumentando la comprensión, la escalabilidad y la flexibilidad del software.

- el incremento de la comprensión, la escalabilidad y la flexibilidad del software.

- La reducción de los costes del mantenimiento.


Una nota que da Luis es, que es muy recomendable hacer TDD (Desarrollo dirigido por tests).


# Concepto de programación orientada objeto
**Clase:** Descripción de los datos (como un libro) y de las operaciones que describen el comportamiento de un cierto conjunto de elementos homogéneos.
Ejemplo: Clase Cerdo
	- datos: hocico, patas, cola...
	- Operaciones: ronca, gruñe, corre...

**Objeto:** Ejemplar concreto (instancia) de una clase, que responde al comportamiento definido por las operaciones de la clase a la que pertenece, adecuándose al estado de sus datos particulares.

Nota: Aunque clase y objetos estén relacionados, no los debes confundir.
Un claro ejemplo sería, no te comerías el libro el cerdo, pero si que te podrías comer un cerdo.
Ahí está la diferencia, uno es la descripción o definición y otro es el ejemplar.


**Mensaje:** Invocación de una operación sobre un objeto.
Un objeto es el agente activo, que es el que lanza el mensaje y otro sujeto es el agente activo, que es el que recibe el mensaje.
(El objeto receptor del mensaje tiene que tener definida dicha operación en su clase).

**Método:** definición de una operación de una clase.
**Parámetro:** argumento que recibe un método.
**Atributo:** Cada uno de los datos de una clase.
**Estado:** Conjunto de los valores de los atributo en un instante dado.

# Elementos de la programación orientada a objetos

**Vista pública o interfaz:** describe qué operaciones responden los objetos de esta clase.
Ejemplo:
Digo qué es lo que puede hacer un cerdo, pero no el como lo hace (no le digo si se tiene que ayudar con las mitocondrias, o mover un pie primero que otro...). En resumen, digo qué hace, pero no cómo lo hace.


**Vista privada o implantación:** describe las estructuras de datos de la clase y cómo manipulan las operaciones los datos.

Las clases que conjugan de forma equilibrada atributo(datos) y métodos (operaciones) son el único bloque de estructuración de programa llamado **Módulos**

La modularidad exige:
- Los datos y operación de una clase son elementos estrechamente relacionados favoreciendo que "una clase se entiende por sí misma", a esto se le llama **cohesión**.
(Es decir se entiende por si misma sin tener que entender el resto del código)

- Las clases se relacionan entre ellas **hay un cierto acoplamiento** porque colaboran lanzándose mensajes entre jerarquías de composición, clasificación, etc.