---
layout: post
title:  "Ctools och custom layouts i Drupal genererar felmeddelande"
date:   2015-08-19 14:00
author: Johan Larsson
categories: Drupal
---

Ibland när man leker med cutoms layouter i Drupal 7 behöver man ta bort eller byta namn på en layout. Detta verkar inte gå. Det genererar ett felmeddelande av typ:

_Fatal error: require_once(): Failed opening required '/sites/all/themes/bootstrap_xxx/layouts/example/example.inc' (include_path='.:/usr/lib/php:/usr/local/lib/php') in /sites/all/modules/ctools/includes/plugins.inc on line 475_

1) Välj rätt databas i mysql och kör: 
{% highlight javascript %}
	delete from cache where cid like 'ctools_plugin%';
{% endhighlight %}
2) Ta bort allt onödigt i layoutväg.
3) F5

Det funkar! 



