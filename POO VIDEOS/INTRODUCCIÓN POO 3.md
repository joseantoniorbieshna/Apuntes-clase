# VISTA PRIVADA CLASE
**Definir atributos:** Se trata de crear objetos de otras clase en las que me apoyo.
- Si el atributo es constante, lo inicializas en la declaración, o puede postergarse la inicialización al constructor.
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

**Principio de encapsulación:** Solo se da a conocer lo que estrictamente se necesita dar a conocer.
### CONSEJO SOBRE MÉTODOS

Es importante saber, que en caso de que no hayas codificado un método pero lo necesites en algún momento, **usarlo, aunque no esté codificado.**

Es normal disponer de **métodos que no han sido solicitados**, para implementar otros métodos, cabe la posibilidad de definir **métodos de ámbito privado** que sólo se pueden usar en la implementación de la clase.

**Esto es muy importante:**
Si yo tengo una clase hecha, con sus getters y setters, **debería** dentro de mi clase, **llamar a esos getter y setter, en vez de tocar los atributos**, porque si en un momento, cambio los atributos(por cualquier motivo), tendría que retocar todo el código, de la otra manera, solo tendría que recodificar los getters y setters afectado, y el código seguiria funcionando igual.
### Regla de estilos
Hay unas reglas de estilos sagradas (Haya donde vayas haz lo que vieres):
- Clases empiezan por mayúsculas
- Los parámetros, los atributos y los métodos, no empiezan por mayúsculas

### MIEMBROS DE INSTANCIA
Son esos que están en cada uno de los objetos sin compartir nada:
- atributos presentes en cada uno de los objetos de la clase
- métodos cuya mensaje se lanzan sobre un objeto particular
### MIEMBROS DE CLASE
Responden a una necesidad de globalidad:
- atributos compartidos por la globalidad de objetos de la clase.
- métodos cuyo mensajes NO se lanzan sobre un objeto particular.

Ejemplo: Personas, tienen una referencia al rey. Si no es global, tendría que ir uno por uno cambiando el rey cada vez que este cambie. En cambio si fuera global, solo lo tendría que cambiar una vez, sin necesidad de instanciarla, ya que pertenece a la clase.

**Atributos estáticos:**
- palabra reservada **static**
- su reserva de memoria e inicialización es obligatioria y se realiza al principio de la ejecución del programa.
- accesible desde cualquier método de la clase
- Sintaxis Clase.atributoEstatico

**métodos estáticos:**
- Después de la visibilidad se pone **static**
- No se permite el acceso this, ni a los atributos de instancia.
- se permite el acceso a los atributos estáticos
- sintaxis Clase.metodoEstaico(argumentos);

Está bien aceptado, hacer atributos de clase público, siempre y cuando sea para **sistemas de codificación**
Ejemplo Fecha.DDMMAA->que sería un 1

### OTRAS ANOTACIONES
**Clases de utilidad:** Clases que reúnen un conjunto cohesivo de métodos estáticos. No suelen ser instanciables y no suelen responden al concepto habitual de objetos.

**Pruebas de clase:** Toda clase de java puede tener un método mágico que es **public static void main(String args\[\])** , donde se utiliza para ejecutar el programa. Antiguamente la gente también lo utilizaba para pruebas, pero hoy día está desfasado, se utiliza Junit para hacer pruebas.


**Desencadenamiento de instanciaciones:** Cuando creas un objeto de alto nivel, se crean muchísimo objetos, es casi imposible seguir eso. Quien intenta seguirlo, se dice que incurre al problema del yoyo (ya que le lleva de un lado a otro y de otro lado a otro lado).

Algunas métricas mencionadas son:
- Recomendable métodos de no más de 25 líneas.
- No más de 2 o 3 parámetros por método.

 