---
layout: post
title:  "En genomgång av hur man skapar en ny bloggpost"
date:   2015-07-16 13:00
author: Jimmy Carlsson
categories: Blogg Jekyll
---

För att skapa en bloggpost:

---

## Första gången

### Installera jekylls gem
```
gem install jekyll
```

### Klona repositoriet
```
git clone git@github.com:ub-digit/our-blog.git
```

### Kör bloggen lokalt

```
jekyll serve
```

Kommandot startar bloggen lokalt på http://localhost:4000/our-blog/ , sparade ändringar i poster visas efter refresh.

---

## Skapa en post

### Kopiera exempelpost
En färdig exempelpost finns skapad som `_posts/exempelpost`

```
cp _posts/exempelpost _posts/2001-01-01-kort-bloggpost-titel.markdown
```

### Byt ut postspecifk data i filens inledning:

* title
* date
* author
* categories

### Skriv bloggpostens innehåll
Förutsatt att du sparat filen som .markdown eller .md används [Markdown-syntax][markdown]

### Commit post till master
Commita samtliga ändringar till master och pusha.

### Deploya ny blogg
För att bloggen ska uppdateras, kör kommandot `make deploy`

Makeskriptet genererar då om bloggen i sin helhet och sparar statiska filer i _site/ mappen.

### Klar!

Kolla in http://ub-digit.github.io/our-blog/ så att allt ser bra ut.

---

## Jekyll dokumentation

http://jekyllrb.com


[markdown]: https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet 

