
#### Relative Layout
Es importante empezar de izquierda a derecha

#### LIST VIEW
Los ListView, tienen una lista de items asociadas, que entra al listView a través de un adapter.

>Si al listview le le quieres poner un listener, debes poner onItemClickListener, es importante que tenga item, ya que si no sería otro listener.

Donde realmente le indicas el tipo de layout que vas a utilizar es en el adapter, el cual, utilizaremos el constructor con (contexto,layout,lista)

#### ArrayAdapter crear tu propio adapter
**Primer Paso:** Creamos una clase que extienda de arrayAdapter\<Tipo\>
**Segundo Paso:** creamos el layout que vayamos a utilizar
**Tercer Paso:** En nuestro adaptador,creamos un atributo por cada parametro que nos entra en el constructor
**Cuarto Paso:** 
Override del método getView, este metodo se lanza por cada elemento que recibimos en la lista por el constructor, cada vez que se lance recive la posición.
Dentro de este hay que hacerle inflate al layout, al hacerle dicho inflate nos quedaremos con la view.
Poniendo:
LayoutInflater.from(ctxInput).inflate(layoutInput,parentViewGroup,false);

Lo que hace es: el layout template, lo va a cargar dentro del elemento padre/parent que sería el listView en este caso.

Recuperamos los campos del view y seteamos los datos del modelo dado por la lista.

![[Pasted image 20231110183623.png]]

#### IMPORTANTE:

Como android no solo es para dispositivos con pantalla tactil, tienen que hacer una diferenciación entre selección y click.
**AdapterView.OnItemSelectedListener** es usado para los spinner
>(including Spinner and Gallery — treat everything as selection events)

**AdapterView.OnItemClickListener** es usado para las listView
>(like ListView and GridView — treat selection events and click events differently)
>Los eventos click para estos será cuando hagas  tanto click con el puntero del dipositivo, es decir por ejemplo en una tv dandole click al centro del mando o por el contrario puedas dar click con el dedo en la pantalla

Fuente: pag 260 The busy Coder´s guide to android development

#### GRID VIEWS
Para hacer es igual que el listView
En el xml hay una propiedad android:numColumns que sirve para dividirla grilla

#### RecycleViews
El listView tiene un problema y es que carga todos los elementos de golpe, si hay muchos elementos puede dar problemas de rendimiento, ya que estarán cargado todos, y a medida que vas scrolleando lo va pintando.

Para esto existe el RecycleView que como indica recicla los elementos que no están en pantalla.

Tienes que extender de recycleViewAdapter, y tener una clase interna ViewHolder
El viewHolder se utilizará para coger los elementos del layout.
EL RecycleViewAdapter, se utilizará para:
1. crear el viewHolder, con la clase interna ViewHolder a base del view y el LayoutInflater
2. OnBindViewHolder se utilizará para bindear los valores al viewHolder creado, el holder se recibe por parametr
![[Pasted image 20231110201934.png]]
![[Pasted image 20231110200800.png]]

