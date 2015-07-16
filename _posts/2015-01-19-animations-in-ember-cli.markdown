---
layout: post
author: Johan Larsson
title:  "Animationer på ett enkelt sätt i Ember!"
date:   2015-01-19 15:12:01
categories: Ember javascript
---


[Liquid-fire][liquid-fire-github] är ett "addon" till [Ember CLI][ember-cli] och det är det  absolut enklaste och snabbaste sättet att få till animationer i en Ember CLI applikation. Det funkar även med [bootstraps-grid][bootstrap-grid]. Man kan också skriva sina egna animationer om man vill.

>Liquid Fire is a toolkit for managing animated transitions in an Ember application. Like Ember itself, our goal is to cultivate shared abstractions so we're free to focus on bigger and better ideas. Good defaults. Convention over configuration. Composable pieces all the way down. 



## 1: Installera

{% highlight javascript %}
	npm install --save-dev liquid-fire
{% endhighlight %}


## 2: Skapa en ny outlet som skall animeras

{% raw %}
	{{liquid-outlet}}
{% endraw %}

## 3: Skapa en Transition Map

Det gör du genom att skapa följande fil _app/transitions.js_. 

Eftersom animationerna kan variera baserat på vilken rutt man går från och till så kan man här ange "fromRoute" och "toRoute". Baserat på det kan man då välja animationstyp. T ex om man går djupare ner i en struktur vill man animera från höger till vänster men när man går tillbaka vill man oftast göra det omvända. 

{% highlight javascript %}
export default function(){
	this.transition(
	  this.fromRoute('foo'),
	  this.toRoute('bar'),
	  this.use('toLeft', {duration: 300}),
	  this.reverse('toRight', {duration: 300})
	);
}
{% endhighlight %}

Full dokumentation för [liquid-fire][liquid-fire-docs].

[liquid-fire-github]:	https://github.com/ef4/liquid-fire
[liquid-fire-docs]: http://ef4.github.io/liquid-fire/
[ember-cli]: 	http://www.ember-cli.com/
[bootstrap-grid]: http://getbootstrap.com/css/#grid
