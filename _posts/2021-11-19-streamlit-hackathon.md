---
featured: true
hide: false
toc: false
layout: post
title: "Streamlit hackathon"
description: "Capitalizando la PyCon Chile"
categories: [balance, cuenta, reflexión]
image: images/preview/2021-11-19-streamlit.png
comments: true
---

Hace unas semanas, el equipo detrás de streamlit me invitó a participar a una hackathon con temática de educación. Todo se lo debo a la visibilidad que logró la presentación que hice en la PyCon Chile, donde las diapositivas mismas de la presentación estaban hechas en streamlit, y fue destacado por streamlit en twitter. Me siento muy halagado de que me hayan invitado a participar.

La participación se ha desarrollado más que nada en un canal dedicado en el slack del equipo de streamlit, y en una página de notion donde están las explicaciones y los equipos. Notion funciona increíblemente bien para textos colaborativos, y el hecho de poder crear templates automáticos y enlazados es maravilloso.

El viernes 19 de noviembre fue la presentación de proyectos de la hackathon. Los proyectos tenían un gran nivel, me sorprendieron mucho. Una app que se mostraba en streamlit todo lo que se escribía en un archivo de notion, otra que generaba una app de streamlit a partir de una descripción usando codex, y otros que analizaban datos de la bolsa o criptomonedas.

Mi proyecto consistió en crear una librería, que llamé streamlit-book, que permite navegar archivos python+streamlit y markdown, además de definir un formato para realizar quizzes y actividades (en markdown y python) usando los elementos de streamlit. Mi objetivo era crear una forma de usar streamlit para crear y distribuir contenido de un curso.

¡Puedo comentar con orgullo que compartió el primer lugar de la hackathon!

![]({{ site.baseurl }}/images/2021-11-19-streamlit-hackathon/hackathon.png "Hackathon")

Desde entonces, he estado trabajando en empaquetar todo y dejarlo completamente funcional: 
* La librería ya está disponible en pypi y es instalable por pip.
* La librería tiene documentación en [readthedocs](https://streamlit-book.readthedocs.io).
* Estoy escribiendo un mini-tutorial (en inglés) para que streamlit pueda usarlo y difundir así mi trabajo. Lo hice pensando en explicar algo sencillo, con gráficos y que fuera divertido: Happy birds.

Algunos aprendizajes de la hackathon: 
* Me entretuve mucho escribiendo código. Es algo que debo hacer con mayor frecuencia. Programar con GitHub's Copilot además me hizo muy productivo, por momentos entendía perfectamente la intención y completaba muy bien el código. Hay un potencial increíble ahí. Seguro que el paso de asembly a C, y de C/C++ a python debe haber sido un salto conceptual similar (aunque menor). 
* Trabajar solo hace que no cuestiones tus decisiones. Acordar un formato, discutiendo pros y contras, me hubiera ayudado a no tener tantas dudas y cambios durante el proyecto.

El destino de la librería quizás sea similar al resto de mis +70 repositorios en github, con poco tráfico y más centrados en mi aprendizaje personal... pero nunca se sabe, ¡ojalá alguien la pueda aprovechar!