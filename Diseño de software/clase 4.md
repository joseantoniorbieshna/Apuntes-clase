**Cohesión:** la medida de como de fuerte están relacionadas y enfocadas las responsabilidades que son de un elemento.

**Acoplamiento (dependencia):** Es el grado del que yo dependo de otro.
El problema de depender de otros, es que si ellos cambiar me repercuten a mi.(por ejemplo si cambia la interfaz de la clase)
Hay de 2 naturalezas:
- A los que lanzo mensajes
- A los que heredo


**Invención Pura:** Hay muchas situaciones en las que la asignación de responsabilidad solamente a las clases de software de la capa de dominio da lugar a problemas en cuanto a escasa cohesión, elevado acoplamiento o bajo potencial de reutilización.

La solución es asignar un conjunto altamente cohesivo de responsabilidades a una clase artificial o de conveniencia que no representa un concepto(algo dominio del problema).

En resumen: sería una clase creada por mi, para facilitarme la programación, trabajando así más a alto nivel.




**Un ejemplo de única responsabilidad.**
La clase Board, solo tiene la responsabilidad de gestionar el tablero, no pregunta nada al usuario.
La clase Player sería la encargada de preguntar al usuario.

Encontrar un equilibrio etntre
**YAGNI:** You aren´t goint to need it
**interfaz suficiente, compleja y primitiva**


**Principio de menor sorpresa y menor compromiso**, no hagas algo que no se indique en el nombre del método.

**UN MÉTODO SOLO TIENE QUE HACER UNA UNICA COSA**


**Cirugía a escopetazo**
No tener raw un numero, porque no vas a saber si ejemplo un 3, es de el tamaño del tablero, o el turno del jugador, o el volumen...
Se le pone en variables, así cuando le tengamos que cambiar, solo hará falta cambiar una variable, además que a la hora de leerlo quedará más claro.
Ejemplo, cambiar de 3 en raya a 4 en raya.

**Obsesión por tipos primitivos**
No hay que obsesionarse con los tipos primitivos, si puedo hacer un objeto, se hace un objeto, eso si. 
- si no tiene comportamiento y solo tiene getter y setter no se hace objeto.

Cuando hay más de 3 parámetros, estaría mal, y se dice que es una **lista de parámetros larga**

Cuando hay **grupo de datos**. normalmente es un objeto.
Ejemplo fila, columna, se podría hacer Coordenada.

**DRY, dont repeat yourself**

**WET,  we enjoy typing.** te repites(esto es MALO)


**Kiss, Keep it Simple Stupid**


Hay que dar responsabilidades a las clases tontas:
![[Pasted image 20231222173445.png]]
Es decir, a las clases tontas, que solo tienen get y set, con imaginación, hay que darle responsabilidades.

Además, siempre me va a costar leer menos 4 clase de 60 líneas, que una clase de 240 líneas.


Como saber si tengo que crear otras clases:
- Cuando una clase excede de 300 lineas(Hay que empezar a partirla)
- Cuando una clase se te queda con solo get y set, piensa como dar responsabilidad. (Mirando en la clase grande donde hay envidia de características. Es decir, "donde hay muchos get y set en la otra clase") 



## Diseño por contrato
**Fallo:** Es cuando el sistema no cumple los requisitos(Se aparta de su comportamiento específico).
**Defecto:** Es la propiedad de un sistema donde puede haber un fallo.

Tipo de errores:
- **Errores excepcionales:** Están fueras del limite de tu ámbito de software(conexión, fichero...)
- **Errores Lógicos:** Cuando haces algo mal dentro de tu código (inicializar mal un contador, recorrer mal un bucle...).

**La robustez**, es la capacidad del software de reaccionar a casos no incluidos en la especificación.

Hay diferentes maneras de conseguir esto:
**Programación defensiva(Mala práctica):** Lo primero que comprueba es, si el número es negativo, saca un error por pantalla. 
- (Está mal, ya que si sacas un error por pantalla, y la pantalla es gráfica  no saldrá o saldrá por el servidor).

- Otro error:
	Si es negativo, devuelvo -1 (Esto también está mal). Ya que si está dentro de las posibilidades, no podrías tirar de este mecanismo, además dentro de todos los que llaman a este, tendrían que comprobar que esto no se cumple.


![[Pasted image 20231224152205.png]]
Es importante poner en la **VM -ea** para activar los assert(enable assert)

Diseño por contrato: Si por ejemplo un método funciona sin null, no controlarlo dentro de ese método, si no en el qué lo utiliza(cliente), porque si no estarías haciendo algo que no le corresponde al método.

Esto tiene una ventaja, ejemplo, si quisiéramos hacer esto mismo con excepciones, habría que obligar al cliente a tener try catch.

Para simplificarlo sirve para cuando estamos desarrollando, que el programa pete si no se le está pasando algo que no debías, para que este mismo que lo llama corrija lo necesario.

