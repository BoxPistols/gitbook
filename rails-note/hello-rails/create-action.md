---
description: add actionsetting / routing
---

# Create Action

{% embed url="http://127.0.0.1:3000/hello/index" %}
[http://127.0.0.1:3000/hello](http://127.0.0.1:3000/hello/index)
{% endembed %}

/app/controllers/hello\_controller.rb

```ruby
class HelloController < ApplicationController
    def index
        render plain:"Hello, This 1s Rails sample page!"
    end
end
```

routes.rb

```
Rails.application.routes.draw do
    get "hello/index"
    get "hello", to: 'hello#index'
end
```

[http://127.0.0.1:3000/hello](http://127.0.0.1:3000/hello) <- hello/index  省略可

#### 解説

* `get` "`アドレス", to: 'コントローラー#アクション'`&#x20;
* `to:=`自動的に割り当てるコントローラーやメソッドではなく、実行するアクションメソッドを自分で明示的に指定したい時に設定する。
* `http://localhost:3000/hello` にアクセスしたら、`to: 'hello#index'`を呼び出す
* \= `HelloController` クラスの`index`メソッドを呼び出す

{% embed url="https://github.com/BoxPistols/dev-rails6-211031/commit/5f2d1cd59756fdcaa84e4003d2f9cbb865fe915d" %}
set Controller & Routeing
{% endembed %}
