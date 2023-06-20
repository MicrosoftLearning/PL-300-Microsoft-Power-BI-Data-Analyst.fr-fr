---
lab:
  title: Créer un tableau de bord Power BI
  module: 11 - Create Dashboards
---


# **Créer un tableau de bord Power BI**

**La durée estimée pour effectuer ce tutoriel est de 45 minutes.**

Dans ce labo, vous allez créer le tableau de bord **Surveillance des ventes**.

Dans ce labo, vous allez découvrir comment :

- Épingler des visuels à un tableau de bord
- Utilisez Questions et réponses pour créer des vignettes de tableau de bord

### **Histoire du labo**

Ce labo est l’un des nombreux labos d’une série qui a été conçue comme une histoire complète allant de la préparation des données jusqu’à leur publication sous forme de rapports et de tableaux de bord. Vous pouvez effectuer ces labos dans l’ordre de votre choix. Toutefois, si vous comptez suivre plusieurs labos, pour les dix premiersd’entre eux, nous vous suggérons de suivre cet ordre :

1. Préparer des données dans Power BI Desktop
1. Charger des données dans Power BI Desktop
1. Modéliser les données dans Power BI Desktop
1. Créer des calculs DAX dans Power BI Desktop
1. Créer des calculs DAX avancés dans Power BI Desktop
1. Concevoir un rapport dans Power BI Desktop
1. Améliorer un rapport dans Power BI Desktop
1. Analyser les données dans Power BI Desktop
1. **Créer un tableau de bord Power BI**
1. Appliquer la sécurité au niveau des lignes

## **Exercice 1 : Créer un tableau de bord**

Dans cet exercice, vous allez créer le tableau de bord **Surveillance des ventes**. Le tableau de bord terminé se présente comme suit :

![Image du tableau de bord terminé, comprenant trois vignettes.](Linked_image_Files/09-create-power-bi-dashboard_image1.png)

### **Tâche 1 : Démarrer – Se connecter**

Au cours de cette tâche, vous allez configurer l’environnement nécessaire pour le labo en vous connectant à Power BI.

*Remarque : Si vous êtes déjà connecté à Power BI, passez à la tâche suivante.*

1. Pour ouvrir Microsoft Edge, dans la barre des tâches, sélectionnez le raccourci du programme Microsoft Edge.

     ![Image 12](Linked_image_Files/08-design-report-in-power-bi-desktop-enhanced_image1.png)

1. Dans la fenêtre du navigateur Microsoft Edge, accédez à **https://app.powerbi.com**.

    *Conseil : Vous pouvez également utiliser le favori Service Power BI dans la barre des favoris Microsoft Edge.*

1. Effectuez le processus de connexion avec vos informations d’identification organisationnelles (ou celles qui vous sont fournies). Si Microsoft Edge vous invite à rester connecté, sélectionnez **Oui**.

1. Dans la fenêtre du navigateur Microsoft Edge, dans le service Power BI, dans le volet **Navigation**, développez **Mon espace de travail**. Laissez la fenêtre du navigateur Microsoft Edge ouverte.

     ![Image 22](Linked_image_Files/07-my-workspace-new.png)

### **Tâche 2 : Démarrer – Ouvrir un rapport**

Au cours de cette tâche, vous allez configurer l’environnement pour le labo en ouvrant le rapport de démarrage.

*Important : Si vous venez d’effectuer le labo précédent (et que vous l’avez entièrement terminé), ignorez cette tâche et passez directement à la suivante.*

1. Ouvrez Power BI Desktop.
    
    *Par défaut, la boîte de dialogue Prise en main s’ouvre par-dessus Power BI Desktop. Connectez-vous, puis fermez la fenêtre contextuelle.*

    ![Icône Power BI Desktop](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image1.png)

1. Pour ouvrir le fichier Power BI Desktop de démarrage, sélectionnez **Fichier > Ouvrir le rapport > Parcourir les rapports**.

1. Dans la fenêtre **Ouvrir**, accédez au dossier **D:\PL300\Labs\09-create-power-bi-dashboard\Starter**, puis ouvrez le fichier **Sales Analysis**.

1. Fermez toutes les fenêtres d’information qui se sont éventuellement ouvertes.

1. Notez qu’un message d’avertissement jaune est affiché sous le ruban. *Ce message vous avertit que les requêtes n’ont pas été appliquées pour se charger en tant que tables de modèle. Vous appliquerez les requêtes plus tard dans le labo.*
    
    *Pour fermer le message d’avertissement, à droite du message d’avertissement jaune, sélectionnez **X**.*

1. Pour créer une copie du fichier, accédez à **Fichier > Enregistrer sous** et enregistrez-le dans le dossier **D:\PL300\MySolution**.

1. Si vous êtes invité à appliquer les modifications, sélectionnez **Appliquer plus tard**.

### **Tâche 3 : Démarrer – Publier le rapport**

Au cours de cette tâche, vous allez configurer l’environnement pour le labo en créant un jeu de données. *Si vous avez déjà publié le jeu de données, passez à la tâche suivante.*

1. Dans la fenêtre du navigateur Microsoft Edge, dans le service Power BI, accédez à **Mon espace de travail**.

1. Sélectionnez **Charger > Parcourir**.

1. Accédez au dossier **D:\PL300\Labs\09-create-power-bi-dashboard\Starter**.

1. Sélectionnez le fichier **Sales Analysis.pbix**, puis sélectionnez **Ouvrir**.

*Si vous êtes invité à remplacer le jeu de données, sélectionnez **Remplacer**.*

### **Tâche 4 : Créer un tableau de bord**

Au cours de cette tâche, vous allez créer le tableau de bord **Surveillance des ventes**. Vous épinglez un visuel à partir du rapport, vous ajoutez une vignette basée sur un URI de données image, puis vous utilisez Questions et réponses pour créer une vignette.

1. Dans le service Power BI, ouvrez le rapport **Sales Analysis**.

1. Dans la page **Vue d’ensemble**, définissez le segment **Année** sur **FY2020** (Année fiscale 2020).

    ![Image 4](Linked_image_Files/09-create-power-bi-dashboard_image17.png)

1. Définissez le segment **Région**, sur **Sélectionner tout**.

    *Les visuels épinglés sont définis avec le contexte de filtre au moment de l’épinglage. Si le visuel sous-jacent change, vous devez également mettre à jour la vignette du tableau de bord. Pour les filtres basés sur le temps, il est préférable d’utiliser un segment de date relative (ou Q&R à l’aide d’une question basée sur le temps relatif).*

1. Pour créer un tableau de bord et y épingler un visuel, pointez le curseur sur le visuel **Sales and Profit Margin by Month** (graphique en colonnes/courbes), puis sélectionnez l’épingle.

    ![Image 43](Linked_image_Files/09-create-power-bi-dashboard_image18.png)

1. Dans la fenêtre **Épingler au tableau de bord**, dans la zone **Nom du tableau de bord**, entrez **Surveillance des ventes**, puis sélectionnez **Épingler**.

    ![Image 3](Linked_image_Files/09-create-power-bi-dashboard_image19.png)

1. Ouvrez **Mon espace de travail**, puis ouvrez le tableau de bord **Surveillance des ventes**.

1. Notez que le tableau de bord comporte une seule vignette.

    ![Image 45](Linked_image_Files/09-create-power-bi-dashboard_image22.png)

1. Pour ajouter une vignette basée sur une question, en haut à gauche du tableau de bord, sélectionnez **Poser une question sur vos données**.
    
    *Vous pouvez utiliser la fonctionnalité Questions et réponses, et Power BI répondra avec un visuel.*

    ![Image 7](Linked_image_Files/09-create-power-bi-dashboard_image23.png)

1. Sélectionnez l’une des questions suggérées sous la zone Questions et réponses, dans les zones bleues, et examinez la réponse.

1. Supprimez tout le texte de la zone Q&R, puis entrez les éléments suivants : **Ventes actuelles**

1. Notez la réponse **(vide)**.
    
    *Vous vous souvenez peut-être que vous aviez ajouté la mesure **Ventes actuelles** dans le labo **Créer des calculs DAX avancés dans Power BI Desktop**. Cette mesure est une expression Time Intelligence et requiert un filtre sur la table **Date** pour produire un résultat.*

    ![Image 14](Linked_image_Files/09-create-power-bi-dashboard_image25.png)

1. Étendez la question avec : **durant l’année fiscale 2020**.

1. Notez que maintenant la réponse est **(33M$)**.

    ![Image 13](Linked_image_Files/09-create-power-bi-dashboard_image27.png)

1. Pour épingler la réponse au tableau de bord, dans le coin supérieur droit, sélectionnez **Épingler un visuel**.

    ![Image 15](Linked_image_Files/09-create-power-bi-dashboard_image28.png)

1. Lorsque vous êtes invité à épingler la vignette au tableau de bord, sélectionnez **Épingler**.

1. Pour revenir au tableau de bord, dans l’angle supérieur gauche, sélectionnez **Quitter Questions et réponses**.

1. Pour ajouter le logo de la société, dans la barre de menus, sélectionnez **Modifier**, puis **Ajouter une vignette**.
    
    *Avec cette technique d’ajout d’une vignette de tableau de bord, vous pouvez améliorer votre tableau de bord en y incorporant des médias, y compris du contenu web, des images, des zones de texte enrichi et des vidéos (au moyen de liens YouTube ou Vimeo).*

1. Dans le volet **Ajouter une vignette** (à droite), sélectionnez la vignette **Image**, puis **Suivant**.

1. Dans le volet **Ajouter une vignette d’image**, dans la zone **URL**, entrez l’URL complète fournie dans le fichier **D:\PL300\Resources\AdventureWorksLogo_DataURL.txt**, puis sélectionnez **Appliquer**.
    
    *Vous pouvez incorporer une image avec son URL, ou utiliser une URL de données qui incorpore le contenu inline.*

1. Pour redimensionner la vignette du logo, faites glisser l’angle inférieur droit et redimensionnez la vignette pour qu’elle ait une unité de largeur et deux unités de hauteur.
    
    *Les vignettes doivent obligatoirement être rectangulaires.*

1. Organisez les vignettes de sorte que le logo apparaisse en haut à gauche, avec la vignette **Ventes actuelles** en dessous et la vignette **Ventes, marge bénéficiaire** à droite.

    ![Image 52](Linked_image_Files/09-create-power-bi-dashboard_image35.png)

### **Tâche 5 : Modifier les détails des vignettes**

Au cours de cette tâche, vous allez modifier les détails de deux vignettes.

1. Pointez le curseur sur la vignette **Ventes actuelles** et, en haut à droite de la vignette, sélectionnez les points de suspension, puis **Modifier les détails**.

    ![Image 50](Linked_image_Files/09-create-power-bi-dashboard_image36.png)

1. Dans le volet **Détails de la vignette** (situé à droite), dans la zone **Sous-titre**, entrez **Année fiscale 2020**, puis sélectionnez **Appliquer**.

1. Notez que la vignette **Ventes actuelles** affiche un sous-titre.

    ![Image 21](Linked_image_Files/09-create-power-bi-dashboard_image39.png)

1. Modifiez les détails de la vignette **Ventes, marge bénéficiaire**.

1. Dans le volet **Détails de la vignette**, dans la section **Fonctionnalité**, cochez **Afficher l’heure de la dernière actualisation**, puis sélectionnez **Appliquer**.

    ![Image 22](Linked_image_Files/09-create-power-bi-dashboard_image40.png)

1. Notez que la vignette décrit l’heure de la dernière actualisation (que vous avez effectuée lors du chargement du modèle de données dans Power BI Desktop).

*Vous actualiserez le jeu de données dans l’exercice suivant. En fonction de vos données et de votre rapport, vous pouvez effectuer une actualisation des données ad hoc à tout moment ou définir une planification. Toutefois, les actualisations planifiées nécessitent des passerelles que nous ne sommes pas en mesure de configurer pour ce labo. Ainsi, à partir de Power BI Desktop, vous allez effectuer une actualisation manuelle des données, puis charger le fichier dans votre espace de travail.*

## **Exercice 2 : Actualiser le jeu de données**

Dans cet exercice, vous commencerez par charger les données des commandes client pour juin 2020 dans la base de données **AdventureWorksDW2020**. Ensuite, vous ouvrirez votre fichier Power BI Desktop, vous actualiserez les données, puis vous chargerez le fichier dans votre espace de travail.

### **Tâche 1 : Mettre à jour la base de données du labo**

Dans cette tâche, vous exécutez un script PowerShell pour mettre à jour les données contenues dans la base de données **AdventureWorksDW2020**.

1. Dans l’Explorateur de fichiers, à l’intérieur du dossier **D:\PL300\Setup**, cliquez avec le bouton droit sur le fichier **UpdateDatabase-2-AddSales.ps1**, puis sélectionnez **Exécuter avec PowerShell**.

    ![Image 28](Linked_image_Files/09-create-power-bi-dashboard_image46.png)

1. Si vous êtes invité à changer la stratégie d’exécution, appuyez sur **A**.

1. Lorsque vous êtes invité à appuyer sur une touche quelconque pour continuer, appuyez de nouveau sur **Entrée**.

*La base de données **AdventureWorksDW2020** inclut maintenant les commandes client pour juin 2020.*

### **Tâche 2 : Actualiser le fichier Power BI Desktop**

Au cours de cette tâche, vous allez ouvrir le fichier **Sales Analysis** Power BI Desktop, effectuer une actualisation des données, puis charger le fichier dans votre espace de travail **Analyse des ventes**.

1. Dans le fichier Power BI Desktop, dans le volet **Champs**, cliquez avec le bouton droit sur la table **Ventes**, puis sélectionnez **Actualiser les données**.

    ![Image 55](Linked_image_Files/09-create-power-bi-dashboard_image47.png)

1. Une fois l’actualisation terminée, enregistrez le fichier Power BI Desktop.

1. Pour publier le fichier dans votre espace de travail, sous l’onglet de ruban **Accueil**, dans le groupe **Partager**, sélectionnez **Publier**, puis **Sélectionner** pour publier.

    ![Image 59](Linked_image_Files/09-create-power-bi-dashboard_image48.png)

1. Lorsque vous êtes invité à remplacer le jeu de données, sélectionnez **Remplacer**.

1. Fermez Power BI Desktop.

*Le jeu de données dans le service Power BI contient maintenant des données de ventes pour juin 2020.*

## **Exercice 3 : Examiner le tableau de bord**

Dans cet exercice, vous allez examiner le tableau de bord pour voir les ventes mises à jour.

### **Tâche 1 : Examiner le tableau de bord**

Au cours de cette tâche, vous allez examiner le tableau de bord pour voir les ventes mises à jour.

1. Dans la fenêtre du navigateur Microsoft Edge, ouvrez Service Power BI, puis passez en revue le tableau de bord **Surveillance des ventes** dans **Mon espace de travail**.

2. Dans la vignette **Sales, Profit Margin**, en concordance avec le sous-titre, notez que les données ont été **Actualisées : MAINTENANT**.

3. Notez également qu’il y a désormais une colonne pour **juin 2020**.
    
    *Si vous ne voyez pas de données pour le mois de juin 2020, essayez d’actualiser le navigateur en appuyant sur **F5**.*

    ![Image 33](Linked_image_Files/09-create-power-bi-dashboard_image50.png)
