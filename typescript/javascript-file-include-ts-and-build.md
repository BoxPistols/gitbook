---
description: JavaScriptファイルをビルドに含んで型推論を当てる
---

# JavaScript file include TS & build

tsconfig.json

```javascript
    /* inslude JavaScript */
    "allowJs": true,
    "checkJs": true
```

sample.js

```javascript
export let sampleText = 'Sample Text'
export function sampleFunction() {
  return true
}

```

test.js

```javascript
import { sampleText, sampleFunction } from './sample'
const a = sampleText
const b = sampleFunction()

// sample.d.ts 型推論
export function sampleFunction(): boolean;
export let sampleText: string;

```

## 用途

* 既存のJavaScriptをTypescript移行していく時
* JavaScriptの型推論を確認したい時
* JavaScriptにダイレクトに型はつけられない、確認用
* 新規TypeScriptでは必要は無い

