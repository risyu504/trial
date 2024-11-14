# スクリプト用フォルダ

この `README.md` ファイルは、このフォルダに関しての説明を記述したファイルです。

## 概要

- このフォルダは、**Typescript**をコンパイル, Webpackする時の**Javascript**の出力先のフォルダです。
- 出力結果をその場で検証できる様に、フォルダ名は運用する環境と同じにします。
- 他の出力結果をその場で検証できる様に、生成したスクリプトだけでなく、検証用に別途用意したスクリプトも置きます。
- [出力先フォルダ](../README.md)の下位フォルダとする事を、想定しています。

## 使い方


- webpack.config.jsでの記述の例

    ```javascript
    const path = require('path')
    module.exports = {
      mode: 'development',
      entry: { index: path.join(__dirname', 'Src', 'Typescript', 'index.ts') },
      output: { path: path.join(__dirname, 'Dest', 'Javascript'), filename: 'index.js' },
      module: { rules: [{ test: /\.ts$/, use: 'ts-loader', },], },
      resolve: { extensions: ['.ts', '.js',], },
    }
    ```

- npmスクリプト(package.json)での記述の例

    ```json
    "scripts": {
      "wp00": "webpack --mode=production"
    }
    ```

## 内部規約

1. 主に [コーディングルール](../../Document/codingrules.md) に準じます。
2. アップロード用フォルダへ、コンパイルしたJavascriptの**直接の出力**を禁じます。
    1. **Typescript**をコンパイルする時の**Javascript**の出力先は、ここです。
    2. ここで検証した後に、アップロード用フォルダへコピーします。
3. 原則として運用する環境と異なるファイルを置くことは禁止する。
    1. この `README.md` ファイルなどの、説明用のファイルは配置してよい。
    2. 検証の為に一時的なセーブファイルを置くことも良いが、使用後は片づける事。

## ナビ

- [開発ホーム](../README.md)
  - [Pug開発](../../Pug/README.md)
  - [Sass開発](../../Sass/README.md)
  - [Typescript開発](../../Typescript/README.md)
  - [ソース](../../Src/README.md)
  - [出力先](../README.md)
    - [スタイルシート用](../Css/README.md)
    - **スクリプト用**
  - [書類倉庫](../../Document/README.md)

## 作成者

Copyright(C) 2022-2024 KOUTAN

