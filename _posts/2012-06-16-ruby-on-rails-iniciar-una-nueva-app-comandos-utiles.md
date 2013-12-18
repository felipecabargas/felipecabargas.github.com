---
author: juanpintoduran
title: 'Ruby on Rails: Iniciar una nueva app - Comandos útiles'
excerpt:
layout: post
categories:
  - Hacking
tags:
  - rails
  - ruby
  - ruby on rails
  - tutoriales
post_format: [ ]
---
Para tener en cuenta, los comandos necesarios para iniciar una nueva app en Rails son:

Creando la App:

{% highlight bash %}
rails new path/of/application
{% endhighlight %}

Ingresando al Directorio:

{% highlight bash %}
cd path/of/application
{% endhighlight %}

Editamos el Gemfile agregando:

{% highlight ruby %}
gem 'therubyracer'
{% endhighlight %}

Y ejecutamos 

{% highlight bash %}
bundle install && rails s
{% endhighlight %}

Tras esto la app debería estar arriba con la página de ejemplo en la dirección http://0.0.0.0:3000

Si queremos hacer un home personalizado debemos ejecutar:

{% highlight bash %}
rails generate controller home
{% endhighlight %}

Se generaran carpetas y archivos, vamos a

{% highlight text %}
app/views/home/
{% endhighlight %}

y creamos un nuevo archivo llamado `index.html.erb` con el contenido de nuestro homepage en sintaxis ERB (yo prefiero .html.haml, pero este tuto es general).

Luego vamos a `app/controllers/home_controller.rb `y agregamos lo siguiente entre las dos lineas ya existentes:

{% highlight ruby %}
 def index
 end
{% endhighlight %}

Salvamos el archivo y vamos a `config/routes.rb` y agregamos la línea `get "home/index"`, para luego ir hasta la línea que contiene el texto `root :to => 'welcome#index'` y la reemplazamos (completa) por:

{% highlight ruby %}
 root :to => 'home#index'
{% endhighlight %}

Una vez hecho todo esto vamos a la consola, detenemos el servidor (si no lo hemos hecho antes), ejecutamos `rake routes` para verificar que el `home/index` esté apuntando a `/` y volvemos a ejecutar la app con `rails s`

 