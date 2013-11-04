---
author: juanpintoduran
title: '[PYTHON] Check existence of an element inside a list'
excerpt:
layout: post
categories:
  - Hacking
tags:
  - utfsm
  - python
  - programacion
post_format: [ ]
---

[![][4]][4]

Para la [tarea de la Tortuga][1] de mi curso de [Programación de Computadores de la UTFSM][2], con los Sres. [Nano Norambuena][5] y [Pancho Madariaga][3] tuvimos que hacer muchísimas restricciones a la entrada del usuario, y la más compleja quizá fue lidiar con que no se ingresaran caracteres en minúsculas o distintos de los C, T y V que se podían ingresar.

Al final resulta que necesitabamos saber si un caracter del string era o no "C" o "V" y por lo tanto revisabamos el string desde el índice 1 hasta el -2 (o el len()-1 de la cadena), aquí pongo el código simplificado como ejemplo:

{% highlight python   %}
torre = raw_input("Ingrese una torre:")
bloques = len(torre)
techo = False
intbloq = ['C','V']

for indice in range(1,bloques-1):
    if bloques != 2:
        if construccion[indice] not in intbloq:
            techo = True

if (techo == True):
    print "Torre mal ingresada"
{% endhighlight %}

Como verán lo que básicamente utilizamos fue ver si el caracter está en una lista de python, lo que es en el fondo el objetivo de este post, así que si quieren chequear la existencia de un elemento dentro de una lista se usa:

{% highlight python   %}
ingreso = raw_input('Ingrese una letra de la A a la C:')
lista = ['A','B','C']

if ingreso not in lista:
    print 'La letra ingresada no es válida'
else:
    print ingreso

{% endhighlight %}

 [1]: http://progra.usm.cl/apunte/tareas/2013-1/tarea-1.html
 [2]: http://progra.usm.cl/
 [3]: http://github.com/franciscomadariaga
 [4]: http://cabargas.com/images/tortuga.png
 [5]: http://github.com/nanorambuena