
---
featured: false
hide: false
toc: false
layout: post
title: "Cambiando fontsize en código"
description: "Más personalización en fastpages"
categories: [fastpages, css]
image: images/preview/fastpages.png
comments: true
---

La configuración por defecto de fastpages para el código no es de mi agrado.
En efecto, me molestaba que incluso cuando la línea no es muy larga, 
al ser de gran tamaño de todas maneras se ocultaba parte del código.

Esto más que nada, porque el tamaño de la fuente era mayor que la del texto. 
Al mirar el css, se ve que los textos de código están definidos como el 
105% o 110% del tamaño normal de la fuente.
Yo pensaría que debe ser al revés: el código está para ser mirado pero no analizado en profundidad.  
Para eso alguien la descargará y revisará en su editor de peferencia. Es mejor que 
se vea todo el código, a que haya que hacer scroll.

¿Qué tan dificil es el cambio?

Googleando llegué a 
https://forums.fast.ai/t/fastpages-how-to-change-font-size/67095
donde se explica que, sólo hay que editar en `_sass/minima/custom-styles.scss`.

Agregué el siguiente código, para reducir el tamaño de la fuente al 75%. 
Hay 3 tipos de ajuste: celdas de código, código inline de markdown y código normal de markdown.

```css
.highlight pre, .highlight code {
    font-size: 75% !important;
}

.input_area pre, .input_area {
    font-size: 75% !important;
}

p code {
    font-size: 75% !important;
}
```

He visto que `!important` se desaconseja, pero bueno, podremos hacer una excepción en virtud del tiempo
y de la humildad de este blog. 