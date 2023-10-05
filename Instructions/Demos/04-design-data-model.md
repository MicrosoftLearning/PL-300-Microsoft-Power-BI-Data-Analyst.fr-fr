---
demo:
  "\_\_ title": Design a data model in Power BI
  "\_\_ module": Design a data model in Power BI
---
# Concevoir un modèle de données dans Power BI

## Passer en revue le modèle

1. Dans le volet Données, développez toutes les tables pour afficher tous les champs.

1. Dans la table Sales, faites remarquer la hiérarchie OrderDate, qui a été créée automatiquement.

1. Expliquez qu’une table Date sera créée dans la démonstration suivante.

1. Dans le vue Modèle, pointez sur la relation créée automatiquement entre les deux tables.

1. Expliquez comment les filtres vont se propager de la table Product à la table Sales.

## Créer une hiérarchie

1. Créez une hiérarchie basée sur la colonne Category de la table Product.

1. Renommez la hiérarchie Products.

1. Ajoutez la colonne Product en tant que deuxième niveau.

## Définir les propriétés du modèle

1. Masquez les deux colonnes ProductID.

1. Mettez en forme la colonne Quantity pour utiliser le séparateur des milliers.

1. Effectuez une sélection multiple incluant les colonnes Sales et Unit Price, puis mettez-les en forme pour qu’elles utilisent deux décimales.

## Valider la conception du modèle avec un visuel de matrice

1. Dans la vue Rapport, ajoutez un visuel de matrice à la page, puis dimensionnez-le de façon remplir la page entière.

1. Ajoutez la hiérarchie Products aux lignes, puis ajoutez les champs Quantity, Sales et Unit Price.

1. Développez tous les niveaux de la hiérarchie Products.

1. Faites remarquer que les valeurs de Unit Price sont la somme des prix, ce qui n’est pas correct.

1. Dans le volet Données, sélectionnez le champ Prix unitaire, puis configurez son résumé pour utiliser Moyenne.

1. Supprimez la colonne Somme de Unit Price du visuel de matrice, puis ajoutez à nouveau le champ Unit Price.

1. Enregistrez le fichier Power BI Desktop.

1. Laissez le fichier Power BI Desktop ouvert pour la démonstration suivante.
