---
description: Vue Basic
---

# Vue

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





