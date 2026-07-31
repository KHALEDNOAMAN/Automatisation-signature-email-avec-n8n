# Automatisation des signatures e-mail avec n8n

##  Présentation

Ce projet a été réalisé dans le cadre de mon stage chez **MaterAuto**.

L'objectif principal est d'automatiser la génération et la distribution des signatures e-mail des employés de l'entreprise à l'aide de **n8n**. Cette solution permet de réduire considérablement le temps consacré à la création manuelle des signatures tout en garantissant une présentation uniforme pour l'ensemble des collaborateurs.

Le workflow récupère automatiquement les informations des employés depuis Google Sheets, sélectionne le modèle de signature approprié selon le département et le type de signature, génère les fichiers HTML correspondants, les regroupe dans une archive ZIP puis les envoie automatiquement par e-mail aux responsables.

---

# Objectifs

- Automatiser la création des signatures e-mail.
- Réduire le temps de traitement.
- Éviter les erreurs de saisie manuelle.

---

#  Fonctionnalités

- Lecture automatique des informations des employés depuis Google Sheets.
- Téléchargement automatique des modèles HTML depuis Google Drive.
- Génération dynamique des signatures selon le modèle choisi.
- Création automatique des fichiers HTML.
- Génération d'une page HTML contenant toutes les signatures d'un département.
- Recherche rapide d'une signature dans la page générée.
- Téléchargement individuel des signatures HTML.
- Compression des signatures en fichiers ZIP.
- Envoi automatique des archives ZIP par Gmail.

---

#  Architecture du projet

Google Sheets
↓
Informations des employés

Google Drive
↓
Modèles HTML

n8n
↓
Lecture des données
↓
Sélection du modèle
↓
Génération des signatures HTML
↓
Création des fichiers HTML
↓
Création d'une page HTML
↓
Compression ZIP
↓
Envoi automatique par Gmail

---
#  Technologies utilisées

## Automatisation

- n8n

## Conteneurisation

- Docker
- Docker Compose

## Langages

- JavaScript
- HTML
- CSS

## Services Google

- Google Cloud Platform (Configuration OAuth 2.0)
- Google Sheets API
- Google Drive API
- Gmail API
- Google Sheets
- Google Drive
- Gmail

---

#  Fonctionnement du workflow

Le workflow est organisé en plusieurs étapes.

### 1. Téléchargement des modèles

Les modèles HTML des signatures sont récupérés automatiquement depuis Google Drive.

### 2. Extraction des modèles

Chaque modèle téléchargé est converti en texte afin de pouvoir être manipulé par les nœuds JavaScript.

### 3. Lecture des données

Les informations des employés (nom, poste, téléphone, e-mail, photo et modèle de signature) sont récupérées depuis Google Sheets.

### 4. Génération des signatures

Les nœuds JavaScript analysent les informations de chaque employé, sélectionnent automatiquement le modèle correspondant puis remplacent les variables dynamiques afin de produire une signature HTML personnalisée.

### 5. Création des fichiers HTML

Chaque signature générée est enregistrée sous forme d'un fichier HTML prêt à être utilisé.

### 6. Création d'une page HTML

Toutes les signatures d'un même département sont regroupées dans une page web contenant un système de recherche ainsi qu'un bouton permettant de télécharger chaque signature individuellement.

### 7. Compression des résultats

Les fichiers HTML générés sont regroupés dans une archive ZIP afin de faciliter leur distribution et de réduire les contraintes liées à l'envoi d'un grand nombre de fichiers par e-mail.

### 8. Envoi automatique

Les archives ZIP sont envoyées automatiquement aux responsables grâce au nœud Gmail.

---

# Résultat

Le workflow permet de produire automatiquement :

- les signatures HTML personnalisées ;
- une page HTML regroupant toutes les signatures d'un département ;
- une archive ZIP contenant les signatures ;
- un envoi automatique par Gmail.

Cette automatisation réduit fortement le temps de traitement et limite les interventions manuelles.

---
# 🔮 Améliorations futures

Plusieurs évolutions sont envisagées afin de rendre cette solution plus simple à utiliser et mieux adaptée aux besoins des entreprises.

- Développer une interface web permettant aux utilisateurs d'utiliser le système sans accéder directement à n8n.
- Permettre à l'utilisateur de saisir simplement le nom du modèle de signature ou de la liste des employés, afin que l'application retrouve automatiquement les fichiers correspondants et lance le workflow.
- Ajouter un aperçu des signatures générées ainsi que le nombre total de signatures avant leur génération ou leur envoi.
- Intégrer un assistant basé sur l'intelligence artificielle pour guider les utilisateurs dans l'utilisation de l'application et les assister lors de la configuration des services Google.
- Détecter automatiquement les erreurs de connexion (identifiants expirés, jetons OAuth invalides ou accès refusés) et fournir des explications compréhensibles ainsi que les étapes à suivre pour résoudre le problème.
- Étendre la solution afin de prendre en charge d'autres plateformes de messagerie et de stockage cloud.

#  Auteur

**RAHARINDRIAKA Angella Toky**
GitHub : https://github.com/Angellatoky