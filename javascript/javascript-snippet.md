# JavaScript Snippets

## テンプレートリテラル

```javascript
const score = [1, 2, 3]
console.log(`${score}[0]`)
```

## HTML 要素取得 / 表示

```javascript
let el = document.querySelector('.content');
el.innerHTML = result;
```

## HTML DOM生成 表示

```javascript
const el = document.querySelector('.content')
el.innerHTML = "コンテンツ表示"

// div要素を生成
const addDiv = document.createElement('div')
// classを追加
addDiv.className = 'sample'

// 生成したdiv要素を追加する
el.appendChild(addDiv);
addDiv.innerHTML = "inner要素"
```

## 非破壊でHTML追加

参照 [https://qiita.com/amamamaou/items/624c22adec32515e863b](https://qiita.com/amamamaou/items/624c22adec32515e863b)

```javascript
let el = document.querySelector('.content')
el.innerHTML = "コンテンツ"

const post = "<h2>Test</h2>"
el.insertAdjacentHTML('beforeend', post )
```

#### insertAdjacentHTMLの位置関係

```markup
<!-- beforebegin -->
<element>
  <!-- afterbegin -->
  <child>Text</child>
  <!-- beforeend -->
</element>
<!-- afterend -->
```

## 配列のHTML表示

```javascript
{
  const el = document.querySelector('.content')

  const score = [1, 2, 3]
  console.log(`Score: ${score}`)

  for (let i = 0; i < score.length ; i++) {
    el.insertAdjacentHTML('beforebegin', (`<h2>Score: ${score[i]}</h2>`) )
  }
}
/*
  Score: 1
  Score: 2
  Score: 3
*/
```

### Mix log

```javascript
{
  const el = document.querySelector('.content')

  let hog = 120

  // console.log(`Score: ${score}`)
  const other = [333, 444, 555]
  const score = [hog, 40, 60, 80, ...other] // ...xxx スップレッド構文
  // score.push(1200, 1500) // 末尾に追加
  // score.shift()
  // pop

  // splice: -> 配列[2番目] = 3つ目 から 2つ削除 = 60, 80 して、そこに item追加
  // score.splice(2, 2, 123, 456)


  /*
   ...スップレッド構文 を関数の引数に使う
 */
  function sum(a, b, c, d){
    return a + b - c + d
  }
  // sum(10, 20)
  el.insertAdjacentHTML('beforebegin', `<h2> ${sum(...other,1000)} </h2>` )

  for (let i = 0; i < score.length ; i++) {
    el.insertAdjacentHTML('beforebegin', (`<h2>${i + 1} : Score: ${score[i]} </h2>`) )
  }


  /*
    分割代入
  */
  const[a,b, ...hoge] = score // hoge = 残りの配列
  el.innerHTML = `${a} : ${b} : ${hoge}`

}
```

### 配列の合計

```javascript
{
  const arr = [1, 2, 3, 4, 5];
 
   const res = (arr) =>{
    
    let sum = 0;
  
    arr.forEach((elm) =>{
      sum += elm;
    });
    
    return sum;
  };
  
  document.write(res(arr)); // 15
}
```

### 配列のソート Sort

```javascript
let arr = [20,12,33,12,15,18,1,2]
arr.sort(function(a, b) {    
    return a > b ? 1 : -1
})
arr
```

### Sort sample

```javascript
{
  const arr = [90, 80, 110, 22]
  // document.write(arr)
  arr.push("88") // 接尾追加　< remove end > pop
  arr.unshift("9")　// 接頭追加 < remove start > shift
  // 削除・追加 場所と値の指定
  // arr.splice(1,2, 999,3)
  // document.write(`${arr}<br>`)

  //　スプレッド構文
  otherArr = [22,11,33,55,77]

  // 配列の結合 追加
  mixArr = [arr, ...otherArr]
  document.write(`mix: ${mixArr} <br>`)

  const lg = otherArr.length
  // document.write(lg)
  sum = (a, b, c) => {
    document.write(`sum(...otherArr) -> ${a + b + c}<br>`)
  }
  sum(...otherArr)
}

{
  // 配列の合計
  const arr = [1, 2, 3, 4, 5];
  const res = (arr) =>{
    let sum = 0;
    arr.forEach((elm) =>{
      sum += elm;
    });
    return sum;
  };
  document.write(`arr合計： ${res(arr)}<br>`); // 15
}

{
  // Sort
  let arr = [20, 12, 33, 12, 15, 18, 1, 2]
  arr.sort(function (a, b) {
    // return a > b ? 1 : -1
    // return a - b
    return b - a
  })
  document.write((`Sort: ${arr}<br>`))
}
```

