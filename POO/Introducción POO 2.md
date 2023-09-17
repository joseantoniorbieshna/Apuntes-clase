**Comentarios:**
\/\* Cualquier cosa en medio es comentario,
aunque esté en varias líneas\*\/
\/\/ Es un comentario de una sola línea

En todos los lenguajes hay palabras reservadas, que pertenecen al propio lenguaje.
Ejemplos de palabras reservadas en java:
final, if, while...
### Tipos primitivos:
**Enteros:** representas números enteros positivos y negativos con distintos rango de valores.
(byte,short, int y long.)
**Reales:** representan números reales positivos y negativos con distintos grados de precisión.
(float y double)
**Lógicos:** representa un valor lógico (booleano)
**Caracteres:** representa un único carácter unicode
(char)

Es importante elegir bien que tipo primitivo usar, porque no todos ocupan el mismo espacio en memoria.

#### Declaración de variables
**Variables:** son reservas de memoria estática que pude almacenar en cada instante uno de los valores de un cierto tipo primitivo.

Se declaran:
\<Tipo> \<Nombre Variable> ;
o
\<Tipo> \<Nombre Variable> = \<expresión>;

**El nombre de la variable** debe ser significativo, sin abreviaturas y debe ser en minúsculas salvo cuando se produce un cambio de palabra, donde la primera letra de la nueva palabra será en mayúsculas.
Ejemplo: Int contadorAlimentos;
#### Declaración de constantes
**Constantes:** son reservas de memoria estáticas que puede almacenar un único valor de un cierto tipo primitivo dado en su inicialización.

Se declaran:
final \<Tipo> \<Nombre Variable> ;
o
final \<Tipo> \<Nombre Variable> = \<expresión>;

**El nombre de las constantes** debe ser significativo, sin abreviaturas y debe ser en mayúsculas separándose con un subrayado cuando se produce un cambio de la palabra;
Ejemplo: final String DIRECCION_IP;

#### Operadores
**Operadores aritméticos:** operan sobre los valores numéricos del mismo tipo y te devuelve un valor del tipo de los operando.
Es decir si utilizas int, te devuelve int.
\+ Devuelve las suma de operador1 y operador2
\- Devuelve la resta de operador2 y operador1
\* Devuelve el producto de operador1 y operador2
\/ Devuelve el cociente de operador1 entre operador2
\% Devuelve el resto de operador1 entre operador2


**Operadores relacionales:** operan sobre dos valores lógicos y devuelven un valor del tipo lógico.
\> Devuelve True si operador1 es mayor que operador2
\< Devuelve True si operador 1 es menor que operador2
\>= Devuelve True si operador1 es mayor o igual que operador2
\<= Devuelve True si operador1 es menor o igual que operador2
\== Devuelve True si operador1 es igual que operador2
\!= Devuelve True si operador1 es distinto que operador2

**Operadores Lógicos:** operan sobre valores lógicos y devuelven un valor tipo lógico.
&& Devuelve True si ambo operadores son ciertos
|| devuelve True si algún operador es cierto
! Devuelve el valor Negado.

### Conversiones de tipo
Cuando hay dos operando y uno es de un tipo y otro es de otro.

Existe diferentes tipos de conversiones:

**Promoción:** transforman un dato de un tipo a otro con el mismo o mayor espacio en memoria para almacenar información. Este tipo de conversión es implícita.

**Contracción:** Transforman un dato de un tipo a otro menor espacio en memoria para almacenar información con la consecuente posible perdida de información. Este tipo de conversión es implícita.


**Véase también:**
- **Conversión implícita:** Es la que te da el propio lenguaje de fabrica.
(Cuando se combinan dos operandos de distinto tipo, se convierte el de menor precisión, al de mayor precisión)
Ejemplo: 2 * 2.3f, el resultado sería 4.6f, convirtiéndose el int en float automaticamente.

- **Conversión explicita:** Conviertes tú el tipo de dato manualmente.
(promocionas o contraes "lo conocemos por castear" un tipo de dato a otro)
Ejemplo: Int contador = (Int) 5.2f


### Vectores de tipo primitivos
Los vectores son dinámicos, al crear el vector, reservo una zona de memoria,  conozco el tamaño en tiempo de ejecución, pero en tiempo de compilación, no se conoce el tamaño.
(Podrías meterle un random al tamaño y solo lo conocerías en tiempo de ejecución)
Es dinámico en la creación, pero estático en su vida.



sintaxis:
new \<tipo\> \[Numero de elementos\]
o
new \<tipo\> \[\]\{\<expresión\>,\<expresión\>\} 
Aquí le das ya valor dentro del array, además de un tamaño.

**Referencia a un vector de tipos primitivos:** es una variable puntero que alberga la dirección del vector.
\(A falta de inicialización es null\)

![[Pasted image 20230917101006.png]]

Véase también:
**Dirección:** Es una dirección de memoria.
**puntero:** Es una variable que está en memoria y que alberga una dirección.


Ejemplo en java:

1- Creo el puntero o referencia.
>int\[\] enteros = new int\[\]\{3,2,1\}

2- Creo otra referencia, que apunta al mismo sitio.
>int\[\] otrosEnteros = enteros;

3- Si cambio el valor en una de las variables se cambiaria en la otra y viceversa.
>enteros\[0\] = 5;
>System.out.println(enteros\[0\]) -> 5
>System.out.println(otrosEnteros\[0\]) -> 5

4- Se libera la memoria automaticamente cuando ninguna referencia apunta al vector
>enteros = null;
>otrosEnteros = null;

### Programación orientada a objetos
**Vistas:**
- **publico:** Se conoce en cualquier punto de la aplicación.
- **privado:** Se conoce únicamente en el ámbito de la clase.

#### VISTA PUBLICA DE LOS OBJETOS
**Interfaz:** nombre de la clase y cabecera de los métodos.
Lo que puedes hacer es:
- Creación de objetos
- Paso de mensajes
- Destrucción de objetos
#### VISTA PRIVADA DE LOS OBJETOS
**Implementación:** Definición de atributos y definición de métodos
Lo que puedes hacer es:
- Desencadenamiento de objetos
- Desencadenamiento de mensajes


#### VISTA PUBLICA DE LA CLASE
**Sobrecarga de métodos de la clase:** Varios métodos pueden tener el mismo nombre en una clase, siempre y cuando, tengan un numero o tipo de parámetros diferente.
Luis Fernández afirma, que la sobrecarga no es una posibilidad, si no, una obligación. 
(No puedes tener una clase con un metodo add, otro annadir y otro annadir2, esto lleva al caos)


**Constructores de la Clase:** Son métodos que reúnen las tareas de inicialización (no construyen) y se lanzan automáticamente en la construcción de objetos.(En otros lenguajes se le llama "init")

El que realmente construye es la palabra reservada "new".


**Destructores de la clase:** Son métodos que reúnen las tareas de liberación de recursos(no destruyen) y se lanzan automáticamente en la destrucción de objetos, sirven para liberar memoria dinámica. 
Es importante saber que:
- Su cabecera es: public static void finalize()
- No se pueden lanzar mensajes que se correspondan con los destructores de la clase
Quien realmente destruye es el recolector de basura de java (garbage collector) y lo hace automáticamente.


**Creación de objetos:** new es un operador unario prefijo cuyo operando es una clase de objetos y devuelve la dirección de memoria donde se ha reservado el espacio para dicho objeto.

hora 2:08

**String:** Son cadenas de texto constantes
**StringBuffer:** Son cadenas de textos dinámicas.