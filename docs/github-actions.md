
# GitHub ActionsでのAndroid/iOSビルドガイド

## 前提
- secretsに `ANDROID_KEYSTORE`, `KEYSTORE_PASSWORD`, `KEY_ALIAS`, `KEY_PASSWORD` を登録済み
- Apple側のビルド証明書なども同様に `secrets` に

## 例：Androidビルド
```yaml
name: Android Build

on:
  push:
    branches: [main]

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - uses: actions/setup-node@v3
        with:
          node-version: 18

      - name: Install dependencies
        run: npm ci

      - name: Build Ionic App
        run: ionic build

      - name: Copy Web Assets
        run: npx cap copy android

      - name: Build APK
        run: cd android && ./gradlew assembleRelease
```
...
