---
lab:
  title: "Effectuer de l’analytique avancée dans Power\_BI"
  module: Perform Data Analysis in Power BI
---


# **Faire une analyse des données dans Power BI**

## **Histoire du labo**

Dans ce labo, vous allez créer le rapport **Sales Exploration** (Exploration des ventes).

Dans ce labo, vous allez découvrir comment :

- Créer des graphiques à nuages de points animés
- Utiliser un visuel pour établir des prévisions sur les valeurs

**Ce labo devrait prendre environ 30 minutes.**

## **Démarrer - Se connecter**

Au cours de cette tâche, vous allez configurer l’environnement nécessaire pour le labo en vous connectant à Power BI.

*Remarque : Si vous êtes déjà connecté à Power BI, passez à la tâche suivante.*

1. Pour ouvrir Microsoft Edge, dans la barre des tâches, sélectionnez le raccourci du programme Microsoft Edge.

     ![Image 12](Linked_image_Files/08-design-report-in-power-bi-desktop-enhanced_image1.png)

1. Dans la fenêtre du navigateur Microsoft Edge, accédez à **https://app.powerbi.com**.

    *Conseil : Vous pouvez également utiliser le favori Service Power BI dans la barre des favoris Microsoft Edge.*

1. Effectuez le processus de connexion avec vos informations d’identification organisationnelles (ou fournies). Si Microsoft Edge vous invite à rester connecté, sélectionnez **Oui**.

1. Dans la fenêtre du navigateur Microsoft Edge, dans le service Power BI, dans le volet **Navigation**, développez **Mon espace de travail**. Laissez la fenêtre du navigateur Microsoft Edge ouverte.

     ![Image 22](Linked_image_Files/07-my-workspace-new.png)

## **Démarrer - Créer un jeu de données**

Au cours de cette tâche, vous allez configurer l’environnement pour le labo en créant un jeu de données. *Si vous avez déjà publié le jeu de données, passez à la tâche suivante.*

1. Dans la fenêtre du navigateur Microsoft Edge, dans le service Power BI, accédez à **Mon espace de travail**.

1. Sélectionnez **Charger > Parcourir**.

1. Accédez au dossier **D:\PL300\Labs\08-perform-data-analysis-in-power-bi-desktop\Starter**.

1. Sélectionnez le fichier **Sales Analysis.pbix**, puis sélectionnez **Ouvrir**.

    *Si vous êtes invité à remplacer le jeu de données, sélectionnez **Remplacer**.*

*Cette méthode crée un rapport et un jeu de données. Nous utiliserons uniquement le jeu de données pour créer un rapport dans cet exercice. Ce même processus peut être effectué avec un jeu de données existant à partir d’un rapport différent au lieu d’en charger un nouveau. En outre, si vous n’utilisez pas le rapport, les bonnes pratiques en matière d’espace de travail vous suggèrent de supprimer le fichier inutile.*

## **Créer le rapport**

Au cours de cette tâche, vous allez créer une connexion active au jeu de données Power BI créé durant la dernière tâche, puis créer un rapport **Sales Exploration**.

1. Ouvrez Power BI Desktop.

    ![Icône Power BI Desktop](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image1.png)

    *Important : Si vous avez déjà ouvert Power BI Desktop (dans le cadre d’un labo précédent), fermez cette instance.*

    *Conseil : Par défaut, la boîte de dialogue Prise en main s’ouvre par-dessus Power BI Desktop. Vous pouvez choisir de vous connecter, puis de fermer la fenêtre contextuelle.*

1. Dans le ruban Accueil, sélectionnez **Obtenir des données > Jeux de données Power BI**.

1. Dans la fenêtre **Hub de données**, sélectionnez le jeu de données **Sales Analysis** dans **Mon espace de travail**, puis **Se connecter** ou double-cliquez pour charger le jeu de données.

1. Accédez à **Fichier > Enregistrer** et enregistrez le fichier sous le nom **Sales Exploration** dans le dossier **D:\PL300\MySolution**.

*Vous allez maintenant créer deux pages de rapport et, sur chaque page, vous allez utiliser un visuel différent pour analyser et explorer les données.*

## **Créer un graphique à nuages de points animé**

Dans cette tâche, vous créez un graphique à nuages de points qui peut être animé.

1. Renommez la **Page 1** en **Graphique à nuages de points**.

1. Ajoutez un visuel de **Graphique à nuages de points** à la page de rapport, puis positionnez-le et redimensionnez-le afin qu’il remplisse toute la page.
    
    *Le graphique peut être animé quand un champ est ajouté à la barre d’outils/zone **Axe de lecture**.*

     ![Image 18](Linked_image_Files/10-perform-data-analysis-in-power-bi-desktop_image15.png)

     ![Image 75](Linked_image_Files/10-perform-data-analysis-in-power-bi-desktop_image16.png)

1. Ajoutez les champs suivants aux barres d’outils/zones des visuels :
    
    *Les labos utilisent une notation abrégée pour référencer un champ, à savoir : **Reseller** **\|** **Business Type**. Dans cet exemple, **Reseller** est le nom de la table et **Business Type** est le nom du champ.*

     - Axe des X : **Sales \| Sales**
     - Axe des Y : **Sales \| Profit Margin**
     - Légende : **Reseller \| Business Type**
     - Taille : **Sales \| Quantity**
     - Axe de lecture : **Date \| Quarter**

1. Dans le volet **Filtres**, ajoutez le champ **Product \| Category** à la barre d’outils/zone **Filtres dans cette page**.

1. Dans la carte de filtre, filtrez sur **Vélos**.

1. Pour animer le graphique, dans le coin inférieur gauche, sélectionnez **Lire**.

    ![Image 41](Linked_image_Files/10-perform-data-analysis-in-power-bi-desktop_image19.png)

1. Regardez la totalité du cycle d’animation de **FY2018 T1** à **FY2020 T4**.
    
    *Le graphique à nuages de points permet de comprendre les valeurs de mesure simultanément ; dans le cas présent, la quantité de commandes, le chiffre d’affaires et la marge bénéficiaire.*
    
    *Chaque bulle représente un type d’activité de revendeur. Les changements apportés à la taille des bulles reflètent l’augmentation ou la diminution des quantités de commandes. Tandis que les mouvements horizontaux représentent les augmentations/diminutions du chiffre d’affaires, les mouvements verticaux représentent les augmentations/diminutions de la rentabilité.*

1. Quand l’animation s’arrête, sélectionnez l’une des bulles pour afficher son suivi au fil du temps.

1. Placez le curseur sur une bulle pour afficher une info-bulle décrivant les valeurs de mesure du type de revendeur à ce moment précis.

1. Dans le volet **Filtres**, filtrez sur **Habillement** uniquement, puis notez que cela produit un résultat très différent.

1. Enregistrez le fichier Power BI Desktop.


## **Créer une prévision**

Au cours de cette tâche, vous allez créer une prévision pour déterminer le chiffre d’affaires futur potentiel.

1. Ajoutez une nouvelle page, puis renommez-la **Prévision**.

1. Ajoutez un visuel de **Graphique en courbes** à la page de rapport, puis positionnez-le et redimensionnez-le afin qu’il remplisse toute la page.

     ![Image 19](Linked_image_Files/10-perform-data-analysis-in-power-bi-desktop_image21.png)

     ![Image 74](Linked_image_Files/10-perform-data-analysis-in-power-bi-desktop_image22.png)

1. Ajoutez les champs suivants aux barres d’outils/zones des visuels :

     - Axe des X : **Date \| Date**
     - Axe des Y : **Sales \| Sales**

1. Dans le volet **Filtres**, ajoutez le champ **Date \| Year** à la barre d’outils/zone **Filtres dans cette page**.

1. Dans la carte de filtre, filtrez sur deux années : **FY2019** et **FY2020**.
    
    *Lors d’une prévision dans le temps, vous avez besoin d’au moins deux cycles (années) de données pour produire une prévision précise et stable.*

1. Ajoutez également le champ **Product \| Category** à la barre d’outils/zone **Filtres dans cette page**, puis filtrez sur **Vélos**.

1. Pour ajouter une prévision, sous le volet **Visualisations**, sélectionnez le volet **Analytique**.

     ![Image 20](Linked_image_Files/10-perform-data-analysis-in-power-bi-desktop_image26.png)

8. Développez la section **Prévision**.
    
    *Si la section **Prévision** n’est pas disponible, cela est probablement dû au fait que le visuel n’a pas été correctement configuré. La prévision est disponible uniquement quand deux conditions sont remplies : l’axe a un seul champ de type date et il n’y a qu’un seul champ de valeur.*

1. Passez l’option **Prévision** sur **Activé**.

1. Configurez les propriétés de prévision suivantes, puis sélectionnez **Appliquer** :

    - Unités : **Mois**
    - Longueur de la prévision : **1 mois**
    - Caractère saisonnier : **365**
    - Intervalle de confiance : **80 %**

    ![Image 52](Linked_image_Files/10-perform-data-analysis-in-power-bi-desktop_image29.png)

1. Dans le visuel de graphique en courbes, notez que la prévision s’est étendue d’un mois au-delà des données d’historique.
    
    *La zone grise représente la confiance. Plus la confiance est importante, moins la prévision est susceptible d’être stable et précise.*
    
    *Quand vous connaissez la durée du cycle (« annuel » dans le cas présent), vous devez entrer les points relatifs au caractère saisonnier. Le cycle peut aussi être hebdomadaire (7) ou mensuel (30).*

1. Dans le volet **Filtres**, filtrez sur **Habillement** uniquement, puis notez que cela produit un résultat différent.

### **Terminer**

Au cours de cette tâche, vous allez terminer le labo dans Power BI Desktop.

1. Sélectionnez la page **Graphique à nuages de points**.

1. Enregistrez le fichier Power BI Desktop.

1. Pour publier le fichier dans **Mon espace de travail**, sous l’onglet de ruban **Accueil**, dans le groupe **Partager**, sélectionnez **Publier**, puis **Sélectionner** pour publier.

    ![Image 23](Linked_image_Files/10-perform-data-analysis-in-power-bi-desktop_image46.png)

1. Fermez Power BI Desktop.
