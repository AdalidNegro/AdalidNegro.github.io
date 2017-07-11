---
layout: post
title: "Instalar Java de Oracle a la Debian"
date: 2017-06-29
categories:
  - Tecnologia
  - Java
description: 
image: https://unsplash.it/2000/1200?image=2
image-sm: https://unsplash.it/500/300?image=2
---
Es la tercera o cuarta vez que escribo esto, y espero que esta vez sea la definitiva, La maquina virtual de Java en debian no se debe instalar usando los PPA de Ubuntu, en debian tenemos siempre una mejor manera de hacer las cosas. Para instalar un JDK de Oracle debemos descargar dicho JDK en nuestra maquina, para este post supondre que es un servidor Debian sin interfaz grafica para hacer el post un poco mas interesante.

Asi pues el primer comando sera descargar el software desde la pagina de Oracle asi:

~~~
~ wget --no-check-certificate --no-cookies --header "Cookie: oraclelicense=accept-securebackup-cookie" http://download.oracle.com/otn-pub/java/jdk/8u131-b11/d54c1d3a095b4ff2b6607d096fa80163/jdk-8u131-linux-x64.tar.gz
~~~

Esto se puede enredar un poco si se trata de descargar una version de Java diferente a la ultima. Ya teniendo esto procedemos a instalar un paquete que se utiliza para la generacion del paquete para Debian de Java:

~~~
# apt-get install -y java-package
~~~

Y ya con este paquete instalado, podemos crear el paquete para nuestro Debian asi:

~~~
~ make-jpkg jdk-8u131-linux-x64.tar.gz
~~~

Y esto nos genera el instalador, al que simplemente instalamos mediante DPKG asi:

~~~
# dpkg -i oracle-java8-jdk
~~~

Y listo!!
