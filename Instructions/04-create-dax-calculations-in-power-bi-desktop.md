---
lab:
  title: Créer des calculs DAX dans Power BI Desktop (partie 1)
  module: Module 5 - Create Model Calculations using DAX in Power BI
ms.openlocfilehash: 743fdd6a85236a40008fcdb3b466c61c617a55fb
ms.sourcegitcommit: 9ea1e7e21b9b3c718030c94b1693d153a2010ec7
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/07/2022
ms.locfileid: "147015336"
---
# <a name="create-dax-calculations-in-power-bi-desktop-part-1"></a>**Créer des calculs DAX dans Power BI Desktop (partie 1)**

**La durée estimée de ce labo est de 45 minutes.**

Dans ce labo, vous allez créer des tables calculées, des colonnes calculées et des mesures simples à l’aide de DAX (Data Analysis Expressions).

Dans ce labo, vous allez découvrir comment :

- Créer des tables calculées

- Créer des colonnes calculées

- Créer des mesures

### <a name="lab-story"></a>**Histoire du labo**

Ce labo est l’un des nombreux labos d’une série qui a été conçue comme une histoire complète allant de la préparation des données jusqu’à leur publication sous forme de rapports et de tableaux de bord. Vous pouvez effectuer ces labos dans l’ordre de votre choix. Toutefois, si vous comptez suivre plusieurs labos, pour les dix premiersd’entre eux, nous vous suggérons de suivre cet ordre :

1. Préparer des données dans Power BI Desktop

2. Charger des données dans Power BI Desktop

3. Modéliser les données dans Power BI Desktop

5. **Créer des calculs DAX dans Power BI Desktop (partie 1)**

6. Créer des calculs DAX dans Power BI Desktop (partie 2)

7. Concevoir un rapport dans Power BI Desktop, partie 1

8. Concevoir un rapport dans Power BI Desktop, partie 2

9. Créer un tableau de bord Power BI

10. Analyser les données dans Power BI Desktop

11. Appliquer la sécurité au niveau des lignes

## <a name="exercise-1-create-calculated-tables"></a>**Exercice 1 : Créer des tables calculées**

Dans cet exercice, vous allez créer deux tables calculées. La première est la table **Salesperson** (Vendeur), qui permettra d’établir une relation directe avec la table **Sales** (Ventes). La seconde est la table **Date**.

### <a name="task-1-get-started"></a>**Tâche 1 : Démarrer**

Dans cette tâche, vous configurez l’environnement pour le labo.

*Important : Si vous venez d’effectuer le labo précédent (et que vous l’avez entièrement terminé), ignorez cette tâche et passez directement à la tâche suivante.*

1. Pour ouvrir Power BI Desktop, accédez à la barre des tâches et cliquez sur le raccourci Microsoft Power BI Desktop.

    ![Image 50](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image1.png)

1. Pour fermer la fenêtre de démarrage, en haut à gauche de cette fenêtre, sélectionnez **X**.

    ![Image 49](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image2.png)

1. Pour ouvrir le fichier de démarrage de Power BI Desktop, sélectionnez **Fichier** dans le ruban afin de passer en mode Backstage.

1. Sélectionnez **Ouvrir un rapport**.

    ![Image 48](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image3.png)

1. Cliquez sur **Parcourir les rapports**.

    ![Image 47](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image4.png)

1. Dans la fenêtre **Ouvrir**, accédez au dossier **D:\PL300\Labs\04-create-dax-calculations-in-power-bi-desktop\Starter**.

1. Sélectionnez le fichier **Sales Analysis** (Analyse des ventes).

1. Cliquez sur **Ouvrir**.

    ![Image 35](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image5.png)

1. Fermez toutes les fenêtres d’information qui se sont éventuellement ouvertes.

1. Pour créer une copie du fichier, sélectionnez l’onglet de ruban **Fichier** afin de passer en mode Backstage.

1. Sélectionnez **Enregistrer sous**.

    ![Image 34](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image6.png)

1. Si vous êtes invité à appliquer les modifications, cliquez sur **Appliquer**.

    ![Image 25](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image7.png)

1. Dans la fenêtre **Enregistrer sous**, accédez au dossier **D:\PL300\MySolution**.

1. Cliquez sur **Enregistrer**.

    ![Image 13](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image8.png)

### <a name="task-2-create-the-salesperson-table"></a>**Tâche 2 : Créer la table Salesperson (Vendeur)**

Au cours de cette tâche, vous allez créer la table **Salesperson** (Vendeur), en relation directe avec **Sales** (Ventes).

1. Dans l’affichage Rapport de Power BI Desktop, cliquez sur **Nouvelle table** à l’intérieur du groupe **Calculs** dans le ruban **Modélisation**.

    ![Image 1](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image9.png)

2. Dans la barre de formule (qui s’ouvre directement sous le ruban lors de la création ou de la modification de calculs), tapez **Salesperson =**, appuyez sur **Maj+Entrée**, tapez **'Salesperson (Performance)'**, puis appuyez sur **Entrée**.

    ![Image 4](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image10.png)

    *Par souci pratique, toutes les définitions DAX de ce labo peuvent être copiées à partir du fichier **D:\PL300\Labs\04-create-dax-calculations-in-power-bi-desktop\Assets\Snippets.txt**.*

    *Pour créer une table calculée, commencez par entrer son nom, suivi du symbole égal (=), puis d’une formule DAX qui retourne une table. Notez que le nom de la table ne doit pas être déjà utilisé dans le modèle de données.*

    *La barre de formule accepte la saisie d’une formule DAX valide. Elle comprend des fonctionnalités telles que la saisie semi-automatique, IntelliSense et le code de couleurs, qui permettent d’entrer rapidement et correctement la formule.*

    *Cette définition de table crée une copie de la table **Salesperson (Performance)** (Vendeur [Performance]). Elle copie uniquement les données, et non les propriétés (visibilité, mise en forme, etc.).*

    *Conseil : Il est recommandé d’entrer un « espace blanc » (c’est-à-dire des retours chariot et des tabulations) pour mettre en forme les formules dans un format intuitif et facile à lire, en particulier si elles sont longues et complexes. Pour entrer un retour chariot, appuyez sur **Maj+Entrée**. L’« espace blanc » est facultatif.*

3. Comme vous pouvez le constater dans le volet **Champs**, l’icône de table apparaît dans une nuance de bleu (indiquant une table calculée).

    ![Image 10](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image11.png)

    *Les tables calculées sont définies à l’aide d’une formule DAX qui retourne une table. Il est important de comprendre que les tables calculées augmentent la taille du modèle de données, car elles matérialisent et stockent des valeurs. Elles sont recalculées chaque fois que les dépendances de la formule sont actualisées, comme ce sera le cas dans ce modèle de données lorsque de nouvelles valeurs de date (ultérieures) seront chargées dans les tables.*

    *Contrairement aux tables provenant de Power Query, les tables calculées ne permettent pas de charger des données à partir de sources externes. Elles ne peuvent transformer les données que sur la base de ce qui a déjà été chargé dans le modèle de données.*

4. Basculez vers l’affichage Modèle.

5. Comme vous pouvez le constater, la table **Salesperson** (Vendeur) est disponible (attention, elle peut être masquée : faites défiler l’affichage horizontalement pour la trouver).

6. Créez une relation entre les colonnes **Salesperson \| EmployeeKey** et **Sales \| EmployeeKey**.

7. Cliquez avec le bouton droit sur la relation inactive entre les tables **Salesperson (Performance)** (Vendeur (Performance)) et **Sales** (Ventes), puis sélectionnez **Supprimer**.

    ![Image 2](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image12.png)

8. Lorsqu’il vous est demandé de confirmer la suppression, cliquez sur **OK**.

    ![Image 3](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image13.png)

9. Dans la table **Salesperson**, sélectionnez les colonnes suivantes, puis masquez-les (définissez la propriété **Is Hidden** sur **Oui**) :

    - EmployeeID (IDEmployé)

    - EmployeeKey (CléEmployé)

    - UPN

10. Dans le diagramme du modèle, sélectionnez la table **Salesperson** (Vendeur).

11. Dans la zone **Description** du volet **Propriétés**, entrez : **Salesperson related to Sales** (Vendeur lié à Ventes)

    *Pour rappel, les descriptions apparaissent sous forme d’info-bulles dans le volet **Champs** lorsque l’utilisateur place le curseur sur une table ou un champ.*

12. Pour la table **Salesperson (Performance)**, définissez la description **Salesperson related to region(s)**

    *Le modèle de données offre désormais deux possibilités pour l’analyse des vendeurs. La table **Salesperson** permet d’analyser les ventes effectuées par un vendeur, tandis que le tableau **Salesperson (Performance)** permet d’analyser les ventes effectuées dans la ou les régions de vente affectées au vendeur.*

### <a name="task-3-create-the-date-table"></a>**Tâche 3 : Créer la table Date**

Dans cette tâche, vous allez créer la table **Date**.

1. Basculez vers l’affichage Données.

    ![Image 29](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image14.png)

2. Dans le groupe **Calculs** de l’onglet de ruban **Accueil**, cliquez sur **Nouvelle table**.

    ![Image 5](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image15.png)

3. Dans la barre de formule, entrez les éléments suivants :


    **DAX**


    ```
    Date =  
    CALENDARAUTO(6)
    ```


    ![Image 6](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image16.png)

    
    *La fonction CALENDARAUTO() retourne une table à une colonne composée de valeurs de date. Le comportement « automatique » consiste à analyser toutes les colonnes de date du modèle de données pour trouver les valeurs de date les plus anciennes et les plus récentes stockées dans le modèle de données. Une ligne est ensuite créée pour chaque date de cette plage, en étendant la plage dans les deux sens pour que les années de données stockées soient complètes.*

    *Cette fonction accepte un seul argument facultatif, à savoir le dernier numéro de mois d’une année. Quand elle n’est pas précisée, la valeur est 12, c’est-à-dire que décembre est considéré comme le dernier mois de l’année. Dans le cas présent, on entre 6 pour indiquer que juin est le dernier mois de l’année.*

4. La colonne de valeurs de date apparaît.

    ![Image 7](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image17.png)

    *Les dates affichées sont mises en forme suivant les paramètres régionaux États-Unis (soit mm/jj/aaaa).*

5. Dans la barre d’état en bas à gauche, les statistiques de la table confirment que 1 826 lignes de données ont été générées, ce qui représente les données de cinq années complètes.

    ![Image 9](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image18.png)

### <a name="task-4-create-calculated-columns"></a>**Tâche 4 :** **Créer des colonnes calculées**

Dans cette tâche, vous allez ajouter des colonnes supplémentaires pour permettre le filtrage et le regroupement selon différentes périodes. Vous allez également créer une colonne calculée qui contrôlera l’ordre de tri des autres colonnes.

*Par souci pratique, toutes les définitions DAX de ce labo peuvent être copiées à partir du fichier **D:\PL300\Labs\04-create-dax-calculations-in-power-bi-desktop\Assets\Snippets.txt**.*

1. Dans le groupe **Calculs** du ruban contextuel **Outils de table**, cliquez sur **Nouvelle colonne**.

    ![Image 11](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image19.png)

2. Dans la barre de formule, tapez les éléments suivants (ou copiez à partir du fichier d’extraits de code), puis appuyez sur **Entrée** :


    **DAX**


    ```
    Year =
    "FY" & YEAR('Date'[Date]) + IF(MONTH('Date'[Date]) > 6, 1)
    ```


    *Pour créer une colonne calculée, commencez par entrer son nom, suivi du symbole égal (=), puis d’une formule DAX qui retourne en résultat une seule valeur. Le nom de la colonne ne doit pas être déjà présent dans la table.*

    *La formule utilise la valeur d’année de la date, en y ajoutant un si le mois est postérieur au mois de juin. C’est ainsi que sont calculés les exercices chez Adventure Works.*

3. Vérifiez que la nouvelle colonne a été ajoutée.

    ![Image 12](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image20.png)

4. Utilisez la définition des fichiers d’extraits de code afin de créer les deux colonnes calculées suivantes pour la table **Date** :

    - Quarter (Trimestre)

    - Month (Mois)

    ![Image 14](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image21.png)

5. Pour valider les calculs, basculez vers l’affichage Rapport.

6. Pour créer une page de rapport, cliquez sur l’icône plus en bas à gauche.

    ![Image 15](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image22.png)

7. Pour ajouter un visuel matrice à la nouvelle page de rapport, sélectionnez le type de visuel matrice dans le volet **Visualisations**.

    *Conseil : Vous pouvez pointer le curseur sur chaque icône pour voir une info-bulle décrivant le type de visuel.*

    ![Image 51](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image23.png)

8. Dans la table **Date** du volet **Champs**, faites glisser le champ **Year** (Année) dans la zone **Lignes**.

    ![Image 17](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image24.png)

9. Faites glisser le champ **Month** (Mois) dans la zone **Lignes**, directement sous le champ **Year** (Année).

    ![Image 18](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image25.png)

10. En haut à droite du visuel de matrice (ou en bas, en fonction de l’emplacement du visuel), cliquez sur l’icône de flèche double fourchée (qui développera toutes les années vers le bas d’un niveau).

    ![Image 19](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image26.png)

11. Comme vous pouvez le constater, les années se développent en mois, qui sont triés par ordre alphabétique plutôt que par ordre chronologique.

    ![Image 20](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image27.png)

    *Par défaut, les valeurs de texte sont triées par ordre alphabétique, les nombres du plus petit au plus grand et les dates de la plus ancienne à la plus récente.*

12. Pour personnaliser l’ordre de tri du champ **Month** (Mois), basculez vers l’affichage Données.

13. Ajoutez la colonne **MonthKey** (CléMois) à la table **Date**.


    **DAX**


    ```
    MonthKey =
    (YEAR('Date'[Date]) * 100) + MONTH('Date'[Date])
    ```


    *Cette formule calcule une valeur numérique pour chaque combinaison année/mois.*

14. Dans l’affichage Données, vérifiez que la nouvelle colonne contient des valeurs numériques (par exemple, 201707 pour juillet 2017).

    ![Image 21](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image28.png)

15. Revenez dans la vue Rapport.

16. Dans le volet **Champs**, vérifiez que le champ **Month** (Mois) est sélectionné (il a alors un arrière-plan gris foncé).

17. Dans le groupe **Trier** du ruban contextuel **Outils de colonne**, cliquez sur **Trier par colonne**, puis sélectionnez **MonthKey** (CléMois).

    ![Image 22](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image29.png)

18. Comme vous pouvez le constater dans le visuel matrice, les mois sont maintenant triés par ordre chronologique.

    ![Image 23](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image30.png)

### <a name="task-5-complete-the-date-table"></a>**Tâche 5 :** **Terminer la table Date**

Dans cette tâche, vous allez terminer la conception de la table **Date** en masquant une colonne et en créant une hiérarchie. Vous allez ensuite créer des relations avec les tables **Sales** (Ventes) et **Targets** (Objectifs).

1. Basculez vers l’affichage Modèle.

2. Dans la table **Date**, masquez la colonne **MonthKey** (définissez **Is Hidden** sur **Yes**).

3. Dans le volet **Champs** à droite, sélectionnez la table **Date**, cliquez avec le bouton droit sur la colonne **Année**, puis sélectionnez **Créer une hiérarchie**. 

4. Cliquez avec le bouton droit sur **Renommer** et remplacez le nom de la hiérarchie nouvellement créée par « Fiscal ». 
5. Ajoutez les deux champs restants suivants à la hiérarchie Fiscal en les sélectionnant dans le volet Champs, en cliquant avec le bouton droit et en sélectionnant **Ajouter à la hiérarchie** -> **Fiscal**.
    
    - Quarter (Trimestre)

    - Month (Mois)

    ![Image 24](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image31.png)

6. Créez les deux relations de modèle suivantes :

    - **Date \| Date** à **Sales \| OrderDate**

    - **Date \| Date** à **Targets \| TargetMonth**

7. Masquez les deux colonnes suivantes :

    - Sales \| OrderDate

    - Targets \| TargetMonth

### <a name="task-6-mark-the-date-table"></a>**Tâche 6 : Marquer la table Date**

Au cours de cette tâche, vous allez marquer la table **Date** comme table de dates.

1. Basculez vers l’affichage Rapport.

2. Dans le volet **Champs**, sélectionnez la table **Date** (et non le champ **Date**).

3. Dans le groupe **Calendriers** du ruban contextuel **Outils de table**, cliquez sur **Marquer comme table de dates**, puis sélectionnez **Marquer comme table de dates**.

    ![Image 8](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image32.png)

4. Dans la liste déroulante **Colonne de dates** de la fenêtre **Marquer comme table de dates**, sélectionnez **Date**.

    ![Image 37](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image33.png)

5. Cliquez sur **OK**.

    ![Image 26](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image34.png)

6. Enregistrez le fichier Power BI Desktop.

    *Power BI Desktop comprend maintenant que cette table définit la date (temps). C’est important avec des calculs Time Intelligence. Vous utiliserez les calculs Time Intelligence dans le labo **Créer des calculs DAX dans Power BI Desktop (partie 2)** .*

    *Cette approche de la conception d’une table de dates est pertinente si votre source de données n’en comporte pas. Si vous avez un entrepôt de données, il est préférable de charger les données de date à partir de sa table de dimension de dates plutôt que de redéfinir la logique de date dans votre modèle de données.*

## <a name="exercise-2-create-measures"></a>**Exercice 2 : Créer des mesures**

Dans cet exercice, vous allez créer et mettre en forme plusieurs mesures.

### <a name="task-1-create-simple-measures"></a>**Tâche 1 : Créer des mesures simples**

Dans cette tâche, vous allez créer des mesures simples. Les mesures simples agrègent des valeurs dans une seule colonne ou comptent des lignes d’une table.

1. Dans l’affichage Rapport, dans le volet **Champs** de la **Page 2**, faites glisser le champ **Sales \| Unit Price** (Ventes | Prix unitaire) dans le visuel matrice.

    *Les labos utilisent une notation abrégée pour référencer un champ. Voici le résultat : **Sales \| Unit Price**. Dans cet exemple, **Sales** est le nom de la table et **Unit Price** correspond au nom du champ.*

    ![Image 27](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image35.png)

    *Dans le labo **Modéliser les données dans Power BI Desktop (partie 2)** , vous définissez la colonne **Unit Price** pour afficher une synthèse par **moyenne**. Le résultat affiché dans le visuel matrice est le prix unitaire moyen mensuel (qui correspond à la somme des valeurs de prix unitaire divisée par le nombre de prix unitaires).*

2. Comme vous pouvez constater dans le volet Champs du visuel (situé sous le volet **Visualisations**), **Unit Price** figure dans la zone **Valeurs**.

    ![Image 28](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image36.png)

3. Cliquez sur la flèche vers le bas de **Unit Price** (Prix unitaire), puis examinez les options de menu disponibles.

    ![Image 30](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image37.png)

    *Les colonnes numériques visibles permettent aux auteurs de déterminer au moment de la conception pour décider le mode de synthèse des valeurs de colonne (le cas échéant). Cela peut se révéler non pertinent. Toutefois, certains modélisateurs de données n’aiment pas s’en remettre au hasard et choisissent de masquer ces colonnes pour exposer à la place la logique d’agrégation définie par les mesures. C’est l’approche que vous allez maintenant appliquer dans ce labo.*

4. Pour créer une mesure, cliquez avec le bouton droit sur le tableau **Sales** (Ventes) dans le volet **Champs**, puis sélectionnez **Nouvelle mesure**.

    ![Image 31](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image38.png)

5. Dans la barre de formule, ajoutez la définition de mesure suivante :


    **DAX**


    ```
    Avg Price =  
    ‎AVERAGE(Sales[Unit Price])
    ```


6. Ajoutez ensuite la mesure **Avg Price** au visuel matrice.

7. Comme vous pouvez le constater, elle produit le même résultat que la colonne **Unit Price** (Prix unitaire) (avec une mise en forme différente toutefois).

8. Dans la zone **Valeurs**, ouvrez le menu contextuel du champ **Avg Price** (Prix moyen). Comme vous pouvez le constater, il n’est pas possible de modifier la technique d’agrégation.

    ![Image 32](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image39.png)

    *Il n’est pas possible de modifier le comportement d’agrégation d’une mesure.*

9. Utilisez la définition des fichiers d’extraits de code afin de créer les cinq mesures suivantes pour la table **Sales** (Ventes) :

    - Median Price (Prix médian)

    - Min Price (Prix minimal)

    - Max Price (Prix maximal)

    - Orders (Commandes)

    - Order Lines (Lignes de commande)

    *La fonction DISTINCTCOUNT() utilisée dans la mesure **Orders** (Commandes) ne compte les commandes qu’une seule fois (en ignorant les doublons). La fonction COUNTROWS() utilisée dans la mesure **Order Lines** (Lignes de commande) s’applique à une table.*

    *Dans le cas présent, le nombre de commandes est calculé en comptant les valeurs distinctes de la colonne **SalesOrderNumber**, tandis que le nombre de lignes de commande correspond simplement au nombre de lignes de la table (chaque ligne représentant une ligne de commande).*

10. Basculez vers l’affichage Modèle, puis sélectionnez les quatre mesures de prix : **Avg Price** (Prix moyen), **Max Price** (Prix maximal), **Median Price** (Prix médian) et **Min Price** (Prix minimal).

11. Pour la sélection multiple de mesures, configurez les critères suivants :

    - Format à deux décimales

    - Dossier d’affichage nommé **Pricing** (Tarifs)

    ![Image 33](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image40.png)

12. Masquez la colonne **Unit Pricing** (Prix unitaire).

    *La colonne **Unit Price** (Prix unitaire) n’est plus accessible aux auteurs de rapports. Ils doivent utiliser la mesure de tarification que vous avez ajoutée au modèle. Cette approche de conception permet d’éviter que les auteurs de rapports n’agrègent à tort les prix, par exemple en les additionnant.*

13. Sélectionnez les mesures **Order Lines** (Lignes de commandes) et **Orders** (Commandes) et configurez les critères suivants :

    - Format avec séparateur de milliers

    - Dossier d’affichage nommé **Counts** (Volumes)

    ![Image 36](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image41.png)

14. Dans l’affichage Rapport, cliquez sur **X** pour supprimer le champ **Unit Price** (Prix unitaire) dans la zone **Valeurs** du visuel matrice.

    ![Image 38](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image42.png)

15. Augmentez la taille du visuel matrice de façon à ce qu’il remplisse la largeur et la hauteur de la page.

16. Ajoutez les cinq mesures suivantes au visuel matrice :

    - Median Price (Prix médian)

    - Min Price (Prix minimal)

    - Max Price (Prix maximal)

    - Orders (Commandes)

    - Order Lines (Lignes de commande)

17. Vérifiez que les résultats semblent cohérents et qu’ils sont correctement mis en forme.

    ![Image 39](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image43.png)

### <a name="task-2-create-additional-measures"></a>**Tâche 2 : Créer des mesures supplémentaires**

Dans cette tâche, vous allez créer des mesures supplémentaires qui utilisent des formules plus complexes.

1. Dans l’affichage Rapport, sélectionnez **Page 1**.

    ![Image 40](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image44.png)

2. Examinez le visuel table, et notamment le total de la colonne **Target** (Objectif).

    ![Image 41](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image45.png)

    

3. Sélectionnez le visuel table et, dans le volet **Visualisations**, supprimez le champ **Target**.

    ![Image 42](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image46.png)

4. Renommez la colonne **Targets \| Target** en **Targets \| TargetAmount**.

    *Conseil : Il existe plusieurs façons de renommer la colonne dans l’affichage Rapport : Dans le volet **Champs**, vous pouvez soit cliquer avec le bouton droit sur la colonne et sélectionner **Renommer**, soit double-cliquer sur la colonne, soit appuyer sur **F2**.*

    *Vous allez créer une mesure nommée **Target** (Objectif). Il n’est pas possible d’avoir une colonne et une mesure du même nom dans la même table.*

5. Créez la mesure suivante sur la table **Targets** (Objectifs) :


    **DAX**


    ```
    Target =

    IF(

    HASONEVALUE('Salesperson (Performance)'[Salesperson]),

    SUM(Targets[TargetAmount])

    )
    ```


    *La fonction HASONEVALUE() teste si une valeur unique est filtrée dans la colonne **Salesperson**. Si c’est le cas, l’expression retourne la somme des objectifs chiffrés (pour ce vendeur en particulier). Sinon, elle retourne la valeur vide (BLANK).*

6. Mettez en forme la mesure **Target** (Objectif) sans décimale.

    *Conseil : Vous pouvez utiliser le ruban contextuel **Outils de mesure**.*

7. Masquez la colonne **TargetAmount** (ObjectifChiffré).

    *Conseil : Vous pouvez cliquer avec le bouton droit sur la colonne dans le volet **Champs**, puis sélectionner **Masquer**.*

8. Ajoutez la mesure **Target** (Objectif) au visuel table.

9. Comme vous pouvez le constater, le total de la colonne **Target** (Objectif) est maintenant vide.

    ![Image 43](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image47.png)

10. Utilisez la définition des fichiers d’extraits de code afin de créer les deux mesures suivantes pour la table **Targets** (Objectifs) :

    - Variance

    - Variance Margin (Marge de variance)

11. Mettez en forme la mesure **Variance** sans décimale.

12. Paramétrez la mesure **Variance Margin** (Marge de variance) sous forme de pourcentage à deux décimales.

13. Ajoutez les mesures **Variance** et **Variance Margin** (Marge de variance) au visuel table.

14. Redimensionnez le visuel table pour afficher la totalité des colonnes et des lignes.

    ![Image 44](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image48.png)

    *S’il apparaît que tous les vendeurs n’atteignent pas les objectifs, n’oubliez pas que le visuel de la table n’est pas filtré sur une période de temps spécifique. Vous générerez des rapports des performances des ventes, filtrés selon une période choisie par l’utilisateur dans le labo **Concevoir un rapport dans Power BI Desktop (partie 1)** .*

15. Réduisez, puis développez et rouvrez le volet **Champs** en haut à droite.

    ![Image 45](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image49.png)

    *Le fait de réduire puis de rouvrir le volet permet de réinitialiser le contenu.*

16. Comme vous pouvez le constater, la table **Targets** (Objectifs) apparaît maintenant en haut de la liste.

    ![Image 46](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image50.png)

    *Les tables qui comportent uniquement des mesures visibles figurent automatiquement en haut de la liste.*

### <a name="task-3-finish-up"></a>**Tâche 3 : Terminer**

Dans cette tâche, vous terminez le labo.

1. Enregistrez le fichier Power BI Desktop.

2. Si vous avez l’intention de démarrer le labo suivant, laissez Power BI Desktop ouvert.

    *Vous améliorerez le modèle de données avec des calculs plus avancés en utilisant DAX dans le labo **Créer des calculs DAX dans Power BI Desktop (partie 2)** .*
