# 文書体系・一覧

このファイルは、開発の前提資料として、「文書体系・一覧」をまとめたものです。

このフォルダについての説明は、[`README.md`](./README.md) に記載しています。

## この文書について

本書は、文書群の体系的な構成を示すものであり、いわゆる管理文書ではありません。  
実際の運用状況を正確に反映することを目的としたものではなく、構造や方針の理解を補助するための資料です。

なお、資料としての更新や加筆は妨げませんが、必ず全体の方針や位置づけが把握できるよう配慮してください。

## 文書体系

```体系
書類倉庫
├── 00_Materials/
│   ├── development_process.md
│   ├── document_structure.md
│   ├── document_relationships.md
│   ├── tools_policy.md
│   ├── folder_policy.md
│   └── glossary.md
│
├── 10_Principles/
│   ├── basicprinciples.md
│   └── supplement_internalrules.md
│
├── 20_Design/
│   ├── coding.md
│   ├── writing.md
│   ├── comment.md
│   ├── Naming/
│   │   ├── namingpolicy.md
│   │   ├── namingfolder.md
│   │   ├── namingmember.md
│   │   └── namingselector.md
│   └── Structure/
│       └── structure.md
│
├── 30_Usagerules/
│   ├── bemclassification.md
│   ├── config.md
│   └── global.md
│
├── 40_Reference/
│   ├── preparation.md
│   ├── environment.md
│   ├── nodejs.md
│   └── setting.md
│
├── 50_Supporting/
│   ├── Checklist/
│   ├── Faq/
│   └── Technotes/
│
└── README.md
```

## 各フォルダの意図と用途

|フォルダ名|日本語名|用途（備考含む）|
|:-:|----|----|
|00_Materials/|前提資料|開発・文書全体の枠組みを示す基礎資料。前提や構成、語彙などを整理。|
|10_Principles/|基本原則|設計判断の最上位規範。「設計の設計」に相当。|
|20_Design/|設計方針|命名・構造・記述に関する各種設計指針。機能や記法のルールも含む。|
|30_Usagerules/|内部仕様|コード・変数のローカル仕様。BEMや制御変数など内部向け技術文書。|
|40_Reference/|開発環境|環境構築・実行基盤の手順やメモ。OS、Node.js、Gulp等の記録。|
|50_Supporting/|補助資料|チェックリストや調査メモ、清書前の技術メモなど。|
|`README.md`|（概要）|このフォルダ以下の構成と目的を記述した概要文書。|

## 文書一覧

|ファイル名|文書名|用途（備考含む）|
|:-:|----|----|
|`development_process.md`|開発プロセス・概要|プロジェクト開発の進行方針・手順の整理。|
|`document_structure.md`|文書体系・一覧|現文書。全体の文書構成と配置の記録。|
|`document_relationships.md`|文書関連図|文書間の依存関係や関連図を記載。|
|`tools_policy.md`|使用ツール・言語方針|Sass / Pug の採用方針、gulp や VSCode の使用方針など、開発技術の前提条件を記載。|
|`folder_policy.md`|フォルダ構成・方針|フォルダ命名・分類に関する方針記録。|
|`glossary.md`|用語集|特殊な語彙・略語の整理。現在は使用最小限の方針。|
||||
|`basicprinciples.md`|基本原則|設計判断の基本的な規則と思想。|
|`supplement_internalrules.md`|補足・内部規則構造図|内部規則の構造補足。現在は基本原則末尾に添付。|
||||
|`coding.md`|機能利用・設計規則|機能単位の設計・記述方法に関するルール。|
|`writing.md`|記述規則|ファイル記述スタイルに関する一般ルール。|
|`comment.md`|コメント記述規則|JSDoc, SassDoc を想定したコメント記法。|
|`namingpolicy.md`|命名指針|一般的な共通命名ルール。|
|`namingfolder.md`|フォルダ・ファイル命名規則|命名形式、接尾辞、通番などの明確な規定。|
|`namingmember.md`|メンバ命名規則|Sass/JS等のメンバ名に関する命名ルール。|
|`namingselector.md`|CSSのセレクタ命名規則|FLOCSS・BEMベースのセレクタ構文ルール。|
|`structure.md`|構造設計|機能・構造の設計方針を記述したドキュメント。|
||||
|`bemclassification.md`|BEM区分・説明書||
|`config.md`|制御変数・説明書||
|`global.md`|共通処理・仕様一覧|共通処理の仕様。現状はREADMEで補足。|
||||
|`preparation.md`|環境・準備手順|初期構築やインストール手順の記録。|
|`environment.md`|開発環境・メモ|ローカル環境の要点・注意点のメモ。|
|`nodejs.md`|Nodejs・メモ|Node.jsに関する設定や補足情報。|
|`setting.md`|gulp・設定メモ|Gulpの設定ファイルと使用メモ。|

## 補足：構成整合性と三文書の役割整理

以下の3文書は、プロジェクト文書群全体を整理・管理するための基幹文書であり、それぞれに異なる視点で文書を分類・説明しています。

|ファイル名|役割|構成上の位置付け|
|------------|------|-------------------|
|`development_process.md`| 文書を「工程別」に分類・整理する。思考の流れや利用タイミングを明示する。 | 流れに沿ったドキュメント導入の指針 |
|`document_structure.md`| 文書を「体系的」に分類。フォルダ構成との対応・包括的な一覧。 | 全体像把握と構造理解の基盤 |
|`document_relationships.md`| 文書同士の「依存」「参照」関係を可視化。文書保守時の影響範囲なども明示。 | 保守効率化とドキュメント更新時の指針 |

### 相互関係まとめ

| ファイル名 | 関係 |
|------------|------|
|`development_process.md`|工程別の「導線」|
|`document_structure.md`|文書の「全景」|
|`document_relationships.md`|文書間の「つながり」|

## 作成者

Copyright(C) 2025-2025 KOUTAN
