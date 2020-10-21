# Preprocesadores
modular, más fácil de reusar, leer, y mantener. pseudocódigo que después será convertido a CSS o HTML estándar que el navegador entiende.

Gracias a los preprocesadores podemos extender las características de CSS y HTML al nivel de otros lenguajes de programación, permitiéndonos usar características como variables, funciones y mixins.

Para solventar las debilidades han surgido los preprocesadores como:
- HTML: PUG
- CSS: Stylus, Less o Sass.

[Tendencias](https://2019.stateofcss.com/technologies/methodologies/)

## Metodologías para estructurar tu HTML+CSS:
- BEM (Bloque, elemento, modificador)
- BEMIT (BEM + Triángulo invertido)
- ABEM (Atomic BEM)
- ITCSS (CSS de triángulo invertido)
- SMACSS
- ACSS (Atomic CSS)
- OOCSS (CSS orientado a objetos)
- AMCSS (Atribute Model CSS)
- SUIT CSS naming conventions

# BEM (Block, Element, Modifier)
Powered by Yandex (google - rusia)
BEM establece que debemos usar clases para nuestro selectores, clases que se dividen en:
- **Bloques:** Contenedores más grandes que a su vez contienen elementos u otros bloques.
- **__Elementos:** Los elementos siempre forman parte de un bloque, normalmente son los botones, textos, imágenes etc.
- **--Modificadores:** Los modificadores se usan para establecer estilos diferentes a un mismo bloque o elemento.

## Ventajas
- Menos repetición
- Los bloques tienen Independencia absoluta
- Mejoría en la herencia multiple
- Evitar la especificidad (no se sentirá la necesidad de usar !important nunca más)

# Design systems
- [Polaris-Shopify](https://polaris.shopify.com/)
- [Atlassian](https://atlassian.design/)
- [lightning-salesforce](https://lightningdesignsystem.com/)


# HTML
## PUG
(Motor de plantillas) Generador de templates implementado con Javascript que nos permite escribir un pseudocódigo limpio y fácil de leer que será compilado a HTML.

- Puedes usar **Prepros**
- instalar pug con *nodejs* `npm install pug-cli -g` `pug landing.pug`
- correrlo con npx `npx pug-cli landing.pug`

También podemos usarlos con `-w` para dejarlo escuchando cambios o `--pretty` para compilarlo sin mimificado si no identado

# CSS
## LESS
Less es un preprocesador para CSS (basado en JS) que nos permite trabajar hojas de estilo con funcionalidades de un lenguaje de programación.

`npm i less -g`
`lessc less/puggames.less css/puggames.css`

### Anidamiento e imports
```less
@import "nombreArchivo.less";
.intro {
	width: 1340px;
	height: 650px;
	&__imagen { //.intro__imagen
		width: 1320px;
		position: absolute;
		img {
			width: 100%;
			height: 624px;
			object-fit: cover;
		}
  }
}
```

### variables
En las variables almacenamos datos que se puede reutilizar en todas nuestras hojas de estilos.
```less
@nombre: valor;
```

### Funciones
Las funciones en Less ya están prediseñadas.
La diferencia entre mixins y funciones es que las funciones por general hacen cálculos y regresan un resultado que es usado como valor de alguna propiedad.

- `fade(color,%opacidad)`

### Mixins
Su finalidad es ofrecer una funcionalidad que pueda ser reutilizada en otras clases pero que no está pensada para usarse de forma autónoma. Nos permite crear bloques reusables de código que cambian su resultado dependiendo del parámetro que enviemos.

Con los mixins logramos escribir menos código, produciendo un código más claro, más expresivo y sobre todo más fácil de mantener.

```less
// mixin se declaran como clases
.sombra-caja {
	box-shadow: 0px 5px 15px 0px fade(@color-primario, 50%);
}
```

## Sass
Sass (Syntactically Awesome StyleSheets) es una extensión de CSS (basad en ruby) que añade características muy potentes y elegantes a este lenguaje de estilos.

Cuando lo usamos con la extensión `.scss`, nos permite usar una sintaxis más parecida a css. Y con la extensión `.sass` podemos omitir algunos caracteres como: `{}`, y `;`, interpreta los atributos y valores por identación

`npm i sass -g`
`sass sass/ejercicio-sass.scss css/ejercicio-pug.css `

### Anidamiento
```scss

.intro {
	width: 1340px;
	height: 650px;
	&__imagen { //.intro__imagen
		width: 1320px;
		position: absolute;
		img {
			width: 100%;
			height: 624px;
			object-fit: cover;
		}
  }
}
```


### variables
En las variables almacenamos datos que se puede reutilizar en todas nuestras hojas de estilos.
```scss
$nombre: valor;
```


### Imports y Extends
**Import** nos permite escribir código modular separando en diferentes archivos para después importarlos todos en uno solo y tener una base código mucho más ordenada.

```scss
@import "nombreArchivo.scss";
```

**Extends** sirve para insertar los estilos de un selector en otro.

```scss
.perfil {
	width: 50%;
	&__nombre {
		text-align: center;
		font-size: 20px;
	}
}

.perfil__minibio {
	h2 {
		@extend .perfil__nombre;
	}
}
```


### Mixins
Su finalidad es ofrecer una funcionalidad que pueda ser reutilizada en otras clases pero que no está pensada para usarse de forma autónoma. Nos permite crear bloques reusables de código que cambian su resultado dependiendo del parámetro que enviemos.

Con los mixin logramos escribir menos código, produciendo un código más claro, más expresivo y sobre todo más fácil de mantener.
```scss
@mixin caja {
	border-radius: 20px;
	box-shadow: 0px 20px 33px 0px rgba(0,0,0,0.50);
}

.estadistica--perfil {
	@include caja;
}
```


### Funciones
La diferencia entre mixins y funciones es que las funciones por general hacen cálculos y regresan un resultado (o valor especifico) que es usado como valor de alguna propiedad. Los mixins al incluirlos, traerá todo el código que tengan.

```scss
@function get-opacity($color,$nivel) {
	@return rgba($color,$nivel);
}

.perfil {
	color: get-opacity($color-claro, .50);
}
```


### Condicionales
Un **condicional** nos permite evaluar cierta condición y bifurcar entre dos caminos dependiendo de si se cumple o no.
```scss
@mixin titulos($fuente){
	@if $fuente==$Fuente1 {
		font-family: $Fuente1;
	} @else {
		font-family: $Fuente2;
		text-transform: uppercase;
	}
}

body {
	@include titulos($Fuente1); // como es un mixin, tenemos que hacerle include
}
```


### Loops
es un fragmento de código que va a ejecutar de forma repetitiva hasta que cumpla una condición.
```scss
// no hace falta llamarlo, se ejecuta de manera automatica
@each $header, $size in (h1: 30px, h2: 25px, h3: 20px){
	#{$header} { // llamar variable
		font-size: $size;
		margin: 0;
	}
}
/*
h1 {
	font-size: 30px;
	margin: 0;
}
y así sucesivamente..
*/
```

## Stylus
Es el preprocesador CSS más reciente de los tres. Fue creado por TJ Holowaychuk (ex programador de Node.js) y escrito en JADE y Node.js.
Extensión `.styl`, los `{}` son opcionales, si no los usas se basará en el identado. El `;` y los `:` también son opcionales

- `npm i stylus -g`
- `stylus stylus/ejercicio-stylus.styl --out css/ejercicio-stylus.css `

### Anidamiento
```styl
.buscador
	width: 100%
	height: 250px
	padding: 100px
	background-image: url("../images/cover.jpg")
	background-size: cover
	text-align: center
	&__input
		width: 75%
		height: 60px
		padding: 20px
		border: none
		border-radius: 30px
		font-size: 25px
```

### variables
En las variables almacenamos datos que se puede reutilizar en todas nuestras hojas de estilos.
```styl
nombre = valor;
```


### Imports
**Import** nos permite escribir código modular separando en diferentes archivos para después importarlos todos en uno solo y tener una base código mucho más ordenada.

```styl
@import "nombreArchivo.styl";
```



### Mixins
Su finalidad es ofrecer una funcionalidad que pueda ser reutilizada en otras clases pero que no está pensada para usarse de forma autónoma. Nos permite crear bloques reusables de código que cambian su resultado dependiendo del parámetro que enviemos.

Con los mixin logramos escribir menos código, produciendo un código más claro, más expresivo y sobre todo más fácil de mantener.
```styl
contenedor()
	display: flex
	width: 96%
	margin: 0 auto
	padding: 30px 0
```

### Funciones
La diferencia entre mixins y funciones es que las funciones por general hacen cálculos y regresan un resultado (o valor especifico) que es usado como valor de alguna propiedad. Los mixins al incluirlos, traerá todo el código que tengan.

```styl
opacidad(color, cantidad) // función creada
	alpha(color,cantidad) // función prediseñada en stylus

.estadistica--articulos
	color: opacidad(color-primario, .30)
```

### Loops
es un fragmento de código que va a ejecutar de forma repetitiva hasta que cumpla una condición.
```styl
// no hace falta llamarlo, se ejecuta de manera automatica
for header in 3 2 1
	h{header}
		font-size: 35px - (5*header)
		margin: 0
/*
h1 {
	font-size: 30px;
	margin: 0;
}
y así sucesivamente..
*/
```

### Condicionales
Un **condicional** nos permite evaluar cierta condición y bifurcar entre dos caminos dependiendo de si se cumple o no. Usualmente se usan en funciones o mixins.

```scss
titulos(fuente)
	if fuente == Fuente1
		font-family: Fuente1
	else
		font-family: Fuente2
		font-weight: 600
		text-transform: uppercase

body
	titulos(Fuente1)
```