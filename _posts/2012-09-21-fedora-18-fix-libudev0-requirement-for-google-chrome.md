---
author: juanpintoduran
title: '[Fedora 18] Fix "libudev.so.0" requirement for Google Chrome / Chromium'
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

Si eres uno de los usuarios de Fedora 18 que usa Chrome o Chromium como navegador, seguramente te encontrarás con que el navegador no inicia y muestra este error (al ejecutarlo por consola):

{% highlight text   %}
/usr/bin/google-chrome: error while loading shared libraries: libudev.so.0: cannot open shared object file: No such file or directory
{% endhighlight %}

Esto se debe a un cambio que se está produciendo entre udev y systemctl en las nuevas versiones de la disto.

Lo bueno es que se soluciona creando un link simbólico... para esto primero debemos encontrar que versión de **libudev** esta presente en el sistema en la carpeta **/usr/lib64/** por un archivo de nombre **libudev.so.1.0.X**.

Tras encontrar el archivo sólo crearemos un enlace simbólico a la dirección ya requerida (con permisos de root):

{% highlight text   %}
ln -sf /usr/lib64/libudev.so.1.0.X /usr/lib64/libudev.so.0
{% endhighlight %}

Recuerden reemplazar la X del archivo por la de vuestra versión (actualmente es la 1.0.4).

Y voilà... ya pueden ejecutar Google Chrome y Chromium normalmente.

  [1]: http://cabargas.com/images/fedora-18-chrome.png