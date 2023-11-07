**Html.Raw():** Queda el código en crudo, pudiendo hacer inyección de javascript o html, llegando a ser peligroso.
**Html.ActionLink():** Te crea un \<a\> con href al action en concreto.

>Html.ActionLink(NombreTexto,Action,Controller)
>Html.ActionLink(NombreTexto,Action,Controller,routeValues,HtmlAttributeValues)

En routeValues y htmlAttributes puedes crear objetos anónimos y le pasas lo que quieras(siempre y cuando esté contemplado).

**Html.RenderAction():** Carga el Action en el momento del código en el cual se llame al método, se utiliza entre @\{\}
>@\{Html.ActionLink(Action);\}

IMPORTANTE
Hay que tener cuidado de poner este renderAction en **el layout general** , ya que si rederizamos un Action que carga **el layout general**, entra en recursividad.

Se puede solucionar poniendo **\[ChildActionResult\]** en el Action en el controller, de esta manera solo se podrá utilizar con RenderAction o Action.

**Html.Action():** Es igual que renderAction, pero me devuelve el html, en vez de escribirlo directamente, pudiendo llegar a tratarlo.
Este no necesitaria meterlo en un bloque de código c#.
##### Muestreo de Objetos
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
