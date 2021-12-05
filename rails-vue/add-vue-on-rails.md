# Add Vue on Rails



### 新規プロダクト

{% embed url="https://qiita.com/Ryoga_aoym/items/e1d91351389904240594" %}

### 既存プロダクト

{% embed url="https://www.petitmonte.com/ruby/rails-vuejs-project.html" %}

```
rails webpacker:install:vue
```

```ruby
rails webpacker:install:vue
Copying vue loader to config/webpack/loaders
      create  config/webpack/loaders/vue.js
Adding vue loader plugin to config/webpack/environment.js
      insert  config/webpack/environment.js
      insert  config/webpack/environment.js
Adding vue loader to config/webpack/environment.js
      insert  config/webpack/environment.js
      insert  config/webpack/environment.js
Updating webpack paths to include .vue file extension
      insert  config/webpacker.yml
Copying the example entry file to /Users/ai/dev/BackEnd/Rails/RailsReactApp/app/javascript/packs
      create  app/javascript/packs/hello_vue.js
Copying Vue app file to /Users/ai/dev/BackEnd/Rails/RailsReactApp/app/javascript/packs
      create  app/javascript/app.vue
Installing all Vue dependencies
         run  yarn add vue vue-loader vue-template-compiler from "."
yarn add v1.22.10
[1/4] 🔍  Resolving packages...
[2/4] 🚚  Fetching packages...
[3/4] 🔗  Linking dependencies...
warning " > @babel/preset-react@7.12.13" has unmet peer dependency "@babel/core@^7.0.0-0".
warning "@babel/preset-react > @babel/plugin-transform-react-display-name@7.12.13" has unmet peer dependency "@babel/core@^7.0.0-0".
warning "@babel/preset-react > @babel/plugin-transform-react-jsx@7.12.17" has unmet peer dependency "@babel/core@^7.0.0-0".
warning "@babel/preset-react > @babel/plugin-transform-react-jsx-development@7.12.17" has unmet peer dependency "@babel/core@^7.0.0-0".
warning "@babel/preset-react > @babel/plugin-transform-react-pure-annotations@7.12.1" has unmet peer dependency "@babel/core@^7.0.0-0".
warning "@babel/preset-react > @babel/plugin-transform-react-jsx > @babel/plugin-syntax-jsx@7.12.13" has unmet peer dependency "@babel/core@^7.0.0-0".
warning " > eslint-plugin-vuetify@1.0.0-beta.8" has unmet peer dependency "eslint@^6.0.0 || ^7.0.0".
warning "eslint-plugin-vuetify > eslint-plugin-vue@6.2.2" has unmet peer dependency "eslint@^5.0.0 || ^6.0.0".
warning "eslint-plugin-vuetify > eslint-plugin-vue > vue-eslint-parser@7.6.0" has unmet peer dependency "eslint@>=5.0.0".
warning " > webpack-dev-server@3.11.2" has unmet peer dependency "webpack@^4.0.0 || ^5.0.0".
warning "webpack-dev-server > webpack-dev-middleware@3.7.3" has unmet peer dependency "webpack@^4.0.0 || ^5.0.0".
warning " > vue-loader@15.9.6" has unmet peer dependency "css-loader@*".
warning " > vue-loader@15.9.6" has unmet peer dependency "webpack@^3.0.0 || ^4.1.0 || ^5.0.0-0".
[4/4] 🔨  Building fresh packages...
success Saved lockfile.
success Saved 11 new dependencies.
info Direct dependencies
├─ vue-loader@15.9.6
├─ vue-template-compiler@2.6.12
└─ vue@2.6.12
info All dependencies
├─ @vue/component-compiler-utils@3.2.0
├─ consolidate@0.15.1
├─ de-indent@1.0.2
├─ he@1.2.0
├─ merge-source-map@1.1.0
├─ vue-hot-reload-api@2.3.4
├─ vue-loader@15.9.6
├─ vue-style-loader@4.1.3
├─ vue-template-compiler@2.6.12
├─ vue-template-es2015-compiler@1.9.1
└─ vue@2.6.12
✨  Done in 8.07s.
Webpacker now supports Vue.js 🎉
```

### Vuetify

{% embed url="https://qiita.com/Ryoga_aoym/items/e1d91351389904240594" %}

### \[WIP] ERB / Vue 互換

{% embed url="https://fuqda.hatenablog.com/entry/2019/02/27/005809" %}

### \[WIP] Vue Rails 環境整備

{% embed url="https://qiita.com/tanaken0515/items/a6e9511fc6d8c0065dc1" %}

　commit:「Add Vue on Rails」 `dafe239`

* yarn install
  * Auto create `hello vue`
    * in javascrt packs
* application.html.erb setting
  * include helo vue
* routing & create html
