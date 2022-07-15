
# Ejemplo display

## Configuración del atributo display

En este breve ejemplo vamos a aprender conceptos básicos de posicionamiento y a jugar un poco con ellos.

### Elementos de bloque

Si repasamos la definición de nuestro HTML

```html
  <p>
    Bienvenides a un <em>nuevo</em> video de <strong>Diseño para todys</strong>
  </p>

  <p>
    <a href="">Mi página web</a> es divertida
  </p>

  <div>
    En esta oportunidad vamos a ver cómo funciona mucho contenido mucho contenido mucho contenido
  </div>

  <section>
    la configuración display block y display inline.
  </section>
```

vemos que los tres elementos principales son un `<p>` (paragraph) y un `div` (contenedor) y ambos tienen la configuración `display` con el valor `block`, definida por defecto por el navegador o _user agent_.

![display block](./images/display-block.png)

Un **elemento de bloque** forma justamente un bloque que toma el ancho de su contenedor. Los navegadores insertan un salto de línea entre los elementos anterior y siguiente.

> Recordá que habilitando las herramientas de desarrollador con F12, podés ver el layout de cada elemento.

Los navegadores definen [los siguientes tags HTML](https://developer.mozilla.org/es/docs/Web/HTML/Block-level_elements#Elementos) con la configuración `display: block` por defecto.

### Elementos de línea

Por otra parte, vemos que el tag `<a>` (anchor, el link) no define un bloque sino que se ubica en la misma línea que el contenido que está antes y después. La configuración `display: inline` hace que los elementos se ubiquen en forma contigua, respetando la separación adicional que definan padding, border o margin.

```html
<a href="">Mi página web</a> es divertida
```

![display inline](./images/display-inline.png)

### Inline-block

Si queremos tener los primeros dos contenedores en la misma línea, podríamos pensar en tener la propiedad `display: inline` pero eso haría que queden pegados. La propiedad `width` no produce ningún efecto, porque el tamaño del contenedor es el que le corresponde en base al contenido. Pero existe la opción `inline-block` que hace que los elementos se ubiquen uno al lado del otro con un tamaño customizable:

![display inline-block](./images/inlineBlock.gif)

### None

Si queremos que un elemento no se visualice, lo configuramos con `display: none`. El elemento no ocupará espacio, al contrario de lo que pasa cuando lo definimos como `visibility: hidden`, como nos cuenta [este artículo](https://stackoverflow.com/questions/133051/what-is-the-difference-between-visibilityhidden-and-displaynone).

### Material adicional

- [Display - CSS Tricks](https://css-tricks.com/almanac/properties/d/display/)
- [Block level elements](https://developer.mozilla.org/es/docs/Web/HTML/Block-level_elements)

## Posicionamiento

Por lo general trataremos de que nuestros elementos se dispongan en un layout semi-automático, de manera que un agregado o un cambio en algún elemento no desacomode toda la página, entonces nos alcanzará con modificar la propiedad display (en estas variantes básicas o bien `flex` / `grid` que aprenderemos más adelante). Para algunos otros casos vamos a necesitar configuraciones extras como las que veremos a continuación.

### Position absolute + Z-Index

Podemos jugar un poco con el posicionamiento de elementos de bloque, con las configuraciones `position` y `z-index`:

![position absolute y z-index](./images/positionAbsoluteAndZIndex.gif)

Al configurar `position: absolute` los dos `<p>` ambos toman una posición exacta en el navegador definidos por los atributos `left` (eje x) y `top` (eje y). ¿Y qué ocurre si colisionan dos bloques? Para eso tenemos la propiedad `z-index`, que define un eje z donde el elemento que tenga un z-index mayor se posicionará por delante del otro.

### Static

Por defecto la posición es **static**, esto significa que un elemento se ubicará en la siguiente línea si tiene el atributo display block, o inmediatamente a la derecha si tiene el atributo display inline (más adelante veremos otras formas de configurar el display). Si queremos modificar las propiedades left, right, top, bottom o z-index, no tiene efecto:

![cambios a un position static](./images/cambiosAUnPositionStatic.gif)

### Relative

Si cambiamos la posición a **relative**, ahora sí comienzan a funcionar las propiedades left, right, top, bottom o z-index:

![position relative](./images/positionRelative.gif)

### Fixed

Y por último, _headers_ o _footers_ de una página conviene definirlos como **fixed**, como vemos en este video (la propiedad bottom lo posiciona al fondo):

![footer](./images/footer.gif)

Si querés crear un sticky footer podés leer [este artículo](https://css-tricks.com/couple-takes-sticky-footer/).

### Twitter es servicio

Para entender el z-index gráficamente: https://twitter.com/_UmairHafeez_/status/1435116506162081796

### Material adicional

Les dejamos material adicional para profundizar:

- [Position - CSS Tricks](https://css-tricks.com/almanac/properties/p/position/)
- [Z-Index - CSS Tricks](https://css-tricks.com/almanac/properties/z/z-index/)
- [Learn Z-Index using a visualization tool](https://thirumanikandan.com/posts/learn-z-index-using-a-visualization-tool)
- [Ejemplo más avanzado con display blocks y jugando con elementos flotantes](https://codepen.io/extragoz/pen/BajJmOZ?editors=1100)
- [CSS Painting Order](https://abandonedwig.info/blog/2020/07/03/css-painting-order.html)
