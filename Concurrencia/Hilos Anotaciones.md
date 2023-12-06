Estados:
- new o creado
- runnable(cuando el hilo hace su tarea)
- Timed_Waiting (esperando tiempo limitado)
- Blocked (Si dos hilos están intentando utilizar una camara web por ejemplo, uno va a estar bloqueado hasta que el otro termine)
- Waiting(Está esperando de manera indefinida hasta que otro lo despierte)
- Terminated


Se puede ver el estado del hilo poniendole getstate() al hilo




El principal problema ocurre cunado 2 o más hilos intentan modificar o leer una variable al mismo tiempo, a esto se le conoce como **condición de carrera** y se puede producir inconsistencias en los datos.
