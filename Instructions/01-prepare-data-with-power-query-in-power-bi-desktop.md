---
lab:
  title: "Préparer des données dans Power\_BI Desktop"
  module: Module 2 - Get Data in Power BI
---

# <a name="prepare-data-in-power-bi-desktop"></a>**Préparer des données dans Power BI Desktop**

**La durée estimée pour effectuer ce tutoriel est de 45 minutes.**

In this lab you commence the development of a Power BI Desktop solution for the Adventure Works company. It involves connecting to source data, previewing the data, and using data preview techniques to understand the characteristics and quality of the source data.

Dans ce labo, vous allez découvrir comment :

- Ouvrir Power BI Desktop

- Définir les options de Power BI Desktop

- Se connecter à des données sources

- Obtenir un aperçu des données sources

- Utilisez des techniques d’aperçu des données pour mieux comprendre les données

### <a name="lab-story"></a>**Histoire du labo**

This lab is one of many in a series of labs that was designed as a complete story from data preparation to publication as reports and dashboards. You can complete the labs in any order. However, if you intend to work through multiple labs, for the first 10 labs, we suggest you do them in the following order:

1. **Préparer des données dans Power BI Desktop**

2. Charger des données dans Power BI Desktop

3. Modéliser les données dans Power BI Desktop

5. Créer des calculs DAX dans Power BI Desktop (partie 1)

6. Créer des calculs DAX dans Power BI Desktop (partie 2)

7. Concevoir un rapport dans Power BI Desktop, partie 1

8. Concevoir un rapport dans Power BI Desktop, partie 2

9. Créer un tableau de bord Power BI

10. Analyser les données dans Power BI Desktop

11. Appliquer la sécurité au niveau des lignes

## <a name="exercise-1-prepare-data"></a>**Exercice 1 : Préparer les données**

In this exercise you will create eight Power BI Desktop queries. Six queries will source data from SQL Server, and two from CSV files.

### <a name="task-1-save-the-power-bi-desktop-file"></a>**Tâche 1 : Enregistrer le fichier Power BI Desktop**

Dans cette tâche, vous allez d’abord enregistrer le fichier Power BI Desktop.

1. Pour ouvrir Power BI Desktop, accédez à la barre des tâches et cliquez sur le raccourci Microsoft Power BI Desktop.

    ![Image 2](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image1.png)

1. Pour fermer la fenêtre de démarrage, en haut à droite de cette fenêtre, sélectionnez **X**.

    ![Image 3](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image2.png)

1. Pour enregistrer le fichier, sélectionnez l’onglet de ruban **Fichier** pour ouvrir le mode Backstage.

1. Sélectionnez **Enregistrer**.

    ![Image 4](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image3.png)

1. Dans la fenêtre **Enregistrer sous**, accédez au dossier **D:\PL300\MySolution**.

1. Dans la zone **Nom du fichier**, entrez **Sales Analysis**.

    ![Image 14](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image4.png)

1. Cliquez sur **Enregistrer**.

    ![Image 17](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image5.png)

    Conseil : Vous pouvez aussi enregistrer le fichier en cliquant sur l’icône **Enregistrer** située en haut à gauche.

    ![Image 18](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image6.png)

### <a name="task-2-set-power-bi-desktop-options"></a>**Tâche 2 : Définir les options de Power BI Desktop**

Dans cette tâche, vous allez définir les options de Power BI Desktop.

1. Dans Power BI Desktop, cliquez sur l’onglet **Fichier** dans le ruban pour ouvrir le mode Backstage.

1. Sur la gauche, sélectionnez **Options et paramètres**, puis sélectionnez **Options**.

    ![Image 1](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image7.png)

1. Dans la fenêtre **Options**, à gauche, dans le groupe **Fichier actif**, sélectionnez **Chargement des données**.

    ![Image 5](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image8.png)

    Les paramètres de **Chargement des données** pour le fichier actif permettent de définir des options qui déterminent les comportements par défaut lors de la modélisation.

1. Dans le groupe **Relations**, désactivez les deux options activées.

    ![Image 7](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image9.png)

    While having these two options enabled can be helpful when developing a data model, you disabled them earlier to support the lab experience. When you create relationships in the <bpt id="p1">**</bpt>Load Data in Power BI Desktop<ept id="p1">**</ept> lab, you’ll learn why you are adding each one.

1. Cliquez sur **OK**.

    ![Image 9](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image10.png)

1. Enregistrez le fichier Power BI Desktop.

### <a name="task-3-get-data-from-sql-server"></a>**Tâche 3 : Obtenir des données de SQL Server**

Dans cette tâche, vous allez créer des requêtes basées sur des tables SQL Server.

1. Sous l’onglet **Accueil** du ruban, cliquez sur **SQL Server** dans le groupe **Données**.

    ![Image 19](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image11.png)

2. Dans la fenêtre **Base de données SQL Server**, dans la zone **Serveur**, entrez **localhost**.

    ![Image 21](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image12.png)

    Au cours de ce labo, vous lancez le développement d’une solution Power BI Desktop pour la société Adventure Works.

3. Cliquez sur **OK**.

    ![Image 22](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image13.png)

4. Dans la fenêtre **Navigateur**, à gauche, développez la base de données **AdventureWorksDW2020**.

    Elle implique la connexion aux données sources, l’affichage de l’aperçu des données et l’utilisation de techniques d’aperçu des données pour comprendre les caractéristiques et la qualité des données sources.

    ![Image 28](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image17.png)

5. Sélectionnez, mais ne cochez pas, la table **DimEmployee**.

    ![Image 29](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image18.png)

6. Notez qu’un aperçu des données de la table s’affiche dans le volet droit.

    Les données aperçues vous permettent de déterminer les colonnes et un échantillon de lignes.

7. Pour créer des requêtes, sélectionnez la case à cocher en regard des six tables suivantes :

    - DimEmployee

    - DimEmployeeSalesTerritory

    - DimProduct

    - DimReseller

    - DimSalesTerritory

    - FactResellerSales

8. Pour appliquer des transformations aux données des tables sélectionnées, cliquez sur **Transformer les données**.

    You won’t be transforming the data in this lab. The objectives of this lab focus on exploring and profiling the data in the <bpt id="p1">**</bpt>Power Query Editor<ept id="p1">**</ept> window.

    ![Image 30](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image19.png)

### <a name="task-4-preview-sql-server-queries"></a>**Tâche 4 : Afficher un aperçu des requêtes SQL Server**

In this task you will preview the data of the SQL Server queries. First, you will learn relevant information about the data. You will also use column quality, column distribution, and column profile tools to understand the data and to assess data quality.

1. Dans la fenêtre **Éditeur Power Query**, à gauche, notez la présence du volet **Requêtes**.

    ![Image 31](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image20.png)

    Le volet **Requêtes** contient une requête pour chaque table cochée.

2. Sélectionnez la première requête **DimEmployee**.

    ![Image 33](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image21.png)

    The <bpt id="p1">**</bpt>DimEmployee<ept id="p1">**</ept> table in the SQL Server database stores one row for each employee. A subset of the rows from this table represents the salespeople, which will be relevant to the model you’ll develop.

3. En bas à gauche, dans la barre d’état, notez les statistiques de la table : elle contient 33 colonnes et 296 lignes.

    ![Image 36](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image22.png)

4. Dans le volet Aperçu des données, faites défiler horizontalement pour passer en revue toutes les colonnes.

5. Notez que les cinq dernières colonnes contiennent des liens **Table** ou **Valeur**.

    These five columns represent relationships to other tables in the database. They can be used to join tables together. You’ll join tables in the <bpt id="p1">**</bpt>Load Data in Power BI Desktop<ept id="p1">**</ept> lab.

6. Pour évaluer la **qualité des colonnes**, cliquez sur l'onglet Affichage dans le ruban et activez l'option Qualité des colonnes dans le groupe **Aperçu des données**.

    ![Image 35](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image23.png)

    La qualité de la colonne vous permet de déterminer facilement le pourcentage de valeurs valides, en erreur ou vides trouvées dans les colonnes.

7. Pour la colonne **Position** (sixième colonne à partir de la droite), remarquez que 94 % des lignes sont vides (null).

    ![Image 38](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image24.png)

8. Pour évaluer la distribution des colonnes, cliquez sur l’onglet Affichage dans le ruban et activez l'option **Distribution des colonnes** dans le groupe **Aperçu des données**.

    ![Image 40](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image25.png)

9. Examinez à nouveau la colonne **Position** et notez qu’il y a quatre valeurs distinctes et une valeur unique.

10. Passez en revue la distribution de la colonne pour la première colonne **EmployeeKey** : il y a 296 valeurs distinctes et 296 valeurs uniques.

    ![Image 43](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image26.png)

    When the distinct and unique counts are the same, it means the column contains unique values. When modeling, it’s important that some model tables have unique columns. These unique columns can be used to create one-to-many relationships, which you will do in the <bpt id="p1">**</bpt>Model Data in Power BI Desktop, Part 1<ept id="p1">**</ept> lab.

11. Dans le volet **Requêtes**, sélectionnez la requête **DimEmployeeSalesTerritory**.

    ![Image 44](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image27.png)

    The <bpt id="p1">**</bpt>DimEmployeeSalesTerritory<ept id="p1">**</ept> table stores one row for each employee and the sales territory regions they manage. The table supports relating many regions to a single employee. Some employees manage one, two, or possibly more regions. When you model this data, you’ll need to define a many-to-many relationship, which you’ll do in the <bpt id="p1">**</bpt>Model Data in Power BI Desktop, Part 2<ept id="p1">**</ept> lab.

12. Dans le volet **Requêtes**, sélectionnez la requête **DimProduct**.

    ![Image 46](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image28.png)

    La table **DimProduct** contient une ligne par produit vendu par l’entreprise.

13. Faites défiler horizontalement pour voir les dernières colonnes.

14. Notez la colonne **DimProductSubcategory**.

    Quand vous ajouterez des transformations à cette requête dans le labo **Charger des données dans Power BI Desktop**, vous utiliserez la colonne **DimProductSubcategory** pour joindre les tables.

15. Dans le volet **Requêtes**, sélectionnez la requête **DimReseller**.

    ![Image 49](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image29.png)

    The <bpt id="p1">**</bpt>DimReseller<ept id="p1">**</ept> table contains one row per reseller. Resellers sell, distribute, or value add to the Adventure Works products.

16. Pour visualiser les valeurs des colonnes, sous l’onglet du ruban **Afficher**, à l’intérieur du groupe **Aperçu des données**, cochez **Profil de colonne**.

    ![Image 41](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image30.png)

17. Sélectionnez l’en-tête de colonne **BusinessType**.

18. Notez qu’un nouveau volet s’ouvre sous le volet Aperçu des données.

19. Passez en revue les statistiques de colonne et la distribution des valeurs dans le volet aperçu des données.

20. Notez le problème de qualité des données : il existe deux étiquettes pour l’entrepôt (**Warehouse** et **Ware House**, cette dernière étant mal orthographiée).

    ![Image 51](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image31.png)

21. Placez le curseur sur la barre **Ware House** ; notez qu’il y a cinq lignes avec cette valeur.

    Vous appliquerez une transformation pour réétiqueter ces cinq lignes dans le labo **Charger des données dans Power BI Desktop**.

22. Dans le volet **Requêtes**, sélectionnez la requête **DimSalesTerritory**.

    ![Image 52](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image32.png)

    The <bpt id="p1">**</bpt>DimSalesTerritory<ept id="p1">**</ept> table contains one row per sales region, including <bpt id="p2">**</bpt>Corporate HQ<ept id="p2">**</ept> (headquarters). Regions are assigned to a country, and countries are assigned to groups. In the <bpt id="p1">**</bpt>Model Data in Power BI Desktop, Part 1<ept id="p1">**</ept> lab, you’ll create a hierarchy to support analysis at region, country, or group level.

23. Dans le volet **Requêtes**, sélectionnez la requête **FactResellerSales**.

    ![Image 54](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image33.png)

    La table **FactResellerSales** contient une ligne par ligne de commande client ; une commande client contient une ou plusieurs lignes.

24. Examinez la qualité de la colonne pour la colonne **TotalProductCost** ; notez que 8 % des lignes sont vides.

    ![Image 63](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image34.png)

    Ce labo est l’un des nombreux labos d’une série qui a été conçue comme une histoire complète allant de la préparation des données jusqu’à leur publication sous forme de rapports et de tableaux de bord.

### <a name="task-5-get-data-from-a-csv-file"></a>**Tâche 5 : Obtenir des données d’un fichier CSV**

Dans cette tâche, vous allez créer une requête basée sur un fichier CSV.

1. Pour ajouter une nouvelle requête, dans la fenêtre **Éditeur Power Query**, sous l’onglet du ruban **Accueil**, dans le groupe **Nouvelle requête**, cliquez sur la flèche vers le bas **Nouvelle source**, puis sélectionnez **Texte/CSV**.

    ![Image 70](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image35.png)

2. Dans la fenêtre **Ouvrir**, accédez au dossier **D:\PL300\Resources**, puis sélectionnez le fichier **ResellerSalesTargets.csv**.

3. Cliquez sur **Ouvrir**.

4. Dans la fenêtre **ResellerSalesTargets.csv**, examinez l’aperçu des données.

5. Cliquez sur **OK**.

    ![Image 71](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image36.png)

  
‎ 

6. Dans le volet **Requêtes**, notez l’ajout de la requête **ResellerSalesTargets**.

    ![Image 72](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image37.png)

    Vous pouvez effectuer ces labos dans l’ordre de votre choix.

7. Notez qu’aucune colonne ne contient de valeurs vides.

    Quand il n’y a pas d’objectif de ventes mensuel, un caractère de trait d’union est stocké à la place.

8. Passez en revue les icônes dans chaque en-tête de colonne, à gauche du nom de la colonne.

    ![Image 74](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image38.png)

    Toutefois, si vous comptez faire plusieurs labos, pour les dix premiers d’entre eux, nous vous suggérons de suivre cet ordre :

    Dans le labo **Charger des données dans Power BI Desktop**, vous appliquerez de multiples transformations pour obtenir un résultat mis en forme différemment, composé de ces trois colonnes uniquement : **Date**, **EmployeeKey** et **TargetAmount**.

### <a name="task-6-get-additional-data-from-a-csv-file"></a>**Tâche 6 : Obtenir des données supplémentaires d’un fichier CSV**

Dans cette tâche, vous allez créer une requête supplémentaire basée sur un autre fichier CSV.

1. Effectuez les étapes de la tâche précédente pour créer une requête basée sur le fichier **D:\PL300\Resources\ColorFormats.csv**.

    ![Image 75](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image39.png)

    The <bpt id="p1">**</bpt>ColorFormats<ept id="p1">**</ept> CSV file contains one row per product color. Each row records the HEX codes to format background and font colors. You’ll integrate this data with the <bpt id="p1">**</bpt>DimProduct<ept id="p1">**</ept> query data in the <bpt id="p2">**</bpt>Load Data in Power BI Desktop<ept id="p2">**</ept> lab.

### <a name="task-7-finish-up"></a>**Tâche 7 : Terminer**

Dans cette tâche, vous terminez le labo.

1. Sous l’onglet du ruban **Afficher**, dans le groupe **Aperçu des données**, décochez les trois options d’aperçu des données précédemment activées dans ce labo :

    - Qualité de la colonne

    - Distribution des colonnes

    - Profil de colonne

    ![Image 76](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image40.png)

2. Pour enregistrer le fichier Power BI Desktop, dans la fenêtre **Éditeur Power Query**, dans la vu en mode Backstage **Fichier**, sélectionnez **Enregistrer**.

    ![Image 77](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image41.png)

3. Quand vous êtes invité à appliquer les requêtes, cliquez sur **Appliquer plus tard**.

    ![Image 86](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image42.png)

    Applying the queries will load their data to the data model. You’re not ready to do that, as there are many transformations that must be applied first.

4. Si vous avez l’intention de démarrer le labo suivant, laissez Power BI Desktop ouvert.

    Dans le labo **Charger des données dans Power BI Desktop**, vous appliquerez différentes transformations aux requêtes, puis vous appliquerez les requêtes pour les charger dans le modèle de données.
