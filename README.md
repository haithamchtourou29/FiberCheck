# FiberCheck

**Plateforme de supervision et de qualification des lignes fibre optique (XPON)**

Projet réalisé dans le cadre du module *Développement Web Dynamique* (ENET'Com, 2e année IDSD, 2026 – 2027).

## Présentation

FiberCheck est une application web dynamique qui permet de suivre l'état des lignes fibre optique par gouvernorat. Elle importe les données du réseau, contrôle automatiquement la qualité des signaux optiques selon des seuils prédéfinis, génère des anomalies et offre un tableau de bord interactif. L'accès est sécurisé et distingue deux rôles : administrateur et technicien.

## Fonctionnalités

- Authentification et gestion des sessions
- Gestion des utilisateurs et des rôles (administrateur / technicien)
- Import de fichiers Excel/CSV (gestion des valeurs manquantes et des doublons)
- Contrôle automatique de qualité selon 5 règles :
  - `OLT_POWER_TX` entre 2 et 7
  - `OLT_RX_ONT_POWER` entre -32 et -12
  - `ONU_POWER_TX` entre 2 et 5
  - `ONU_POWER_RX` entre -28 et -7
  - si `F_SUSP = 1`, alors `ADMIN_STATUS` doit être égal à 0
- Gestion des lignes (consultation, recherche, filtres, CRUD)
- Gestion des anomalies et des interventions (assignation, statuts, commentaires)
- Tableau de bord interactif (Chart.js) par gouvernorat et par carte OLT
- Paramétrage des seuils

### Fonctionnalités complémentaires

- Export CSV / PDF et journal d'activité
- Simulation d'un flux de mesures en quasi temps réel (démonstration)
- Intégration d'un modèle de machine learning de détection d'anomalies exposé par une API REST (optionnel, l'application fonctionne sans)

## Technologies

| Catégorie | Technologies |
|---|---|
| Frontend | HTML5, CSS3, Bootstrap 5, JavaScript (AJAX), Chart.js |
| Backend | PHP 8 (PDO, sessions) |
| Base de données | MySQL 8 |
| Environnement | XAMPP (Apache, PHP, MySQL), phpMyAdmin |
| Versionnement | Git / GitHub |

## Installation

1. Installer [XAMPP](https://www.apachefriends.org/) et démarrer **Apache** et **MySQL**.
2. Copier le dossier du projet dans `htdocs/` (par exemple `htdocs/fibercheck`).
3. Ouvrir phpMyAdmin et importer le script SQL fourni dans le dossier `database/`.
4. Adapter les paramètres de connexion dans le fichier de configuration (`config/`).
5. Ouvrir `http://localhost/fibercheck` dans le navigateur.

## Structure du projet

```
fibercheck/
├── config/        # connexion à la base de données
├── database/      # script SQL
├── includes/      # fonctions communes (sécurité, règles de contrôle)
├── pages/         # pages de l'application
├── assets/        # CSS, JavaScript, images
└── index.php
```

## Équipe

- Chtourou Haitham
- Bahloul Youssef

## Licence

Projet académique.
