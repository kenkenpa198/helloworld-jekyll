<!-- omit in toc -->
# tutorial-jekyll

Jekyll のチュートリアル用リポジトリです。

## 1. 公開しているページ

- トップページ  
[https://kenkenpa198.github.io/tutorial-jekyll/](https://kenkenpa198.github.io/tutorial-jekyll/)
- マークダウン記法のテスト用ページ  
[https://kenkenpa198.github.io/tutorial-jekyll/notes/contents/20221118_show_markdown_test.html](https://kenkenpa198.github.io/tutorial-jekyll/notes/contents/20221118_show_markdown_test.html)

## 2. 環境構築メモ

- [インストール | Jekyll • シンプルで、ブログのような、静的サイト](http://jekyllrb-ja.github.io/docs/installation/)
- [Jekyll on Ubuntu | Jekyll • シンプルで、ブログのような、静的サイト](http://jekyllrb-ja.github.io/docs/installation/ubuntu/)

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

## 3. ビルド

- [HTMLサイトをJekyllに変換 | Jekyll • シンプルで、ブログのような、静的サイト](http://jekyllrb-ja.github.io/tutorials/convert-existing-site-to-jekyll/)

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

## 4. チュートリアルメモ

⇒ [チュートリアルメモ](%E3%83%81%E3%83%A5%E3%83%BC%E3%83%88%E3%83%AA%E3%82%A2%E3%83%AB%E3%83%A1%E3%83%A2.md)

## 5. 参考文献

- [インストール | Jekyll • シンプルで、ブログのような、静的サイト](http://jekyllrb-ja.github.io/docs/installation/)
- [Jekyll on Ubuntu | Jekyll • シンプルで、ブログのような、静的サイト](http://jekyllrb-ja.github.io/docs/installation/ubuntu/)
- [HTMLサイトをJekyllに変換 | Jekyll • シンプルで、ブログのような、静的サイト](http://jekyllrb-ja.github.io/tutorials/convert-existing-site-to-jekyll/)
