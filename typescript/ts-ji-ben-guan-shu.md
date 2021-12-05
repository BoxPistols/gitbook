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

![Quokkaでの即時表示 / Atom Editor](<../.gitbook/assets/image (1) (1).png>)

### オーバーロード

```javascript
// ===== 関数のオーバーロード =====

function overNum(a: number, b: number): number; // 関数のシグネチャ = 組み合わせ
function overStr(a: string, b: string): string;

// 実務的な書き方
function overLoad(a: any, b: any): any {
    if (typeof a === "number" && typeof b === "number") {
        return a + b
    }
    return a + " " + b
}
overLoad(1, 2)
overLoad("much", 2)
```

![result value](<../.gitbook/assets/image (5) (1).png>)

オーバーライド パターン

![](<../.gitbook/assets/image (6).png>)
