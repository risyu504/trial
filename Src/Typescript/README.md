# Typescriptエントリーポイントフォルダ

この `README.md` ファイルは、このフォルダに関しての説明を記述したファイルです。

## 概要

- このフォルダは、Typescriptで開発をするにあたっての**エントリーポイントファイル**(index.ts等)を収めるフォルダです。
- Javascriptを生成するファイルであり、import用の素材はここに置きません。
- [ソースフォルダ](../README.md)の下位ファルダとする事を、想定しています。

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

- index.tsの記述の例

    ```typescript
    import { fvCfUserAgent } from '../../Typescript/config';
    import { fvEvAddClickhAnchor, fbEvScrollAnchor, csEvAnchorInpage } from '../../Typescript/event';
    document.addEventListener('DOMContentLoaded', function(){
      fvCfUserAgent();
      fvEvAddClickhAnchor(csEvAnchorInpage, fbEvScrollAnchor);
    });
    ```

## 内部規約

1. 主に [コーディングルール](../../Document/codingrules.md) に準じます。
2. エントリーポイントファイルと import用のファイルを別々のフォルダに収めます。
3. このフォルダのフォルダ区分は、'Ep' です。
4. このフォルダのファイルに関する規約は、以下の通りとする。
    1. このフォルダのファイル区分は、以下の通りとする。
        - 現在はありません。
    2. エントリーポイントファイルなので、他から読み込まれる事への配慮は不要です。

## ナビ

- [開発ホーム](../../README.md)
  - [Pug開発](../../Pug/README.md)
  - [Sass開発](../../Sass/README.md)
  - [Typescript開発](../../Typescript/README.md)
  - [ソース](../README.md)
    - [データ用](../Data/README.md)
    - [Pug用](../Pug/README.md)
    - [Sass用](../Sass/README.md)
    - **Typescript用**
  - [出力先](../../Dest/README.md)
  - [書類倉庫](../../Document/README.md)

## 作成者

Copyright(C) 2024-2024 KOUTAN
