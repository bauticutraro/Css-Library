<h1 style="text-align: center">Tyle</h1>
Tyle es una libreía de css de código abierto con un sistema de grid de 12 columnas (utilizando css grid). Además de contar con el sistema de grid, cuenta tambien con propiedades utilitarias, como lo son por ejemplo las propiedades de flexbox, de grid, propiedades para los márgenes, entre otros.

Tyle también cuenta con componentes adicionales como por ejemplo botones, barras de progreso, navs, modals, cards, entre otros.

---

##¿Cómo utilizarlo?
Para empezar, una vez descargado podes vincular, a tu página .html, diferentes archivos de Tyle:
```
tyle/ 
 ├── css/
 |   ├── tyle.css
 |   ├── tyle.min.css
 |   |
 |   ├── tyle-grid-sistem.css
 |   ├── tyle-grid-sistem.min.css
 |   |
 |   ├── tyle-utilities.css
 |   ├── tyle-utilities.min.css
 |   |
 |   ├── tyle-components.css
 |   └── tyle-components.min.css
 |
 └── js/
     ├── tyle.js
     └── tyle.min.js
```
A continuación les mostraré un cuadro con lo que contienen los diferentes archivos:

|                       Archivos                          | Sistema de grid  | Componentes |     Clases utilitarias     |
| ------------------------------------------------------- |:---------------: | :---------: | :------------------------: |
| **tyle.css**<br>**tyle.min.css**                        |     Incluido     |  Incluido   |          Incluido          |
| **tyle-grid-sistem.css**<br>**tyle-grid-sistem.min.css**|     Incluido     | No Incluido | Solo las de grid y flexbox |
| **tyle-utilities.css**<br>**tyle-utilities.min.css**    |    No Incluido   | No Incluido |          Incluido          |
| **tyle-components.css**<br>**tyle-components.min.css**  |    No Incluido   |   Incluido  |         No Incluido        |

Como podrás ver en el anterior cuadro, tenes la libertad de poder elegir si querés utilizar todo lo que es Tyle, o solo su sistema de grid o sus componentes o sus clases utilitarias.

### Estructura básica para comenzar a utilizar Tyle:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Comenzando a utilizar Tyle</title>
    <link href="https://file.myfontastic.com/VKjMJTbzfBSFneVYf4x7VT/icons.css" rel="stylesheet">    
    <link rel="stylesheet" href="tyle/css/tyle.min.css">
</head>
<body>
    <!-- 
        Contenido de tu página
    -->
    <script src="tyle/js/tyle.min.js"></script>
</body>
</html>
```
Cómo podrás observar, solor tienes que vincular los archivos de Tyle de Css y JavaScript para comenzar a utilizarlo y poder desarrollar todo tu código con Tyle.

Además, otra cosa que podrás observar en el anterior código es que, se está linkeando un archivo exterior,este archivo es de _fontastic_ (se utiliza para poder incluir íconos en la página), que trae algunos íconos para utilizarlos en los diferentes componentes de Tyle (solo es necesario linkearlo si utilizas algún componente, si no, no es necesario).

## Documentación:

### Sistema de Grid:

Para empezar, Tyle cuenta con un sistema de grid de 12 columnas. Dicho sistema esta hecho con Css grid.

Para utilizar el sistema de grid debes crear un div con la clase **_row_**, y allí dentro del div ponés los distintos componenetes con sus respectivas clases del sistema de grid. Dichas clases que le debes poner a los hijos del div con la clase _row_ son las diferentes clases de columnas que las indicas con la clase **_col-_** y luego del guión le indicas cuantas columnas querés que ocupe tu elemento. Tal como se muestra en el siguiente bloque de código:

Html:
```html
    <div class="row">
        <div class="col-1">Una columna</div>
        <div class="col-2">Dos columnas</div>
        <div class="col-3">Tres columnas</div>
        <div class="col-4">Cuatro columnas</div>
        <div class="col-5">Cinco columnas</div>
        <div class="col-6">Seis columnas</div>
        <div class="col-7">Siete columnas</div>
        <div class="col-8">Ocho columnas</div>
        <div class="col-9">Nueve columnas</div>
        <div class="col-10">Diez columnas</div>
        <div class="col-11">Once columnas</div>
        <div class="col-12">Doce columnas</div>
    </div>
```
Con un poco de estilos css (indicándole a los contenedores una altura, un color de fondo, un color al texto, un centrado total al texto, una separación entre los divs, que cada contenedor valla debajo y no al lado, etc...) , obtenés el siguiente resultado:

![Grid sistem](/images/grid-sistem.png "Grid sistem")

Sin embargo, esto no es todo acerca del sistema de grid, ya que Tyle cuenta con un sistema de grid totalmente responsive.
Estas clases para el responsive de los elementos se definen de la siguiente manera:
**_col_-(a partir de que medida ocupa dichas columnas)-(Número de columnas a ocupar)**
Las medidas utilizadas en Tyle son las siguientes: 

| Clase | Desde  |  Hasta  |
| ----- |:-----: | :-----: |
| _xs_  | 480px  | 639px   |
| _sm_  | 640px  | 767px   |
| _md_  | 768px  | 1023px  |
| _lg_  | 1024px | 1365px  |
| _xl_  | 1366px | +1366px |

Por lo tanto podés formar clases como por ejemplo:
_col-xs-12_ (va a ocupar 12 columnas desde 480px para arriba)
_col-sm-6_ (va a ocupar 6 columnas desde 640px para arriba)
_col-md-4_ (va a ocupar 4 columnas desde 768px para arriba)
_col-lg-3_ (va a ocupar 3 columnas desde 1024px para arriba)

Si no pones la medida en la clase col, quiere decir que siempre va a ocupar las columnas que le indiques, al menos que le agregues otra clase con la medida.
Ejemplo:
```html
<div class="row">
    <div class="col-12 col-md-4 col-lg-3"></div>
</div>
```
En este ejemplo, el div va a ocupar 12 columnas hasta 768px, debido a que a partir de 768px ocupará 4 columnas, y a partir de 1024px ocupará 3 columnas.

Y así podes seguir y formar todas las combinaciones que quieras segun lo necesite tu página.

#### Start Column
Tyle también cuenta con clases para que puedas elegir a partir de que columna empieza el div.
Dicha clase se llama de la siguientes maneras:
**_start-(A partir de que columna empieza)_**
O también podes elegir a partir de que medida empezará en la columna que elijas, poniendo la clase de la siguiente forma:
**_start-(A partir de que medida)-(A partir de que columna empieza)_**

Las medidas son las mismas que las mencionadas anteriormente (xs, sm, md, lg, xl).

En el siguiente ejemplo podrás observar mejor lo mencionado anteriormente:

Html
```html
<div class="row">
    <div class="col-5 start-5">Comienza en la columna 5</div>
    <div class="col-8 start-2">Comienza en la columna 2</div>
    <div class="col-9 start-3">Comienza en la columna 3</div>    
</div>
```
Resultado:

![Start Column](/images/start-col.png "Start Column")

Como podrás observar (con la ayuda del inspector de google Chrome) que cada div comienza donde se lo indiques.

### Clases Utilitarias:

#### Clases de Grid:

- #### Grid Gap:

La proppiedad **_grid-gap_** se puede aplicar solamente a los componentes que tengan la propiedad _display: grid_.
Grid gap se refiere a la separación que hay entre las columnas y filas que se encuentran dentro del componente que tenga la propiedad display: grid.

Como podrás ver en la siguiente imagen, el contenedor (con la clase _row_) no tiene la propiedad _grid-gap_, y por lo tanto no hay ninguna separación entre sus columnas y filas.
![Sin Grid Gap](/images/grid-gap-0.png "Sin Grid Gap")

En cambio, en la siguiente imagen, el contenedor si tiene la propiedad _grid-gap_, y por la tanto se genera una separación entre sus columnas y filas.
![Con Grid Gap](/images/grid-gap-1.png "Con Grid Gap")

Tyle cuenta con clases para el _grid-gap_. Estas calses se llaman de la siguiente manera:
**grid-gap-(número)**
El numero que va luego de _grid-gap-_ puede ir del 0 hasta al 10. Cuanto mas grande sea el número, habrá una mayor separación entre columnas y filas.


- #### Order:
La propiedad **_order_** sirve para indicarle un orden al componente que tenga dicha propiedad. Solo se le puede aplicar a los hijos directos de los componentes que tengan la propiedad _display: grid_ o la propiedad _display: flex_. La propiedad _order_ solor acepta números, y estos números pueden ser tanto positivos, como negativos. El valor por defecto de la propiedad _order_ es 0.
Tyle cuenta con clases para la propiedad _order_, y dicahs clases se indican de la siguiente forma:
**_order-(número)**
El número, que va luego de _order-_, puede ir desde -6 hasta 6.

Ejemplo:
```html
<div class="row">
    <div class="col-4">Elemento Nº 1</div>
    <div class="col-4">Elemento Nº 2</div>
    <div class="col-4">Elemento Nº 3</div>
    <div class="col-4">Elemento Nº 4</div>
    <div class="col-4">Elemento Nº 5</div>
    <div class="col-4">Elemento Nº 6</div>
    <div class="col-4">Elemento Nº 7</div>
    <div class="col-4">Elemento Nº 8</div>
    <div class="col-4">Elemento Nº 9</div>
    <div class="col-4">Elemento Nº 10</div>
    <div class="col-4">Elemento Nº 11</div>
    <div class="col-4">Elemento Nº 12</div>
</div>
```

Resultado:
![Sin la propiedad order](/images/order-0.png "Sin la propiedad order")

Como podrás ver en la anterior imagen, los elementos no tienen la propiedad _order_, y por lo tanto, están ubicados según su posición en el html.

En cambio, en la siguiente situación, los elementos tienen la propiedad _order_, y ya no se posicionan según están ubicados en el html, si no que se posicionan según la propiedad order

```html
<div class="row">
    <div class="col-4 order--3">Elemento Nº 1</div>
    <div class="col-4 order--1">Elemento Nº 2</div>
    <div class="col-4 order-1">Elemento Nº 3</div> 
    <div class="col-4 order--2">Elemento Nº 4</div> 
    <div class="col-4 order-3">Elemento Nº 5</div>
    <div class="col-4 order-2">Elemento Nº 6</div>
    <div class="col-4 order--6">Elemento Nº 7</div>
    <div class="col-4 order--4">Elemento Nº 8</div>
    <div class="col-4 order-6">Elemento Nº 9</div> 
    <div class="col-4 order-5">Elemento Nº 10</div>
    <div class="col-4 order--5">Elemento Nº 11</div>
    <div class="col-4 order-4">Elemento Nº 12</div>
</div>
```

Resultado:
![Con la propiedad order](/images/order-1.png "Con la propiedad order")

- #### Justify Items:
Esta propiedad **_justify-items_** se le debe aplicar (en el caso de grid) a los contenedores que tengan la propiedad _display: grid_. Lo que hace esta propiedad es alinear el contenido dentro de un elemento de la cuadrícula a lo largo del eje de la fila. Dicha propiedad puede tener los siguientes valores:
- _start_: Alinea el contenido en el extremo izquierdo del área de la cuadrícula.
![Justify Items](/images/justify-items-1.png "Justify Items")
- _end_: Alinea el contenido en el extremo derecho del área de la cuadrícula.
![Justify Items](/images/justify-items-2.png "Justify Items")
- _center_: Alinea el contenido en el centro del área de la cuadrícula.
![Justify Items](/images/justify-items-3.png "Justify Items")
- _stretch_: Rellena toda la altura del área de la cuadrícula (este es el valor predeterminado).
![Justify Items](/images/justify-items-4.png "Justify Items")

Tyle cuenta con clases para estas propiedades. Para indicar dicahs clases se hace de la siguiente manera:
**_g-justify-items-(valor)_**
La _g-_ es para diferenciar las clases de grid de las de flexbox, ya que en flexbox hay propiedades con el mismo nombre pero diferente valor. Y los _valores_ son los mencionados anteriormente (start, end, center, stretch).


- #### Align Items:
Esta propiedad **_align-items_** se le debe aplicar (en el caso de grid) a los contenedores que tengan la propiedad _display: grid_. Lo que hace esta propiedad es alinear el contenido dentro de un elemento de la cuadrícula a lo largo del eje de la columna. Dicha propiedad puede tener los siguientes valores:
- _start_: Alinea el contenido en la parte superior del área de la cuadrícula.
![Align Items](/images/align-items-1.png "Align Items")
- _end_: Alinea el contenido en la parte inferior del área de la cuadrícula.
![Align Items](/images/align-items-2.png "Align Items")
- _center_: Alinea el contenido en el centro del área de la cuadrícula.
![Align Items](/images/align-items-3.png "Align Items")
- _stretch_: Rellena todo el ancho del área de la cuadrícula (este es el valor por defecto).
![Align Items](/images/justify-items-4.png "Align Items")

Tyle cuenta con clases para estas propiedades. Para indicar dichas clases se hace de la siguiente manera:
**_g-align-items-(valor)_**
Los _valores_ son los mencionados anteriormente (start, end, center, stretch).


- #### Justify Content:
Esta propiedad **_justify-content_** se le debe aplicar (en el caso de grid) a los contenedores que tengan la propiedad _display: grid_. Lo que hace esta propiedad es alinear el todo el contenido de la cuadrícula dentro del contenedor de la cuadrícula. Esta propiedad alinea la cuadrícula a lo largo del eje de la fila. Dicha propiedad puede tener los siguientes valores:
- _start_: Alinea la cuadrícula con el extremo izquierdo del contenedor de la cuadrícula.
![Justify Content](/images/justify-content-1.png "Justify Content")
- _end_: Alinea la grilla con el extremo derecho del contenedor de la grilla.
![Justify Content](/images/justify-content-2.png "Justify Content")
- _center_: Alinea la cuadrícula en el centro del contenedor de la cuadrícula.
![Justify Content](/images/justify-content-3.png "Justify Content")
- _stretch_: Cambia el tamaño de los elementos de la grilla para permitir que la grilla ocupe todo el ancho del contenedor de la grilla.
![Justify Content](/images/justify-content-4.png "Justify Content")
- _space-between_: Coloca una cantidad par de espacio entre cada elemento de la cuadrícula, sin espacio en los extremos.
![Justify Content](/images/justify-content-5.png "Justify Content")
- _space-around_: Coloca una cantidad par de espacios entre cada elemento de la grilla, con espacios de la mitad de tamaño en los extremos.
![Justify Content](/images/justify-content-6.png "Justify Content")
- _space-evenly_: Coloca una cantidad igual de espacio entre cada elemento de la cuadrícula, incluidos los extremos.
![Justify Content](/images/justify-content-7.png "Justify Content")


Tyle cuenta con clases para estas propiedades. Para indicar dichas clases se hace de la siguiente manera:
**_g-justify-content-(valor)_**
Los _valores_ son los mencionados anteriormente (start, end, center, stretch, beetween, around, evenly).


- #### Align Content:
Esta propiedad **_align-content_** se le debe aplicar (en el caso de grid) a los contenedores que tengan la propiedad _display: grid_. Lo que hace esta propiedad es esestablecer la alineación de la cuadrícula dentro del contenedor de la cuadrícula. Esta propiedad alinea la cuadrícula a lo largo del eje de la columna. Dicha propiedad puede tener los siguientes valores:
- _start_: Alinea la cuadrícula con la parte superior del contenedor de la cuadrícula.
![Align Content](/images/align-content-1.png "Align Content")
- _end_: Alinea la grilla con la parte inferior del contenedor de la grilla.
![Align Content](/images/align-content-2.png "Align Content")
- _center_: Ainea la cuadrícula en el centro del contenedor de la cuadrícula.
![Align Content](/images/align-content-3.png "Align Content")
- _stretch_: Cambia el tamaño de los elementos de la grilla para permitir que la grilla ocupe toda la altura del contenedor de la grilla.
![Align Content](/images/align-content-4.png "Align Content")
- _space-between_: Coloca una cantidad par de espacio entre cada elemento de la cuadrícula, sin espacio en los extremos.
![Align Content](/images/align-content-5.png "Align Content")
- _space-around_: Coloca una cantidad par de espacios entre cada elemento de la grilla, con espacios de la mitad de tamaño en los extremos.
![Align Content](/images/align-content-6.png "Align Content")
- _space-evenly_: Coloca una cantidad igual de espacio entre cada elemento de la cuadrícula, incluidos los extremos.
![Align Content](/images/align-content-7.png "Align Content")


Tyle cuenta con clases para estas propiedades. Para indicar dichas clases se hace de la siguiente manera:
**_g-align-content-(valor)_**
Los _valores_ son los mencionados anteriormente (start, end, center, stretch, beetween, around, evenly).


- #### Justify Self:
Esta propiedad **_justify-self_** se le debe aplicar (en el caso de grid) a los contenedores que tengan la propiedad _display: grid_. Lo que hace esta propiedad es alinear el contenido dentro de un elemento de la cuadrícula a lo largo del eje de la fila. Este valor se aplica al contenido dentro de un único elemento de la grilla. Dicha propiedad puede tener los siguientes valores:
- _start_: Alinea el contenido en el extremo izquierdo del área de la cuadrícula.
![Justify Self](/images/justify-self-1.png "Justify Self")
- _end_: Alinea el contenido en el extremo derecho del área de la cuadrícula.
![Justify Self](/images/justify-self-2.png "Justify Self")
- _center_: Alinea el contenido en el centro del área de la cuadrícula.
![Justify Self](/images/justify-self-3.png "Justify Self")
- _stretch_: Rellena todo el ancho del área de la cuadrícula (este es el valor por defecto).
![Justify Self](/images/justify-self-4.png "Justify Self")

Tyle cuenta con clases para estas propiedades. Para indicar dicahs clases se hace de la siguiente manera:
**_g-justify-self-(valor)_**
Los _valores_ son los mencionados anteriormente (start, end, center, stretch).

- #### Align Self:
Esta propiedad **_align-self_** se le debe aplicar (en el caso de grid) a los contenedores que tengan la propiedad _display: grid_. Lo que hace esta propiedad es alinear el contenido dentro de un elemento de la cuadrícula a lo largo del eje de la columna. Este valor se aplica al contenido dentro de un único elemento de la grilla. Dicha propiedad puede tener los siguientes valores:
- _start_: Alinea el contenido en la parte superior del área de la cuadrícula.
![Align Self](/images/align-self-1.png "Align Self")
- _end_: Alinea el contenido en la parte inferior del área de la cuadrícula.
![Align Self](/images/align-self-2.png "Align Self")
- _center_: Alinea el contenido en el centro del área de la cuadrícula.
![Align Self](/images/align-self-3.png "Align Self")
- _stretch_: Rellena toda la altura del área de la cuadrícula (este es el valor predeterminado).
![Align Self](/images/align-self-4.png "Align Self")

Tyle cuenta con clases para estas propiedades. Para indicar dicahs clases se hace de la siguiente manera:
**_g-align-self-(valor)_**
Los _valores_ son los mencionados anteriormente (start, end, center, stretch).