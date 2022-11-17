<!-- omit in toc -->
# tutorial-jekyll

Jekyll のチュートリアル用リポジトリです。

## 1. 操作メモ

### 1.1. 環境構築

1. 参考文献をもとに Ruby をインストール。

    ```shell
    $ sudo apt-get install ruby-full build-essential zlib1g-dev
    $ ruby -v
    $ gem -v
    ```

2. 以下を `.zshrc` へ追加。

    ```shell
    # Install Ruby Gems to ~/gems
    export GEM_HOME="$HOME/gems"
    export PATH="$HOME/gems/bin:$PATH"
    ```

3. シェルを再起動または `.zshrc` を再読み込みして環境変数のチェック。

    ```shell
    $ source ~/.zshrc
    $ env | grep gems
    ```

4. Jekyll をインストール。

    ```shell
    $ gem install jekyll bundler
    # コマンド実行後、出力が出るまでしばらく時間かかった
    $ jekyll --version
    ```

### 1.2. チュートリアル

```shell
# ルートディレクトリを作成
$ mkdir docs
$ cd docs

# 設定ファイルを作成
# 作成したらチュートリアルに記載のあるコードを3つのファイルへ記述する
$ touch _config.yml index.md default.html
$ mkdir _layouts && mv default.html _layouts

# serve でサイトをサーバーに構築
$ jekyll serve

# Server address: http://127.0.0.1:4000 と出ているので localhost へブラウザでアクセスする
```

うおー

![結果](images/20221117_preview.jpg)

`index.md` を基に html ファイル `_site/index.html` も生成された。

```shell
.
├── docs
│   ├── _layouts
│   │   └── default.html
│   ├── _site             ← 生成
│   │   └── index.html   ← 生成
│   ├── _config.yml
│   └── index.md
└── README.md
```

`index.md`

```md
---
title: My page
layout: default
---

# {{ page.title }}

Content is written in [Markdown](https://learnxinyminutes.com/docs/markdown/). Plain text format allows you to focus on your **content**.

<!--
You can use HTML elements in Markdown, such as the comment element, and they won't be affected by a markdown parser. However, if you create an HTML element in your markdown file, you cannot use markdown syntax within that element's contents.
-->
```

`_site/index.html`

```html
<!DOCTYPE html>
<html>
  <body>
     <h1 id="my-page">My page</h1>

<p>Content is written in <a href="https://learnxinyminutes.com/docs/markdown/">Markdown</a>. Plain text format allows you to focus on your <strong>content</strong>.</p>

<!--
You can use HTML elements in Markdown, such as the comment element, and they won't be affected by a markdown parser. However, if you create an HTML element in your markdown file, you cannot use markdown syntax within that element's contents.
-->

  </body>
</html>
```

## 2. 参考文献

- [インストール | Jekyll • シンプルで、ブログのような、静的サイト](http://jekyllrb-ja.github.io/docs/installation/)
- [Jekyll on Ubuntu | Jekyll • シンプルで、ブログのような、静的サイト](http://jekyllrb-ja.github.io/docs/installation/ubuntu/)
- [HTMLサイトをJekyllに変換 | Jekyll • シンプルで、ブログのような、静的サイト](http://jekyllrb-ja.github.io/tutorials/convert-existing-site-to-jekyll/)
