# 環境の準備 readme

このファイルは、開発フォルダなどの環境の準備に関しての説明を記したものです。

このフォルダに関しての説明は、[`README.md`](./README.md) に記述しています。

- [環境の準備 readme](#環境の準備-readme)
  - [概要](#概要)
  - [開発する予定の物](#開発する予定の物)
  - [開発に用いる予定の物](#開発に用いる予定の物)
  - [開発用フォルダの用意](#開発用フォルダの用意)
  - [VSCode の準備](#vscode-の準備)
  - [Node.js と npm の準備](#nodejs-と-npm-の準備)
  - [npm のパッケージを管理](#npm-のパッケージを管理)
    - [共通した説明](#共通した説明)
    - [gulp の準備](#gulp-の準備)
    - [Pug に関する説明](#pug-に関する説明)
    - [Sass に関する説明](#sass-に関する説明)
    - [JavaScript に関する説明](#javascript-に関する説明)
    - [npmスクリプト に関する説明](#npmスクリプト-に関する説明)
    - [最終確認](#最終確認)
  - [gulpfile.jsを用意する](#gulpfilejsを用意する)
  - [npmスクリプトを用意する](#npmスクリプトを用意する)
  - [Sassのドキュメント, CSS, HTMLの生成](#sassのドキュメント-css-htmlの生成)
  - [作成者](#作成者)

## 概要

- 開発環境の再構築の為に、ここに情報を残しています。
- 開発者が一人なので集団での意識統一の面はないのですが、過去の自分と今の自分の意識統一という意識で規約を用意しています。
- 主な構成は、**目的の確認**, **ツールの確認**, **フォルダの用意**, **環境の確認**, **ツールの準備** などになります。
- Publicユーザーで例示していますが、アカウントを意識しないで例示する為に選んだだけで、使い方などは意識していません。

## 開発する予定の物

1. HTML - Webページの開発の為に HTML を用いる。
2. CSS - Webページの装飾の為に CSS を用いる。
3. JavaScript - Webページの機能追加の為に JavaScript を用いる。

## 開発に用いる予定の物

1. VSCode - ソースコードエディタとして VSCode を用いる。
2. Node.js - 実行環境として Node.js を用いる。
3. npm - Node.jsのパッケージ管理として npm を用いる。
4. Gulp - 開発作業を自動化する「タスクランナー」として Gulp を用いる。
5. gulp-pug - HTML を作成する為のテンプレートエンジンとして Pug を用いる。そのコンパイルの為に、gulp-pugモジュール を用いる。
6. sass - CSS を作成する為のCSS拡張言語として Sass を用いる。そのコンパイルの為に、sassモジュール を用いる。
7. gulp-sass - sassモジュール と gulpモジュール を連携する為に、gulp-sassモジュール を用いる。
8. sassdoc - Sass の資料作成の為に SassDoc を用いる。その実行の為に sassdocモジュール を用いる。

## 開発用フォルダの用意

1. 既存の規約を調べます。使用する制限など要注意です。規約がないとか明文化されていない場合は、規約文書を作成します。
2. 既存の環境を留意しつつ、規約に従って開発用フォルダを用意します。(例では、windowsのパブリックのドキュメントのフォルダにDevelopment という名前で開発フォルダを用意します)
3. 下記の フォルダ構成 を参考にして、フォルダを用意します。
    - HTML出力先, CSS出力先のフォルダ名は、本番環境での名称と同じが望ましいです。これは検証の時のパスの調整が容易になる為です。故に必要に応じて開発用フォルダの名称も変更は可能です。その場合、各コマンドや説明ファイルの記述の変更も必要となります。
    - 運用環境の都合で HTML と スタイルシートを同じフォルダに置く必要がある場合は、１つの出力先フォルダとする事も問題ありません。

- Development
  - Dest - 生成物出力先用フォルダ(配下のフォルダ名は、本番環境での名称と同じ)
    - Html - HTML出力先フォルダ
    - Img - 出力先確認用画像フォルダ
    - Javascript - Javascript出力先フォルダ
    - Jsdoc - JsDoc出力先フォルダ
    - Sassdoc - SassDoc出力先フォルダ
    - Stylesheet - StyleSheet出力先フォルダ
    - Theme - Theme(StyleSheet)出力先フォルダ
  - Pug - Pug開発資源用フォルダ
  - Sass - Sass開発資源用フォルダ
  - Src - 開発用データフォルダ
    - Pugcontent - Pug開発データ用フォルダ
    - Pugentry - Pugエントリーファイル用フォルダ
    - Sass - Sassエントリーファイル用フォルダ
    - Sasstheme - Theme(Sass)エントリーファイル用フォルダ
  - Typescript - Typescript用フォルダ

## VSCode の準備

1. ソースコードを作成する為のエディタとして、VSCode を選択します。
2. VSCode をインストールします。(詳細は、後日に作成予定)

## Node.js と npm の準備

1. Node.jsを確認します。

    ```shell
    C:\Users\Public\Documents\Development> node --version
    ```

2. nvm(nvm-windows) を確認します。

    ```shell
    C:\Users\Public\Documents\Development> nvm --version
    ```

3. Node.js がなくて nvm がない場合は、nvm(nvm-windows) をインストールします。Node.js があって nvm がない場合は、既存の環境が nvm の使用を許す場合のみ nvm(nvm-windows) をインストールします。

    - [Releases · coreybutler/nvm-windows · GitHub](https://github.com/coreybutler/nvm-windows/releases) からダウンロードして nvm-windows をインストールします。
    - nvm(nvm-windows) を確認します。

        ```shell
        C:\Users\Public\Documents\Development> nvm --version
        ```

4. Node.js がない場合、nvm を用いて Node.js をインストールします。

    - インストール可能なNode.jsのバージョンを確認します。

        ```shell
        C:\Users\Public\Documents\Development> nvm list available
        ```

    - 特に選択する理由がない場合は、LTS(Long Term Support)の最新バージョンをインストールします。

        ```shell
        C:\Users\Public\Documents\Development> nvm install 18.12.1
        ```

5. 使用するNode.jsのバージョンを指定します。

    - パブリックでは管理者権限が必要なので、ターミナル(コマンドプロンプト)を管理者権限で立ち上げます。以下のコマンドを実行する事でも、新しいウインドウになりますが、管理者権限のターミナル(コマンドプロンプト)が起動できます。

        ```shell
        powershell start-process cmd -verb runas
        ```

    - インストールしたNode.jsのバージョンの一覧を確認します。

        ```shell
        C:\Users\Public\Documents\Development> nvm list
        ```

    - 使用するNode.jsのバージョンを指定します。(インストールしたバージョンが１つの場合でも、使用する指定は必要です。)(管理者権限が必要な場合があります。)

        ```shell
        C:\Users\Public\Documents\Development> nvm use 18.12.1
        ```

    - 使用するNode.jsのバージョンを確認します。

        ```shell
        C:\Users\Public\Documents\Development> node --version
        ```

6. npm を確認します。

    ```shell
    C:\Users\Public\Documents\Development> npm --version
    ```

## npm のパッケージを管理

### 共通した説明

1. グローバルモードでインストールしたパッケージを確認します。

    ```shell
    C:\Users\Public\Documents\Development> npm list -g
    ```

    既にインストールされているパッケージは、利用できますが既に他で利用されている可能性があるので注意が必要です。

2. ローカルモードでインストールしたパッケージを確認します。

    ```shell
    C:\Users\Public\Documents\Development> npm list
    ```

    既存のフォルダを使っている場合は、そこにプロジェクトが既にあってローカルモードでインストールしたパッケージがある場合があります。

3. 不要なNodeパッケージをアンインストールします。

    ```shell
    C:\Users\Public\Documents\Development> npm uninstall (パッケージ名) -g
    C:\Users\Public\Documents\Development> npm uninstall (パッケージ名)
    ```

    パッケージのインストールのモードと、本当に不要と確認できた範囲に注意が必要です。

4. プロジェクトを初期化します。(既存のフォルダを使っている場合は、そこにプロジェクトが既にある場合があるので注意が必要です。package.jsonファイルがそのフォルダに既に存在する場合は、プロジェクトが既にある可能性が高いです。)

    ```shell
    C:\Users\Public\Documents\Development> npm init
    ```

### gulp の準備

1. gulpを確認します。

    ```shell
    C:\Users\Public\Documents\Development> gulp --version
    ```

2. gulp パッケージをインストールします。[Quick Start | gulp.js](https://gulpjs.com/docs/en/getting-started/quick-start)

    ```shell
    C:\Users\Public\Documents\Development> npm install --global gulp-cli
    C:\Users\Public\Documents\Development> npm install --save-dev gulp
    ```

3. gulpfile を作成します。

    ```js gulpfile.js
    function defaultTask(cb) {
        // place code for your default task here
        cb();
    }

    exports.default = defaultTask
    ```

4. 動作確認 をします。

    ```shell
    C:\Users\Public\Documents\Development> gulp
    ```

    ```shell
    [18:41:23] Using gulpfile C:\Users\Public\Documents\Development\gulpfile.js
    [18:41:23] Starting 'default'...
    [18:41:23] Finished 'default' after 12 ms
    ```

5. gulp 関係のパッケージの追加

    - エラー通知

        ```shell
        C:\Users\Public\Documents\Development> npm install --save-dev gulp-notify
        ```

    - エラーが発生した場合にタスクが停止するのを防止

        ```shell
        C:\Users\Public\Documents\Development> npm install --save-dev gulp-plumber
        ```

    - 処理中のファイルをログに表示

        ```shell
        C:\Users\Public\Documents\Development> npm install --save-dev gulp-debug
        ```

    - ファイルフィルター

        ```shell
        C:\Users\Public\Documents\Development> npm install --save-dev gulp-filter
        ```

    - ファイル名の変更

        ```shell
        C:\Users\Public\Documents\Development> npm install --save-dev gulp-rename
        ```

    - 複数の JSON ファイルを 1 つのファイルにディープマージする

        ```shell
        C:\Users\Public\Documents\Development> npm install --save-dev gulp-merge-json
        ```

### Pug に関する説明

1. Pug から HTML を生成するパッケージをインストールします。(グローバルモードでインストールするので、既にインストールされている場合はそのまま利用する。) [pug-cli - npm](https://www.npmjs.com/package/pug-cli)

    ```shell
    C:\Users\Public\Documents\Development> npm install pug-cli -g
    ```

2. gulp を用いて Pug を使う場合のパッケージをインストールします。

    ```shell
    C:\Users\Public\Documents\Development> npm install --save-dev gulp-pug
    ```

### Sass に関する説明

1. Sass から CSS を生成するパッケージをインストールします。 [sass - npm](https://www.npmjs.com/package/sass)

    ```shell
    C:\Users\Public\Documents\Development> npm install sass -g
    ```

2. Sass からドキュメントを生成するパッケージをインストールします。 [sassdoc - npm](https://www.npmjs.com/package/sassdoc)

    ```shell
    C:\Users\Public\Documents\Development> npm install sassdoc -g
    ```

### JavaScript に関する説明

1. JavaScriptをトランスコンパイル, バンドルするパッケージをインストールします。[webpack - npm](https://www.npmjs.com/package/webpack)

    ```shell
    C:\Users\Public\Documents\Development> npm install --save-dev webpack
    C:\Users\Public\Documents\Development> npm install --save-dev webpack-cli
    C:\Users\Public\Documents\Development> npm install -g typescript
    C:\Users\Public\Documents\Development> npm install --save-dev ts-loader
    ```

2. Javascript からドキュメントを生成するパッケージをインストールします。 [jsdoc - npm](https://www.npmjs.com/package/jsdoc)

    ```shell
    C:\Users\Public\Documents\Development> npm install -g jsdoc
    ```

### npmスクリプト に関する説明

1. npmスクリプトを並列または順次実行する為のパッケージをインストールします。 [npm-run-all - npm](https://www.npmjs.com/package/npm-run-all)

    ```shell
    C:\Users\Public\Documents\Development> npm install npm-run-all --save-dev
    ```

### 最終確認

1. `npm install`によってインストールされた Nodeパッケージを確認します。

    ```shell
    C:\Users\Public\Documents\Development> npm list -g
    C:\Users\Public\Documents\Development> npm list
    ```

    - `npm list` : ローカルモードでインストールしたパッケージを一覧表示します。

## gulpfile.jsを用意する

1. gulpfile を分割したいので、gulpfile.jsファイル ではなくて gulpfile.jsフォルダ を作成する。そのフォルダの中に index.jsファイル を作成して、gulpfile.jsファイル で記述していた内容を記す。

## npmスクリプトを用意する

1. npmスクリプトを記述して、生成用のコマンドを用意する。

    ``` npm package.json
    "scripts": {
      "test": "echo \"Error: no test specified\" && exit 1"
      "sass01": "sass ./Sass/front.scss ./Stylesheet/front.css",
      "sass01t": "sass ./Sass/themefront.scss ./Theme/themefront.css",
      "sass02": "sass ./Sass/index.scss ./Stylesheet/index.css",
      "sass02t": "sass ./Sass/themeindex.scss ./Theme/themeindex.css",
      "sass03": "sass ./Sass/description.scss ./Stylesheet/description.css",
      "sass03t": "sass ./Sass/themedesc.scss ./Theme/themedesc.css",
      "sass04": "sass ./Sass/specification.scss ./Stylesheet/specification.css",
      "sass04t": "sass ./Sass/themespec.scss ./Theme/themespec.css",
      "sass00": "npm-run-all sass01 && npm-run-all sass02 && npm-run-all sass03 && npm-run-all sass04",
      "sass00t": "npm-run-all sass01t && npm-run-all sass02t && npm-run-all sass03t && npm-run-all sass04t",
      "sass": "npm-run-all sass01 && npm-run-all sass01t && npm-run-all sass02 && npm-run-all sass02t && npm-run-all sass03 && npm-run-all sass03t && npm-run-all sass04 && npm-run-all sass04t",
      "pug00": "pug ./Pug/Html/Index --out ./Html --extension htm --pretty",
      "pug01": "pug ./Pug/Html/What --out ./Html --extension htm --pretty",
      "pug02": "pug ./Pug/Html/Write --out ./Html --extension htm --pretty",
      "pug03": "pug ./Pug/Html/Rendering --out ./Html --extension htm --pretty",
      "pug04": "pug ./Pug/Html/Classification --out ./Html --extension htm --pretty",
      "pug05": "pug ./Pug/Html/Page --out ./Html --extension htm --pretty",
      "pug": "npm-run-all pug00 && npm-run-all pug01 && npm-run-all pug02 && npm-run-all pug03 && npm-run-all pug04 && npm-run-all pug05",
      "sassdoc": "sassdoc ./Sass --dest ./Sassdoc"
    }
    ```

## Sassのドキュメント, CSS, HTMLの生成

1. Sass からドキュメントを生成するコマンドを実行する。

    - `npm run sassdoc` : Sass から ドキュメント を一括生成します。

2. Sass から CSS を生成するコマンドを実行する。

    - `npm run sass` : Sass から CSS を一括生成します。

3. Pug から HTML を生成するコマンドを実行する。

    - `npm run pug` : Pug から HTML を一括生成します。

## 作成者

Copyright(C) 2022-2024 KOUTAN
