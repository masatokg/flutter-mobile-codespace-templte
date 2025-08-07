
# Flutter Firebase DevContainer Codespaces Template

This repository contains a Flutter project configured with Firebase and Android SDK support inside a VS Code Dev Container.
It is designed to work seamlessly with GitHub Codespaces.

## Usage

- Open this repository in GitHub Codespaces.
- Codespaces will build the Dev Container automatically.
- Run the following commands inside the container terminal:

```bash
flutter pub get
firebase login
firebase init
flutter run -d chrome  # for web testing
flutter build apk      # to build Android APK
```

## Notes

- Android Emulator cannot run inside Codespaces. Use a physical device or local emulator.
- Configure Firebase using the Firebase CLI (`firebase init`).
- Add Firebase configuration files (`firebase_options.dart`) as needed.
