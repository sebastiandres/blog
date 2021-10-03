---
featured: false
hide: false
toc: false
layout: post
title: "Compartir tu código en python"
description: "Revisión de las muchas alternativas"
categories: [python, compartir]
image: images/preview/python.png
comments: true
---

Aparte de mis herramientas favoritas de jupyter notebook y streamlit, existen otras alternativas. Esta es una lista preliminar de enumerarlas y compararlas.

### Repositorio en línea
La versión más básica para compartir tu código (ya sea python, jupyter notebook u otros) es simplemente almacenarlo en un repositorio en línea, como [github](https://github.com/), [bitbucket](https://bitbucket.org/) u otros. Tiene la ventaja de entregar todo el detalle, con el copyright o copyleft que deseas, pero el usuario tiene que tener los conocimientos para poder instalarlo y probarlo.

### Jupyter Notebooks en línea
Otra opcion para compartir código de python es incluirlo en un jupyter notebooks. La opción más común es tener instalado Jupyter Notebook/Lab en local y así ejecutar los notebooks, pero han surgido muchas alternativas para compartirlas en línea. Algunas de las opciones más comunes son: [binder](https://mybinder.org/) o en [Google Colab](https://colab.research.google.com/). Existen otras alternativas que funcionan como los notabooks, como [Kaggle Kernels](https://www.kaggle.com/kernels), [CoCalc](https://cocalc.com/) o [Datalore](https://datalore.jetbrains.com/) pero no los conozco en profundidad. 

### Desarrollo web y API
Para desarrollo web y apis existen múltiples alternativas:
* [falcon](https://falconframework.org/): Un framework para construir APIs (+9 años) 
* [FastAPI](https://fastapi.tiangolo.com/): Otro framework web para construir APIs, más reciente (+3 años) y creciente popularidad.
* [web2pi](http://www.web2py.com/): Un framework web inspirado por Ruby on Rails y Django (+13 años). No conozco a nadie que lo use.
* [bottle](https://bottlepy.org/): Un framework web minimalista pero extensible, con +12 años de desarrollo. 
* [flask](https://flask.palletsprojects.com/en/2.0.x/): Un framework web minimalista pero extensible, con +11 años de desarrollo. ¿Similar a bottle? Si, mucho. A pesar de ser más reciente e inspirarse en su hermano, Flask es mucho más popular. 
* [pyramid](https://trypyramid.com/): framework web que busca situarse entre los micro-frameworks y los mega-frameworks: un framework que permite comenzar pequeño pero escalar sin problemas de ser necesario.
* [Django](https://www.djangoproject.com/): un framework web completamente pythonistico con esquema modelo–vista–controlador (MVC), y con +15 años de desarrollo. No es simple, pero tiene todo lo necesario para competir con frameworks "famosos" de otros lenguajes.

### Dashboards, Web apps y data apps
Entre el desarrollo web y los jupyter notebooks existe un fértil campo de frameworks y librerías para hacer dashboards y webapps. La idea es que puedas crear y compartir la interactividad generando poco código **adicional** al necesario para tu código base:
* [Plotly](https://plotly.com/) y [Dash](https://plotly.com/dash/)
* [Voila](https://voila.readthedocs.io/en/stable/using.html)
* [Gradio](https://www.gradio.app/)
* [Panel](https://panel.holoviz.org/)
* [Streamlit](https://streamlit.io/): permite generar páginas web interactivas de manera simple e intuitiva. Se hace un tradeoff de flexibilidad por simpleza y diseño predefinido.

Por ahora conozco poco de los primeros, pero espero actualizar esta lista con más detalles pronto.