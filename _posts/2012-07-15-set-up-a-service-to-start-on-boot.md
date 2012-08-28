---
author: juanpintoduran
title: '[TIP] LINUX: Set-up a service to start on boot'
excerpt:
layout: post
category:
  - Linux
tags:
  - apache
  - bash
  - linux
  - mysql
  - postgre
  - rails
  - servers
  - service start
  - Terminal
post_format: [ ]
---
Este es de esos tips que muchos conocen y que incluso pueden parecer ridículos como para publicarse, pero yo al menos estaba más que complicado con como hacer que el Server de PostgreSQL iniciara con el sistema para las múltiples apps en rails que tengo en mi computadora.

Para hacer que un servicio (postgresql, mysqld, httpd, etc) parta con el sistema operativo al arrancar, simplemente anda a una terminal y ejecuta:

`sudo chkconfig --level 2345 service on`

donde `service` indica el servicio que necesitas arrancar con tu sistema.

 