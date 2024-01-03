---
lab:
  "\_\_ title": Manage files and semantic models in Power BI
  "\_\_ module": Deploy and manage Power BI service items
---

# Gérer des fichiers et des modèles sémantiques dans Power BI

## Préparer l’actualisation des données de la passerelle

> **Notez** que les étapes suivantes ne sont pas nécessaires lors de l’utilisation de la passerelle de données en mode personnel. Vous pouvez passer directement à l’objectif suivant (configurer la passerelle).

1. Dans Power BI Desktop, ouvrez la fenêtre de l’Éditeur Power Query, puis sélectionnez la requête **ProductCost**.

1. Modifiez l’étape Source, puis modifiez le chemin du fichier pour utiliser le partage de fichiers, comme suit :

    `\\DATA-AI\Data\ProductCost.xlsx`

1. Fermez et appliquez la fenêtre Éditeur Power Query.

1. Enregistrez le fichier Power BI Desktop.

1. Publiez le fichier Power BI Desktop sur l’espace de travail, en remplaçant le modèle sémantique et le rapport dans le service.

## Configurer la passerelle (mode personnel)

1. Dans le service Power BI pour l’instructeur, rechargez (F5) la page des paramètres du modèle sémantique.

1. Développez la section Connexion à la passerelle et faites remarquer qu’aucune passerelle n’est installée.

1. Utilisez la liste déroulante de téléchargement (située en haut à droite), puis sélectionnez Passerelle de données.

1. Dans la nouvelle page web, téléchargez la passerelle en mode personnel.

1. Une fois qu’il est téléchargé, ouvrez le fichier téléchargé.

1. Effectuez la configuration de la passerelle en utilisant les informations d’identification du compte de l’instructeur.

1. Une fois la passerelle configurée, revenez à la page des paramètres du modèle sémantique et rechargez-la.

1. Affectez la passerelle personnelle et modifiez les informations d’identification pour les deux sources de données.

1. Pour les deux sources de données, affectez à la méthode d’authentification la valeur **WindowsWithoutImpersonation**, puis affectez au niveau de confidentialité la valeur **Organisation**.

1. Si vous le souhaitez, développez la section **Actualisation planifiée**, puis montrez comment configurer une planification récurrente.

## Actualiser le modèle sémantique

1. Avant d’actualiser le modèle sémantique, ouvrez le tableau de bord **Surveillance des ventes**.

1. Modifiez les détails de la vignette Sales, Profit Margin pour y afficher l’heure de la dernière actualisation.

1. Cliquez avec le bouton droit sur le fichier `D:\PL300\Demo\Resources\UpdateDatabase-LoadAdditionalSales.ps1`, puis exécutez avec PowerShell. *Ce script va charger les données des ventes de décembre 2020 dans la base de données.*

1. Dans le service Power BI pour l’instructeur, à partir du volet de navigation, actualisez le modèle sémantique **Sales Analysis**.

1. Une fois l’actualisation terminée, montrez comment la colonne **Décembre 2020** de la vignette du tableau de bord apparaît et que l’heure d’actualisation est **MAINTENANT**.
