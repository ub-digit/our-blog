---
layout: post
title:  "Installera Drupal 7 mha Drush"
date:   2015-08-18 09:00
author: Johan Larsson
categories: Drupal
---

Här hittar du några copy-paste-kommandon för att ladda ner och installera Drupal. Observera att du måste ha Drush installerad på din maskin. Du måste också såklart ha en MySql-tjänst (mariadb i mitt fall), PHP samt Apache (eller annan webserver). 

__Ladda ner önskad version av Drupal__ 

Om du inte anger någon version tar den senaste stabila version som finns tillgänglig. Skriv då bara _drush dl_. 

{% highlight javascript %}

drush dl drupal-7.x

{% endhighlight %}

__Installera Drupal__ 

Om du inte redan har skapat databasen så kommer Drush göra detta åt dig. 

Den första parametern är vilken installationsprofil du vill använda. Om du inte har någon egen rekomenderar jag _standard_ men du kan också välja _minimal_. 

{% highlight javascript %}

drush site-install standard --account-name=admin --account-pass=admin --db-url=mysql://root:RandomPassword@localhost/databasename

{% endhighlight %}


