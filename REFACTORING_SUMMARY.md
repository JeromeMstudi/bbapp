# 🏀 BBApp - Refactorisation Clean Architecture

## 📋 Résumé de la refactorisation

Cette refactorisation transforme l'application existante pour suivre les principes de Clean Architecture et les règles définies dans `@/rules`.

## 🏗️ Nouvelle structure

### Architecture en couches
```
lib/
├── core/                    # Utilitaires partagés
│   ├── constants/          # Constantes et strings
│   ├── errors/             # Classes d'erreur personnalisées
│   ├── usecases/           # Interface UseCase de base
│   ├── router/             # Configuration Autoroute
│   └── di/                 # Injection de dépendances
├── features/               # Modules par fonctionnalité
│   └── games/
│       ├── data/           # Couche données
│       │   ├── datasources/  # Sources de données (API, cache)
│       │   ├── models/       # Modèles de données
│       │   └── repositories/ # Implémentations repository
│       ├── domain/         # Couche métier
│       │   ├── entities/     # Entités métier
│       │   ├── repositories/ # Interfaces repository
│       │   └── usecases/     # Cas d'usage
│       └── presentation/   # Couche présentation
│           ├── bloc/         # Gestion d'état BLoC
│           ├── pages/        # Pages de l'app
│           └── widgets/      # Widgets spécifiques
└── shared/                 # Composants partagés
    └── widgets/            # Widgets réutilisables
```

## 🔄 Changements majeurs

### 1. Navigation : GoRouter → Autoroute
- ✅ Migration vers `auto_route` pour navigation type-safe
- ✅ Routes générées automatiquement 
- ✅ Configuration centralisée dans `AppRouter`
- ✅ Support des routes imbriquées

### 2. Gestion d'état : Provider → BLoC
- ✅ Migration vers `flutter_bloc` 
- ✅ États avec sealed classes pour type safety
- ✅ Séparation claire des événements et états
- ✅ Pattern Either<Failure, Success> pour gestion d'erreur

### 3. Injection de dépendances
- ✅ `get_it` + `injectable` pour DI
- ✅ Configuration centralisée des dépendances
- ✅ Découplage des couches

### 4. Couches Clean Architecture
- ✅ **Domain Layer** : Entités, repositories interfaces, use cases
- ✅ **Data Layer** : Modèles, data sources, repository implementations  
- ✅ **Presentation Layer** : Pages, widgets, BLoC

### 5. Amélioration code quality
- ✅ Constantes centralisées (couleurs, strings)
- ✅ Classes d'erreur personnalisées avec Failure pattern
- ✅ Widgets réutilisables (LoadingWidget, ErrorWidget)
- ✅ Respect des conventions de nommage Dart

## 🚀 Utilisation

```bash
# Générer les routes et DI
flutter packages pub run build_runner build

# Lancer l'app
flutter run
```

## 📋 Commandes utiles

```bash
# Nettoyer et regénérer
flutter packages pub run build_runner build --delete-conflicting-outputs

# Tests
flutter test

# Analyse statique
flutter analyze
```