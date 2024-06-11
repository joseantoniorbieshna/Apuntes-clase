### ANOTACIONES A NIVEL DE CLASE
@Entity
@Component
@Repository

### ANOTACIONES A NIVEL DE ATRIBUTO
@AutoWired
@Id
@GeneratedValue(strategy = GenerationType.AUTO)

### ANOTACIONES DE RELACION
@OneToOne
@ManyToOne
@ManyToMany
@ManyToMany(targetEntity = Persona.class)

//sirve para que vaya guardando y haciendo las cosas en cascada
@ManyToMany(**cascade = CascadaType.ALL**) 

// Cuando haces cualquier tipo de consulta, **te trae todo**(eager es ansioso)
@ManyToMany(**fetch = FetchType.EAGER**) 

// Mapeas esa relación y le dices que ya existe en otro sitio(Para que no te cree otra tabla si ya tienes esa relación en otra parte)
@ManyToMany(**mappedBy = "jugadores"**) 
### De controlador
//en el parametro del método, localhost/controlador/**1** ese 1 sería el pathVariable, que puedes cambiar el tipo poniendo string u otra cosa
@PathVariable 

//Le pasas el objeto por el body
@RequestBody
//Le pasas por parametro
@RequestParams

### Añadir Beans
Creamos una clase con la anotación
@Configuration
En el método donde lo pillas ponemos @Beans

### Validaciones
HAY QUE IMPORTAR LA DEPENDENCIA "Validation".

@NotNull
@NotEmpty
@Size
@Min
@Max
@Valid -> En el endpoint, en el parametro(Se valida antes de entrar al método)
#### Comprobadores expecíficos
@Email
@NotBlank
@Url
@CreditCardNumber
@DecimalMin
@DecimalMax
@Digits
@Positive
@Negative
@Future -> Sobre fechas
@Past -> Sobre fechas
@Pattern(regexp=" ") -> Regex

