---
description: オプションTypeScript3.0以降、buildコマンドが導入された
---

# Build Mode オプション

## Build Mode

`tsc -b tsconfig.json --verbos  // ログ出力`

`tsc -b tsconfig.json --dry　// ビルドテスト、出力しない`

`tsc -b tsconfig.json --clean　// Distフォルダなど削除`&#x20;

監視

`tsc -b tsconfig.json --force`

監視

`tsc -b tsconfig.json --watch`　

## オプション

### tsc -b --xxx

* verbose
  * ログ
* dry
  * ビルドテスト、出力なし
* clean
  * dist/ 削除
* force
  * 関連しないファイルもビルドする
* watch
  * 監視
