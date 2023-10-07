---
demo:
  "\_\_ title": 'Clean, transform, and load data in Power BI'
  "\_\_ module": 'Clean, transform, and load data in Power BI'
---
# Nettoyer, transformer et charger des données dans Power BI

## Appliquer des transformations de requête

1. Tout d’abord, appliquez les transformations à la requête Product.

1. Supprimez les colonnes RetailPrice, Photo et Sales.

1. Changez le type de données de la colonne Channels en Nombre entier.

1. Renommer les colonnes suivantes :

    - ProductSKU en SKU

    - ProductName en Product

    - ProductCategory en Category

    - ItemGroup en Item Group

    - KitType en Kit Type

1. Appliquez ensuite les transformations à la requête Sales.

1. Supprimez toutes les colonnes sauf :

    - OrderDate

    - ProductID

    - Quantité

    - UnitPrice

1. Changez le type de données de la colonne UnitPrice en Fixed Decimal Number.

1. Renommez la colonne UnitPrice en Unit Price.

1. Effectuez une sélection multiple incluant les colonnes Quantity et Unit Price, puis ajoutez une nouvelle colonne basée sur leur produit.

1. Renommez la nouvelle colonne Sales.

## Intégrer des requêtes

1. Créez une requête à l’aide du connecteur Excel, en vous connectant au fichier D:\PL300\Demo\Data\ProductCost.xlsx.

1. Supprimez la colonne Product.

1. Changez le type de données de la colonne ProductCost en Nombre décimal fixe.

1. Sélectionnez la requête Product, puis fusionnez-la avec la requête ProductCost, en mettant en relation les colonnes SKU.

1. Dans la fenêtre Niveaux de confidentialité, affectez au niveau de confidentialité de D:\ la valeur Organisation.

1. Développez la colonne ProductCost pour inclure la colonne ProductCost (provenant de la requête ProductCost).

1. Renommez la nouvelle colonne Cost.

## Désactiver et charger des requêtes sur le modèle de données

1. Dans le volet Requêtes, désactivez la requête ProductCost.

1. Sous l’onglet de ruban Accueil, cliquez sur l’icône Fermer et appliquer.

1. Dans Power BI Desktop, faites remarquer les deux tables dans le volet Données.

1. Enregistrez le fichier Power BI Desktop.

1. Laissez le fichier Power BI Desktop ouvert pour la démonstration suivante.
