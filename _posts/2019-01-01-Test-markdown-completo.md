---
toc: true
description: Ejemplo usando markdown con fastpages.
categories: [fastpages, markdown]
comments: true
---
# Test 1: Post mediante Markdown

## Configuración básica

Un blog post files debe tener el siguiente formato:

`AAAA-MM-DD-filename.md`

Donde `AAAA` es el año con 4 dígitos, `MM` es el mes con 2 dígitos, `DD` es el día con 2 dígitos, y `filename` es un nombre de referencia para recordarte de que se trataba el post (el título real se indica adentro). La extensión `.md` se usa para archivos markdown.

La primera línea del archivo debe comenzar con `# Mi título` para que se defina "Mi título" como el título del post. Dentro del post, se pueden hacer subtítulos `## Mi subtítulo` (y sub-subtítulos, `### Mi sub-subtítulo`, pero ya es desaconsejado.)

# Configuración avanzada

Para agregar una descripción, categorías (etiquetas/tags), y toc (table of contents - tabla de contenidos) es necesario agregar un contenido específico encerrado por `---`. Por ejemplo, las primeras 10 líneas de este post son las siguientes:

```
---
toc: true
description: Ejemplo usando markdown con fastpages.
categories: [fastpages, markdown]
comments: true
---
# Test 1: Post mediante Markdown

## Configuración básica

Un blog post files debe tener el siguiente formato:

```

Para desactivar la funcionalidad basta con eliminarla o dejarla vacía.

## Formato básico

Se pueden usar *cursivas*, **negritas**, ***negritas cursivas***, `código`. También notas a pie de página [^1]. También una línea horizontal:
---

´´´
Se pueden usar *cursivas*, **negritas**, ***negritas cursivas***, `código`. También notas a pie de página [^1]. También una línea horizontal:
---
´´´

## Links

Se pueden crear [links](https://www.markdownguide.org/cheat-sheet/) o simplemenente [https://www.markdownguide.org/cheat-sheet/](), (https://www.markdownguide.org/cheat-sheet/).

´´´
Se pueden crear [links](https://www.markdownguide.org/cheat-sheet/) o simplemenente [https://www.markdownguide.org/cheat-sheet/](), (https://www.markdownguide.org/cheat-sheet/).
´´´

OBS: Siempre se me olvida el orden. Regla nemotécnica "cuasi = no es" (CUACI NOE): cuadrado antes de círculo, nombre antes de enlace.

## Listas

Acá hay una lista (regular):

* item 1
* item 2

Acá hay una lista numerada:

1. item 1
1. item 2

´´´
Acá hay una lista (regular):

* item 1
* item 2

Acá hay una lista numerada:

1. item 1
1. item 2
´´´

## Código

Texto preformateado general:

    # Do a thing in a programming language
    do_thing()

Código de python y su salida:

```python
# Prints '2'
print(1+1)
```

    2

```
Texto preformateado general:

    # Do a thing in a programming language
    do_thing()

Código de python y su salida:

```python
# Prints '2'
print(1+1)
```

    2
```

## Imágenes

![]({{ site.baseurl }}/images/logo.png "fast.ai's logo")

```
![]({{ site.baseurl }}/images/logo.png "fast.ai's logo")
```

## Videos

{% include youtube.html content='https://youtu.be/XfoYk_Z5AkI' %}

```
{% include youtube.html content='https://youtu.be/XfoYk_Z5AkI' %}
```

## Tablas

| Columna 1 | Columna 2 |
|-|-|
| Una cosa | Otra cosa |
| Una cosa más | Otra cosa más |

```
| Columna 1 | Columna 2 |
|-|-|
| Una cosa | Otra cosa |
| Una cosa más | Otra cosa más |
```

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

Tip:
{% include tip.html content='This is my tip.' %}

Nota:
{% include note.html content='Take note of this.' %}

```
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

Tip:
{% include tip.html content='This is my tip.' %}

Nota:
{% include note.html content='Take note of this.' %}
```


## Tweets

{% twitter https://twitter.com/jakevdp/status/1204765621767901185?s=20 %}

```
{% twitter https://twitter.com/jakevdp/status/1204765621767901185?s=20 %}
```

## Notas a pie de página

[^1]: Esta es la nota al pie de página.

```
[^1]: Esta es la nota al pie de página.
```
