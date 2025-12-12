# Lomé-Tokoin I.A. - Application Mobile Aéroportuaire

<div align="center">

**Application mobile pour l'Aéroport International Gnassingbé Eyadéma (AIGE) de Lomé**

*Vous accueillir autrement*

[![Flutter](https://img.shields.io/badge/Flutter-3.5.4-02569B?logo=flutter)](https://flutter.dev/)
[![Dart](https://img.shields.io/badge/Dart-3.5.4-0175C2?logo=dart)](https://dart.dev/)
[![Firebase](https://img.shields.io/badge/Firebase-Enabled-FFCA28?logo=firebase)](https://firebase.google.com/)

</div>

---

## Table des matières

- [Vue d'ensemble](#vue-densemble)
- [Contexte de l'aviation civile](#contexte-de-laviation-civile)
- [Fonctionnalités principales](#fonctionnalités-principales)
- [Architecture technique](#architecture-technique)
- [Prérequis](#prérequis)
- [Installation](#installation)
- [Structure du projet](#structure-du-projet)
- [Faisabilité et conformité](#faisabilité-et-conformité)
- [Contributions](#contributions)
- [Licence](#licence)

---

## Vue d'ensemble

**Lomé-Tokoin I.A.** est une application mobile développée avec Flutter pour améliorer l'expérience des passagers et optimiser la gestion opérationnelle de l'Aéroport International Gnassingbé Eyadéma (AIGE) de Lomé, Togo.

L'application répond aux besoins spécifiques du secteur aéronautique en offrant :
- Une communication efficace avec les passagers
- Un système de signalement et de gestion des incidents
- Un assistant virtuel intelligent pour l'information aéroportuaire
- Une plateforme de diffusion d'informations en temps réel

### Informations clés

- **Aéroport** : Aéroport International Gnassingbé Eyadéma (AIGE)
- **Code IATA** : LFW
- **Localisation** : Lomé, Togo
- **Capacité** : 2 millions de passagers/an
- **Organisation** : Global Flight Solutions

---

## Contexte de l'aviation civile

### Pertinence pour le secteur aéronautique

Cette application s'inscrit dans la modernisation des infrastructures aéroportuaires africaines et répond à plusieurs enjeux critiques du secteur :

#### 1. **Amélioration de l'expérience passager**
- Réduction des temps d'attente grâce à l'information en temps réel
- Accès facilité aux services aéroportuaires (Wi-Fi, boutiques, restaurants, salons VIP)
- Communication proactive sur les promotions et événements

#### 2. **Gestion opérationnelle optimisée**
- Système de signalement structuré permettant une réponse rapide aux incidents
- Traçabilité complète des alertes (création, traitement, résolution)
- Support pour les signalements anonymes ou identifiés

#### 3. **Conformité réglementaire**
- Respect des standards de sécurité aéroportuaire
- Gestion sécurisée des données personnelles
- Traçabilité des interactions pour audits

#### 4. **Réduction des coûts opérationnels**
- Diminution de la charge sur les guichets physiques
- Automatisation des réponses aux questions fréquentes
- Optimisation de l'allocation des ressources humaines

### Infrastructure cible

L'AIGE dispose de :
- Terminal passagers de 21 000 m²
- Piste de 3 000 mètres (gros porteurs)
- 8 passerelles télescopiques
- Zone de fret de 50 000 tonnes
- Services : Wi-Fi gratuit, boutiques duty-free, restaurants, salons VIP

---

## Fonctionnalités principales

### 1. **Système de signalement d'alertes**
- Création d'alertes avec types personnalisables
- Support des signalements anonymes ou identifiés
- Géolocalisation optionnelle des incidents
- Ajout de photos et commentaires
- Suivi en temps réel du statut (créé → en traitement → résolu/annulé)
- Historique des signalements par utilisateur

**États des alertes** :
- `created` : Alerte créée, en attente de traitement
- `processing` : Alerte prise en charge par un administrateur
- `terminated` : Alerte résolue
- `aborted` : Alerte annulée

### 2. **Assistant virtuel intelligent (Bot)**
- Chatbot basé sur **Google Gemini 2.5 Flash**
- Réponses spécialisées sur :
  - Procédures administratives (douanes, immigration, visas)
  - Informations de voyage (vols, bagages, services)
  - Services aéroportuaires disponibles
- Restrictions strictes pour garantir la précision des informations
- Interface conversationnelle intuitive

### 3. **Centre de publications**
- Diffusion d'annonces officielles
- Promotions et offres spéciales
- Informations sur les services (Wi-Fi, boutiques, restaurants)
- Support d'images et de liens externes
- Affichage chronologique avec pagination

### 4. **Gestion des comptes utilisateurs**
- Authentification sécurisée (Firebase Auth)
- Connexion via email/mot de passe
- Connexion avec Google Sign-In
- Récupération de mot de passe
- Profils utilisateurs personnalisables

### 5. **Widget météorologique**
- Affichage des conditions météo en temps réel
- Informations pertinentes pour les passagers

### 6. **Système de commentaires**
- Commentaires sur les publications
- Interactions sociales entre utilisateurs
- Modération possible par les administrateurs

### 7. **Thème adaptatif**
- Mode clair et mode sombre
- Préférences sauvegardées localement
- Interface moderne et accessible

---

## Architecture technique

### Stack technologique

- **Framework** : Flutter 3.5.4
- **Langage** : Dart 3.5.4
- **Backend** : Firebase
  - Authentication
  - Cloud Firestore (base de données NoSQL)
  - Cloud Messaging (notifications push)
  - Analytics
  - AI (Gemini)

### Dépendances principales

```yaml
# Authentification & Backend
firebase_core
firebase_auth
cloud_firestore
firebase_messaging
firebase_analytics
firebase_ai

# UI & Navigation
provider (state management)
heroicons (icônes)
flutter_animate (animations)
wolt_modal_sheet (modales)

# Utilitaires
shared_preferences (stockage local)
http (requêtes HTTP)
cached_network_image (cache d'images)
flutter_local_notifications (notifications locales)
intl (internationalisation)
```

### Architecture du code

```
lib/
├── base/              # Classes de base (notifier, processor, validator)
├── builders/          # Builders pour app, forms, themes, pages
├── constants/          # Constantes (couleurs, textes, UI)
├── dialogs/            # Dialogues réutilisables
├── models/             # Modèles de données
├── providers/          # State management (Provider)
├── tools/              # Utilitaires (routes, parser, checker)
├── views/              # Écrans de l'application
├── widgets/            # Widgets réutilisables
└── main.dart          # Point d'entrée
```

---

## Prérequis

### Outils de développement

- **Flutter SDK** : Version 3.5.4 ou supérieure
- **Dart SDK** : Version 3.5.4 ou supérieure
- **Android Studio** ou **VS Code** avec extensions Flutter/Dart
- **Git** pour le contrôle de version

### Comptes et services

- **Compte Firebase** avec projet configuré
- **Google Cloud Platform** (pour Firebase AI/Gemini)
- **Android SDK** (pour le développement Android)
- **Xcode** (pour le développement iOS, macOS uniquement)

### Configuration système

- **Android** : API 21 (Android 5.0) minimum
- **iOS** : iOS 12.0 minimum
- Connexion Internet pour les services Firebase

---

## Installation

### 1. Cloner le dépôt

```bash
git clone https://github.com/MonkeyLuffy9745/LTIA-2
cd src
```

### 2. Installer les dépendances Flutter

```bash
flutter pub get
```

### 3. Vérifier la configuration Flutter

```bash
flutter doctor
```

Assurez-vous que tous les composants sont correctement configurés.

### 4. Lancement

Connectez un appareil mobile et lancer les commandes suivantes:

```bash
flutter build apk --release --obfuscate --split-debug-info=debug_info/
flutter install
```

## Structure Firestore

Les collections principales sont :
- `alerts` : Signalements d'incidents
- `alert_types` : Types d'alertes configurables
- `publications` : Annonces et communications
- `accounts` : Comptes utilisateurs
- `tasks` : Tâches et activités
- `entries` : Entrées de suivi
- `sessions` : Sessions utilisateur

---

### Première utilisation

1. **Lancement** : L'application démarre sur l'écran de splash
2. **Onboarding** : Suivez le guide de première utilisation
3. **Authentification** : Créez un compte ou connectez-vous
4. **Accueil** : Explorez les fonctionnalités depuis l'écran d'accueil

### Utilisation des fonctionnalités

#### Signaler un problème
1. Accédez à l'écran d'accueil
2. Cliquez sur "Signaler un problème"
3. Sélectionnez le type d'alerte
4. Remplissez le formulaire (description, photos optionnelles, localisation)
5. Soumettez l'alerte

#### Consulter l'assistant virtuel
1. Cliquez sur "Parler au Bot" depuis l'accueil
2. Posez vos questions sur l'aéroport
3. Recevez des réponses instantanées

#### Consulter les publications
1. Accédez à l'onglet "Publications"
2. Parcourez les annonces et promotions
3. Cliquez pour voir les détails
4. Ajoutez des commentaires si connecté

---

## Structure du projet

```
ltia/
├── android/              # Configuration Android
├── ios/                  # Configuration iOS
├── lib/                  # Code source Dart/Flutter
│   ├── base/            # Classes de base
│   ├── builders/        # Builders (app, forms, themes)
│   ├── constants/       # Constantes
│   ├── dialogs/         # Dialogues
│   ├── models/          # Modèles de données
│   ├── providers/       # State management
│   ├── tools/           # Utilitaires
│   ├── views/           # Écrans
│   ├── widgets/         # Widgets réutilisables
│   └── main.dart        # Point d'entrée
├── assets/              # Ressources (images, fonts)
├── test/                # Tests unitaires
├── pubspec.yaml         # Dépendances et configuration
└── README.md           # Ce fichier
```

---

## Faisabilité et conformité

### Faisabilité technique

**Architecture solide**
- Utilisation de technologies éprouvées (Flutter, Firebase)
- Architecture modulaire et maintenable
- Séparation claire des responsabilités

**Scalabilité**
- Backend Firebase gère automatiquement la montée en charge
- Structure de données optimisée pour les performances
- Pagination implémentée pour les grandes listes

**Maintenabilité**
- Code organisé et documenté
- Utilisation de patterns Flutter recommandés
- Tests unitaires possibles (structure en place)

### Conformité aviation civile

**Sécurité des données**
- Authentification sécurisée via Firebase Auth
- Chiffrement des données en transit et au repos
- Gestion des permissions granulaires

**Traçabilité**
- Historique complet des alertes
- Timestamps sur toutes les actions
- Logs d'audit disponibles via Firebase

**Accessibilité**
- Interface utilisateur intuitive
- Support du mode sombre pour le confort visuel
- Design responsive adapté aux différentes tailles d'écran

**Performance**
- Chargement optimisé des images (cache)
- Requêtes Firestore optimisées avec indexation
- Notifications push pour les mises à jour importantes

### Points d'attention pour la production

**Sécurité**
- Revoir et renforcer les règles Firestore selon les besoins réels
- Implémenter une validation côté serveur (Cloud Functions)
- Ajouter un système de modération pour les contenus utilisateur

**Performance**
- Optimiser les requêtes Firestore avec des index appropriés
- Implémenter un système de cache local pour les données fréquentes
- Surveiller l'utilisation des quotas Firebase

**Conformité légale**
- Respect du RGPD pour les données personnelles
- Politique de confidentialité et conditions d'utilisation
- Gestion du consentement utilisateur

---

### Standards de code

- Suivez les conventions Dart/Flutter
- Documentez le code complexe
- Écrivez des tests pour les nouvelles fonctionnalités
- Respectez la structure existante du projet

---

## Licence

Ce projet est développé pour **Global Flight Solutions** dans le cadre de la gestion de l'Aéroport International Gnassingbé Eyadéma de Lomé.

Tous droits réservés.

---

## Contact et support

### Informations aéroport

- **Aéroport** : Aéroport International Gnassingbé Eyadéma (AIGE)
- **Code IATA** : LFW
- **Localisation** : Lomé, Togo
- **Téléphone** : +228 22 26 60 00
- **Site web** : https://www.aeroportdelome.com/

### Support technique

Pour toute question technique ou problème, veuillez contacter l'équipe de développement.

---

<div align="center">

**Développé pour améliorer l'expérience aéroportuaire**

*Lomé-Tokoin I.A. - Vous accueillir autrement*

</div>

