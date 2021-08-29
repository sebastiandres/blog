---
featured: true
hide: false
toc: false
layout: post
title: "PyCon Latam 2021"
description: "Mi tercera PyCon"
categories: [notebook, rise, pycon]
image: images/preview/pylatam.jpg
comments: true
---

Acabo de terminar mi charla en la PyCon Latam 2021, y fue una gran experiencia. 
A diferencia de otras oportunidades, estaba relajado y disfruté muchísimo dar la charla.
Creo que la diferencia tuvo que ver con la preparación. Aunque ya sabía bastante, 
había aprendido muchísimo más en las últimas semanas preparando el tutorial de RISE que publiqué en el blog.
Así que ya tenía todo el material a mano, y fue fácil armar las diapositivas.

![]({{ site.baseurl}}/images/2021-08-28-pylatam/hubilo.png "PyCon Latam 2021")

En la PyCon utilizamos la plataforma hubilo.com que me gustó mucho, fue fácil de utilizar y no tuve
complicaciones durante el evento. Un tremendo esfuerzo del equipo organizador, porque tuvieron que cambiarse
a última hora de la plataforma que tenían considerada últimamente.

![]({{ site.baseurl}}/images/2021-08-28-pylatam/setup.jpg "Setup para la PyCon Latam 2021")

Algunas de las cosas que aprendí específicamente para esta presentación fueron: 
* Porqué se llama RISE: Reveal.js IPython Slideshow Extension
* Utilizar `_repr_html_` para tener una representación nativa para los jupyter notebook, 
* A ocultar los botones con `,`, y a usar header y footer con propiedades de html.
* A hacer animaciones más complejas con `<p class="fragment">Mi texto</p>`, al igual que en [revealjs](https://revealjs.com/)
* A ocultar código con un botón.

La presentación en sus distintas formas de visualización se encuentran acá: [Slides pylatam](https://sebastiandres.github.io/talk_2021_08_pylatam/)
