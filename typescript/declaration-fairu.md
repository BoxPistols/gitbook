---
description: '"declaration": true'
---

# declaration / 型宣言ファイル

## declaration

### tsconfig.json

```text
"declaration": true
```

### Create .d.ts

```javascript
// ts
export function test2() {
  return { value: 'test2' }
}

// tsc

// create x.d.ts 自動型推測
export declare function test2(): {
    value: string;
};

```

* 用途はLibrary開発
* 普段は使わない

