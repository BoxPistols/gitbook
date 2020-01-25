---
description: Basic Dott
---

# Basic

Source: [https://github.com/BoxPistols/JavaScriptBasicDott.git](https://github.com/BoxPistols/JavaScriptBasicDott.git)

### Type 型判定

```javascript
"use strict"

console.log(typeof "hello") // string
console.log(typeof 5) // number
console.log(typeof true) // boolean'../css/base.styl'

console.log(typeof underfined)
console.log(typeof null) // obj


console.log('5' + 3) // 53
console.log(parseInt('5', 10) + 3) // 8 <- parseIntで文字列を数値に変更

```

### 演算子条件

```javascript
"use strict"

const score = 40
score >= 80 ? console.log('Win') : console.log('Lose')

const el = document.querySelector('.content')
el.innerHTML = score
```

論理演算子

```javascript
'use strict'

const score = 60
const name = 'mike'

if(score >= 50){
  if(name === 'mike'){
    console.log('Good!!')
  }
}

// 同じ条件文で、論理演算子
if(score >= 50 && name === 'mike'){
  console.log('LON!')
}


```



