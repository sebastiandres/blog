---
featured: false
hide: false
toc: false
layout: post
title: "Nuevo favicon"
description: "De python a sebastiandres en 1 paso."
categories: [fastpages, favicon]
image: images/2021-08-04-favicon/preview.png
comments: true
---

Ya había reemplazado el favicon del sitio, pero no me terminaba de convencer.
Hoy mirando el logo de python me di cuenta que podía facilmente transformarse en una S,
que me pareció muy adecuado para un favicon simple pero memorable. 

![]({{ site.baseurl}}/images/2021-08-04-favicon/transformacion.png "Transformación del logo de python al favicon")

La imagen final tiene algunos detalles en los bordes, pero no es relevante
dado que al convertirlo a favicon se reduce enormemente el tamaño.

![]({{ site.baseurl}}/images/2021-08-04-favicon/preview.png "Favicon obtenido")

Hay varios servicios para generar un favicon a partir de una imagen, en este caso obtuve mejores resultados con [favicon.io](https://favicon.io/).

El favicon se puede modificar reemplazando directamente `images/favicon.ico`, o bien,
editando el archivo `_includes/favicons.html` para definir una ruta diferente. 

**Test final**: el siguiente texto con 80 chars debería verse completo...

```
123456789 123456789 123456789 123456789 123456789 123456789 123456789 123456789 
```