---
description: tsconfig.json
---

# target / module

## target / module 

on tsconfig.json

```javascript
{
  "compilerOptions": {
    "target": "es5",
    "module": "commonjs",
    "strict": true,
    "esModuleInterop": true,
    "skipLibCheck": true,
    "forceConsistentCasingInFileNames": true
  }
}

```

### Change Test

```javascript
"target": "es2015",
"module": "amd",
```

Modern JS

```javascript
"target": "esnext",
"module": "esnext",
```

### Strict

厳密な型チェック

```javascript
"strict": true, // false
```

### Add Folder Path 

ターゲット階層

```javascript
{
  "compilerOptions": {
    "target": "es5", // esnext
    "module": "commonjs", // esnext
    "strict": true,
    "esModuleInterop": true,
    "outDir": "dist"
  },
  "include": ["src/**/*"]
}

```

ignore -&gt; dist

### Options

```javascript
{
  "compilerOptions": {
    "target": "es5", // esnext es5　es2015 - es2018
    "module": "commonjs", // esnext commonjs
    "strict": true,
    "noUnusedLocals": true, // 未使用チェック
    "noUnusedParameters": true, // 未使用パラメータチェック
    "noImplicitReturns": true, // 不明なreturnチェック
    "noFallthroughCasesInSwitch": false, // 不明なcaseチェック,
    "esModuleInterop": true,
    "outDir": "dist",
    /* create x.d.ts */
    "declaration": true,
    /* inslude JavaScript */
    "allowJs": true, // JavaScript Build
    "checkJs": true, // js error check
    "removeComments": true // remove comments
  },
  "include": ["src/Book/**/*"],
  "exclude": ["node_modules", "**/*.test.ts"], // 除外フィルター
  "compileOnSave": true // compile on save
}

/**
 * include < exclude < files
 * files excludeを無視してincludeに追加する
 * extends 継承
 * references 参照プロジェクトへの指定
 * compilerOptions // ビルド設定
 * compileOnSave // ソースコード変更時にビルドする
 **/

```

