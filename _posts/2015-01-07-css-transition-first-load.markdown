---
layout: post
author: Johan Larsson
title:  "CSS transitions triggar på första laddningen."
date:   2015-01-09 20:05
categories: CSS animation javascript
---

__Uppgift:__ Animera "color-attributet" på hover på länkar bara efter page-load. 

{% highlight css %}
a {
    color: #fff;
    transition: color .5s ease;
}

a:hover {
        color: #000;
}
{% endhighlight %}



__Problem:__ Det problem jag stötte på var att länkarna animerade från sitt ursprunliga tillstånd som browsern hade stylat dom med. Detta var inte önskvärt då besökta länkar är lila som default. Detta gjorde att länkarna gick från lila till den färg som jag valt vid första laddningen. Vidrigt och fult. 

__Lösning:__ Lägg till en class på body elementet som heter "preload" och stäng ner alla animationer på allt om den är närvarande.



{% highlight html %}
<body class="preload">
{% endhighlight %}

Stäng ner alla animationer om preload finns närvarande. 

{% highlight css %}
.preload * {
  -webkit-transition: none !important;
  -moz-transition: none !important;
  -ms-transition: none !important;
  -o-transition: none !important;
}
{% endhighlight %}

Glöm sen inte att ta bort classen från body när första laddningen är klar. 

{% highlight javascript %}
$().ready(function() {
  	$("body").removeClass("preload");
});
{% endhighlight %}

 Detta kommer från [css-tricks][css-tricks]

[css-tricks]:  http://css-tricks.com/transitions-only-after-page-load/

