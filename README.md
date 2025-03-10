# OrgVizApp - Application de Visualisation de Structures Organisationnelles

OrgVizApp est une application web interactive conçue pour visualiser, gérer et maintenir des structures organisationnelles complexes. Elle remplace les représentations statiques basées sur des fichiers DOT par une interface dynamique et conviviale qui permet aux utilisateurs d'explorer, de modifier et de comprendre facilement des relations organisationnelles complexes.

![Version](https://img.shields.io/badge/version-1.0.0--alpha-blue)
![License](https://img.shields.io/badge/license-MIT-green)

## Table des matières

- [OrgVizApp - Application de Visualisation de Structures Organisationnelles](#orgvizapp---application-de-visualisation-de-structures-organisationnelles)
  - [Table des matières](#table-des-matières)
  - [Aperçu](#aperçu)
  - [Fonctionnalités clés](#fonctionnalités-clés)
    - [Visualisation interactive](#visualisation-interactive)
    - [Vues adaptatives](#vues-adaptatives)
    - [Navigation simplifiée](#navigation-simplifiée)
    - [Documentation intégrée](#documentation-intégrée)
    - [Édition et gestion](#édition-et-gestion)
    - [Exportation et partage](#exportation-et-partage)
  - [Architecture technique](#architecture-technique)
    - [Frontend](#frontend)
    - [Backend](#backend)
    - [Modèle de données](#modèle-de-données)
  - [Installation](#installation)
    - [Prérequis](#prérequis)
    - [Installation locale](#installation-locale)
  - [Utilisation](#utilisation)
  - [Documentation](#documentation)
  - [Feuille de route](#feuille-de-route)
  - [Contribuer](#contribuer)
  - [Licence](#licence)
  - [Contact](#contact)

## Aperçu

Avec l'évolution des organisations modernes, les structures organisationnelles sont devenues de plus en plus complexes. Les représentations statiques traditionnelles ne suffisent plus à capturer et à communiquer efficacement ces structures. OrgVizApp répond à ce défi en offrant une plateforme dynamique et intuitive qui permet de visualiser, d'explorer et de maintenir des structures organisationnelles complexes.

OrgVizApp aide les organisations à :

- Comprendre les relations entre les différents domaines organisationnels
- Analyser les flux d'information, de décision et de ressources
- Maintenir et adapter les structures organisationnelles en fonction de l'évolution des besoins

## Fonctionnalités clés

### Visualisation interactive

- **Zoom et panoramique** - Explorez librement la structure organisationnelle
- **Filtrage** - Affichez uniquement les domaines et relations qui vous intéressent
- **Mise en évidence** - Mettez en évidence des chemins et des relations spécifiques

### Vues adaptatives

- **Vue stratégique** - Concentrez-vous sur les domaines et relations stratégiques
- **Vue opérationnelle** - Examinez les aspects opérationnels de l'organisation
- **Vue des informations** - Visualisez les flux d'information dans l'organisation
- **Vues personnalisées** - Créez et enregistrez vos propres perspectives de l'organisation

### Navigation simplifiée

- **Focus sur un domaine** - Cliquez sur un domaine pour voir uniquement ses connexions directes
- **Exploration contextuelle** - Naviguez dans la structure de manière intuitive
- **Recherche avancée** - Trouvez rapidement des domaines et des relations spécifiques

### Documentation intégrée

- **Informations contextuelles** - Accédez à la documentation de chaque domaine et relation
- **Annotations** - Ajoutez des notes et des commentaires à la structure
- **Historique des versions** - Suivez l'évolution de la structure organisationnelle

### Édition et gestion

- **Interface d'édition intuitive** - Modifiez la structure sans connaissances techniques
- **Gestion des versions** - Conservez l'historique des modifications
- **Collaboration** - Travaillez simultanément sur la structure avec plusieurs utilisateurs

### Exportation et partage

- **Formats multiples** - Exportez en PDF, SVG, PNG et autres formats
- **Partage de liens** - Partagez des vues spécifiques avec d'autres utilisateurs
- **Intégration** - Intégrez les visualisations dans d'autres applications

## Architecture technique

OrgVizApp est construit sur une architecture moderne et évolutive :

### Frontend

- **React** - Pour une interface utilisateur réactive et modulaire
- **D3.js / Cytoscape.js** - Pour des visualisations interactives de graphes
- **Material-UI** - Pour une expérience utilisateur cohérente et élégante

### Backend

- **Node.js** - Pour un serveur performant et scalable
- **Express** - Pour une API RESTful robuste
- **MongoDB** - Pour le stockage flexible des données structurelles

### Modèle de données

- Schéma flexible permettant de représenter des structures organisationnelles complexes
- Support pour les métadonnées, les annotations et les versions
- Optimisé pour les requêtes rapides et les mises à jour en temps réel

## Installation

### Prérequis

- Node.js (v14 ou supérieur)
- npm (v6 ou supérieur)
- MongoDB (v4 ou supérieur)

### Installation locale

1. Cloner le dépôt :

   ```bash
   git clone https://github.com/omar-el-mountassir/OrgVizApp.git
   cd OrgVizApp
   ```

2. Installer les dépendances du backend :

   ```bash
   cd backend
   npm install
   ```

3. Installer les dépendances du frontend :

   ```bash
   cd ../frontend
   npm install
   ```

4. Configurer les variables d'environnement :

   - Créez un fichier `.env` dans le dossier `backend` basé sur le modèle `.env.example`
   - Ajustez les paramètres selon votre environnement local

5. Lancer l'application en mode développement :

   ```bash
   # Dans le dossier backend
   npm run dev

   # Dans un autre terminal, dans le dossier frontend
   npm start
   ```

6. Accéder à l'application :
   Ouvrez votre navigateur et accédez à `http://localhost:3000`

## Utilisation

_Une documentation détaillée sur l'utilisation sera fournie une fois que l'application aura atteint un stade de développement plus avancé._

## Documentation

- [Guide utilisateur](docs/user-guide.md)
- [Documentation API](docs/api.md)
- [Guide du développeur](docs/developer-guide.md)

## Feuille de route

Consultez notre [fichier TODO](TODO.md) pour voir les fonctionnalités prévues et les améliorations à venir.

## Contribuer

Nous accueillons les contributions ! Veuillez consulter notre [guide de contribution](CONTRIBUTING.md) pour plus d'informations.

## Licence

Ce projet est sous licence MIT. Voir le fichier [LICENSE](LICENSE) pour plus de détails.

## Contact

Pour toute question ou suggestion, n'hésitez pas à nous contacter à [contact@email.com](mailto:contact@email.com) ou à ouvrir une issue sur GitHub.
