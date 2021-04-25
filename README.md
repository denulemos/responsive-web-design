# Responsive Web Design 🚀️

Responsive Web design es la practica de construir paginas web que se puedan adaptar solos a todos los dispositivos y a todos los tamaños.

## Paso a paso para el desarrollo ⚙️ 

#### Agregar HTML a un `index.html`

```html
<!DOCTYPE html>
<html>
  <head>
    <title>My Landing Page</title>
    <link rel="stylesheet" href="styles.css">
  </head>
  <body>
    <header>
      header
    </header>
    
    <section class="features">
      features
    </section>

    <section class="quote">
      quote
    </section>
    <footer>
      footer
    </footer>

</body>
</html>
```

#### Creamos el archivo `styles.css`

```
@import url(//fonts.googleapis.com/css?family=Open+Sans:400,700,800,300);

body {
    margin: 0;
    padding: 0;
    font-family: 'Open Sans','Helvetica Neue',Helvetica, sans-serif;
    line-height: 1.45;
}
header {
  color: #FFFFFF;
  background-color: #284b63;
  padding: 80px 0;
  text-align: center;
}
section {
  padding: 40px 0;
  text-align: center;
}
.features {
  background: #FFFFFF;
  color: #000000;
}
.quote {
  background:#549DA0;
  color:#FFFFFF;
}
footer {
  background: #353535;
  padding: 32px 0;
  text-align: center;
  color: #868686;
}
```

* Poner `padding: 40p 0;` es lo mismo que poner `padding: 40px 0 40px 0;`
* No le dimos ningun `width` a las secciones, asi ocupan todo el width disponible, eso quiere decir que cuando la pantalla cambie de tamaño, el width siempre sera de 100%

#### Completemos el header

```
<div class="container">
  <h1>Awesome App</h1>
  <h2>This app will change your life!</h2>
  <a class="btn">Download Now</a>
</div>
```

#### Agregamos CSS al header

```
h1 {
  font-size: 48px;
  margin: 0 0 16px 0;
}
h2 {
  font-weight: 300;
  font-size: 24px;
  margin: 0 0 16px 0;
}
```

* `margin: top right bottom left`, los valores van en direccion al reloj

#### Le agregamos estilos al container

```
.container {
    margin: 0 auto;
    padding: 0 20px 0 20px;
    max-width: 900px;
}
```

* Estamos limitando el  `width` a un maximo de `900px` con el `max-width` para que el texto no se haga muy ancho
* Con un `margin: 0 auto;` nos aseguramos que el contenido se quede en el centro del container (su padre), sin importar su tamaño.

#### Le agregamos estilo al boton "Download Now"

```
.btn {
    display: inline-block;
    color: white;
    font-weight: 500;
    font-size: 20px;
    background: #549DA0;
    border: none;
    border-radius: 5px;
    padding: 12px 16px;
    cursor: pointer;
}
```

#### Le agregamos un `hover` al boton de descarga

```
.btn:hover {
    background: #468486;
}
```

#### Agregamos codigo a la seccion de `features`

```
<div class="container">
    
            <div class="feature">
                  <img src="https://www.sololearn.com/uploads/img_blue_pin.png" alt=""/>
                  <p>An awesome feature</p>
                </div>
            
                <div class="feature">
                  <img src="https://www.sololearn.com/uploads/img_blue_chart.png" alt=""/>
                  <p>An awesome feature</p>
                </div>
            
                <div class="feature">
                  <img src="https://www.sololearn.com/uploads/img_blue_msg.png" alt=""/>
                  <p>An awesome feature</p>
                </div>
            
              </div>
```

#### Agregamos estilos a la seccion de`features`

```
.feature {
    width: 32%;
    display: inline-block;
    font-size:16px;
}
.feature img {
    width:40%;
}
```

* Si usamos valores % en los `widths`, se hará la misma posicion en relacion al tamaño del navegador

#### Le agregamos fotos a la seccion `Quote`

```
<section class="quote">
  <blockquote class="container">
    <p>"Some great quote!"</p>
    <cite>Satisfied Customer</cite>
  </blockquote>
</section>
```

* `cite` pone el texto en italica. Es citando la fuente de la quote.

#### Definimos el estilo de la seccion

```
blockquote {
    margin: 0;
    padding: 0;
    text-align: center;
}
blockquote p {
    margin: 0 0 5px 0;
    font-size: 24px;
}
blockquote cite {
    font-size: 16px;
    font-style: italic;
}  
blockquote cite:before {
    content: '–';
    margin-right: 5px;
}
```

* Debemos resetear el `padding/margin` del `blockquote` ya que algunos navegadores proveen valores por defecto para los mismos
* Usamos el `:before` para imprimir un "-" despues del elemento `cite`

#### Agregamos el codigo al footer

```
<footer>
  <div class="container">
    <ul>
      <li><a href="#">Home</a></li>
      <li><a href="#">About</a></li>
      <li><a href="#">Contacts</a></li>
    </ul>
    <p>&copy; All rights reserved.</p>
  </div>
</footer>
```

* Por defecto los `<li>` de una lista de muestran uno abajo del otro

#### Agregamos el estilo al footer

```
footer {
    background: #353535;
    padding: 32px 0;
    text-align: center;
    color: #868686;
    font-size: 12px;
}
footer ul {
    margin: 0;
    padding: 0;
    list-style: none;
}
footer li {
    display: inline-block;
}
footer li a {
    padding: 6px;
    font-size: 14px;
    text-decoration: none;
    color: #c3c3c3;
}
footer li a:hover {
    color: white;
}
```

* Para que la lista aparezca horizontal, agregamos un `list-style: none` para el elemento `<ul>`

## Haciendolo Responsive 🔗

### Viewport

Es la parte visible de la pagina web, este puede ser modificado mediante un **meta tag**

```
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```

* `width=device-width` Setea el width de la pagina para que se ajuste al width de la pantalla
* `initial-scale=1.0` Setea el zoom inicial de la pagina

### Media Queries

Nos da la habilidad de setear distintas configuraciones de CSS para distintos viewports u otras especificaciones.

```
@media screen and (max-width: 600px) {

   body {

     background-color: blue;

  }

}
```

Tambien podemos definir multiples condiciones en la media query

```
@media screen and (min-width: 800px) and (max-width: 1024px) {

body {

background-color: blue;}}
```

Esta regla va a aplicar a pantallas de tamaño 800 a 1024px.

#### Hacer el header Responsive, agregamos una media query

```
@media screen and (max-width: 480px) {
    
}
```

* `480px` es el tamaño promedio para los telefonos celulares

#### Definimos los estilos dentro del media query

```
@media screen and (max-width: 480px) {
    .btn {
        display: block;
        font-size: 18px;
    }
    h1 {
        font-size: 32px;
        margin: 0 0 8px 0;
    }
    h2 {
        font-size: 18px;
    }
    section {
        padding: 25px 0 15px 0;
    } 
}
```

#### Agregamos CSS en la media query para nuestra seccion feature

```
.feature {
        width: 100%;
        text-align: left;
        margin: 0 0 10px 0;
        font-size: 16px;
        display: flex;
        align-items: center;
        justify-content: center;
    }
    .feature img {
        width:15%;
        min-width:60px;
        margin-right:20px;
    }
```

#### Agregamos mas codigo en la media query

```
.quote {
        padding: 30px 0;
    }
    blockquote p {
        font-size: 18px;
    }
    blockquote cite {
        font-size: 14px;
    }
```

Y agregamos para el footer

```
footer {
        padding: 30px 0 10px 0;
    }
    footer li {
        display: block;
        margin: 5px 0;
    }
```

### Unidades CSS

CSS te permite definir tamaños relativos para los `font-sizes` con la unidad `em`.
Por ejemplo, si nuestro `body `tiene un `font-size` de `16px`, si uso `1.5em`, sera igual a `24px (16*1.5)`

```
body {
    font-size: 16px;
}
p {
    font-size: 1.5em;
}
```

Otra unidad es `rem`, que quiere decir **Root Em**, quiere decir que solo se fija en el `font-size` del elemento root, que es `<html>`. Hace que el uso de `em` sea mas facil

```
html {
    font-size: 16px;
}
```

```
h1 {
        font-size: 2rem;
        margin: 0 0 8px 0;
    }
    h2 {
        font-size: 1.125rem;
    }
```

#### Creamos un submenu

Agregamos lo siguiente al menu del HTML

```
<a class="btn">Download Now</a>
        <div class="submenu">
            <a href="#">Link 1</a>
            <a href="#">Link 2</a>
        </div>
```

Y los estilos al submenu

```
.submenu {
    left: 50%;
    transform: translate(-50%, 0);
    text-align:center;
    position: absolute;
    background-color: #549DA0;
    min-width: 160px;
    border-radius: 5px;
    box-shadow: 0px 8px 16px 0px rgba(0,0,0,0.2);
}
.submenu a {
    color: white;
    padding: 12px 16px;
    text-decoration: none;
    display: block;
}
.submenu a:hover {
    background-color: #468486;
}
```

* En CSS colocamos el menu en el centro de la pantalla.

Tambien agregamos lo siguiente a la media query

```
.submenu {
        width: 100%;
        position: relative;
    }
```

#### Agregando animacion

Agregamos el siguiente tag en nuestro `<head> `

```
<script src="https://code.jquery.com/jquery-3.6.0.js"></script>
```

Para agregar `JQuery` a HTML. Creamos el archivo `script.js` y ponemos el siguiente codigo

```
$(function() {
    $(".btn").click(function() {
        $(".submenu").slideToggle(500);
    });
});
```

y le agregamos un `display: none;` a nuestro CSS en `.submenu` asi lo ocultamos por defecto

