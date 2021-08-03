---
featured: false
hide: true
toc: false
layout: post
title: "PaaS: Python as a Service"
description: Entregando python en la nube, más fácil que nunca.
categories: [opinión, startup, tecnología]
image: images/2020-07-25-python-as-a-service/paas.gif
comments: true
---

La tecnología cambia y nos trae muchas ventajas. Pero el volumen de conocimiento a manejar se ha vuelto enorme: python, ipython, jupyter notebooks y sus librerías por un lado, y por el otro lado, servidores, kubernetes, y un sin fin de siglas. Aquellos que saben de todo esto pueden sacarles el mejor provecho pero… ¿cómo podemos disponibilizar todas estas tecnologías a un usuario que no sabe ni necesita conocer de todo esto?

## ¿Existe alguna forma de entregar PaaS: Python as a Service?

Sí. Hay una forma que resulta sencilla tanto para el usuario como para el desarrollador.

## ¿Qué buscamos para el usuario?

La forma más sencilla para un eventual usuario, es crear una librería permita instalarse con pip:

```
pip install la_libreria_que_hice_con_mucho_esfuerzo
```

De esa manera un usuario podría usar la librería con jupyter notebook, sin instalar nada en local, con mybinder o google colab. ¡Hasta podría usarlo desde un tablet o celular!

Un ejemplo sencillo: **calculando quién es el próximo en estar de cumpleaños**.

Tengo buena memoria para algunas cosas, pero los cumpleaños no se cuentan entre esas cosas. Es un problema familiar, y probablemente a más de alguno le podría servir un recordatorio. Con un código en python muy sencillo podría implementar una función que muestre quienes son las próximos 3 personas en estar de cumpleaños y calculara la edad que van a cumplir.
¿Cómo podría compartir ese código con mi familia?

¡Muy simple! Con [MyBinder](https://mybinder.org/v2/gh/sebastiandres/family_birthdays/master?filepath=tests%2Fjupyter_test.ipynb) o [Google Colab](https://colab.research.google.com/drive/1XnruLOcG39i4SrQSSy9rnHIQ3RsQJdJr?usp=sharing).

La situación sería tan fácil como se muestra en el siguiente gif.

![]({{ site.baseurl }}/images/2020-07-25-python-as-a-service/paas.gif "MyBinder carga el jupyter notebook, donde se instala la librería que hemos creado y ya se puede ejecutar.")

Es posible configurar MyBinder (pero no en Google Colab) para que la librería ya venga instalada por defecto.

## ¿Qué tiene que hacer el desarrollador?

Hay varias cosas que necesitamos tener para poder proveer un servicio fácil a los usuarios:
* Librería instalable por pip: requiere definir un archivos setup.py y configurar una estructura de carpetas adecuadamente. El código podrá instalarse desde pypi (oficial, estable) y github (edge).
* Usar git: permite mantener versiones del código y hacer incrementos de código.
* Interface simple: Esconder la complejidad del código con orientación a objetos, exponiendo sólo lo estrictamente necesario.
* Guardar parámetros: cuando todo falla, permite debuggear rápidamente (y reproducir las condiciones de ejecución). En el caso anterior, me sirvió para darme cuenta que Google Colab usa python 3.6.9 y por eso no estaban disponibles ciertas funciones recientes de la librería estándar datetime.
* Documentación: para usuarios más avanzados y para documentar la librería.

## ¿Cómo funciona?

Empaqueté todo lo anterior en una librería que sirve como framework de trabajo, que basta con descargar y personalizar.
La librería está en [github](https://github.com/sebastiandres/GenericSimulationLibrary) y acá está la [documentación](https://readthedocs.org/projects/generalsimulationlibrary/).

En resumen, el framework tiene preconfiguradas buenas prácticas, librerías y recursos que permiten cumplir con pip, git, interface simple, documentación y guardar parámetros, al menos de la forma más minimal posible.
