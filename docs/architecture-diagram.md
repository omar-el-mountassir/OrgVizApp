# Architecture de OrgVizApp

Ce document présente l'architecture globale de OrgVizApp avec un diagramme visuel et une description des différents composants.

## Diagramme d'architecture

```
┌────────────────────────────────────────────────────────────────────────────────┐
│                                   CLIENT                                        │
│                                                                                │
│  ┌─────────────────┐  ┌─────────────────┐  ┌─────────────────────────────────┐ │
│  │                 │  │                 │  │                                 │ │
│  │  Composants UI  │  │  Visualisation  │  │  Gestion d'état               │ │
│  │                 │  │                 │  │                                 │ │
│  │  - Pages        │  │  - D3.js ou     │  │  - Redux Store                 │ │
│  │  - Layouts      │  │    Cytoscape.js │  │  - Actions                     │ │
│  │  - Material-UI  │  │  - Renderers    │  │  - Reducers                    │ │
│  │  - Formulaires  │  │  - Interactions │  │  - Middleware                  │ │
│  │                 │  │                 │  │                                 │ │
│  └─────────────────┘  └─────────────────┘  └─────────────────────────────────┘ │
│                                                                                │
│  ┌─────────────────────────────────────────────────────────────────────────────┐│
│  │                                Services                                     ││
│  │                                                                             ││
│  │  - API Client                                                               ││
│  │  - Authentification                                                         ││
│  │  - Gestion de cache                                                         ││
│  │  - Utilitaires                                                              ││
│  └─────────────────────────────────────────────────────────────────────────────┘│
└────────────────────────────────────────────────────────────────────────────────┘
                                      │
                                      │ HTTP/HTTPS
                                      ▼
┌────────────────────────────────────────────────────────────────────────────────┐
│                                   SERVEUR                                       │
│                                                                                │
│  ┌─────────────────┐  ┌─────────────────┐  ┌─────────────────────────────────┐ │
│  │                 │  │                 │  │                                 │ │
│  │  API RESTful    │  │  Services       │  │  Utilitaires                   │ │
│  │                 │  │                 │  │                                 │ │
│  │  - Routes       │  │  - Structures   │  │  - Exportation                 │ │
│  │  - Contrôleurs  │  │  - Utilisateurs │  │  - Parser DOT                  │ │
│  │  - Middleware   │  │  - Vues         │  │  - Générateur de rapports      │ │
│  │  - Validation   │  │  - Versions     │  │  - Logger                      │ │
│  │                 │  │                 │  │                                 │ │
│  └─────────────────┘  └─────────────────┘  └─────────────────────────────────┘ │
│                                                                                │
│  ┌─────────────────────────────────────────────────────────────────────────────┐│
│  │                              Base de données                                ││
│  │                                                                             ││
│  │  - Modèles                                                                  ││
│  │  - Schémas                                                                  ││
│  │  - Migrations                                                               ││
│  │  - Requêtes                                                                 ││
│  └─────────────────────────────────────────────────────────────────────────────┘│
└────────────────────────────────────────────────────────────────────────────────┘
                                      │
                                      │
                                      ▼
┌────────────────────────────────────────────────────────────────────────────────┐
│                                 STOCKAGE                                        │
│                                                                                │
│  ┌─────────────────────────┐      ┌─────────────────────────────────────────┐  │
│  │                         │      │                                         │  │
│  │     MongoDB             │      │               Redis (optionnel)         │  │
│  │                         │      │                                         │  │
│  │  - Structures           │      │  - Cache                                │  │
│  │  - Nœuds                │      │  - Sessions                             │  │
│  │  - Relations            │      │  - Pub/Sub (collaboration en temps réel)│  │
│  │  - Utilisateurs         │      │                                         │  │
│  │  - Vues                 │      │                                         │  │
│  │  - Versions             │      │                                         │  │
│  └─────────────────────────┘      └─────────────────────────────────────────┘  │
│                                                                                │
└────────────────────────────────────────────────────────────────────────────────┘
```

## Description des composants

### Client (Frontend)

#### Composants UI

- **Pages** : Toutes les pages de l'application (tableau de bord, éditeur, visualisateur, etc.)
- **Layouts** : Structures de base des pages (en-tête, pied de page, barres latérales)
- **Material-UI** : Composants UI réutilisables pour une expérience cohérente
- **Formulaires** : Composants pour la saisie de données (création de structures, édition de domaines, etc.)

#### Visualisation

- **D3.js/Cytoscape.js** : Bibliothèque de visualisation pour le rendu des graphes
- **Renderers** : Composants pour le rendu des différents éléments du graphe (nœuds, arêtes)
- **Interactions** : Gestion des interactions utilisateur (zoom, pan, sélection, etc.)

#### Gestion d'état

- **Redux Store** : Stockage centralisé pour l'état de l'application
- **Actions** : Définition des actions possibles sur les données
- **Reducers** : Logique de mise à jour de l'état
- **Middleware** : Traitements intermédiaires (API calls, logging, etc.)

#### Services

- **API Client** : Communication avec le backend
- **Authentification** : Gestion des sessions utilisateur
- **Gestion de cache** : Mise en cache des données pour optimiser les performances
- **Utilitaires** : Fonctions utilitaires réutilisables

### Serveur (Backend)

#### API RESTful

- **Routes** : Définition des endpoints de l'API
- **Contrôleurs** : Traitement des requêtes et réponses
- **Middleware** : Traitement intermédiaire (authentification, validation, logging)
- **Validation** : Validation des données entrantes

#### Services

- **Structures** : Gestion des structures organisationnelles
- **Utilisateurs** : Gestion des utilisateurs et des permissions
- **Vues** : Gestion des vues personnalisées
- **Versions** : Gestion des versions des structures

#### Utilitaires

- **Exportation** : Génération de fichiers dans différents formats (PDF, SVG, PNG)
- **Parser DOT** : Analyse et conversion de fichiers DOT
- **Générateur de rapports** : Création de rapports sur les structures
- **Logger** : Journalisation des événements et des erreurs

#### Base de données

- **Modèles** : Définition des modèles de données
- **Schémas** : Structure des données
- **Migrations** : Gestion des changements de schéma
- **Requêtes** : Fonctions pour l'accès aux données

### Stockage

#### MongoDB

- Base de données principale pour toutes les données de l'application
- Collections pour les structures, nœuds, relations, utilisateurs, vues, versions

#### Redis (optionnel)

- Cache pour améliorer les performances
- Stockage des sessions utilisateur
- Système pub/sub pour la collaboration en temps réel
