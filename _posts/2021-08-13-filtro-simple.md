---
featured: false
hide: false
toc: false
layout: post
title: "Agregando un filtro en fastpages"
description: "Más personalización en fastpages 2"
categories: [fastpages, css, javascript]
image: images/2021-08-13-filtro-simple/boton.gif
comments: true
---

El menu superior del blog empezaba a tener demasiadas opciones, y tenía ganas de simplificarlo.
Me dí cuenta que en realidad habían 2 grandes temáticas: lo que escribo y lo que leo. 
Lo que estoy leyendo tiene siempre el mismo formato: opinión de libro. Lo que escribo puede
ser un post simple (en markdown) o algo más sofisticado en un notebok, o bien ser algún escrito de ficción.
Lo que necesitaba era agregar botones con filtros para poder seleccionar según fuera necesario.

Antes de ponerme a modificar el html de la página web, hice una página web en local con html y css autocontenido,
que cumpliera con estas condiciones. Después de googlear un poco, aprendí que eso podía hacerse de manera simple con 
las opciones `display: 'none'` y `display: 'block'`.

![]({{ site.baseurl}}/images/2021-08-13-filtro-simple/boton.gif "MVP")

El código es el siguiente. Toda la magia está en usar javascript, donde la función `querySelectorAll` que permite encontrar todos los elementos de una cierta condición (las clases `story`, `notebook` y `post`). Para manipular más fácil creé una función que muestra una(s) clase(s) y esconde otra(s).

```html
<!DOCTYPE html>
<html>
 
<head>
    <style>
        .story {background-color: green;}
        .notebook {background-color: blue;}
        .post {background-color: red;}
    </style>
</head>
 
<body>
    <button onclick="show_hide('.story','.notebook, .post')">Show Book</button> 
    <button onclick="show_hide('.notebook','.story, .post')">Show Notebooks</button>
    <button onclick="show_hide('.post','.notebook, .story')">Show Posts</button>
    <button onclick="show_hide('.story,.notebook, .post','')">Show All</button>
 
    <div class="story"> <h1>Book</h1> </div>
    <div class="notebook"> <h1>Notebook</h1> </div>
    <div class="post"> <h1>Post</h1> </div>
    <div class="notebook"> <h1>Notebook</h1> </div>
    <div class="post"> <h1>Post</h1> </div>
    <div class="story"> <h1>Book</h1> </div>
    <div class="notebook"> <h1>Notebook</h1> </div>
      
    <script type="text/javascript">
        function show_hide(selector_show, selector_hide) {
            if (selector_show.length>0){
                elements = document.querySelectorAll(selector_show);
                for (let i = 0; i < elements.length; i++){
                    elements[i].style.display = 'block';
                }
            }
            if (selector_hide.length>0){
                elements = document.querySelectorAll(selector_hide);
                for (let i = 0; i < elements.length; i++){
                    elements[i].style.display = 'none';
                }
            }    
        }
    </script>
</body>
</html>
```

¡Listo! Una vez que estaba funcionarlo, solo fue necesario agregarlo al
layout correspondiente, creando las clases respectivas para cada tipo de post.
¡Me sorprendió que funcionó a la primera!

Como los botones se veian un poco feos, les puse el css de un botón de streamlit.

```css
.css-qbe2hs {
    justify-content: center;
    padding: 0.25rem 0.75rem;
    border-radius: 0.25rem;      
    @media (orientation: portrait) {
       font-size: 75% !important;
    }
    margin-bottom: 10px !important;
    margin-right: 10px !important;
    line-height: 1.6;
    color: inherit;
    width: auto;
    background-color: rgb(255, 255, 255);
    border: 1px solid rgba(38, 39, 48, 0.2);
}
```

Finalmente, el resultado se ve muy profesional para lo sencillo del código:

![]({{ site.baseurl}}/images/2021-08-13-filtro-simple/escribiendo-final.gif "Resultado final")


