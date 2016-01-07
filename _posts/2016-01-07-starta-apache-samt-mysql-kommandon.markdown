---
layout: post
title:  "Hur man restartar apache samt startar mariadb-demonen på OSX"
date:   2016-01-07 10:00
author: Johan Larsson
categories: kommandon terminal osx
---


__Starta mariadb som root:__

{% highlight javascript %}

mysqld
mysql -u root -p

{% endhighlight %}


__Restart apache__

{% highlight javascript %}
sudo apachectl restart // restarta servern
{% endhighlight %}
