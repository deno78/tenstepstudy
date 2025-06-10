
# Ionic + Capacitor プロジェクトセットアップガイド

## 前提条件
- Node.js (v18以上推奨)
- npm または yarn
- Ionic CLI（`npm install -g @ionic/cli`）

## プロジェクト作成
```bash
ionic start softskills-tracker tabs --type=react
cd softskills-tracker
ionic integrations enable capacitor
npx cap add android
npx cap add ios
```
...
