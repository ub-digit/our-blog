---
layout: post
title:  "Blanda procent och pixlar - border-box"
author: Johan Larsson
date:   2015-01-19 15:12:01
categories:  CSS
---

Detta får jag alltid googla upp och jag hamlar alltid på [Paul Irish post](http://www.paulirish.com/2012/box-sizing-border-box-ftw/). Men ibland glömmer jag hur jag skall googla det. Så därför kommer snippeten nedan. 

{% highlight css %}
/* apply a natural box layout model to all elements, but allowing components to change */
html {
  box-sizing: border-box;
}
*, *:before, *:after {
  box-sizing: inherit;
}
{% endhighlight %}


Läs mer om detta på [Paul Irish blogg](http://www.paulirish.com/2012/box-sizing-border-box-ftw/).