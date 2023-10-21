---
lab:
  "\_\_ title": Enforce Row-level security in Power BI
  "\_\_ module": Deploy and manage Power BI service items
---
# Renforcer la sécurité au niveau des lignes dans Power BI

## Ajouter une table de sécurité au modèle

1. Dans Power BI Desktop, ouvrez la fenêtre Éditeur Power Query.

1. Ajoutez une nouvelle requête basée sur le fichier`D:\Demo\Data\**ManagerCategory**.xlsx`.

1. Utilisez la table **ManagerCategory** dans le fichier.

1. Supprimez la colonne **Manager**.

1. Divisez la colonne **Catégorie** en utilisant le point-virgule comme délimiteur, puis divisez-la en lignes (options avancées).

1. Dans la colonne **E-mail**, remplacez la valeur **<ty-johnston@tailspintoys.com>** par le compte du destinataire (provenant du fichier MySettings.txt).

1. Faites remarquer que cet utilisateur peut voir trois catégories de produits : **Collective pitch, Trainer et Warbird**.

1. Fermez et appliquez les requêtes.

1. Dans la vue Modèle, créez une relation entre les tables **ManagerCategory** et Product pour les colonnes **Category**.

1. Définissez la direction du filtre croisé sur Single (**ManagerCategory** filtre Product).

1. Masquez la table **ManagerCategory**.

## Ajouter un rôle

1. Dans la vue Rapport, ouvrez Gérer les rôles, puis créez un rôle nommé **Manager**.

1. Dans le rôle, filtrez la colonne Email address de la table **ManagerCategory** comme suit :

  ```dax
   [Email] = USERPRINCIPALNAME()
   ```

1. **Enregistrez.** .

## Vérifier le rôle

1. Ouvrez  l'affichage Voir comme, puis configurez les paramètres suivants :

    - Autre utilisateur : activez l'option, puis entrez le compte du destinataire.

    - Rôle Manager : activez l'option

1. Faites remarquer que le visuel de filtre montre seulement trois catégories de produits.

1. Arrêtez l’affichage du rapport en utilisant les options de Voir comme.

1. Enregistrez le fichier Power BI Desktop.

1. Publiez le fichier Power BI Desktop sur l’espace de travail, en remplaçant le jeu de données et le rapport dans le service.

1. Fermez Power BI Desktop.

## Configurer la sécurité du jeu de données

1. Dans le service Power BI pour l’instructeur, dans le volet Navigation, ouvrez la page Sécurité du jeu de données **Sales Analysis**.

1. Dans la section Membres, entrez le compte du destinataire (qui représente **Ty Johnston**).

1. Ajouter et enregistrer.

## Tester la sécurité au niveau des lignes dans l’application

1. Dans le service Power BI pour le destinataire, actualisez le tableau de bord (laissé ouvert depuis la démonstration précédente).

1. Dans la vignette du tableau de bord **Profit Margin**, vérifiez que seules trois catégories de produits sont visibles.
