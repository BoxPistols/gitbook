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

