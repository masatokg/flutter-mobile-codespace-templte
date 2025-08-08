
# Flutter Firebase DevContainer Codespaces Template

This repository contains a Flutter project configured with Firebase and Android SDK support inside a VS Code Dev Container.
It is designed to work seamlessly with GitHub Codespaces.<br>
このリポジトリには、VS Code 開発環境内の Firebase および Android SDK サポートで構成された Flutter プロジェクトが含まれています。 ローカルはもちろん、GitHub codespacesとスムーズに連携するように設計されています。

## Usage

- Open this repository in GitHub Codespaces.
- Codespaces will build the Dev Container automatically.
- Run the following commands inside the container terminal:<br><br>

- このリポジトリを GitHub コードスペースで開きます。
- コードスペースは開発コンテナを自動的に構築します。
- コンテナターミナル内で次のコマンドを実行します。

```bash
flutter pub get # 依存関係にあるパッケージをインストール
firebase login # firebaseプロジェクトにアクセス
firebase init # firebaseプロジェクトにアクセス
flutter run -d chrome  # for web testing
flutter build apk      # to build Android APK
```

## Notes

- Android Emulator cannot run inside Codespaces. Use a physical device or local emulator.
- Configure Firebase using the Firebase CLI (`firebase init`).
- Add Firebase configuration files (`firebase_options.dart`) as needed.
