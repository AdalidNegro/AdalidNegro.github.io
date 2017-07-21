---
layout: post
title: "Solucionar error de libcanberra"
date: 2017-07-21
categories:
  - Personal
description: 
image: https://unsplash.it/2000/1200?image=2
image-sm: https://unsplash.it/500/300?image=2
---
Cuando instalamos nuestro linux y ejecutamos aplicaciones desde el escritorio muchas veces podemos observar un molesto error que sale repetidamente:

~~~
Gtk-Message: Failed to load module "canberra-gtk-module"
~~~

Para solucionar este pequeño error la solución es simplemente instalar un paquete y listo, lo haremos usando el usuario root así:

~~~
# apt-get install libcanberra-gtk0
~~~

Y listo.

<figure>
  <img src="https://unsplash.it/2000/1200?image=2" alt="Nuevo Blog"/>
</figure>

Así nos saldrán permanentemente errores casi a diario, pero buscando un poco se puede encontrar una solución a casi todo.

<blockquote>
  Si te sientes atraído por la actividad hacker porque no tienes vida propia, está bien también —al menos no tendrá problemas de concentración—. A lo mejor más adelante podrás conseguir una vida propia como el resto de la gente. 
  <cite>Eric Raymond</cite>
</blockquote>
