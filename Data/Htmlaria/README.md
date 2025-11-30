# ARIA in HTML データフォルダ readme

この `README.md` ファイルは、このフォルダに関しての説明を記述したファイルです。

## 概要

- このフォルダは、**ARIA in HTML**の関連データファイルを収めるフォルダです。
- HTML等に関する仕様を記述をする為の関連データファイルです。
- [データフォルダ](../README.md)の下位フォルダとする事を、想定しています。
- データの内容を意識しての、それに対応する構成です。
- 外部データ, 手書きデータ, スクリプト作成データといろいろあり、内部規約の例外となる物もありうるので、ご注意ください。
- 名称: **Htmlaria**, 区分: **Ha** です。

## 使い方

上位の [データフォルダ](../README.md) のreadme に記述があります。

## 内部規約

1. 主に [コーディングルール](../../Document/20_Design/codingrules.md) に準じます。
2. 上位の [データフォルダ](../README.md) のreadme に記述があります。
3. 現時点では、内部作成データのみなので、規約の例外はありません。
4. このフォルダのフォルダ区分は、'**Ha**'(Htmlaria) です。

## 構成

自由な構成の為、ここでは記しません。しいて言えば、JSONファイルを分かり易くフォルダ分けしてある位です。

- ※ データを分かり易くフォルダ分け
- `htmlaria.json` 用意したデータファイルをスクリプトで纏めたデータファイル
- `README.md` 説明ファイル(このファイルです)

## データ構造

### ARIA in HTML

- @type: **htmlAria**
- lastReviewed: このコンテンツの正確性および完全性が最後に確認された日付。[yyyy-mm-dd]
- supplementaryExplanation: このコンテンツの補足説明。
- alias: アイテムの別名
- implicit: 暗黙的な ARIA セマンティクス
  - Obsolete: 廃止。不採用。
  - No: 対応するロールなし。
  - Separately: 別途記載。
  - []: 複数指定は配列。
- implicitsupplement: 暗黙的な ARIA セマンティクスの説明
- role: 作成者が要素に指定できる ARIA ロール値
  - No: 指定できるロールなし。
  - Anyrole: 任意のロール値を使用できる。
  - []: 複数指定は配列。
- rolesupplement: 作成者が要素に指定できる ARIA ロール値の説明
- dpub: 作成者が要素に指定できる dpub ロール値
- dpubsupplement: 作成者が要素に指定できる dpub ロール値の説明
- ariaattributes: 作成者が要素に指定できる aria-* 属性
  - GlobalAny: グローバル aria-* 属性と、許可されたロールに適用可能な任意の aria-* 属性。
- ariaattributessupplement: 作成者が要素に指定できる aria-* 属性についての説明
- naming: 命名禁止
  - "Naming prohibited"以外: 命名禁止の条件(ARIA ロール値)
- prohibited: 禁止されている area-* 属性
- prohibitedsupplement: 禁止に関する説明
- reference: 参照元(配列)
  - title: アイテムの名前。(Webページの名前)英字表記
  - href: アイテムのURL。 [Thingのurl]
  - heading: アイテムの名前。(Webページの名前) [Thingのname]
  - sub: アイテムの補足説明

## 作成者

Copyright(C) 2022-2025 KOUTAN
