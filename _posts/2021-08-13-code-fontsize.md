---
featured: false
hide: false
toc: false
layout: post
title: "Cambiando fontsize de código"
description: "Más personalización en fastpages"
categories: [fastpages, css]
image: images/preview/fastpages.png
comments: true
---

La configuración por defecto de fastpages para el código no es de mi agrado.
Me molestaba que incluso cuando la línea no es muy larga se ocultaba gran parte del código.

Esto ocurre  porque el tamaño de la fuente es mayor que la del texto. 
Al mirar el css, se ve que los textos de código están definidos como el 
105% o 110% del tamaño normal de la fuente.
Yo pensaría que debe ser al revés: el código está para ser mirado pero no analizado en profundidad.  
Si lo desea, alguien descargará el código y lo revisará en su editor de peferencia. 
Es mejor que se vea todo el código, a que haya que hacer scroll.

¿Qué tan difícil es el cambio?

Googleando llegué a la siguiente [respuesta](https://forums.fast.ai/t/fastpages-how-to-change-font-size/67095) 
donde se explica que es necesario editar el archivo `_sass/minima/custom-styles.scss`.

Agregué el siguiente código, para reducir el tamaño de la fuente al 75%. 

```css
code {
    font-size: 75% !important;
}

pre {
    font-size: 75% !important;
}
```

He visto que `!important` se desaconseja, pero bueno, podremos hacer una excepción en virtud del tiempo
y de la humildad de este blog. 

**Test final**: el siguiente texto con 80 chars debería verse completo...

```
123456789 123456789 123456789 123456789 123456789 123456789 123456789 123456789 
```

¡Funciona!