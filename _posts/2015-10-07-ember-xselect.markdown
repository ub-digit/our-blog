---
layout: post
title:  "Ember-xselect istället för Ember.select"
date:   2015-10-07 10.30
author: Jimmy Carlsson
categories: Ember Select
---

Då Ember iom version 2.0 ej kommer att ha kvar stöd för de tidigare selecthelpers **'Ember.select'** och **'view 'select''**, så bör dessa bytas ut mot antingen en ren `<select>` tag mha HTMLBars, eller via ett add-on.

Jag har testat **emberx-select**, vilket är ett populärt addon som verkar fungera bra.

För att installera:

    ember install emberx-select

Kod innan byte:
{% raw %}
    {{view Ember.Select 
      content=pubyears  
      optionValuePath="content.id"
      optionLabelPath="content.pubyear"
      value=pubyear
      class="form-control"
    }}
{% endraw %}
Kod efter byte
{% raw %}
    {{#x-select value=pubyear class="form-control"}}
      {{#each pubyears as |selectValue|}}
        {{#x-option value=selectValue.id}}{{selectValue.pubyear}}{{/x-option}}
      {{/each}}
    {{/x-select}}
{% endraw %}
Länk till repositoriet: <https://github.com/thefrontside/emberx-select>
