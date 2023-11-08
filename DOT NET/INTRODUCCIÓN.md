ASP.NET es un framework para crear paginas web.

### Regla de ruteo
Se aplica en cascada, si no se aplica esa regla de ruteo, se pasa al siguiente hasta que haya una coincidencia
![[Pasted image 20231107185752.png]]
### Todos los tipos de Result
**ActionResult:** Engloba todos los tipos de result, por polimorfismo puedes devolver lo que quieras.
(Suele utilizarse cuando depende del usuario puede devolver una cosa u otra y no son del mismo tipo, dando mayor flexibilidad)

Los siguientes obliga a que sea del propio tipo indicado (Es decir siendo más especifico):
![[Pasted image 20231107190749.png]]
Fuente: https://learn.microsoft.com/en-us/previous-versions/aspnet/dd493064(v=vs.118)

Anotaciones importantes :
- Si quieres devolver un **Json**  utilizando **JsonResult** en un get request, tienes que ponerse por parametro, indicandole: JsonRequestBehaviour.AllowGet
- Si quieres utilizar HttpStatusCodeResult, tienes que devolver new HttpStatusCodeResult(codigoEnNumero, opcionalDescripcionMensaje);
- Para los archivo, existe Server.MapPath("Ruta")

Normalmente cuando tienes que indicar el tipo se pone "application/pdf" o "application/json", como ves solo cambia lo del final.


### Query String
![[Pasted image 20231107193403.png]]
Si quieres más de un valor se utiliza para separa el símbolo: &
![[Pasted image 20231107193446.png]]
Hay que tener mucho cuidado con esto, ya que hay algunos valores que no permiten nulos
![[Pasted image 20231107193812.png]]
![[Pasted image 20231107193827.png]]
En este caso edad es un entero y no puede ser nulo.

### METODOS ESPECIFICO GET Y POST
Tienes que utilizar arriba del método:
\[HttpGet\] o \[HttpPost\]


Normalmente POST se utiliza para cuando te llegan datos desde la página y GET para mostrar la página sin datos o con algún dato sin relevancia por ejemplo avanzando en un catalogo.

### ViewBag Y ViewData
**ViewBag:** Es un objeto especial que nos permite enviar información desde el Action hasta la vista.

Este viewBag se crea y se destruye en cada llamada/método del controller, es decir si creas una variable ViewBag cuando salga del método se destruye.

Para entender mejor el Viewbag voy a explicar el siguiente concepto:
ViewBag es dynamic, la palabra clave dynamic le permite usar variables que no tienen un tipo específico, en cambio, actúan como el tipo de datos que contienen.
![[Pasted image 20231107195936.png]]
Véase este ejemplo y observa bien el objeto anónimo.

**ViewData:** Sirve para hacer lo mismo pero con otra sintaxis.
Ejemplo:
ViewData\[\"PalabraClave\"\] \= \"Esto es un mensaje de ViewData\"\;

### Vistas
En un documento cshtml puedes mezclar codigo c# y html, este archivo utiliza una sintaxis razor(mezcla c# y html en el mismo).

La vista no tienes que tener mucha lógica, ya que esta se debería solo de encargarse en mostrar los datos al usuario.

Para comentarios en razor: @\*Comentario\*@

##### Explicación Layot Design o pagina de diseño
![[Pasted image 20231107202314.png]]
En ingles: Use layout page.

Cuando marcas esa opción, le estas diciendo que la vista se cargará primero en View/Shared y el archivo por defecto \_Layout. En algún momento de ese archivo se cargará la vista que acabamos de crear.
![[Pasted image 20231107203225.png]]
Esta pagina de diseño se utiliza cuando las páginas comparten el mismo contenido, por ejemplo un menú de navegación, footer...

Donde se carga la vista dentro de esta página de diseño es en la llamada al método: **RenderBody()**

El layout que se carga en todos se indica en View/\_ViewStart, de todas formas en cada Vista, podemos definir con codigo C# que layout queremos cargar ejemplo:
@{
	layout=null; //Aquí lo quitariamos
}
##### Carpeta Shared
Views/Shared, es una carpeta especial, donde se colocan los recursos compartidos que pueden utilizar cualquiera de las otras vistas.

##### Escribiendo Código en la vista
Si viene algún dato del controller hay que indicarle con:
>@model TipoDatoQueEntra o @model List\<TipoDatoQueEntra\>

**Nota:** si queda con muchos puntos al indicarle el tipo de dato, se pude cambiar en el web.config (No testeado)
##### Anotaciones HTML
Vease: [[HTML NOTACION | HTML metodos]]
