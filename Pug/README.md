# Pug開発フォルダ readme

この `readme.md` ファイルは、このフォルダに関しての説明を記述したファイルです。

## 概要

- このフォルダは、Pugを用いて HTML を作成する為のフォルダです。
- [開発フォルダ](../README.md)の下位フォルダとする事を、想定しています。
- クラス属性の編集の容易さを意識して、CSSの設計に合わせて Pugでも FLOCSSを基調としたフォルダ構成にします。(出来るだけファイルも含めて１対１の対応とします。)
- このフォルダ直下には、ファイルは説明などのファイルだけとします。
- HTML を生成する Pug のファイル(エントリーポイントファイル, コンテンツファイル)は、一括管理, 一括生成を考えてそれ用のフォルダを用意します。(`../Src/Pugentry`, `../Src/Pugcontent`)
- コンパイル後の HTML は、仮の別フォルダに生成します。(`../Dest`)

---

- [Pug](https://pugjs.org/api/getting-started.html) は、HTMLを記述する為のテンプレートエンジンです。
- [FLOCSS](https://github.com/hiloki/flocss) は、CSS設計の一つです。
- エントリポイントとは、実行する際に、一番最初に実行する事になっている箇所の事です。
- コンテンツとは、中身, 内容の事です。ここでは、記事自体などを指します。(ここでは、エントリポイントとコンテンツを別ファイルにしています。)

## ナビ

- [開発ホーム](../README.md)
  - **Pug開発**
  - [Sass開発](../Sass/README.md)
  - [Typescript開発](../Typescript/README.md)
  - [ソース](../Src/README.md)
  - [出力先](../Dest/README.md)

## 作成者

Copyright(C) 2022-2024 KOUTAN
