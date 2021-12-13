---
featured: true
hide: false
toc: false
layout: post
title: "Graficando emojis"
description: "Resumen de un googleo interminable"
categories: [python, comunidad, pycon]
image: images/preview/python.png
comments: true
---

Hace poco necesitaba mezclar un gráfico de líneas con un emoji. Googlee hasta el cansancio, 
pero las soluciones no me funcionaban correctamente. Despues de probar muchísimas opciones, 
el código que si me funcionó fue el siguiente:

```python
def plot_emoji(emoji_path, ax, x, y, zoom=0.35):
    """
    Plots an emoji on a figure.
    Based on:
    https://www.geeksforgeeks.org/emojis-as-markers-in-matplotlib/
    image_path: path to the image
    ax: axis to plot on
    x: x coordinate
    y: y coordinate
    zoom: zoom factor (resizing)
    """
    # reading the image
    image = plt.imread(emoji_path)
    # OffsetBox
    image_box = OffsetImage(image, zoom=zoom)
    # Drawing the image
    ab = AnnotationBbox(image_box, (x, y), frameon=False)
    ax.add_artist(ab)
    return
```

No permite usar directamente un emoji, pero sí cualquier imagen.
