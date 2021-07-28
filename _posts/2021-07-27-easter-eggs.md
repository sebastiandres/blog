---
featured: false
hide: false
toc: false
layout: post
title: "Easter Eggs"
description: "Customizando fastpages."
categories: [fastpages]
image: images/monty-python-pig.png
permalink: /fastpages-easter-eggs/
comments: true
---

Para conocer un poco más del funcionamiento de fastpages, decidí personalizar
un poco el sitio. Tenía ganas de agregarle algo divertido, así que 
me decidí por agregarle un toque absurdo a lo Monty Python. 

## 404

La [página 404]({{ site.baseurl }}/404.html) (página no encontrada) fue fácil de personalizar. 
Bastó editar el archivo `_pages/404.html`, y agregarle una nueva imagen.

## Pie animado

Un desafío mayor fue agregar un pie animado que se moviera sin mover otros elementos.
Para ello, tuve que generar un css específico:

```html
img.monty-python-foot {
    position: absolute;
    top: -900px;
    z-index: 99;
    animation: move_down 4s;
}

@keyframes move_down {
    0% { transform: translateY(-1200px); }
    50% { transform: translateY(800px); }
    100% { transform: translateY(-1200px);
    }
}
```
Luego, en las páginas donde quisiera aplicarlo, bastaba con agregar una imagen
con la clase respectiva:

```html
<img src="{{ site.baseurl }}/images/monty_python_foot.png" height=800px class="monty-python-foot" />
```

El resultado puede verse en algunas de las páginas del sitio, es cosa de buscar.