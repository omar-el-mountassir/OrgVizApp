# User Stories - OrgVizApp

Ce document détaille les user stories et les critères d'acceptation pour OrgVizApp. Ces user stories guideront le développement et aideront à prioriser les fonctionnalités.

## Utilisateurs et rôles

- **Administrateur** : Gère les utilisateurs et a un accès complet à toutes les fonctionnalités
- **Éditeur** : Peut créer, modifier et supprimer des structures organisationnelles
- **Collaborateur** : Peut modifier des structures organisationnelles spécifiques
- **Lecteur** : Peut consulter des structures organisationnelles sans les modifier

## Épic 1 : Gestion des utilisateurs et authentification

### Story 1.1 : Inscription d'un utilisateur

**En tant que** visiteur  
**Je veux** pouvoir créer un compte  
**Afin de** commencer à utiliser l'application

**Critères d'acceptation :**

- Le formulaire d'inscription doit inclure : nom d'utilisateur, email, mot de passe, prénom, nom
- Les mots de passe doivent contenir au moins 8 caractères, incluant lettres, chiffres et caractères spéciaux
- L'email doit être unique dans le système
- Un email de vérification doit être envoyé après l'inscription
- Les termes et conditions doivent être acceptés avant l'inscription

### Story 1.2 : Connexion d'un utilisateur

**En tant qu'** utilisateur inscrit  
**Je veux** pouvoir me connecter à mon compte  
**Afin d'** accéder à mes structures organisationnelles

**Critères d'acceptation :**

- L'utilisateur peut se connecter avec son email et son mot de passe
- Une option "Se souvenir de moi" est disponible
- Une fonctionnalité de mot de passe oublié est fournie
- L'utilisateur est redirigé vers son tableau de bord après la connexion
- Les tentatives de connexion échouées sont limitées pour prévenir les attaques par force brute

### Story 1.3 : Gestion du profil utilisateur

**En tant qu'** utilisateur connecté  
**Je veux** pouvoir gérer mon profil  
**Afin de** mettre à jour mes informations personnelles et mes préférences

**Critères d'acceptation :**

- L'utilisateur peut modifier son prénom, nom, organisation
- L'utilisateur peut changer son mot de passe
- L'utilisateur peut définir des préférences d'interface (thème, langue)
- L'utilisateur peut définir une vue par défaut pour les structures

### Story 1.4 : Gestion des utilisateurs (Admin)

**En tant qu'** administrateur  
**Je veux** gérer les utilisateurs du système  
**Afin de** contrôler les accès et les permissions

**Critères d'acceptation :**

- L'administrateur peut voir la liste de tous les utilisateurs
- L'administrateur peut créer, modifier et désactiver des comptes utilisateurs
- L'administrateur peut attribuer des rôles aux utilisateurs
- L'administrateur peut réinitialiser le mot de passe d'un utilisateur

## Épic 2 : Visualisation de structures organisationnelles

### Story 2.1 : Consultation d'une structure organisationnelle

**En tant qu'** utilisateur connecté  
**Je veux** pouvoir consulter une structure organisationnelle  
**Afin de** comprendre l'organisation et ses relations

**Critères d'acceptation :**

- L'utilisateur voit un graphe interactif représentant la structure organisationnelle
- Les différents types de domaines (stratégique, opérationnel, etc.) sont visuellement distincts
- Les relations entre les domaines sont clairement indiquées
- L'interface est responsive et fonctionne sur desktop et tablette
- Les performances restent acceptables même avec de grandes structures (100+ nœuds)

### Story 2.2 : Navigation interactive dans une structure

**En tant qu'** utilisateur consultant une structure  
**Je veux** pouvoir naviguer interactivement dans le graphe  
**Afin de** explorer efficacement la structure organisationnelle

**Critères d'acceptation :**

- L'utilisateur peut zoomer et dézoomer sur le graphe
- L'utilisateur peut faire glisser le graphe pour naviguer
- L'utilisateur peut cliquer sur un domaine pour le mettre en évidence
- Lorsqu'un domaine est sélectionné, ses connexions directes sont mises en évidence
- Une minimap est disponible pour les grandes structures

### Story 2.3 : Filtrage des éléments d'une structure

**En tant qu'** utilisateur consultant une structure  
**Je veux** pouvoir filtrer les éléments affichés  
**Afin de** me concentrer sur des aspects spécifiques de l'organisation

**Critères d'acceptation :**

- L'utilisateur peut filtrer les domaines par type (stratégique, opérationnel, etc.)
- L'utilisateur peut filtrer les relations par type (hiérarchique, fonctionnel, etc.)
- L'utilisateur peut rechercher des domaines par nom ou code
- Les filtres peuvent être combinés
- L'état des filtres est préservé lors de la navigation entre les pages

### Story 2.4 : Utilisation de vues prédéfinies

**En tant qu'** utilisateur consultant une structure  
**Je veux** pouvoir basculer entre différentes vues prédéfinies  
**Afin de** comprendre différents aspects de l'organisation

**Critères d'acceptation :**

- L'utilisateur peut basculer entre des vues prédéfinies (stratégique, opérationnelle, information)
- Chaque vue montre un sous-ensemble pertinent de la structure
- Le changement de vue est instantané et fluide
- Les vues prédéfinies ont des descriptions explicatives

### Story 2.5 : Accès à la documentation contextuelle

**En tant qu'** utilisateur consultant une structure  
**Je veux** pouvoir accéder à la documentation des domaines et relations  
**Afin de** comprendre leur rôle et leur fonction

**Critères d'acceptation :**

- L'utilisateur peut cliquer sur un domaine pour voir sa documentation détaillée
- L'utilisateur peut cliquer sur une relation pour voir sa description
- La documentation s'affiche dans un panel latéral ou une modal
- La documentation peut inclure du texte formaté, des listes et des tableaux
- L'utilisateur peut fermer la documentation et revenir facilement au graphe

## Épic 3 : Création et modification de structures

### Story 3.1 : Création d'une nouvelle structure organisationnelle

**En tant qu'** éditeur  
**Je veux** créer une nouvelle structure organisationnelle  
**Afin de** modéliser une organisation

**Critères d'acceptation :**

- L'éditeur peut créer une structure vide ou partir d'un modèle
- L'éditeur fournit un nom, une description et des métadonnées pour la structure
- L'éditeur peut définir les permissions d'accès à la structure
- La nouvelle structure est immédiatement disponible pour édition

### Story 3.2 : Ajout et modification de domaines

**En tant qu'** éditeur ou collaborateur  
**Je veux** ajouter et modifier des domaines dans une structure  
**Afin de** construire le modèle organisationnel

**Critères d'acceptation :**

- L'utilisateur peut ajouter un nouveau domaine via un formulaire
- L'utilisateur peut définir le type, le code, le nom et la description du domaine
- L'utilisateur peut personnaliser l'apparence du domaine (couleur, forme, icône)
- L'utilisateur peut déplacer les domaines sur le graphe par glisser-déposer
- L'utilisateur peut modifier ou supprimer un domaine existant

### Story 3.3 : Création et modification de relations

**En tant qu'** éditeur ou collaborateur  
**Je veux** créer et modifier des relations entre domaines  
**Afin de** définir les interactions organisationnelles

**Critères d'acceptation :**

- L'utilisateur peut créer une relation en connectant deux domaines
- L'utilisateur peut définir le type, le label et la description de la relation
- L'utilisateur peut personnaliser l'apparence de la relation (couleur, style de ligne)
- L'utilisateur peut modifier ou supprimer une relation existante
- Le système prévient la création de relations cycliques inappropriées

### Story 3.4 : Création de vues personnalisées

**En tant qu'** éditeur ou collaborateur  
**Je veux** créer des vues personnalisées d'une structure  
**Afin de** mettre en évidence des aspects spécifiques pour différents publics

**Critères d'acceptation :**

- L'utilisateur peut créer une nouvelle vue à partir de l'état actuel du graphe
- L'utilisateur peut nommer et décrire la vue
- L'utilisateur peut définir les filtres associés à la vue
- L'utilisateur peut enregistrer la position des domaines et le niveau de zoom
- L'utilisateur peut marquer certains domaines comme mis en évidence dans la vue

### Story 3.5 : Gestion des versions

**En tant qu'** éditeur  
**Je veux** gérer différentes versions d'une structure organisationnelle  
**Afin de** suivre son évolution ou explorer différentes options

**Critères d'acceptation :**

- L'utilisateur peut créer une nouvelle version à partir de la version actuelle
- L'utilisateur peut basculer entre les différentes versions
- L'utilisateur peut voir un historique des versions avec dates et descriptions
- L'utilisateur peut comparer deux versions pour voir les différences
- L'utilisateur peut fusionner des modifications de différentes versions

## Épic 4 : Importation, exportation et partage

### Story 4.1 : Importation depuis un fichier DOT

**En tant qu'** éditeur  
**Je veux** importer une structure à partir d'un fichier DOT existant  
**Afin de** convertir des structures statiques en structures interactives

**Critères d'acceptation :**

- L'utilisateur peut téléverser un fichier DOT
- Le système analyse le fichier et crée une structure correspondante
- Le système préserve les styles et attributs définis dans le fichier DOT
- L'utilisateur est averti des éventuels problèmes de conversion
- L'utilisateur peut ajuster la structure importée après l'importation

### Story 4.2 : Exportation dans différents formats

**En tant qu'** utilisateur consultant une structure  
**Je veux** exporter la structure dans différents formats  
**Afin de** l'utiliser dans d'autres contextes ou documents

**Critères d'acceptation :**

- L'utilisateur peut exporter la structure en PDF, SVG, PNG
- L'utilisateur peut exporter la structure au format DOT
- L'utilisateur peut exporter les données au format JSON
- L'exportation reflète l'état actuel du graphe (filtres, zoom, mise en évidence)
- L'utilisateur peut choisir des options d'exportation (taille, qualité, etc.)

### Story 4.3 : Partage de vues avec d'autres utilisateurs

**En tant qu'** utilisateur  
**Je veux** partager une vue spécifique avec d'autres utilisateurs  
**Afin de** collaborer sur la compréhension de la structure

**Critères d'acceptation :**

- L'utilisateur peut générer un lien de partage pour une vue spécifique
- L'utilisateur peut définir si le lien est accessible à tous ou uniquement aux utilisateurs autorisés
- L'utilisateur peut définir une date d'expiration pour le lien
- Les utilisateurs recevant le lien voient exactement la même vue (filtres, zoom, mise en évidence)
- Les utilisateurs ayant les permissions adéquates peuvent modifier la structure partagée

### Story 4.4 : Collaboration en temps réel

**En tant que** collaborateur  
**Je veux** travailler simultanément avec d'autres utilisateurs sur une structure  
**Afin de** collaborer efficacement sur la modélisation

**Critères d'acceptation :**

- Plusieurs utilisateurs peuvent modifier une structure simultanément
- Les modifications d'un utilisateur sont visibles en temps réel par les autres
- Le système gère les conflits de modification
- Les utilisateurs voient qui est actuellement en train de modifier la structure
- Les utilisateurs peuvent communiquer via un chat intégré

## Épic 5 : Administration et reporting

### Story 5.1 : Tableau de bord des structures

**En tant qu'** utilisateur  
**Je veux** voir un tableau de bord des structures auxquelles j'ai accès  
**Afin de** gérer facilement mes structures organisationnelles

**Critères d'acceptation :**

- L'utilisateur voit une liste des structures auxquelles il a accès
- Pour chaque structure, l'utilisateur voit le nom, la description, la dernière modification
- L'utilisateur peut filtrer et trier les structures
- L'utilisateur peut rapidement créer, ouvrir, dupliquer ou supprimer des structures
- Des statistiques de base sont affichées pour chaque structure (nombre de domaines, relations)

### Story 5.2 : Monitoring de l'application (Admin)

**En tant qu'** administrateur  
**Je veux** surveiller l'utilisation de l'application  
**Afin de** gérer les ressources et résoudre les problèmes

**Critères d'acceptation :**

- L'administrateur voit des statistiques d'utilisation (utilisateurs actifs, structures créées, etc.)
- L'administrateur voit les journaux d'erreurs et peut les filtrer
- L'administrateur peut identifier les goulots d'étranglement de performance
- L'administrateur reçoit des alertes en cas de problèmes critiques
- L'administrateur peut voir les ressources système utilisées

### Story 5.3 : Génération de rapports

**En tant qu'** utilisateur  
**Je veux** générer des rapports sur les structures organisationnelles  
**Afin d'** analyser et de communiquer sur l'organisation

**Critères d'acceptation :**

- L'utilisateur peut générer des rapports prédéfinis (résumé, détaillé, etc.)
- L'utilisateur peut personnaliser les rapports (sections à inclure, niveau de détail)
- Les rapports incluent des visualisations et des données textuelles
- Les rapports peuvent être exportés en PDF, DOCX ou HTML
- L'utilisateur peut programmer la génération régulière de rapports
