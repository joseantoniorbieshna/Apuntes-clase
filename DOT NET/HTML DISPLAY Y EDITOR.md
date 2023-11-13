##### Muestreo de Objetos/DISPLAY TEMPLATES
**Html.Display():** Se le pone el texto de la propiedad pasada por el ViewBag, y muestra los objetos en texto plano.(Pertenece a html helper).

Ejemplo:
@{
ViewBag.Propiedad= new Persona("Claudia",35,true,new DateTime(2015,1,23));
}
@Html.Display("Propiedad")

![[Pasted image 20231107215930.png]]

Se puede cambiar el tipo de muestreo de fábrica creando una carpeta "Display Templates" dentro de la carpeta de la vista concreta, vas a crear una vista para ese dato y le vas a quitar la opción de layout page.
![[Pasted image 20231107220903.png]]
 Le vas a indicar que del @model te va a venir un Boolean por ejemplo:
![[Pasted image 20231107220842.png]]

En el caso de que quiera que se aplique a todos, la debería de mover a la carpeta Shared.

HTML CON LAMBDAS
**Html.LabelFor(lambda)**: le digo que voy a crear un label de la propiedad que seleccione del objeto en la lambda.
**Html.DisplayFor(lambda)**: Hace lo mismo que el display, pero le indicas por lambda lo que va a sacar.
#### Template de editor
**Html.Editor():** Sería como el html.display, por parametro se le pone entre comillas la variable pasada por viewbag


De la misma manera que display tiene un template, editor también le tienes que crear una carpeta template y como nombre de la vista tiene que ser el tipo.
![[Pasted image 20231112152429.png]]

EJEMPLO:
![[Pasted image 20231112153353.png]]

