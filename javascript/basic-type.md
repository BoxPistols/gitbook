---
description: Basic Dott
---

# Basic JavaScript基本構文

Source: [https://github.com/BoxPistols/JavaScriptBasicDott.git](https://github.com/BoxPistols/JavaScriptBasicDott.git)

参考: [https://www.javadrive.jp/javascript/](https://www.javadrive.jp/javascript/)

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

### 関数宣言・関数式・無名関数

```javascript
// 関数宣言
function sum(x, y, z) { // 関数(仮引数)
  //console.log(x + y + z);
  return x + y + z; // 処理結果を値で返したい
  // return以降は何も機能しない
}

// 関数式 function()無名関数
const sum = function(x, y, z) { // 関数(仮引数)
  //console.log(x + y + z);
  return x + y + z; // 処理結果を値で返したい
  // return以降は何も機能しない
};

/*
 returnにすることで、
 sum関数自体を式に出来るようになった
 関数名(実引数, 実引数, ...)
 */
const total = sum(12, 3, 4) + sum(2, 3, 4);
console.log(total);

```

### アロー関数

```javascript
let el = document.querySelector('.content');


// default js
const sum = function (a, b, c) {
  return a + b + c
};

// arrow js
const sum = (a, b, c) => {
  return a + b + c
};

// 省略表現
const sum = (a, b, c) =>  a + b + c;

const result = sum(12, 3, 4);
el.innerHTML = result;

// 関数式 無名関数
const d = function (a) {
  return a * 2;
};

// 関数式省略 / 単体だと(仮引数):（） は無くて良い / return省略 & 一行で可
const d = a => a * 2;
el.innerHTML = d(12);
```

## 

## Object

### map

```javascript
{
  let el = document.querySelector('.content');
  const prices = [180, 190, 200];

  const upDatePrices = prices.map((price) => {
    return price * 2;
  });
  console.log(upDatePrices);
  el.innerHTML = upDatePrices;

  // to Arrow function
  const upPrice2 = prices.map(price => price * 20);
  console.log(upPrice2);
  el.innerHTML = upDatePrices;
}
```

### Array Loop

```javascript
'use strict';

{
  const scores = [80, 90, 40, 70];

  // console.log(`Score: ${scores[0]}`);
  // console.log(`Score: ${scores[1]}`);
  // console.log(`Score: ${scores[2]}`);

  // for (let i = 0; i < 3; i++) {
  for (let i = 0; i < scores.length ; i++) {
    console.log(`${i}: ${scores[i]}`)
  }
}

```

### Array 操作 push shift pop unshuft

![TODO: &#x753B;&#x50CF;&#x5DEE;&#x3057;&#x66FF;&#x3048;](../.gitbook/assets/image%20%282%29.png)



```javascript
'use strict';

{
  const scores = [80, 90, 40, 70];
  
  scores.push(60,50); // 末尾に追加
  scores.shift(); // 先頭削除
  
  // console.log(`Score: ${scores[0]}`);
  // console.log(`Score: ${scores[1]}`);
  // console.log(`Score: ${scores[2]}`);

  // for (let i = 0; i < 3; i++) {
  for (let i = 0; i < scores.length ; i++) {
    console.log(`${i}: ${scores[i]}`)
  }
}

```

### splice 削除 追加

![](../.gitbook/assets/image%20%284%29.png)

![](../.gitbook/assets/image%20%283%29.png)

