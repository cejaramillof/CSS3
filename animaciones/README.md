
# Animaciones
Las animaciones son las transiciones que suceden de un elemento en un punto A que se transforma, se mueve o se desplaza hasta un punto. Es decir, la animación es cada uno de los detalles del proceso de un cambio que de manera rápida se ve de forma animada.

Las animaciones nos permiten generar una sensación vida, es decir, si un elemento esta animado las personas tendrán un mayor engagement y relación con el elemento que están viendo.

## 12 Principios de animación de Disney
Éstos principios son utilizados para la animación tradicional, pero nos quedan como anillo al dedo para hacer animaciones para la web.

### Estirar y encoger
![](https://66.media.tumblr.com/23599728d69aaee2dfe440b0fae1418c/tumblr_n4rq4wXp241tx30c0o1_500.gifv)
Los objetos no mecánicos se pueden deformar, en la animación cuando un objeto toca una superficie se contrae y cuando llega a su punto más lejano de las superficies se expande.

### Anticipación
![](https://66.media.tumblr.com/e0f1476023817047ea757bea5bee924b/tumblr_n4rq4fLeYx1tx30c0o1_500.gifv)
Los personajes se preparan antes de hacer una animación

### Puesta en escena
![](https://66.media.tumblr.com/693e3afe54ccdbf32da53088534cc596/tumblr_n4rq3xrhYu1tx30c0o1_500.gifv)
Se puede revelar u ocultar el punto de interés mediante animaciones

### Acción directa y pose a pose
![](https://66.media.tumblr.com/849e992a19373475a9d6a6929571982b/tumblr_n4rq2vOobA1tx30c0o1_500.gifv)
Está relacionado con los keyframes.

La acción directa da fluidez al movimiento, y proporciona un aspecto fresco, suelto y desenfadado.

En la acción pose a pose se desarrolla un planteamiento inicial. Es una animación más controlada que viene determinada por el número de poses, y las poses intermedias. Se pueden mezclar estas dos técnicas


### Acción continuada y superposición
![](https://66.media.tumblr.com/912d1b0e23d9d3eda7ff64c635a49501/tumblr_n4rp3vzY9H1tx30c0o1_500.gifv)
En la acción continuada, el personaje aún sigue moviéndose después de la acción principal.

En la acción superpuesta, se mezclan movimientos múltiples que influyen en la posición del personaje.


### Entradas lentas y salidas lentas
![](https://66.media.tumblr.com/1b333b53b545a0395a9107f5fd77a486/tumblr_n4rp2jtnWJ1tx30c0o1_500.gifv)
Se trata de acelerar el centro de la acción, y ralentizar el principio y el final de la misma. (ease-in-out)


### Arcos
![](https://66.media.tumblr.com/d27d01901530cd2d791f9d1b16d375b6/tumblr_n4rp0cHVGG1tx30c0o1_500.gifv)
Los objetos orgánicos se mueven en curvas, no líneas


### Acción secundaria
![](https://66.media.tumblr.com/42e2d745bed420c3ea1cac7e43aeedff/tumblr_n4roywPwA01tx30c0o1_500.gifv)
Una animación puede afectar a otros objetos


### Ritmo
![](https://66.media.tumblr.com/854108db6690b07fb05ca7a49e3e00ab/tumblr_n4row2fvJ71tx30c0o1_500.gifv)


### Exageración
![](https://66.media.tumblr.com/5e1e8583ed03f1fc2248c29bc988fdc6/tumblr_n4rovcm0hn1tx30c0o1_500.gifv)
Exagerar una acción, generalmente ayuda a hacerla más creíble.


### Dibujos sólidos
![](https://66.media.tumblr.com/449b2df509f0acc081862d50acddd70a/tumblr_n4rodcDJai1tx30c0o1_500.gifv)
Se tiene que entender un objeto por su contorno


### Personalidad o apariencia
![](https://66.media.tumblr.com/5d4cb8e2abb700da4ba4108bb9dcbbbd/tumblr_n4robdL86D1tx30c0o1_500.gifv)
Los objetos pueden tener personalidad propia


## CSS3
Transitions, Transforms, Animations

## Transiciones
Una transicion sucede cuando existe un cambio en una o mas propiedades css asignadas a un selector, normalmente el cambio es de manera inmediata, pero mediante la propiedad Transition podremos personalizar como se visualizara.

- **Duración (transition-duration):** Tiempo en segundos (s) o milisegundos (ms) que durara la transición cuando ocurra un cambio en las propiedades de la etiqueta al que el selector CSS hace referencia. Esta propiedad es la única requerida para establecer una transición.

```css
.selector {
  transition-duration: 2000ms /* 2s */
}
```

- **Retardo (transition-delay):** Define un retardo en el comienzo de la transición cuando ocurra un cambio es las propiedades de la etiqueta al que el selector CSS hace referencia. en (s) o (ms). Por defecto es 0.

```css
.selector {
  transition-delay: 1000ms /* 1s */
}
```

- **Propiedades (transition-property):** Define un listado de propiedades separadas por coma que serán afectadas por Transition si cambian. Por defecto todas pueden ser afectadas.

```css
.selector {
  transition-property: width, height;
}
```

- **Aceleración (transition-timing-function):** Define el tipo de aceleración que tendrá la transición. linear es su valor por defecto

- - **ease:** define la aceleración rápida al inicio y muy leve al final (opción por defecto)
- - **ease-in:** define la aceleración leve al inicio y rápida al final
- - **ease-out:** define la aceleración rápida al inicio y leve al final
- - **ease-in-out**: define la aceleración leve al inicio y leve al final
- - **linear: define** un efecto sin aceleración, es decir, constante durante todo el trazo
- - **steps(0):** define la aceleración en frames, que son los pasos que dará el selector para completarla.
- - **cubic-bezier (0, 0, 0, 0):** define una aceleración personalizada mediante una configuración avanzada, la cual, consta de 4 valores de -1 a 1.

```css
.selector {
  transition-timing-function: ease;
  transition-timing-function: ease-in;
  transition-timing-function: ease-out;
  transition-timing-function: ease-in-out;
  transition-timing-function: linear;
  transition-timing-function: steps(0);
  transition-timing-function: cubic-bezier(1, 0, 0, 1);
}
```

- **Combinar todas:**
```css
.selector {
  transition: 1s; /* only duration required*/
  transition: width 1s 1s ease; /* property (optional), duration, delay (optional), timing-function (optional, default ease)*/
}
```

### Ejemplo
```css

.pelota {
  width: 100px;
  height: 100px;
  border-radius: 50%;
  background-color: red;
  /*transition-property: width;*/
  /*transition-duration: 1s;*/
  /*transition-delay: 1s;*/
  /*transition-timing-function: ease;*/
  transition: 1s;
}

/* Transicion sobre si misma */
.pelota:hover {
  width: 150px;
  height: 150px;
}

.canasta {
  border: 1px solid red;
}

/* transiciones a múltiples elementos */
.canasta:hover .pelota {
  width: 200px;
  height: 200px;
}
```


## Transformormaciones
Es la propiedad más famosa al hacer animaciones, algunas de las cosas que podemos lograr en un elemento con transform son:
- Rotar un elemento. (**rotate**)
- Inclinar-Sesgar un elemento. (**skew**)
- Cambiar la posición de un elemento. (**translate**)
- Cambiar el tamaño de un elemento. (**scale**)
-
### Ejemplo
```css
.canasta:hover {
  border: 1px solid red;
  /* transform: rotar | inclinar | posicion | tamaño (0 to 1, 1 es el 100% del elemento, 2 el 200%, 0.1 el 10%) */
  transform: rotate(5deg) skew(10deg) translate(100px) scale(1);
}
```

### Rotar un elemento. (**rotate**)
Recibe un valor en grados (deg), si le pones un valor positivo, van como las agulas del reloj, negativo hacia el lado izquierdo.

```css
.container {
  border: 1px solid red;
}

.cuadrado {
  transition: .3s;
}

/*
 A veces puede causar bugs, así que es mejor practica a veces aplicarla al hijo de alguien:
.cuadrado:hover { */
.container:hover .cuadrado {
  transform: rotate(45deg);
  transform: rotate(-45deg);

  transform: rotateZ(45deg); /* Al igual que rotate, Rota en un plano 2d, hacia los lados */

  transform: rotateX(45deg); /* Rota en un plano 3d, tirando la parte superior hacia el fondo  */
  transform: rotateY(45deg); /* Rota en un plano 3d, tirando la parte izquierda hacia el fondo  */


  /* También se pueden anidar transofmraciónes */
  transform: rotateX(45deg) rotateY(45deg) rotateZ(45deg);
  /* Rotar en 3d, uniendo todos los valores anteriores, 0 no rotar, 1 rotar */
  transform: rotate3d(x, y, z, rotate);
  transform: rotate3d(0, 0, 1, 45deg) /* Es como si girara 45deg, en Z solamente*/
}
```


### Inclinar-Sesgar un elemento. (**skew**)
Sesgar (pensamiento sesgado = inclinado) es esa inclinación que puede sufrir un elemento gracias a una transformación en CSS.
```css
.container {
  border: 1px solid red;
}

.cuadrado {
  transition: .3s;
}

.container:hover .cuadrado {
  transform: skew(x); /* only in x */
  transform: skew(x, y);
}
```

### Cambiar la posición de un elemento. (**translate**)
Translate nos sirve para poder mover un elemento arriba, abajo, derecha e izquierda. También utilizamos la propiedad perspective para poder darle profundidad a un elemento y obtener un efecto 3D.

```css
.container {
  border: 1px solid red;
}

.cuadrado {
  transition: .3s;
}

.container:hover .cuadrado {
  /*
  Move in 2d:
  */
  transform: translate(x);  /* in X, move to right*/
  transform: translate(-x); /* in X, move to left */

  transform: translateX(x);
  transform: translateY(y);

  transform: translate(x, y);

  /*
  con translateZ, podemos modificar la profunidad, no funciona en 2d.
  Necesitamos modificar la perspectiva, poniendole un contexto 3d a nuestro elemento.

  Le añadimos a body, o al padre del elemento:
  */
  perspective: 200px;
  perspective-origin: Center; /* por defecto es center, pero podemos cambiarla (top, bottom, left, right) */
  perspective-origin: Top Right;
  perspective-origin: x y;

  transform: translateZ(z);


  /* Todos unidos */
  transform: translate3d(x, y, z);
}
```


### Cambiar el tamaño de un elemento. (**scale**)
Transform-scale nos permite modificar el tamaño de nuestros elementos a nuestro gusto.
- 0 = 0% del tamaño.
- .1 = 10% del tamaño.
- 1 = 100% del tamaño.
- 2 = 200% del tamaño.

```css
.container {
  border: 1px solid red;
}

.cuadrado {
  transition: .3s;
}

.container:hover .cuadrado {
  transform: scale(n); /* update both, X and Y */
  transform: scale(x, y);
}
```

### Punto de Transformación
El punto de transformación de un elemento está clavado en alguna parte de la interfaz, y por defecto se encuentra en el centro.
Sin embargo, podemos jugar con la posición de este punto según el tipo de animación que queramos crear.

```css
.container {
  border: 1px solid red;
}

.cuadrado {
  transition: .3s;

  transform-origin: x y;
  transform-origin: 50% 50%; /* por defecto */


  transform-origin: top;
  /*  used with
  transform: rotateX(45deg);
  */


  transform-origin: left; /*0% 50%*/
  transform-origin: right; /*100% 50%*/
  /* used with
  transform: rotateY(45deg);
  */


  transform-origin: top right;
  /* used with
  transform: rotateZ(45deg);
  */
}

.container:hover .cuadrado {
  transform: rotateY(45deg);
}
```

## Animaciones
Css de forma nativa nos ofrece la propiedad änimation, esta nos permitirá crear animaciones con varios estados, es decir, con transitions podemos animar elementos de un punto A a un punto B, pero con animation podremos crear varios puntos de referencia, para que el elemento pueda tener mas de un estado, como puntos A, B, C y D.

Lista de propiedades animables: [link](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_animated_properties)

```css
.container {
  border: 1px solid red;
  width: 100%;
}

.cuadrado {
  width: 200px;
  /* Requireds props */
  animation-name: cuadrado; /*multiples, separateds by comma in all animation properties ej: cuadrado, rebote // 2s, 4s  */
  animation-duration: 2s; /* 2s, 4s */

  /* Optionals */
  animation-delay: 1s;
  animation-iteration-count: 3;
  animation-fill-mode: forwards; /* will finish animation, with last keyframes value */

  animation-iteration-count: infinite; /* or number of times to be executed */

  animation-timing-function: ease; /* default is in ease */ /* ease-in, ease-out, ease-in-out, linear */
  animation-timing-function: cubic-bezier(1,1,1,1); /* Linear */ /* cubic-bezier: -1 to 1, cubic-bezier.com */
  animation-timing-function: steps(60); /* cantidad de pasos por la duración: ej duration:1s - steps(60) 60 cuadros por segundo*/

  animation-direction: alternate; /* default is normal */ /* alternat, reverse */

  animation-play-state: running; /* running, paused, to start on hover or any*/
}

@keyframes cuadrado {
  0% { /* the same at from */
    opacity: 1;
    left: 1;
  }
  100% { /* the same at to */
    opacity: 0;
    left : calc(100% - 200px);
  }
}

.container:hover .cuadrado {
  transform: scale(n); /* update both, X and Y */
  transform: scale(x, y);
}
```

## Detectar eventos de animaciones CSS en JS
```javascript
       const $cuadrado = document.getElementById('cuadrado');

        // Cuando comienza el evento
        $cuadrado.addEventListener('animationstart', (event) => {
             $cuadrado.innerHTML='Animation Started';
             $cuadrado.style.backgroundColor='blue';
         });

         // Cuando se repite el evento
         $cuadrado.addEventListener('animationiteration', (event) => {
            $cuadrado.innerHTML='Animation Iteration';
            $cuadrado.style.backgroundColor='red';
         });

        // Cuando termina el evento
        $cuadrado.addEventListener('animationend', (event) => {
            // console.log(event.animationName);
            /*
             if(event.animationName==='rebote') {
              $cuadrado.style.animationName = 'cuadrado ladder';
              $cuadrado.style.animationDuration = '3s';
            }
            */
            $cuadrado.innerHTML='Animation Finished';
            $cuadrado.style.backgroundColor='green';
        });
        // Cuando termina el evento, inesperadamente, sin ejecutarse un animationend
        $cuadrado.addEventListener('animationcancel', (event) => {})
```

## Developer tools
Inspection -> (3 points) -> (animations or rendering)

## Performance
con la propiedad `will-change`, podemos optimizar el cambio de algunas propiedades, como opacity y transform.
ej:
```css

.pelota {
  background-color: red;
  border-radius: 50%;
  width: 100px;
  height: 100px;


  transition: 1s;
  /* properties to be changed, like transform, opacity. Not all propertes are optimized for this. */
  will-change: opacity, transform;
}

.pelota:hover {
  opacity: 0;
}
```

## Web Animations API (js)
Se pueden animar elementos en CSS3 por medio de JavaScript a través de `$element.animate`, el cual es un método que crea y reproduce una animación de algún selector especificado, lo que finalmente nos devuelve una instancia del objeto Animation.

```javascript
  const $pelota = document.getElementById('pelota');

  // element.animate(keyframes= [], options = {})
  $pelota.animate([
    // keyframes
    { // from
      transform: 'translateX(0)',
    },
    { // to
      transform: 'translateX(500px)',
    }
  ], {
    // options
    duration: 1000,
    delay: 1000,
    direction: 'reverse', // alternate, normal (Default), reverse
    easing: 'linear', // aceleracion
    iterations: Infinity, // iterations count - Infinity, 1, 2
    fill: 'forwards',
    iterationStart: .5, // 50% // start animation at other moment of animation 0 -1
    endDelay: 5000 // Milisegundos de delay, al final de la animacion
  })

  const $playButton = document.getElementById("play");
  const $stopButton = document.getElementById("stop");
  const $reverseButton = document.getElementById("reverse");
  const $acelerarButton = document.getElementById("acelerar");
  const $frenarButton = document.getElementById("frenar");
  const $subirButton = document.getElementById("subir");
  const $lblSpeedButton = document.getElementById("lbl_Speed");

  $pelota.playbackRate = 0

  $playButton.addEventListener('click', (event) => {
  // $pelota.play();
  if ($playButton.innerHTML == "Pause") {
    $playButton.innerHTML = "Play";
  }else {
    $playButton.innerHTML = "Pause";
  }

  if ($playButton.innerHTML == "Play") {
    $pelota.pause();
    $playButton.innerHTML = "Play"
  } else {
    $pelota.play();
    $playButton.innerHTML = "Pause"
  }
})

$reverseButton.addEventListener('click', (event) => {
  $pelota.reverse();
})

$subirButton.addEventListener('click', (event) => {
  if ($pelotajs6.style.gridArea == "top / top / top / top") {
    $SubirButton.innerHTML = "Subir";
    $pelotajs6.style.gridArea = "normal";
  } else {
    $SubirButton.innerHTML = "Bajar";
    $pelotajs6.style.gridArea = "top";
  }
})

$acelerarButton.addEventListener('click', (event) => {
  if ($pelota.playbackRate < 9.9){
    $pelota.playbackRate = $pelota.playbackRate + 0.1;
    if ($pelota.playbackRate >= 9.9) {
      $lblSpeedButton.innerText = `${$pelota.playbackRate.toFixed(1)}`;
    }else {
      $lblSpeedButton.innerText = `0${$pelota.playbackRate.toFixed(1)}`;
    }
  }
})

$frenarButton.addEventListener('click', (event) => {
  if ($pelota.playbackRate > 0.1) {
    $pelota.playbackRate = $pelota.playbackRate - 0.1;
    $lblSpeedButton.innerText = `0${$pelota.playbackRate.toFixed(1)}`;
  }
})

$stopButton.addEventListener('click', (event) => {
  $pelota.cancel();
})

```