---
author: juanpintoduran
title: '[OS X] Verify Local Data on Transmission for Mac'
excerpt:
layout: post
categories:
  - HowTo
tags:
  - torrents
  - howto
  - mac
post_format: [ ]
---

[![][1]][1]

Transmission es quizá el mejor cliente de torrents para Mac y Linux.

A veces mientras descargamos "legalmente" contenido desde la web vía torrent algunos datos están corruptos y por lo tanto las descargas se pausan.

El mensaje de error por defecto de Transmission es 'Verify local data'... hasta ahí todo bien, dehecho en linux basta con hacer clic derecho en el torrent y luego en 'Verify local data'. Pero en OS X no.

[![][2]][2]

Para sortear este problema vamos a las Preferencias de Transmission (⌘,) ubicadas en el menú superior (clic sobre "Transmission"):

[![][5]][5]

Una vez ahí, vamos a la pestaña "Remoto" y seleccionamos la opción "Activar acceso remoto":

[![][3]][3]

Luego hacemos clic en "Ejecutar interfaz web" o abrimos http://localhost:9091/transmission/web/ en el navegador y ya sólo bastará con hacer clic derecho sobre el torrent en cuestión y presionar "Verify Local Data".

[![][4]][4]

Espero que este tip les haya sido tan útil como a mi. Un saludo a todos.

[1]: http://cabargas.com/images/transmission.png
[2]: http://cabargas.com/images/tra1.png
[3]: http://cabargas.com/images/tra2.png
[4]: http://cabargas.com/images/tra3.png
[5]: http://cabargas.com/images/pref1.png