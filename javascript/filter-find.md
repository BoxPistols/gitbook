---
description: '*document.writeは現在非推奨です'
---

# filter find

### filter 検索 抽出

```javascript
/*
  forEach Method
*/
const nums = [1,2,3] 
// アロー関数 - コールバック関数
//nums.forEach((num) => { document.write(`forEach/コールバック関数： ${num} <br>`) })

document.write(`<br>`) 

/*
  find Method
*/
let flNums = [1, 2, 3, 4, 5, 6, "もげ", "もげ"]
const foundNum = flNums.find((flNum) => {
  return flNum > 2
})

document.write(foundNum)

document.write(`<br>`) 

/*
  filter Method
*/
const filterNum = flNums.filter((flNum) => {
  return flNum > 2
})
document.write(filterNum)


/*
  検索
*/
var a = [1,2,3,3,2,2,5, "もげ", "もげ", "ほげ"];

// 重複を削除したリスト
var b = a.filter(function (x, i, self) {
  return self.indexOf(x) === i;
});

document.write(`<br>`) 
document.write(a)


// 重複のみをリスト
var c = a.filter(function (x, i, self) {
  return self.indexOf(x) !== self.lastIndexOf(x);
});
document.write(`<br>`) 
document.write(c)


// 重複を検出したものを重複しないでリスト
var d = a.filter(function (x, i, self) {
  return self.indexOf(x) === i && i !== self.lastIndexOf(x);
});
document.write(`<br>`) 
document.write(d)


// 重複していないものリスト
var e = a.filter(function (x, i, self) {
  return self.indexOf(x) == self.lastIndexOf(x);
});
document.write(`<br>`) 
document.write(e)


console.log(a); // [ 1, 2, 3, 3, 2, 2, 5 ]
console.log(b); // [ 1, 2, 3, 5 ]
console.log(c); // [ 2, 3, 3, 2, 2 ]
console.log(d); // [ 2, 3 ]
console.log(e); // 
//console.log(f); // 

document.write(`<br>`) 
document.write(`<br>`) 

// テキスト一致の回数
const words = ['spray', 'limit', 'elite', 'elite', 'elite', 'elite', 'exuberant', 'destruction', 'present', 'elite'];

// 指定の文言一致の回数
const resultElite = words.filter( word => word === "elite" );
document.write(resultElite.length);

document.write(`<br>`)
// elite が ８時間勤務の属性としたら
let eliteCount = 8
// ８時間勤務が3人で、24時間
document.write(`本日の「${eliteCount}時間勤務」は${resultElite.length}人、 合計=${resultElite.length * eliteCount} 時間`);




```
