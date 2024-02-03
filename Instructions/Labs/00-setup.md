---
lab:
  course: 'PL-300, DP-605'
  title: Configurer votre propre environnement
  module: Set up your own environment
---

# Configurer un environnement de labo local

Dans l’idéal, vous devez suivre ces labos dans un environnement de labo hébergé. Si vous souhaitez les terminer sur votre propre ordinateur, vous pouvez le faire en installant le logiciel suivant.

- Tous les fichiers d’installation et de ressources peuvent être [téléchargés à partir de GitHub](https://github.com/MicrosoftLearning/PL-300-Microsoft-Power-BI-Data-Analyst/raw/Main/AllfilesDownload.zip).
  - Extrayez le dossier « AllFiles » dans D:/ et renommez-le « D:\Allfiles\' ».

***Vous pouvez rencontrer des boîtes de dialogue et des comportements inattendus lors de l’utilisation de votre propre environnement. En raison du large choix de configurations locales possibles, l’équipe du cours ne peut pas prendre en charge les problèmes que vous êtes susceptible de rencontrer dans votre propre environnement.***

## Instructions d’utilisation pour Windows 11

> &#128221; Les instructions ci-dessous s’appliquent aux ordinateurs Windows 11. L’expérience peut être différente avec un autre système d’exploitation.

### Power BI Desktop

1. Télécharger et installer à partir du Microsoft Store. Si vous n’avez pas accès au Microsoft Store, effectuez le téléchargement à partir du [web](https://www.microsoft.com/download/details.aspx?id=58494). Power BI Desktop est la principale application de ces labos.

    - Utilisez les options par défaut dans le programme d’installation.

### Compte de développeur M365

Pour certains exercices, vous devrez vous connecter à Power BI avec un compte d’organisation. Vous pouvez utiliser votre propre compte, mais si vous n’y avez pas accès, vous pouvez créer un [compte de développeur M365](https://developer.microsoft.com/en-us/microsoft-365/dev-program) gratuit.

### Moteur de base de données SQL Server

1. Le labo se connecte à une instance de SQL Server localhost. Les instructions suivantes vous aideront à installer SQL Server et à configurer les options par défaut. Il vous suffit d’installer la fonctionnalité Moteur de base de données.

    - Télécharger la [copie Développeur gratuite du support d’installation](https://www.microsoft.com/sql-server/sql-server-downloads?SilentAuth=1&f=255&MSPPError=-2147217396&rtc=1)
    - [Installer SQL Server à partir de l’Assistant Installation (programme d’installation)](https://learn.microsoft.com/sql/database-engine/install-windows/install-sql-server-from-the-installation-wizard-setup)

> &#128221; Vous pouvez utiliser une instance SQL Server existante si vous y avez accès, au lieu d’installer une version locale. Toutefois, vous devrez remplacer la chaîne de connexion « localhost » par le nom de votre instance.

### Microsoft Edge

1. Installez la dernière version de [Microsoft Edge](https://microsoft.com/edge) pour accéder au service Power BI en ligne.
