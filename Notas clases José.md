# PROGRAMACIÓN DE SERVICIOS
>Propiedades privados tienen getter y setter
>Atributos públicos

Grasp
>Experto en información:
>alumno.expediente.algo.tal está mal no es aconsejable
>
>No sigue este principio debería de preguntar a alguien que se encarga de esto.
>
>explicar más detallado
>
>**Invención pura:** Es cuando creas una clase, que no es totalmente necesaria, para mejorar el acoplamiento y la cohesión.
>
>**Principio del controlador:** Separación del código que controla las clases, en vez de meterlo en la clase, hace una llamada al controlador, para que si cambia unas de las clases, no necesiten cambiar las demás, si no que solo el controlador.
>
>**El principio Creador:** (habla de la Factoria)
>
>**Principio de Indirección:** A y b se conecta, pero no quieres que se conecten, entonces haces una clase en el medio para esa comunicación.(Ejemplo 2 personas de distinto idioma, en el medio hay un traductor)
>
>**Polimorfismo:** Múltiples formas. (downCasting y upCasting)(dijo de que hablaria más adelante de los ValueObject)
>Livskot o/c: 


NOTA: Quien hace el objeto es el que tiene información.

### Granularidad
> Granularidad como de pequeño se puede hacer algo


## COHESION
mide el grado de conectividad entre los elementos de un solo módulo.

**Funcional:** Se encarga de realizar solo una acción(Función)

**Secuencial:** Por ejemplo A hace algo y B utiliza a A

**Comunicacional o de datos:** A y B utilizan los mismos datos por lo tanto si se utiliza A modificaría el resultado de B y viceversa.


**Temporal:** Tienen que ser ejecutadas al mismo tiempo
**Procedimental:** Cuándo no existe relación entre los módulos del bloque más que la de ejecutarse en un orden concreto.
Ejemplo: En una cocina, hacer cierto procedimiento en orden.
**Lógica:** Cuando varios elementos están juntos porque realizan funciones de la misma naturaleza.
**Coincidental:** No existe ningún tipo de relación, ni excusa para que los módulos estén juntos.

### Acoplamiento

**Normal:** Cuando dos módulos solo intercambian datos.
- Dato: se comunica por parametro por tipo primitivo
- De marca o estampado; Se comunica con una estructura de datos(clase)
- De control: un modulo controla el funcionamiento de otro mediante parámetros de control.


Nota: cuando necesitas los datos, no te queda de otra que estar acoplado con estampado. Cambia sin embargo, si estas acoplado por funciones.


**Cola** LinkedList,
**Conjunto** hashet y treeset(no puede haber un elemento repetido).
**Maps** cada elemento está asociado a un indice.
**Pila** el último que entra es el primero que sale.


# Clase Acceso a Datos
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
YAGNI: YOU AREN´T GOINT TO NEED IT
DRY: DON´T REPEAT YOURSELF
KISS: KEEP IT SIMPLE, STUPID

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
