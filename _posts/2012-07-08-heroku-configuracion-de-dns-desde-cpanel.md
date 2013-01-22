---
author: juanpintoduran
title: '[HEROKU] Configuración de DNS desde CPANEL'
excerpt:
layout: post
categories:
  - Hacking
tags:
  - cpanel
  - dns
  - heroku
  - mockingbird
  - rails
post_format: [ ]
---
Hace poco necesitabamos redirigir nuestro dominio principal de Mockingbird hacia el servidor de producción de la App en Heroku.

El proceso de redirección de dominios (y subdominios) es sencillo y conveniente ya que se puede hacer desde CPANEL sin necesariamente editar las DNS de tu dominio completo (y con esto comprometer otros subdominios).

Para hacer esto, ingresa a CPanel y busca el “Editor de Zona DNS”.

Si tu idea es usar un dominio principal, añade registros de tipo “A” apuntando a las siguientes IP’s:

`75.101.163.44`
`75.101.145.87`
`174.129.212.2`

 En cambio sí quieres utilizar un subdominio solo agrega un registro CNAME apuntando a tu app en heroku (dependiendo del servidor de heroku puede ser “*test.heroku.com*” o “*test.herokuapp.com*“)

Ahora viene la parte importante, si no quieres que salga el error **“Heroku | No such app”,** tienes que ingresar a tu cuenta en heroku.com e ir a “My Apps”.

[![][4]][4]

Una vez dentro de tu panel de aplicaciones, haz clic en la pestaña “General Info” de la app en cuestión y añade EL MISMO dominio al que apuntaste el dominio en CPANEL; en el caso de Mockingbird así queda:

[![][5]][5]

Espero que esto sea útil !

 
 [1]: http://cabargas.com/images/cpanel1.png
 [2]: http://cabargas.com/images/registro1.png
 [3]: http://cabargas.com/images/registros2.png
 [4]: http://cabargas.com/images/app.png
 [5]: http://cabargas.com/images/domains.png
