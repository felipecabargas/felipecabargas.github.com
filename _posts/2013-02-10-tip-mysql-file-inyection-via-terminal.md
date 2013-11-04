---
author: juanpintoduran
title: '[TIP] Importar archivos *.sql desde la terminal'
excerpt:
layout: post
categories:
  - Hacking
tags:
  - edoome
  - Trabajo
post_format: [ ]
---

Cuando se trabaja con bases de datos y servidores dentro del PC de cada uno, lo que sin duda es agradable cuando de ambientes de desarrollo se trata pero que sin embargo está sujeto a la inestabilidad propia de un computador personal.

Es en estos casos que los respaldos de las consultas SQL en archivos *.sql son fundamentales... Sin embargo y como muchos sabemos, no es del todo agradable estar siempre importando los archivos sql en GUIs como phpMyAdmin uno por uno y lidiar con las limitaciones que el archivo php.ini viene por defecto.

Así, es como llegamos a el siguiente comando, que permite importarlos de manera más fácil y cómoda:

{% highlight bash   %}
felipe@afcm-linux $ mysql -u root -p database < path/to/file.sql
{% endhighlight %}

Simplemente basta con reemplazar el user (root) la base de datos objetivo (database) y la ruta hacia el archivo.sql

Éxito (!)