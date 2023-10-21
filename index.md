---
title: Instructions hébergées en ligne
permalink: index.html
layout: home
---

# Répertoire de contenu

Les liens hypertexte vers chaque exercice et démonstration de labo sont répertoriés ci-dessous.

## Laboratoires

{% assign labs = site.pages | where_exp:"page", "page.url contains '/Instructions/Labs'" %}
| Section | Laboratoire |
| --- | --- |
{% for activity in labs  %}| {{ activity.lab.module }} | [{{ activity.lab.title }}{% if activity.lab.type %} - {{ activity.lab.type }}{% endif %}]({{ site.github.url }}{{ activity.url }}) |
{% endfor %}

## Démonstrations

{% assign demos = site.pages | where_exp:"page", "page.url contains ’/Instructions/Demos’" %}
| Section | Laboratoire |
| --- | --- |
{% for activity in demos  %}| {{ activity.lab.module }} | [{{ activity.lab.title }}{% if activity.lab.type %} - {{ activity.lab.type }}{% endif %}]({{ site.github.url }}{{ activity.url }}) |
{% endfor %}
