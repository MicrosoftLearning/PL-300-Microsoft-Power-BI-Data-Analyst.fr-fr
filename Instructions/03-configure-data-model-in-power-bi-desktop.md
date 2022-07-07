---
lab:
  title: Modéliser les données dans Power BI Desktop
  module: Module 4 - Design a Data Model in Power BI
ms.openlocfilehash: 1617d6a1a50e37a5dc7d9094eaa86057b2ddeee2
ms.sourcegitcommit: 9ea1e7e21b9b3c718030c94b1693d153a2010ec7
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/07/2022
ms.locfileid: "147015363"
---
# <a name="model-data-in-power-bi-desktop"></a>**Modéliser les données dans Power BI Desktop**

**La durée estimée pour effectuer ce tutoriel est de 45 minutes.**

Dans ce labo, vous allez commencer à développer le modèle de données. Pour cela, vous créerez des relations entre les tables, puis configurerez des propriétés de table et de colonne pour améliorer la convivialité du modèle de données. Vous créerez également des hiérarchies et des mesures rapides.

Dans ce labo, vous allez découvrir comment :

- Créer des relations de modèle

- Configurer des propriétés de table et de colonne

- Créer des hiérarchies


### <a name="lab-story"></a>**Histoire du labo**

Ce labo est l’un des nombreux labos d’une série qui a été conçue comme une histoire complète allant de la préparation des données jusqu’à leur publication sous forme de rapports et de tableaux de bord. Vous pouvez effectuer ces labos dans l’ordre de votre choix. Toutefois, si vous comptez faire plusieurs labos, nous vous suggérons de suivre cet ordre :

1. Préparer des données dans Power BI Desktop

2. Charger des données dans Power BI Desktop

3. **Modéliser les données dans Power BI Desktop**

5. Créer des calculs DAX dans Power BI Desktop (partie 1)

6. Créer des calculs DAX dans Power BI Desktop (partie 2)

7. Concevoir un rapport dans Power BI Desktop, partie 1

8. Concevoir un rapport dans Power BI Desktop, partie 2

9. Créer un tableau de bord Power BI

10. Analyser les données dans Power BI Desktop

11. Appliquer la sécurité au niveau des lignes

## <a name="exercise-1-create-model-relationships"></a>**Exercice 1 : Créer des relations de modèle**

Dans cet exercice, vous allez créer des relations de modèle.

### <a name="task-1-get-started"></a>**Tâche 1 : Démarrer**

Dans cette tâche, vous configurez l’environnement pour le labo.

*Important : Si vous venez d’effectuer le labo précédent (et que vous l’avez entièrement terminé), ignorez cette tâche et passez directement à la tâche suivante.*

1. Pour ouvrir Power BI Desktop, accédez à la barre des tâches et cliquez sur le raccourci Microsoft Power BI Desktop.

    ![Image 12](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image1.png)

1. Pour fermer la fenêtre de démarrage, en haut à gauche de cette fenêtre, sélectionnez **X**.

    ![Image 11](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image2.png)

1. Pour ouvrir le fichier Power BI Desktop de démarrage, sélectionnez l’onglet de ruban **Fichier** afin de passer en mode Backstage.

1. Sélectionnez **Ouvrir un rapport**.

    ![Image 10](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image3.png)

1. Cliquez sur **Parcourir les rapports**.

    ![Image 8](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image4.png)

1. Dans la fenêtre **Ouvrir**, accédez au dossier **D:\PL300\Labs\03-configure-data-model-in-power-bi-desktop\Starter**.

1. Sélectionnez le fichier **Sales Analysis** (Analyse des ventes).

1. Cliquez sur **Ouvrir**.

    ![Image 7](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image5.png)

1. Fermez toutes les fenêtres d’information qui se sont éventuellement ouvertes.

1. Pour créer une copie du fichier, sélectionnez l’onglet de ruban **Fichier** afin de passer en mode Backstage.

1. Sélectionnez **Enregistrer sous**.

    ![Image 5](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image6.png)

1. Si vous êtes invité à appliquer les modifications, cliquez **Appliquer**.

    ![Image 15](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image7.png)

1. Dans la fenêtre **Enregistrer sous**, accédez au dossier **D:\PL300\MySolution**.

1. Cliquez sur **Enregistrer**.

    ![Image 3](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image8.png)

### <a name="task-2-create-model-relationships"></a>**Tâche 2 : Créer des relations de modèle**

Dans cette tâche, vous allez créer des relations de modèle.

1. Dans Power BI Desktop, à gauche, cliquez sur l’icône de la vue **Modèle**.

    ![Image 1](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image9.png)

2. Si vous ne voyez pas les sept tables, faites défiler horizontalement vers la droite, puis rapprochez les tables en les faisant glisser pour qu’elles soient toutes visibles en même temps.

    *Conseil : Vous pouvez également vous servir du contrôle de zoom situé en bas de la fenêtre.*

    *Dans la vue Modèle, il est possible de voir chacune des tables et leurs relations éventuelles (connecteurs entre les tables). Actuellement, il n’y a aucune relation, car dans le labo **Préparer des données dans Power BI Desktop**, vous aviez désactivé les options de relation de chargement des données.*

3. Pour revenir à la vue Rapport, à gauche, cliquez sur l’icône de la vue **Rapport**.

    ![Image 327](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image10.png)

4. Pour voir tous les champs de la table, dans le volet **Champs**, cliquez avec le bouton droit sur une zone vide, puis sélectionnez **Développer tout**.

    ![Image 328](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image11.png)

5. Pour créer un visuel de table, dans le volet **Champs**, à partir de la table **Product**, cochez le champ **Category**.

    ![Image 329](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image12.png)

    *Les labos utilisent une notation abrégée pour référencer un champ. Voici le résultat : **Product \| Category**. Dans cet exemple, **Product** est le nom de la table et **Category** correspond au nom du champ.*

6. Pour ajouter une colonne à la table, dans le volet **Champs**, cochez le champ **Sales \| Sales**.

7. Notez que le visuel de table liste quatre catégories de produits et que la valeur des ventes est la même pour chaque catégorie et pour le total.

    ![Image 330](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image13.png)

    *Le problème est dû au fait que la table est basée sur des champs de tables différentes. Chaque catégorie de produit est censée afficher les ventes de cette catégorie. Toutefois, étant donné qu’il n’existe pas de relation de modèle entre ces tables, la table **Sales** n’est pas filtrée. Vous allez maintenant ajouter une relation pour propager les filtres entre les tables.*

8. Sous l’onglet de ruban **Modélisation**, à partir du groupe **Relations**, cliquez sur **Gérer les relations**.

    ![Image 331](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image14.png)

9. Dans la fenêtre **Gérer les relations**, notez qu’aucune relation n’est encore définie.

10. Pour créer une relation, cliquez sur **Nouveau**.

    ![Image 332](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image15.png)

11. Dans la fenêtre **Créer une relation**, dans la première liste déroulante, sélectionnez la table **Product**.

    ![Image 333](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image16.png)

12. Dans la deuxième liste déroulante (sous la grille de la table **Product**), sélectionnez la table **Sales**.

    ![Image 334](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image17.png)

13. Notez que les colonnes **ProductKey** de chaque table sont sélectionnées automatiquement.

    *Les colonnes ont été automatiquement sélectionnées parce qu’elles ont le même nom et le même type de données.*

14. Dans la liste déroulante **Cardinalité**, notez que l’option **Un à plusieurs (1:*)** est sélectionnée.

    *La cardinalité est détectée automatiquement, car Power BI comprend que la colonne **ProductKey** de la table **Product** contient des valeurs uniques. La relation un-à-plusieurs est la cardinalité la plus courante, et toutes les relations que vous créez dans ce labo sont de ce type.*

15. Dans la liste déroulante **Direction du filtre croisé**, notez que l’option **À sens unique** est sélectionnée.

    *Cette direction signifie que les filtres sont propagés du côté « un » au côté « plusieurs ». Dans ce cas, les filtres appliqués à la table **Product** sont propagés à la table **Sales**, mais pas dans la direction opposée.*

16. Notez que l’option **Rendre cette relation active** est cochée.

    *Les relations actives propagent les filtres. Il est possible de marquer une relation comme inactive pour ne pas propager les filtres. Vous pouvez avoir des relations inactives si plusieurs chemins de relation existent entre les tables. Dans ce cas, les calculs de modèle peuvent utiliser des fonctions spéciales pour les activer.*

17. Cliquez sur **OK**.

    ![Image 335](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image18.png)

18. Dans la fenêtre **Gérer les relations**, notez que la nouvelle relation est listée, puis cliquez sur **Fermer**.

    ![Image 336](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image19.png)

19. Dans le rapport, notez que le visuel de table a été mis à jour pour afficher des valeurs différentes pour chaque catégorie de produit.

    ![Image 337](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image20.png)

    *Les filtres appliqués à la table **Product** sont désormais propagés à la table **Sales**.*

20. Basculez vers l’affichage Modèle, puis notez qu’il existe maintenant un connecteur entre les deux tables (peu importe si les tables sont positionnées en regard de l’autre).

    ![Image 338](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image21.png)

21. Dans le diagramme, notez que vous pouvez interpréter la cardinalité qui est représentée par les indicateurs **1** et *****.

    *La direction du filtre est représentée par la tête de flèche. Une ligne pleine représente une relation active tandis qu’une ligne en pointillés représente une relation inactive.*

22. Placez le curseur sur la relation pour mettre en surbrillance les colonnes associées.

    *Il existe un moyen plus simple de créer une relation. Dans le diagramme de modèle, vous pouvez faire glisser-déposer des colonnes pour créer une relation.*

23. Pour créer une relation en utilisant une technique différente, à partir de la table **Reseller**, faites glisser la colonne **ResellerKey** sur la colonne **ResellerKey** de la table **Sales**.

    ![Image 339](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image22.png)

    *Conseil : Parfois, il est impossible de faire glisser une colonne. Dans ce cas, sélectionnez une autre colonne, puis resélectionnez la colonne que vous souhaitez faire glisser et réessayez. Assurez-vous que vous voyez la nouvelle relation ajoutée au diagramme.*

24. Créez la nouvelle technique pour créer les deux relations modèle suivantes :

    - **Region \| SalesTerritoryKey** vers **Sales \| SalesTerritoryKey**

    - **Salesperson \| EmployeeKey** vers **Sales \| EmployeeKey**

25. Dans le diagramme, organisez les tables afin que la table **Sales** soit positionnée au centre du diagramme et que les tables associées soient organisées à ce sujet. Placez les tables déconnectées sur le côté.

    ![Image 340](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image23.png)


26. Enregistrez le fichier Power BI Desktop.

## <a name="exercise-2-configure-tables"></a>**Exercice 2 : Configurer les tables**

Dans cet exercice, vous allez configurer toutes les tables. Pour cela, vous allez créer des hiérarchies et masquer, mettre en forme et catégoriser les colonnes.

### <a name="task-1-configure-the-product-table"></a>**Tâche 1 : Configurer la table Product**

Dans cette tâche, vous allez configurer la table **Product**.

1. Dans la vue Modèle, dans le volet **Champs**, si nécessaire, développez la table **Product**.

2. Pour créer une hiérarchie, dans le volet **Champs**, cliquez avec le bouton droit sur la colonne **Category**, puis sélectionnez **Créer une hiérarchie**.

    ![Image 341](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image24.png)

3. Dans le volet **Propriétés** (à gauche du volet **Champs**), dans la zone **Nom**, remplacez le texte par **Products**.

    ![Image 344](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image25.png)

4. Pour ajouter le deuxième niveau à la hiérarchie, dans le volet **Propriétés**, dans la liste déroulante **Hiérarchie**, faites défiler vers le bas et sélectionnez **Subcategory**.

5. Pour ajouter le troisième niveau à la hiérarchie, dans la liste déroulante **Hiérarchie**, sélectionnez **Product**.

6. Pour terminer la conception de la hiérarchie, cliquez sur **Appliquer les changements de niveau**.

    ![Image 343](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image26.png)

    *Conseil : N’oubliez pas de cliquer sur **Appliquer les modifications de niveau**. Il est courant d’oublier cette étape.*

7. Dans le volet **Champs**, notez la hiérarchie **Products**.

    ![Image 347](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image27.png)

8. Pour faire apparaître les niveaux de hiérarchie, développez la hiérarchie **Products**.

    ![Image 346](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image28.png)

9. Pour organiser les colonnes dans un dossier d’affichage, dans le volet **Champs**, sélectionnez d’abord la colonne **Background Color Format**.

10. Tout en appuyant sur la touche **Ctrl**, sélectionnez la colonne **Font Color Format**.

11. Dans la zone **Dossier d’affichage** du volet **Propriétés**, entrez **Mise en forme**.

    ![Image 348](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image29.png)

12. Dans le volet **Champs**, notez que les deux colonnes se trouvent désormais dans un dossier.

    ![Image 349](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image30.png)

    *Les dossiers d’affichage sont un excellent moyen de désencombrer les tables, en particulier celles qui contiennent un grand nombre de champs.*

### <a name="task-2-configure-the-region-table"></a>**Tâche 2 : Configurer la table Region**

Dans cette tâche, vous allez configurer la table **Region**.

1. Dans la table **Region**, créez une hiérarchie nommée **Region** avec les trois niveaux suivants :

    - Group

    - Country

    - Région

    ![Image 350](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image31.png)

2. Sélectionnez la colonne **Country** (pas le niveau de hiérarchie **Country**).

3. Dans le volet **Propriétés**, développez la section **Avancé** (en bas du volet), puis dans la liste déroulante **Catégorie de données**, sélectionnez **Country/Region**.

    ![Image 352](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image32.png)

    *La catégorisation des données peut fournir des indications au concepteur de rapports. Dans ce cas, le fait de placer la colonne dans la catégorie Country/Region permet de fournir des informations plus précises à Power BI pour le rendu d’une visualisation de carte.*

### <a name="task-3-configure-the-reseller-table"></a>**Tâche 3 : Configurer la table Reseller**

Dans cette tâche, vous allez configurer la table **Reseller**.

1. Dans la table **Reseller**, créez une hiérarchie nommée **Resellers** avec les deux niveaux suivants :

    - Business Type

    - Reseller

    ![Image 351](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image33.png)

2. Créez une deuxième hiérarchie nommée **Geography** avec les quatre niveaux suivants :

    - Country-Region

    - État-Province

    - City

    - Reseller

    ![Image 353](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image34.png)

3. Définissez la **catégorie de données** pour les colonnes **Pays-Région**, **État-Province**, et **Ville** (non le niveau hiérarchique) sur **Pays/Région**, **État ou Province**, et **Ville**, respectivement. 

### <a name="task-4-configure-the-sales-table"></a>**Tâche 4 : Configurer la table Sales**

Dans cette tâche, vous allez configurer la table **Sales**.

1. Dans la table **Sales**, sélectionnez la colonne **Cost**.

2. Dans la zone **Description** du volet **Propriétés**, entrez : **Based on standard cost**

    ![Image 358](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image35.png)

    *Les descriptions peuvent être appliquées aux tables, aux colonnes, aux hiérarchies ou aux mesures. Dans le volet **Champs**, le texte de la description apparaît dans une info-bulle quand un auteur de rapport place son curseur sur le champ.*

3. Sélectionnez la colonne **Quantity**.

4. Dans la section **Mise en forme** du volet **Propriétés**, faites passer la propriété **Séparateur de milliers** en position **Oui**.

    ![Image 357](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image36.png)

5. Sélectionnez la colonne **Unit Price**.

6. Dans la section **Mise en forme** du volet **Propriétés**, définissez la propriété **Nombre de décimales** avec la valeur **2**.

7. Dans la liste déroulante **Totaliser par** du groupe **Avancé** (vous devrez peut-être faire défiler la page pour y accéder), sélectionnez **Moyenne**.

    ![Image 354](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image37.png)

    *Par défaut, les colonnes numériques sont totalisées en additionnant les valeurs. Ce comportement par défaut ne convient pas à une colonne comme **Unit Price** qui représente un taux. Le fait de choisir une moyenne comme méthode de totalisation par défaut produit un résultat significatif.*

### <a name="task-5-bulk-update-properties"></a>**Tâche 5 : Mettre à jour en bloc les propriétés**

Dans cette tâche, vous allez mettre à jour plusieurs colonnes à l’aide une seule mise à jour en bloc. Vous suivrez cette approche pour masquer les colonnes et mettre en forme les valeurs des colonnes.

1. Dans le volet **Champs**, sélectionnez la colonne **Product \| ProductKey**.

2. Tout en appuyant sur la touche **Ctrl**, sélectionnez les 13 colonnes suivantes (couvrant plusieurs tables) :

    - Region \| SalesTerritoryKey

    - Reseller \| ResellerKey

    - Sales \| EmployeeKey
    
    - Sales \| ProductKey

    - Sales \| ResellerKey

    - Sales \| SalesOrderNumber

    - Sales \| SalesTerritoryKey

    - Salesperson \| EmployeeID

    - Salesperson \| EmployeeKey

    - Salesperson \| UPN

    - SalespersonRegion \| EmployeeKey

    - SalespersonRegion \| SalesTerritoryKey

    - Targets \| EmployeeID

3. Dans le volet **Propriétés**, faites passer la propriété **Est masqué** sur **Oui**.

    ![Image 355](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image38.png)

    *Les colonnes ont été masquées, car elles sont utilisées par des relations ou sont utilisées dans la configuration de sécurité au niveau des lignes ou dans la logique de calcul.*

    *Vous utiliserez la colonne **SalesOrderNumber** dans un calcul dans le labo **Créer des calculs DAX dans Power BI Desktop (partie 1)** .*

4. Sélectionnez les trois colonnes suivantes (sélection multiple) :

    - Product \| Standard Cost

    - Sales \| Cost

    - Sales \| Sales

5. Dans la section **Mise en forme** du volet **Propriétés**, définissez la propriété **Nombre de décimales** avec la valeur **0** (zéro).

    ![Image 356](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image39.png)

## <a name="exercise-3-review-the-model-interface"></a>**Exercise 3 : Passer en revue l’interface du modèle**

Dans cet exercice, vous allez passer à la vue Rapport et examiner l’interface du modèle.

### <a name="task-1-review-the-model-interface"></a>**Tâche 1 : Examiner l’interface du modèle**

Dans cette tâche, vous allez passer à la vue Rapport et examiner l’interface du modèle.

1. Passez à la vue Rapport.

2. Dans le volet **Champs**, notez les points suivants :

    - Les colonnes, les hiérarchies et leurs niveaux sont des champs qui peuvent être utilisés pour configurer des visuels de rapport

    - Seuls les champs applicables à la création de rapports sont visibles.

    - La table **SalespersonRegion** n’est pas visible, car tous ses champs sont masqués

    - Les champs spatiaux dans les tables **Region** et **Reseller** sont ornés d’une icône spatiale.

    - Les champs ornés du symbole sigma (Ʃ) sont totalisés par défaut.

    - Une info-bulle apparaît quand vous placez le curseur sur le champ **Sales \| Cost**

3. Développez le champ **Sales \| OrderDate**, puis notez qu’il révèle une hiérarchie de dates.

    ![Image 359](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image40.png)

    *Le champ **Targets \| TargetMonth** présente une hiérarchie similaire. Ces hiérarchies n’ont pas été créées par vous. Elles sont créées automatiquement. Il y a toutefois un problème. L’exercice comptable d’Adventure Works commence le 1er juillet de chaque année. En revanche, l’année de la hiérarchie de dates qui est créée automatiquement commence le 1er janvier de l’année.*

    *Vous allez maintenant désactiver ce comportement automatique. Dans le labo **Créer des calculs DAX dans Power BI Desktop (partie 1)** , vous utiliserez DAX pour créer une table de dates et vous la configurerez pour définir le calendrier Adventure Works.*

4. Pour désactiver Date/heure automatique, cliquez sur l’onglet de ruban **Fichier** pour ouvrir le mode Backstage.

5. Sur la gauche, sélectionnez **Options et paramètres**, puis sélectionnez **Options**.

    ![Image 360](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image41.png)

6. Dans la fenêtre **Options**, à gauche, dans le groupe **Fichier actif**, sélectionnez **Chargement des données**.

    ![Image 361](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image42.png)

7. Dans la section **Time Intelligence**, décochez **Date/heure automatique**.

    ![Image 362](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image43.png)

8. Cliquez sur **OK**.

    ![Image 9](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image44.png)

9. Dans le volet **Champs**, vous pouvez noter que les hiérarchies de dates ne sont plus disponibles.

    ![Image 363](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image45.png)


## <a name="exercise-4-create-quick-measures"></a>**Exercise 4 : Créer des mesures rapides**

Dans cet exercice, vous allez créer deux mesures rapides.

### <a name="task-1-create-quick-measures"></a>**Tâche 1 : Créer des mesures rapides**

Au cours de cette tâche, vous allez créer deux mesures rapides pour calculer le profit et la marge bénéficiaire.

1. Cliquez avec le bouton droit sur la table **Sales** dans le volet **Champs**, puis sélectionnez **Nouvelle mesure rapide**.

    ![Image 366](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image46.png)

2. Dans la liste déroulante **Calcul** de la fenêtre **Mesures rapides**, dans le groupe **Opérations mathématiques**, sélectionnez **Soustraction**.

    ![Image 367](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image47.png)

3. Dans le volet **Champs** de la fenêtre **Mesures rapides**, développez la table **Sales**.

4. Faites glisser le champ **Sales** dans la zone **Valeur de base**.

5. Faites glisser le champ **Cost** dans la zone **Valeur à soustraire**.

    ![Image 368](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image48.png)

6. Cliquez sur **OK**.

    ![Image 369](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image49.png)

    *Une mesure rapide crée la formule de calcul pour vous. Ce type de mesure est facile et rapide à créer pour les calculs simples et courants. Vous créerez des mesures sans utiliser cet outil dans le labo **Créer des calculs DAX dans Power BI Desktop (partie 1)** .*

7. Dans la table **Sales** du volet **Champs**, notez cette nouvelle mesure.

    ![Image 370](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image50.png)

    *Les mesures sont ornées de l’icône de la calculatrice.*

8. Pour renommer la mesure, cliquez dessus avec le bouton droit, puis sélectionnez **Renommer**.

    ![Image 371](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image51.png)

    *Conseil : Pour renommer un champ, vous pouvez également double-cliquer dessus ou le sélectionner et appuyer sur **F2**.*

9. Renommez la mesure **Profit**, puis appuyez sur **Entrée**.

10. Dans la table **Sales**, ajoutez une deuxième mesure rapide basée sur les exigences suivantes :

    - Utiliser l’opération mathématique **Division**

    - Définir le **Numérateur** avec le champ **Sales \| Profit**

    - Définir le **Dénominateur** avec le champ **Sales \| Sales**

    - Renommer la mesure **Profit Margin**

    ![Image 372](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image52.png)

    ![Image 373](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image53.png)

11. Vérifiez que la mesure **Profit Margin** est sélectionnée, puis, dans le ruban contextuel **Outils de mesure**, choisissez le format **Pourcentage** avec deux décimales.

    ![Image 374](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image54.png)

12. Pour tester les deux mesures, commencez par sélectionner le visuel de table dans la page du rapport.

13. Dans le volet **Champs**, cochez les deux mesures.

    ![Image 375](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image55.png)

14. Cliquez sur le repère droit et faites-le glisser pour élargir le visuel de table.

    ![Image 376](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image56.png)

15. Vérifiez que les mesures produisent un résultat raisonnable qui est correctement mis en forme.

    ![Image 378](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image57.png)

### <a name="task-2-create-a-many-to-many-relationship"></a>**Tâche 2 : Créer une relation plusieurs-à-plusieurs**

Dans cette tâche, vous créez une relation plusieurs-à-plusieurs entre la table **Salesperson** et la table **Sales**.

1. Dans Power BI Desktop, dans le volet **Champs** de la vue Rapport, cochez les deux champs suivants pour créer un visuel de table :

    - Salesperson \| Salesperson

    - Sales \| Sales

    *Les labos utilisent une notation abrégée pour référencer un champ. Voici le résultat : **Salesperson \| Salesperson**. Dans cet exemple, **Salesperson** est le nom de la table et **Salesperson** correspond au nom du champ.*

    ![Image 1](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image9.png)

    *La table présente les ventes réalisées par chaque vendeur. Toutefois, il existe une autre relation entre les vendeurs et les ventes. Certains vendeurs appartiennent à une ou deux régions de vente voire plus. Par ailleurs, plusieurs vendeurs peuvent être affectés à une même région de vente.*

    *Du point de vue de la gestion des performances, les ventes d’un vendeur (sur la base des territoires qui lui sont affectés) doivent être analysées et comparées aux objectifs de vente. Dans le prochain exercice, vous allez créer les relations nécessaires à cette analyse.*

2. Notez que les ventes de Michael Blythe atteignent presque 9 millions de dollars.

3. Passez à la vue Modèle.

    ![Image 10](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image10.png)

4. Faites glisser la table **SalespersonRegion** pour la placer entre les tables **Region** et **Salesperson**.

5. Créez les deux relations de modèle suivantes par glisser-déposer :

    - **Salesperson \| EmployeeKey** à **SalespersonRegion \| EmployeeKey**

    - **Region \| SalesTerritoryKey** à **SalespersonRegion \| SalesTerritoryKey**

    *La table **SalespersonRegion** peut être considérée comme une table de pontage.*

6. Si vous passez à la vue Rapport, vous pouvez noter que le visuel n’a pas été mis à jour. Le résultat des ventes de Michael Blythe est le même.

7. Revenez à la vue Modèle, puis suivez les directions du filtre de relation (pointe de flèche) à partir de la table **Salesperson**.

    *Notez que la table **Salesperson** filtre la table **Sales**. Elle filtre également la table **SalespersonRegion**, mais ne continue pas de se propager des filtres à la table **Region** (la pointe de flèche va dans la mauvaise direction).*

    ![Image 380](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image11.png)

8. Pour modifier la relation entre les tables **Region** et **SalespersonRegion**, double-cliquez sur la relation.

9. Dans la liste déroulante **Direction du filtre croisé** de la fenêtre **Modifier la relation**, sélectionnez **Les deux**.

10. Cochez la case **Appliquer le filtre de sécurité dans les deux directions**.

    ![Image 381](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image12.png)

11. Cliquez sur **OK**.

    ![Image 335](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image13.png)

12. Notez que la relation a une double pointe de flèche.

    ![Image 382](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image14.png)

13. Si vous passez à la vue Rapport, vous pouvez noter que les valeurs des ventes sont toujours les mêmes.

    *Le problème est maintenant lié au fait qu’il existe deux chemins de propagation de filtre possibles entre les tables **Salesperson** et **Sales**. Cette ambiguïté est résolue en interne selon une évaluation de type « plus petit nombre de tables ». Pour être clair, vous ne devez pas concevoir des modèles avec ce type d'ambiguïté. Nous traiterons ce problème en partie plus tard dans ce labo, puis durant le labo **Créer des calculs DAX dans Power BI Desktop (partie 1)** .*

14. Basculez vers l’affichage Modèle.

15. Pour forcer la propagation du filtre par le biais de la table de pontage, modifiez (double-cliquez) la relation entre les tables **Salesperson** et **Sales**.

16. Dans la fenêtre **Modifier la relation**, décochez la case **Rendre cette relation active**.

    ![Image 383](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image15.png)

17. Cliquez sur **OK**.

    ![Image 5696](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image16.png)

    *La propagation du filtre suivra désormais le seul chemin actif.*

18. Dans le diagramme, notez que la relation inactive est représentée par une ligne en pointillés.

    ![Image 5697](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image17.png)

19. Si vous passez à la vue Rapport, vous pouvez noter que les ventes de Michael Blythe atteignent presque 22 millions de dollars.

    ![Image 5698](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image18.png)

20. Notez également que la somme des ventes de chaque vendeur dépasse le total de la table.

    *Cela s’observe souvent en présence d’une relation plusieurs-à-plusieurs qui compte plusieurs fois les résultats des ventes régionales. Prenons Brian Welcker, le deuxième vendeur listé. Le montant de ses ventes est égal au montant total des ventes. Comme il est le directeur des ventes, ce résultat est correct : ses ventes correspondent aux ventes de toutes les régions.*

    *Bien que la relation plusieurs-à-plusieurs fonctionne, il est pour l’instant impossible d’analyser les ventes réalisées par un vendeur (car la relation est inactive). Dans le labo **Créer des calculs DAX dans Power BI Desktop (partie 1)** , vous pourrez réactiver la relation quand vous introduirez une table calculée permettant d’analyser les performances des vendeurs dans leurs régions.*

21. Passez à la vue Modélisation, puis dans le diagramme, sélectionnez la table **Salesperson**.

22. Dans la zone **Nom** du volet **Propriétés**, remplacez le texte par **Salesperson (Performance)**.

    *La table renommée reflète désormais son objectif, à savoir signaler et analyser les performances des vendeurs en fonction des ventes réalisées dans les régions qui leur sont affectées.*

### <a name="task-3-relate-the-targets-table"></a>**Tâche 3 : Créer une relation à la table Targets**

Dans cette tâche, vous allez créer une relation à la table **Targets**.

1. Créez une relation à partir de la colonne **Salesperson (Performance) \| EmployeeID** et la colonne **Targets \| EmployeeID**.

2. Dans la vue Rapport, ajoutez le champ **Targets \| Target** au visuel de table.

3. Redimensionnez le visuel de table afin que toutes les colonnes soient visibles.

    ![Image 5699](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image19.png)

    *Vous pouvez désormais visualiser les ventes et les objectifs. Mais faites attention, et ce pour deux raisons. Premièrement, comme il n’y a pas de filtre sur une période de temps, les objectifs incluent également les quantités des objectifs futurs. Deuxièmement, les objectifs ne sont pas additifs et le total ne doit donc pas être affiché. Vous pouvez les désactiver à l’aide d’une mise en forme du visuel ou les supprimer à l’aide d’une logique de calcul. Vous suivrez la deuxième approche dans le labo **Créer des calculs DAX dans Power BI Desktop (partie 2)** , où vous créerez une mesure d’objectif qui retourne une valeur vide (BLANK) quand plusieurs vendeurs sont filtrés.*

### <a name="task-4-finish-up"></a>**Tâche 4 : Finalisation**

Dans cette tâche, vous terminez le labo.

1. Enregistrez le fichier Power BI Desktop.

2. Si vous êtes invité à appliquer des requêtes, cliquez sur **Appliquer plus tard**.

3. Si vous avez l’intention de démarrer le labo suivant, laissez Power BI Desktop ouvert.
