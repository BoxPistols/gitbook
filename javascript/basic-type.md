---
description: Basic Dott
---

# Basic JavaScript基本構文

Source: [https://github.com/BoxPistols/JavaScriptBasicDott.git](https://github.com/BoxPistols/JavaScriptBasicDott.git)

参考: [https://www.javadrive.jp/javascript/](https://www.javadrive.jp/javascript/)

### Type 型判定

```javascript
"use strict"
{
    console.log(typeof "hello") // string
    console.log(typeof 5) // number
    console.log(typeof true) // boolean'../css/base.styl'
    
    console.log(typeof underfined)
    console.log(typeof null) // obj
    
    
    console.log('5' + 3) // 53
    console.log(parseInt('5', 10) + 3) // 8 <- parseIntで文字列を数値に変更
}
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

### Arrow関数でforEach

```javascript
const array = [1, 2, 3, 4];
array.forEach(number => console.log(number));

array.forEach((num, index) => console.log(index + 1, num));
```

### アロー関数の種類

{% tabs %}
{% tab title="JavaScript" %}
```javascript
アロー関数のexpression部は、次の2種類を持つことが出来る

const array = [1, 2, 3, 4];

1- {}で囲わない簡潔文体(concise body)
// 簡潔文体
array.map(number => number + number);

2- {}で囲うブロック文体(block body)
// ブロック文体
array.map(number => {
  return number + number;
});

簡潔文体は、最後の処理結果がそのまま戻り値として返りますが、
ブロック文体は自動的に値を返しません。
そのため、明示的にreturnで値を返す必要があります。


```
{% endtab %}
{% endtabs %}



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

![](<../.gitbook/assets/image (1).png>)

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

```javascript
'use strict';

{
  const scores = [80, 90, 40, 70];
  // scores.push(60,50); // 末尾に追加
  // scores.shift(); // 先頭削除

  scores.splice(0,1,777, 888);
  // (start: x, deleteCount: x, items: x , x)
  // 先頭[0]番目から１つ要素を削除して、末尾に要素を追加

  // for (let i = 0; i < 3; i++) {
  for (let i = 0; i < scores.length ; i++) {
    console.log(`${i}: ${scores[i]}`)
  }
}
```

![](<../.gitbook/assets/image (4).png>)

![](<../.gitbook/assets/image (3).png>)

### filter

```javascript
'use strict';

{
  const numbers = [1, 4, 7, 8, 10];

  // const evenNumbers = numbers.filter(number => {
  //   if (number % 2 === 0) {
  //     return true;
  //   } else {
  //     return false;
  //   }
  // });

  // 一行で
  const evenNumbers = numbers.filter(number => number % 2 === 0);

  console.log(evenNumbers);
  
  ---------------------------------------
  
  // 式自体を return
  const evenNum = numbers.filter(num => {
     return num % 3 === 0;
  });

  // さらに短く
  const evenNum = numbers.filter(num => num % 3 === 0)
  
  const el = document.querySelector(".content");
  el.insertAdjacentHTML("beforeend", `<h2>even：${evenNum}</h2>`);

}
```

### 分割代入

```javascript
 const score = [40, 60, 80, 90, 120]
 /*
    分割代入
 */
 const[a,b, ...hoge] = score // hoge = 残りの配列
 el.innerHTML = `${a} : ${b} : ${hoge}`

```

### Object オブジェクトの取得と操作

```javascript
"use strict";

{
  const el = document.querySelector(".content");
  // el.insertAdjacentHTML("beforeend", `<p>テスト：テスト${null}`);

  const others = {
    r: 111,
    color: "red"
  };

  const point = {
    x: 100,
    y: 180,
    n: 120,
    ...others // include
  };

  point.x = 120; // 上書き
  point.z = 90; // 要素追加

  // delete point.z
  // console.log(point)

  // キーからプロパティを取得
  el.insertAdjacentHTML("beforeEnd", `<p>キーからプロパティを取得：${point.z}`);

  // forで全部取得 <- 冗長？
  // for (var i = 0; i < Object.keys(point).length; i++) {
  //   el.insertAdjacentHTML(
  //     "beforeEnd",
  //     `<p>Obj：
  //     ${Object.keys(point)[i]}:
  //     ${Object.values(point)[i]}`
  //   );
  // }
  
  // forEachで取得
  const keys = Object.keys(point);　// 定数keysにオブジェクト内容を設定
  keys.forEach(key => {　// keyという名前でキーを全部受け取る
  // キーの取得 ＝ ${key} ＆　プロパティの取得 ＝ ${point[key]}
    el.insertAdjacentHTML("beforeEnd", `<div class="fx"><p>Key：${key}</p> <p>Value：${point[key]}</p></div>`);
  });

}

```

### 文字列

```javascript
"use strict";

{
  const el = document.querySelector(".content");
  el.insertAdjacentHTML("beforeend", `<p>テスト：テスト${null}`);

  const str = "吉田かおり"

  // 文字数： str.length
  // 部分文字列： str.substring(2, 4)
  let end = str.length
  el.insertAdjacentHTML("beforeend", `<p>テスト：テスト${str.substring(0, end)}`);
}

```

### 文字列の整形

```javascript
"use strict";

{
  const el = document.querySelector(".content");
  // el.insertAdjacentHTML("beforeend", `<p>テスト：テスト${null}`);

  const str = "吉田かおり"
  // 文字数： str.length
  // 部分文字列： str.substring(2, 4)
  let end = str.length
  el.insertAdjacentHTML("beforeend", `<p>名前：
${str.substring(0, end - 1)}`);


/*------ join() split() --------*/
  const d = [2019, 11, 14];
  // 配列の連結UI
  el.insertAdjacentHTML("beforeend", `<p>日時： ${d} </p>`);
  el.insertAdjacentHTML("beforeend", `<p>日時 join('/')： ${d.join('/')} </p>`);
  el.insertAdjacentHTML("beforeend", `<p>日時 join('')： ${d.join('')} </p>`);

  const t = '17:08:24';
  el.insertAdjacentHTML("beforeend", `<p>時間： ${t} </p>`);
  el.insertAdjacentHTML("beforeend", `<p>時間 split(':')： ${t.split(':')} </p>`);

  const [hour, minute, second] = t.split(':');
  el.insertAdjacentHTML("beforeend", `<p>const [hour, minute, second] = t.split(':');</p><p>時間： ${hour}時${minute}分${second}秒 </p>`);

}

```

### 数値表示 合計 平均 小数点

```javascript
"use strict";

{
  const el = document.querySelector(".content");
  // el.insertAdjacentHTML("beforeend", `<p>テスト： ${null}</p>`);

  /*------ 数値計算 --------*/

  const scores = [10, 3, 9];

  // 形容の変数を置く
  let sum = 0;

  scores.forEach(score => {
    sum += score;
  });

  el.insertAdjacentHTML("beforeend",
    `<p>forEach 計算：${scores.length}件：　合計 ${sum}</p>`
  );

  const avg = sum / scores.length

  el.insertAdjacentHTML("beforeend",
  `<p>forEach 平均：${avg.toFixed(2)}</p>`);
  /*
    少数点 切り捨て Math.floor(avg)
    少数点 切り上げ Math.ceil(avg)
    少数点 四捨五入 Math.round(avg)
    少数点 num桁表示 avg.Math.toFixed(3)
  */
}
```

### ランダム

```javascript
  /*
  console.log(Math.random()); 0以上1未満

  0, 1, 2
  Math.floor(Math.random() * 3)

  0, ..., n
  Math.floor(Math.random() * (n + 1))

  min, ..., max
  Math.floor(Math.random() * (max + 1 - min)) + min
  el.insertAdjacentHTML("beforeend", `<h3>ランダム</h3>`);
  console.log(Math.floor(Math.random() * 6) + 1);
*/

// サイコロ ＝ 1 - 6 の間の整数
  el.insertAdjacentHTML(
    "beforeend",
    `<h3>サイコロ ランダム：　${Math.floor(Math.random() * 6) + 1}</h3>`
  );
```

### import  / export

Foo.js

```javascript
export default function Foo(){}
  return (<p>foo</p>)
```

Bar.js

```javascript
const Bar = () =>{
  return (<p>boo</p>)
}
export default Bar
```

