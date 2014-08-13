#felipecabargas.github.com
---
This repo contains my [IT blog](http://blog.cabargas.com).

Is based in [Jekyll](http://jekyllrb.com) & [Jekyll Bootstrap](http://jekyllbootstrap.com)

**Development notes**
---
In order to use this repo you need to install the following dependencies:

+ Ruby 2.1
+ Jekyll 2.3.0
+ RDiscount

In order to install the necessary gems just run:

	gem install jekyll
	gem install rdiscount

To start the server with auto-regeneration capacities:

	jekyll serve --watch

**Deployment notes**
---
1. Create a repo named username.github.io
2. Put the contents on this repo inside your local repo folder
3. Remove all posts

		cd _posts/ && rm *

4. Add your templates and posts, then commit your changes


		git push origin master
		
	**GitHub will automatically deploy your changes.**

5. Enjoy!

**About**
---
2012-2014 &copy; Contenido bajo licencia CC-BY-NC

*Enjoy jekyll. Blog like a hacker.*