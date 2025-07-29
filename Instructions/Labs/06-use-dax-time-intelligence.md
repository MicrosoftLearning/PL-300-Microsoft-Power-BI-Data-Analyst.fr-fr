---
lab:
  title: Utiliser les fonctions DAX d'intelligence temporelle dans Power BI
  module: Use DAX time intelligence functions in Power BI
---

# Utiliser les fonctions DAX d'intelligence temporelle dans Power BI

## Histoire du labo

Dans ce laboratoire, vous allez créer des mesures avec des expressions DAX qui impliquent l’Assistant Time Intelligence.

Dans ce laboratoire, découvrez comment :

 - Utilisez diverses fonctions d'intelligence temporelle pour manipuler le contexte de filtrage qui concerne spécifiquement les dates.

**Ce laboratoire devrait prendre environ 15 minutes.**

## Démarrage

Pour effectuer cet exercice, ouvrez d’abord un navigateur web et entrez l’URL suivante pour télécharger le fichier zip :

`https://github.com/MicrosoftLearning/PL-300-Microsoft-Power-BI-Data-Analyst/raw/Main/Allfiles/Labs/06-use-dax-time-intelligence/06-time-intelligence.zip`

Extrayez le fichier dans le dossier ** C:ousersStudentCownloadsC06-time-intelligence.**

Ouvrez le fichier **06-Starter-Sales Analysis.pbix**.

> _**Remarque** : Vous pouvez ignorer la connexion en sélectionnant **Annuler**. Fermez toutes les autres fenêtres d’information ouvertes. Si vous êtes invité à appliquer les modifications, sélectionnez **Appliquer plus tard**_.

## Créer une mesure de ventes cumulées annuelles jusqu’à ce jour (YTD)

Dans cette tâche, vous allez créer une mesure de ventes cumulées annuelles jusqu’à ce jour (YTD) à l’aide de fonctions Time Intelligence.

1. Dans Power BI Desktop, en vue Rapport, à la **Page 2**, notez le visuel de la matrice qui affiche diverses mesures avec les années et les mois regroupés sur les lignes.

2. Ajoutez une mesure à la table `Sales`, basée sur l’expression suivante et sans décimale :

    ```dax
    Sales YTD =
    TOTALYTD(
        SUM(Sales[Sales]),
        'Date'[Date],
        "6-30"
    )
    ```

    > _La fonction `TOTALYTD` évalue une expression – ici la somme de la colonne `Sales` – sur une colonne de date donnée. La colonne de dates doit appartenir à une table de dates marquée comme telle._
    >
    > _La fonction peut également accepter un troisième argument facultatif représentant la dernière date d’une année. En l’absence de cette date, le 31 décembre est considéré comme la dernière date de l’année. Juin est le dernier mois de l’année d’Adventure Works ; d’où l’argument « 6-30 »._

3. Ajoutez le champ `Sales` et la mesure `Sales YTD` au visuel de matrice.

4. Comme vous pouvez le constater, les valeurs de ventes sont cumulées au cours de l’année.

    ![Image 1](Linked_image_Files/06-use-dax-time-intelligence-functions_image21.png)

> _La fonction `TOTALYTD` effectue une manipulation de filtre, en l’occurrence de temps. Par exemple, dans le cadre du calcul des ventes cumulées annuelles jusqu'à ce jour pour septembre 2017 (le troisième mois de l’exercice), tous les filtres de la table `Date` sont supprimés et remplacés par un nouveau filtre de dates commençant au début de l’année (1er juillet 2017) et s’étendant jusqu’à la dernière date de la période de dates en contexte (30 septembre 2017)._
>
> _De nombreuses [fonctions Time Intelligence](/dax/time-intelligence-functions-dax/?azure-portal=true) sont disponibles dans DAX pour gérer les manipulations de filtre de temps courantes._

## Créer une mesure de croissance en glissement annuel (YoY)

Au cours de cette tâche, vous allez créer une mesure de croissance des ventes en glissement annuel à l’aide d’une variable.

> Les variables vous aident à simplifier la formule et sont plus efficaces si vous utilisez la logique plusieurs fois dans une formule. Les variables sont déclarées à l’aide d’un nom unique, et l’expression de la mesure doit être produite après le mot clé `RETURN`. Contrairement à d’autres variables de langage de codage, les variables DAX ne peuvent être utilisées qu’au sein de la seule formule._

1. Ajoutez une autre mesure à la table `Sales`, à partir de l’expression suivante :

    ```dax
    Sales YoY Growth =
    VAR SalesPriorYear =
        CALCULATE(
            SUM(Sales[Sales]),
            PARALLELPERIOD(
                'Date'[Date],
                -12,
                MONTH
            )
        )
    RETURN
        SalesPriorYear
    ```

    > _La variable `SalesPriorYear` est affectée à une expression qui calcule la somme de la colonne `Sales` dans un contexte modifié. Ce contexte utilise la fonction `PARALLELPERIOD` pour rebasculer 12 mois à partir de chaque date dans le contexte de filtre._

1. Ajoutez la mesure `Sales YoY Growth` au visuel matrice.

1. Comme vous pouvez le constater, la nouvelle mesure rend compte de `BLANK` pour les 12 premiers mois (aucune vente n’ayant été enregistrée avant l’exercice 2017).

1. Notez que la valeur de la mesure `Sales YoY Growth` pour _2018 juillet 2018_ est la valeur des ventes pour _juillet 2017_.

    ![Image 2](Linked_image_Files/06-use-dax-time-intelligence-functions_image22.png)

    > _Maintenant que la « partie difficile » de la formule a été testée, vous pouvez remplacer la mesure par la formule finale qui calcule le résultat de la croissance._

1. Pour terminer la mesure, remplacez la mesure `Sales YoY Growth` par cette formule, en la formatant sous la forme d'un pourcentage avec deux décimales :

    ```dax
    Sales YoY Growth =
    VAR SalesPriorYear =
        CALCULATE(
            SUM(Sales[Sales]),
            PARALLELPERIOD(
                'Date'[Date],
                -12,
                MONTH
            )
        )
    RETURN
        DIVIDE(
            (SUM(Sales[Sales]) - SalesPriorYear),
            SalesPriorYear
        )
    ```

1. Comme vous pouvez le constater, la clause `RETURN` de la formule comporte deux références à la variable.

1. Vérifiez que la croissance en glissement annuel de _Juillet 2018_ est bien de 392,83 %.

    ![Image 3](Linked_image_Files/06-use-dax-time-intelligence-functions_image23.png)

    > _La mesure de croissance en glissement annuel indique une augmentation de près de 400 % (ou une multiplication par quatre) des ventes au cours de la même période de l’année précédente._

1. Dans l’affichage Modèle, placez les deux nouvelles mesures dans un dossier d’affichage nommé _Assistant Time Intelligence_.

    ![Image 4](Linked_image_Files/06-use-dax-time-intelligence-functions_image24.png)

1. Enregistrez le fichier Power BI Desktop.

## Labo terminé
