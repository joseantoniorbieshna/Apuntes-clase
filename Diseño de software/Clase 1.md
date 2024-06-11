Los fundamentos del software, en todos los lenguajes y todos los paradigmas, son:
- **la abstracción**
- **la encapsulación**
- **la modularidad** 
- **la jerarquía**.

La economía del software(4 variables):
- el tiempo
- el coste
-  ámbito(requisitos o funcionalidad)
- Calidad del software
### DEFINICION DE SOFTWARE
Según Cox:
El software es la información que  suministra el desarrollador a la computadora para que manipule la información que suministra el usuario.
### Definición de sistema complejo
**Un sistema:** Es un conjunto de componentes interactuando o interdependientes formando un todo integrado. Cada sistema está delimitado por sus límites espacio/temporales e influenciado por su entorno, descrito por su estructura y propósito y expresado en su funcionamiento

Ejemplo: El sistema circulatorio, tiene corazón, venas, sangre...
El sistema respiratorio, o sistema universitario(Tiene profesores, personas interrelacionadas, buscan un objetivo común que es que se formen las personas...)


Se dice que es **un sistema complejo** cuando su complejidad excede la capacidad intelectual humana.
##### Atributos Sistemas Complejos
Los sistemas tienen una estructura jerárquica.
Donde el sistema complejo está compuesto de subsistemas interrelacionados que a su vez tienen su propios subsistemas y así hasta que se alcanza algún elemento del más bajo nivel.

- **Estructuras jerárquicas**
- **Elementos primitivos relativos**
		(Cuando son ya tipos primitivos y no interesa bajar más, por ejemplo cuando llegas a profesor, te da igual las células, glóbulos rojos...)
- **Separación de asuntos**
		Laboratorios, profesores o alumnos, al profesor le da igual como funcione alumno, solo le interesa, que lleguen a su silla por las mañanas.
- **Patrones comunes**
		La forma en la que se interconectan los elementos del sistemas, suelen ser la misma forma. Ejemplo: En el sistema sanguíneo flujo de sangre, sistema universitario, hablando...
- **Formas intermedias estables**: Todo sistema complejo alguna vez partió de un sistema sencillo que funcionaba.
		Es decir, un sistema complejo diseñado desde cero no funciona. Tienes que comenzar de nuevo, a partir de un sistema sencillo de trabajo.
### Complejidad
El principal enemigo de la fiabilidad, y tal vez de la calidad del software es **la complejidad**\[Meyer\]
- Ley de la conversación dela complejidad: Cada aplicación tiene una cantidad de complejidad que no puede ser eliminada u ocultada\[Tesler,87\]
- Cuanto más complejo sea un sistema, más abierto está al colapso total. Gran parte de la complejidad que se tiene que dominar es la **complejidad arbitraria o gratuita** \[Booch\]
- "**El descubrimiento del orden no es tarea fácil... Sin embargo, una vez que el orden ha sido descubierto no hay dificultad alguna en reconocerlo**" \[Descartes\]
- Mecanismo para facilitar la comprensión de un sistema complejo:
	- **la abstracción**
	- **la encapsulación**
	- **la modularidad** 
	- **la jerarquía**.

### ABSTRACCIÓN
Proceso mental de extracción de las características esenciales de algo, ignorando los detalles superfluos \[Booch\]
Ejemplo bus:
	Para mi lo importante en un bus es, que tenga conductor, la ruta, las horas de salida y llegada, precio. Pero ignoro, el tipo de gas, tipo de motor, mitocondrias del conductor...
	Sin embargo para un mecánico, no sería una abstracción mala lo anterior mencionado.
### Encapsulación
Ocultar el detalle del soporte de las características esenciales de una abstracción \[Booch\]
Ejemplo:
Entendiendo por soporte, que igual me viene de una base de datos, de un fichero, de un input del usuario y se guarda en memoria...

**Ocultación de la información:** Ocultar todo aquello que no me es relevante en absoluto.
### Modularidad
Es el proceso de descomposición de un sistema en un conjunto de piezas poco acopladas y cohesivas.\[Booch,96\]
- **El acoplamiento(Dependencia entre clases):** es la medida de fuerza de la asociación establecida por una conexión entre un módulo -elemento- y otro. El acoplamiento fuerte complica un sistema porque los módulos son más difíciles de comprender, cambiar o corregir por sí mismos si están muy interrelacionados con otros módulos.\[Booch, 96\]
	SI tuvieras acoplamiento 0, no pertenecerías al sistema.
- **La cohesión** mide el grado de conectividad entre los elementos de un solo módulo\[Booch,96\] Por tanto, un módulo cohesivo debe tener significado propio por sí mismo agrupando abstracciones lógicamente relacionados.


	Es decir, el **acoplamiento** mide la fuerza entre un elemento y los elementos de fuera, y la **cohesión** mide la fuerza o el grado de conexión entre los elementos de un elemento.

Si una clase llama a un método o instancia de otra clase, entonces ahí hay un acoplamiento(conocido de otra manera dependencia)

Modulo es Clase, método, paquete, librería...

Una clase, puede tener varias responsabilidad, sí están bien escogidas, comparten los mismos datos y tienen sentido que estén juntas, se dice que esa clase es cohesiva.

La técnica para manejar la complejidad, ha sido conocida desde la antigüedad, "Divide y vencerás".

### Jerarquía
Es el proceso de estructuración por el cual se produce una organización de un conjunto de elementos en grados o niveles de responsabilidad, de clasificación o de composición,... entre otros

![[Pasted image 20231203174435.png]]
![[Pasted image 20231203174500.png]]

**Análisis:** Haz lo correcto.(Voy a proponer unas clases, para hacer lo que tengo que hacer)
"Sería más entidades del mundo real"

Hay que tener en cuenta:
- Es superficial
- Es un análisis de problema del dominio, no del problema para la solución. 
	- No se mete en tecnologías
	- no entra en temas de distribución
	- no entra en sistemas operativos
	- no entra en si es para web o móvil, etc.
- Es como si estuviéramos haciendo un software maravilloso, donde se ejecutara en todos los sitios.
- Es hablar con el cliente, hablar con el lenguaje del cliente, sin pensar en tecnologías, ni lenguajes de programación.
**Diseño:** Hazlo correctamente.(Las clases propuestas, las voy a hacer bien, para que en caso de que me vengan con nuevas funcionalidades, pueda responder).
