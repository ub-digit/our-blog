---
layout: post
title:  "Ember-cli i18n i javascript-kod och språkhanterad dokumenttitel"
date:   2015-10-19 15:23
author: Johan Larsson
categories: Ember-cli I18N 
---

Stötte i grupprumsbokninge på problemet med att dokumenttiteln skulle översättas. Löste detta genom att på application-controllern på afterModel-hooken göra följande: 


{% highlight javascript %}
	afterModel: function() {
		// update documenttitle 
		var t = this.container.lookup('utils:t');
		document.title = t('header.title'); 
	},
{% endhighlight %}

Ett tips är att trots att du overridar med javascript ändå har titeln på svenska kvar i index.html då den syns ett par ögonblick då du byter språk. 


