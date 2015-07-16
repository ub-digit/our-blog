---
layout: post
title:  "En liten 'setting' för att få en Ember-cli app att köra embeddad"
author: Johan Larsson
date:   2015-4-27 20:05
categories: Ember-cli konfiguration javascript
---

Ember-cli sparar "by default" konfiguration in ett speciellt meta fält i dist/index.html. Om man inte använder sig av denna index.html fil utan istället embeddar applikationen på en annan websida tappar man detta. Man kan därför ändra på detta genom att istället spara denna konfigurationsdata i den kompilerade javascript-koden. 

Lägg till detta i Brocfile.js

{% highlight javascript %}
var app = new EmberApp({
	  storeConfigInMeta: false,
	   fingerprint: {
			exclude: ['js', 'css']
    	}
});
{% endhighlight %}

URL:rna till filerna kan inte kan 'fingerprintas' därför exluderas dessa med hjälp av "exclude" ovan. 


Tillgängligt från ember-cli 0.1.2 