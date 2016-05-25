# 避難所てだすけくん Web サイト

[浜松職業能力開発短期大学校](http://www3.jeed.or.jp/shizuoka/college/)電子情報技術科で製作している[「避難所てだすけくん」の Web サイト](http://hinanjo-tedasukekun.github.io/)のリポジトリです。

## 編集の準備

ソースコードは Git を使ってダウンロード（クローン）します。Git がインストールされていない場合はインストールしておいてください。

以下のコマンドでクローンします。作業ディレクトリは仮に `/path/to/workspace` と書いているので、実際の場所を指定してください。

```sh
cd /path/to/workspace
git clone https://github.com/hinanjo-tedasukekun/hinanjo-tedasukekun.github.io.git

# /path/to/workspace/hinanjo-tedasukekun.github.io/ に
# ソースコードが含まれているので
# 以降はそこで作業します
cd hinanjo-tedasukekun
```

この Web サイトは Ruby 製ツールの [Jekyll](http://jekyllrb-ja.github.io/) を使って構築されています。Ruby のインストールのほか、ライブラリのインストールが必要です。

Ruby のインストール後、以下のコマンドを実行してライブラリをインストールします。

```sh
# /path/to/workspace/hinanjo-tedasukekun.github.io/ 内で
gem install bundler # 失敗する場合は sudo gem install bundler
bundle install --path=vendor/bundle
```

以上で準備は完了です。

## 編集方法

はじめに、作業ディレクトリを現在アップロードされている状態と同期します。以下のコマンドで「プル」という同期作業を行います。

```sh
# /path/to/workspace/hinanjo-tedasukekun.github.io/ 内で
git pull
```

その後、作業ディレクトリ内のファイルを編集します。ニュースのファイルは `/_posts/` ディレクトリ以下のファイルを、それ以外のファイルは例えば [about.html](about.html) を同じディレクトリにコピーして少しずつ変えていくとよいでしょう。形式については HTML（.html）あるいは Markdown（.md；[書き方の例](http://qiita.com/tbpgr/items/989c6badefff69377da7)）で書くことができますが、レイアウトの都合上 HTML にしなければならない場合が多いかもしれません。

画像は `/img/` 以下に、スタイルシートは `/css/` 以下に置きます。

### 部品

サイトのテーマ（見た目）は「[Bootstrap](http://getbootstrap.com/)」というフレームワーク上に作られています。以下のページにある部品のサンプルコードを貼り付けて変えていくと、狙った見た目にしやすいです。

* [CSS · Bootstrap](http://getbootstrap.com/css/)
* [Components · Bootstrap](http://getbootstrap.com/components/)

### 確認

編集時は以下のコマンドで Web サーバーを起動しておくと確認が簡単になります。

```sh
# /path/to/workspace/hinanjo-tedasukekun.github.io/ 内で
bundle exec jekyll serve
# 終了させる場合は Ctrl + C を押す
```

このように Web サーバーを起動しておくと、http://localhost:4000/ より編集中のサイトを確認することができます。

### 記録

変更内容がある程度固まったら「コミット」という記録作業を行います。以下のコマンドを実行します。

```sh
# 現在の状態を確認する
git status
# 赤文字で編集したファイル、追加したファイルが出てくる

# 「記録するファイル」を設定する（ステージング）
git add 編集・追加したファイル

# 再度状態を確認する
git status
# 緑文字で記録するように設定したファイルが出てくる

# 記録を行う
git commit
# vi が起動するので、1 行目に何をしたかを簡潔に書く
# :wq で保存終了すると作業内容が記録される

# 作業が記録されたことを確認する
git log
```

## Git について

Git については以下のサイトを参考にしてください。

* [Gitを使ったバージョン管理【Gitの基本】 | サルでもわかるGit入門 〜バージョン管理を使いこなそう〜 | どこでもプロジェクト管理バックログ](http://www.backlog.jp/git-guide/intro/intro1_1.html)
    * 「お使いのパソコンの環境を選んで下さい。」という欄では「コンソールを選択」を選びます。
* [Git 入門](http://www.slideshare.net/y-uti/git-41040074)
* [Git - Book](https://git-scm.com/book/ja/v2)

## テーマ

Dean Attali 氏が作成した「[Beautiful Jekyll](https://github.com/daattali/beautiful-jekyll)」というテーマを使っています。詳しい編集方法（英語）はこのテーマのサイトにも書かれています。
