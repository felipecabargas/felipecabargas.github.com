---
author: juanpintoduran
title: '[Fedora 17] Set Ruby on Rails and make it work'
excerpt:
layout: post
categories:
  - Linux
tags:
  - Fedora
  - mysql
  - rails
  - ruby on rails
  - rvm
post_format: [ ]
---
Reestructurando el proyecto más grande del que formo parte y habiendo vuelto a ser un Fedorano hace poco (recaída como Ubuntero), me vi en la necesidad de instalar Ruby on Rails para trabajar.

Primero que los problemas para instalar ‘sqlite3′ y despues que ‘bundler’ no funcionaba en Fedora. Bueno, la solución era sencilla, un poco de ‘Yum’ y otra pizca de ‘RVM’ y listo; aquí los comandos que necesitan

1) Si Ruby no está instalado

`sudo yum install ruby`

2) Instalando RVM

`bash -s stable < <(curl -s https://raw.github.com/wayneeseguin/rvm/master/binscripts/rvm-installer)`

3) Ahora hay que recargar los perfiles de la consola

`source ~/.bash_profile && source ~/.bashrc`

4.1) Ejecutamos los requerimientos de RVM (Atentos!)

`rvm requirements`

4.2) Te saldrá algo como “Additional Dependencies:” y una serie de cosas a instalar (dehecho dice “yum install”) sólo copia eso y se instalarán las dependencias ![:)][1]

5) Instalando Ruby

`rvm get head && rvm reload`

`rvm install 1.9.3`

6) Creando el Gemset por defecto

`rvm use 1.9.3@myGemSet --create --default`

7) Instalar Rails

`gem install rails`

Finalmente sólo instalar SQLite3 y ya podrás crear proyectos con Rails

`sudo yum install sqlite-devel`

Espero que este HOW-TO te haya sido útil, recuerda cualquier duda en los comentarios o a mi email felipe@cabargas.com