---
description: 基本仕様キャッチアップ
---

# Living Standard

&#x20;&#x20;

#### 基本ルール

* DOCTYPE => `<!DOCTYPE html>`
* DOCTYPE宣言を作成できない場合 = `<!DOCTYPE html SYSTEM "about:legacy-compat">`

#### 厳格な仕様

* HTTPレスポンスヘッダ
  * XML = application/xhtml+xml、application/xml又はtext/xml
  * HTML = `text/html`

#### 強い禁則

* `document.write`と`document.writeln`は使用禁止

#### どちらでも良い

* svg要素及びmath要素の`xmlns属性`
