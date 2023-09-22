# PROGRAMA ORIENTADO A OBJETOS
Al trabajar en un proyecto con muchas personas, habrá clase que hayan hecho otros y tú puedas utilizar, el cual solo necesitas conocer, el nombre de la clase y los métodos y a veces, con ayuda de la documentación en la clase. Sabes lo que hace, ignorando los detalles superfluos. A esto hemos dicho que le llamamos abstracción.

La abstracción, la utilizamos todos los días, cuando utilizamos un mando de la televisión, utilizando la lavadora... Tú sabes que le tienes que dar a un botón y que va a responder de x manera, el como lo haga no lo sabes y además te da igual para usarlo.

### CITAS

Cuando un programador piensan en los problemas, en términos de comportamientos y responsabilidades de los objetos, traen con ellos un caudal de intuición, ideas y conocimientos provenientes de su experiencia diaria.**\[Budd,94\]**

Según esta cita, cuando tú estás haciendo un programa a objetos, casi que estás haciendo como un espejo del mundo real, y al hacerlo así, se entiende mejor y se ahorran costes.




En lugar de un saqueador de bits que saquea estructurad de datos, nosotros tenemos un universo de objetos con buen comportamiento que cortésmente se solicitan entre sí cumplir diversos deseos.**\[Ingalls,81\]**



Un objeto en si mismo no es interesante. Los objetos contribuyen al comportamiento de un sistema colaborando con otros objetos.**\[Booch,96\]**


### Comparación programación tradicional y orientada a objetos
![[Pasted image 20230921215814.png]]

Como vemos aquí un programa tradicional, es un montón de variables arriba, y un montón de subprogramas que violan y sistemáticamente sodomizan a los datos.

La misma representación en objetos, nos encontramos con unos pocos datos y unas pocas operaciones para esos datos.

Los niveles de acoplamiento y cohesión mejoran muchísimo.

Si en el programa tradicional tuviera que cambiar un dato, tendría que cambiar en todo los subprogramas. En la poo, si cambio algo, solo necesitaría cambiarlo en ese modulo.

Además cohesivamente, la programación tradicional, sería imposible entenderla por si misma, ya que tendría que leerme toda la parte de valores, para entender mínimamente qué hace.  Un modulo de poo se entiende por si mismo.


#### PROGRAMA ORIENTADO A OBJETO
Un programa orientado a objeto, es un único objeto, que recibe un único mensaje, que produce un desencadenamiento de objetos y mensajes. No recibe ni devuelve nada.


Dado el mismo conjunto de requisitos, más módulos significa menor tamaño individual del módulo. Sin embargo, a medida que crece el número de módulos, el esfuerzo asociado con la integración de módulos también crece. Esta características llevan a una curva del coste total. Hay un número, M, de módulos que resultaría en un coste de desarrollo mínimo pero no tenemos la sofisticación necesaria para predecir M con seguridad
\[Pressman,93\]
![[Pasted image 20230921222403.png]]

Si intento integrar todo en un modulo, ves que los costes de módulo tiene ese módulo es tiende hacia infinito. En cambio, si separo demasiado, es decir en muchos módulos, vemos que el coste de integración tiende a infinito.

La linea discontinua sería la suma de los dos costes en ese punto, como vemos, lo mejor es un punto medio.
(Supuestamente no es muy bueno Pressman, pero esta cita es muy acertada)



### METODO DE HOOD(simplificación extrema)
El método propuesto es una simplificación extrema y variación de HOOD(Diseño orientado a objetos jerarquicos). El resultado es un método muy sencillo y utilizable en pequeñas aplicaciones.
Este metodo tiene 5 Fases:
1. Tomar una clase
2. Definir el comportamiento
3. Definir los atriburos
4. Codificar los métodos
5. Recapitular nuevas clases y métodos

Recuerda que para estos tiene que ser pequeño el programa.

Cuando creas atributos y métodos, tienes que imaginar objetos de otras clases que "creo" que ya existen, y en base a lo que crea que necesitan los mensajes. 

Después hago las Clases que había imaginado, cogiendo mejor la parte que más miedo me de, ya que esa puede afectar a mi programa si no se del todo como se hace, a esto se le llama **gestión de riesgos**


### Ejemplo de 3 en raya
Recordando partir en cachos y inspirarte en la realidad, partiendo el código en objetos que hay en la realidad.

Cosas que puede tener un 3 en raya:
- Tablero
- Jugadores
- Turno

![[Pasted image 20230921225032.png]]

Y seguir desarrollando esas clases de la misma manera que hemos hecho con esta.