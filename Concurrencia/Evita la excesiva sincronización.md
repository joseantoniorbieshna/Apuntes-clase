Hemos visto la falta de sincronización[[Importancia de Syncronized (atomicidad y volatile modifier)]], ahora vamos a ver el caso contrario, el exceso de sincronización.

Dependiendo de la situación, la exesiva sincronización puede causar una reducción del rendimiento, bloqueos o incluso comportamiento no deterministas.


para evitar fallos de vivacidad(liveness) y fallas de seguridad(safety failure), nunca debes ceder el control al cliente dentro de un método o bloque sincronizado.
En otras palabras, dentro de una región sincronizada, no invoques un metodo que está diseñado para ser override, o una dado por el ciente en forma de objeto función. Desde la perspectiva de la clase con región sincronizada, estos metodos son alien(No tiene ni conocimiento, ni control de lo que hacen). Si llamas a un método alien, dependiendo de lo que haga, puede ocasionar excepciones, bloqueos y corrupción de datos.

para hacer esto concretamente, considera utilizar un set Observable, permite al cliente suscribirse a notificaciones, cuando se agregan elementos al set.
![[Pasted image 20231201001139.png]]
![[Pasted image 20231201001454.png]]

El observador se suscribe a las notificaciones invocando el metodo addObserver y desuscribiendose invocando el metodo removeObserver. En ambos casos, se pasa al metodo una instancia que implementa la interfaz calback.
![[Pasted image 20231201002650.png]]

