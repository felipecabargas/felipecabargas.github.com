---
author: juanpintoduran
title: 'Screencast: Cómo usar el archivo .bashrc para modificar el terminal'
excerpt:
layout: post
category:
  - Destacado
  - Linux
  - Mac
tags:
  - linux
  - Personalización
  - Terminal
post_format: [ ]
---
Como parte de las recopilaciones de mis trabajos en la web, quisiera compartir con ustedes un ScreenCast que subí a HolaGEEK hace unos meses:

El día de hoy les traigo el que sin duda es mi tip favorito de personalización para Linux: el archivo .bashrc.

Para este tutorial necesitas este archivo: <http://www.mediafire.com/?5lgi3ivvdgk4ydw> (3kb) y pegalo dentro de tu carpeta de usuario.

Para editarlo puedes utilizar el comando *“sudo gedit .bashrc*” o simplemente “*gedit .bashrc*”

Ahora vamos con el video:

 

Las opciones que puedes utilizar en el bash son las siguientes:

*   \a carácter de campana ASCII (07)
*    \d la fecha en formato día mes día (p.ej., “mié jul 02″)
*    \D{format} el formato es proporcionado a strftime(3) y el resultado es insertado en la cadena del indicador; un formato vacío resulta en una representación de fecha especifica local. Las llaves son requeridas.
*    \e caracter de escape ASCII (033)
*    \h el nombre del host hasta el primer '.'
*    \H el nombre del la máquina completo (FQDN)
*    \j el número de trabajos actualmente gestionados por el interprete
*    \l el nombre base del dispositivo de terminal del interprete
*    \n carácter de nueva línea
*    \r retorno de carro
*    \s el nombre del interprete, el nombre base de $0 (el fragmento que sigue a la última diagonal)
*    \t la hora actual en formato 24-horas HH:MM:SS
*    \T la hora actual en formato 12-horas HH:MM:SS
*    \@ la hora actual en formato 12-horas AM/PM
*    \A la hora actual en formato 24-houras HH:MM
*    \u el nombre del usuario actual
*    \v la versión del pquete bash (p.ej., 2.00)
*    \V la versión del paquete bash + el nivel de parche (p.ej., 2.00.0)
*    \w el directorio actual de trabajo, con el directorio $HOME abreviado con una tilde
*    \W el nombre base del directorio actual de trabajo, con el directorio $HOME abreviado con una tilde
*    \! el número del comando actual en el histórico
*    \# el número de comando del comando actual
*    \$ si el UID efectivo es 0, un #; en otro caso, $
*    \nnn el caracter correspondiente al número en octal nnn
*    \\ una diagonal invertida
*    \[ inicio de una secuencia de caracteres no imprimibles que pueden usarse para ingresar una secuencia de control en el indicador de la terminal
*    \] fin de una secuencia de carácteres no imprimibles

Y los colores posibles son:

*   Negro 0;30
*   Gris Obscuro 1;30
*   Azul 0;34
*   Azul Claro 1;34
*   Verde 0;32
*   Verde Claro 1;32
*   Cyan 0;36
*   Cyan Claro 1;36
*   Rojo 0;31
*   Rojo Claro 1;31
*   Purpura 0;35
*   Fuschia 1;35
*   Café 0;33
*   Amarillo 1;33
*   Gris Claro 0;37
*   Blanco 1;37

El resultado final tras modificarlo a mi actual sistema operativo y cambiar los colores es este:

[![][1]][1]

Para más opciones de modificacion la Wiki de ArchLinux contiene más datos: [ArchWiki][2]

 
 [1]: http://cabargas.com/blog/wp-content/uploads/2011/10/bash.png
 [2]: https://wiki.archlinux.org/index.php/Colorear_Indicador_Bash_%28Espa%C3%B1ol%29