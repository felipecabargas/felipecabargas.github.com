---
author: juanpintoduran
title: '[Fedora] Update from Stable to Rawhide via Yum'
excerpt:
layout: post
categories:
  - Linux
tags:
  - Fedora
  - Rawhide
  - RPMFusion
  - YUM
post_format: [ ]
---
[![][1]][1]

Para los usuarios habituales de Linux, hay fechas importantes y las de salida de la nueva versión de la distribución.

En mi caso, soy usuario de Fedora, pero no me gusta esperar 6 meses para probar las nuevas features de la distro... así que como muchos, trabajo sólo unos meses en la versión "Stable" y luego de la salida del primer "Alpha" me cambio al Pre-Release (o Rawhide en el caso de Fedora).

Esa fecha llegó ayer 18, cuando se liberó el Alpha de Fedora 18 y esta vez por temas de trabajo, en vez de hacer una instalación limpia me decidí por hacer un update (cosa que no había hecho antes) y que me parece que puede ser útil a quien se anime a probar...

Para esto instalaremos un paquete y correremos un par de comandos (nada del otro mundo) con permisos de ROOT (sudo):

{% highlight text   %}
yum install fedora-release-rawhide
{% endhighlight %}

El programa resolverá dependencias y lo instalará (son 20KB :P)

Tras esto, corremos el siguiente comando (también con permisos de root):

{% highlight text   %}
yum --releasever=rawhide distro-sync
{% endhighlight %}

Si el programa falla (dando errores 404), se debe a la habilitación de repositorios de terceros (como es mi caso) y que deben deshabilitarse, para esto, en la terminal:

{% highlight text   %}
cd /etc/yum.repos.d/
ls
{% endhighlight %}

y veremos una lista de todos nuestros repos; en los que no se llaman "fedora*", tendremos que editar la siguiente línea:

{% highlight text   %}
enabled=1
{% endhighlight %}

para que quede así:

{% highlight text   %}
enabled=0
{% endhighlight %}

De no existir la línea "enabled=1", tienes que agregar la ya descrita con el "0" para deshabilitarlo.

Si tienen habilitados los famosos repositorios de [RPMFusion][2] no les servirán de nada tras actualizar (deberán habilitar los de Rawhide - comandos para instalación de esos repos en el link-) así que los borraremos para evitar tener tantos con el comando:

{% highlight text   %}
sudo rm /etc/yum.repos.d/rpmfusion*
{% endhighlight %}

Tras esto, instalación de paquetes nuevos y voilá (bueno, con paciencia y buena conexión a internet demora un rato extenso)... Fedora 18 en sus PC's :)

Espero que les haya sido útil como a mi; cualquier duda la responderé gustoso en los comentarios!

  [1]: http://cabargas.com/images/fedora-18.png
  [2]: http://rpmfusion.org