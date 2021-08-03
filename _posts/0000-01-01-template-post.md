---
featured: false
hide: true
toc: false
layout: post
title: Template de entrada de Markdown
description: "Descripcion de la entrada en markdown"
categories: [fastpages, markdown, template]
image: images/logo.png
permalink: /markdown-test/
comments: true
---

## Configuración básica

El archivo de un post files debe tener el formato `_posts/AAAA-MM-DD-some-filename.md`

Donde `AAAA` es el año con 4 dígitos, `MM` es el mes con 2 dígitos, `DD` es el día con 2 dígitos, y `some-filename` es un nombre de referencia, más que nada para recordarte de que se trataba el post. El título real se indica adentro). La extensión `.md` se usa para archivos markdown, como es esperable. El inicio del archivo debe tener los siguiente:
 
```
---
featured: false
hide: false
toc: false
layout: post
title: Template
description: "Descripcion"
categories: [fastpages, markdown, template]
image: images/logo.png
permalink: /markdown-test/
comments: true
---
```

## Formato básico

Se pueden usar *cursivas*, **negritas**, ***negritas cursivas***, `código`. También notas a pie de página [^1]. También una línea horizontal:

---

## Links

Se pueden crear [links](https://www.markdownguide.org/cheat-sheet/) o simplemenente [https://www.markdownguide.org/cheat-sheet/](), (https://www.markdownguide.org/cheat-sheet/).

## Listas

Acá hay una lista (regular):

* item 1
* item 2

Acá hay una lista numerada:

1. item 1
1. item 2

## Código

Texto preformateado general:

    # Do a thing in a programming language
    do_thing()

Código de python:

```python
# Prints '2'
print(1+1)
```

## Imágenes

![]({{ site.baseurl }}/images/logo.png "fast.ai's logo")


## Videos

{% include youtube.html content='https://youtu.be/XfoYk_Z5AkI' %}

## Tablas

| Columna 1 | Columna 2 |
|-|-|
| Una cosa | Otra cosa |
| Una cosa más | Otra cosa más |


## Citas y otras formas de destacar

Citas:
> Esta es una cita

Alerta:
{% include alert.html text="Puedes incluir alertas" %}

Información:
{% include info.html text="Puedes destacar información" %}

Warning:
{% include warning.html content='There will be no second warning!' %}

Important:
{% include important.html content='Pay attention! It&#8217;s important.' %}

Consejo:
{% include tip.html content='This is my tip.' %}

Nota:
{% include note.html content='Take note of this.' %}

## Tweets

{% twitter https://twitter.com/sebastiandres/status/1413114104215113728 %}

## Notas a pie de página

[^1]: Esta es la nota al pie de página.
