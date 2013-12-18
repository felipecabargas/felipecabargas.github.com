---
author: juanpintoduran
title: '[TIP] Set a “.dev” domain for your project'
excerpt:
layout: post
categories:
  - Hacking
tags:
  - domains
  - hosts
  - servers
post_format: [ ]
---
I really hate to use “localhost/index.html”, “192.168.0.100:3000″ or “127.0.0.1/whatever.php”, so now I want to show you guys how to set a*yourproject.dev *domain for your project

Simply use your favourite text-editor (w/ root privileges) and add this line to your *hosts* (it’s inside the “*etc” *directory) file:

{% highlight text %}
127.0.0.1 www.yourpage.dev yourpage.dev <www.yourpage.dev>
{% endhighlight %}

And that’s all, I hope that this will be helpful for someone.

 