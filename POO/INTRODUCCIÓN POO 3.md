# VISTA PRIVADA
**Definir atributos:** Crear objetos de otras clase en las que me apoyo.
- Si el atributo es constante, lo inicializas en la declaración, o pude postergarse la inicialización al constructor.
**Definición de métodos:** es lanzar mensajes a esos objetos en los que me apoyo.

**Ley estricta de Demeter**: cuando yo voy a codificar un método (entre las llaves), yo tengo acceso a atributos de clase, a los parámetros y a las variables locales.

Cuando en un método, devuelvo algo que no sea **void**, la sentencia return \<expresion\>; determina el valor devuelto por el método.


**this**, es una referencia constante que guarda la dirección del objeto que recibe el mensaje correspondiente al método que se está definiendo.
Ejemplo: this.hacerMovimiento();
Sirve para:
- Resolver ambigüedades (colisión de parámetros o declaraciones locales con el mismo nombre)
- Reutilización de métodos en la codificación de otros métodos.
- Para que un **constructor pueda reutilizar el código de otro constructor**, se pone this en la primera linea del nuevo constructor y los argumentos entre paréntesis del otro constructor.

**DRY**(dont repeat yourself) "no te repitas" es reutilizar tu propio código.
### CONSEJO SOBRE MÉTODOS

Es importante saber, que en caso de que no hayas codificado un método pero lo necesites en algún momento, **usarlo, aunque no esté codificado.**

Es normal disponer de **métodos que no han sido solicitados**, para implementar otros métodos, cabe la posibilidad de definir **métodos de ámbito privado** que sólo se pueden usar en la implementación de la clase.

### Regla de estilos
Hay unas reglas de estilos sagradas (Haya donde vayas haz lo que vieres):
- Clases empiezan por mayúsculas
- Los parámetros, los atributos y los métodos, no empiezan por mayúsculas

