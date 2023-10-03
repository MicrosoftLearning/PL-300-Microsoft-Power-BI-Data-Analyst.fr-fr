---
demo:
  "\_\_ title": Create reports in Power BI
  "\_\_ module": Create reports in Power BI
---
# Créer des rapports

## Créer un rapport monopage

1. Supprimez le visuel de matrice utilisé pour tester et valider les calculs du modèle.

1. Renommez la page du rapport Sales Summary.

## Ajouter un segment

1. Ajoutez un segment à la table Date colonne Année et placez le en haut à gauche de la page du rapport.

1. Utilisez les options de mise en forme afin de configurer le sélecteur pour qu’il permette une seule sélection.

## Ajouter différents visuels

1. Ajoutez un graphique en courbes et histogramme empilé à la page et configurez-le comme suit :

    - Axe partagé : Date | Month

    - Valeurs de colonnes : Sales | Sales

    - Valeurs de lignes : Sales | Profit Margin

1. Utilisez le segment pour filtrer la page en fonction de CY2019, puis de CY2020.

1. Dans le graphique en courbes et histogramme empilé, faites remarquer qu’il n’y a pas de colonne des ventes pour décembre 2020.

1. Configurez l’axe partagé pour « Afficher les éléments sans données ».

1. Faites remarquer que décembre 2020 est ajouté à l’axe, mais qu’il n’y a pas de colonne de données.

1. Expliquez que les données des ventes de décembre 2020 ne sont pas encore présentes. *Vous allez exécuter un script dans une démonstration ultérieure pour charger les ventes de décembre 2020.*

1. Ajoutez un graphique en entonnoir et configurez-le comme suit :

    - Groupe : Product | Category

    - Valeurs : Sales | Profit Margin

1. Utilisez les options de mise en forme pour sélectionner une couleur de données contrastée.

1. Ajoutez un visuel de questions et réponses, puis entrez la question suivante : Total sales by product demographic (Total des ventes par données démographiques pour les produits)

1. Enregistrez le fichier Power BI Desktop.

1. Laissez le fichier Power BI Desktop ouvert pour une démonstration ultérieure.
