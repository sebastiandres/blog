---
featured: true
hide: false
toc: false
layout: post
title: "Fastpages 2: reloaded"
description: "Las grandes ideas nunca mueren."
categories: [fastpages]
image: images/logo.png
permalink: /fastpages2/
comments: true
---

Ya perdí la cuenta de la cantidad de veces que he armado un sitio web para 
publicar posts y jupyter notebook. Esta vez espero ser más constante.
Estuve averiguando sobre como funciona, y acá aprovecho de poner mis notas. 

## ¿Cómo funciona fastpages?

Al crear un blog con fastpages se generan 2 ramas:
* En la rama [master](https://github.com/sebastiandres/blog/tree/master) 
se encuentran los posts en formato markdown, 
jupyter notebooks o word, los archivos de configuración, y distintos 
archivo de html, css y javascript.
* En la rama [gh-pages](https://github.com/sebastiandres/blog/tree/gh-pages) 
se encuentra únicamente el html que se genera 
a partir del contenido de la rama master, y que se despliega como 
una página web en `<username>.github.io/<repository-name>` 
gracias a Github Pages (sino, se vería como el clásico repositorio de código).

Cuando haces push de un cambio a master, se ejecutan automáticamente 3 acciones
mediante github actions:
1. `check_config.yaml`: Revisa que los archivos de configuración 
sean consistentes y tengan la información necesaria. Esto toma usualmente unos 15 segundos.
2. `ci.yaml`: Toma unos 90 segundos en completar los siguientes pasos.
  * Crea un ambiente linux donde se realizarán todas las operaciones. 
  * Chequea que tengas permiso hayas definido `SSH_DEPLOY_KEYS`
  * Descarga la ultima versión del repositorio (la versión que recien pusheaste) de la rama master.
  * Convierte a markdown todos los archivos de jupyter notebook y word.
  * Descarga el tema de Jekyll `minima` para tener todos los html, css y javascript necesarios. 
  * Usa Jekyll para convertir todos los markdowns a páginas web con el tema `minima`.
  * Copia el html generado a la rama gh-pages.
3. `gh-pages.yaml`: Revisa que todo se haya generado correctamente (creo).

## Personalizando la página principal

Para personalizar la página principal, basta con modificar `./index.html`.
La página principal que se verá en el sitio web se genera de manera encadenada. 
En `index.html` se define que se usará el layout `home.html`, 
que a su vez define que usará el layout `default.html`.
Es posible modificar `./layouts/home.html` tomará el texto de ./index.html y lo convertirá 
de markdown a html, y le agregará un contenido adicional. 

## Personalizando el favicon

El favicon se puede modificar reemplazando directamente `images/favicon.ico`, o bien,
editando el archivo `_includes/favicons.html` para definir una ruta diferente. 

Es posible generar un favicon de manera gratuita en [realfavicongenerator](https://realfavicongenerator.net/).

## Agregar nuevas páginas

Para agregar nuevas páginas, basta con agregar los archivos en la carpeta `_pages`.
Los archivos agregados pueden ser html o markdown, pero tienen la misma estructura:

```markdown
---
layout: default
permalink: /desired-path/
title: Desired Name
search_exclude: true
---

SOME TEXT IN HTML OR MARKDOWN
```

El layout debe ser default o uno de los layouts definidos en la carpeta `_layouts`. 
Se puede usar html o markdown, según lo que sea más conveniente usar.
