# app
[![CI](https://github.com/eugeniopunti/ecuapp/workflows/CI/badge.svg)](https://github.com/eugeniopunti/ecuapp/actions)

# ECUApp

## Descripción

Aplicación Flutter multiplataforma para monitoreo en tiempo real de una ECU embebida via Bluetooth (Classic & BLE). Permite visualizar datos como RPM, AFR, MAP y TPS con gauges y gráficos. 

## Arquitectura del proyecto

```
/ecuapp
├── android/        # Módulo Android
├── ios/            # Módulo iOS
├── linux/          # Soporte Linux
├── macos/          # Soporte macOS
├── windows/        # Soporte Windows
├── web/            # Soporte Web (opcional)
├── assets/         # Recursos estáticos
│   ├── fonts/
│   ├── images/
│   └── locales/
├── lib/            # Código Dart
│   ├── main.dart   # Punto de entrada
│   ├── app.dart    # Configuración MaterialApp, Theme y rutas
│   ├── models/     # Clases de datos (p.ej. EcuData)
│   ├── services/   # Lógica de hardware y storage (DeviceService, StorageService)
│   ├── providers/  # State management (Riverpod/Provider)
│   └── ui/
│       ├── widgets/ # Widgets reutilizables (gauges, tablas)
│       └── pages/   # Pantallas (Connection, Monitoring, Mapping, Calibration)
├── test/           # Unit & widget tests
└── integration_test/ # Tests end-to-end
```

## Prerrequisitos

* Flutter 3.22 en canal **stable**
* Android SDK (API ≥ 33)
* Xcode (para iOS)
* Visual Studio (para Windows desktop)
* GTK Dev (para Linux desktop)

## Comandos básicos

```bash
# Instalar dependencias
flutter pub get

# Ejecutar en Android Emulator o dispositivo
flutter run -d android

# Ejecutar en iOS Simulator
flutter run -d ios

# Ejecutar en escritorio (Windows/macOS/Linux)
flutter run -d windows     # o macos/linux según plataforma

# Compilar release Android
flutter build apk --release

# Compilar release desktop
flutter build windows --release
flutter build macos --release
flutter build linux --release
```

## Convenciones de código

* **Formateo**: usa `dart format .` antes de commitear.
* **Análisis estático**: corre `flutter analyze` y corrige warnings.
* **Naming**:

  * Ficheros y carpetas: snake\_case (`connection_page.dart`)
  * Clases y enums: PascalCase (`ConnectionPage`)
  * Variables y métodos: camelCase (`deviceService`)
* **Commits**: sigue convención **Conventional Commits**:

  * `feat:`, `fix:`, `chore:`, `docs:`, `refactor:`
  * Ejemplo: `feat: add monitoring gauges`
* **Ramas**:

  * `main` (producción)
  * `develop` (integración)
  * `feature/<nombre-descriptivo>`

## Enlaces útiles

* [Documentación Flutter](https://docs.flutter.dev)
* [Syncfusion Gauges](https://pub.dev/packages/syncfusion_flutter_gauges)
* [fl\_chart](https://pub.dev/packages/fl_chart)
