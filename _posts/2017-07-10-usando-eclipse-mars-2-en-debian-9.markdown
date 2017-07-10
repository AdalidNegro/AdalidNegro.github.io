---
layout: post
title: "Usando Eclipse Mars 2 en Debian 9 - Stretch"
date: 2017-07-10
categories:
  - Tecnologia
  - Java
description: 
image: https://unsplash.it/2000/1200?image=2
image-sm: https://unsplash.it/500/300?image=2
---
A veces hay que solucionar problemas con software viejo, y para esto toca instalar software viejo, bueno, no tan viejo, pero cuando sales de tu zona de confort y te enfrentas a cosas diferentes, muchas veces puedes enredarte la vida tratando de solucionar problemas que realmente son pequeños. De este modo tuve que enfrentarme a configurar para su uso un Eclipse Mars sobre Debian, pero al instalarlo normalmente, no funcionaba el marketplace y otras funcionalidades.

Despues de mucho buscar, encontre la solucion que comparto aqui.
<ul>
  <li>Instalar el software.</li>
  <li>Editar el archivo de configuracion.</li>
  <li>Crear el lanzador.</li>
  <li>Y pues echar codigo</li>
</ul>

<h3>Instalar el software</h3>
Los pasos para instalar el software son los pasos normales, ir ala pagina de Eclipse y buscar el archivo tar.gz donde viene el software listo, luego copiarlo en /opt/, descomprimirlo y ya esta!

<h3>Editar el archivo de configuracion</h3>
Esta es la parte central del asunto, hay que entrar en la carpeta /opt/eclipse y editar el archivo eclipse .ini que ortiginalmente es asi:

~~~
-startup
plugins/org.eclipse.equinox.launcher_1.3.100.v20150511-1540.jar
--launcher.library
plugins/org.eclipse.equinox.launcher.gtk.linux.x86_64_1.1.300.v20150602-1417
-product
org.eclipse.epp.package.jee.product
--launcher.defaultAction
openFile
-showsplash
org.eclipse.platform
--launcher.XXMaxPermSize
256m
--launcher.defaultAction
openFile
--launcher.appendVmargs
-vmargs
-Dosgi.requiredJavaVersion=1.7
-XX:MaxPermSize=256m
-Xms256m
-Xmx10i24m
~~~

Y debemos dejarlo asi:

~~~
-startup
plugins/org.eclipse.equinox.launcher_1.3.100.v20150511-1540.jar
--launcher.library
plugins/org.eclipse.equinox.launcher.gtk.linux.x86_64_1.1.300.v20150602-1417
-product
org.eclipse.epp.package.jee.product
--launcher.GTK_version
2
openFile
-showsplash
org.eclipse.platform
--launcher.XXMaxPermSize
256m
--launcher.GTK_version
2
openFile
--launcher.appendVmargs
-vmargs
-Dosgi.requiredJavaVersion=1.7
-XX:MaxPermSize=256m
-Xms256m
-Xmx10i24m
~~~

<h3>Crear el lanzador</h3>
Para esto utilizaremos el software alacarte que se encuentra buscando en aplicaciones como menu principal, su uso es evidente y se escapa del alcance de este tutorial.

<h3>Y a echar codigo</h3>
Pues espero que haya sido util la pequeña guia, a usar eclipse sin problemas en nuestro Debian Stretch.
