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
el.insertAdjacentHTML('afterend', post )
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

