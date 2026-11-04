# 8. Geração do arquivo APK

O aplicativo será desenvolvido com Flutter e compilado para Android utilizando o Flutter SDK e o Android SDK instalados e configurados no ambiente de desenvolvimento.

## 8.1 Processo previsto

1. Abrir o projeto Flutter no Android Studio.
2. Instalar as dependências declaradas no arquivo `pubspec.yaml`.
3. Configurar o identificador do aplicativo e as versões Android necessárias.
4. Configurar a URL da API para o ambiente de teste ou produção.
5. Executar análise estática e testes.
6. Conectar um dispositivo Android ou iniciar um emulador.
7. Testar as funcionalidades online e offline.
8. Configurar a assinatura de release.
9. Executar o comando de compilação do APK.

## 8.2 Comandos

```bash
flutter pub get
flutter analyze
flutter test
flutter build apk --release
```

## 8.3 Localização do arquivo

Após a compilação bem-sucedida, o APK de release será gerado em:

`build/app/outputs/flutter-apk/app-release.apk`

O caminho é relativo à pasta do projeto Flutter.

## 8.4 Distribuição

O arquivo poderá ser transferido para um dispositivo Android e instalado para testes. Antes da distribuição, deverão ser conferidos a assinatura de release, permissões, configuração HTTPS da API e funcionamento do banco SQLite.

Nesta primeira etapa, apenas o procedimento de geração está documentado. O APK será produzido em uma etapa posterior, após a implementação e os testes do aplicativo.
