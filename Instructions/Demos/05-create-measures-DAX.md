---
demo:
  title: Créer des mesures en utilisant DAX dans Power BI
  module: Create measures using DAX in Power BI
---
# Créer des mesures en utilisant DAX dans Power BI

> **Conseil** : Tous les calculs peuvent être copiés à partir du fichier D:\Allfiles\Demo\Resources\Snippets-Demo-05.txt.

## Créer une table calculée

1. Créez une table calculée en utilisant l’expression suivante :

```dax
Date = CALENDARAUTO()
```

1. Passez à la vue Données et examinez la table, qui comprend une colonne de date unique.

Créer des colonnes calculées

1. Ajoutez une colonne calculée à la table Date :

```dax
Year = "CY" & YEAR('Date'[Date])
```

1. Ajoutez une colonne calculée supplémentaire à la table Date :

```dax
Month = FORMAT('Date'[Date], "YYYY-MM")
```

1. Dans la vue Modèle, créez une relation en faisant glisser la colonne Date de la table Date vers la colonne OrderDate de la table Sales.

1. Masquez la colonne OrderDate de la table Sales.

1. Dans la table Date, créez la hiérarchie Calendar, avec les niveaux Année et Mois.

1. Dans la vue Rapport, marquez la table Date en tant que table de dates à l’aide de la colonne Date.

1. Dans le visuel de matrice, supprimez la hiérarchie Products, puis remplacez-la par la hiérarchie Calendar.

1. Ajoutez une colonne calculée à la table Sales :

```dax
Cost = 'Sales'[Quantity] * RELATED('Product'[Cost])
```

1. Mettez en forme la colonne Cost avec deux décimales.

## Créer une mesure rapide

1. Ajoutez une mesure rapide à la table Sales, en soustrayant la colonne Cost de la colonne Profit.

1. Renommez la mesure Profit.

1. Expliquez que la mesure ne stocke pas de données dans le modèle.

Créer des mesures standard

1. Ajoutez une mesure à la table Sales :

```dax
Profit Margin = DIVIDE([Profit], SUM('Sales'[Sales]))
```

1. Mettez en forme la colonne Profit Margin sous forme de pourcentage.

1. Ajoutez une autre mesure à la table Ventes :

```dax
Sales YTD = TOTALYTD(SUM('Sales'[Sales]), 'Date'[Date])
```

1. Mettez en forme la colonne Sales YTD avec deux décimales.

## Vérifier les calculs avec le visuel de matrice

1. Ajoutez les champs Cost, Profit, Profit Margin et Sales YTD au visuel de matrice.

1. Enregistrez le fichier Power BI Desktop.

1. Laissez le fichier Power BI Desktop ouvert pour une démonstration ultérieure.
