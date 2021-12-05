---
description: コントローラー関連ファイル作成
---

# Genarate Controllr

{% embed url="https://github.com/BoxPistols/dev-rails6-211031/pull/2/commits/33be99b9f0184c6ef3e5a96f47d8f224b750bd4a" %}

```dart
$ rails g controller hello
Running via Spring preloader in process 12084
      create  app/controllers/hello_controller.rb
      invoke  erb
      create    app/views/hello
      invoke  test_unit
      create    test/controllers/hello_controller_test.rb
      invoke  helper
      create    app/helpers/hello_helper.rb
      invoke    test_unit
      invoke  assets
      invoke    scss
      create      app/assets/stylesheets/hello.scss
```

```
app/assets/stylesheets/hello.scss
app/controllers/hello_controller.rb
app/helpers/hello_helper.rb
test/controllers/hello_controller_test.rb
```
