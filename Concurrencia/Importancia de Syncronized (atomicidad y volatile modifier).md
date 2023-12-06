La especificación de lenguaje garantiza que la lectura o escritura de una variable es atomica al menos que la variable sea de tipo long o double. En otras palabras, al leer una variable que no es de tipo long o double, se garantiza que se devolverá un valor que fue almacenado en esa variable por algún hilo, incluso si varios hilos modifican la variable de manera concurrente y sin sincronización.

Considerar detener un hilo desde otro. Thread.Stop es inherentemente inseguro, su uso puede dar lugar a la corrupción de datos

La forma recomendada de detener un hilo desde otro es hacer que el primer hilo consulte un campo booleano que inicialmente está en falso, pero que puede ser establecido en verdadero por el segundo hilo para indicar que el primer hilo debe detenerse. Debido a que la lectura y escritura de un campo booleano es atómica, algunos programadores prescinden de la sincronización al acceder al campo

![[Pasted image 20231130082544.png]]
Aquí hay un problema, y es que va a estar en el bucle infinitamente

El problema es que en ausencia de sincronización, no hay garantia de que el hilo secundario vea el cambio en el valor stopRequested hecho in el main.

Es normal que la maquina virtual de java transforme este codigo:
![[Pasted image 20231130082628.png]]
Esta optimización de la máquina de java es conocida como hoisting(Es lo que OpenJDK Server VM hace)
El resultado es un fallo en la vivacidad(Liveness)

LiveNess: La "vivacidad" (o "liveness") en este contexto se refiere a la capacidad de un sistema para ejecutarse de manera continua y realizar progresos, evitando bloqueos, inanición u otros problemas que podrían hacer que el sistema se quede estancado.

Una manera de solucionarlo sería:
![[Pasted image 20231130082722.png]]
mira que los dos tanto el metodo de lectura como el de escritura están sincronizado. No es suficiente con sincronizar el método de escritura. La sincronización no está garantizada al menos que el metodo de lectura y escritura estén sincronizados.

si sincronizas solo un metodo(lectura o escritura) puede parecer que funciona pero esta apariencia sería engañosa.
La accion de sincronizar metodos en stopThread es atomica incluso sin sincronización. **En otras palabas la sincronización en este metodo es usado solo para la comunicación, no para la exclusión mutua**

**La exclusión mutua** es como una regla que evita que varias partes de un programa se entrometan al mismo tiempo.

El syncronice es costoso , veamos una alternativa menos verbose y con mejor rendimiento

El bloqueo en esta version puede hacerse si stopRequested se declara como volatile. Mientras el comportamiento del modificador volatile no tiene exclusión mutua, este garantiza que cualqueir thread que lea el campo verá el valor escrito más reciente
![[Pasted image 20231130082855.png]]

Pero hay que tener cuidado con usar volatiles, vamos a poner un ejemplo:
![[Pasted image 20231130083028.png]]
La intención de este metodo es garantizar, que cada vez que se llame, te devuelva un valor unico

El comportamiento del método se construye con un campo atómico, entonces la sincronización no es necesaria para protegerlo de invarianzas. No obstante, no funcionará correctamente sin sincronización.
El problema es el operador incrementar(++), no es atómico(Ya que estás leyendo el valor en ese momento y escribiendo el valor leido anteriormente y sumándole uno, por lo tanto hay 2 acciones)

Si un segundo hilo lee el campo en el tiempo que otro hilo está leyendo el antiguo valor y escribiendo el nuevo, ambos tendrán el mismo numero

Y esto sería una gran falla, una forma de corregirlo sería añadir el modificador syncronized
Ya no sería necesario el modificador volatile en este caso (editado)



Mejor todavía sería utilizar la clase atomicLong, la cual es parte de las clases de utilidades de concurrencia de java. Este paquete proporciona primitivas para la programación libre de bloqueos y segura en hilos.
Mientras que volatile, solo te da los efectos de comunicación de la sincronización.

Con el paquete anteriomente mencionado mejorariamos el rendimiento, aquí un ejemplo;
![[Pasted image 20231130083227.png]]
**La mejor manera de evitar este problema sería, no compartir datos mutables, compartiendo solo imutables o no compartirlos del todo. En otras palabra, limita los datos mutable a solo un hilo.**

Es aceptable que un hilo modifique un objeto por un momento y después compartilo con otros hilos, sincronizando solo el acto de compartir la referencia del objeto, siempre y cuando no se modifique otra vez. podríamos llamarlo inmutable.
Pasar una referencia de un objeto de esta manera, de un hilo a otro, se llama "publicacion segura(safe publication)"


Maneras de hacer una publicación segura, algunas son: 
1. guardarlo en un campo estatico
2. guardarlo en un campo volitle 
3. en un campo final 
4. un campo normal, que es accedido con un bloqueador(synchronized) 
5. Una lista concurrente

En resumen, cuando multiples hilos comparten datos mutables, cada hilo que lee y escribe el dato debe llevar syncronización(si no se hace, no hay seguridad de que los demás hilos vean el cambio)

