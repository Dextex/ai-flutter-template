# Flutter UI Rules

## Material Design First (PFLICHT)
- Vor dem Erstellen eines UI-Elements immer prüfen ob Material Design es bereits hat
- NIEMALS custom Implementierungen erstellen für: Button, TextField, Checkbox, Switch, Dialog, AlertDialog, SnackBar, Card, Badge, DropdownButton, Tooltip, NavigationBar, Drawer, AppBar
- Custom Widgets NUR für business-spezifische Kompositionen die intern Material-Primitives nutzen

## Import Pattern
```dart
import 'package:flutter/material.dart';
import 'package:flutter_bloc/flutter_bloc.dart';
```

## Widget Standards
- `const` Konstruktoren wo immer möglich (Performance)
- Alle Screens müssen verschiedene Größen unterstützen (360px, 390px, 412px Breite)
- Lade-Zustände, Fehler-Zustände und leere Zustände implementieren
- Semantics Widget für Accessibility verwenden wo nötig
- Widgets klein und fokussiert halten (Single Responsibility)
- Typen immer angeben — kein `var` für Widget-Properties

## BLoC Standards
- KEIN Business Logic in Widgets — gehört in BLoC
- Events für alle Nutzeraktionen definieren
- States für alle möglichen Zustände definieren (laden, geladen, fehler)
- BlocProvider so nah wie möglich am Widget das ihn braucht

## Ordnerstruktur pro Feature
```
lib/features/feature_name/
├── bloc/
│   ├── feature_bloc.dart
│   ├── feature_event.dart
│   └── feature_state.dart
├── screens/
│   └── feature_screen.dart
└── widgets/
    └── feature_widget.dart
```

## Dateibenennung
- Dart-Dateien: `snake_case.dart`
- Klassen: `PascalCase`
- Variablen & Methoden: `camelCase`
- Keine Leerzeichen oder Sonderzeichen in Dateinamen

## Styling
- Theme-Farben verwenden: `Theme.of(context).colorScheme.primary`
- Keine hardcodierten Hex-Farben
- Text-Styles aus Theme: `Theme.of(context).textTheme.titleLarge`
- ThemeData zentral in `main.dart` definieren