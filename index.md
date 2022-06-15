---
title: Instructions hébergées en ligne
permalink: index.html
layout: home
ms.openlocfilehash: 0c2c63aea8926ec06e02203a9ff9a9a5d5cc9b85
ms.sourcegitcommit: 9f66e4932aaf188d3be327646561dc7fe8e5c7a5
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/21/2022
ms.locfileid: "145197313"
---
# <a name="content-directory"></a>Répertoire de contenu

Les liens hypertexte vers chaque exercice et démonstration de labo sont répertoriés ci-dessous.

## <a name="labs"></a>Laboratoires

{% assign labs = site.pages | where_exp:"page", "page.url contains '/Instructions'" %}
| Module | Laboratoire |
| --- | --- | 
{% for activity in labs  %}| {{ activity.lab.module }} | [{{ activity.lab.title }}{% if activity.lab.type %} - {{ activity.lab.type }}{% endif %}]({{ site.github.url }}{{ activity.url }}) |
{% endfor %}
