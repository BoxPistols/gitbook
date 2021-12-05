---
description: TypeScript基本記法 関数
---

# TS基本 関数

## 関数宣言 関数式

### 値の初期値 取得不可時の代入値

base.ts

```tsx
/* 一行の時はreturnも{}も省略可 */
const addBase = (a: number = 120, b?: number = 12): number => a + b

const x = addBase(undefined, 9)
const y = addBase(100)

console.log(x)
console.log(y)
```

Quokkaでの即時表示 / Atom Editor

![](<../.gitbook/assets/image (1).png>)
