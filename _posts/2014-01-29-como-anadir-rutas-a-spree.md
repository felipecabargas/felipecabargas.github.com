---
author: juanpintoduran
title: '[HOW-TO] Añadir y testear rutas en un engine de rails cómo Spree'
excerpt:
layout: post
categories:
  - Tutorial
tags:
  - rails
  - spree
  - ruby
  - tdd
post_format: [ ]
---
Cómo siempre, para añadir nuevas rutas, se deben añadir con los correspondientes métodos al `config/routes.rb`. En el caso de **Spree** estas rutas no deben dibujarse en `Rails.application.routes` si no que en `Spree::Core:Engine.routes`; así, para añadir un modelo CRUD al panel de administrador de la plataforma:

{% highlight ruby %}
Spree::Core::Engine.routes.draw do
  namespace :admin do
    resources :items
  end
end
{% endhighlight %}

Al añadir rutas, se crearán paths dentro del namespace señalado de esta forma:

{% highlight bash %}
spree  / Spree::Core::Engine

Routes for Spree::Core::Engine:
                                      admin_items GET    /admin/items(.:format)                                                      spree/admin/items#index
                                                  POST   /admin/items(.:format)                                                      spree/admin/items#create
                                   new_admin_item GET    /admin/items/new(.:format)                                                  spree/admin/items#new
                                  edit_admin_item GET    /admin/items/:id/edit(.:format)                                             spree/admin/items#edit
                                       admin_item GET    /admin/items/:id(.:format)                                                  spree/admin/items#show
                                                  PATCH  /admin/items/:id(.:format)                                                  spree/admin/items#update
                                                  PUT    /admin/items/:id(.:format)                                                  spree/admin/items#update
                                                  DELETE /admin/items/:id(.:format)                                                  spree/admin/items#destroy

{% endhighlight %}

A pesar de esto, al intentar testear cualquier elemento que contenga rutas con RSpec, los test arrojarán `undefined method some_new_path` - [véase ejemplo aquí](https://gist.github.com/felipecabargas/8676836) -.

Esto se debe a que estas rutas están **dibujadas** dentro de **Spree** y no dentro de Application::Routes por lo cual deben ser llamadas usando el prefijo **spree.**, por ejemplo en una vista:

{% highlight ruby %}
<%= link_to 'Show', spree.admin_items_path(@item), class: "button" %>
<%= link_to 'Back', spree.admin_items_path, class: "button" %>
{% endhighlight %}

y en un controlador:

{% highlight ruby %}
if @item.save
  redirect_to spree.admin_items_url, notice: 'Item was successfully updated.'
else
  render action: 'new'
end
{% endhighlight %}

Para los test de routing, también encontramos el mismo problema, que puede ser fácilmente sorteado al añadir esta línea tras el `describe "routing" do`:

{% highlight ruby %}
routes { Spree::Core::Engine.routes }
{% endhighlight %}