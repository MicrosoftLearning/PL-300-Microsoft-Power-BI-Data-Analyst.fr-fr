---
lab:
  course: PL-300
  title: Appliquer la sécurité au niveau des lignes
  module: Enforce Row-Level Security
---


# **Appliquer la sécurité au niveau des lignes**

## **Histoire du labo**

Dans ce labo, vous allez appliquer la sécurité au niveau des lignes pour vous assurer qu’un vendeur ne peut analyser les données de ventes que pour la ou les régions qui lui sont affectées.

Dans ce labo, vous allez découvrir comment :

- Appliquer la sécurité au niveau des lignes
- Choisir entre des méthodes dynamiques et statiques

**Ce labo devrait prendre environ 20 minutes.**

## **Prise en main**

Au cours de cette tâche, vous allez configurer l’environnement pour le labo.

*Important : Si vous venez d’effectuer le labo précédent (et que vous l’avez entièrement terminé), ignorez cette tâche et passez directement à la suivante.*

1. Ouvrez Power BI Desktop.

    ![Icône Power BI Desktop](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image1.png)

1. Pour ouvrir le fichier Power BI Desktop de démarrage, sélectionnez **Ouvrir > Parcourir cet appareil**.

1. Dans la fenêtre **Ouvrir**, accédez au dossier **D:\Allfiles\Labs\10-row-level-security\Starter**, puis ouvrez le fichier **Sales Analysis**.

   *Remarque : à ce stade, Power BI vous demande de vous connecter si ce n’est déjà fait. Vous pouvez vous connecter ou sélectionner **Annuler** et continuer le labo.*

1. Fermez toutes les fenêtres d’information qui se sont éventuellement ouvertes.

1. Notez le message d’avertissement sous le ruban. *Ce message vous avertit que les requêtes n’ont pas été appliquées pour se charger en tant que tables de modèle. Vous appliquerez les requêtes plus tard dans ce labo.*
    
    *Pour ignorer le message d’avertissement, sélectionnez **X** à droite.*

1. Pour créer une copie du fichier, accédez à **Fichier > Enregistrer sous**, puis enregistrez dans le dossier **D:\Allfiles\MySolution**.

1. Si vous êtes invité à appliquer les modifications, sélectionnez **Appliquer plus tard**.

## **Appliquer la sécurité au niveau des lignes**

Au cours de cette tâche, vous allez appliquer la sécurité au niveau des lignes pour vous assurer qu’un vendeur ne peut voir que les ventes réalisées dans la ou les régions qui lui sont affectées.

1. Revenez à la vue Table.

   ![Image 5701](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image20.png)

1. Dans le volet **Données**, sélectionnez la table **Salesperson (Performance)** (Vendeur - Performances).


1. Examinez les données. Notez que Michael Blythe (EmployeeKey 281) a cette valeur UPN : **michael-blythe@adventureworks.com**
    
    *Rappelez-vous que Michael Blythe est affecté à trois régions de vente : USA Nord-Est, USA Centre et USA Sud-Est.*

1. Dans l’onglet de ruban **Accueil**, à l’intérieur du groupe **Sécurité**, sélectionnez **Gérer les rôles**.

    ![Image 5700](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image21.png)

1. Dans la fenêtre **Gérer les rôles de sécurité**, dans la section **Rôles**, sélectionnez **Nouveau**.

1. Dans la zone, remplacez le texte sélectionné par le nom du rôle : **Salespeople**, puis appuyez sur **Entrée**.

   ![Image 5703](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image23.png)

1. Pour affecter un filtre, sélectionnez la table **Salesperson (Performance)**, puis sélectionnez **Basculer vers l’éditeur DAX** dans la section **Filtrer les données**.

   ![Capture d’écran 2024-04-18 144345](https://github.com/afelix-95/PL-300-Microsoft-Power-BI-Data-Analyst/assets/148110824/1308d47f-2cca-4f88-9237-b02b66b4cf1e)

1. Dans zone de l’éditeur DAX, entrez l’expression suivante :

    **DAX**

    ```
    [UPN] = USERPRINCIPALNAME()
    ```
    
    *USERPRINCIPALNAME() est une fonction DAX (Data Analysis Expressions) qui retourne le nom de l’utilisateur authentifié. Cela signifie que la table **Salesperson (Performance)** filtrera par le nom d’utilisateur principal (UPN) de l’utilisateur qui interroge le modèle.*

   ![Image 11](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image25.png)

1. Sélectionnez **Enregistrer** et **Fermer**.

1. Pour tester le rôle de sécurité, dans l’onglet de ruban **Accueil**, à l’intérieur du groupe **Sécurité**, sélectionnez **Afficher comme**.

   ![Image 5708](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image27.png)

1. Dans la fenêtre **Afficher comme rôles**, activez la case à cocher  **Autre utilisateur**, puis dans la zone correspondante, entrez : **michael-blythe@adventureworks.com**

1. Vérifiez le rôle **Salespeople**, puis sélectionnez **OK**.
    
    *Cette configuration se traduit par l’utilisation du rôle **Salespeople** et l’emprunt de l’identité de l’utilisateur avec le nom de Michael Blythe.*

   ![Image 5709](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image28.png)

1. Notez la bannière jaune au-dessus de la page du rapport, qui indique le contexte de sécurité du test.

   ![Image 13](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image30.png)

1. Notez, dans le visuel de table, que seul le vendeur **Michael Blythe** est listé.

   ![Image 5713](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image31.png)

1. Pour arrêter le test, sur le côté droit de la bannière jaune, sélectionnez **Arrêter l’affichage**.

   ![Image 5712](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image32.png)

1. Pour supprimer le rôle **Salespeople**, dans l’onglet de ruban **Accueil**, à l’intérieur du groupe **Sécurité**, sélectionnez **Gérer les rôles**.

   ![Image 16](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image33.png)

1. Dans la fenêtre **Gérer les rôles de sécurité**, sélectionnez les points de suspension (…) dans le rôle **Salespeople** , puis sélectionnez **Supprimer**. Lorsque vous êtes invité à confirmer la suppression, sélectionnez **Oui, Supprimer**.

   ![Capture d’écran 2024-04-18 145556](https://github.com/afelix-95/PL-300-Microsoft-Power-BI-Data-Analyst/assets/148110824/deeb4eac-b639-433d-a9d4-29c8e127008e)

### **Terminer**

Dans cette tâche, vous allez terminer le labo.

1. Sélectionnez **Enregistrer**, puis enregistrez le fichier Power BI Desktop pour mettre fin au labo.

*Remarque : Une fois que le fichier Power BI Desktop aura été publié sur le service Power BI, vous devrez effectuer une tâche de post-publication pour mapper les principaux de sécurité au rôle **Salespeople**. Vous n’effectuerez pas cette tâche durant ce labo.*
