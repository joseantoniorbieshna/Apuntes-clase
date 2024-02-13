### ORM (Object Relational Mapping)
Al objeto DTO que se corresponde con una tupla de db se le suele llamar **entidad**, es decir, si un DTO, tiene la misma forma que la tabla de la base de datos se le llama **Entity**.

**Nota:** La nota primaria en JSON, se escribe con un under score \_id por ejemplo.


Tenemos que usar las dependencia Jpa y la base de datos a usar.
JPA: Será la encargada de mapear las bases de datos.
H2: La base de datos a usar

**Nota:** Al iniciarlo como no tenemos servidor TOMCAT se parará.

Instalaremos H2 Console, para poder ver los datos de la base de datos.

En el **application.propierties** pondremos:
```
spring.datasource.url=jdbc:h2:~/Desktop/YakartaNew01
spring.datasource.username=sa
spring.datasource.password=
spring.jpa.hibernate.ddl-auto=create
spring.jpa.show-sql=true
```


Es importante **DESCONECTAR  LA BASE DE DATOS** en la pagina web, si no se cierra el programa SE ROMPE.


Después tendremos que crear el Repositorio, no sería DAO, ya que lo hace todo JPA de Spring.
1. Crearemos **una interfaz del repositorio de la tabla** que se quiere hacer, y extiende de **JPARepository**
2. Para crear un test, la clase del test necesita tener la anotación \@SpringBootTest
3. En el repo de JpaRepository, para hacer metodos nuevos, tienes que crear un nuevo método y donde sucede la inyección, es por el nombre del método(obligatorio **empezar con findBy**). ej: findByPersona(Persona persona)

### Relaciones
@OneToOne
@ManyToOne
@GeneratedValue(strategy = GenerationType.AUTO)

### Anotaciones importantes
- Es importante hacer el hashCode y el equals
- 