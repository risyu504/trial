# HTML 要素 データフォルダ readme

この `README.md` ファイルは、このフォルダに関しての説明を記述したファイルです。

## 概要

- このフォルダは、**HTML 要素**の関連データファイルを収めるフォルダです。
- HTML等に関する要素の仕様を記述をする為の関連データファイルです。
- [データフォルダ](../README.md)の下位フォルダとする事を、想定しています。
- データの内容を意識しての、それに対応する構成です。
- 外部データ, 手書きデータ, スクリプト作成データといろいろあり、内部規約の例外となる物もありうるので、ご注意ください。
- 名称: **Htmlspec**, 区分: **Hs** です。

## 使い方

上位の [データフォルダ](../README.md) のreadme に記述があります。

## 内部規約

1. 主に [コーディングルール](../../Document/20_Design/codingrules.md) に準じます。
2. 上位の [データフォルダ](../README.md) のreadme に記述があります。
3. 現時点では、内部作成データのみなので、規約の例外はありません。
4. このフォルダのフォルダ区分は、'**Hs**'(Htmlspec) です。

## 構成

自由な構成の為、ここでは記しません。しいて言えば、JSONファイルを分かり易くフォルダ分けしてある位です。

- ※ データを分かり易くフォルダ分け
- `htmlelements.json` 用意したデータファイルをスクリプトで纏めたデータファイル
- `README.md` 説明ファイル(このファイルです)

## データ構造

### HTML仕様記述データ

- @type: **htmlElement**
- lastReviewed: このコンテンツの正確性および完全性が最後に確認された日付。[yyyy-mm-dd]
- supplementaryExplanation: このコンテンツの補足説明。
- group: グループ
- element: 簡易要素仕様DTD風
- attlist: 簡易属性仕様DTD風
- alias: アイテムの別名
- summary: 簡易説明
- point: 要点説明
- description: 説明
- elementKind: 種類
- kindsupplement: 種類の補足説明
- categories: カテゴリ
- categoriessupplement: カテゴリの補足説明
- canUsedContexts: 使用できるコンテキスト
- usedsupplement: カテゴリの補足説明
- contentModel: コンテンツモデル
- contentmodelsupplement: コンテンツモデルの補足説明
- tagOmission: タグの省略
- tagsupplement: タグの省略の補足説明
- rendering: レンダリング
- renderingsupplement: レンダリングの補足説明
- domInterface: DOM インターフェイス
- dominterfacesupplement: DOM インターフェイスの補足説明
- contentAttributes: コンテンツ属性
- attributessupplement: コンテンツ属性の補足説明
- obsoleteAttributes: 廃止されたコンテンツ属性
- obsoleteattributessupplement: 廃止されたコンテンツ属性の補足説明
- reference: 参照元(配列)
  - title: アイテムの名前。(Webページの名前)英字表記
  - href: アイテムのURL。 [Thingのurl]
  - heading: アイテムの名前。(Webページの名前) [Thingのname]
  - sub: アイテムの補足説明

## 作成者

Copyright(C) 2022-2025 KOUTAN
