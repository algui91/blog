---
id: 148
title: 'Clases y Objetos &#8211; Control del acceso a los miembros de la clase'

layout: post
guid: http://elbauldelprogramador.org/clases-y-objetos-control-del-acceso-a-los-miembros-de-la-clase/
permalink: /clases-y-objetos-control-del-acceso-los/
blogger_blog:
  - www.elbauldelprogramador.org
  - www.elbauldelprogramador.org
  - www.elbauldelprogramador.org
blogger_author:
  - Alejandro Alcaldehttps://profiles.google.com/117030001562039350135noreply@blogger.com
  - Alejandro Alcaldehttps://profiles.google.com/117030001562039350135noreply@blogger.com
  - Alejandro Alcaldehttps://profiles.google.com/117030001562039350135noreply@blogger.com
blogger_permalink:
  - /2011/03/clases-y-objetos-control-del-acceso-los.html
  - /2011/03/clases-y-objetos-control-del-acceso-los.html
  - /2011/03/clases-y-objetos-control-del-acceso-los.html
categories:
  - C
---
<div class="iconcpp">
</div>

Veamos la diferencia entre las siguientes declaraciones de la [clase Punto][1]:  
  
<!--more-->

  


{% highlight bash %}class Punto{
 
public:
  int x;
  int y;
  char ch;

  Punto (char ch1, int x1, int y1);
  void mostrar ();
  void ocultar ();
};
{% endhighlight %}

{% highlight bash %}class Punto{
  int x;
  int y;
  char ch;

public:
  Punto(char chl, int x1, int yl);
  void mostrar();
  void ocultar();
};
{% endhighlight %}



La diferencia de las declaraciones de las clases está en el acceso a los miembros  
dato de la clase, **private**, por defecto. Los datos son, por tanto, privados y las funciones  
son públicas. Cualquier intento de modificar directamente los valores de la abscisa x, la  
ordenada y, o del carácter ch, dará lugar a un error en tiempo de compilación. Luego, en  
**main** no podremos escribir las sentencias:



{% highlight bash %}pt.x=19;
pt.y=5;
pt.ch=’+’;
{% endhighlight %}

El hecho de que los datos sean privados no quiere decir que sean invisibles:  
simplemente quiere decir que no se pueden cambiar desde el exterior. Si es imposible  
acceder a los datos privados, se pueden añadir a la clase funciones que permitan conocer  
sus valores. Si nos interesa conocer la abscisa x y la ordenada y del punto, podernos  
añadir a la clase dos funciones miembro denominadas getx y gety, que retornan los  
valores de *x* y de *y*.



{% highlight bash %}class Punto{
  int y;
  char ch;
public:
  Punto(char chl, int x1, int y1);
  void mostrar ();
  void ocultar ();
  int getx () { return x;}
  int gety () { return y;}
};
{% endhighlight %}



Este ejemplo ilustra una faceta importante del lenguaje C++ denominada  
encapsulación. El acceso a los miembros de una clase está controlado. Para usar una  
clase, solamente se necesita saber qué funciones miembro se pueden llamar y qué datos  
son accesibles. A esto se le denomina interfaz de la clase. No necesitamos saber cómo está hecha la clase, cómo son sus detalles internos. A esto se le denomina ocultamiento  
de la información. Una vez que la clase está depurada y probada, la clase es como una  
caja negra. Los objetos de dicha clase guardan unos datos, y están caracterizados por  
una determinada conducta.

Para acceder a un miembro público (dato o función), desde un objeto de la clase  
Punto basta escribir:



{% highlight bash %}objeto.miembro_público;
{% endhighlight %}

Habitualmente, los miembros públicos son funciones, como mostrar, ocultar,  
*getx, gety*. Las llamadas a dichas funciones miembro desde un objeto *pt1* de la clase  
Punto, se escribirán:



{% highlight bash %}ptl.mostrar ();
cout < < "nabscisa del punto= " << ptl.getx();
cout << "nordenada del punto= "<< ptl.gety ();
{% endhighlight %}

* * *

#### Siguiente tema: [Clases y Objetos - Funciones Inline][2] {.referencia}



 [1]: http://elbauldelprogramador.com/clases-y-objetos-definir-una-clase/
 [2]: http://elbauldelprogramador.com/clases-y-objetos-funciones-inline/

{% include _toc.html %}