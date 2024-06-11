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


### ID DE VARIAS TABLAS
Si necesitamos una key de varios tablas, se hace una clase donde obtenga varios objetos y tiene que ser SERIALIZABLE. Y en la clase donde está la relación, hay que poner la etiqueta: @IdClass(PacienteQuirofanoCirujanoKey.class)
Y en cada campo que esté en la clase, en la clase de la relación hay que poner @Id

**En la relación poner CASCADE.ALL, para que cuando inserte sin ser la misma referencia, guarde.**

### Mocks
@MockBeans -> Son objetos que no existen, no se comportan de ninguna manera.
				Hay que utilizar when
@InjectMocks -> Tiene que ir con @autowired y tiene que ser una implementación concreta.


### Crear tu propias reglas
find o delete -> Luego podemos (opcional) poner first, first %num%


### Configuración MySql
```
spring.datasource.url=jdbc:mysql://localhost:3306/usuarios
spring.datasource.username=root
spring.datasource.password=

spring.jpa.hibernate.ddl-auto=create
spring.jpa.show-sql=true
spring.jpa.properties.hibernate.format_sql=true
```