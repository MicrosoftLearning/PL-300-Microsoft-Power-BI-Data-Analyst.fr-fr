---
lab:
  title: "Obtenir des données dans Power\_BI"
  module: Get data in Power BI
---

# Obtenir des données dans Power BI

## Histoire du labo

Ce labo a pour but de vous présenter l’application Power BI Desktop, et de vous expliquer comment se connecter aux données et comment utiliser des techniques d’aperçu des données pour comprendre les caractéristiques et la qualité des données sources.

Dans ce labo, vous découvrez comment :

- Ouvrez Power BI Desktop.
- Se connecter à différentes sources de données.
- Affichez un aperçu des données sources avec Power Query.
- Utilisez les fonctionnalités de profilage des données dans Power Query.

**Ce labo devrait prendre environ 30 minutes.**

## Prise en main de Power BI Desktop

Pour effectuer cet exercice, ouvrez d’abord un navigateur web et entrez l’URL suivante pour télécharger le dossier zip :

`https://github.com/MicrosoftLearning/PL-300-Microsoft-Power-BI-Data-Analyst/raw/Main/Allfiles/Labs/01-get-data-in-power-bi/01-get-data.zip`

Extrayez le dossier dans celui de **C:\Users\Student\Downloads\01-load-data**.

Ouvrez le fichier **01-Starter-Sales Analysis.pbix**.

- Le fichier de démarrage a été spécialement configuré pour vous aider à suivre le labo. Les paramètres au niveau du rapport suivants ont été désactivés dans le fichier de démarrage :

  - Chargement des données > Importer des relations à partir de sources de données au premier chargement
  - Chargement des données > Détecter automatiquement les nouvelles relations une fois les données chargées

## Obtenir des données de SQL Server

Cette tâche vous apprend à vous connecter à une base de données SQL Server et à importer des tables, qui créent des requêtes dans Power Query.

1. Sous l’onglet de ruban **Accueil**, dans le groupe **Données**, sélectionnez **SQL Server**.

     ![Icône Obtenir des données à partir de SQL Server](Linked_image_Files/01-get-data-in-power-bi_image11.png)

1. Dans la fenêtre **Base de données SQL Server**, dans la zone **Serveur**, entrez **localhost** et laissez **Base de données** vide, puis sélectionnez **OK**.

    > ***Remarque** : Dans ce labo, vous allez vous connecter à la base de données SQL Server en utilisant **localhost**. Bien que cela convienne pour le laboratoire, cela n’est pas considéré comme une bonne pratique pour les solutions concrètes.*

1. Si vous y êtes invité, sélectionnez **Windows > Utiliser mes informations d’identification actuelles**, puis **Se connecter**.

1. Sélectionnez **OK** si vous recevez un avertissement indiquant qu’une connexion chiffrée ne peut pas être établie.

1. Dans le volet **Navigateur**, développez la base de données **AdventureWorksDW2020**.

    > ***Remarque** : la base de données **AdventureWorksDW2020** est basée sur l’exemple de base de données **AdventureWorksDW2017**. Elle a été modifiée pour prendre en charge les objectifs d’apprentissage des labos du cours.*

1. Sélectionnez la table **DimEmployee**, et notez la présence de l’aperçu des données de la table.

     ![Base de données AdventureWorksDW2020 avec DimEmployee mise en évidence](Linked_image_Files/01-get-data-in-power-bi_image18.png)

    > ***Remarque** : l’aperçu des données vous permet de voir les colonnes et un échantillon des lignes.*

1. Sélectionnez les tableaux suivants **en cochant les cases** en regard de leurs noms.

    - DimEmployee
    - DimEmployeeSalesTerritory
    - DimProduct
    - DimReseller
    - DimSalesTerritory
    - FactResellerSales

1. Effectuez cette tâche en cliquant sur **Transformer les données**, ce qui ouvre l’Éditeur Power Query. Gardez-le ouvert pour la tâche suivante.

Vous êtes maintenant connecté à six tables à partir d’une base de données SQL Server.

## Afficher un aperçu des données dans l’Éditeur Power Query

Cette tâche présente l’Éditeur Power Query, et vous permet de passer en revue et de profiler les données. Cela vous aide à déterminer comment nettoyer et transformer les données ultérieurement. Vous allez également passer en revue les tables de dimension préfixées de « Dim » et les tables de faits préfixées de « Fact ».

1. Dans la fenêtre **Éditeur Power Query**, à gauche, notez la présence du volet **Requêtes**. Le volet **Requêtes** contient une requête pour chaque table cochée.

     ![Liste des requêtes chargées](Linked_image_Files/01-get-data-in-power-bi_image20.png)

1. Sélectionnez la requête **DimEmployee**.

    > *La table **DimEmployee** de la base de données SQL Server stocke une ligne pour chaque employé. Un sous-ensemble des lignes de cette table représente les vendeurs, qui seront pertinents pour le modèle que vous développerez.*

1. En bas à gauche de la barre d’état, certaines statistiques de la table sont fournies : elle contient 33 colonnes et 296 lignes.

     ![33 colonnes, 296 lignes](Linked_image_Files/01-get-data-in-power-bi_image22.png)

1. Dans le volet Aperçu des données, faites défiler horizontalement pour passer en revue toutes les colonnes. Notez que les cinq dernières colonnes contiennent des liens **Table** ou **Valeur**.

    > *Ces cinq colonnes représentent les relations avec d’autres tables de la base de données. Elles peuvent être utilisées pour joindre des tables ensemble. Vous allez joindre ces tables plus tard dans le laboratoire **Charger les données transformées dans Power BI Desktop**.*

1. Pour évaluer la **qualité des colonnes**, cliquez sur l'onglet Affichage dans le ruban et activez l'option Qualité des colonnes dans le groupe **Aperçu des données**. La qualité de la colonne vous permet de déterminer facilement le pourcentage de valeurs valides, en erreur ou vides trouvées dans les colonnes.

     ![Sélection de la qualité de colonne dans le ruban](Linked_image_Files/01-get-data-in-power-bi_image23.png)

1. Notez que la colonne **Position** contient 94 % de lignes vides (null).

     ![Qualité de colonne montrant 94 % de lignes vides](Linked_image_Files/01-get-data-in-power-bi_image24.png)

1. Pour évaluer la distribution de la colonne, sous l’onglet du ruban **Afficher**, à l’intérieur du groupe **Aperçu des données**, cochez **Distribution des colonnes**.

1. Examinez à nouveau la colonne **Position** et notez qu’il y a quatre valeurs distinctes et une valeur unique.

1. Passez en revue la distribution de colonne pour la colonne **EmployeeKey** : il y a 296 valeurs distinctes et 296 valeurs uniques.

     ![Distribution de colonne montrant 296 valeurs distinctes et 296 valeurs uniques](Linked_image_Files/01-get-data-in-power-bi_image26.png)

    > ***Remarque** : quand les nombres de valeurs distinctes et uniques sont identiques, cela signifie que la colonne contient des valeurs uniques. Lors de la modélisation, il est important que certaines tables de modèle contiennent des colonnes uniques. Ces colonnes uniques peuvent être utilisées pour créer des relations un-à-plusieurs. C’est ce que vous ferez dans le labo **Modéliser les données dans Power BI Desktop***.

1. Dans le volet **Requêtes**, sélectionnez la requête **DimProduct**.

    > *La table **DimProduct** contient une ligne par produit vendu par l’entreprise.*

1. Dans le volet **Requêtes**, sélectionnez la requête **DimReseller**.

    > *La table **DimReseller** contient une ligne par revendeur. Les revendeurs vendent, distribuent ou ajoutent de la valeur aux produits Adventure Works.*

1. Pour visualiser les valeurs des colonnes, sous l’onglet du ruban **Afficher**, à l’intérieur du groupe **Aperçu des données**, cochez **Profil de colonne**.

1. Sélectionnez l’en-tête de colonne **BusinessType** et notez le nouveau volet sous le volet d’aperçu des données. Passez en revue les statistiques de colonne et la distribution des valeurs dans le volet aperçu des données.

    > *Notez le problème de qualité des données : il existe deux étiquettes pour l’entrepôt (**Warehouse** et **Ware House**, cette dernière étant mal orthographiée).*

     ![Distribution des valeurs pour la colonne BusinessType](Linked_image_Files/01-get-data-in-power-bi_image31.png)

1. Placez le curseur sur la barre **Ware House** ; notez qu’il y a cinq lignes avec cette valeur.

1. Dans le volet **Requêtes**, sélectionnez la requête **DimSalesTerritory**.  

    > *La table **DimSalesTerritory** contient une ligne par région de vente, y compris **Corporate HQ** (siège social de l’entreprise). Les régions sont affectées à un pays, et les pays sont affectés à des groupes. Dans le labo **Modéliser des données dans Power BI Desktop**, vous créerez une hiérarchie pour prendre en charge l’analyse au niveau de la région, du pays ou du groupe.*

1. Dans le volet **Requêtes**, sélectionnez la requête **FactResellerSales**.

    > *La table **FactResellerSales** contient une ligne par ligne de commande client ; une commande client contient une ou plusieurs lignes.*

1. Examinez la qualité de la colonne pour la colonne **TotalProductCost** ; notez que 8 % des lignes sont vides.

    > *Les valeurs manquantes de la colonne **TotalProductCost** sont un problème de qualité des données.*

## Obtenir des données d’un fichier CSV

Dans cette tâche, vous allez créer une requête basée sur des fichiers CSV.

1. Pour ajouter une nouvelle requête, dans la fenêtre **Éditeur Power Query**, sous l’onglet de ruban **Accueil**, dans le groupe **Nouvelle requête**, sélectionnez la flèche vers le bas **Nouvelle source**, puis sélectionnez **Texte/CSV**.

1. Accédez au dossier **Téléchargements > 01-get-data** que vous avez extrait précédemment et sélectionnez le fichier **ResellerSalesTargets.csv**. Sélectionnez **Ouvrir**.

1. Dans la fenêtre **ResellerSalesTargets.csv**, examinez l’aperçu des données. Sélectionnez **OK**.

1. Dans le volet **Requêtes**, notez l’ajout de la requête **ResellerSalesTargets**.

    > *Le fichier CSV **ResellerSalesTargets** contient une ligne par vendeur et par an. Chaque ligne enregistre 12 cibles de ventes mensuelles (exprimées en milliers). L’année commerciale de la société Adventure Works commence le 1er juillet.*

1. Notez qu’aucune colonne ne contient de valeurs vides.  Si une cible de ventes mensuelles est manquante, la colonne affiche un trait d’union à la place.

1. Passez en revue les icônes dans chaque en-tête de colonne, à gauche du nom de la colonne. Les icônes représentent le type de données de la colonne. **123** représente un nombre entier et **ABC** représente du texte.

     ![Type de données de colonne](Linked_image_Files/01-get-data-in-power-bi_image38.png)

1. Répétez les étapes pour créer une requête basée sur le fichier **ColorFormats.csv**.

    > *Le fichier CSV **ColorFormats** contient une ligne par couleur de produit. Chaque ligne enregistre les codes HEX pour mettre en forme les couleurs d’arrière-plan et de police.*

Vous devez maintenant avoir deux nouvelles requêtes, **ResellerSalesTargets** et **ColorFormats**.

 ![Liste des requêtes](Linked_image_Files/01-get-data-in-power-bi_image43.png)

## Labo terminé

Vous pouvez choisir d’enregistrer votre rapport Power BI, même s’il n’est pas nécessaire pour ce labo. Dans l’exercice suivant, vous allez utiliser un fichier de démarrage prédéfini.

1. Accédez au menu **« Fichier »** dans le coin supérieur gauche, puis sélectionnez **« Enregistrer sous ».** 
1. Sélectionnez **Parcourir cet appareil**.
1. Sélectionnez le dossier dans lequel vous souhaitez enregistrer le fichier et donnez-lui un nom descriptif. 
1. Sélectionnez le bouton **Enregistrer** pour enregistrer votre rapport en tant que fichier .pbix. 
1. Si une boîte de dialogue s’affiche pour vous inviter à appliquer des modifications de requête en attente, sélectionnez **Appliquer**.
1. Fermez Power BI Desktop.