---
author: juanpintoduran
title: '[RUBY] Creating a Gem from scratch - Day 1'
excerpt:
layout: post
categories:
  - Hacking
tags:
  - Ruby 
  - Ruby on Rails
post_format: [ ]
---

*Aquí se relata cómo crear una gema desde 0, y no pretende ser una guía sino más bien una bitácora que ayude a sortear errores típicos de este proceso. Para usar Jeweler u "scaffolds" de generación siéntase libre de Googlear (!)*

Ruby on Rails es grandioso, pero no tenemos idea de como muchas cosas funcionan y es tiempo de asumirlo. Quizá de este "hermoso y desconocido" mundo lo más interesante sea el sistema de gemas (gems) y en particular el 'repo' [RubyGems][1].

En fin, siempre quize hacer una gema yo mismo y en particular tras mi último proyecto, una forma de simplificar a los desarrolladores la inclusión de sistemas de rating en sus sitios.

Para empezar obviamente y como todo en informática, hay que partir por leer. Yo empecé por las [guías de RubyGems][5] y en específico creo que es importante partir por las recomendaciones de [como nombrar una gema][2] (es más, creo que tendré que cambiarle el nombre a la mía) ya que el uso de "-" o "_" es más que algo de azar e influye en el comportamiento de la gema, la llamada y la denominación de las clases, etc.

Luego se debe ir a la referencia básica y el "Hello World" de la creación de gemas ([Make Your Own Gem][3]). Básicamente ahí se entiende la estructura básica de un Gem folder, la forma correcta de escribir el archivo gemspec y otros aspectos esenciales.

De ahí ya podemos saltar a la terminal y el editor de texto (en mi caso la gema es rate-it así que pondré los comandos que yo usé):

{% highlight bash %}
mkdir rate-it && mkdir rate-it/lib && cd rate-it && touch rate-it.gemspec 
cd lib && touch rate-it.rb
{% endhighlight %}

Estas sencillas líneas generarán el siguiente directorio:

{% highlight text %}
tree
   ├── rate-it.gemspec
   └── lib
         └── rate-it.rb
{% endhighlight %}

El archivo **rate-it.gemspec** corresponde a las variables de configuración de la gema y contiene el nombre, versión, autor, licencia, dependencias y ramas de archivos que deben considerarse. En tanto el archivo **lib/rate-it.rb** corresponde al archivo que contiene las funciones de la gema.

Pero eso no sirve de mucho, mi idea es una gema que funcione de la siguiente manera:

#####Gemfile
{% highlight ruby %}
gem 'rate-it', '1.0'
{% endhighlight %}

Guardamos e instalamos la gema (si lo hacen se instalará, ya está disponible arriba aunque no contiene código dicha versión)

{% highlight bash %}
bundle install && rails g rate-it:install
{% endhighlight %}

y que eso generase todas las migraciones, vistas, assets, controladores y el modelo de los ratings.

Así que me puse a investigar junto con mirar el código de 'devise' y me entretuve un buen rato en el mundo de los [Generadores de Rails][6] y así a los namespaces en los mismos, etc.

En otro minuto explicaré en detalle como construir un generator.

Así que nuevamente a agregar archivos (no explicaré esto en detalle pero les dejaré el tree para que sepan más o menos como va cada cosa)

{% highlight text %}
tree
  ├── rate-it.gemspec
  └── lib
       ├── generators
       │     ├── rate-it
       │     │    └── install_generator.rb #also create routes
       │     └── templates
       │          ├── views #views for rates
       │          │    ├── new.html.erb
       │          │    ├── edit.html.erb
       │          │    └── show.html.erb                           
       │          ├── AddTableRates.rb #this is a migration
       │          ├── average_rate.rb #injects a method to helpers
       │          └── rating.css.scss #stylesheet
       └── rate-it.rb
{% endhighlight %}

Así y tras mucho rato de investigación y lectura, tenemos una gema básica con importaciones básicas, y ahora ya puedo preocuparme de incluir funcionalidad.

Definitivamente no es mi proyecto prioritario por ahora, pero no lo dejaré de lado y los mantendré al tanto.

[1]: https://rubygems.org
[2]: http://guides.rubygems.org/name-your-gem/
[3]: http://guides.rubygems.org/make-your-own-gem/
[4]: http://guides.rubygems.org/command-reference/
[5]: http://guides.rubygems.org/
[6]: http://guides.rubyonrails.org/generators.html