1. Tenemos que poner en la configuracion : @EnableWebSecurity
2. Crearemos un bean de filtro(SecurityFilterChain que obtenga un HttpSecurity por parametro)

### DEPRECATED HTTP BASIC
desactivamos el csrf y activamos el httpbasic
![[Pasted image 20240205090247.png]]
Y te tiene que aparecer:
![[Pasted image 20240205085859.png]]

Cross site Request Forgery(CSRF)


### FORM LOGIN SECURITY (No seguro)
![[Pasted image 20240205091644.png]]
Uno de los ataques posibles sería:
SessionFixation->El usuario fija siempre la misma id.


### JSON WEB TOKEN(JWT)
![[Pasted image 20240206100136.png]]
