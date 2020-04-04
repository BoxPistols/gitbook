---
description: Vue Basic
---

# Vue Basic

### date関数で、変数にコンポーネントを渡す

```markup
<div id="root">
  <h1>
    Hello {{ message }}
    <hell/>
  </h1>
</div>
```

```javascript
Vue.component('hell',{
  data: function(){ // data関数
  return {
      hl: 'Hell!!',
      msg: 'これは地獄です',
      style: 'hell'
    };
  },
  template: '<p class="hell">Hell! {{ hl }} {{ msg }}</p>'
});

const app = new Vue({
  el: '#root',
  data: {
    message: 'Hell'
  }
});
```

```css
body
  background: #234
  color: gray
.hell
  color: crimson
```

### props: name属性で名前を指定

```javascript
Vue.component('hell',{
  props: ['name'],
  //  props: { name:String }, <- 型指定
  template: '<p class="hell">Hell! {{ name }}</p>'
});

const app = new Vue({
  el: '#root',
});
```

```markup
<div id="root">
  <h1>
    <hell name="地獄の３丁目"/>    
  </h1>
  <h2>
    <hell name="地獄の4丁目"/>    
  </h2>
</div>
```

### v-bindで属性を設定する

```markup
<div id="app">
  <h1>v-bindで属性を設定する</h1>
  <div class="box">
    <hello v-for="item in data" v-bind:name="item" />
  </div>
</div>
```

```javascript
let hello = Vue.component('hello',{
  props: ['name'],
  template: '<p class="hell">Hello, {{ name }}</p>'
})

const app = new Vue({
  el: '#app',
  data: {
    data: ['サタン',
           'ベルゼブブ',
           'パズズ',
           'ラーヴァナ',
           'マーラ',
           'イブリース',
           'アンラ・マンユ(アンリ・マユ)',
           'テスカトリポカ']
  }
})
```

```markup
Hello, サタン

Hello, ベルゼブブ

Hello, パズズ

Hello, ラーヴァナ

Hello, マーラ

Hello, イブリース

Hello, アンラ・マンユ(アンリ・マユ)

Hello, テスカトリポカ
```

### v-modelを使い、入力値で表示させる

```markup
<div id="app">
  <div class="box container">
    <p>v-modelで入力値でコンポーネントを表示</p>
    <div class="row">
      <div class="column column-25 column-offset-25">
        // template props
        <hello v-bind:name="name" />
      </div>
      <div class="column column-25">
        // v-model
        <input type="text" v-model="name">
      </div>
    </div>
  </div>
</div>
```

```javascript
let hello = Vue.component('hello',{
  props: ['name'],
  template: '<p class="hell">Hello, {{ name }}</p>'
})

const app = new Vue({
  el: '#app',
  data: {
    name: ''
  },
})
```

### v-on でイベントをbind

[https://jsfiddle.net/StyleEye/to67demy/43/](https://jsfiddle.net/StyleEye/to67demy/43/)

```markup
<div id="app">
  <div class="box container">
    <p>v-onでイベントをバインド</p>
    <div class="row">
      <div class="column column-25 column-offset-25">
        <hello />
      </div>
    </div>
  </div>
</div>
```

```javascript
let hello = Vue.component('hello',{
data: function(){
  return {
    counter: 0
  };
},
template: '<p class="hell" v-on:click="counter++;">Hello, {{ counter }}</p>'
})

const app = new Vue({
  el: '#app',
})
```

### Method イベント処理を別途用意

[Vue.js: 複数のクラスをバインディングする場合どのような書き方があるか](https://qiita.com/FumioNonaka/items/08ab308cf1e931d4b2eb)

```markup
<div id="app">
  <div class="box container">
    <div class="row">
      <div class="column column-25 column-offset-25">
        <hello />
      </div>
    </div>
  </div>
</div>
```

```javascript
let hello = Vue.component('hello',{
data: function(){
  return {
    counter: 0,
    isRed: false,
		isBorderChange: false,
  };
},
methods: {
  doAction:function(event){
	this.counter++;
		if(this.counter > 10) {
      this.counter = 0;
    }
		if(this.counter % 2 == 0) {
			this.isRed = true;
			this.isBorderChange = false;
    } else {
			this.isRed = false;
			this.isBorderChange = true;
		}
  }
},
template: '<p class="hell" v-bind:class="{red:isRed, teal:isBorderChange}" v-on:click="doAction">Clicked, {{ counter }}</p>'
})

const app = new Vue({
  el: '#app',
})
```

```css
body{
  font-size: 200%;
  padding: 0 24px;
	color: #234;
	}
.box{
  padding: 24px;
	}
.hell{
  font-size: 200%;
  color: orange;
  cursor: pointer;
  border: 4px solid orange;
  text-align: center;
	white-space: nowrap;
	width: fit-content;
	padding: 12px 24px;
	border-radius: 10px;
}
.red{
	color:crimson;
	transition: .7s;
}
.teal{
	border-color: teal;
}
```



