# セレクタの命名規則

このファイルは、開発の設計方針として、「セレクタの命名規則」をまとめたものです。

このフォルダについての説明は、[`README.md`](./README.md) に記載しています。

## セレクタ(CSS)の命名規則

1. BEM(MindBEMding), FLOCSS のクラス名の付け方も、考慮します。
2. 要素セレクタだけでも可能か否かも、考慮します。
3. オリジナル命名規約も、考慮します。

## 形式

「.r-block__element--modifier」(推奨)  
「.rBlockPattern」(BEM不採用の場合)

|位置|決まり|
|:-:|----|
|プレフィックス|英字小文字(必須)|
|１項目目|英字小文字(必須)|
|２項目目|英字小文字(任意)|
|３項目目|英字小文字(任意)|

## 接頭語: プレフィックス

「prefix-xxxxx」

ハイフンで１項目目のブロックの前に付与する。  
BEM不採用の場合はハイフンは不要です。

|接頭語|内容|
|:-:|----|
|f|Foundation|
|l|Layout|
|c|Component|
|p|Project|
|u|Utility|
|t|Theme|
|h|HTML|
|j|JavaScript|
|r|risyu|
|rl|risyu.Layout|
|rc|risyu.Component|
|rp|risyu.Project|
|ru|risyu.Utility|

## １項目目: ブロック

「prefix-block」

ブロック名。英字小文字で必須です。  
BEM不採用の場合はキャメルケースを採用です。

## ２項目目: エレメント

「prefix-block__element」

エレメント名。任意であり、アンダーバー２つで１項目目のブロックの後ろに付与する。

## ３項目目: モディファイ

「prefix-block--modifier」  
「prefix-block__element--modifier」

モディファイ名。任意であり、ハイフン２つで１項目目のブロックまたは２項目目のエレメントの後ろに付与する。

## パターン

「.rBlockPattern」(BEM不採用の場合)

ブロックのパターン。任意であり、BEM不採用の場合にブロックのパターン分けに使用。
キャメルケースを採用です。

## 補足

- [BEM](https://github.com/juno/bem-methodology-ja/blob/master/definitions.md)は、CSS設計の一つです。
- [FLOCSS](https://github.com/hiloki/flocss)は、CSS設計の一つです。
- [MindBEMding](https://csswizardry.com/2013/01/mindbemding-getting-your-head-round-bem-syntax/) は、BEMをCSSのクラス名に適用するために作られた命名規則です。

## 作成者

Copyright(C) 2025-2025 KOUTAN
