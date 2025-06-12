# BBApp - Flutter Basketball App

Application Flutter pour suivre la BETCLIC ELITE league et l'équipe AS Monaco.

## Architecture

Cette application suit les principes de Clean Architecture avec :

- **Domain Layer** : Entités métier, repositories interfaces, use cases
- **Data Layer** : Modèles de données, sources de données, implémentations repository
- **Presentation Layer** : Pages, widgets, gestion d'état BLoC

## Fonctionnalités

- 🏀 Suivi des matchs de la BETCLIC ELITE
- 📊 Classements et statistiques
- 🏆 Focus sur l'AS Monaco
- 📱 Interface moderne et responsive

## Technologies

- **Flutter** : Framework UI
- **BLoC** : Gestion d'état
- **auto_route** : Navigation type-safe
- **get_it + injectable** : Injection de dépendances
- **dio** : Client HTTP
- **dartz** : Programmation fonctionnelle

## Démarrage

```bash
# Installer les dépendances
flutter pub get

# Générer le code auto_route et injection
flutter packages pub run build_runner build

# Lancer l'application
flutter run
```

## Tests

```bash
# Lancer tous les tests
flutter test
```