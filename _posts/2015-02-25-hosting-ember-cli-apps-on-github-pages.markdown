---
layout: post
title:  "Hur man hostar en ember-cli applikation på Github Pages"
author: Johan Larsson
date:   2015-02-25 21:05
tags: Ember-cli Github Github-pages
---


När du väljer att publicera dina sidor på [Github Pages](https://pages.github.com/) kommer url:n  att bli 

{% highlight javascript %}

http://yourusername.github.io/projectname

{% endhighlight %}

Eftersom ember-cli som default utgår från att den kör i rooten på domänen måste man ändra detta. Det gör man genom config/environment.js. 

{% highlight javascript %}
if (environment === 'production') {
  ENV.baseURL = '/projectname'
}
{% endhighlight%}


__Publicera__

När baseUrl nu är ändrad kan vi bygga applikationen och publicera den. Github Pages kräver att siten ligger i en branch som heter "gh-pages". För att bygga, skapa den nya branchen och publicera siten kan man använda följande skript. 


{% highlight sh %}

// publishToGithubPages.sh
#!/bin/bash
git branch -D gh-pages
git push origin --delete gh-pages
git checkout -b gh-pages
ember build --environment production
git rm -rf app addon config tests
git rm -rf Brocfile.js bower.json package.json testem.json
git rm -rf .bowerrc .editorconfig .jshintrc .travis.yml
mv dist/* .
rm -rf dist
git add .
git commit -m "Publishing to github pages"
git push origin gh-pages
git checkout master

{% endhighlight %}

[Jag hittade informationen om detta här](http://xcv.no/2014/11/29/Deploying-ember-cli-apps-and-addons-to-github-pages.html)
