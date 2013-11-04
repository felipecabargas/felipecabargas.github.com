---
author: juanpintoduran
title: '[RAILS] Rename paths & routes in a resource'
excerpt:
layout: post
categories:
  - Hacking
tags:
  - Ruby on Rails
post_format: [ ]
---

Como parte de mi nuevo trabajo en FOSUBO - ganador del AngelHack Spring 2013 SCL - me ha tocado hacer varios cambios en el modelo de datos, y uno de esos implicaba pasar de Members a POSs en las rutas (por temas de consistencia).

La primera opcion era renombrar el modelo y así resources lo haría por mi pero ya se esta usando el producto y no quiero traspasar tanta información a mano. Así que lo hice en las rutas, eliminé la parte del modelo y los campos de la base de datos que no me servían y dispuse manos a la obra.

Rake me arrojaba paths de esta forma ( *rake routes* ):

{% highlight ruby   %}
location_members GET /location/:id/members(.:format) members#index
{% endhighlight %}

y yo las quería así:

{% highlight ruby   %}
location_point_of_sales GET /location/:id/pos(.:format) members#index
{% endhighlight %}

Para lograrlo abrimos *routes.rb* encontramos el resource del modelo en cuestión y lo cambiamos desde:

{% highlight ruby   %}
resources :locations do
  resources :members
end
{% endhighlight %}

a:

{% highlight ruby   %}
resources :locations do
  resources :members, :as => "point_of_sales", :path => "pos"
end
{% endhighlight %}

Con esta sencilla línea de código nos ahorramos muchísimo tiempo de renaming y evitamos inconsistencias entre archivos. Espero que les sirva