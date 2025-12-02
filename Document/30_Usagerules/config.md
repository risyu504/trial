# 制御変数 説明書

このファイルは、制御変数に関する仕様を記したものです。

このフォルダに関しての説明は、[`README.md`](./README.md) に記述しています。

## 概要

- このプロジェクトでは、制御変数を用いて処理を振り分けています。
- 制御変数にも既定値を用意して、指定を省略しても既定の処理を実行できる様にします。
- 指定している値の適性検査はしません。(作成時の動作テストは行っています)

## 優先順位

1. 実行時制御変数
   - [設定ファイルフォルダ](../../Config/README.md)にjsonファイルを配置します。
   - ここに用意したjsonファイルを適切に変換して各処理で読み込みます。
2. エントリーポイント制御変数
   - エントリーポイントのファイルに記述します。
3. 制御変数既定値
   - 各処理で保持します。

## 実行時制御変数

- risyucfconfig.json の記述例

  ```JSON:risyucfconfig.json
  {
    "jmJsData" : {
      "@type" : "risyuConfig",
      "date"  : "'2025-11-30'",
      "thememonth" : "'12'",
      "theme" : "Ivory",
      "risyu" : "bem",
      "comment" : false,
      "site"           : "離珠のHTMLでしぃ！",
      "webSiteUrl"     : "'https://storage.googleapis.com/risyu/index.htm'",
      "author"         : "'コータン (KOUTAN)'",
      "authoralphabet" : "'KOUTAN'",
      "googlefonts"      : true,
      "googlebreadcrumb" : true,
      "commentWK" : true,
      "cssWK"      : ["'../Stylesheet/what.css'"],
      "themecssWK" : ["'../Theme/themewhat.css'"],
      "risyuSV1" : "free",
      "risyuSV2" : "bem-risyu"
    }
  }
  ```

- risyucfconfig.json の説明

  ※ Sassファイルに変更(複写)する想定なので、項目名やその値に、制限があります。

  - `joJsConfig` : 制御変数
    - `type` : この変数のデータ型を記します。'risyuConfig'で、制御変数を表します。('@type'としないのは、Sassへ配慮してのことです。)
    - `date`  : 更新日付を引用符付きで 'yyyy-mm-dd' の書式で指定する。この書式で指定される前提で編集処理を行います。
    - `thememonth`  : テーマの対象月を指定します。
    - `theme` : テーマを指定します。
    - `risyu` : クラスセレクタの命名方法を指定します。('bem':BEMのみ, 'risyu':離珠オリジナルのみ, 'free':クラス指定なし, 他:BEMと離珠オリジナルの併記)
    - `comment` : 詳細なコメントの有無を指定します。(true:詳細なコメントを記述する, false:詳細なコメントを記述しない)
    - `site` : サイト名。引用符付き
    - `webSiteUrl` : サイトのURL。引用符付き
    - `author` : 署名。引用符付き
    - `authoralphabet` : 作者名の英字表記。引用符付き
    - `googlefonts` : google の Webフォントの使用の有無を指定します。 (何を使用するかは処理に組み込み済み)
    - `googlebreadcrumb` : google の breadcrumb の対応の有無を指定します。
    - `css` : スタイルシートのリンク先をリスト形式で指定する。(リストにより複数指定に対応)
    - `themecss` : テーマ用のスタイルシートのリンク先をリスト形式で指定する。(リストにより複数指定に対応)

- Pug用の実行時制御変数ファイル
  - 廃止。元のファイルをそのまま読みます。

- Sass用の実行時制御変数ファイル
  - 変数名を `$jmJsConfig` として、json の形式を SASS のmap形式 とした scssファイル(`risyucfconfig.scss`) に変えています。

- 注意事項
  - 設定ファイルフォルダのjsonファイルを元に、各処理の制御ファイルが更新されます。ただし、自動ではありません。一括更新処理タスクには、常に制御ファイルの更新をする様に組み込む事を推奨します。
  - 検証の為などの為に各処理の制御ファイルを直接書き直す事を禁止しません。ただし最終確認で、必ず設定ファイルフォルダのjsonファイルを元に、各処理の制御ファイルを更新して検証を行って下さい。
  - 制御変数は、存在チェック等はしないので、キー項目の記述ミスはそのまま指定がないものとして処理されます。また、不適切な値は、動作は不定です。

## エントリーポイント制御変数

各処理の説明を参照して下さい。

## 制御変数既定値

各処理の説明を参照して下さい。

## 作成者

Copyright(C) 2022-2025 KOUTAN
