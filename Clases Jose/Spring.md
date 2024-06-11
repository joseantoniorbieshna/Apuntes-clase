@springBootApplication -> Es el punto de entrada de la aplicación(Se pone encima de la clase)
@utowired-> inyectas un componente(bean) en otro sitio


INTERPOLACIÓN: cuando pones dos llave **{{variable}}** , esto se pone en la vista, se usa para poder inyectar datos.

Si a una variable pasado por el controller, puede estar o no estar y en base a esto quieres o no mostrar un parte de html se haría de la siguiente manera:
{{#variable}}
	{{-index}} //Te muestra el indice, empieza por el 1
	{{.}} //Recorrerias la variable
{{/variable}}

Por ahora las únicas dependencias usadas son:
- Spring Web
- Mustache

### Eclipse Market Place
Vamos a instalar en el Eclipse Market Place:
- dbeaver
### H2 Y JPA
Para meter una nueva dependencia:
Spring\>Add starter -- Ahí buscamos **H2** 
	Le decimos que nos modifique solo el **pom**
	
Añadimos **Spring data JPA** y lo volvemos a añadir al pom.
Ahora podemos utilizar la inyección \@Entity
Añadimos al application.propierties:
	spring.jpa.show-sql=true

**Nota:** Si a cualquier dependencia instalada, queremos que sea una versión específica, tenemos que añadir una etiqueta llamada dependencia con el número de la versión dentro de la etiqueta.
```
<version>2.5.3</version>
```

### Archivos y cosas Importantes
En el aplication.properties añadimos:
```
spring.mustache.prefix=classpath:/templates/

spring.mustache.suffix=.html
```

Archivo **banner.txt**, este permite poner un banner personalizado a Spring, se tiene que meter en la carpeta resources.
### HTTP
**GET:** Es **idempotente** (Solo deben recuperar datos y no deben tener ningún otro efecto.
**HEAD:** Le pasas la información por el head, en vez del body
**POST:** Para meter "publicar informacion" (**No es idempotente**, ya que puede tener (id por ejemplo, o la fechaActual...)
**PUT:** Para actualizar información
**DELETE:** Sirve como indica el nombre para borrar información.


**Recurso o endPoint:** es un elemento que satisface una petición http.
### Buenas prácticas
En el controller, es buena práctica que el atributo sea static y que se inyecte en el contructor, en vez de poner autowired.
