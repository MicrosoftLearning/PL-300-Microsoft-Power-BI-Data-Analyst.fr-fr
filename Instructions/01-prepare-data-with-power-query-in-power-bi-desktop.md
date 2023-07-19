---
lab:
  title: Obtenir des données dans Power BI Desktop
  module: Get Data in Power BI
---

# Obtenir des données dans Power BI Desktop

## **Histoire du labo**

Ce labo a pour but de vous présenter l’application Power BI Desktop, et de vous expliquer comment se connecter aux données et comment utiliser des techniques d’aperçu des données pour comprendre les caractéristiques et la qualité des données sources. Les objectifs d’apprentissage sont les suivants :

- Ouvrir Power BI Desktop
- Se connecter à différentes sources de données
- Afficher un aperçu des données sources avec Power Query
- Utiliser les fonctionnalités de profilage des données dans Power Query

**Ce labo devrait prendre environ 30 minutes.**

## **Prise en main de Power BI Desktop**

Dans cette tâche, vous commencez par ouvrir un fichier Power BI (.pbix) de démarrage. Le fichier de démarrage ne contient aucune donnée, mais a été spécialement configuré pour vous aider à suivre le labo. Les paramètres au niveau du rapport suivants ont été désactivés dans le fichier de démarrage :

- Chargement des données > Importer des relations à partir de sources de données au premier chargement
- Chargement des données > Détecter automatiquement les nouvelles relations une fois les données chargées

*Remarque : Bien que l’activation de ces deux options puisse être utile lors du développement d’un modèle de données, vous les avez désactivées précédemment pour prendre en charge l’expérience du labo. Lorsque vous créerez des relations dans le labo **Charger des données dans Power BI Desktop**, vous découvrirez pourquoi vous ajoutez chacune d’elles.*

1. Ouvrez Power BI Desktop.

    ![Icône Power BI Desktop](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image1.png)

    *Conseil : Par défaut, la boîte de dialogue Prise en main s’ouvre par-dessus Power BI Desktop. Vous pouvez choisir de vous connecter, puis de fermer la fenêtre contextuelle.*

1. Pour ouvrir le fichier Power BI Desktop de démarrage, sélectionnez **Fichier > Ouvrir le rapport > Parcourir les rapports**.

1. Dans la fenêtre **Ouvrir**, accédez au dossier **D:\PL300\Labs\01-load-data-with-power-query-in-power-bi-desktop\Starter**.

1. Sélectionnez le fichier **Sales Analysis** (Analyse des ventes).

1. Enregistrez une copie du fichier avec **Enregistrer sous** dans le dossier **D:\PL300\MySolution**.

## **Obtenir des données de SQL Server**

Cette tâche vous apprend à vous connecter à une base de données SQL Server et à importer des tables, qui créent des requêtes dans Power Query.

1. Sous l’onglet de ruban **Accueil**, dans le groupe **Données**, sélectionnez **SQL Server**.

     ![Icône Obtenir des données à partir de SQL Server](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image11.png)

1. Dans la fenêtre **Base de données SQL Server**, dans la zone **Serveur**, entrez **localhost**, puis sélectionnez **OK**.

    *Remarque : Dans ce labo, vous allez vous connecter à la base de données SQL Server à l’aide de **localhost**, car les sources de données de passerelle ne peuvent pas résoudre **localhost**. Cette pratique n’est pas recommandée lors de la création de vos propres solutions.*

1. Si vous y êtes invité, dans la fenêtre **Base de données SQL Server**, sélectionnez **Utiliser mes informations d’identification actuelles**, puis **Se connecter**.

1. Dans la fenêtre **Navigateur**, à gauche, développez la base de données **AdventureWorksDW2020**.

    *Remarque : La base de données **AdventureWorksDW2020** est basée sur l’exemple de base de données **AdventureWorksDW2017**. Elle a été modifiée pour prendre en charge les objectifs d’apprentissage des labos de cours.*

1. Sélectionnez (mais ne cochez pas) la table **DimEmployee**.

     ![Base de données AdventureWorksDW2020 avec DimEmployee mise en évidence](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image18.png)

1. Notez qu’un aperçu des données de la table s’affiche dans le volet droit. L’aperçu des données vous permet de voir les colonnes et un échantillon de lignes.

1. Pour créer des requêtes, sélectionnez la case à cocher en regard des six tables suivantes :

    - DimEmployee
    - DimEmployeeSalesTerritory
    - DimProduct
    - DimReseller
    - DimSalesTerritory
    - FactResellerSales

1. Effectuez cette tâche en cliquant sur **Transformer les données**, ce qui ouvre l’Éditeur Power Query.
    1. *Ce labo est uniquement destiné à se connecter aux données et à les profiler, mais pas **à transformer les données**.*

## **Afficher un aperçu des données dans l’Éditeur Power Query**

Cette tâche présente l’Éditeur Power Query, et vous permet de passer en revue et de profiler les données. Cela vous aide à déterminer comment nettoyer et transformer les données ultérieurement.

1. Dans la fenêtre **Éditeur Power Query**, à gauche, notez la présence du volet **Requêtes**. Le volet **Requêtes** contient une requête pour chaque table cochée.

     ![Liste des requêtes chargées](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image20.png)

1. Sélectionnez la première requête **DimEmployee**.

    *La table **DimEmployee** de la base de données SQL Server stocke une ligne pour chaque employé. Un sous-ensemble des lignes de cette table représente les vendeurs, qui seront pertinents pour le modèle que vous développerez.*

1. En bas à gauche de la barre d’état, certaines statistiques de la table sont fournies : elle contient 33 colonnes et 296 lignes.

     ![33 colonnes, 296 lignes](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image22.png)

1. Dans le volet Aperçu des données, faites défiler horizontalement pour passer en revue toutes les colonnes. Notez que les cinq dernières colonnes contiennent des liens **Table** ou **Valeur**.

    *Ces cinq colonnes représentent des relations avec d’autres tables de la base de données. Elles peuvent être utilisées pour joindre des tables. Vous joindrez des tables dans le labo **Charger des données dans Power BI Desktop**.*

1. Pour évaluer la **qualité des colonnes**, cliquez sur l'onglet Affichage dans le ruban et activez l'option Qualité des colonnes dans le groupe **Aperçu des données**. La qualité de la colonne vous permet de déterminer facilement le pourcentage de valeurs valides, en erreur ou vides trouvées dans les colonnes.

     ![Sélection de la qualité de colonne dans le ruban](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image23.png)

1. Notez que la colonne **Position** contient 94 % de lignes vides (null).

     ![Qualité de colonne montrant 94 % de lignes vides](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image24.png)

1. Pour évaluer la distribution de la colonne, sous l’onglet du ruban **Afficher**, à l’intérieur du groupe **Aperçu des données**, cochez **Distribution des colonnes**.

1. Examinez à nouveau la colonne **Position** et notez qu’il y a quatre valeurs distinctes et une valeur unique.

1. Passez en revue la distribution de colonne pour la colonne **EmployeeKey** : il y a 296 valeurs distinctes et 296 valeurs uniques.

    *Lorsque les nombres distincts et uniques sont les mêmes, cela signifie que la colonne contient des valeurs uniques. Lors de la modélisation, il est important que certaines tables de modèles aient des colonnes uniques. Ces colonnes uniques peuvent être utilisées pour créer des relations un-à-plusieurs, ce que vous ferez dans le labo **Modéliser des données dans Power BI Desktop**.*

     ![Distribution de colonne montrant 296 valeurs distinctes et 296 valeurs uniques](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image26.png)

1. Dans le volet **Requêtes**, sélectionnez la requête **DimEmployeeSalesTerritory**.

    *La table **DimEmployeeSalesTerritory** stocke une ligne pour chaque employé et les régions du territoire de vente qu’il gère. La table prend en charge la relation de nombreuses régions à un seul employé. Certains employés gèrent une, deux ou peut-être plusieurs régions. Lorsque vous modélisez ces données, vous devez définir une relation plusieurs-à-plusieurs.*

1. Dans le volet **Requêtes**, sélectionnez la requête **DimProduct**. La table **DimProduct** contient une ligne par produit vendu par l’entreprise.

1. Faites défiler horizontalement pour voir les dernières colonnes. Notez la colonne **DimProductSubcategory**.

    *Quand vous ajouterez des transformations à cette requête dans le labo **Charger des données dans Power BI Desktop**, vous utiliserez la colonne **DimProductSubcategory** pour joindre les tables.*

1. Dans le volet **Requêtes**, sélectionnez la requête **DimReseller**.

    *La table **DimReseller** contient une ligne par revendeur. Les revendeurs vendent, distribuent ou ajoutent de la valeur aux produits Adventure Works.*

1. Pour visualiser les valeurs des colonnes, sous l’onglet du ruban **Afficher**, à l’intérieur du groupe **Aperçu des données**, cochez **Profil de colonne**.

1. Sélectionnez l’en-tête de colonne **BusinessType** et notez le nouveau volet sous le volet d’aperçu des données.

1. Passez en revue les statistiques de colonne et la distribution des valeurs dans le volet aperçu des données.

    *Notez le problème de qualité des données : il existe deux étiquettes pour l’entrepôt (**Warehouse** et **Ware House**, cette dernière étant mal orthographiée).*

     ![Distribution des valeurs pour la colonne BusinessType](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image31.png)

1. Placez le curseur sur la barre **Ware House** ; notez qu’il y a cinq lignes avec cette valeur.

    *Vous appliquerez une transformation pour réétiqueter ces cinq lignes dans le labo **Charger des données dans Power BI Desktop**.*

1. Dans le volet **Requêtes**, sélectionnez la requête **DimSalesTerritory**.  

    *La table **DimSalesTerritory** contient une ligne par région de vente, y compris **Corporate HQ** (siège social de l’entreprise). Les régions sont affectées à un pays, et les pays sont affectés à des groupes. Dans le labo **Modéliser des données dans Power BI Desktop**, vous créerez une hiérarchie pour prendre en charge l’analyse au niveau de la région, du pays ou du groupe.*

1. Dans le volet **Requêtes**, sélectionnez la requête **FactResellerSales**.

    *La table **FactResellerSales** contient une ligne par ligne de commande client ; une commande client contient une ou plusieurs lignes.*

1. Examinez la qualité de la colonne pour la colonne **TotalProductCost** ; notez que 8 % des lignes sont vides.

    *Des valeurs de colonne **TotalProductCost** manquantes constituent un problème de qualité des données. Pour le résoudre, dans le labo **Charger des données dans Power BI Desktop**, vous appliquerez des transformations afin de renseigner les valeurs manquantes en utilisant le coût standard du produit, qui est stocké dans la table **DimProduct** associée.*

## **Obtenir des données d’un fichier CSV**

Dans cette tâche, vous allez créer une requête basée sur des fichiers CSV.

1. Pour ajouter une nouvelle requête, dans la fenêtre **Éditeur Power Query**, sous l’onglet de ruban **Accueil**, dans le groupe **Nouvelle requête**, sélectionnez la flèche vers le bas **Nouvelle source**, puis sélectionnez **Texte/CSV**.

1. Dans la fenêtre **Ouvrir**, accédez au dossier **D:\PL300\Resources**, puis sélectionnez le fichier **ResellerSalesTargets.csv**. Sélectionnez **Ouvrir**.

1. Dans la fenêtre **ResellerSalesTargets.csv**, examinez l’aperçu des données. Sélectionnez **OK**.

1. Dans le volet **Requêtes**, notez l’ajout de la requête **ResellerSalesTargets**.

    *Le fichier CSV **ResellerSalesTargets** contient une ligne par vendeur et par an. Chaque ligne enregistre 12 cibles de ventes mensuelles (exprimées en milliers). L’année commerciale de la société Adventure Works commence le 1er juillet.*

1. Notez qu’aucune colonne ne contient de valeurs vides.  Quand il n’y a pas d’objectif de ventes mensuel, un caractère de trait d’union est stocké à la place.

1. Passez en revue les icônes dans chaque en-tête de colonne, à gauche du nom de la colonne. Les icônes représentent le type de données de la colonne. **123** représente un nombre entier et **ABC** représente du texte.

     ![Image 74](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image38.png)

1. Répétez les étapes pour créer une requête basée sur le fichier **D:\PL300\Resources\ColorFormats.csv**.

    *Le fichier CSV **ColorFormats** contient une ligne par couleur de produit. Chaque ligne enregistre les codes HEX pour mettre en forme les couleurs d’arrière-plan et de police.*

*Vous devez maintenant avoir deux nouvelles requêtes, **ResellerSalesTargets** et **ColorFormats**.*

 ![Liste des requêtes](Linked_image_Files/01-all-queries-loaded.png)

### **Terminer**

Dans cette tâche, vous allez terminer le labo.

1. Sous l’onglet du ruban **Afficher**, dans le groupe **Aperçu des données**, décochez les trois options d’aperçu des données précédemment activées dans ce labo :

    - Qualité de la colonne
    - Distribution des colonnes
    - Profil de colonne

     ![Image 76](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image40.png)

1. **Enregistrez** le fichier Power BI Desktop. Quand vous êtes invité à appliquer les modifications en attente, sélectionnez **Appliquer plus tard**.

    *Conseil : L’application des requêtes charge leurs données dans le modèle de données. Vous n’êtes pas prêt à le faire, car de nombreuses transformations doivent d’abord être appliquées.*
