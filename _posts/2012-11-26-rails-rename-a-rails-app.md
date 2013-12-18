---
author: juanpintoduran
title: '[HACKING] Renaming a Rails app'
excerpt:
layout: post
categories:
  - Hacking
tags:
  - Hackathon
  - AngelHackSCL
  - BikeTripin
post_format: [ ]
---

[![][1]][1]

Estando en el AngelHack y mientras levantabamos el proyecto -PRONTO MÁS NOVEDADES- con mi partner Federico nos vimos en el problema de encontrar un buen nombre (y en ingles) que reflejara de manera directa lo que queríamos y que además cumpliera con el requisito de estar disponible como dominio '.com' así que generé la app con el nombre 'AngelHack'.

{% highlight bash   %}
rails new angelhack
{% endhighlight %}

El problema de esto es que archivos esenciales del proyecto (como controladores entre otros) se generan con esta variable.  Especificamente afecta a los siguientes archivos:

{% highlight text %}
config
  ├── application.rb
  ├── environment.rb
  ├── routes.rb
  ├── enviroments/
  │       ├── development.rb
  │       ├── test.rb          
  │       └── production.rb
  └── initializers/
          ├── secret_token.rb
          └── session_store.rb
{% endhighlight %}

Cuando finalmente decidimos que se llamaría BikeTripin, sinceramente me dió paja cambiarlos así que esperé y hoy ya habiendo terminado la Hackathon me dispuse a buscar una forma de hacerlo más sencilla y la quiero dejar para todos. Gal Koren ([Gal Koren @ GitHub][2]) creó un plugin que nos hace esta pega de la forma más sencilla posible, asi que abran una terminal y manos a la obra:

{% highlight bash   %}
cd path/to/app
rails plugin install git@github.com:get/Rename.git
rails g rename_to NewName
{% endhighlight %}

Y luego si queremos deshacernos del plugin:

{% highlight bash   %}
rm -r "vendor/plugins/Rename"
{% endhighlight %}

y darle 'y' a todo.

Espero que les sirva (!)

  [1]: http://cabargas.com/images/railsapp.png
  [2]: https://github.com/get