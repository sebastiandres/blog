---
featured: true
hide: false
toc: false
title: Keynotes de la PyCon 2020 Colombia
description: Videos, slides y resúmenes. 
layout: post
categories: [pycon, keynote]
comments: true
---


> “Came for the language, stayed for the community” - Brett Cannon

Todos los keynote speakers recalcaron la importancia del trabajo en equipo y la colaboración de la comunidad de Python, como refleja la frase de Brett Cannon de la PyCon US del 2014. Los principales elementos comunes fueron:
1. **Comunicación, inclusión y mentoring**: La comunidad de python es un ejemplo de que la colaboración puede más que la competencia. Andrew mencionó la importancia de una buena comunicación entre equipos de ingeniería. Fernando habló del valor de la comunidad y de haber tenido buenos mentores. Emily mencionó lo importante de tener una comunidad receptiva y que potencie nuevos miembros.
2. **Documentación y respaldos**:La documentación es crucial para facilitar la colaboración de las comunidades, y para respaldar hacia el futuro: lo que no se documenta se pierde. Emily mencionó que “Documentar es ahorrar dinero”, y que es un esfuerzo necesario. Esto lo mencionó también Nick Sweeting en una charla: damos por sentado que todo lo que leemos hoy estará disponible en todos lados y en el futuro. Respaldar es importante.
3. **Sobre el fracaso**: Todos tenemos nuestros fracasos. Hacerlos visibles es importante para mostrar a otros que es normal, y que forma parte del crecimiento y aprendizaje. Fernando mencionó ejemplos de sus fracasos (desconectar el internet en todo Colombia, un curso práctico de computación fallido). Emily habló de sus inseguridades, la falta de confianza para abordar desafíos y de la necesidad de salir de la zona de confort.

## Andrew Godwin [@andrewgodwin](https://twitter.com/andrewgodwin)
The Scientist and the engineer: [slides original](https://speakerdeck.com/andrewgodwin/the-scientist-and-the-engineer) / [slides respaldo](https://drive.google.com/file/d/1bfZAgeNa4vkB6MDGQF7ZuVXd27pvmA61/view?usp=sharing)

<center>
<iframe width="600" height="400" src="https://youtube.com/embed/862xL6jm_PQ" frameborder="0" allowfullscreen></iframe>
</center>

* **TLDR;** Los sistemas actuales son demasiado grandes para una sola persona. La comunicación y delegación son parte crucial de la ingeniería.
* *“Computer science is no more about computers than astronomy is about telescopes”* — Edsger Dijkstra.
* *“In theory there is no difference between theory and practice.
In practice there is”* — Benjamin Brewster.
* *“A ship in port is safe, but that’s not what ships are built for”*— Grace Hopper
* The real world is messy. Cosmic ray affects RAM and quantum tunneling affects CPUs. Python is a balanced language to deal with a messy world.
* Learn when and how to forget. You can’t remember all the details all the time. Besides, it’s inefficient. Abstract - Verify - Forget.
* Scientists observe and question: They are always asking “why?” and “how?”. Engineers build and invent: they look at a question and think of solutions. Be the scientist and the engineer: Model your systems. Ask the tough questions. Build them for the real world.

## Sarah Guido [@sarah_guido](https://twitter.com/sarah_guido)
Data Science Retrospective: [slides original](https://www.slideshare.net/SarahGuido/data-science-retrospective) / [slides respaldo](https://drive.google.com/file/d/19dlfJCQoE3DFU7IVf6GpnMJpl_P9634H/view?usp=sharing)

<center>
<iframe width="600" height="400" src="https://youtube.com/embed/Apsrm8tiV54" frameborder="0" allowfullscreen></iframe>
</center>

* **TLDR;** La industria siempre creará hype. Lo que no cambia (ni cambiará) es que los datos nunca serán perfectos.
* What’s the definition of Data Science? Using data to drive business outcomes!
Specialized roles are now required: data engineer, machine learning engineer, business intelligence engineer, data analyst, decision scientist, data science engineer, product scientist and more.
* Learning data science has evolved. Before: no college programs, few bootcamps, early days for Coursera, Codecademy, etc. Today: Lots of free & open source material, (too) many bootcamps and university programs, not so free resources like Coursera, documentation has improved.
* Lots of new and cool tools: docker, spark, AWS cloud tools, Zeppelin, Sagemaker, dasboarding tools (Looker, Mode, Periscope, Amplitude). Most tools have a python API!
Job offers for data science ask for: Python or R, SQL, basic knowledge of statistics and Machine Learning, data intuition, ability to communicate and to be independent. Communications is a must.
* Data in the wild is still messy: and that’s not ever going to change.

## Wes McKinney [@wesmckinn](https://twitter.com/wesmckinn) 
Python for Data Analysis: Past, Present, and Future: [slides original](https://www.slideshare.net/wesm/pycon-colombia-2020-python-for-data-analysis-past-present-and-future) / [slides respaldo](https://drive.google.com/file/d/1Gzcwg1Pew1GAEuzz3itpM_FiFer2zqOt/view?usp=sharing)

<center>
<iframe width="600" height="400" src="https://youtube.com/embed/ZTXFQ2sEarQ" frameborder="0" allowfullscreen></iframe>
</center>


* **TLDR;** El crecimiento de python se debe a una tormenta perfecta de librerías, y el éxito de pandas a que puede leer csv (entre otras cosas).
* Pandas first version still at Pypi: [https://pypi.org/project/pandas/0.1/](https://pypi.org/project/pandas/0.1/).
* Wes is no longer working on pandas since 2013, don’t insist!
Python growth is due to several things, pandas being one of them. There was the need of data wrangling, and there was a “perfect storm” of packages. And packaging of libraries was improved.
* The success of pandas, mostly due to being able to read csv.
Python being readable makes everyone can contribute. The new pandas logo is an example of non cs contributions with huge impact
See: [“PyData NYC 2013: 10 Things I Hate About pandas”](https://www.slideshare.net/wesm/practical-medium-data-analytics-with-python)
* Pandas has taken responsability of too many things. It is more productive to have a common computational framework to . This is why
Apache Arrow is “a common standard designed for speed, for data processing libraries”.  It should be CPU/GPU friendly, memory map huge datasets, and relocate data structures without serialization.
* Reflexión personal: en 10 años parecerá natural que exista un estándar para dataframe data. ¿Se imaginan lo complejo e ineficiente que sería si cada lenguaje manejara un estándar distinto de chars, enteros y flotantes?

## Ines Montani [@_inesmontani](https://twitter.com/_inesmontani)
The Future of NLP in Python: [slide original](https://speakerdeck.com/inesmontani/the-future-of-nlp-in-python-keynote-pycon-colombia-2020) / [slide respaldo](https://drive.google.com/file/d/1z1ErZYM_3L8NiQHlJGJOZBIqpSHMi_pz/view?usp=sharing)

<center>
<iframe width="600" height="400" src="https://youtube.com/embed/YDAgQO1DX0Q" frameborder="0" allowfullscreen></iframe>
</center>

* **TLDR;** Lo más dificil es tener buenos sets de datos. Es necesario crear software que nos ayude con eso.
* Skills are tree shaped: There’s overlap and branches can grow into empty spaces.
* spaCy: Open-source library for industrial-strength Natural Language Processing.
* Prodigy: Annotation tool for creating training data for machine learning models.
* Thinc: Lightweight deep learning library for composing models with a functional type-checked API
* Why python? general purpose better than specialized “AI language” & easier for developers. Your team needs specialist, generalists and complementary.
* Problem 1: Connecting layers in DL is hard. Matrix dimensions must match, and it’s not straightforward. Thic allows to simplify to unblock developer experience to unlock productivity.
* Problem 2: Dependencies and configuration is a nightmare. You need to close the gap between prototype & production.
* Problem 3: We needed something so we built it.
* Problem 4: It all depends on the data. It’s better to pay someone on your team to precisely gather/create the data you need. Move fast and train things. Have several models and choose based on results.

## Emily Morehouse [@emilyemorehouse](https://twitter.com/emilyemorehouse)
We go further together: [slide original](https://drive.google.com/file/d/1KZeyDkd-UphbHOWi_kv9KkN83mnDUU9s/view) / [slide respaldo](https://drive.google.com/file/d/1bwv7hLyo09J2aP1nnGu7LypxJac2A758/view?usp=sharing)

<center>
<iframe width="600" height="400" src="https://youtube.com/embed/TSphDJdco8M" frameborder="0" allowfullscreen></iframe>
</center>

* **TLDR;** nadie es perfecto todo el tiempo, incluso los python core developers tienen dudas y han superpuesto al síndrome del impostor. Todos pueden contribuir, y la documentación está subvalorada.
* Walrus operator := allows to assign and return value. This was hugely polemic. People are afraid to change. But people is the community.
* If you’re bored in tech, you’re not working on the right things.
* Writing documentation is hard! You have the bias of not having fresh eyes.
* Time is money. Documentation saves time. Ergo, documentation saves money.
* Mentoring is crucial. Reach out to others, and to overcome impostor syndrome.

## Fernando Perez [@fperez_org](https://twitter.com/fperez_org)
Jupyter, física y comunidades abiertas: [slides original](https://docs.google.com/presentation/d/1KAvDHwslapwO4l98M0HWRjyHEsGxzVFVT2tX_6e1dPQ) / [slides respaldo](https://drive.google.com/file/d/1eBAYRkIZ-IX-bZnGgnSv9IWxVK5hkBh_/view?usp=sharing)

<center>
<iframe width="600" height="400" src="https://youtube.com/embed/XFynShM1xLU" frameborder="0" allowfullscreen></iframe>
</center>

* **TLDR;** El trabajo en comunidad es muy importante. La comunidad de python y de python científico comparten valores y han aprendido de manera recíproca.
Fernando desconectó un cable para prestarlo y dejó sin internet a toda Colombia por algunas horas.
* La gente se sorprende de la comunidad de python: mucha colaboración, no hay envidias ni competencias, a diferencia de conferencias de otras áreas.
* IPython partió como un hack de una tarde, y se juntó con otros 2 proyectos que tenía funcionalidades similares (Interactive Python, Lazy Python).
* Mail original anunciando IPython: [link](https://mail.python.org/pipermail/python-list/2001-December/093408.html)
* Fue crucial encontrar apoyo y colaboradores en el camino: Eric Jones (Enthought), Scipy, John Hunter (matplotlib), Tarvis Oliphant (numpy — scipy), Wes McKinney (pandas) y muchos más, además del apoyo de la comunidad de python (Guido et al.).
La comunidad de python científico persigue los ideales de la ciencia: (1) la búsqueda de conocimiento verificable (2) reproducibilidad (3) esfuerzo colectivo en beneficio de la humanidad.
* Toda contribución tiene valor, y las necesitamos a todas: diversidad geográfica, cultural, lingüística, etc!
* ¿Impacto generado? Agujeros negros! LIGO 2015 (Nobel 17), primera imagen de un agujero negro 2019 (Nobel ?).
* Cool stuff: Pangeo — volúmenes ridículamente grandes de datos geológicos, ICESat (icepyx), simpeg, GeoSci.xyz, JupyterBook, cursos de ciencias de datos en Berkeley +2000 alumnos simultáneos,
* Hay un libro sobre como usar Jupyter como herramienta pedagógica: [libro](https://jupyter4edu.github.io/jupyter-edu-book/).