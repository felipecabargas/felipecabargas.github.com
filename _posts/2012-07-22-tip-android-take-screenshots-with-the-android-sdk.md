---
author: juanpintoduran
title: '[TIP] Android: Take screenshots with the Android SDK'
excerpt:
layout: post
category:
  - Linux
tags:
  - android
  - deploy
  - desarrollo
  - linux
  - programacion
  - sdk
post_format: [ ]
---
Seguramente desarrollando Apps o Webs te has visto en la necesidad de tomar screenshots desde los dispositivos móviles (iOS, Android, etc…)

Normalmente esto se hace desde el dispositivo, pero hoy quiero mostrarle a los que no saben (o tienen dispositivos Android no rooteados) como tomarlos con el SDK de dispositivos ANDROID.

Para esto obviamente se requiere tener el SDK de Android instalado en tu computadora.

Primero, haremos activaremos la ‘Depuración USB’ en el dispositivo:

[![][2]][2]
Ingresa a “Configuración” (o Ajustes) y luego a “Aplicaciones”

[![][3]][3]
Luego tap en ‘Desarrollo’

[![][4]][4]
y luego activa ‘Depuración USB’

Ahora, con el dispositivo conectado a un puerto USB, vamos a una terminal y vamos al directorio de la SDK (normalmente será el siguiente):

`~/android-sdk-linux/tools/`

Y luego ejecutamos,

`./ddms`

Una vez ejecutado, hacemos clic en el dispositivo en el menú izquierdo y luego en la barra de menú vamos a ‘Device’-> ‘Screen Capture…’ (o Ctrl+S)

[![][5]][5]

y luego en ‘Save’… si quieres tomar más Screenshots, simplemente presiona ‘Refresh’ y se refrescará la pantalla por la actual.

[![][6]][6]

 
 [2]: http://www.cabargas.com/blog/wp-content/uploads/2012/07/apps.png
 [3]: http://www.cabargas.com/blog/wp-content/uploads/2012/07/desarrollo.png
 [4]: http://www.cabargas.com/blog/wp-content/uploads/2012/07/depuration.png
 [5]: http://www.cabargas.com/blog/wp-content/uploads/2012/07/Screenshot-from-2012-07-22-203748.png
 [6]: http://www.cabargas.com/blog/wp-content/uploads/2012/07/Screenshot-from-2012-07-22-203807.png