---
author: juanpintoduran
title: '[HOW-TO] Install Android KitKat (4.4) on the Moto X (XT1058) with locked bootloader'
excerpt:
layout: post
categories:
  - Tutorial
tags:
  - android
  - kitkat
  - motox
  - mac
post_format: [ ]
---
[![][1]][1]

####DISCLAIMER:

I used this method with the following hardware and software:

{% highlight text %}
- Moto X (XT1058) Movistar.en.CL original with LOCKED bootloader
- MacBook Air with MDM (Motorola Device Manager) installed
- 4.2.2 ROM file: fastboot-ghost_retbr-user-4.2.2-13.9.0Q2.X-116-LCX-35-36-release-keys-cid12-Brasil-BR.tar.gz (EXTRACTED ON DOWNLOADS FOLDER)
- 4.4.0 ROM file: Blur_Version.143.44.8.ghost_row.Brasil.en.BR.zip

THE FILES BELOW WERE UPLOADED BY SOMEONE ELSE.
SO DON'T BLAME ME IF THE LINKS ARE NOT WORKING OR YOU BRICK YOUR PHONE.
{% endhighlight %}

The process is pretty simple:

First, you "convert" your Moto X to Brasil Retail version (Flashing the 4.2.2 ROM) and then you upgrade via "sdcard" to 4.4 ROM.

The whole process takes about 20 minutes and I preserved my info and apps but a wipe is recommended in XDA & MotoXBrasil forums.

####Downloads:

1. [4.2.2 ROM][3]
2. [4.4.0 ROM][2]

####Goint to Retail Steps:

1. Put your **Moto X** in "fastboot" mode (With the phone OFF, press and hold the Volume Down & Power Button and then release de Power Button).
2. Connect your Moto X to your PC vía USB.
3. In Linux & OS X go to Terminal and enter the following commands:

   {% highlight bash %}
   cd Downloads/fastboot-ghost_retbr-user-4.2.2-13.9.0Q2.X-116-LCX-35-36-release-keys-cid12-Brasil-BR/
   bash flashall.sh
   {% endhighlight %}
  
   (In Windows open the Files Explorer go to the extracted folder and execute flashall.bat)

**Wait until it finish.**

####Updating to KitKat Steps:

1. Connect your Moto X to the computer as a media device.
2. Put the Blur_Version.143.44.8.ghost_row.Brasil.en.BR.zip file under the root folder of your phone
3. Go to Settings->About->Available Updates
4. Accept all and wait
5. You're now using KitKat without losing your Warranty.

 [1]: http://cabargas.com/images/kitkat.png
 [2]: https://docs.google.com/file/d/0By-LEiKdlBMwcXRRY1EtS0F6b2M/edit
 [3]: https://docs.google.com/file/d/0B3jLajZtiO8kclluMXBscGpzanc/edit
