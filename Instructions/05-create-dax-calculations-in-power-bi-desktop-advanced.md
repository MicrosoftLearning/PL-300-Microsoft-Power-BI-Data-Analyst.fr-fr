---
lab:
  title: Créer des calculs DAX dans Power BI Desktop (partie 2)
  module: Module 5 - Create Model Calculations using DAX in Power BI
ms.openlocfilehash: 064f5bb2c313448f7d15b01bd0e69a84aa85811f
ms.sourcegitcommit: 9ea1e7e21b9b3c718030c94b1693d153a2010ec7
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/29/2022
ms.locfileid: "146650196"
---
# <a name="create-dax-calculations-in-power-bi-desktop-part-2"></a>**Créer des calculs DAX dans Power BI Desktop (partie 2)**

**La durée estimée pour effectuer ce tutoriel est de 45 minutes.**

Dans ce labo, vous allez créer des mesures avec des expressions DAX impliquant une manipulation du contexte de filtre.

Dans ce labo, vous allez découvrir comment :

- Utiliser la fonction CALCULATE() pour manipuler le contexte de filtre

- Utiliser les fonctions Time Intelligence

### <a name="lab-story"></a>**Histoire du labo**

Ce labo est l’un des nombreux labos d’une série qui a été conçue comme une histoire complète allant de la préparation des données jusqu’à leur publication sous forme de rapports et de tableaux de bord. Vous pouvez effectuer ces labos dans l’ordre de votre choix. Toutefois, si vous comptez faire plusieurs labos, nous vous suggérons de suivre cet ordre :

1. Préparer des données dans Power BI Desktop

2. Charger des données dans Power BI Desktop

3. Modéliser les données dans Power BI Desktop

5. Créer des calculs DAX dans Power BI Desktop (partie 1)

6. **Créer des calculs DAX dans Power BI Desktop (partie 2)**

7. Concevoir un rapport dans Power BI Desktop, partie 1

8. Concevoir un rapport dans Power BI Desktop, partie 2

9. Créer un tableau de bord Power BI

10. Analyser les données dans Power BI Desktop

11. Appliquer la sécurité au niveau des lignes

## <a name="exercise-1-work-with-filter-context"></a>**Exercice 1 : Utiliser le contexte de filtre**

Dans cet exercice, vous allez créer des mesures avec des expressions DAX impliquant une manipulation du contexte de filtre.

### <a name="task-1-get-started"></a>**Tâche 1 : Démarrer**

Dans cette tâche, vous configurez l’environnement pour le labo.

*Important : Si vous venez d’effectuer le labo précédent (et que vous l’avez entièrement terminé), ignorez cette tâche et passez directement à la tâche suivante.*

1. Pour ouvrir Power BI Desktop, accédez à la barre des tâches et cliquez sur le raccourci Microsoft Power BI Desktop.

    ![Image 12](Linked_image_Files/06-create-dax-calculations-in-power-bi-desktop-advanced_image1.png)

1. Pour fermer la fenêtre de démarrage, en haut à gauche de cette fenêtre, sélectionnez **X**.

    ![Image 11](Linked_image_Files/06-create-dax-calculations-in-power-bi-desktop-advanced_image2.png)

1. Pour ouvrir le fichier Power BI Desktop de démarrage, sélectionnez l’onglet de ruban **Fichier** afin de passer en mode Backstage.

1. Sélectionnez **Ouvrir un rapport**.

    ![Image 10](Linked_image_Files/06-create-dax-calculations-in-power-bi-desktop-advanced_image3.png)

1. Cliquez sur **Parcourir les rapports**.

    ![Image 9](Linked_image_Files/06-create-dax-calculations-in-power-bi-desktop-advanced_image4.png)

1. Dans la fenêtre **Ouvrir**, accédez au dossier **D:\PL300\Labs\05-create-dax-calculations-in-power-bi-desktop-advanced\Starter**.

1. Sélectionnez le fichier **Sales Analysis** (Analyse des ventes).

1. Cliquez sur **Ouvrir**.

    ![Image 8](Linked_image_Files/06-create-dax-calculations-in-power-bi-desktop-advanced_image5.png)

1. Fermez toutes les fenêtres d’information qui se sont éventuellement ouvertes.

1. Pour créer une copie du fichier, sélectionnez l’onglet de ruban **Fichier** afin de passer en mode Backstage.

1. Sélectionnez **Enregistrer sous**.

    ![Image 7](Linked_image_Files/06-create-dax-calculations-in-power-bi-desktop-advanced_image6.png)

1. Si vous êtes invité à appliquer les modifications, cliquez sur **Appliquer**.

    ![Image 6](Linked_image_Files/06-create-dax-calculations-in-power-bi-desktop-advanced_image7.png)

1. Dans la fenêtre **Enregistrer sous**, accédez au dossier **D:\PL300\MySolution**.

1. Cliquez sur **Enregistrer**.

    ![Image 2](Linked_image_Files/06-create-dax-calculations-in-power-bi-desktop-advanced_image8.png)

### <a name="task-2-create-a-matrix-visual"></a>**Tâche 2 : Créer un visuel matrice**

Au cours de cette tâche, vous allez créer un visuel matrice pour gérer les tests de vos nouvelles mesures.

1. Dans Power BI Desktop, créez une page de rapport dans l’affichage Rapport.

    ![Image 1](Linked_image_Files/06-create-dax-calculations-in-power-bi-desktop-advanced_image9.png)

2. Sur la **Page 3**, ajoutez un visuel matrice.

    ![Image 13](Linked_image_Files/06-create-dax-calculations-in-power-bi-desktop-advanced_image10.png)

3. Redimensionnez le visuel matrice de façon à ce qu’il remplisse toute la page.

4. Pour configurer les champs du visuel matrice, faites glisser la hiérarchie **Region \| Regions** du volet **Champs** vers le visuel.

    *Les labos utilisent une notation abrégée pour référencer un champ ou une hiérarchie. Voici le résultat : **Region \| Regions**. Dans cet exemple, **Region** est le nom de la table et **Regions** correspond au nom de la hiérarchie.*

5. Ajoutez également le champ **Sales \| Sales** (Ventes | Ventes).

6. Pour développer toute la hiérarchie, cliquez deux fois sur l’icône de flèche à deux branches en haut à droite du visuel matrice.

    ![Image 47](Linked_image_Files/06-create-dax-calculations-in-power-bi-desktop-advanced_image11.png)

    *Pour rappel, la hiérarchie **Regions** comporte les niveaux **Group**, **Country**, et **Region**.*

7. Pour mettre en forme le visuel, sélectionnez le volet **Mise en forme** dans le volet **Visualisations**.

    ![Image 14](Linked_image_Files/06-create-dax-calculations-in-power-bi-desktop-advanced_image12.png)

8. Dans la zone **Recherche**, entrez **Échelonné**.

9. **Désactivez** la propriété **Disposition échelonnée**.

    ![Image 49](Linked_image_Files/06-create-dax-calculations-in-power-bi-desktop-advanced_image14.png)

10. Vérifiez que le visuel matrice comporte maintenant quatre en-têtes de colonne.

    ![Image 50](Linked_image_Files/06-create-dax-calculations-in-power-bi-desktop-advanced_image15.png)

    *Chez Adventure Works, les régions de vente sont organisées en groupes, pays et régions. Tous les pays, à l’exception des États-Unis, comportent une seule région, qui est nommée après le pays. Comme les États-Unis constituent un grand secteur de vente, ils sont divisés en cinq régions de vente.*

    *Vous allez créer plusieurs mesures dans cet exercice, puis les tester en les ajoutant au visuel matrice.*

### <a name="task-3-manipulate-filter-context"></a>**Tâche 3 : Manipuler le contexte de filtre**

Dans cette tâche, vous allez créer plusieurs mesures avec des expressions DAX qui utilisent la fonction CALCULATE() pour manipuler le contexte de filtre.

1. Ajoutez une mesure à la table **Sales** (Ventes), à partir de l’expression suivante :

    *Par souci pratique, toutes les définitions DAX de ce labo peuvent être copiées à partir du fichier **D:\PL300\Labs\05-create-dax-calculations-in-power-bi-desktop-advanced\Assets\Snippets.txt**.*


    **DAX**


    ```
    Sales All Region =

    CALCULATE(SUM(Sales[Sales]), REMOVEFILTERS(Region))
    ```


    *La fonction CALCULATE() est une fonction puissante servant à manipuler le contexte de filtre. Le premier argument est une expression ou une mesure (à savoir une simple expression nommée). Les arguments suivants permettent la modification du contexte de filtre.*

    *La fonction REMOVEFILTERS() supprime les filtres actifs. Elle prend comme argument une table, une ou plusieurs colonnes, ou rien du tout.*

    *Dans cette formule, la mesure évalue la somme de la colonne **Sales** dans un contexte de filtre modifié, ce qui supprime tous les filtres appliqués à la table **Region**.*

2. Ajoutez la mesure **Sales All Région** (Ventes toutes régions) au visuel matrice.

    ![Image 52](Linked_image_Files/06-create-dax-calculations-in-power-bi-desktop-advanced_image16.png)

3. Comme vous pouvez le constater, la mesure **Sales All Region** (Ventes Toutes régions) calcule le total des ventes pour toutes les régions, tous les pays (sous-total) et tous les groupes (sous-total).

    *La nouvelle mesure n’offre pas encore un résultat intéressant. Lorsque l’on divise les ventes d’un groupe, d’un pays ou d’une région par cette valeur, on obtient un ratio utile connu sous le nom de « pourcentage du total général ».*

4. Dans le volet **Champs**, vérifiez que la mesure **Sales All Region** est sélectionnée (elle a alors un arrière-plan gris foncé), puis, dans la barre de formule, remplacez le nom de la mesure et la formule par la formule suivante :

    *Conseil : Pour remplacer la formule existante, commencez par copier l’extrait de code. Ensuite, cliquez à l’intérieur de la barre de formule et appuyez sur **Ctrl+A** pour sélectionner tout le texte. Ensuite, appuyez sur **Ctrl+V** pour coller l’extrait de code et ainsi remplacer le texte sélectionné. Appuyez enfin sur **Entrée**.*


    **DAX**


    ```
    Sales % All Region =  
    ‎DIVIDE(  
    ‎ SUM(Sales[Sales]),  
    ‎ CALCULATE(  
    ‎ SUM(Sales[Sales]),  
    ‎ REMOVEFILTERS(Region)  
    ‎ )  
    ‎)
    ```


    *La mesure a été renommée pour refléter avec précision la formule mise à jour. La fonction DIVIDE() divise la mesure **Sales** non modifiée par le contexte de filtre par la mesure **Sales** dans un contexte modifié, ce qui supprime tous les filtres appliqués à la table **Region**.*

5. Comme vous pouvez le constater dans le visuel matrice, la mesure a été renommée et une autre valeur apparaît maintenant pour chaque groupe, pays et région.

6. Paramétrez la mesure **Sales % All Region** (Pourcentage Ventes Toutes régions) sous forme de pourcentage à deux décimales.

7. Dans le visuel matrice, passez en revue les valeurs de la mesure **Sales % All Region** (Pourcentage Ventes Toutes régions).

    ![Image 53](Linked_image_Files/06-create-dax-calculations-in-power-bi-desktop-advanced_image17.png)

8. Ajoutez une autre mesure à la table **Sales** (Ventes), à partir de l’expression suivante, sous forme de pourcentage :


    **DAX**

    ```
    Sales % Country =  
    ‎DIVIDE(  
    ‎ SUM(Sales[Sales]),  
    ‎ CALCULATE(  
    ‎ SUM(Sales[Sales]),  
    ‎ REMOVEFILTERS(Region[Region])  
    ‎ )  
    ‎)
    ```


9. Comme vous pouvez le constater, la formule de la mesure **Sales % Country** (Pourcentage Ventes Pays) est légèrement différente de celle de la mesure **Sales % All Region** (Pourcentage Ventes Toutes régions).

    *En effet, le dénominateur modifie le contexte de filtre en supprimant les filtres sur la colonne **Region** de la table **Region**, et non sur toutes les colonnes de la table **Region**. Par conséquent, tous les filtres appliqués aux colonnes du groupe ou du pays sont conservés. Le résultat obtenu représente les ventes sous forme de pourcentage du pays.*

10. Ajoutez la mesure **Sales % Country** (Pourcentage Ventes Pays) au visuel matrice.

11. Comme vous pouvez le constater, seules les régions des États-Unis produisent une valeur différente de 100%.

    ![Image 54](Linked_image_Files/06-create-dax-calculations-in-power-bi-desktop-advanced_image18.png)

    *Pour rappel, seuls les États-Unis comportent plusieurs régions. Tous les autres pays sont composés d’une seule région, ce qui explique pourquoi ils indiquent tous 100 %.*

12. Pour améliorer la lisibilité du visuel, remplacez la mesure **Sales % Country** (Pourcentage Ventes Pays) par cette formule améliorée.


    **DAX**


    ```
    Sales % Country =  
    ‎IF(  
    ‎ ISINSCOPE(Region[Region]),  
    ‎ DIVIDE(  
    ‎ SUM(Sales[Sales]),  
    ‎ CALCULATE(  
    ‎ SUM(Sales[Sales]),  
    ‎ REMOVEFILTERS(Region[Region])  
    ‎ )  
    ‎ )  
    ‎)
    ```


    *Imbriquée dans la fonction IF(), la fonction ISINSCOPE() permet de déterminer si la colonne Region (Région) est le niveau dans une hiérarchie de niveaux. Si la valeur est true, la fonction DIVIDE() est évaluée. Comme il n’y a pas de partie fausse, une valeur vide est retournée si la colonne Region n’est pas comprise dans la portée.*

13. Comme vous pouvez le constater, la mesure **Sales % Country** (Pourcentage Ventes Pays) ne retourne maintenant de valeur que si la région est comprise dans la portée.

    ![Image 55](Linked_image_Files/06-create-dax-calculations-in-power-bi-desktop-advanced_image19.png)

14. Ajoutez une autre mesure à la table **Sales** (Ventes), à partir de l’expression suivante, sous forme de pourcentage :


    **DAX**


    ```
    Sales % Group =  
    ‎DIVIDE(  
    ‎ SUM(Sales[Sales]),  
    ‎ CALCULATE(  
    ‎ SUM(Sales[Sales]),  
    ‎ REMOVEFILTERS(  
    ‎ Region[Region],  
    ‎ Region[Country]  
    ‎ )  
    ‎ )  
    ‎)
    ```


    *Pour formuler les ventes sous forme de pourcentage d’un groupe, vous pouvez appliquer deux filtres qui suppriment les filtres sur deux colonnes.*

15. Ajoutez la mesure **Sales % Group** (Pourcentage Ventes Groupe) au visuel matrice.

16. Pour améliorer la lisibilité du visuel, remplacez la mesure **Sales % Group** (Pourcentage Ventes Groupe) par cette formule améliorée.


    **DAX**


    ```
    Sales % Group =  
    ‎IF(  
    ‎ ISINSCOPE(Region[Region])  
    ‎ || ISINSCOPE(Region[Country]),  
    ‎ DIVIDE(  
    ‎ SUM(Sales[Sales]),  
    ‎ CALCULATE(  
    ‎ SUM(Sales[Sales]),  
    ‎ REMOVEFILTERS(  
    ‎ Region[Region],  
    ‎ Region[Country]  
    ‎ )  
    ‎ )  
    ‎ )  
    ‎)
    ```


17. Comme vous pouvez le constater, la mesure **Sales % Group** (Pourcentage Ventes Groupe) ne retourne maintenant de valeur que si la région est comprise dans la portée.

18. Dans l’affichage Modèle, placez les trois nouvelles mesures dans un dossier d’affichage nommé **Ratios**.

    ![Image 56](Linked_image_Files/06-create-dax-calculations-in-power-bi-desktop-advanced_image20.png)

19. Enregistrez le fichier Power BI Desktop.

    *Les mesures ajoutées à la table **Sales** ont modifié le contexte de filtre pour produire une navigation hiérarchique. Comme vous pouvez le constater, le modèle permettant d’effectuer le calcul d’un sous-total implique de supprimer certaines colonnes du contexte de filtre ; pour obtenir le total général, vous devez supprimer toutes les colonnes.*

## <a name="exercise-2-work-with-time-intelligence"></a>**Exercice 2 : Utiliser Time Intelligence**

Dans cet exercice, vous allez créer une mesure de ventes cumulées annuelles jusqu'à ce jour et une mesure de croissance des ventes en glissement annuel.

### <a name="task-1-create-a-ytd-measure"></a>**Tâche 1 : Créer une mesure de ventes cumulées annuelles jusqu'à ce jour**

Au cours de cette tâche, vous allez créer une mesure de ventes cumulées annuelles jusqu'à ce jour.

1. Comme vous pouvez le constater sur la **Page 2** de l’affichage Rapport, le visuel matrice présente différentes mesures en regroupant les années et les mois sur les lignes.

2. Ajoutez une mesure à la table **Sales** (Ventes), à partir de l’expression suivante, sans décimale :


    **DAX**


    ```
    Sales YTD =  
    ‎TOTALYTD(SUM(Sales[Sales]), 'Date'[Date], "6-30")
    ```


    *La fonction TOTALYTD() évalue une expression (dans ce cas, la somme de la colonne **Sales**) sur une colonne de date donnée. La colonne de date doit appartenir à une table de dates marquée comme telle, comme cela a été fait dans le labo **Créer des calculs DAX dans Power BI Desktop (partie 1)** .*

    *La fonction peut également accepter un troisième argument facultatif représentant la dernière date d’une année. En l’absence de cette date, le 31 décembre est considéré comme la dernière date de l’année. Juin est le dernier mois de l’année d’Adventure Works ; d’où l’argument « 6-30 ».*

3. Ajoutez le champ **Sales** (Ventes) et la mesure **Sales YTD** (Ventes cumulées annuelles jusqu'à ce jour) au visuel matrice.

4. Comme vous pouvez le constater, les valeurs de ventes sont cumulées au cours de l’année.

    ![Image 59](Linked_image_Files/06-create-dax-calculations-in-power-bi-desktop-advanced_image21.png)

    *La fonction TOTALYTD() effectue une manipulation de filtre, en l’occurrence de temps. Par exemple, dans le cadre du calcul des ventes cumulées annuelles jusqu'à ce jour pour septembre 2017 (le troisième mois de l’exercice), tous les filtres de la table **Date** sont supprimés et remplacés par un nouveau filtre de dates qui commence au début de l’année (1er juillet 2017) et s’étend jusqu’à la dernière date de la période du contexte (30 septembre 2017).*

    *Notez que de nombreuses fonctions Time Intelligence sont disponibles dans DAX pour gérer les manipulations de filtre de temps courantes.*

### <a name="task-2-create-a-yoy-growth-measure"></a>**Tâche 2 : Créer une mesure de croissance en glissement annuel**

Au cours de cette tâche, vous allez créer une mesure de croissance des ventes en glissement annuel.

1. Ajoutez une autre mesure à la table **Sales** (Ventes), à partir de l’expression suivante :


    **DAX**


    ```
    Sales YoY Growth =  
    ‎VAR SalesPriorYear =  
    ‎ CALCULATE(  
    ‎ SUM(Sales[Sales]),  
    ‎ PARALLELPERIOD(  
    ‎ 'Date'[Date],  
    ‎ -12,  
    ‎ MONTH  
    ‎ )  
    ‎ )  
    ‎RETURN  
    ‎ SalesPriorYear
    ```


    *La formule de mesure **Croissance des ventes en glissement annuel** déclare une variable. Les variables peuvent être utiles pour simplifier la logique des formules, et plus efficaces lorsqu’une expression doit être évaluée plusieurs fois dans la formule (ce qui sera le cas pour la logique de croissance en glissement annuel). Les variables sont déclarées à l’aide d’un nom unique, et l’expression de la mesure doit être produite après le mot clé **RETURN**.*

    *La variable **SalesPriorYear** est une expression calculant la somme de la colonne **Sales** dans un contexte modifié qui utilise la fonction PARALLELPERIOD() pour revenir en arrière de 12 mois à partir de chaque date dans le contexte de filtre.*

2. Ajoutez la mesure **Sales YoY Growth** (Croissance des ventes en glissement annuel) au visuel matrice.

3. Comme vous pouvez le constater, la nouvelle mesure retourne une valeur vide pour les 12 premiers mois (aucune vente n’ayant été enregistrée avant l’exercice 2017).

4. Comme vous pouvez le constater, la valeur de la mesure **Croissance des ventes en glissement annuel** de **Juil 2018** est la valeur **Ventes** de **Juil 2017**.

    ![Image 61](Linked_image_Files/06-create-dax-calculations-in-power-bi-desktop-advanced_image22.png)

    *Maintenant que la « partie difficile » de la formule a été testée, vous pouvez remplacer la mesure par la formule finale qui calcule le résultat de la croissance.*

5. Pour terminer la mesure, remplacez la mesure **Sales YoY Growth** (Croissance des ventes en glissement annuel) par cette formule, sous forme de pourcentage à deux décimales :


    **DAX**


    ```
    Sales YoY Growth =  
    ‎VAR SalesPriorYear =  
    ‎ CALCULATE(  
    ‎ SUM(Sales[Sales]),  
    ‎ PARALLELPERIOD(  
    ‎ 'Date'[Date],  
    ‎ -12,  
    ‎ MONTH  
    ‎ )  
    ‎ )  
    ‎RETURN  
    ‎ DIVIDE(  
    ‎ (SUM(Sales[Sales]) - SalesPriorYear),  
    ‎ SalesPriorYear  
    ‎ )
    ```


6. Comme vous pouvez le constater, la clause **RETURN** de la formule comporte deux références à la variable.

7. Vérifiez que la croissance en glissement annuel de **Juillet 2018** est bien de **392,83 %**.

    ![Image 62](Linked_image_Files/06-create-dax-calculations-in-power-bi-desktop-advanced_image23.png)

    *Cela signifie que les ventes de juillet 2018 (2 411 559 $) représentent une augmentation de près de 400 % (presque 4 fois) par rapport aux ventes réalisées l’année précédente (489 328 $).*

8. Dans l’affichage Modèle, placez les deux nouvelles mesures dans un dossier d’affichage nommé **Time Intelligence**.

    ![Image 63](Linked_image_Files/06-create-dax-calculations-in-power-bi-desktop-advanced_image24.png)

### <a name="task-3-finish-up"></a>**Tâche 3 : Terminer**

Dans cette tâche, vous terminez le labo.

1. Pour nettoyer la solution prête pour le développement de rapport, en bas à gauche, cliquez avec le bouton droit sur l’onglet **Page 2**, puis sélectionnez **Supprimer la page**.

    ![Image 17](Linked_image_Files/06-create-dax-calculations-in-power-bi-desktop-advanced_image25.png)

2. Quand vous êtes invité à supprimer la page, cliquez sur **Supprimer**.

    ![Image 18](Linked_image_Files/06-create-dax-calculations-in-power-bi-desktop-advanced_image26.png)

3. Supprimez également la **page 3**.

4. Pour effacer la page restante, sélectionnez le visuel table dans cette page, puis appuyez sur la touche **Supprimer**.

5. Enregistrez le fichier Power BI Desktop.

6. Si vous avez l’intention de démarrer le labo suivant, laissez Power BI Desktop ouvert.

    *Vous créerez un rapport basé sur le modèle de données dans le labo **Concevoir un rapport dans Power BI Desktop (partie 1)** .*
