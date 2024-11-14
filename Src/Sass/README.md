# Sassエントリーポイントフォルダ

この `README.md` ファイルは、このフォルダに関しての説明を記述したファイルです。

## 概要

- このフォルダは、SCSSで開発をするにあたっての**エントリーポイントファイル**を収めるフォルダです。
- CSSを生成するファイルであり、開発用の素材はここに置きません。
- [ソースフォルダ](../README.md)の下位ファルダとする事を、想定しています。

## 使い方

- npmスクリプト(package.json)での記述の例

    ```json
    "scripts": {
      "sass": "sass ./Src/Sass/sample.scss ./Dest/Stylesheet/sample.css",
    }
    ```

## 内部規約

1. 主に [コーディングルール](../../Document/codingrules.md) に準じます。
2. このフォルダのフォルダ区分は、'**Ge**'(Generation) です。
3. このフォルダのファイルに関する規約は、以下の通りとする。
    1. このフォルダのファイル区分は、以下の通りとする。
        - 現在はありません。
    2. エントリーポイントファイルなので、他から読み込まれる事への配慮は不要です。
    3. ファイル名は、生成するCSSと同一とする。(拡張子だけ異なる)

## ナビ

- [開発ホーム](../../README.md)
  - [Pug開発](../../Pug/README.md)
  - [Sass開発](../../Sass/README.md)
  - [Typescript開発](../../Typescript/README.md)
  - [ソース](../README.md)
    - [データ用](../Data/README.md)
    - [Pug用](../Pug/README.md)
    - **Sass用**
    - [Typescript用](../Typescript/README.md)
  - [出力先](../../Dest/README.md)
  - [書類倉庫](../../Document/README.md)

## 作成者

Copyright(C) 2022-2024 KOUTAN
