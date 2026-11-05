# 12. Geração do APK

Com Flutter SDK e Android SDK configurados:

```bash
cd app
flutter pub get
flutter analyze
flutter test
flutter build apk --release
```

O APK de versão release será gerado, por padrão, em:

`app/build/app/outputs/flutter-apk/app-release.apk`

Para gerar APKs separados por arquitetura:

```bash
flutter build apk --split-per-abi
```

Antes de distribuir o aplicativo, configurar assinatura de release, revisar permissões, configurar a URL HTTPS da API e testar em aparelho Android físico. Não versionar chaves de assinatura ou senhas no repositório.
