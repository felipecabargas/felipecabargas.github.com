---
author: juanpintoduran
title: '[OS X] Install Python 2.7.4 & PyGame in Mountain Lion without Homebrew'
excerpt:
layout: post
categories:
  - Hacking
tags:
  - utfsm
  - python
  - programacion
  - mac
post_format: [ ]
---

[![][1]][1]

Ayer dabamos la solución para instalar PyGame 1.9.1 en Mountain Lion mediante Homebrew, hoy les traigo la alternativa más conservadora.

He preparado este tutorial y un archivo .dmg que hace las veces de contenedor de todos los paquetes que se deben descargar (al final de este post adjunto una lista con los instaladores incluidos y su función).

Durante el proceso sin embargo es necesario repetir algunos procesos de los que veíamos ayer... Lo bueno es que TODOS SE EJECUTAN TRAS LOS INSTALADORES:

Tras instalar todo ejecuten los siguientes comandos:

{% highlight bash   %}
cd /Library/Frameworks/SDL.framework/Headers
ln -s SDL ./
export CC='/usr/bin/gcc'
export CFLAGS='-isysroot /Applications/Xcode.app/Contents/Developer/Platforms/MacOSX.platform/Developer/SDKs/MacOSX10.8.sdk -I/opt/X11/include -arch i386'
export LDFLAGS='-arch i386'
export ARCHFLAGS='-arch i386'
{% endhighlight %}

Ahora para instalar PyGame (requerido):

{% highlight bash   %}
curl -O http://www.pygame.org/ftp/pygame-1.9.1release.tar.gz
tar -xzf pygame-1.9.1release.tar.gz
cd pygame-1.9.1release/
python config.py
python setup.py build
python setup.py install
{% endhighlight %}

Para instalar PyObjC (requerido):

{% highlight bash   %}
env CC=clang easy_install -U pyobjc-core
env CC=clang easy_install -U pyobjc
{% endhighlight %}

Tras todo esto ya deberían poder hacer import del módulo 'pygame' normalmente. Pueden remover el directorio pygame-1.9.1release.

[1]: http://cabargas.com/images/pygame.png