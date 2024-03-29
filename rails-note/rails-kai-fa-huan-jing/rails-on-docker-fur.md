---
description: Develop Rails on Docker / Mac M1 （多分Win その他でも同じ） 2022.01.01~
---

# Rails on Docker 導入フロー

### Why This?

M1環境でRails5系 + Ruby2系で MySQLまわりのbundleエラーが出る

Rails6\~ + Ruby3系だと出ない

OSやローカルに依存せず、汎用的なRailsダウングレード環境をM1で構築したい

## Rails on Docker

構築からテストファイルルーティングまで

### Note

* 新規RailsをDockerで作成（8度目くらいのリトライ、いつもどこかで改修出来ないバグが出る）
* 環境
  * M1 Mac
  * Homebrew、rbenv、nodenv->voltaなどは設定済

### Tree Now First Commit

新規作成ファイル内訳

```
.
├── Dockerfile
├── Gemfile
├── Gemfile.lock（カラファイル）
├── README.md（This）
└── docker-compose.yml
```

#### Gemfile

* Railsバージョン指定

```ruby
source 'https://rubygems.org'
gem 'rails', '5.2.6'
```

#### Dockerfile

```batch
FROM ruby:2.7.2 # FROM: Rubyバージョン
RUN apt-get update -qq && apt-get install -y build-essential nodejs指定 # RUN: コンテナー内で実行するコマンド。ubuntuでパッケージのインストール。
RUN mkdir /app # RUN: Dockerのルートディレクトリで /app（Rails）フォルダーを作成
WORKDIR /app # WORKDIR: 作業ディレクトリを/appに移動
COPY Gemfile /app/Gemfile # COPY: Gemファイルのコピー/移動
COPY Gemfile.lock /app/Gemfile.lock
RUN bundle install # RUN: install
COPY . /app # COPY: Dockerファイル内の内容をすべてコピー
```

#### docker-compose.yml

* 開発IPパス
* DB領域
  * パス
  * SQL
  * password

```batch
version: '3' # フォーマット
services:
  web: # ====== Railsコンテナの定義 ======
    build: . # 同階層のDockerfileからイメージを使用する
    command: bundle exec rails s -p 3000 -b '0.0.0.0' # 起動時のコマンド -p サーバー -b IPアドレス
    volumes:
      - .:/app # LocalとDockerの共有パス/接点
    ports:
      - 3333:3000 # く公開するポート番号>:くコンテナ内部の転送先ポート番号〉  => http://localhost:3333/
    depends_on:
      - db # 起動時にMySQLサーバーが先に起動する
    tty: true # debug用
    stdin_open: true # debug用
  db: # ====== MySQLサーバーコンテナの定義 ======
    platform:  linux/arm64/v8 # Mac M1対応
    image: mysql:5.7 # そのまま
    volumes:
      - db-volume:/var/lib/mysql # PC上にdb-volumeという名前でボリューム(データ保持領域)を作成。コンテナ上でDBを持たせず、PCローカルにDBを保存させる
    environment:
      MYSQL_ROOT_PASSWORD: password
volumes:
  db-volume: # 上記の定義
```

***

### Rails環境作成 use MySQL

```ruby
docker-compose run web rails new . --force --database=mysql

=begin
- rails new.でコマンド実行時のディレクトリ上に、新しいRaisプロジェクトのファイルを作成します
- forceは、既存ファイル上書きするオプション
- dbdatabase= mysqlは MYSQLを使用する設定を入れるオプション
```

?: なにか分からないので一旦無視

> bundle exec spring binstub --all

* エラー
  * `gem install mysql2 -v '0.5.3'` ?
* いったん無視
  * ローカル上はこれは解消しなかった

### 初期設定

#### イメージのbuild、取り込み

```
docker-compose build
```

* 出たエラー
  * `ERROR: Service 'web' failed to build : Build failed`
  * 対応 = 実際はやっていなく、 無視して`docker-compose build`を再実行
    * `docker-compose run web bundle update`

### DB設定

#### database.ymlの設定

* パスワード # TODO: 本格開発時は再設定し、envなどで個人で隠蔽する
* ホスト

```yml
  password: password
  host: localhost
```

#### コマンド

現在のディレクトリにある、docker-compose.ymlに基づいて、コンテナーを起動するコマンド:

```
docker-compose up -d
```

確認：

```
docker-compose ps
```

bundle exec rake

* Rails環境にインストールされているrakeコマンドを実行
* rake db:create = Railsで使用するデータベースをMYSQLサーバ上に作成してくれます
* bundle exec以降が実行コマンド
* rake db:create=まだデーターがない時にDBを作成するコマンド

```
docker-compose run web bundle exec rake db:create
```

### Docker

* 起動
  * docker-compose up -d
* Stop
  * docker-compose stop
* 削除（再度立ち上げれば戻るので大丈夫）
  * docker-compose down

#### 注意点

* 起動`-d`無しだと起動ログの監視から外れ、再起動時にpidエラーが出るかも
  * docker-compose up
* 対応
  * `rm tmp/pids/server.pid`

### ブラウザ確認：

* http://localhost:3333/
* 他とかぶらないた対策で3333にしている

### 起動時にシェルでserver.pidを消す設定

docker-compose.yml

```
command: bash -c "rm -f tmp/pids/server.pid; bundle exec rails s -p 3000 -b '0.0.0.0'"
```

### ---

### 掲示板を作成する基盤

* 必要な作成ファイル
  * コントローラー
  * アクション
  * ルーティング
  * HTML

#### コントローラーとアクション

app/controllers/boards\_controller.rb

```ruby
class BoardsController < ApplicationController
  def index
  end
end
```

#### ルーティング

config/routes.rb

```ruby
Rails.application.routes.draw do
  # get 'boards', to: 'boards#index'
  root 'boards#index'
end
```

#### HTML

app/views/boards/index.html.erb

```html
<h1>掲示板</h1>
<p>lorem ipsum dolor sit amet, consectetur adip</p>
```

![http://localhost:3333/](../../.gitbook/assets/image.png)

