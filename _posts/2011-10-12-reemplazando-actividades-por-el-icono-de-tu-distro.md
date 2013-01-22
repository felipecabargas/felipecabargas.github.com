---
author: juanpintoduran
title: Reemplazando "Actividades" por el ícono de tu distro
layout: post
categories:
  - Linux
tags:
  - Fedora
  - GNOME 3
  - Gnome-Shell
  - linux
post_format: [ ]
---
Basándome en una extensión para Gnome-Shell de F. Murphy que permite modificar a tu gusto esta zona del escritorio de Gnome 3, decidí arreglar esta extensión de modo tal que la modificación se haga automaticamente al activarla.

[![][1]][1]

Por ahora, la extensión trabaja en la versión 3 y no 3.2, ya que me encuentro modificando los códigos para lograr su funcionamiento en la nueva versión, estará listo dentro de este jueves.

Lo más importante de esta extensión sin duda es que permite mediante una simple modificación al código (destacado con una anotación en inglés) cambiar el ícono a mostrar por cualquier otro que tenga el tema que estás usando.

`// the "icon_name" value must be a valid icon name without extension`
`let logo = new St.Icon({ ``icon_type: St.IconType.FULLCOLOR,`
`icon_size: hotCornerButton.height,`
`icon_name: 'start-here' });`

El ícono start-here puede ser reemplazado por cualquiera en el directorio de apps de tu tema de íconos.

**Actualización:**

Con la corrección a ‘start-here’ debería funcionar en todas las distros comúnes (FEDORA, UBUNTU, OpenSUSE, Debian, ArchLinux) ya que este ícono es común en los temas de todas las distros.

### Descarga:

[Ícono de Actividades (ZIP)][2]

**Para utilizarlo DEBES tener instalado Gnome Tweak Tool. **Si no lo tienes en tu sistema, simplemente usa el siguiente comando:

**Fedora:**  
`sudo yum install gnome-tweak-tool`

**Ubuntu**:  
`sudo apt-get install gnome-tweak-tool`

 
 [1]: http://cabargas.com/images/gnomeshellicon.png
 [2]: http://cabargas.com/proyectos/gnome-shell/extensions/iconoactividades@felipecabargas.zip