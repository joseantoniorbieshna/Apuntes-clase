Hay diferentes tipos de if

SI en una lambda quiero hacer referencia a un metodo existente, ya sea estatico o no,
se utiliza **::**

Ejemplo: Float::valueOf;



### AÑO PASADO REPASO
NOTAS: VERSATILIDAD, PRIVACIDAD Y TEMPORALIDAD
**Dependencias:**
- uso
- asociación
- agregación
- composición
- implementación
- Herencia

POJO: plain old java object, lo llaman objeto tonto, sirve para transladar de una base de datos a java

### CODIGO LIMPIO
NO TENGAS CÓDIGO MUERTO
**YAGNI:** YOU AREN´T GOINT TO NEED IT
**DRY:** DON´T REPEAT YOURSELF
**KISS:** KEEP IT SIMPLE, STUPID

**Bibliotecas:** conjuntos de clases e interfaces que permiten las solución de una categoría de problemas.

Menos compromiso: Se debe de poner solo lo esencial.
Menor sorpresa: No puede hacer dos cosas un método.
Cohesión de métodos: 

**NO** obsesionarse con los **tipos primitivos**.

El **número de parámetros** ideal es 0,1 o 2.

**COMPLEJIDAD CICLOMATICA** (RECORDARSELO A JOSE)
Mide la complejidad de un algoritmo 

**No** se deben tener **métodos largos**, debe tener entre 10-15 como general, pero puede tener un poco más o menos, 80-120 caracteres.


**ENVIDIA DE CARACTERÏSTICAS**
Esto ocurre cuando un método que necesita de muchas propiedades o métodos que se encuentran en otro objeto.
Esto quiere decir que igual no debería de estar ahí

**DISEÑO POR CONTRATO**


**ERRORES**
Excepcionales: Cuando no depende de ti, por ejemplo una base de datos.
Lógicos: EL programador es el que tiene el error.


**NO A LAS CLASES GRANDES**
3-5 atributos
20 métodos

**HERENCIA RECHAZADA**
Cuando la clase derivada no utiliza métodos de la clase padre.

**INTIMIDAD INAPROPIADA**
Ya hemos hablado, cuando hay más de dos puntos, nos estamos equivocando.

### SOLID
Propuesto por Tío Bob.
Es importante entender el problema, para entender estas soluciones.

Principio: Idea fundamental de algo.

Son los siguientes principios:
**SINGLE RESPONSABILITY:** principio de responsabilidad única
**OPEN/CLOSED:** un software que funciona, está cerrado a modificación y abierto para su extensión
**INTERFACE SEGREGATION: **
- Es mejor tener 5 interfaces de 1 método, que 1 interfaz grande.

NOTA: CUANDO DIGO INVERSIÓN, es que es otro el que lo hace
**INVERSIÓN DE DEPENDENCIA:** Una clase no debería de depender de una implementación, si no de una abstracción.
(Inversión de dependencia, yo ya no dependo, le doy la vuelta a la dependencia.)
- Las de nivel más bajo, son las que no dependen de ninguna otra.
**INYECCIÓN DE DEPENDENCIA:** Desde fuera le digo que implementación sobre esa clase abstracta voy a tener, pero desde dentro, le da igual que haya.
	**Características:**
	- Al usar la inyección, varios objetos B, pueden utilizar 1 mismo objeto A(comparten el objeto)

**INVERSIÓN DE CONTROL:** Es el propio programa el que controla como se ejecuta. No eres un main, con un montón de cosas que tiene que hacer.
Ejemplo:
	Interface Hook{
		public void onCreate();
		public void onClose();
	}

##### clase i/o
Las writer y reader son de char
las de byte son input y output
 
Buffered, diferentes velocidades(adecuarse a las velocidades, parece que utiliza thread, ya que no se bloquea el programa) 

Ruta canónica: es cuando es absoluta, pero con puntos por el medio, modificando donde estás, yendo hacia delante o atrás.

Para evitar el down casting se utiliza programación parametrizada.

### PATRONES
**FACTORY METHOD:** Cuando son objetos simple, pero en tiempo de compilación no sabes cual te va a crear
**ABSTRACT FACTORY:** Es cuando tienes diferentes tipos de familias de objetos
**BUILDER:** Se utiliza cuando hay valores que se pueden o no especificar. Ejemplo algunos alimentos tienen azúcar y otros 0 azucares.

**Bridge:** Una metafora sería un puente, que une dos orillas, ejemplo mando universal, que puedes cambiar el tipo de tv que es.

Nota: si no puedes cambiarlo con un set es bridge, si lo puedes cambiar en tiempo de ejecución con un set sería **strategy**.

**Adapter:** Es como la corriente y un cargador, donde la entrada de la corriente entra algo, se transforma en el medio y sale la entrada transformada.