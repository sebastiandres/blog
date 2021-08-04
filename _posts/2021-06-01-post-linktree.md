---
featured: true
hide: false
toc: false
layout: post
title: Emulador de Linktree
description: "Imitando un directorio de enlaces sólo con recursos gratuitos"
categories: [fastpages, markdown]
image: images/preview/linktree.png
permalink: /linktree/
comments: true
---

Un directorio de enlaces permite tener entregar un link único y memorable, que puedes actualizar posteriormente a haberlo compartido. Donde, por ejemplo, al dar una charla pudiera decir “el código y la presentación estarán en este link”, pero donde posteriormente sea posible agregarle la grabación de la charla o un resultados de una encuesta. Probé con Linktree, pero pronto lo llené con demasiados enlaces y se volvió confuso y difícil de navegar. Necesitaba una forma de agrupar de manera temática y con un grado flexible de niveles de profundad. En efecto, si a alguien no le interesa el tema “X” probablemente no le interesaría el video de “X”, el código de “X”, la presentación de “X” en html o pdf.

![]({{ site.baseurl }}/images/2021-06-01-linktree/comparacion.png "Formato ofrecido por linktree (izquieda) versus lo que necesitaba y que tuve que crear (derecha).")

Formato ofrecido por linktree (izquieda) versus lo que necesitaba y que tuve que crear (derecha).
Necesitaba una manera de tener un directorio de enlaces con un nombre memorable, fácil de compartir y personalizar, pero permitiendo mantener distintos niveles de agrupación. Desafío adicional: Cuando se trata de recursos en línea, soy un tacaño extremo. Así que buscaba una solución que pudiera implementar sin costos mensuales recurrentes.

Como tacaño extremo llegué a pensar en hacer varias cuentas en linktree y vincularlas entre sí, pero no era una solución escalable (y tendría que acordarme de que correo y password usé para cada enlace). Así que entre una mezcla de vergüenza y flojera terminé desechando la idea. La solución me llegó de golpe. Github permite mostrar páginas html estáticas. ¡Podía hacer una página html simple que emulara a linktree y que podía guardar en cada repositorio en github! El enlace central seguiría siendo en linktree (lintr.ee/sebastiandres en mi caso) y los enlaces serían a los htmls plano de cada repositorio de github. Es una buena mezcla, porque linktree es bastante amigable y tiene algunas herramientas de administración como activar/desactivar enlaces. Comencé revisando el código de linktree, pero era excesivamente largo y confuso. Así que puse manos a la obra y me puse a construir una solución de manera incremental.

* **Primera versión**: Un único archivo html, simple y funcional. Imita los colores y botones sólo con html y css, sin javascript, incluyendo la animación del botón. Comienzo a desplegarlo en mis repositorios y enlazarlos desde linktree. Basta con activar cada repositorio como github pages para que github proporcione un enlace fijo y estable para index.html (o README.md). No es perfecto, pero funciona, ya se cumple el funcionamiento mínimo. Problemas detectados: el tipo y tamaño de fuente es similar pero no es correcto. El despliegue en un smartphone es muy distinto entre linktree y imitación (tacaña).

![]({{ site.baseurl }}/images/2021-06-01-linktree/v1.png "Resultado de la primera versión: web (izquierda) y mobile (derecha). Un resultado sorprendentemente similar para la cantidad de código y esfuerzo.")

* **Segunda versión**: Después de googlear, aprendí a manejar css selectivo usando @media (orientation: landscape/portrait). Problemas detectados: Todavía se ve un poco diferente, sobre todo en los márgenes y tamaño del botón. Al ir actualizando en mis repositorios esta segunda versión, me doy cuenta que es difícil recordar y distinguir visualmente cuál es la versión actual. Sería interesante tener algún tipo de indicador visual al respecto.
Tercera versión: Ajustes a las propiedades del css para imitar mejor linktree (width, height, text wrapping, font sizes). Incluye un texto con la versión para distinguir la versión utilizada en cada repositorio y hacer más fácil la actualización. Problemas detectados: Los textos no están centrados adecuadamente. Lo peor es tener que ir copiando manualmente el nuevo estilo a cada repositorio en cada nueva actualización. Lo ideal es que el estilo se manejara centralmente y actualizara automáticamente a todos los repositorios que lo utilizaran.

* **Cuarta versión**: En lugar de tener el css directamente en el html, lo muevo a un archivo css. De esa manera, todos los archivos pueden llamar a ese archivo. Eso permite separar contenido de formato. Esta cuarta versión me dio muchos problemas. En local todo funcionaba bien, pero github no desplegaba bien la página por un problema con el MIME type del archivo css. Así que tuve que usar https://raw.githack.com para obtener un enlace del css con el MIME type correcto. Problemas detectados: La actualización de css con github a través de https://raw.githack.com tiene un lag importante, a veces de horas, por lo que es difícil (y frustrante) comprobar si el cambio resultó bien.

* **Quinta versión**: Comienzo a utilizar DigitalOcean para levantar un sitio estático a partir del repositorio en github. De esa manera, se generan urls fijas de los assets (css o eventualmente javascript) que se actualizan automáticamente con cada push a github, sin costo asociado y con el MIME type adecuado. Eso permite tener un enlace estable para css y html que puede utilizarse en los repos de github. Ahora también externalizo la “versión” del archivo, para que sea importado por el archivo. Estos archivos css y html ahora se llamarán siempre “latest_style.css” y “latest_copyright.html”, y que actualizo con cada cambio de versión. Así el archivo final se actualiza automáticamente cuando hay algún cambio (¡¡¡no más cambios masivos en los repos!!!). Se definen también algunas clases adicionales para manejar títulos y subtítulos. Problemas detectados: En general se observa bien, pero hay algunos glitchs de tamaño de fuente, textos centrados y detalles así.

*** Sexta (y última) versión**: Revisión general del código para optimizarlo y limpiarlo. Se eliminan algunas propiedades css innecesarias. Hay 3 archivos: El archivo principal es index.html donde se definen los enlaces, y se utilizan los archivos latest_style.css (estilo) y latest_copyright.html (versión de emulador). Cada nueva página con enlaces sólo necesita definir los enlaces, ¡el estilo y copyright ya está definido! Problemas detectados: Nada por ahora.

![]({{ site.baseurl }}/images/2021-06-01-linktree/vf.png "El resultado final: web (izquierda) y mobile (derecha). Las versiones son prácticamente indistinguibles.")

**Sneak peak:**

¿Cómo es el código? La primera versión mezcla el código y el estilo. Hace que actualizar múltiples archivos sea tedioso y propenso a errores (pero fue una versión rápida de desarrollar y autocontenida).

```html
<!DOCTYPE html>
<html>
    <head>
        <style>
            html {background-color:#3d3b3c; font-family: Karla, sans-serif; 
                  font-size: 16px; font-weight: 700;}
            h3, h2, h1 { color:#ffffff; margin-bottom: 16px; text-align: center;}
            div {position: fixed; top: 25%; left: 50%; 
                -webkit-transform: translate(-50%, -50%); transform: translate(-50%, -50%);}
            a {text-decoration: none!important;}
            p  {background-color:#ffffff; color:#3d3b3c; line-height: 56px; width: 676px;
                border: 2px solid rgb(255, 255, 255); margin-bottom: 16px; text-align: center;}
            p:hover {background-color:#3d3b3c; color:rgb(255, 255, 255);}
        </style>
    </head>

    <body>
        <div>
            <h1>Emulador de Linktree</h1>
            <h3>Enlaces</h3>
            <a href="https://linktree-ixkge.ondigitalocean.app/demo1.html" target="_blank">
                <p>Primera versión</p>
            </a>
            <a href="https://linktree-ixkge.ondigitalocean.app/demo6.html" target="_blank">
                <p>Última versión</p>
            </a>
            <h3>Enlaces</h3>
            <a href="https://linktr.ee/sebastiandres">
                <p>⇦ linktree</p>
            </a>
        </div>
    </body>
</html>
```


La última versión permite cambiar el estilo y copyright de manera centralizada, y preocuparse únicamente del contenido.

```html
<!DOCTYPE html>
<html>
    <head>
        <link href="https://fonts.googleapis.com/css2?family=Karla:wght@300;400;600;700&amp;display=swap" rel="stylesheet">
        <link href="https://linktree-ixkge.ondigitalocean.app/latest_style.css" rel="stylesheet"> 
    </head>
    <body>
        <div>
            <h1>Emulador de Linktree</h1>
            <h3>Enlaces</h3>
            <a href="https://linktree-ixkge.ondigitalocean.app/demo1.html" target="_blank">
                <p>Primera versión</p>
            </a>
            <a href="https://linktree-ixkge.ondigitalocean.app/demo6.html" target="_blank">
                <p>Última versión</p>
            </a>
            <h3>Enlaces</h3>
            <a href="https://linktr.ee/sebastiandres">
                <p>⇦ linktree</p>
            </a>
        </div>
        <!-- Version - dont change this code-->       
        <object data="https://linktree-ixkge.ondigitalocean.app/latest_copyright.html" width=100%></object>
    </body>
</html>
```

¿Y cómo se ve todo al final?
Se ve así:


![]({{ site.baseurl }}/images/2021-06-01-linktree/vfinal.gif "El resultado final funciona sorprendentemente bien. La transición es suave y no se nota que son 2 servicios distintos.")

## Aprendizajes:

La separación de contenido y forma es esencial para poder ahorrar trabajo. Incluso para un proyecto pequeño como éste, ayuda enormemente a no duplicar trabajo y hacer más fácil las actualizaciones de N páginas.

La primera versión, que tenía el 80% de las funcionalidades me tomó el 20% del tiempo invertido. Pero el 80% del tiempo restante me enseñó muchas cosas que no sabía de html y css, mime types, y fue muy valioso.

Crear Github pages por cada repositorio es muy práctico, pero tiene ciertas limitaciones para que la gente no abuse al crear páginas estáticas y sea utilizado como un webserver gratis. Existen algunos sitios para entregar css y javascript con el MIME type correcto (https://raw.githack.com por ejemplo), pero no se actualizan automáticamente. DigitalOcean permite levantar sitios estáticos a costo cero y con actualización automática, y poder tener todo sincronizado.

Enlaces de interés:
* https://linktr.ee/sebastiandres: Mi directorio de enlaces, el sitio que quería imitar.
linktree-ixkge.ondigitalocean.app: Sitio web estático, sirve como demo de “cómo se vería” y para almacenar/enlazar el css y copyright.
* https://github.com/sebastiandres/linktree: Repositorio con las distintas versiones del código. Puedes tomar la última versión de html, css y copyright y personalizarlo a tu antojo.
* ¿Cosas por mejorar? ¡Muchas! ¡Sugerencias y comentarios bienvenidos!
