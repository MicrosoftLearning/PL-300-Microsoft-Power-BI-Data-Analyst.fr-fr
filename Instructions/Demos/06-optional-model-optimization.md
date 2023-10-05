---
demo:
  "\_\_ title": (Optional) Optimize model performance in Power BI
  "\_\_ module": Optimize model performance in Power BI
---

# (Facultatif) Optimiser le niveau de performance d’un modèle

## Passer en revue la conception d’un modèle DirectQuery

> **Remarque** : cette démonstration utilise un autre fichier Power BI Desktop.

1. Ouvrez le fichier D:\PL300\Demo\Resources\AW Sales Analysis.pbix.

1. Si vous êtes invité à vous connecter à la source de données, cliquez sur Se connecter.

1. Dans le coin inférieur droit, faites remarquer que le modèle de données comprend des tables DirectQuery.

1. Enregistrez le fichier Power BI Desktop dans le dossier D:\PL300\Demo\MySolution.

1. Dans l’affichage Modèle, présentez la conception du modèle, qui inclut deux tables associées.

1. Dans la vue Rapport, interagissez avec le rapport en sélectionnant différents éléments dans le segment Fiscal Year.

1. Explorez la colonne pour n’importe quel mois de façon à montrer les détails des commandes.

1. Revenez à la page Sales Summary.

## Examiner les performances des requêtes

1. Sous l’onglet de ruban Affichage, montrez le volet Analyseur de performances.

1. Actualisez les objets visuels, puis développez le segment et l’objet visuel Ventes par mois.

1. Soulignez que le mode DirectQuery a été utilisé (les données ont été demandées à la source de données).

## Configurer des tables de stockage doubles

1. Dans la vue Modèle, sélectionnez la table Date, puis sélectionnez le mode de stockage Double.

1. Une fois les données importées, passez à la vue Rapport, puis, dans le volet Analyseur de performances, actualisez les visuels.

1. Faites remarquer que la table Date est désormais interrogée à partir du cache du modèle.

## Créer des agrégations

1. Ouvrez la fenêtre de l’Éditeur Power Query, puis dans le volet Requêtes, dupliquez la requête Reseller Sales.

1. Renommez la nouvelle requête Reseller Sales Agg.

1. Appliquez un groupe par transformation, comme suit :

    - Effectuez un regroupement par OrderDate.

    - Nouvelle colonne : Sales, qui correspond à la somme de la colonne SalesAmount.

1. Fermez et appliquez les requêtes.

1. Dans la vue Modèle, définissez le mode de stockage de la table Reseller Sales Agg à Importer.

1. Créez une relation entre la table Date colonne Date et la table Reseller Sales Agg colonne OrderDate : vérifiez que la cardinalité de la colonne est définie sur un sur plusieurs, avec la table Date d’un côté.

1. Gérez les agrégations sur la table Reseller Sales Agg :

    - OrderDate : effectuez un regroupement en fonction de la colonne OrderDate de la table Reseller Sales.

    - Sales : calculez la somme de la colonne SalesAmount de la table Reseller Sales.

1. Faites remarquer que la table d’agrégation est maintenant masquée.

1. Passez à la vue Rapport, puis dans le volet Analyseur de performances, actualisez les visuels.

1. Faites remarquer que la table Sales by Month est désormais interrogée à partir du cache du modèle.

1. Faites une recherche sur n’importe quel mois et faites remarquer que les détails de la table sont demandés via DirectQuery auprès de la source de données.

1. Enregistrez le fichier Power BI Desktop.

1. Fermez Power BI Desktop.

> **Remarque** : vous n’utiliserez plus cette solution Power BI Desktop.
