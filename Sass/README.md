# Sass開発フォルダ readme

この `readme.md` ファイルは、このフォルダに関しての説明を記述したファイルです。

- [Sass開発フォルダ readme](#sass開発フォルダ-readme)
  - [概要](#概要)
  - [使い方](#使い方)
  - [環境](#環境)
  - [内部規約](#内部規約)
  - [構成](#構成)
  - [参照](#参照)
  - [ナビ](#ナビ)
  - [作成者](#作成者)

## 概要

- このフォルダは、Sassを用いて CSS を作成する為のフォルダです。
- [開発フォルダ](../README.md)の下位フォルダとする事を、想定しています。
- Sassを用いる理由は、セレクタの編集(管理)を用意にする為です。
- SassにはSASSとSCSSの２つの構文がありますが、ここでは**SCSS構文**を採用します。
- このフォルダ直下には、ファイルは説明などのファイルだけとします。
- CSS を生成する SCSS のファイルは、一括管理, 一括生成を考えてそれ用のフォルダを用意します。(`../Src/Sass`, `../Src/Sasstheme`)
- コンパイル後の CSS は、仮の別フォルダに生成します。(`../Dest/Stylesheet`, `../Dest/Theme`)
- 読み込み用の「パーシャル」なファイルなどは、下位のフォルダに保持します。フォルダ構成は、FLOCSSを基調とします。
- ルールセットは mixin で編集, 出力する事にして、FLOCSS でのモジュラーなアプローチを実現する様にします。
- セレクタの編集は、編集用の関数を用意して命名規則に合わせます。
- クラスの命名規則は、MindBEMding を考慮しますが、要素セレクタだけとかオリジナル命名規約も考慮します。
- Extend(拡張)は、意味を持って行うものとする。内容が同じという事で、一緒にしてはいけません。意味が同じであれば、レイヤーやモジュールを超えても良いとする。尚、記述箇所の問題は、プレースホルダーセレクターを用いて対応する。

---

- [Sass](https://sass-lang.com/)は、CSSのメタ言語です。
- SCSSは、Sassの構文の一つです。
- [BEM](https://github.com/juno/bem-methodology-ja/blob/master/definitions.md)は、CSS設計の一つです。
- [FLOCSS](https://github.com/hiloki/flocss)は、CSS設計の一つです。
- [MindBEMding](https://csswizardry.com/2013/01/mindbemding-getting-your-head-round-bem-syntax/) は、BEMをCSSのクラス名に適用するために作られた命名規則です。
- オリジナル命名規約は、BEM でのブロック(Block)だけクラス名を付け、エレメント(Element)に当たる部分は要素セレクタで表す規則です。エレメント(Element)の組み合わせや配置もブロック(Block)のクラスセレクタで表します。

## ナビ

- [開発ホーム](../README.md)
  - **Sass開発**
  - [Pug開発](../Pug/README.md)
  - [Typescript開発](../Typescript/README.md)
  - [ソース](../Src/README.md)
  - [出力先](../Dest/README.md) 生成物出力先

## 作成者

Copyright(C) 2022-2024 KOUTAN
