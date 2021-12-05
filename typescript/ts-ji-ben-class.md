---
description: TypeScript Class
---

# TS基本 Class

## &#x20;TypeScript クラス基本

```javascript
// ===== クラス on TypeScript =====

/*
 * @User: クラス
 * @name: string & コンストラクタ
 * @greet: メソッド <- 挙動確認
 * @sayHi: インスタンス生成
 * === オプション アクセス修飾子  ===
 * - public: default
 * - private
 * - protected
 */

class User {
    /*
    public name: string
    constructor(name: string) {
        this.name = name
    }
    */
    constructor(public name: string) { } // 上述の省略形
    public greet(): void {
        console.log('Hi' + this.name)
    }
}

const say = new User('Bob')
// say
say.name
say.greet() // ? <- 出ない？ 仕様確認


// ========= class try2 to Private
class User2 {
    constructor(private _name: string) { } // 外から読ませない
    public greet2(): void {
        console.log('Hi!' + this.name)
    }
    get name() {
        return this._name;
    }
}

const say2 = new User2('Jane')
say2.name // @to result: Property 'name' does not exist on type 'User2'.
say2.greet2() // ? <- 出ない？ 仕様確認

// =========

```

![](<../.gitbook/assets/image (1).png>)

![](<../.gitbook/assets/image (5).png>)

### 残課題

* [ ] メソッドが呼び出せていない
  * [ ] 仕様が変わったか、設定が必要？
