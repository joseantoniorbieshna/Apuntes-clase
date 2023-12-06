>Propiedades privados tienen getter y setter
>Atributos públicos

# GRASP
>**Experto en información:**
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


NOTAS: 
- Quien hace el objeto es el que tiene información.
- El object mother sería como coger datos de una base de datos.
- El controlador, no sabe hacer nada, pero conoce a todo el mundo que sabe hacer cosas


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

METODOS INTERESANTES
Instant.now
Duration.between(instante1,intante2)

1-Hacemos la parte que no tiene hilos
2-Hacemos test de la parte sin hilos
3-Cuando el paso anterior esté correcto, Creamos la parte de hilos
4- Hacemos test de la parte de hilo
5- SI no funciona los test, hacemos trazas en los diferentes actores(Objetos el cual sea hilo o lo pueda modificar)


CALLABLE PUEDES HACER FUTURE
RUNNABLE