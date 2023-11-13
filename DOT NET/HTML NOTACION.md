Todo lo que empieza por html. se utilizará normalmente en la view.

**Html.Raw():** Queda el código en crudo, pudiendo hacer inyección de javascript o html, llegando a ser peligroso.
**Html.ActionLink():** Te crea un \<a\> con href al action en concreto.

>Html.ActionLink(NombreTexto,Action,Controller)
>Html.ActionLink(NombreTexto,Action,Controller,routeValues,HtmlAttributeValues)

En routeValues y htmlAttributes puedes crear objetos anónimos y le pasas lo que quieras(siempre y cuando esté contemplado).

**Html.RenderAction():** Carga el Action en el momento del código en el cual se llame al método, se utiliza entre @\{\}
>@\{Html.ActionLink(Action);\}

IMPORTANTE
Hay que tener cuidado de poner este renderAction en **el layout general** , ya que si rederizamos un Action que carga **el layout general**, entra en recursividad.

para quitar el layout:
@{
	Lauout=null;
}

Si pones **\[ChildActionResult\]** en el Action/método del controller, de esta manera solo se podrá utilizar con RenderAction o Action.

**Html.Action():** Es igual que renderAction, pero me devuelve el html, en vez de escribirlo directamente, pudiendo llegar a tratarlo.
Este no necesitaria meterlo en un bloque de código c#.

**HTML.DropDownList():**
DROPDOWNLIST, el equivalente al select en html
![[Pasted image 20231112153720.png]]
Dentro de los selectListItem, puedes poner una propiedad Disabled a true, esto te mostraría la opcion pero no podrías seleccionarla.
![[Pasted image 20231112154024.png]]
Recuerda que todo esto no puede estar en la vista, ya que la vista solo tiene que presentar los datos sin casi nada de parte lógica.

**Html.BeginForm():** Se utiliza con using(), sirve para empezar un formulario