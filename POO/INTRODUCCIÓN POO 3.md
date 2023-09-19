**Definir atributos:** Crear objetos de otras clase en las que me apoyo.
- Si el atributo es constante, lo inicializas en la declaración, o pude postergarse la inicialización al constructor.
**Definición de métodos:** es lanzar mensajes a esos objetos en los que me apoyo.

**Ley estricta de Demeter**: cuando yo voy a codificar un método (entre las llaves), yo tengo acceso a atributos de clase, a los parámetros y a las variables locales.

Cuando en un método, devuelvo algo que no sea **void**, la sentencia return \<expresion\>; determina el valor devuelto por el método.


**this**, es una referencia constante que guarda la dirección del objeto que recibe el mensaje correspondiente al método que se está definiendo.
Ejemplo: this.hacerMovimiento();
Sirve para:
- Resolver ambigüedades (colisión de parámetros o declaraciones locales con el mismo nombre)




