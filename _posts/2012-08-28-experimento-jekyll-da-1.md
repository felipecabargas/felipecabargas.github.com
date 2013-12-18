---
date: "2012-08-28 12:30"
layout: post
title: "Experimento Jekyll: Día 1"
description: ""
categories:
  - Jekyll
tags:
  - blog
  - jekyll
  - ruby
---
Vamos bien por hoy, estoy corrigiendo el tema de las imágenes de los post anteriores para poder dejar de usar el "blog original" dentro de esta semana.

[![][3]][3]

La idea también es corregir las líneas de código que hay a lo largo de los post debido a que el remarcado es distinto al de WordPress y el Plugin de importación que usé [WordPress to Jekyll Exporter][1] no hace la pega con el 100% de exactitud.

Les cuento cosas entretenidas, por ejemplo para hacer links lo que se debe hacer es básicamente esto:

{% highlight text %}
[descripción link][1]
{% endhighlight %}

y al final del archivo debes agregar una línea así:

{% highlight text %}
 [1]: http://urldedestino.com
{% endhighlight %}

Otra cosa curiosa es el manejo de categorías, en Jekyll si pongo "Off-Topic" y "Vida diaria" en la info del post cuando lo redacto, lo que se crea es una categoría jerarquizada "Off-Topic/Vida diaria" por eso si van a [CATEGORIES][2] se darán cuenta que hay demasiadas categorías de esta manera producto del uso de más de una categoría en WordPress originalmente.

Espero que vayamos aprendiendo un poco todos con quienes lean este post, y cualquier duda comente o mandeme un email (:

**EDIT:** Acabo de arreglar el tema de las categorías, ya no se verán tantas pero se entiende el mote de como se hace.

 [1]: https://github.com/benbalter/wordpress-to-jekyll-exporter
 [2]: http://blog.cabargas.com/categories.html
 [3]: http://cabargas.com/images/jekyll-dia1.png