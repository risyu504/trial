# Node.js に関するメモ

このファイルは、Node.js に関するメモを記したものです。

このフォルダに関しての説明は、[`README.md`](./README.md) に記述しています。

## Node.js とは？

## Node.js を使う理由(目的)

## Node.js を使う注意点

## Node.js の使い方(導入方法)

## 以下、書き込む為の仮のコピー

- Sass からドキュメントを生成する。
  - npmスクリプトにコマンドを用意する。

    ```JSON:package.json
    "scripts": {
      "sassdoc00": "sassdoc ./Sass --dest ./Sassdoc"
    }
    ```

  - ターミナル(コマンドプロンプト)からコマンドを実行する。

    ```shell
    C:\Users\Public\Documents\Development> npm run sassdoc00
    ```

- Sass から CSS を生成する。
  - npmスクリプトにコマンドを用意する。

    ```JSON:package.json
    "scripts": {
      "sass00": "sass ./Sass/index.scss ./Stylesheet/index.css",
    }
    ```

  - ターミナル(コマンドプロンプト)からコマンドを実行する。

    ```shell
    C:\Users\Public\Documents\Development> npm run sass00
    ```

- Pug から HTML を生成する。
  - npmスクリプトにコマンドを用意する。

    ```JSON:package.json
    "scripts": {
      "pug00": "pug ./Pug/Html/Index --out ./Html --extension htm --pretty",
    }
    ```

  - ターミナル(コマンドプロンプト)からコマンドを実行する。

    ```shell
    C:\Users\Public\Documents\Development> npm run pug00
    ```

- 複数の処理を一度に実行する。
  - npmスクリプトにコマンドを用意する。

    ```JSON:package.json
    "scripts": {
      "sass00": "sass ./Sass/index.scss ./Stylesheet/index.css",
      "pug00": "pug ./Pug/Html/Index --out ./Html --extension htm --pretty",
      "set00": "npm-run-all sass00 && npm-run-all pug00",
    }
    ```

  - ターミナル(コマンドプロンプト)からコマンドを実行する。

    ```shell
    C:\Users\Public\Documents\Development> npm run set00
    ```

- Pug での開発
  - PUG開発用フォルダの `readme.md` ファイルの記述に従い、開発する。
- Sass での開発
  - Sass開発用フォルダの `readme.md` ファイルの記述に従い、開発する。
- Pug や Sass 以外での開発
  - それ用のフォルダをこのフォルダ直下に作成します。
  - 追加したフォルダに、その機能に関しての説明を記述した `readme.md` ファイルを作成します。
  - この `readme.md` ファイルに、追加した機能についての記述を行います。
  - npmスクリプトを記述して、実行環境を用意します。

### 開発用フォルダの用意

1. 既存の環境を留意しつつ、開発用フォルダを用意します。(例では、windowsのパブリックのドキュメントのフォルダにDevelopment という名前で開発フォルダを用意します)
2. 上記の フォルダ構成 に記述してあるフォルダを用意します。(HTML出力先, CSS出力先のフォルダ名は、本番環境での名称と同じが望ましいです。これは検証の時のパスの調整が容易になる為です。故に必要に応じて開発用フォルダの名称も変更は可能です。その場合、各コマンドや説明ファイルの記述の変更も必要となります。)

### Node.js と npm の準備

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

### npm のパッケージを管理

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

5. Pug から HTML を生成するパッケージをインストールします。(グローバルモードでインストールするので、既にインストールされている場合はそのまま利用する。) [pug-cli - npm](https://www.npmjs.com/package/pug-cli)

    ```shell
    C:\Users\Public\Documents\Development> npm install pug-cli -g
    ```

6. Sass から CSS を生成するパッケージをインストールします。 [sass - npm](https://www.npmjs.com/package/sass)

    ```shell
    C:\Users\Public\Documents\Development> npm install sass -g
    ```

7. Sass からドキュメントを生成するパッケージをインストールします。 [sassdoc - npm](https://www.npmjs.com/package/sassdoc)

    ```shell
    C:\Users\Public\Documents\Development> npm install sassdoc -g
    ```

8. npmスクリプトを並列または順次実行する為のパッケージをインストールします。 [npm-run-all - npm](https://www.npmjs.com/package/npm-run-all)

    ```shell
    C:\Users\Public\Documents\Development> npm install npm-run-all --save-dev
    ```

9. `npm install`によってインストールされた Nodeパッケージを確認します。

    ```shell
    C:\Users\Public\Documents\Development> npm list -g
    C:\Users\Public\Documents\Development> npm list
    ```

    - `npm list` : ローカルモードでインストールしたパッケージを一覧表示します。

### npmスクリプトを用意する

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

## 作成者

Copyright(C) 2022-2024 KOUTAN
