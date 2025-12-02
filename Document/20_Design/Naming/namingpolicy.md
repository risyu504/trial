# 命名指針

このファイルは、開発の設計方針として、「命名指針」をまとめたものです。

このフォルダについての説明は、[`README.md`](./README.md) に記載しています。

## この文書について

- 本書は、基本原則に基づいて各命名規則を決める為の方針を記したものである。
- 方針であり、原則でも規則でもない。規則ではないので、文言を厳守する必要はないが、文章を理解して意図を尊重する必要はあります。原則ではないので、具体的な点まで記す必要があります。

## かんたんな説明

ここでは、コードで使う名前（変数や関数など）をどう付けるかについての決まりごとをまとめています。

たとえば、

- 「ローカル変数には `_` を名前の前に付ける。」
- 「フラグには、2文字目に `b` を使う。」

といったルールがあります。

この文書は、あとで自分が読み返してもわかるように、なるべくくわしく書いています。だからすこしむずかしいところもあるけど、ひとつずつ読めばだいじょうぶです。

## 命名規則とは

命名規則とは、変数名、関数名、クラス名などに対して、一貫したルールにしたがって名前を付けることです。

命名規則は、運用上の規則に分類され、この一般的な「規則」の枠組みを コードベースの開発作業の命名に特化して適用したものです。
それは、次のような開発現場のニーズに応えるために存在します：

- 誰が命名しても構造や意味が読み取れる（判断の一貫性）
- ビルドやCI/CD、静的解析などの自動処理と整合性がある
- 命名に個人差が出ず、他者や未来の自分が理解しやすい
- 柔軟な運用が必要な場面でも、明示された例外のもとでのみ運用できる

たとえば、すべての変数をキャメルケースで書く、クラス名の先頭は大文字にする、などの決まりがそれにあたります。

このような命名のルールは、構造設計やコーディングルールと並んで、コード全体のわかりやすさや保守性を高めるために使われます。

ここでは、そうした「わかりきっている」と思えるようなことも、あえて学習の視点から確認のために記述しています。また、この文書の命名規則は、[基本原則](../../10_Principles/basicprinciples.md)に基づいて設計されています。

## 基本方針

1. 以下、「この規則」とは、各命名規則を意味します。本書「命名指針」の事ではありません。
2. この規則は、[「基本原則」](../../10_Principles/basicprinciples.md)に基づいて設計されます。  
  各ルールには、その背景となる意図も記載し、基本原則に即して判断・変更できるようにします。
3. この規則は、[コーディングルール(内部共通規約)](../../20_Design/codingrules.md) の一部です。  
  競合した場合の解釈は、コーディングルールを上位とする。
4. 既存の思想等を参考にする場合は、それに準じた名称にする。
5. 予約語と衝突しないようにする。
6. スコープが分かるようにする。
7. 種類が分かるようにする。
8. 役割が分かるようにする。
9. 無理にその名称だけで完全にわかる必要はない。ただ、意図はわかるようにする。
10. 命名はテキスト（文字列）であることを意識し、ツールによる検索や一括置換などの操作がしやすいように工夫する。
     1. 例えば a要素 は `a` 一文字ですが、`anchor` と記す事で部分一致での差別化がしやすくなります。尚その場合、システム内で統一する必要があるので注意。
11. 適度な長さに収めるように意識はする。ただしわかりやすさ優先です。
12. 記号を使う場合は、必ず説明を用意する。  
  その際は、説明を書く手間だけでなく、記号の意味や内容変更に伴う説明の更新の手間も考慮すること。  
  なお、説明が放置されるのが最も有害である点に注意する。  
  ここでの記号とは、英字で○○区分(BEM区分で'PEC'はプレースフォルダーセレクタでコンポーネントのエレメント)とする様な事をいっているので、決して文字種('_', '-' など)の事ではありません。
13. ファイルに関しては、ツールのフィルタリングも意識します。

## 一般的な命名規則

### スコープが分かるようにする

|接頭子|意味|
|:-:|----|
|_|ローカルスコープを表す。|
|なし|グローバルスコープを表す。|

### 複数の単語の繋ぎ方

|用例|名称|補足|
|----|----|----|
|toWord|ローワーキャメルケース||
|ToWord|アッパーキャメルケース||
|to_word|スネークケース|接頭子に注意|
|TO_WORD|アッパースネークケース|接頭子に注意|
|to-word|ケバブケース|演算子に注意|
|To-Word|トレインケース|演算子に注意|

#### ローワーキャメルケース(LCC：Lower Camel Case)/キャメルケース(Camel Case)

- lowerCcamelCase: 先頭の単語だけ小文字に、後の単語の先頭を大文字にする。
- インスタンス化した全ての変数、関数等に使われる。

#### アッパーキャメルケース(UCC：Upper Camel Case)/パスカルケース(Pascal Case)

- UpperCamelCase: 全ての単語の先頭を大文字にする。
- クラスに使われる。

#### スネークケース(snake case)

- snake_case: 単語の間をアンダーバーでつなぐ。単語を小文字で揃える。
- `'_'`(アンダーバー)は、ローカルを表す時の接頭子としても用いる事があり、文字列検索で紛らわしい可能性があります。 (`_local` と `word_local` が、文字列検索で紛らわしい。)

#### アッパースネークケース(upper snake case)/コンスタントケース(constant case)

- UPPER_SNAKE_CASE: 単語を大文字で揃えて、単語の間をアンダーバーでつなぐ。
- 定数, 環境変数, グローバル変数, その他強い意味を持たせたい時に使われる。
- `'_'`(アンダーバー)は、ローカルを表す時の接頭子としても用いる事があり、文字列検索で紛らわしい可能性があります。 (`_LOCAL` と `WORD_LOCAL` が、文字列検索で紛らわしい。)

#### ケバブケース(kebab case)/チェーンケース(chain case)

- kebab-case: 単語の間をハイフンでつなぐ。
- `'-'`(ハイフン) は、演算子との兼ね合いで使えない場合がある。

### 種類が分かるようにする

|種類|内容|
|:-:|----|
|フォルダ|スネークケース|
|ファイル|スネークケース|
|クラス|アッパーキャメルケース|
|その他の<br>メンバ|ローワーキャメルケース|

## 方針の実現方法

### 予約語と衝突しないようにする

接頭語の採用により、予約語との独自性は保てると思う。

### 詳細な種類が分かるようにする

接頭語で詳細な種類を表す事で、実現できる。

### 役割が分かるようにする

役割別にフォルダを分ける(メンバをまとめる)ので、所属を表す接頭語の採用で、実現できる。

## 命名規則でよく使われる英単語

### フォルダ(構造付き)

```参考用
.  
├── Assets/   - 資源用のフォルダ  
├── Config/   - 設定ファイル用のフォルダ  
├── Bin/      - 実行ファイル用のフォルダ  
├── Data/     - データ用のフォルダ  
├── Dest/     - 成果物の出力用のフォルダ  
├── Dist/     - 成果物の配布用のフォルダ  
├── Document/ - ドキュメント用のフォルダ  
├── Gulpfile/ - gulpのフォルダ  
│    ├── Global/    - 共通メンバのフォルダ  
│    │    ├── Constant/   - 共通定数のフォルダ  
│    │    ├── Inspection/ - 検査フォルダ  
│    │    └── Operationt/ - 操作フォルダ  
│    ├── Component/ - コンポーネントのフォルダ  
│    ├── Project/   - プロジェクトのフォルダ  
│    └── Test/      - 検証用のフォルダ  
├── Module/      - FLOCSS を元にした開発用パッケージのファルダ  
│    ├── Foundation/    - 基礎のフォルダ  
│    │    ├── Font/       - フォントのフォルダ  
│    │    └── Reset/      - リセットのフォルダ  
│    ├── Global/        - 共通メンバのフォルダ  
│    │    ├── Constant/   - 共通定数のフォルダ  
│    │    ├── Inspection/ - 検査フォルダ  
│    │    ├── Operationt/ - 操作フォルダ  
│    │    ├── Variable/   - 共通変数のフォルダ  
│    │    └── Vendors/    - ベンダーのフォルダ  
│    ├── Layout/        - レイアウトのフォルダ  
│    ├── Object/        - オブジェクトのフォルダ  
│    │    ├── Component/  - コンポーネントのフォルダ  
│    │    ├── Project/    - プロジェクトのフォルダ  
│    │    └── Utility/    - ユーティリティのフォルダ  
│    └── Theme/         - テーマのフォルダ  
├── node_modules/ - Node.jsのフォルダ  
└── Src/ - ソースコード用のフォルダ  
      ├── Pug/        - Pugのフォルダ  
      ├── Sass/       - Sassのフォルダ  
      └── Typescript/ - JavaScriptの開発資源用のファルダ  
```

### 真偽値

|場所|単語| 意味 | 例 | 活用例 | 例の内容 |
|:--:| ---- | ---- | ---- | ---- | ---- |
| prefix | is       | 期待する状態になっているか | isEnabled | fbGfIsEnabled | 有効か否か |
| prefix | can      | 期待する処理ができるか | canRemove | fbGfCanRemove | 削除できるか否か |
| prefix | should   | 命令を実行するべきか | shouldMigrate | fbGfShouldMigrate | 移行するべきか否か |
| prefix | need     | 命令を実行する必要があるか | needFileCopy | fbGfNeedFileCopy | ファイルコピーをする必要があるか否か |
| prefix | has      | 期待するデータやプロパティを持っているか | hasConnection | fbGfHasConnection | 関連するデータやプロパティを持っているか否か |
| － | exists   | 期待するデータやプロパティが存在するか | exists(dir) | fbGfExistsVariable | 変数が存在するか否か |
| － | contains | 期待するデータやプロパティが含まれているか | contains(item) | fbGfContainsItem | 項目が含まれているか否か |

### 文字列操作

|場所|単語| 意味 | 例 | 活用例 | 例の内容 |
|:--:| ---- | ---- | ---- | ---- | ---- |
| prefix | find    | 情報を検索する (発見可能前提) | findString | fsGfFindString | 文字列検索 |
| prefix | search  | 情報を探索する (発見不可前提) | searchString | fsGfSearchString | 文字列探索 |
| － | seek    | 連続した情報を順番に探査する | file.seek() | fsGfSeek | 文字列連続探査 |
| － | extract | 情報をある条件で抽出する | hash.extract() | fsGfExtract | 文字列抽出 |
| － | filter  | 情報をある条件で除外する | filter() | fsGfFilter | 文字列除外 |
| － | replace | 既存のデータを置き換える | String.replace() | fsGfReplace | 文字列置換 |
| － | join    | 既存のデータを結合する | String.join() | fsGfJoin | 文字列結合 |
| － | parse   | 既存のデータを解析する | String.Parse() | fsGfParse | 文字列解析 |

### データ追加

|場所|単語| 意味 | 例 | 活用例 | 例の内容 |
|:--:| ---- | ---- | ---- | ---- | ---- |
| prefix | set      | データを設定する(setter) | setProperty | setProperty | セッター |
| prefix | add      | データやオブジェクトを追加する | addList | flGfAddList | リストを追加 |
| prefix | put      | データやオブジェクトを追加する | hash.put(key,value) | fvGfPut | 追加 |
| prefix | insert   | データやオブジェクトを挿入する | insertQueue | flGfInsertQueue | 列を挿入 |
| prefix | append   | データやオブジェクトを末尾に追加する | appendQueue | flGfAppendQueue | 列を末尾に追加 |
| prefix | push     | データやオブジェクトを先頭に追加する | pushQueue | flGfPushQueue | 列を先頭に追加 |
| prefix | prepend  | データやオブジェクトを先頭に追加する | prependQueue | flGfPrependQueue | 列を先頭に追加 |
| prefix | register | データやオブジェクトを登録する | registerStorage | foGfRegisterStorage | 登録ストレージ |
| prefix | create   | 新しいデータやファイルを作る | createAccount | fmGfCreateAccount | アカウント作成 |
| prefix | new      | 新しいデータやファイルを作る | newAccount | fmGfNewAccount | アカウント作成 |
| prefix | make     | 既存データを加工してデータやファイルを作る | makeFile | fvGfMakeFile | 加工してファイルを作る |
| prefix | build    | 既存データからデータやファイルを組み立てる | buildFile | fvGfBuildFile | ファイルを組み立てる |
| prefix | from     | 既存データを流用してデータやファイルを作る | fromConfigFile | fvGfFromConfigFile | 流用してファイルを作る |
| prefix | generate | 何かのルールに従ってデータやファイルを作る | generateFile | fvGfGenerateFile | ルールに従ってファイルを作る |

### データ変更

|場所|単語| 意味 | 例 | 活用例 | 例の内容 |
|:--:| ---- | ---- | ---- | ---- | ---- |
| prefix | update   | 既存のデータを最新化する | updateAccount | fmGfUpdateAccount | アカウント更新 |
| prefix | upgrade  | 既存のデータをより優れたものに交換する | upgradeAccount | fmGfUpgradeAccount | アカウントアップグレード |
| prefix | apply    | 既存のデータを適用する | applyAccount | fmGfApplyAccount | アカウント適用 |
| prefix | refresh  | 既存のデータを更新する | refreshAccount | fmGfRefreshAccount |アカウント更新(刷新) |
| prefix | changed  | 既存のデータを変更する | changedAccount | fmGfChangedAccount | アカウント変更 |
| prefix | modified | 既存のデータを修正する | modifiedAccount | fmGfModifiedAccount | アカウント修正 |
| prefix | revised  | 既存のデータを改版する | revisedAccount | fmGfRevisedAccount | アカウント改版 |
| prefix | enable   | 既存のデータを使用可能にする | enableAccount | fmGfEnableAccount | アカウント使用可 |
| prefix | disable  | 既存のデータを使用不可にする | disableAccount | fmGfDisableAccount | アカウント使用不可 |
| prefix | fix      | 既存のデータの問題を解決する | fixAccount | fmGfFixAccount | アカウントの問題を解決 |
| prefix | repair   | 既存のデータを修理する | repairAccount | fmGfRepairAccount | アカウント修理 |
| prefix | restore  | 既存のデータを復元する | restoreAccount | fmGfRestoreAccount | アカウント復元 |
| prefix | recover  | 既存のデータを復旧する | recoverAccount | fmGfRecoverAccount | アカウント復旧 |
| prefix | edit     | 既存のデータを編集する | editAccount | fmGfEditAccount | アカウント編集 |
| prefix | adjust   | 既存のデータを調整する | adjustString | fsGfAdjustString | 文字列調整 |
| prefix | adapt    | 既存のデータを適合させる | adaptString | fsGfAdaptString | 文字列適合 |
| prefix | convert  | 既存のデータを変換する | convertString | fsGfConvertString | 文字列変換 |
| prefix | to       | 既存のデータを変換する | toString | fsGfToString | 文字列変換 |

### データ削除

|場所|単語| 意味 | 例 | 活用例 | 例の内容 |
|:--:| ---- | ---- | ---- | ---- | ---- |
| prefix | delete     | 既存のデータを削除する (復元不可) | deleteAccount | fmGfDeleteAccount | アカウント削除 (復元不可) |
| prefix | remove     | 既存のデータを除去する (復元可能) | removeAccount | fmGfRemoveAccount | アカウント除去 (復元可能) |
| prefix | trash      | 既存のデータを廃棄する (復元可能) | trashAccount | fmGfTrashAccount | アカウント廃棄 (復元可能) |
| prefix | erase      | 既存のデータを消去する (書き直し可能) | eraseAccount | fmGfEraseAccount | アカウント消去 (書き直し可能) |
| prefix | clear      | 既存のデータを初期化する | clearAccount | fmGfClearAccount | アカウント初期化 |
| prefix | flush      | 既存のデータを初期化する | flushAccount | fmGfFlushAccount | アカウント初期化 |
| prefix | reset      | 既存のデータを初期化する | resetAccount | fmGfResetAccount | アカウント初期化 |
| prefix | dispose    | 既存のデータを開放する (再利用可能) | disposeAccount | fmGfDisposeAccount | アカウント開放 (再利用可能) |
| prefix | destroy    | 既存のデータを破棄する (再利用不可) | destroyAccount | fmGfDestroyAccount | アカウント破棄 (再利用不可) |
| prefix | unregister | 登録済みのデータを解除する | unregisterStorage | fvGfUnregisterStorage | ストレージ登録解除 |
| prefix | unset      | 定義済みのデータを未定義にする | unsetAccount | fmGfUnsetAccount | アカウントの設定解除 |
| prefix | pop        | 先頭のデータを取り出して取り除く | popQueue | flGfPopQueue | 先頭の列の除去 |
| －     | initialize | 既存のデータを初期化する | initialize() | fvGfInitialize | データ初期化 |

### データ書き込み

|場所|単語| 意味 | 例 | 活用例 | 例の内容 |
|:--:| ---- | ---- | ---- | ---- | ---- |
| prefix | save   | 既存のデータを保存する | saveAccount | fvGfSaveAccount | アカウント保存 |
| prefix | output | 既存のデータを出力する | outputAccount | fvGfOutputAccount | アカウント出力 |
| prefix | export | 既存のデータを書き出す | exportAccount | fvGfExportAccount | アカウント書き出し |
| prefix | write  | 既存のデータを書き込む | writeAccount | fvGfWriteAccount | アカウント書き込み |
| prefix | store  | 既存のデータを貯蔵する | storeAccount | fvGfStoreAccount | アカウント貯蔵 |
| prefix | send   | 既存のデータを送信する | sendAccount | fvGfSendAccount | アカウント送信 |
| prefix | commit | 既存のデータを確定する | commitAccount | fvGfCommitAccount | アカウント確定 |

### データ読み込み

|場所|単語| 意味 | 例 | 活用例 | 例の内容 |
|:--:| ---- | ---- | ---- | ---- | ---- |
| prefix | get(gettet) | 既存のデータを取得する | getAccount | getAccount | ゲッター |
| prefix | load    | 既存のデータを呼び出す | loadAccount | fmGfLoadAccount | アカウント呼び出し |
| prefix | input   | 既存のデータを入力する | inputAccount | fmGfInputAccount | アカウント入力 |
| prefix | import  | 既存のデータを読み出す | importAccount | fmGfImportAccount | アカウント読み出し |
| prefix | read    | 既存のデータを読み込む | readAccount | fmGfReadAccount | アカウント読み込み |
| prefix | restore | 既存のデータを復元する | restoreAccount | fmGfRestoreAccount | アカウント復元 |
| prefix | fetch   | 既存のデータを取得する | fetchAccount | fmGfFetchAccount | アカウント取得 |

### データ検証

|場所|単語| 意味 | 例 | 活用例 | 例の内容 |
|:--:| ---- | ---- | ---- | ---- | ---- |
| prefix | check    | 対象のデータがある条件に適合するか確認する | checkAccount | fbGfCheckAccount | アカウント検証 |
| prefix | test     | 対象のデータがあるルールを満たすか確認する | testAccount | fbGfTestAccount | アカウント適性検査 |
| prefix | validate | 対象のデータが正しいか検証する | validateAccount | fbGfValidateAccount | アカウント正誤検査 |
| prefix | compare  | 対象のデータを比較する | compareAccount | fbGfCompareAccount | アカウント比較検査 |
| prefix | verify   | 対象のデータを照合する | verifyAccount | fbGfVerifyAccount | アカウント照合 |

### 許可・禁止を表す

|場所|単語| 意味 | 例 | 活用例 | 例の内容 |
|:--:| ---- | ---- | ---- | ---- | ---- |
| prefix | allow    | 対象に利用権限を与える | allowAccount | cvGvAllowAccount | 利用権限ありアカウント |
| prefix | disallow | 対象に利用権限を与えない | disallowAccount | cvGvDisallowAccount | 利用権限なしアカウント |
| prefix | accept   | 対象を承認する | acceptAccount | cvGvAcceptAccount | 承認アカウント |
| prefix | deny     | 対象を否認する | denyAccount | cvGvDenyAccount | 否認アカウント |
| prefix | refuse   | 申請や要求を辞退する | refuseAccount | cvGvRefuseAccount | 辞退アカウント |
| prefix | reject   | 申請や要求を拒否する | rejectAccount | cvGvRejectAccount | 拒否アカウント |
| prefix | grant    | 対象にある範囲の権限を与える | grantAccount | cvGvGrantAccount | 範囲の権限ありアカウント |
| prefix | revoke   | 対象から権限を剥奪する | revokeAccount | cvGvRevokeAccount | 権限剥奪アカウント |

## 補足

- [BEM](https://github.com/juno/bem-methodology-ja/blob/master/definitions.md)は、CSS設計の一つです。
- [FLOCSS](https://github.com/hiloki/flocss)は、CSS設計の一つです。
- [MindBEMding](https://csswizardry.com/2013/01/mindbemding-getting-your-head-round-bem-syntax/) は、BEMをCSSのクラス名に適用するために作られた命名規則です。

## 作成者

Copyright(C) 2022-2025 KOUTAN
