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

### 論理演算子

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

### Switch文

```javascript
const el = document.querySelector('.content');

const signal = 'red';

switch(signal) {
  case "red":
    console.log('stop');
    el.innerHTML = ('stop');
    el.classList.add('stop');
    break;
  case "yellow":
    console.log('alert');
    el.innerHTML = ('alert');
    el.classList.add('alert');
    break;
  case "blue":
  case "green": // 複数条件
    console.log('go!');
    el.innerHTML = ('go!');
    break;
  default: // 該当が何もなかった時
    console.log('Wait...');
    el.innerHTML = ('Wait...');
}
```

### for文

```javascript
let el = document.querySelector('.content');

for (let i = 0; i <= 10; i++) {
  console.log(`Hello: ${i}`); //<- 1 2 3... 9 10
  el.innerHTML = (`Hello: ${i}`); //<- Hello 10
}

```

### while / do while

```javascript
let el = document.querySelector('.content');

let hp = 100;
while (hp > 0){
  console.log(`${hp} left!`);
  hp -= 15
}

// もし初期値が最初からコープ外だった時
let hpMinus = -70;
do{
  // 1- 初期変数が一度だけ表示され
 console.log(`${hpMinus} left!`);
  hpMinus -= 15;
} while (hpMinus > 0); // 2- その後whileが稼働する
```

### Continue / Break

```javascript
for (let i = 0; i <= 10; i++) {
  if (i === 2 || i === 4 || i % 3 ===0){ // 2, 4, 3の倍数
    continue // 飛ばす箇所
  }
  if(i >= 9){
    break　// 止める
  }
  console.log(i);
}
```

### 関数 / 引数

```javascript
let el = document.querySelector('.content');

function showAd() {
  console.log('-------------------');
  console.log('--------AD---------');
  console.log('-------------------');
}
showAd();

function showAd2(msg = '何もなかった時表示') { // 仮引数 =  仮置き
  console.log('-------------------');
  console.log(`------${msg}-----`); // `xxx` テンプレートリテラル
  console.log('-------------------');
}
showAd2('ナイスな広告'); // 実引数

```

