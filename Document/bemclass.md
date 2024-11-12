# BEM区分 説明書

FLOCSSを基調とした構成を考える為に、BEM区分というものを用意して処理しています。

このフォルダに関しての説明は、[`readme.md`](./README.md) に記述しています。

- [BEM区分 説明書](#bem区分-説明書)
  - [一覧](#一覧)
  - [区分け](#区分け)
    - [@at-root](#at-root)
    - [BEM](#bem)
    - [レイヤー](#レイヤー)
    - [その他](#その他)
  - [処理の例](#処理の例)
    - [ファウンデーション・ブロック\[BF\]](#ファウンデーションブロックbf)
    - [レイアウト・ブロック\[BL\]](#レイアウトブロックbl)
    - [コンポーネント・ブロック\[BC\]](#コンポーネントブロックbc)
    - [プロジェクト・ブロック\[BP\]](#プロジェクトブロックbp)
    - [ユーティリティ・ブロック\[BU\]](#ユーティリティブロックbu)
    - [テーマ・ブロック\[BT\]](#テーマブロックbt)
    - [エレメント\[BE\]](#エレメントbe)
    - [エレメント(レイアウト用)\[BEL\]](#エレメントレイアウト用bel)
    - [エレメント(コンポーネント用)\[BEC\]](#エレメントコンポーネント用bec)
    - [エレメント(プロジェクト用)\[BEP\]](#エレメントプロジェクト用bep)
    - [テーマ・エレメント\[BET\]](#テーマエレメントbet)
    - [モディファイ\[BM\]](#モディファイbm)
    - [モディファイ(レイアウト用)\[BML\]](#モディファイレイアウト用bml)
    - [モディファイ(コンポーネント用)\[BMC\]](#モディファイコンポーネント用bmc)
    - [モディファイ(プロジェクト用)\[BMP\]](#モディファイプロジェクト用bmp)
    - [プレースフォルダ\[PH\]](#プレースフォルダph)
    - [ファウンデーション・プレースフォルダ\[PF\]](#ファウンデーションプレースフォルダpf)
    - [レイアウト・プレースフォルダ\[PL\]](#レイアウトプレースフォルダpl)
    - [コンポーネント・プレースフォルダ\[PC\]](#コンポーネントプレースフォルダpc)
    - [プロジェクト・プレースフォルダ\[PP\]](#プロジェクトプレースフォルダpp)
    - [ユーティリティ・プレースフォルダ\[PU\]](#ユーティリティプレースフォルダpu)
    - [テーマ・プレースフォルダ\[PT\]](#テーマプレースフォルダpt)
    - [エクステンド\[EX\]](#エクステンドex)
    - [ファウンデーション・エクステンド\[EF\]](#ファウンデーションエクステンドef)
    - [レイアウト・エクステンド\[EL\]](#レイアウトエクステンドel)
    - [コンポーネント・エクステンド\[EC\]](#コンポーネントエクステンドec)
    - [プロジェクト・エクステンド\[EP\]](#プロジェクトエクステンドep)
    - [ユーティリティ・エクステンド\[EU\]](#ユーティリティエクステンドeu)
    - [テーマ・エクステンド\[ET\]](#テーマエクステンドet)
    - [ＩＤ\[ID\]](#ｉｄid)
    - [クラス\[CL\]](#クラスcl)
    - [ルート\[RO\]](#ルートro)
    - [離珠オリジナル\[RS\]](#離珠オリジナルrs)
    - [離珠レイアウト\[RL\]](#離珠レイアウトrl)
    - [離珠コンポーネント\[RC\]](#離珠コンポーネントrc)
    - [離珠プロジェクト\[RP\]](#離珠プロジェクトrp)
    - [離珠ユーティリティ\[RU\]](#離珠ユーティリティru)
    - [要素型セレクタ\[TS\]](#要素型セレクタts)
    - [装飾なし(アンデコレーション)\[UN\]](#装飾なしアンデコレーションun)
    - [宣言(デクラレーション)\[DE\]](#宣言デクラレーションde)
    - [文(ステートメント)\[ST\]](#文ステートメントst)
    - [装飾なし\[''\]](#装飾なし)
    - [処理なし\[null\]](#処理なしnull)
    - [プレフィックス(その他)](#プレフィックスその他)
  - [メディア区分](#メディア区分)
  - [作成者](#作成者)

## 一覧

|区分|名称|[レイヤー](#レイヤー)|[BEM](#bem)|prefix|[@at-root](#at-root)|
|:-:|----|----|----|----|----|
|BF|[ファウンデーション・ブロック](#ファウンデーションブロックbf)<br>Foundation Block|ファウンデーション|ブロック|`.f-`|ルート|
|BL|[レイアウト・ブロック](#レイアウトブロックbl)<br>Layout Block|レイアウト|ブロック|`.l-`|ルート|
|BC|[コンポーネント・ブロック](#コンポーネントブロックbc)<br>Component Block|コンポーネント|ブロック|`.c-`|ルート|
|BP|[プロジェクト・ブロック](#プロジェクトブロックbp)<br>Project Block|プロジェクト|ブロック|`.p-`|ルート|
|BU|[ユーティリティ・ブロック](#ユーティリティブロックbu)<br>Utility Block|ユーティリティ|ブロック|`.u-`|ルート|
|BT|[テーマ・ブロック](#テーマブロックbt)<br>Theme Block|テーマ|ブロック|`.t-`|ルート|
|BE|[エレメント](#エレメントbe)<br>Element|-|エレメント|`&__`|ルート|
|BEL|[エレメント](#エレメントbe)(レイアウト用)<br>Element|レイアウト|エレメント|`&__`|ルート|
|BET|[テーマ・エレメント](#テーマエレメントbet)<br>Element|-|エレメント|`&__`|ルート|
|BM|[モディファイ](#モディファイbm)<br>Modifier|-|モディファイ|`&--`|ルート|
|PH|[プレースフォルダ](#プレースフォルダph)<br>Placeholder Selectors|-|-|`%`|ルート|
|PF|[ファウンデーション・<br>プレースフォルダ](#ファウンデーションプレースフォルダpf)<br>Placeholder Selectors (Foundation)|ファウンデーション|-|`%XFPh`|ルート|
|PL|[レイアウト・プレースフォルダ](#レイアウトプレースフォルダpl)<br>Placeholder Selectors (Layout)|レイアウト|-|`%XLPh`|ルート|
|PC|[コンポーネント・プレースフォルダ](#コンポーネントプレースフォルダpc)<br>Placeholder Selectors (Component)|コンポーネント|-|`%XCPh`|ルート|
|PP|[プロジェクト・プレースフォルダ](#プロジェクトプレースフォルダpp)<br>Placeholder Selectors (Project)|プロジェクト|-|`%XPPh`|ルート|
|PU|[ユーティリティ・プレースフォルダ](#ユーティリティプレースフォルダpu)<br>Placeholder Selectors (Utility)|ユーティリティ|-|`%XUPh`|ルート|
|PT|[テーマ・プレースフォルダ](#テーマプレースフォルダpt)<br>Placeholder Selectors (Theme)|テーマ|-|`%XTPh`|ルート|
|EX|[エクステンド](#エクステンドex)<br>Extend|-|-|`%`|ルート|
|EF|[ファウンデーション・エクステンド](#ファウンデーションエクステンドef)<br>Extend (Foundation)|ファウンデーション|-|`%XFPh`|ルート|
|EL|[レイアウト・エクステンド](#レイアウトエクステンドel)<br>Extend (Layout)|レイアウト|-|`%XLPh`|ルート|
|EC|[コンポーネント・エクステンド](#コンポーネントエクステンドec)<br>Extend (Component)|コンポーネント|-|`%XCPh`|ルート|
|EP|[プロジェクト・エクステンド](#プロジェクトエクステンドep)<br>Extend (Project)|プロジェクト|-|`%XPPh`|ルート|
|EU|[ユーティリティ・エクステンド](#ユーティリティエクステンドeu)<br>Extend (Utility)|ユーティリティ|-|`%XUPh`|ルート|
|ET|[テーマ・プレースフォルダ](#テーマプレースフォルダpt)<br>Extend (Theme)|テーマ|-|`%XTPh`|ルート|
|ID|[ＩＤ](#ｉｄid)<br>Id Selectors|-|-|`#`|ネスト|
|CL|[クラス](#クラスcl)<br>Class Selectors|-|-|`.`|ネスト|
|RO|[ルート](#ルートro)<br>Root|-|-|なし|ルート|
|RS|[離珠オリジナル](#離珠オリジナルrs)|-|-|なし|ルート|
|RL|[離珠レイアウト](#離珠レイアウトrl)<br>Risyu Layout Block|レイアウト|ブロック|`.XL`|ルート|
|RC|[離珠コンポーネント](#離珠コンポーネントrc)<br>Risyu Component Block|コンポーネント|ブロック|`.XC`|ルート|
|RP|[離珠プロジェクト](#離珠プロジェクトrp)<br>Risyu Project Block|プロジェクト|ブロック|`.XP`|ルート|
|RU|[離珠ユーティリティ](#離珠ユーティリティru)<br>Risyu Utility Block|ユーティリティ|ブロック|`.XU`|ルート|
|TS|[要素型セレクタ](#要素型セレクタts)<br>type selector|-|-|なし|ネスト|
|UN|[装飾なし](#装飾なしアンデコレーションun)<br>Undecorated|-|-|なし|ネスト|
|DE|[宣言](#宣言デクラレーションde)<br>Declarations|-|-|なし|宣言のみ|
|ST|[文(ステートメント)](#文ステートメントst)<br>Statements|-|-|なし|宣言のみ|
|''|[装飾なし](#装飾なし)|-|-|なし|ネスト|
|null|[処理なし](#処理なしnull)|-|-|なし|なし|
|他|[プレフィックス(その他)](#プレフィックスその他)|-|-|区分|ネスト|

## 区分け

### @at-root

Sass を用いるにあたっての、ネストするかルートに出力するかの区分けが必要です。

### BEM

MindBEMding を用いる場合の、ブロック, エレメント, モディファイ による命名規則(セレクタの編集)の為の区分けが必要です。

### レイヤー

MindBEMding を用いる場合の、レイアウト, プロジェクト, コンポーネント, ユーティリティ による命名規則(セレクタの編集)の為の区分けが必要です。他に、ファウンデーション, テーマ などの区分けが追加されたりします。

### その他

セレクタの有無で、区分けが必要です。セレクタの種類での区分けもありますが、あまり必要ないと思います。(編集規則が明確に一定でないと、処理を用意できない。)

## 処理の例

### ファウンデーション・ブロック[BF]

FLOCSSのレイヤーの１つ、ブラウザのデフォルトスタイルの初期化や、プロジェクトにおける基本的なスタイルを定義するFoundationレイヤーを表します。MindBEMdingでの抽象化またはコンポーネントの上位レベルを表すBlockも表します。このレイヤーで敢えてクラスセレクタを用いたい時に使います。
\[[一覧へ戻る](#一覧)\]

- Scss

  ```Scss
  .f-html {
    @include mrGmBEMStyleRule01('BF', 'body') {
      margin: 0;
    }
  }
  ```

- Css

  ```Css
  .f-html {}
  .f-body {margin: 0;}
  ```

### レイアウト・ブロック[BL]

FLOCSSのレイヤーの１つ、ページレイアウトから見たスタイルを定義するLayoutレイヤーを表します。MindBEMdingでの抽象化またはコンポーネントの上位レベルを表すBlockも表します。
\[[一覧へ戻る](#一覧)\]

- Scss

  ```Scss
  .l-body {
    @include mrGmBEMStyleRule01('BL', 'selecter') {
      color: black;
    }
  }
  ```

- Css

  ```Css
  .l-body {}
  .l-selecter {color: black;}
  ```

### コンポーネント・ブロック[BC]

FLOCSSのレイヤーの１つ、再利用できるパターンとして、小さな単位のモジュールを定義するComponentレイヤーを表します。MindBEMdingでの抽象化またはコンポーネントの上位レベルを表すBlockも表します。
\[[一覧へ戻る](#一覧)\]

- Scss

  ```Scss
  .l-body {
    @include mrGmBEMStyleRule01('BC', 'selecter') {
      color: black;
    }
  }
  ```

- Css

  ```Css
  .l-body {}
  .c-selecter {color: black;}
  ```

### プロジェクト・ブロック[BP]

FLOCSSのレイヤーの１つ、プロジェクト固有のパターンを定義するProjectレイヤーを表します。MindBEMdingでの抽象化またはコンポーネントの上位レベルを表すBlockも表します。
\[[一覧へ戻る](#一覧)\]

- Scss

  ```Scss
  .l-body {
    @include mrGmBEMStyleRule01('BP', 'selecter') {
      color: black;
    }
  }
  ```

- Css

  ```Css
  .l-body {}
  .p-selecter {color: black;}
  ```

### ユーティリティ・ブロック[BU]

FLOCSSのレイヤーの１つ、ComponentとProjectレイヤーのObjectのモディファイアで解決することが難しい・適切では無い、わずかなスタイルの調整のための便利クラスなどを定義するUtilityレイヤーを表します。MindBEMdingでの抽象化またはコンポーネントの上位レベルを表すBlockも表します。
\[[一覧へ戻る](#一覧)\]

- Scss

  ```Scss
  .l-body {
    @include mrGmBEMStyleRule01('BU', 'selecter') {
      color: black;
    }
  }
  ```

- Css

  ```Css
  .l-body {}
  .u-selecter {color: black;}
  ```

### テーマ・ブロック[BT]

FLOCSSのレイヤーではありませんが、サイト全体の見た目を統一させる為の色などを定義するThemeレイヤーを表します。MindBEMdingでの抽象化またはコンポーネントの上位レベルを表すBlockも表します。
\[[一覧へ戻る](#一覧)\]

- Scss

  ```Scss

  .l-body {
    @include mrGmBEMStyleRule01('BT', 'selecter', null, '.t-theme') {
      color: black;
    }
  }
  ```

- Css

  ```Css
  .l-body {}
  .t-theme .t-selecter {color: black;}
  ```

### エレメント[BE]

MindBEMdingでの、全体として(.block を形成するのに役立つ) .block の子孫を表すElementを表します。
\[[一覧へ戻る](#一覧)\]

- Scss

  ```Scss
  .l-body {
    @include mrGmBEMStyleRule01('BE', 'selecter') {
      color: black;
    }
  }
  ```

- Css

  ```Css
  .l-body {}
  .l-body__selecter {color: black;}
  ```

### エレメント(レイアウト用)[BEL]

エレメントのレイアウト用です。内部処理でレイヤーを意識した処理を行います。

### エレメント(コンポーネント用)[BEC]

エレメントのコンポーネント用です。内部処理でレイヤーを意識した処理を行います。

### エレメント(プロジェクト用)[BEP]

エレメントのプロジェクト用です。内部処理でレイヤーを意識した処理を行います。

### テーマ・エレメント[BET]

Pug での class属性値のテーマ分の制御用です。
MindBEMdingでの、全体として(.block を形成するのに役立つ) .block の子孫を表すElementを表します。
\[[一覧へ戻る](#一覧)\]

- Scss

  ```Scss
  .l-body {
    @include mrGmBEMStyleRule01('BET', 'selecter') {
      color: black;
    }
  }
  ```

- Css

  ```Css
  .l-body {}
  .t-body__selecter {color: black;}
  ```

### モディファイ[BM]

MindBEMdingでの、.block 又は Element の異なる状態またはバージョンを表すModifierを表します。
\[[一覧へ戻る](#一覧)\]

- Scss

  ```Scss
  .l-body {
    @include mrGmBEMStyleRule01('BM', 'selecter') {
      color: black;
    }
  }
  ```

- Css

  ```Css
  .l-body, .l-body--selecter {}
  .l-body--selecter {color: black;}
  ```

### モディファイ(レイアウト用)[BML]

モディファイのレイアウト用です。内部処理でレイヤーを意識した処理を行います。

### モディファイ(コンポーネント用)[BMC]

モディファイのコンポーネント用です。内部処理でレイヤーを意識した処理を行います。

### モディファイ(プロジェクト用)[BMP]

モディファイのプロジェクト用です。内部処理でレイヤーを意識した処理を行います。

### プレースフォルダ[PH]

Sassの機能の１つ、CSS出力に含まれないセレクタであるPlaceholder Selectorsを表します。宣言は、拡張する事でCSS出力に含まれます。尚、当プロジェクトでは、プレースフォルダセレクタの重複を禁止して、作成を変数で管理します。
\[[一覧へ戻る](#一覧)\]

- Scss

  ```Scss
  .l-body {
    @include mrGmBEMStyleRule01('PH', 'selecter') {
      color: black;
    }
  }
  .l-head {
    @extend %selecter !optional;
  }
  ```

- Css

  ```Css
  .l-body {}
  .l-head {color: black;}
  ```

### ファウンデーション・プレースフォルダ[PF]

Sassの機能の１つ、CSS出力に含まれないセレクタであるPlaceholder Selectorsを表します。Foundationレイヤー相当を表します。宣言は、拡張する事でCSS出力に含まれます。レイヤー毎に出力場所を調整する時に用います。尚、当プロジェクトでは、プレースフォルダセレクタの重複を禁止して、作成を変数で管理します。
\[[一覧へ戻る](#一覧)\]

- Scss

  ```Scss
  .f-body {
    @include mrGmBEMStyleRule01('PF', 'selecter') {
      color: black;
    }
  }
  .f-head {
    @extend %XFPhSelecter !optional;
  }
  ```

- Css

  ```Css
  .f-body {}
  .f-head {color: black;}
  ```

### レイアウト・プレースフォルダ[PL]

Sassの機能の１つ、CSS出力に含まれないセレクタであるPlaceholder Selectorsを表します。Layoutレイヤー相当を表します。宣言は、拡張する事でCSS出力に含まれます。レイヤー毎に出力場所を調整する時に用います。尚、当プロジェクトでは、プレースフォルダセレクタの重複を禁止して、作成を変数で管理します。
\[[一覧へ戻る](#一覧)\]

- Scss

  ```Scss
  .l-body {
    @include mrGmBEMStyleRule01('PL', 'selecter') {
      color: black;
    }
  }
  .l-head {
    @extend %XLPhSelecter !optional;
  }
  ```

- Css

  ```Css
  .l-body {}
  .l-head {color: black;}
  ```

### コンポーネント・プレースフォルダ[PC]

Sassの機能の１つ、CSS出力に含まれないセレクタであるPlaceholder Selectorsを表します。Componentレイヤー相当を表します。宣言は、拡張する事でCSS出力に含まれます。レイヤー毎に出力場所を調整する時に用います。尚、当プロジェクトでは、プレースフォルダセレクタの重複を禁止して、作成を変数で管理します。
\[[一覧へ戻る](#一覧)\]

- Scss

  ```Scss
  .c-body {
    @include mrGmBEMStyleRule01('PC', 'selecter') {
      color: black;
    }
  }
  .c-head {
    @extend %XCPhSelecter !optional;
  }
  ```

- Css

  ```Css
  .c-body {}
  .c-head {color: black;}
  ```

### プロジェクト・プレースフォルダ[PP]

Sassの機能の１つ、CSS出力に含まれないセレクタであるPlaceholder Selectorsを表します。Projectレイヤー相当を表します。宣言は、拡張する事でCSS出力に含まれます。レイヤー毎に出力場所を調整する時に用います。尚、当プロジェクトでは、プレースフォルダセレクタの重複を禁止して、作成を変数で管理します。
\[[一覧へ戻る](#一覧)\]

- Scss

  ```Scss
  .p-body {
    @include mrGmBEMStyleRule01('PP', 'selecter') {
      color: black;
    }
  }
  .p-head {
    @extend %XPPhSelecter !optional;
  }
  ```

- Css

  ```Css
  .p-body {}
  .p-head {color: black;}
  ```

### ユーティリティ・プレースフォルダ[PU]

Sassの機能の１つ、CSS出力に含まれないセレクタであるPlaceholder Selectorsを表します。Utilityレイヤー相当を表します。宣言は、拡張する事でCSS出力に含まれます。レイヤー毎に出力場所を調整する時に用います。尚、当プロジェクトでは、プレースフォルダセレクタの重複を禁止して、作成を変数で管理します。
\[[一覧へ戻る](#一覧)\]

- Scss

  ```Scss
  .u-body {
    @include mrGmBEMStyleRule01('PU', 'selecter') {
      color: black;
    }
  }
  .u-head {
    @extend %XUPhSelecter !optional;
  }
  ```

- Css

  ```Css
  .u-body {}
  .u-head {color: black;}
  ```

### テーマ・プレースフォルダ[PT]

Sassの機能の１つ、CSS出力に含まれないセレクタであるPlaceholder Selectorsを表します。Themeレイヤー相当を表します。宣言は、拡張する事でCSS出力に含まれます。レイヤー毎に出力場所を調整する時に用います。尚、当プロジェクトでは、プレースフォルダセレクタの重複を禁止して、作成を変数で管理します。
\[[一覧へ戻る](#一覧)\]

- Scss

  ```Scss
  .t-body {
    @include mrGmBEMStyleRule01('PT', 'selecter') {
      color: black;
    }
  }
  .t-head {
    @extend %XTPhSelecter !optional;
  }
  ```

- Css

  ```Css
  .t-body {}
  .t-head {color: black;}
  ```

### エクステンド[EX]

Sassの機能の１つ、セレクタの拡張を示す@extendを表します。あるセレクターが別のセレクターのスタイルを継承する必要があることを Sass に伝えます。尚、当プロジェクトでは、この'EX'区分での拡張対象をプレースフォルダセレクタのみとしています。対象が未作成の場合は、作成して拡張します。
\[[一覧へ戻る](#一覧)\]

- その１(拡張対象が既存の場合)
  - Scss

    ```Scss
    .l-body {
      @include mrGmBEMStyleRule01('PH', 'selecter') {
        color: black;
      }
    }
    .l-head {
      @include mrGmBEMStyleRule01('EX', 'selecter') {
        color: white;
      }
    }
    ```

  - Css

    ```Css
    .l-body {}
    .l-head {color: black;}
    ```

- その２(拡張対象が未作成の場合)
  - Scss

    ```Scss
    .l-head {
      @include mrGmBEMStyleRule01('EX', 'selecter') {
        color: white;
      }
    }
    ```

  - Css

    ```Css
    .l-head {color: white;}
    ```

### ファウンデーション・エクステンド[EF]

'EX'(エクステンド)のFoundationレイヤー版です。ファウンデーション・プレースフォルダセレクタの拡張を示す@extendを表します。レイヤー毎に出力場所を調整する時に用います。
\[[一覧へ戻る](#一覧)\]

- Scss

  ```Scss
  .f-body {
    @include mrGmBEMStyleRule01('PF', 'selecter') {
      color: black;
    }
  }
  .f-head {
    @include mrGmBEMStyleRule01('EF', 'selecter');
  }
  ```

- Css

  ```Css
  .f-body {}
  .f-head {color: black;}
  ```

### レイアウト・エクステンド[EL]

'EX'(エクステンド)のLayoutレイヤー版です。レイアウト・プレースフォルダセレクタの拡張を示す@extendを表します。レイヤー毎に出力場所を調整する時に用います。
\[[一覧へ戻る](#一覧)\]

- Scss

  ```Scss
  .l-body {
    @include mrGmBEMStyleRule01('PL', 'selecter') {
      color: black;
    }
  }
  .l-head {
    @include mrGmBEMStyleRule01('EL', 'selecter');
  }
  ```

- Css

  ```Css
  .l-body {}
  .l-head {color: black;}
  ```

### コンポーネント・エクステンド[EC]

'EX'(エクステンド)のComponentレイヤー版です。コンポーネント・プレースフォルダセレクタの拡張を示す@extendを表します。レイヤー毎に出力場所を調整する時に用います。
\[[一覧へ戻る](#一覧)\]

- Scss

  ```Scss
  .c-body {
    @include mrGmBEMStyleRule01('PC', 'selecter') {
      color: black;
    }
  }
  .c-head {
    @include mrGmBEMStyleRule01('EC', 'selecter');
  }
  ```

- Css

  ```Css
  .c-body {}
  .c-head {color: black;}
  ```

### プロジェクト・エクステンド[EP]

'EX'(エクステンド)のProjectレイヤー版です。プロジェクト・プレースフォルダセレクタの拡張を示す@extendを表します。レイヤー毎に出力場所を調整する時に用います。
\[[一覧へ戻る](#一覧)\]

- Scss

  ```Scss
  .p-body {
    @include mrGmBEMStyleRule01('PP', 'selecter') {
      color: black;
    }
  }
  .p-head {
    @include mrGmBEMStyleRule01('EP', 'selecter');
  }
  ```

- Css

  ```Css
  .p-body {}
  .p-head {color: black;}
  ```

### ユーティリティ・エクステンド[EU]

'EX'(エクステンド)のUtilityレイヤー版です。ユーティリティ・プレースフォルダセレクタの拡張を示す@extendを表します。レイヤー毎に出力場所を調整する時に用います。
\[[一覧へ戻る](#一覧)\]

- Scss

  ```Scss
  .u-body {
    @include mrGmBEMStyleRule01('PU', 'selecter') {
      color: black;
    }
  }
  .u-head {
    @include mrGmBEMStyleRule01('EU', 'selecter');
  }
  ```

- Css

  ```Css
  .u-body {}
  .u-head {color: black;}
  ```

### テーマ・エクステンド[ET]

'EX'(エクステンド)のThemeレイヤー版です。テーマ・プレースフォルダセレクタの拡張を示す@extendを表します。レイヤー毎に出力場所を調整する時に用います。
\[[一覧へ戻る](#一覧)\]

- Scss

  ```Scss
  .t-body {
    @include mrGmBEMStyleRule01('PT', 'selecter') {
      color: black;
    }
  }
  .t-head {
    @include mrGmBEMStyleRule01('ET', 'selecter');
  }
  ```

- Css

  ```Css
  .t-body {}
  .t-head {color: black;}
  ```

### ＩＤ[ID]

IDセレクタを表します。
\[[一覧へ戻る](#一覧)\]

- Scss

  ```Scss
  .l-body {
    @include mrGmBEMStyleRule01('ID', 'selecter') {
      color: black;
    }
  }
  ```

- Css

  ```Css
  .l-body {}
  .l-body #selecter {color: black;}
  ```

### クラス[CL]

クラスセレクタを表します。
\[[一覧へ戻る](#一覧)\]

- Scss

  ```Scss
  .l-body {
    @include mrGmBEMStyleRule01('CL', 'selecter') {
      color: black;
    }
  }
  ```

- Css

  ```Css
  .l-body {}
  .l-body .selecter {color: black;}
  ```

### ルート[RO]

Sassの機能の１つ、通常のネストを使用する代わりに、その中のすべてがドキュメントのルートに出力する@at-rootを表します。
\[[一覧へ戻る](#一覧)\]

- Scss

  ```Scss
  .l-body {
    @include mrGmBEMStyleRule01('RO', '.selecter') {
      color: black;
    }
  }
  ```

- Css

  ```Css
  .l-body {}
  .selecter {color: black;}
  ```

### 離珠オリジナル[RS]

作者オリジナルのセレクタの命名規則を表します。MindBEMdingでの抽象化またはコンポーネントの上位レベルを表すBlockだけにクラスセレクタを用い、その子孫は要素セレクタを用いるという規則にしています。制作意図を表すだけで、機能はルートと同じです。
\[[一覧へ戻る](#一覧)\]

- Scss

  ```Scss
  .l-body {
    @include mrGmBEMStyleRule01('RS', 'LHHead') {
      color: black;
    }
  }
  ```

- Css

  ```Css
  .l-body {}
  .XLHHead {color: black;}
  ```

### 離珠レイアウト[RL]

作者オリジナルのセレクタの命名規則を表します。MindBEMdingでの抽象化またはコンポーネントの上位レベルを表すBlockだけにクラスセレクタを用い、その子孫は要素セレクタを用いるという規則にしています。
プロジェクト共通のコンテナーブロックのスタイルを定義するLayoutレイヤーを表します。
\[[一覧へ戻る](#一覧)\]

- Scss

  ```Scss
  .l-body {
    @include mrGmBEMStyleRule01('RL', 'head', 'F') {
      color: black;
    }
  }
  ```

- Css

  ```Css
  .l-body {}
  .XLFHead {color: black;}
  ```

### 離珠コンポーネント[RC]

作者オリジナルのセレクタの命名規則を表します。MindBEMdingでの抽象化またはコンポーネントの上位レベルを表すBlockだけにクラスセレクタを用い、その子孫は要素セレクタを用いるという規則にしています。
小さな単位のモジュールを定義するComponentレイヤーを表します。
\[[一覧へ戻る](#一覧)\]

- Scss

  ```Scss
  .l-body {
    @include mrGmBEMStyleRule01('RC', 'head', 'F') {
      color: black;
    }
  }
  ```

- Css

  ```Css
  .l-body {}
  .XCFHead {color: black;}
  ```

### 離珠プロジェクト[RP]

作者オリジナルのセレクタの命名規則を表します。MindBEMdingでの抽象化またはコンポーネントの上位レベルを表すBlockだけにクラスセレクタを用い、その子孫は要素セレクタを用いるという規則にしています。
プロジェクト固有のパターンを定義するProjectレイヤーを表します。
\[[一覧へ戻る](#一覧)\]

- Scss

  ```Scss
  .l-body {
    @include mrGmBEMStyleRule01('RP', 'head', 'F') {
      color: black;
    }
  }
  ```

- Css

  ```Css
  .l-body {}
  .XPFHead {color: black;}
  ```

### 離珠ユーティリティ[RU]

作者オリジナルのセレクタの命名規則を表します。MindBEMdingでの抽象化またはコンポーネントの上位レベルを表すBlockだけにクラスセレクタを用い、その子孫は要素セレクタを用いるという規則にしています。
ComponentとProjectレイヤーのObjectのモディファイアで解決することが難しい・適切では無い、わずかなスタイルの調整のための便利クラスなどを定義するUtilityレイヤーを表します。
\[[一覧へ戻る](#一覧)\]

- Scss

  ```Scss
  .l-body {
    @include mrGmBEMStyleRule01('RU', 'head', 'F') {
      color: black;
    }
  }
  ```

- Css

  ```Css
  .l-body {}
  .XUFHead {color: black;}
  ```

### 要素型セレクタ[TS]

要素名をセレクタとして用いる事を表します。既定値が該当する要素名であるだけで、機能としては指定したセレクタをそのまま用います。ネストもそのままです。
\[[一覧へ戻る](#一覧)\]

- Scss

  ```Scss
  .l-body {
    @include mrGmBEMStyleRule01('TS', 'h1') {
      color: black;
    }
  }
  ```

- Css

  ```Css
  .l-body {}
  .l-body h1 {color: black;}
  ```

### 装飾なし\(アンデコレーション)[UN]

指定したセレクタをそのまま用いる事を表します。ネストもそのままです。
\[[一覧へ戻る](#一覧)\]

- Scss

  ```Scss
  .l-body {
    @include mrGmBEMStyleRule01('UN', '.selecter') {
      color: black;
    }
  }
  ```

- Css

  ```Css
  .l-body {}
  .l-body .selecter {color: black;}
  ```

### 宣言\(デクラレーション)[DE]

セレクタを付与せず、宣言(プロパティと値の組)だけを出力する事を表します。指定したセレクタは無視します。ネストした親のルールセットの一部となります。
\[[一覧へ戻る](#一覧)\]

- Scss

  ```Scss
  .l-body {
    @include mrGmBEMStyleRule01('DE', 'selecter') {
      color: black;
    }
  }
  ```

- Css

  ```Css
  .l-body {color: black;}
  ```

### 文\(ステートメント)[ST]

文(ステートメント)を表します。CSSで文とは、At-rules と style rule(rule sets) を指します。区分として用意していますが、機能としては未対応です。
\[[一覧へ戻る](#一覧)\]

- Scss

  ```Scss
  .l-body {
    @include mrGmBEMStyleRule01('ST', 'selecter') {
      color: black;
    }
  }
  ```

- Css

  ```Css
  .l-body {color: black;}
  ```

### 装飾なし\['']

[装飾なし\(アンデコレーション)](#装飾なしアンデコレーションun)と同じです。機能を作成する経緯で残っています。
\[[一覧へ戻る](#一覧)\]

- Scss

  ```Scss
  .l-body {
    @include mrGmBEMStyleRule01('', '.selecter') {
      color: black;
    }
  }
  ```

- Css

  ```Css
  .l-body {}
  .l-body .selecter {color: black;}
  ```

### 処理なし\[null]

Sass の機能で 宣言の値が null であると宣言自体がCSSとして出力されないという事を参考に、BEM区分が null であるとその処理自体を行わないという事にしました。
\[[一覧へ戻る](#一覧)\]

- Scss

  ```Scss
  .l-body {
    @include mrGmBEMStyleRule01(null, '.selecter') {
      color: black;
    }
  }
  ```

- Css

  ```Css
  .l-body {}
  ```

### プレフィックス(その他)

用意されたBEM区分の値以外は、全てprefixとして処理する事を表します。
\[[一覧へ戻る](#一覧)\]

- Scss

  ```Scss
  .l-body {
    @include mrGmBEMStyleRule01('.l-', 'selecter') {
      color: black;
    }
  }
  ```

- Css

  ```Css
  .l-body {}
  .l-body .l-selecter {color: black;}
  ```

## メディア区分

@media に対応する為に、メディア区分を用意しました。
これは、セレクタの拡張で @media に対応する為に、プレースフォルダセレクタにメディアを表す記述を組み込む様にしました。
合わせて、モディファイでの拡張でもプレースフォルダセレクタを用いるようにしました。

## 作成者

Copyright(C) 2022-2024 KOUTAN
