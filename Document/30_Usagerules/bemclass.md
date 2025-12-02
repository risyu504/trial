# BEM区分 説明書

FLOCSSを基調とした構成を考える為に、BEM区分というものを用意して処理しています。

このフォルダに関しての説明は、[`README.md`](./README.md) に記述しています。

- [BEM区分 説明書](#bem区分-説明書)
  - [一覧](#一覧)
  - [区分け](#区分け)
    - [@at-root](#at-root)
    - [BEM](#bem)
    - [レイヤー](#レイヤー)
    - [prefix](#prefix)
    - [その他](#その他)
  - [処理の例](#処理の例)
    - [ブロック\[BBK\]](#ブロックbbk)
    - [ファウンデーション・ブロック\[BBF\]](#ファウンデーションブロックbbf)
    - [レイアウト・ブロック\[BBL\]](#レイアウトブロックbbl)
    - [コンポーネント・ブロック\[BBC\]](#コンポーネントブロックbbc)
    - [プロジェクト・ブロック\[BBP\]](#プロジェクトブロックbbp)
    - [ユーティリティ・ブロック\[BBU\]](#ユーティリティブロックbbu)
    - [テーマ・ブロック\[BBT\]](#テーマブロックbbt)
    - [エレメント\[BEK\]](#エレメントbek)
    - [ファウンデーション・エレメント\[BEF\]](#ファウンデーションエレメントbef)
    - [レイアウト・エレメント\[BEL\]](#レイアウトエレメントbel)
    - [コンポーネント・エレメント\[BEC\]](#コンポーネントエレメントbec)
    - [プロジェクト・エレメント\[BEP\]](#プロジェクトエレメントbep)
    - [ユーティリティ・エレメント\[BEU\]](#ユーティリティエレメントbeu)
    - [テーマ・エレメント\[BET\]](#テーマエレメントbet)
    - [モディファイ\[BMK\]](#モディファイbmk)
    - [ファウンデーション・モディファイ\[BMF\]](#ファウンデーションモディファイbmf)
    - [レイアウト・モディファイ\[BML\]](#レイアウトモディファイbml)
    - [コンポーネント・モディファイ\[BMC\]](#コンポーネントモディファイbmc)
    - [プロジェクト・モディファイ\[BMP\]](#プロジェクトモディファイbmp)
    - [ユーティリティ・モディファイ\[BMU\]](#ユーティリティモディファイbmu)
    - [テーマ・モディファイ\[BMT\]](#テーマモディファイbmt)
    - [プレースフォルダ\[PHK\]](#プレースフォルダphk)
    - [要素型・プレースフォルダ\[PHY\]](#要素型プレースフォルダphy)
    - [ファウンデーション・プレースフォルダ\[PHF\]](#ファウンデーションプレースフォルダphf)
    - [レイアウト・プレースフォルダ\[PHL\]](#レイアウトプレースフォルダphl)
    - [コンポーネント・プレースフォルダ\[PHC\]](#コンポーネントプレースフォルダphc)
    - [プロジェクト・プレースフォルダ\[PHP\]](#プロジェクトプレースフォルダphp)
    - [ユーティリティ・プレースフォルダ\[PHU\]](#ユーティリティプレースフォルダphu)
    - [テーマ・プレースフォルダ\[PHT\]](#テーマプレースフォルダpht)
    - [エクステンド\[EXK\]](#エクステンドexk)
    - [要素型・エクステンド\[EXY\]](#要素型エクステンドexy)
    - [ファウンデーション・エクステンド\[EXF\]](#ファウンデーションエクステンドexf)
    - [レイアウト・エクステンド\[EXL\]](#レイアウトエクステンドexl)
    - [コンポーネント・エクステンド\[EXC\]](#コンポーネントエクステンドexc)
    - [プロジェクト・エクステンド\[EXP\]](#プロジェクトエクステンドexp)
    - [ユーティリティ・エクステンド\[EXU\]](#ユーティリティエクステンドexu)
    - [テーマ・エクステンド\[EXT\]](#テーマエクステンドext)
    - [ブロック(プレースフォルダ)\[PBK\]](#ブロックプレースフォルダpbk)
    - [ファウンデーション・ブロック(プレースフォルダ)\[PBF\]](#ファウンデーションブロックプレースフォルダpbf)
    - [レイアウト・ブロック(プレースフォルダ)\[PBL\]](#レイアウトブロックプレースフォルダpbl)
    - [コンポーネント・ブロック(プレースフォルダ)\[PBC\]](#コンポーネントブロックプレースフォルダpbc)
    - [プロジェクト・ブロック(プレースフォルダ)\[PBP\]](#プロジェクトブロックプレースフォルダpbp)
    - [ユーティリティ・ブロック(プレースフォルダ)\[PBU\]](#ユーティリティブロックプレースフォルダpbu)
    - [テーマ・ブロック(プレースフォルダ)\[PBT\]](#テーマブロックプレースフォルダpbt)
    - [エレメント(プレースフォルダ)\[PEK\]](#エレメントプレースフォルダpek)
    - [ファウンデーション・エレメント(プレースフォルダ)\[PEF\]](#ファウンデーションエレメントプレースフォルダpef)
    - [レイアウト・エレメント(プレースフォルダ)\[PEL\]](#レイアウトエレメントプレースフォルダpel)
    - [コンポーネント・エレメント(プレースフォルダ)\[PEC\]](#コンポーネントエレメントプレースフォルダpec)
    - [プロジェクト・エレメント(プレースフォルダ)\[PEP\]](#プロジェクトエレメントプレースフォルダpep)
    - [ユーティリティ・エレメント(プレースフォルダ)\[PEU\]](#ユーティリティエレメントプレースフォルダpeu)
    - [テーマ・エレメント(プレースフォルダ)\[PET\]](#テーマエレメントプレースフォルダpet)
    - [モディファイ(プレースフォルダ)\[PMK\]](#モディファイプレースフォルダpmk)
    - [ファウンデーション・モディファイ(プレースフォルダ)\[PMF\]](#ファウンデーションモディファイプレースフォルダpmf)
    - [レイアウト・モディファイ(プレースフォルダ)\[PML\]](#レイアウトモディファイプレースフォルダpml)
    - [コンポーネント・モディファイ(プレースフォルダ)\[PMC\]](#コンポーネントモディファイプレースフォルダpmc)
    - [プロジェクト・モディファイ(プレースフォルダ)\[PMP\]](#プロジェクトモディファイプレースフォルダpmp)
    - [ユーティリティ・モディファイ(プレースフォルダ)\[PMU\]](#ユーティリティモディファイプレースフォルダpmu)
    - [テーマ・モディファイ(プレースフォルダ)\[PMT\]](#テーマモディファイプレースフォルダpmt)
    - [離珠オリジナル\[RSK\]](#離珠オリジナルrsk)
    - [離珠ファウンデーション\[RSF\]](#離珠ファウンデーションrsf)
    - [離珠レイアウト\[RSL\]](#離珠レイアウトrsl)
    - [離珠コンポーネント\[RC\]](#離珠コンポーネントrc)
    - [離珠プロジェクト\[RP\]](#離珠プロジェクトrp)
    - [離珠ユーティリティ\[RU\]](#離珠ユーティリティru)
    - [ＩＤ\[ID\]](#ｉｄid)
    - [クラス\[CL\]](#クラスcl)
    - [ルート\[RO\]](#ルートro)
    - [要素型セレクタ\[TS\]](#要素型セレクタts)
    - [装飾なし(アンデコレーション)\[UN\]](#装飾なしアンデコレーションun)
    - [宣言(デクラレーション)\[DE\]](#宣言デクラレーションde)
    - [文(ステートメント)\[ST\]](#文ステートメントst)
    - [装飾なし\[''\]](#装飾なし)
    - [処理なし\[null\]](#処理なしnull)
    - [プレフィックス(その他)](#プレフィックスその他)
  - [メディア区分](#メディア区分)
  - [補足](#補足)
  - [作成者](#作成者)

## 一覧

|区分|名称|[レイヤー](#レイヤー)|[BEM](#bem)|prefix|[@at-root](#at-root)|
|:-:|----|----|----|----|----|
|BBK|[ブロック](#ブロックbbk)<br>Block|不定|ブロック|`.`|ルート|
|BBF|[ファウンデーション・ブロック](#ファウンデーションブロックbbf)<br>Foundation Block|ファウンデーション|ブロック|`.f-`|ルート|
|BBL|[レイアウト・ブロック](#レイアウトブロックbbl)<br>Layout Block|レイアウト|ブロック|`.l-`|ルート|
|BBC|[コンポーネント・ブロック](#コンポーネントブロックbbc)<br>Component Block|コンポーネント|ブロック|`.c-`|ルート|
|BBP|[プロジェクト・ブロック](#プロジェクトブロックbbp)<br>Project Block|プロジェクト|ブロック|`.p-`|ルート|
|BBU|[ユーティリティ・ブロック](#ユーティリティブロックbbu)<br>Utility Block|ユーティリティ|ブロック|`.u-`|ルート|
|BBT|[テーマ・ブロック](#テーマブロックbbt)<br>Theme Block|テーマ|ブロック|`.t-`|ルート|
|BEK|[エレメント](#エレメントbek)<br>Element|不定|エレメント|`&__`|ルート|
|BEF|[ファウンデーション・エレメント](#ファウンデーションエレメントbef)<br>Foundation Element|ファウンデーション|エレメント|`&__`|ルート|
|BEL|[レイアウト・エレメント](#レイアウトエレメントbel)<br>Layout Element|レイアウト|エレメント|`&__`|ルート|
|BEC|[コンポーネント・エレメント](#コンポーネントエレメントbec)<br>Component Element|コンポーネント|エレメント|`&__`|ルート|
|BEP|[プロジェクト・エレメント](#プロジェクトエレメントbep)<br>Project Element|プロジェクト|エレメント|`&__`|ルート|
|BEU|[ユーティリティ・エレメント](#ユーティリティエレメントbeu)<br>Utility Element|ユーティリティ|エレメント|`&__`|ルート|
|BET|[テーマ・エレメント](#テーマエレメントbet)<br>Theme Element|テーマ|エレメント|`&__`|ルート|
|BMK|[モディファイ](#モディファイbmk)<br>Modifier|不定|モディファイ|`&--`|ルート|
|BMF|[ファウンデーション・モディファイ](#ファウンデーションモディファイbmf)<br>Foundation Modifier|ファウンデーション|モディファイ|`&--`|ルート|
|BML|[レイアウト・モディファイ](#レイアウトモディファイbml)<br>Layout Modifier|レイアウト|モディファイ|`&--`|ルート|
|BMC|[コンポーネント・モディファイ](#コンポーネントモディファイbmc)<br>Component Modifier|コンポーネント|モディファイ|`&--`|ルート|
|BMP|[プロジェクト・モディファイ](#プロジェクトモディファイbmp)<br>Project Modifier|プロジェクト|モディファイ|`&--`|ルート|
|BMU|[ユーティリティ・モディファイ](#ユーティリティモディファイbmu)<br>Utility Modifier|ユーティリティ|モディファイ|`&--`|ルート|
|BMT|[テーマ・モディファイ](#テーマモディファイbmt)<br>Theme Modifier|テーマ|モディファイ|`&--`|ルート|
|PHK|[プレースフォルダ](#プレースフォルダphk)<br>Placeholder Selectors|-|-|`%`|ルート|
|PHY|[要素型・プレースフォルダ](#要素型プレースフォルダphy)<br>Type Placeholder Selectors|-|-|`%XYPh`|ルート|
|PHF|[ファウンデーション・<br>プレースフォルダ](#ファウンデーションプレースフォルダphf)<br>Foundation Placeholder Selectors|ファウンデーション|-|`%XFPh`|ルート|
|PHL|[レイアウト・プレースフォルダ](#レイアウトプレースフォルダphl)<br>Layout Placeholder Selectors|レイアウト|-|`%XLPh`|ルート|
|PHC|[コンポーネント・プレースフォルダ](#コンポーネントプレースフォルダphc)<br>Component Placeholder Selectors|コンポーネント|-|`%XCPh`|ルート|
|PHP|[プロジェクト・プレースフォルダ](#プロジェクトプレースフォルダphp)<br>Project Placeholder Selectors|プロジェクト|-|`%XPPh`|ルート|
|PHU|[ユーティリティ・プレースフォルダ](#ユーティリティプレースフォルダphu)<br>Utility Placeholder Selectors|ユーティリティ|-|`%XUPh`|ルート|
|PHT|[テーマ・プレースフォルダ](#テーマプレースフォルダpht)<br>Theme Placeholder Selectors|テーマ|-|`%XTPh`|ルート|
|EXK|[エクステンド](#エクステンドexk)<br>Extend|-|-|`%`|ルート|
|EXY|[要素型・エクステンド](#要素型エクステンドexy)<br>Type Extend|-|-|`%XFPh`|ルート|
|EXF|[ファウンデーション・エクステンド](#ファウンデーションエクステンドexf)<br>Foundation Extend|ファウンデーション|-|`%XFPh`|ルート|
|EXL|[レイアウト・エクステンド](#レイアウトエクステンドexl)<br>Layout Extend|レイアウト|-|`%XLPh`|ルート|
|EXC|[コンポーネント・エクステンド](#コンポーネントエクステンドexc)<br>Component Extend|コンポーネント|-|`%XCPh`|ルート|
|EXP|[プロジェクト・エクステンド](#プロジェクトエクステンドexp)<br>Project Extend|プロジェクト|-|`%XPPh`|ルート|
|EXU|[ユーティリティ・エクステンド](#ユーティリティエクステンドexu)<br>Utility Extend|ユーティリティ|-|`%XUPh`|ルート|
|EXT|[テーマ・エクステンド](#テーマエクステンドext)<br>Theme Extend|テーマ|-|`%XTPh`|ルート|
|PBK|[ブロック(プレースフォルダ)](#ブロックプレースフォルダpbk)<br>Block (Placeholder Selectors)|不定|ブロック|``|ルート|
|PBF|[ファウンデーション・ブロック(プレースフォルダ)](#ファウンデーションブロックプレースフォルダpbf)<br>Foundation Block (Placeholder Selectors)|ファウンデーション|ブロック|`.f-`|ルート|
|PBL|[レイアウト・ブロック(プレースフォルダ)](#レイアウトブロックプレースフォルダpbl)<br>Layout Block (Placeholder Selectors)|レイアウト|ブロック|`.l-`|ルート|
|PBC|[コンポーネント・ブロック(プレースフォルダ)](#コンポーネントブロックプレースフォルダpbc)<br>Component Block (Placeholder Selectors)|コンポーネント|ブロック|`.c-`|ルート|
|PBP|[プロジェクト・ブロック(プレースフォルダ)](#プロジェクトブロックプレースフォルダpbp)<br>Project Block (Placeholder Selectors)|プロジェクト|ブロック|`.p-`|ルート|
|PBU|[ユーティリティ・ブロック(プレースフォルダ)](#ユーティリティブロックプレースフォルダpbu)<br>Utility Block (Placeholder Selectors)|ユーティリティ|ブロック|`.u-`|ルート|
|PBT|[テーマ・ブロック(プレースフォルダ)](#テーマブロックプレースフォルダpbt)<br>Theme Block (Placeholder Selectors)|テーマ|ブロック|`.t-`|ルート|
|PEK|[エレメント(プレースフォルダ)](#エレメントプレースフォルダpek)<br>Element (Placeholder Selectors)|-|エレメント|`&__`|ルート|
|PEF|[ファウンデーション・エレメント(プレースフォルダ)](#ファウンデーションエレメントプレースフォルダpef)<br>Foundation Element (Placeholder Selectors)|ファウンデーション|エレメント|`&__`|ルート|
|PEL|[レイアウト・エレメント(プレースフォルダ)](#レイアウトエレメントプレースフォルダpel)<br>Layout Element (Placeholder Selectors)|レイアウト|エレメント|`&__`|ルート|
|PEC|[コンポーネント・エレメント(プレースフォルダ)](#コンポーネントエレメントプレースフォルダpec)<br>Component Element (Placeholder Selectors)|コンポーネント|エレメント|`&__`|ルート|
|PEP|[プロジェクト・エレメント(プレースフォルダ)](#プロジェクトエレメントプレースフォルダpep)<br>Project Element (Placeholder Selectors)|プロジェクト|エレメント|`&__`|ルート|
|PEU|[ユーティリティ・エレメント(プレースフォルダ)](#ユーティリティエレメントプレースフォルダpeu)<br>Utility Element (Placeholder Selectors)|ユーティリティ|エレメント|`&__`|ルート|
|PET|[テーマ・エレメント(プレースフォルダ)](#テーマエレメントプレースフォルダpet)<br>Theme Element (Placeholder Selectors)|テーマ|エレメント|`&__`|ルート|
|PMK|[モディファイ(プレースフォルダ)](#モディファイプレースフォルダpmk)<br>Modifier (Placeholder Selectors)|-|モディファイ|`&--`|ルート|
|PMF|[ファウンデーション・モディファイ(プレースフォルダ)](#ファウンデーションモディファイプレースフォルダpmf)<br>Foundation Modifier (Placeholder Selectors)|ファウンデーション|モディファイ|`&--`|ルート|
|PML|[レイアウト・モディファイ(プレースフォルダ)](#レイアウトモディファイプレースフォルダpml)<br>Layout Modifier (Placeholder Selectors)|レイアウト|モディファイ|`&--`|ルート|
|PMC|[コンポーネント・モディファイ(プレースフォルダ)](#コンポーネントモディファイプレースフォルダpmc)<br>Component Modifier (Placeholder Selectors)|コンポーネント|モディファイ|`&--`|ルート|
|PMP|[プロジェクト・モディファイ(プレースフォルダ)](#プロジェクトモディファイプレースフォルダpmp)<br>Project Modifier (Placeholder Selectors)|プロジェクト|モディファイ|`&--`|ルート|
|PMU|[ユーティリティ・モディファイ(プレースフォルダ)](#ユーティリティモディファイプレースフォルダpmu)<br>Utility Modifier (Placeholder Selectors)|ユーティリティ|モディファイ|`&--`|ルート|
|PMT|[テーマ・モディファイ(プレースフォルダ)](#テーマモディファイプレースフォルダpmt)<br>Theme Modifier (Placeholder Selectors)|テーマ|モディファイ|`&--`|ルート|
|RS|[離珠オリジナル](#離珠オリジナルrs)|-|-|なし|ルート|
|RL|[離珠レイアウト](#離珠レイアウトrl)<br>Risyu Layout Block|レイアウト|ブロック|`.XL`|ルート|
|RC|[離珠コンポーネント](#離珠コンポーネントrc)<br>Risyu Component Block|コンポーネント|ブロック|`.XC`|ルート|
|RP|[離珠プロジェクト](#離珠プロジェクトrp)<br>Risyu Project Block|プロジェクト|ブロック|`.XP`|ルート|
|RU|[離珠ユーティリティ](#離珠ユーティリティru)<br>Risyu Utility Block|ユーティリティ|ブロック|`.XU`|ルート|
|SID|[ＩＤ](#ｉｄid)<br>Id Selectors|-|-|`#`|ネスト|
|SCL|[クラス](#クラスcl)<br>Class Selectors|-|-|`.`|ネスト|
|SRO|[ルート](#ルートro)<br>Root|-|-|なし|ルート|
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

### prefix

セレクタの種類で、区分けが必要です。それによりセレクタの編集の為の接頭子として prefix があります。

### その他

セレクタの有無で、区分けが必要です。セレクタの種類での区分けもありますが、あまり細かくは必要ないと思います。(編集規則が明確に一定でないと、処理を用意できない。)

## 処理の例

### ブロック[BBK]

FLOCSSのレイヤーが不定である事を表します。MindBEMdingでの抽象化またはコンポーネントの上位レベルを表すBlockを表します。レイヤーを特に示さず、ただBlockとして扱いたい時に使います。
\[[一覧へ戻る](#一覧)\]

- Scss

  ```Scss
  .f-html {
    @include mrGmBEMStyleRule01('', 'BBK', 'body') {
      margin: 0;
    }
  }
  ```

- Css

  ```Css
  .f-html {}
  .body {margin: 0;}
  ```

### ファウンデーション・ブロック[BBF]

FLOCSSのレイヤーの１つ、ブラウザのデフォルトスタイルの初期化や、プロジェクトにおける基本的なスタイルを定義するFoundationレイヤーを表します。MindBEMdingでの抽象化またはコンポーネントの上位レベルを表すBlockを表します。このレイヤーで敢えてクラスセレクタを用いたい時に使います。
\[[一覧へ戻る](#一覧)\]

- Scss

  ```Scss
  .f-html {
    @include mrGmBEMStyleRule01('', 'BBF', 'body') {
      margin: 0;
    }
  }
  ```

- Css

  ```Css
  .f-html {}
  .f-body {margin: 0;}
  ```

### レイアウト・ブロック[BBL]

FLOCSSのレイヤーの１つ、ページレイアウトから見たスタイルを定義するLayoutレイヤーを表します。MindBEMdingでの抽象化またはコンポーネントの上位レベルを表すBlockを表します。
\[[一覧へ戻る](#一覧)\]

- Scss

  ```Scss
  .l-body {
    @include mrGmBEMStyleRule01('', 'BBL', 'selecter') {
      color: black;
    }
  }
  ```

- Css

  ```Css
  .l-body {}
  .l-selecter {color: black;}
  ```

### コンポーネント・ブロック[BBC]

FLOCSSのレイヤーの１つ、再利用できるパターンとして、小さな単位のモジュールを定義するComponentレイヤーを表します。MindBEMdingでの抽象化またはコンポーネントの上位レベルを表すBlockを表します。
\[[一覧へ戻る](#一覧)\]

- Scss

  ```Scss
  .l-body {
    @include mrGmBEMStyleRule01('', 'BBC', 'selecter') {
      color: black;
    }
  }
  ```

- Css

  ```Css
  .l-body {}
  .c-selecter {color: black;}
  ```

### プロジェクト・ブロック[BBP]

FLOCSSのレイヤーの１つ、プロジェクト固有のパターンを定義するProjectレイヤーを表します。MindBEMdingでの抽象化またはコンポーネントの上位レベルを表すBlockを表します。
\[[一覧へ戻る](#一覧)\]

- Scss

  ```Scss
  .l-body {
    @include mrGmBEMStyleRule01('', 'BBP', 'selecter') {
      color: black;
    }
  }
  ```

- Css

  ```Css
  .l-body {}
  .p-selecter {color: black;}
  ```

### ユーティリティ・ブロック[BBU]

FLOCSSのレイヤーの１つ、ComponentとProjectレイヤーのObjectのモディファイアで解決することが難しい・適切では無い、わずかなスタイルの調整のための便利クラスなどを定義するUtilityレイヤーを表します。MindBEMdingでの抽象化またはコンポーネントの上位レベルを表すBlockを表します。
\[[一覧へ戻る](#一覧)\]

- Scss

  ```Scss
  .l-body {
    @include mrGmBEMStyleRule01('', 'BBU', 'selecter') {
      color: black;
    }
  }
  ```

- Css

  ```Css
  .l-body {}
  .u-selecter {color: black;}
  ```

### テーマ・ブロック[BBT]

FLOCSSのレイヤーではありませんが、サイト全体の見た目を統一させる為の色などを定義するThemeレイヤーを表します。MindBEMdingでの抽象化またはコンポーネントの上位レベルを表すBlockを表します。
\[[一覧へ戻る](#一覧)\]

- Scss

  ```Scss

  .l-body {
    @include mrGmBEMStyleRule01('', 'BBT', 'selecter', null, '.t-theme') {
      color: black;
    }
  }
  ```

- Css

  ```Css
  .l-body {}
  .t-theme .t-selecter {color: black;}
  ```

### エレメント[BEK]

FLOCSSのレイヤーが不定である事を表します。MindBEMdingでの、全体として(.block を形成するのに役立つ) .block の子孫を表すElementを表します。レイヤーを特に示さず、ただElementとして扱いたい時に使います。
\[[一覧へ戻る](#一覧)\]

- Scss

  ```Scss
  .l-body {
    @include mrGmBEMStyleRule01('', 'BEK', 'selecter') {
      color: black;
    }
  }
  ```

- Css

  ```Css
  .l-body {}
  .l-body__selecter {color: black;}
  ```

### ファウンデーション・エレメント[BEF]

FLOCSSのレイヤーの１つ、ブラウザのデフォルトスタイルの初期化や、プロジェクトにおける基本的なスタイルを定義するFoundationレイヤーを表します。MindBEMdingでの、全体として(.block を形成するのに役立つ) .block の子孫を表すElementを表します。
\[[一覧へ戻る](#一覧)\]

- Scss

  ```Scss
  .f-body {
    @include mrGmBEMStyleRule01('', 'BEF', 'selecter') {
      color: black;
    }
  }
  ```

- Css

  ```Css
  .f-body {}
  .f-body__selecter {color: black;}
  ```

### レイアウト・エレメント[BEL]

FLOCSSのレイヤーの１つ、ページレイアウトから見たスタイルを定義するLayoutレイヤーを表します。MindBEMdingでの、全体として(.block を形成するのに役立つ) .block の子孫を表すElementを表します。
\[[一覧へ戻る](#一覧)\]

- Scss

  ```Scss
  .l-body {
    @include mrGmBEMStyleRule01('', 'BEL', 'selecter') {
      color: black;
    }
  }
  ```

- Css

  ```Css
  .l-body {}
  .l-body__selecter {color: black;}
  ```

### コンポーネント・エレメント[BEC]

FLOCSSのレイヤーの１つ、再利用できるパターンとして、小さな単位のモジュールを定義するComponentレイヤーを表します。MindBEMdingでの、全体として(.block を形成するのに役立つ) .block の子孫を表すElementを表します。
\[[一覧へ戻る](#一覧)\]

- Scss

  ```Scss
  .c-body {
    @include mrGmBEMStyleRule01('', 'BEC', 'selecter') {
      color: black;
    }
  }
  ```

- Css

  ```Css
  .c-body {}
  .c-body__selecter {color: black;}
  ```

### プロジェクト・エレメント[BEP]

FLOCSSのレイヤーの１つ、プロジェクト固有のパターンを定義するProjectレイヤーを表します。MindBEMdingでの、全体として(.block を形成するのに役立つ) .block の子孫を表すElementを表します。
\[[一覧へ戻る](#一覧)\]

- Scss

  ```Scss
  .p-body {
    @include mrGmBEMStyleRule01('', 'BEP', 'selecter') {
      color: black;
    }
  }
  ```

- Css

  ```Css
  .p-body {}
  .p-body__selecter {color: black;}
  ```

### ユーティリティ・エレメント[BEU]

FLOCSSのレイヤーの１つ、ComponentとProjectレイヤーのObjectのモディファイアで解決することが難しい・適切では無い、わずかなスタイルの調整のための便利クラスなどを定義するUtilityレイヤーを表します。MindBEMdingでの、全体として(.block を形成するのに役立つ) .block の子孫を表すElementを表します。
\[[一覧へ戻る](#一覧)\]

- Scss

  ```Scss
  .u-body {
    @include mrGmBEMStyleRule01('', 'BEU', 'selecter') {
      color: black;
    }
  }
  ```

- Css

  ```Css
  .u-body {}
  .u-body__selecter {color: black;}
  ```

### テーマ・エレメント[BET]

FLOCSSのレイヤーではありませんが、サイト全体の見た目を統一させる為の色などを定義するThemeレイヤーを表します。MindBEMdingでの、全体として(.block を形成するのに役立つ) .block の子孫を表すElementを表します。
\[[一覧へ戻る](#一覧)\]

- Scss

  ```Scss
  .t-body {
    @include mrGmBEMStyleRule01('', 'BET', 'selecter', null, '.t-theme') {
      color: black;
    }
  }
  ```

- Css

  ```Css
  .t-body {}
  .t-theme t-body__selecter {color: black;}
  ```

### モディファイ[BMK]

FLOCSSのレイヤーが不定である事を表します。MindBEMdingでの、.block 又は Element の異なる状態またはバージョンを表すModifierを表します。レイヤーを特に示さず、ただModifierとして扱いたい時に使います。
\[[一覧へ戻る](#一覧)\]

- Scss

  ```Scss
  .l-body {
    @include mrGmBEMStyleRule01('', 'BMK', 'selecter') {
      color: black;
    }
  }
  ```

- Css

  ```Css
  .l-body, .l-body--selecter {}
  .l-body--selecter {color: black;}
  ```

### ファウンデーション・モディファイ[BMF]

FLOCSSのレイヤーの１つ、ブラウザのデフォルトスタイルの初期化や、プロジェクトにおける基本的なスタイルを定義するFoundationレイヤーを表します。MindBEMdingでの、.block 又は Element の異なる状態またはバージョンを表すModifierを表します。
\[[一覧へ戻る](#一覧)\]

- Scss

  ```Scss
  .f-body {
    @include mrGmBEMStyleRule01('', 'BMF', 'selecter') {
      color: black;
    }
  }
  ```

- Css

  ```Css
  .f-body, .f-body--selecter {}
  .f-body--selecter {color: black;}
  ```

### レイアウト・モディファイ[BML]

FLOCSSのレイヤーの１つ、ページレイアウトから見たスタイルを定義するLayoutレイヤーを表します。MindBEMdingでの、.block 又は Element の異なる状態またはバージョンを表すModifierを表します。
\[[一覧へ戻る](#一覧)\]

- Scss

  ```Scss
  .l-body {
    @include mrGmBEMStyleRule01('', 'BML', 'selecter') {
      color: black;
    }
  }
  ```

- Css

  ```Css
  .l-body, .l-body--selecter {}
  .l-body--selecter {color: black;}
  ```

### コンポーネント・モディファイ[BMC]

FLOCSSのレイヤーの１つ、再利用できるパターンとして、小さな単位のモジュールを定義するComponentレイヤーを表します。MindBEMdingでの、.block 又は Element の異なる状態またはバージョンを表すModifierを表します。
\[[一覧へ戻る](#一覧)\]

- Scss

  ```Scss
  .c-body {
    @include mrGmBEMStyleRule01('', 'BMC', 'selecter') {
      color: black;
    }
  }
  ```

- Css

  ```Css
  .c-body, .c-body--selecter {}
  .c-body--selecter {color: black;}
  ```

### プロジェクト・モディファイ[BMP]

FLOCSSのレイヤーの１つ、プロジェクト固有のパターンを定義するProjectレイヤーを表します。MindBEMdingでの、.block 又は Element の異なる状態またはバージョンを表すModifierを表します。
\[[一覧へ戻る](#一覧)\]

- Scss

  ```Scss
  .p-body {
    @include mrGmBEMStyleRule01('', 'BMP', 'selecter') {
      color: black;
    }
  }
  ```

- Css

  ```Css
  .p-body, .p-body--selecter {}
  .p-body--selecter {color: black;}
  ```

### ユーティリティ・モディファイ[BMU]

FLOCSSのレイヤーの１つ、ComponentとProjectレイヤーのObjectのモディファイアで解決することが難しい・適切では無い、わずかなスタイルの調整のための便利クラスなどを定義するUtilityレイヤーを表します。MindBEMdingでの、.block 又は Element の異なる状態またはバージョンを表すModifierを表します。
\[[一覧へ戻る](#一覧)\]

- Scss

  ```Scss
  .u-body {
    @include mrGmBEMStyleRule01('', 'BMU', 'selecter') {
      color: black;
    }
  }
  ```

- Css

  ```Css
  .u-body, .u-body--selecter {}
  .u-body--selecter {color: black;}
  ```

### テーマ・モディファイ[BMT]

FLOCSSのレイヤーではありませんが、サイト全体の見た目を統一させる為の色などを定義するThemeレイヤーを表します。MindBEMdingでの、.block 又は Element の異なる状態またはバージョンを表すModifierを表します。
\[[一覧へ戻る](#一覧)\]

- Scss

  ```Scss
  .t-body {
    @include mrGmBEMStyleRule01('', 'BMT', 'selecter', null, '.t-theme') {
      color: black;
    }
  }
  ```

- Css

  ```Css
  .t-body, .t-theme t-body--selecter {}
  .t-theme t-body--selecter {color: black;}
  ```

### プレースフォルダ[PHK]

Sassの機能の１つ、CSS出力に含まれないセレクタであるPlaceholder Selectorsを表します。FLOCSSのレイヤーが不定である事を表します。宣言は、拡張する事でCSS出力に含まれます。
\[[一覧へ戻る](#一覧)\]

- Scss

  ```Scss
  .l-body {
    @include mrGmBEMStyleRule01('', 'PHK', 'selecter') {
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

### 要素型・プレースフォルダ[PHY]

Sassの機能の１つ、CSS出力に含まれないセレクタであるPlaceholder Selectorsを表します。要素名をセレクタとして用いる事を表します。宣言は、拡張する事でCSS出力に含まれます。
\[[一覧へ戻る](#一覧)\]

- Scss

  ```Scss
  .l-body {
    @include mrGmBEMStyleRule01('', 'PHY', 'selecter') {
      color: black;
    }
  }
  selecter {
    @extend %selecter !optional;
  }
  ```

- Css

  ```Css
  .l-body {}
  selecter {color: black;}
  ```

### ファウンデーション・プレースフォルダ[PHF]

Sassの機能の１つ、CSS出力に含まれないセレクタであるPlaceholder Selectorsを表します。FLOCSSのレイヤーの１つ、ブラウザのデフォルトスタイルの初期化や、プロジェクトにおける基本的なスタイルを定義するFoundationレイヤーを表します。宣言は、拡張する事でCSS出力に含まれます。レイヤー毎に出力場所を調整する時に用います。
\[[一覧へ戻る](#一覧)\]

- Scss

  ```Scss
  .f-body {
    @include mrGmBEMStyleRule01('', 'PHF', 'selecter') {
      color: black;
    }
  }
  .f-head {
    @extend %XFPhselecter !optional;
  }
  ```

- Css

  ```Css
  .f-body {}
  .f-head {color: black;}
  ```

### レイアウト・プレースフォルダ[PHL]

Sassの機能の１つ、CSS出力に含まれないセレクタであるPlaceholder Selectorsを表します。FLOCSSのレイヤーの１つ、ページレイアウトから見たスタイルを定義するLayoutレイヤーを表します。宣言は、拡張する事でCSS出力に含まれます。レイヤー毎に出力場所を調整する時に用います。
\[[一覧へ戻る](#一覧)\]

- Scss

  ```Scss
  .l-body {
    @include mrGmBEMStyleRule01('', 'PHL', 'selecter') {
      color: black;
    }
  }
  .l-head {
    @extend %XLPhselecter !optional;
  }
  ```

- Css

  ```Css
  .l-body {}
  .l-head {color: black;}
  ```

### コンポーネント・プレースフォルダ[PHC]

Sassの機能の１つ、CSS出力に含まれないセレクタであるPlaceholder Selectorsを表します。FLOCSSのレイヤーの１つ、再利用できるパターンとして、小さな単位のモジュールを定義するComponentレイヤーを表します。宣言は、拡張する事でCSS出力に含まれます。レイヤー毎に出力場所を調整する時に用います。
\[[一覧へ戻る](#一覧)\]

- Scss

  ```Scss
  .c-body {
    @include mrGmBEMStyleRule01('', 'PHC', 'selecter') {
      color: black;
    }
  }
  .c-head {
    @extend %XCPhselecter !optional;
  }
  ```

- Css

  ```Css
  .c-body {}
  .c-head {color: black;}
  ```

### プロジェクト・プレースフォルダ[PHP]

Sassの機能の１つ、CSS出力に含まれないセレクタであるPlaceholder Selectorsを表します。FLOCSSのレイヤーの１つ、プロジェクト固有のパターンを定義するProjectレイヤーを表します。宣言は、拡張する事でCSS出力に含まれます。レイヤー毎に出力場所を調整する時に用います。
\[[一覧へ戻る](#一覧)\]

- Scss

  ```Scss
  .p-body {
    @include mrGmBEMStyleRule01('', 'PHP', 'selecter') {
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

### ユーティリティ・プレースフォルダ[PHU]

Sassの機能の１つ、CSS出力に含まれないセレクタであるPlaceholder Selectorsを表します。FLOCSSのレイヤーの１つ、ComponentとProjectレイヤーのObjectのモディファイアで解決することが難しい・適切では無い、わずかなスタイルの調整のための便利クラスなどを定義するUtilityレイヤーを表します。宣言は、拡張する事でCSS出力に含まれます。レイヤー毎に出力場所を調整する時に用います。
\[[一覧へ戻る](#一覧)\]

- Scss

  ```Scss
  .u-body {
    @include mrGmBEMStyleRule01('', 'PHU', 'selecter') {
      color: black;
    }
  }
  .u-head {
    @extend %XUPhselecter !optional;
  }
  ```

- Css

  ```Css
  .u-body {}
  .u-head {color: black;}
  ```

### テーマ・プレースフォルダ[PHT]

Sassの機能の１つ、CSS出力に含まれないセレクタであるPlaceholder Selectorsを表します。FLOCSSのレイヤーではありませんが、サイト全体の見た目を統一させる為の色などを定義するThemeレイヤーを表します。宣言は、拡張する事でCSS出力に含まれます。レイヤー毎に出力場所を調整する時に用います。
\[[一覧へ戻る](#一覧)\]

- Scss

  ```Scss
  .t-body {
    @include mrGmBEMStyleRule01('', 'PHT', 'selecter') {
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

### エクステンド[EXK]

Sassの機能の１つ、セレクタの拡張を示す@extendを表します。FLOCSSのレイヤーが不定である事を表します。あるセレクターが別のセレクターのスタイルを継承する必要があることを Sass に伝えます。
\[[一覧へ戻る](#一覧)\]

- Scss

  ```Scss
  .l-body {
    @include mrGmBEMStyleRule01('', 'PHK', 'selecter') {
      color: black;
    }
  }
  .l-head {
    @include mrGmBEMStyleRule01('', 'EXK', 'selecter') {
      color: white;
    }
  }
  ```

- Css

  ```Css
  .l-body {}
  .l-head {color: black;}
  ```

### 要素型・エクステンド[EXY]

Sassの機能の１つ、セレクタの拡張を示す@extendを表します。FLOCSSのレイヤーが不定である事を表します。要素名をセレクタとして用いる事を表します。あるセレクターが別のセレクターのスタイルを継承する必要があることを Sass に伝えます。
\[[一覧へ戻る](#一覧)\]

- Scss

  ```Scss
  .l-body {
    @include mrGmBEMStyleRule01('', 'PHY', 'selecter') {
      color: black;
    }
  }
  .l-head {
    @include mrGmBEMStyleRule01('', 'EXY', 'selecter') {
      color: white;
    }
  }
  ```

- Css

  ```Css
  .l-body {}
  selecter {color: black;}
  ```

### ファウンデーション・エクステンド[EXF]

Sassの機能の１つ、セレクタの拡張を示す@extendを表します。FLOCSSのレイヤーの１つ、ブラウザのデフォルトスタイルの初期化や、プロジェクトにおける基本的なスタイルを定義するFoundationレイヤーを表します。ファウンデーション・プレースフォルダセレクタの拡張を示す@extendを表します。レイヤー毎に出力場所を調整する時に用います。
\[[一覧へ戻る](#一覧)\]

- Scss

  ```Scss
  .f-body {
    @include mrGmBEMStyleRule01('', 'PHF', 'selecter') {
      color: black;
    }
  }
  .f-head {
    @include mrGmBEMStyleRule01('', 'EXF', 'selecter');
  }
  ```

- Css

  ```Css
  .f-body {}
  .f-head {color: black;}
  ```

### レイアウト・エクステンド[EXL]

Sassの機能の１つ、セレクタの拡張を示す@extendを表します。FLOCSSのレイヤーの１つ、ページレイアウトから見たスタイルを定義するLayoutレイヤーを表します。レイアウト・プレースフォルダセレクタの拡張を示す@extendを表します。レイヤー毎に出力場所を調整する時に用います。
\[[一覧へ戻る](#一覧)\]

- Scss

  ```Scss
  .l-body {
    @include mrGmBEMStyleRule01('', 'PHL', 'selecter') {
      color: black;
    }
  }
  .l-head {
    @include mrGmBEMStyleRule01('', 'EXL', 'selecter');
  }
  ```

- Css

  ```Css
  .l-body {}
  .l-head {color: black;}
  ```

### コンポーネント・エクステンド[EXC]

Sassの機能の１つ、セレクタの拡張を示す@extendを表します。FLOCSSのレイヤーの１つ、再利用できるパターンとして、小さな単位のモジュールを定義するComponentレイヤーを表します。コンポーネント・プレースフォルダセレクタの拡張を示す@extendを表します。レイヤー毎に出力場所を調整する時に用います。
\[[一覧へ戻る](#一覧)\]

- Scss

  ```Scss
  .c-body {
    @include mrGmBEMStyleRule01('', 'PHC', 'selecter') {
      color: black;
    }
  }
  .c-head {
    @include mrGmBEMStyleRule01('', 'EXC', 'selecter');
  }
  ```

- Css

  ```Css
  .c-body {}
  .c-head {color: black;}
  ```

### プロジェクト・エクステンド[EXP]

Sassの機能の１つ、セレクタの拡張を示す@extendを表します。FLOCSSのレイヤーの１つ、プロジェクト固有のパターンを定義するProjectレイヤーを表します。プロジェクト・プレースフォルダセレクタの拡張を示す@extendを表します。レイヤー毎に出力場所を調整する時に用います。
\[[一覧へ戻る](#一覧)\]

- Scss

  ```Scss
  .p-body {
    @include mrGmBEMStyleRule01('', 'PHP', 'selecter') {
      color: black;
    }
  }
  .p-head {
    @include mrGmBEMStyleRule01('', 'EXP', 'selecter');
  }
  ```

- Css

  ```Css
  .p-body {}
  .p-head {color: black;}
  ```

### ユーティリティ・エクステンド[EXU]

Sassの機能の１つ、セレクタの拡張を示す@extendを表します。FLOCSSのレイヤーの１つ、ComponentとProjectレイヤーのObjectのモディファイアで解決することが難しい・適切では無い、わずかなスタイルの調整のための便利クラスなどを定義するUtilityレイヤーを表します。ユーティリティ・プレースフォルダセレクタの拡張を示す@extendを表します。レイヤー毎に出力場所を調整する時に用います。
\[[一覧へ戻る](#一覧)\]

- Scss

  ```Scss
  .u-body {
    @include mrGmBEMStyleRule01('', 'PHU', 'selecter') {
      color: black;
    }
  }
  .u-head {
    @include mrGmBEMStyleRule01('', 'EXU', 'selecter');
  }
  ```

- Css

  ```Css
  .u-body {}
  .u-head {color: black;}
  ```

### テーマ・エクステンド[EXT]

Sassの機能の１つ、セレクタの拡張を示す@extendを表します。FLOCSSのレイヤーではありませんが、サイト全体の見た目を統一させる為の色などを定義するThemeレイヤーを表します。テーマ・プレースフォルダセレクタの拡張を示す@extendを表します。レイヤー毎に出力場所を調整する時に用います。
\[[一覧へ戻る](#一覧)\]

- Scss

  ```Scss
  .t-body {
    @include mrGmBEMStyleRule01('', 'PHT', 'selecter') {
      color: black;
    }
  }
  .t-head {
    @include mrGmBEMStyleRule01('', 'EXT', 'selecter');
  }
  ```

- Css

  ```Css
  .t-body {}
  .t-head {color: black;}
  ```

### ブロック(プレースフォルダ)[PBK]

FLOCSSのレイヤーが不定である事を表します。MindBEMdingでの抽象化またはコンポーネントの上位レベルを表すBlockを表します。
Sassの機能の１つ、セレクタの拡張を示す@extendを表します。あるセレクターが別のセレクターのスタイルを継承する必要があることを Sass に伝えます。拡張対象が未作成の場合、Sassの機能の１つ、CSS出力に含まれないセレクタであるPlaceholder Selectorsでルールセットを作成して、それを拡張対象とします。
\[[一覧へ戻る](#一覧)\]

- その１(拡張対象が既存の場合)
  - Scss

    ```Scss
    .l-body {
      @include mrGmBEMStyleRule01('', 'PHK', 'selecter') {
        color: black;
      }
    }
    .l-head {
      @include mrGmBEMStyleRule01('', 'PBK', 'selecter') {
        color: white;
      }
    }
    ```

  - Css

    ```Css
    .l-body {}
    .l-selecter {color: black;}
    .l-head {}
    ```

- その２(拡張対象が未作成の場合)
  - Scss

    ```Scss
    .l-head {
      @include mrGmBEMStyleRule01('', 'PBK', 'selecter') {
        color: white;
      }
    }
    ```

  - Css

    ```Css
    .l-head {}
    .l-selecter {color: white;}
    ```

### ファウンデーション・ブロック(プレースフォルダ)[PBF]

FLOCSSのレイヤーの１つ、ブラウザのデフォルトスタイルの初期化や、プロジェクトにおける基本的なスタイルを定義するFoundationレイヤーを表します。MindBEMdingでの抽象化またはコンポーネントの上位レベルを表すBlockを表します。Sassの機能の１つ、セレクタの拡張を示す@extendを表します。あるセレクターが別のセレクターのスタイルを継承する必要があることを Sass に伝えます。拡張対象が未作成の場合、Sassの機能の１つ、CSS出力に含まれないセレクタであるPlaceholder Selectorsでルールセットを作成して、それを拡張対象とします。
\[[一覧へ戻る](#一覧)\]

- その１(拡張対象が既存の場合)
  - Scss

    ```Scss
    .f-body {
      @include mrGmBEMStyleRule01('', 'PHF', 'selecter') {
        color: black;
      }
    }
    .f-head {
      @include mrGmBEMStyleRule01('', 'PBF', 'selecter') {
        color: white;
      }
    }
    ```

  - Css

    ```Css
    .f-body {}
    .f-selecter {color: black;}
    .f-head {}
    ```

- その２(拡張対象が未作成の場合)
  - Scss

    ```Scss
    .f-head {
      @include mrGmBEMStyleRule01('', 'PBF', 'selecter') {
        color: white;
      }
    }
    ```

  - Css

    ```Css
    .f-head {}
    .f-selecter {color: white;}
    ```

### レイアウト・ブロック(プレースフォルダ)[PBL]

FLOCSSのレイヤーの１つ、ページレイアウトから見たスタイルを定義するLayoutレイヤーを表します。MindBEMdingでの抽象化またはコンポーネントの上位レベルを表すBlockを表します。Sassの機能の１つ、セレクタの拡張を示す@extendを表します。あるセレクターが別のセレクターのスタイルを継承する必要があることを Sass に伝えます。拡張対象が未作成の場合、Sassの機能の１つ、CSS出力に含まれないセレクタであるPlaceholder Selectorsでルールセットを作成して、それを拡張対象とします。
\[[一覧へ戻る](#一覧)\]

- その１(拡張対象が既存の場合)
  - Scss

    ```Scss
    .l-body {
      @include mrGmBEMStyleRule01('', 'PHL', 'selecter') {
        color: black;
      }
    }
    .l-head {
      @include mrGmBEMStyleRule01('', 'PBL', 'selecter') {
        color: white;
      }
    }
    ```

  - Css

    ```Css
    .l-body {}
    .l-selecter {color: black;}
    .l-head {}
    ```

- その２(拡張対象が未作成の場合)
  - Scss

    ```Scss
    .l-head {
      @include mrGmBEMStyleRule01('', 'PBL', 'selecter') {
        color: white;
      }
    }
    ```

  - Css

    ```Css
    .l-head {}
    .l-selecter {color: white;}
    ```

### コンポーネント・ブロック(プレースフォルダ)[PBC]

FLOCSSのレイヤーの１つ、再利用できるパターンとして、小さな単位のモジュールを定義するComponentレイヤーを表します。MindBEMdingでの抽象化またはコンポーネントの上位レベルを表すBlockを表します。Sassの機能の１つ、セレクタの拡張を示す@extendを表します。あるセレクターが別のセレクターのスタイルを継承する必要があることを Sass に伝えます。拡張対象が未作成の場合、Sassの機能の１つ、CSS出力に含まれないセレクタであるPlaceholder Selectorsでルールセットを作成して、それを拡張対象とします。
\[[一覧へ戻る](#一覧)\]

- その１(拡張対象が既存の場合)
  - Scss

    ```Scss
    .c-body {
      @include mrGmBEMStyleRule01('', 'PHC', 'selecter') {
        color: black;
      }
    }
    .c-head {
      @include mrGmBEMStyleRule01('', 'PBC', 'selecter') {
        color: white;
      }
    }
    ```

  - Css

    ```Css
    .c-body {}
    .c-selecter {color: black;}
    .c-head {}
    ```

- その２(拡張対象が未作成の場合)
  - Scss

    ```Scss
    .c-head {
      @include mrGmBEMStyleRule01('', 'PBC', 'selecter') {
        color: white;
      }
    }
    ```

  - Css

    ```Css
    .c-head {}
    .c-selecter {color: white;}
    ```

### プロジェクト・ブロック(プレースフォルダ)[PBP]

FLOCSSのレイヤーの１つ、プロジェクト固有のパターンを定義するProjectレイヤーを表します。MindBEMdingでの抽象化またはコンポーネントの上位レベルを表すBlockを表します。Sassの機能の１つ、セレクタの拡張を示す@extendを表します。あるセレクターが別のセレクターのスタイルを継承する必要があることを Sass に伝えます。拡張対象が未作成の場合、Sassの機能の１つ、CSS出力に含まれないセレクタであるPlaceholder Selectorsでルールセットを作成して、それを拡張対象とします。
\[[一覧へ戻る](#一覧)\]

- その１(拡張対象が既存の場合)
  - Scss

    ```Scss
    .p-body {
      @include mrGmBEMStyleRule01('', 'PHP', 'selecter') {
        color: black;
      }
    }
    .p-head {
      @include mrGmBEMStyleRule01('', 'PBP', 'selecter') {
        color: white;
      }
    }
    ```

  - Css

    ```Css
    .p-body {}
    .p-selecter {color: black;}
    .p-head {}
    ```

- その２(拡張対象が未作成の場合)
  - Scss

    ```Scss
    .p-head {
      @include mrGmBEMStyleRule01('', 'PBP', 'selecter') {
        color: white;
      }
    }
    ```

  - Css

    ```Css
    .p-head {}
    .p-selecter {color: white;}
    ```

### ユーティリティ・ブロック(プレースフォルダ)[PBU]

FLOCSSのレイヤーの１つ、ComponentとProjectレイヤーのObjectのモディファイアで解決することが難しい・適切では無い、わずかなスタイルの調整のための便利クラスなどを定義するUtilityレイヤーを表します。MindBEMdingでの抽象化またはコンポーネントの上位レベルを表すBlockを表します。Sassの機能の１つ、セレクタの拡張を示す@extendを表します。あるセレクターが別のセレクターのスタイルを継承する必要があることを Sass に伝えます。拡張対象が未作成の場合、Sassの機能の１つ、CSS出力に含まれないセレクタであるPlaceholder Selectorsでルールセットを作成して、それを拡張対象とします。
\[[一覧へ戻る](#一覧)\]

- その１(拡張対象が既存の場合)
  - Scss

    ```Scss
    .u-body {
      @include mrGmBEMStyleRule01('', 'PHU', 'selecter') {
        color: black;
      }
    }
    .u-head {
      @include mrGmBEMStyleRule01('', 'PBU', 'selecter') {
        color: white;
      }
    }
    ```

  - Css

    ```Css
    .u-body {}
    .u-selecter {color: black;}
    .u-head {}
    ```

- その２(拡張対象が未作成の場合)
  - Scss

    ```Scss
    .u-head {
      @include mrGmBEMStyleRule01('', 'PBU', 'selecter') {
        color: white;
      }
    }
    ```

  - Css

    ```Css
    .u-head {}
    .u-selecter {color: white;}
    ```

### テーマ・ブロック(プレースフォルダ)[PBT]

FLOCSSのレイヤーではありませんが、サイト全体の見た目を統一させる為の色などを定義するThemeレイヤーを表します。MindBEMdingでの抽象化またはコンポーネントの上位レベルを表すBlockを表します。Sassの機能の１つ、セレクタの拡張を示す@extendを表します。あるセレクターが別のセレクターのスタイルを継承する必要があることを Sass に伝えます。拡張対象が未作成の場合、Sassの機能の１つ、CSS出力に含まれないセレクタであるPlaceholder Selectorsでルールセットを作成して、それを拡張対象とします。
\[[一覧へ戻る](#一覧)\]

- その１(拡張対象が既存の場合)
  - Scss

    ```Scss
    .t-body {
      @include mrGmBEMStyleRule01('', 'PHT', 'selecter') {
        color: black;
      }
    }
    .t-head {
      @include mrGmBEMStyleRule01('', 'PBT', 'selecter') {
        color: white;
      }
    }
    ```

  - Css

    ```Css
    .t-body {}
    .t-selecter {color: black;}
    .t-head {}
    ```

- その２(拡張対象が未作成の場合)
  - Scss

    ```Scss
    .t-head {
      @include mrGmBEMStyleRule01('', 'PBT', 'selecter') {
        color: white;
      }
    }
    ```

  - Css

    ```Css
    .t-head {}
    .t-selecter {color: white;}
    ```

### エレメント(プレースフォルダ)[PEK]

FLOCSSのレイヤーが不定である事を表します。MindBEMdingでの、全体として(.block を形成するのに役立つ) .block の子孫を表すElementを表します。
Sassの機能の１つ、セレクタの拡張を示す@extendを表します。あるセレクターが別のセレクターのスタイルを継承する必要があることを Sass に伝えます。拡張対象が未作成の場合、Sassの機能の１つ、CSS出力に含まれないセレクタであるPlaceholder Selectorsでルールセットを作成して、それを拡張対象とします。
\[[一覧へ戻る](#一覧)\]

- その１(拡張対象が既存の場合)
  - Scss

    ```Scss
    .l-body {
      @include mrGmBEMStyleRule01('', 'PHK', 'selecter') {
        color: black;
      }
    }
    .l-head {
      @include mrGmBEMStyleRule01('', 'PEK', 'selecter') {
        color: white;
      }
    }
    ```

  - Css

    ```Css
    .l-body {}
    .l-head__selecter {color: black;}
    .l-head {}
    ```

- その２(拡張対象が未作成の場合)
  - Scss

    ```Scss
    .l-head {
      @include mrGmBEMStyleRule01('', 'PEK', 'selecter') {
        color: white;
      }
    }
    ```

  - Css

    ```Css
    .l-head {}
    .l-head__selecter {color: white;}
    ```

### ファウンデーション・エレメント(プレースフォルダ)[PEF]

FLOCSSのレイヤーの１つ、ブラウザのデフォルトスタイルの初期化や、プロジェクトにおける基本的なスタイルを定義するFoundationレイヤーを表します。MindBEMdingでの、全体として(.block を形成するのに役立つ) .block の子孫を表すElementを表します。Sassの機能の１つ、セレクタの拡張を示す@extendを表します。あるセレクターが別のセレクターのスタイルを継承する必要があることを Sass に伝えます。拡張対象が未作成の場合、Sassの機能の１つ、CSS出力に含まれないセレクタであるPlaceholder Selectorsでルールセットを作成して、それを拡張対象とします。
\[[一覧へ戻る](#一覧)\]

- その１(拡張対象が既存の場合)
  - Scss

    ```Scss
    .f-body {
      @include mrGmBEMStyleRule01('', 'PHF', 'selecter') {
        color: black;
      }
    }
    .f-head {
      @include mrGmBEMStyleRule01('', 'PEF', 'selecter') {
        color: white;
      }
    }
    ```

  - Css

    ```Css
    .f-body {}
    .f-head__selecter {color: black;}
    .f-head {}
    ```

- その２(拡張対象が未作成の場合)
  - Scss

    ```Scss
    .f-head {
      @include mrGmBEMStyleRule01('', 'PEF', 'selecter') {
        color: white;
      }
    }
    ```

  - Css

    ```Css
    .f-head {}
    .f-head__selecter {color: white;}
    ```

### レイアウト・エレメント(プレースフォルダ)[PEL]

FLOCSSのレイヤーの１つ、ページレイアウトから見たスタイルを定義するLayoutレイヤーを表します。MindBEMdingでの、全体として(.block を形成するのに役立つ) .block の子孫を表すElementを表します。Sassの機能の１つ、セレクタの拡張を示す@extendを表します。あるセレクターが別のセレクターのスタイルを継承する必要があることを Sass に伝えます。拡張対象が未作成の場合、Sassの機能の１つ、CSS出力に含まれないセレクタであるPlaceholder Selectorsでルールセットを作成して、それを拡張対象とします。
\[[一覧へ戻る](#一覧)\]

- その１(拡張対象が既存の場合)
  - Scss

    ```Scss
    .l-body {
      @include mrGmBEMStyleRule01('', 'PHL', 'selecter') {
        color: black;
      }
    }
    .l-head {
      @include mrGmBEMStyleRule01('', 'PEL', 'selecter') {
        color: white;
      }
    }
    ```

  - Css

    ```Css
    .l-body {}
    .l-head__selecter {color: black;}
    .l-head {}
    ```

- その２(拡張対象が未作成の場合)
  - Scss

    ```Scss
    .l-head {
      @include mrGmBEMStyleRule01('', 'PEL', 'selecter') {
        color: white;
      }
    }
    ```

  - Css

    ```Css
    .l-head {}
    .l-head__selecter {color: white;}
    ```

### コンポーネント・エレメント(プレースフォルダ)[PEC]

FLOCSSのレイヤーの１つ、再利用できるパターンとして、小さな単位のモジュールを定義するComponentレイヤーを表します。MindBEMdingでの、全体として(.block を形成するのに役立つ) .block の子孫を表すElementを表します。Sassの機能の１つ、セレクタの拡張を示す@extendを表します。あるセレクターが別のセレクターのスタイルを継承する必要があることを Sass に伝えます。拡張対象が未作成の場合、Sassの機能の１つ、CSS出力に含まれないセレクタであるPlaceholder Selectorsでルールセットを作成して、それを拡張対象とします。
\[[一覧へ戻る](#一覧)\]

- その１(拡張対象が既存の場合)
  - Scss

    ```Scss
    .c-body {
      @include mrGmBEMStyleRule01('', 'PHC', 'selecter') {
        color: black;
      }
    }
    .c-head {
      @include mrGmBEMStyleRule01('', 'PEC', 'selecter') {
        color: white;
      }
    }
    ```

  - Css

    ```Css
    .c-body {}
    .c-head__selecter {color: black;}
    .c-head {}
    ```

- その２(拡張対象が未作成の場合)
  - Scss

    ```Scss
    .c-head {
      @include mrGmBEMStyleRule01('', 'PEC', 'selecter') {
        color: white;
      }
    }
    ```

  - Css

    ```Css
    .c-head {}
    .c-head__selecter {color: white;}
    ```

### プロジェクト・エレメント(プレースフォルダ)[PEP]

FLOCSSのレイヤーの１つ、プロジェクト固有のパターンを定義するProjectレイヤーを表します。MindBEMdingでの、全体として(.block を形成するのに役立つ) .block の子孫を表すElementを表します。Sassの機能の１つ、セレクタの拡張を示す@extendを表します。あるセレクターが別のセレクターのスタイルを継承する必要があることを Sass に伝えます。拡張対象が未作成の場合、Sassの機能の１つ、CSS出力に含まれないセレクタであるPlaceholder Selectorsでルールセットを作成して、それを拡張対象とします。
\[[一覧へ戻る](#一覧)\]

- その１(拡張対象が既存の場合)
  - Scss

    ```Scss
    .p-body {
      @include mrGmBEMStyleRule01('', 'PHP', 'selecter') {
        color: black;
      }
    }
    .p-head {
      @include mrGmBEMStyleRule01('', 'PEP', 'selecter') {
        color: white;
      }
    }
    ```

  - Css

    ```Css
    .p-body {}
    .p-head__selecter {color: black;}
    .p-head {}
    ```

- その２(拡張対象が未作成の場合)
  - Scss

    ```Scss
    .p-head {
      @include mrGmBEMStyleRule01('', 'PEP', 'selecter') {
        color: white;
      }
    }
    ```

  - Css

    ```Css
    .p-head {}
    .p-head__selecter {color: white;}
    ```

### ユーティリティ・エレメント(プレースフォルダ)[PEU]

FLOCSSのレイヤーの１つ、ComponentとProjectレイヤーのObjectのモディファイアで解決することが難しい・適切では無い、わずかなスタイルの調整のための便利クラスなどを定義するUtilityレイヤーを表します。MindBEMdingでの、全体として(.block を形成するのに役立つ) .block の子孫を表すElementを表します。Sassの機能の１つ、セレクタの拡張を示す@extendを表します。あるセレクターが別のセレクターのスタイルを継承する必要があることを Sass に伝えます。拡張対象が未作成の場合、Sassの機能の１つ、CSS出力に含まれないセレクタであるPlaceholder Selectorsでルールセットを作成して、それを拡張対象とします。
\[[一覧へ戻る](#一覧)\]

- その１(拡張対象が既存の場合)
  - Scss

    ```Scss
    .u-body {
      @include mrGmBEMStyleRule01('', 'PHU', 'selecter') {
        color: black;
      }
    }
    .u-head {
      @include mrGmBEMStyleRule01('', 'PEU', 'selecter') {
        color: white;
      }
    }
    ```

  - Css

    ```Css
    .u-body {}
    .u-head__selecter {color: black;}
    .u-head {}
    ```

- その２(拡張対象が未作成の場合)
  - Scss

    ```Scss
    .u-head {
      @include mrGmBEMStyleRule01('', 'PEU', 'selecter') {
        color: white;
      }
    }
    ```

  - Css

    ```Css
    .u-head {}
    .u-head__selecter {color: white;}
    ```

### テーマ・エレメント(プレースフォルダ)[PET]

FLOCSSのレイヤーではありませんが、サイト全体の見た目を統一させる為の色などを定義するThemeレイヤーを表します。MindBEMdingでの、全体として(.block を形成するのに役立つ) .block の子孫を表すElementを表します。Sassの機能の１つ、セレクタの拡張を示す@extendを表します。あるセレクターが別のセレクターのスタイルを継承する必要があることを Sass に伝えます。拡張対象が未作成の場合、Sassの機能の１つ、CSS出力に含まれないセレクタであるPlaceholder Selectorsでルールセットを作成して、それを拡張対象とします。
\[[一覧へ戻る](#一覧)\]

- その１(拡張対象が既存の場合)
  - Scss

    ```Scss
    .t-body {
      @include mrGmBEMStyleRule01('', 'PHT', 'selecter') {
        color: black;
      }
    }
    .t-head {
      @include mrGmBEMStyleRule01('', 'PET', 'selecter') {
        color: white;
      }
    }
    ```

  - Css

    ```Css
    .t-body {}
    .t-head__selecter {color: black;}
    .t-head {}
    ```

- その２(拡張対象が未作成の場合)
  - Scss

    ```Scss
    .t-head {
      @include mrGmBEMStyleRule01('', 'PET', 'selecter') {
        color: white;
      }
    }
    ```

  - Css

    ```Css
    .t-head {}
    .t-head__selecter {color: white;}
    ```

### モディファイ(プレースフォルダ)[PMK]

FLOCSSのレイヤーが不定である事を表します。MindBEMdingでの、.block 又は Element の異なる状態またはバージョンを表すModifierを表します。
Sassの機能の１つ、セレクタの拡張を示す@extendを表します。あるセレクターが別のセレクターのスタイルを継承する必要があることを Sass に伝えます。拡張対象が未作成の場合、Sassの機能の１つ、CSS出力に含まれないセレクタであるPlaceholder Selectorsでルールセットを作成して、それを拡張対象とします。
\[[一覧へ戻る](#一覧)\]

- その１(拡張対象が既存の場合)
  - Scss

    ```Scss
    .l-body {
      @include mrGmBEMStyleRule01('', 'PHK', 'selecter') {
        color: black;
      }
    }
    .l-head {
      @include mrGmBEMStyleRule01('', 'PMK', 'selecter') {
        color: white;
      }
    }
    ```

  - Css

    ```Css
    .l-body {}
    .l-head--selecter {color: black;}
    .l-head, .l-head--selecter {}
    ```

- その２(拡張対象が未作成の場合)
  - Scss

    ```Scss
    .l-head {
      @include mrGmBEMStyleRule01('', 'PMK', 'selecter') {
        color: white;
      }
    }
    ```

  - Css

    ```Css
    .l-head, .l-head--selecter {}
    .l-head--selecter {color: white;}
    ```

### ファウンデーション・モディファイ(プレースフォルダ)[PMF]

FLOCSSのレイヤーの１つ、ブラウザのデフォルトスタイルの初期化や、プロジェクトにおける基本的なスタイルを定義するFoundationレイヤーを表します。MindBEMdingでの、.block 又は Element の異なる状態またはバージョンを表すModifierを表します。Sassの機能の１つ、セレクタの拡張を示す@extendを表します。あるセレクターが別のセレクターのスタイルを継承する必要があることを Sass に伝えます。拡張対象が未作成の場合、Sassの機能の１つ、CSS出力に含まれないセレクタであるPlaceholder Selectorsでルールセットを作成して、それを拡張対象とします。
\[[一覧へ戻る](#一覧)\]

- その１(拡張対象が既存の場合)
  - Scss

    ```Scss
    .f-body {
      @include mrGmBEMStyleRule01('', 'PHF', 'selecter') {
        color: black;
      }
    }
    .f-head {
      @include mrGmBEMStyleRule01('', 'PMF', 'selecter') {
        color: white;
      }
    }
    ```

  - Css

    ```Css
    .f-body {}
    .f-head--selecter {color: black;}
    .f-head, .f-head--selecter {}
    ```

- その２(拡張対象が未作成の場合)
  - Scss

    ```Scss
    .f-head {
      @include mrGmBEMStyleRule01('', 'PMF', 'selecter') {
        color: white;
      }
    }
    ```

  - Css

    ```Css
    .f-head, .f-head--selecter {}
    .f-head--selecter {color: white;}
    ```

### レイアウト・モディファイ(プレースフォルダ)[PML]

FLOCSSのレイヤーの１つ、ページレイアウトから見たスタイルを定義するLayoutレイヤーを表します。MindBEMdingでの、.block 又は Element の異なる状態またはバージョンを表すModifierを表します。Sassの機能の１つ、セレクタの拡張を示す@extendを表します。あるセレクターが別のセレクターのスタイルを継承する必要があることを Sass に伝えます。拡張対象が未作成の場合、Sassの機能の１つ、CSS出力に含まれないセレクタであるPlaceholder Selectorsでルールセットを作成して、それを拡張対象とします。
\[[一覧へ戻る](#一覧)\]

- その１(拡張対象が既存の場合)
  - Scss

    ```Scss
    .l-body {
      @include mrGmBEMStyleRule01('', 'PHL', 'selecter') {
        color: black;
      }
    }
    .l-head {
      @include mrGmBEMStyleRule01('', 'PEL', 'selecter') {
        color: white;
      }
    }
    ```

  - Css

    ```Css
    .l-body {}
    .l-head__selecter {color: black;}
    .l-head {}
    ```

- その２(拡張対象が未作成の場合)
  - Scss

    ```Scss
    .l-head {
      @include mrGmBEMStyleRule01('', 'PEL', 'selecter') {
        color: white;
      }
    }
    ```

  - Css

    ```Css
    .l-head {}
    .l-head__selecter {color: white;}
    ```

### コンポーネント・モディファイ(プレースフォルダ)[PMC]

FLOCSSのレイヤーの１つ、再利用できるパターンとして、小さな単位のモジュールを定義するComponentレイヤーを表します。MindBEMdingでの、.block 又は Element の異なる状態またはバージョンを表すModifierを表します。Sassの機能の１つ、セレクタの拡張を示す@extendを表します。あるセレクターが別のセレクターのスタイルを継承する必要があることを Sass に伝えます。拡張対象が未作成の場合、Sassの機能の１つ、CSS出力に含まれないセレクタであるPlaceholder Selectorsでルールセットを作成して、それを拡張対象とします。
\[[一覧へ戻る](#一覧)\]

- その１(拡張対象が既存の場合)
  - Scss

    ```Scss
    .c-body {
      @include mrGmBEMStyleRule01('', 'PHC', 'selecter') {
        color: black;
      }
    }
    .c-head {
      @include mrGmBEMStyleRule01('', 'PEC', 'selecter') {
        color: white;
      }
    }
    ```

  - Css

    ```Css
    .c-body {}
    .c-head__selecter {color: black;}
    .c-head {}
    ```

- その２(拡張対象が未作成の場合)
  - Scss

    ```Scss
    .c-head {
      @include mrGmBEMStyleRule01('', 'PEC', 'selecter') {
        color: white;
      }
    }
    ```

  - Css

    ```Css
    .c-head {}
    .c-head__selecter {color: white;}
    ```

### プロジェクト・モディファイ(プレースフォルダ)[PMP]

FLOCSSのレイヤーの１つ、プロジェクト固有のパターンを定義するProjectレイヤーを表します。MindBEMdingでの、.block 又は Element の異なる状態またはバージョンを表すModifierを表します。Sassの機能の１つ、セレクタの拡張を示す@extendを表します。あるセレクターが別のセレクターのスタイルを継承する必要があることを Sass に伝えます。拡張対象が未作成の場合、Sassの機能の１つ、CSS出力に含まれないセレクタであるPlaceholder Selectorsでルールセットを作成して、それを拡張対象とします。
\[[一覧へ戻る](#一覧)\]

- その１(拡張対象が既存の場合)
  - Scss

    ```Scss
    .p-body {
      @include mrGmBEMStyleRule01('', 'PHP', 'selecter') {
        color: black;
      }
    }
    .p-head {
      @include mrGmBEMStyleRule01('', 'PEP', 'selecter') {
        color: white;
      }
    }
    ```

  - Css

    ```Css
    .p-body {}
    .p-head__selecter {color: black;}
    .p-head {}
    ```

- その２(拡張対象が未作成の場合)
  - Scss

    ```Scss
    .p-head {
      @include mrGmBEMStyleRule01('', 'PEP', 'selecter') {
        color: white;
      }
    }
    ```

  - Css

    ```Css
    .p-head {}
    .p-head__selecter {color: white;}
    ```

### ユーティリティ・モディファイ(プレースフォルダ)[PMU]

FLOCSSのレイヤーの１つ、ComponentとProjectレイヤーのObjectのモディファイアで解決することが難しい・適切では無い、わずかなスタイルの調整のための便利クラスなどを定義するUtilityレイヤーを表します。MindBEMdingでの、.block 又は Element の異なる状態またはバージョンを表すModifierを表します。Sassの機能の１つ、セレクタの拡張を示す@extendを表します。あるセレクターが別のセレクターのスタイルを継承する必要があることを Sass に伝えます。拡張対象が未作成の場合、Sassの機能の１つ、CSS出力に含まれないセレクタであるPlaceholder Selectorsでルールセットを作成して、それを拡張対象とします。
\[[一覧へ戻る](#一覧)\]

- その１(拡張対象が既存の場合)
  - Scss

    ```Scss
    .u-body {
      @include mrGmBEMStyleRule01('', 'PHU', 'selecter') {
        color: black;
      }
    }
    .u-head {
      @include mrGmBEMStyleRule01('', 'PEU', 'selecter') {
        color: white;
      }
    }
    ```

  - Css

    ```Css
    .u-body {}
    .u-head__selecter {color: black;}
    .u-head {}
    ```

- その２(拡張対象が未作成の場合)
  - Scss

    ```Scss
    .u-head {
      @include mrGmBEMStyleRule01('', 'PEU', 'selecter') {
        color: white;
      }
    }
    ```

  - Css

    ```Css
    .u-head {}
    .u-head__selecter {color: white;}
    ```

### テーマ・モディファイ(プレースフォルダ)[PMT]

FLOCSSのレイヤーではありませんが、サイト全体の見た目を統一させる為の色などを定義するThemeレイヤーを表します。MindBEMdingでの、.block 又は Element の異なる状態またはバージョンを表すModifierを表します。Sassの機能の１つ、セレクタの拡張を示す@extendを表します。あるセレクターが別のセレクターのスタイルを継承する必要があることを Sass に伝えます。拡張対象が未作成の場合、Sassの機能の１つ、CSS出力に含まれないセレクタであるPlaceholder Selectorsでルールセットを作成して、それを拡張対象とします。
\[[一覧へ戻る](#一覧)\]

- その１(拡張対象が既存の場合)
  - Scss

    ```Scss
    .t-body {
      @include mrGmBEMStyleRule01('', 'PHT', 'selecter') {
        color: black;
      }
    }
    .t-head {
      @include mrGmBEMStyleRule01('', 'PET', 'selecter') {
        color: white;
      }
    }
    ```

  - Css

    ```Css
    .t-body {}
    .t-head__selecter {color: black;}
    .t-head {}
    ```

- その２(拡張対象が未作成の場合)
  - Scss

    ```Scss
    .t-head {
      @include mrGmBEMStyleRule01('', 'PET', 'selecter') {
        color: white;
      }
    }
    ```

  - Css

    ```Css
    .t-head {}
    .t-head__selecter {color: white;}
    ```

### 離珠オリジナル[RSK]

作者オリジナルのセレクタの命名規則を表します。MindBEMdingでの抽象化またはコンポーネントの上位レベルを表すBlockだけにクラスセレクタを用い、その子孫は要素セレクタを用いるという規則にしています。制作意図を表すだけで、機能はルートと同じです。
\[[一覧へ戻る](#一覧)\]

- Scss

  ```Scss
  .l-body {
    @include mrGmBEMStyleRule01('', 'RSK', 'head') {
      color: black;
    }
  }
  ```

- Css

  ```Css
  .l-body {}
  .XKhead {color: black;}
  ```

### 離珠ファウンデーション[RSF]

作者オリジナルのセレクタの命名規則を表します。MindBEMdingでの抽象化またはコンポーネントの上位レベルを表すBlockだけにクラスセレクタを用い、その子孫は要素セレクタを用いるという規則にしています。
FLOCSSのレイヤーの１つ、ブラウザのデフォルトスタイルの初期化や、プロジェクトにおける基本的なスタイルを定義するFoundationレイヤーを表します。このレイヤーで敢えてクラスセレクタを用いたい時に使います。
\[[一覧へ戻る](#一覧)\]

- Scss

  ```Scss
  .l-body {
    @include mrGmBEMStyleRule01('', 'RSF', 'head') {
      color: black;
    }
  }
  ```

- Css

  ```Css
  .l-body {}
  .XFhead {color: black;}
  ```

### 離珠レイアウト[RSL]

作者オリジナルのセレクタの命名規則を表します。MindBEMdingでの抽象化またはコンポーネントの上位レベルを表すBlockだけにクラスセレクタを用い、その子孫は要素セレクタを用いるという規則にしています。
FLOCSSのレイヤーの１つ、ページレイアウトから見たスタイルを定義するLayoutレイヤーを表します。
\[[一覧へ戻る](#一覧)\]

- Scss

  ```Scss
  .l-body {
    @include mrGmBEMStyleRule01('RSL', 'head', 'F') {
      color: black;
    }
  }
  ```

- Css

  ```Css
  .l-body {}
  .XLhead {color: black;}
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

## 補足

- [BEM](https://github.com/juno/bem-methodology-ja/blob/master/definitions.md)は、CSS設計の一つです。
- [FLOCSS](https://github.com/hiloki/flocss)は、CSS設計の一つです。

## 作成者

Copyright(C) 2022-2025 KOUTAN
