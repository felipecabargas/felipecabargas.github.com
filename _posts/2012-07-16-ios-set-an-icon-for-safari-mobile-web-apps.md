---
author: juanpintoduran
title: '[TIP] iOS: Set an icon for Safari Mobile Web Apps'
excerpt:
layout: post
category:
  - Programacion
tags:
  - css
  - html
  - ios
  - mac
  - programacion
  - rails
post_format: [ ]
---
Para cuando hagas tu web móvil y quieras que cuando el usuario guarde tu página a su inicio salga tú icono, simplemente agrega:

`<link rel="apple-touch-icon" href="custom-icon.png"/>`

(donde custom-icon.png es tú icono en 57×57 pixeles) en el head de tu homepage y *voilà *

[![][3]][3]

**[EDIT]**

****Cuando quieres incluir diferentes íconos para las nuevas Retina Display y los iPad en general, usa este código:

`<link rel="apple-touch-icon" href="touch-icon-iphone.png" />`
`<link rel="apple-touch-icon" sizes="72x72" href="touch-icon-ipad.png" />`
`<link rel="apple-touch-icon" sizes="114x114" href="touch-icon-iphone4.png" />`


 [3]: http://www.cabargas.com/blog/wp-content/uploads/2012/07/IMG_0310.png