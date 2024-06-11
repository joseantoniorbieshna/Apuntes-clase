### ANOTACIONES
**DE CLASE:**
@Document(collection="nombreColección") -> Sería como en @Entity de sql

@CompoundIndexes({
	@CompoundIndex(name="nombre_de_clave",def"{'marca':1,'referencia':5}")
})


**DE ATRIBUTOS:**
@DBRef -> Hace la relación
@Id
@Indexed(unique=true)
### Configuracion
```
spring.data.mongodb.host=localhost
spring.data.mongodb.port=27017
spring.data.mongodb.database=harnina01
```


### MongoTemplate class
1. Haremos Autowired a la clase MongoTemplate
2. getCollection("nombreColección") y trabjar sobre esta poniendo por ejemplo:
- drop()
Quedaría: 
MongoTemplate.getCollection("nombreColección"). drop()


### Clave compuesta
**Nota:** Al crear el repository te pide una clave, entonces tendremos que crear una clase para la key