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
