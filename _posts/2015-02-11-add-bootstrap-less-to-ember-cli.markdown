---
layout: post
title:  "Lägg till Bootstrap Less i Ember CLI"
date:   2015-02-11 14:05
author: Johan Larsson
categories: ember-cli bootstrap
---

Ember-cli har support för LESS kompilering om du installerar ett addon som heter Ember-cli-less. By default kommer alla filer som ligger i styles katalogen slås ihop och kompileras till en fil om dom har en .less extension. Detta gör det mycket smidigt att komma igång med LESS och Bootstrap i ett projekt. 

__Steg 1 - installera ember-cli-less__
{% highlight javascript %}

npm install --save-dev ember-cli-less

{% endhighlight %}

__Steg 2 - installera bootstrap med bower__

{% highlight javascript %}

bower install --save-dev  bootstrap

{% endhighlight %}

Du kommer nu ha en katalog som heter bootstrap i bower_components. I den folder hittar du hela bootstrappakektet. Det som är intressant just nu är såklart less-katalogen. 

__Steg 3 - länka in bootstrap.less i din app__

Detta gör jag genom att byta namn på filen som i ett initialt Ember-cli projekt heter app.css och ligger i styles-katalogen. Det nya namnet blir app.less. Sen tömmer jag den på det lilla innehåll som finns där i. 

Sedan lägger jag dit följande rad

{% highlight javascript %}

@import "bower_components/bootstrap/less/bootstrap.less";

{% endhighlight %}

Detta gör nu att bootstrap finns inlänkat i ditt projekt. Du kan sen skapa egna .less filer och länka in i denna filen. Det gör du direkt i styles-katalogen. Jag brukar alltid börja med header.less, footer.less och sen ser man vart man hamlar allt eftersom.



