---
demo:
  title: "Gérer des fichiers et des modèles sémantiques dans Power\_BI"
  module: Deploy and manage Power BI service items
---
# Gérer des fichiers et des modèles sémantiques dans Power BI

## Configurer la passerelle (mode personnel)

1. Dans le service Power BI, rechargez (F5) la page des paramètres du modèle sémantique.

1. Développez la section Connexion à la passerelle et faites remarquer qu’aucune passerelle n’est installée.

1. Utilisez la liste déroulante de téléchargement (située en haut à droite), puis sélectionnez Passerelle de données.

1. Dans la nouvelle page web, téléchargez la passerelle en mode personnel.

1. Une fois qu’il est téléchargé, ouvrez le fichier téléchargé.

1. Terminez la configuration de la passerelle à l’aide de votre compte d’organisation.

1. Une fois la passerelle configurée, revenez à la page des paramètres du modèle sémantique et rechargez-la.

1. Affectez la passerelle personnelle et modifiez les informations d’identification pour les deux sources de données.

1. Pour les deux sources de données, affectez à la méthode d’authentification la valeur**WindowsWithoutImpersonation**, puis affectez au niveau de confidentialité la valeur**Organisation**.

1. Si vous le souhaitez, développez la section**Actualisation planifiée**, puis montrez comment configurer une planification récurrente.

## Actualiser le modèle sémantique

1. Avant d’actualiser le modèle sémantique, ouvrez le tableau de bord**Surveillance des ventes**.

1. Modifiez les détails de la vignette Sales, Profit Margin pour y afficher l’heure de la dernière actualisation.

1. Cliquez avec le bouton droit sur le fichier`D:\Allfiles\Demo\Resources\UpdateDatabase-LoadAdditionalSales.ps1`, puis exécutez avec PowerShell. *Ce script va charger les données des ventes de décembre 2020 dans la base de données.*

1. Dans le service Power BI pour l’instructeur, à partir du volet de navigation, actualisez le modèle sémantique**Sales Analysis**.

1. Une fois l’actualisation terminée, montrez comment la colonne**Décembre 2020** de la vignette du tableau de bord apparaît et que l’heure d’actualisation est**MAINTENANT**.
