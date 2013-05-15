---
author: juanpintoduran
title: '[OS X] Install pygame on OS X with a Homebrew Python 2.7 install'
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

Si eres uno de los tantos usuarios del gran proyecto HomeBrew quizá te has visto en el dilema de instalar el módulo 'pygame' en OS X (mi Mac Mini tiene 10.8.3 así que sé que este tuto funciona en Mountain Lion).

Para mi segunda tarea del curso de Programación de Computadores de la UTFSM tenemos que usar el módulo (que convenientemente conozco debido al curso de Inteligencia Artificial de Berkeley que tomé hace un semestre en edX) y necesitaba instalarlo, es aquí donde surge el problema:

Existen 10 o más instaladores, más de 10 taps y sin duda más de una respuesta en StackOverflow al respecto así que te dejo los comandos que a mi me funcionaron y que no deberían fallar.

Manos a la obra. Abran un terminal e ingresen los siguientes comandos:

{% highlight bash %}
curl -O http://www.pygame.org/ftp/pygame-1.9.1release.tar.gz
tar -xzf pygame-1.9.1release.tar.gz
cd pygame-1.9.1release/
python config.py
{% endhighlight %}

En el archivo 'Setup' buscamos las entradas con SDL, FONT, IMAGE y MIXER y las reemplazamos por las siguientes (estan juntas):

{% highlight python %}
SDL = -I/usr/local/include/SDL -L/usr/local/lib -lSDL 
FONT = -lSDL_ttf
IMAGE = -lSDL_image
MIXER = -lSDL_mixer
{% endhighlight %}

Pueden también descomentar funciones extra que quieren que se compilen quitando los # de las líneas correspondientes

Ahora de vuelta en la terminal reemplazaremos un archivo con este otro (cambian dos ocurrencias pero les ahorro el trabajo):

{% highlight bash %}
cd src/
sudo curl -O http://www.cabargas.com/files/scale_mmx64.c
cd ..
sudo python setup.py install
{% endhighlight %}

Tras todo esto ya deberían poder hacer import del módulo 'pygame' normalmente. Pueden remover el directorio pygame-1.9.1release.

[1]: http://cabargas.com/images/pygame.png