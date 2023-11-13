Uso interfaces cuando tenga herencia múltiple,


**PREGUNTAS EXAMEN**

- Si no has puesto autenticación en el proyecto, hay que instalar EntityFramework
- Para tener una conexión a la base de datos necesito un DbContext, si no se pone nada en el conexionString "Parametro del contructor DbContex", utiliza el que tiene embebido.
- AutomaticMigrationsEnabled=true, se hace cambio cuando pongo update-database -force

[Odoo](https://edu-joserb.odoo.com/web#cids=1&action=menu)


Si encima de un metodo o un controller pongo \[Authorize\] solo me permitirá entrar si estoy logeado en todos los actions si lo pongo en el controller y solo en un action si está en un método.
Puedo poner entre paresntesis **Roles** o **User** si quiero que solo entre los que tienen x rol o los queque tengan el user x.

En caso de querer tener una excepcion y que pueda entrar cualquiera, encima del método pondría \[AllowAnonymous\].
