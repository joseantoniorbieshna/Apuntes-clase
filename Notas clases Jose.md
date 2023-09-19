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
>Invención pura: Es cuando creas una clase, que no es totalmente necesaria, para mejorar el acoplamiento y la cohesión.

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





# Clase Acceso a Datos
Hay diferentes tipos de if

SI en una lambda quiero hacer referencia a un metodo existente, ya sea estatico o no,
se utiliza **::**

Ejemplo: Float::valueOf;




