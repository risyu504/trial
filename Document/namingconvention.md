# 命名規則

このファイルは、開発者がソースコード等を記述する際に要請される、名称に関する決まりごとを記したものです。

このフォルダに関しての説明は、[`README.md`](./README.md) に記述しています。

- [命名規則](#命名規則)
  - [基本概念](#基本概念)
  - [全体共通の命名規則](#全体共通の命名規則)
  - [フォルダの命名規則](#フォルダの命名規則)
  - [ファイルの命名規則](#ファイルの命名規則)
  - [メンバの命名規則](#メンバの命名規則)
  - [セレクタ(CSS)の命名規則](#セレクタcssの命名規則)
  - [命名規則で複数の単語の繋ぎ方](#命名規則で複数の単語の繋ぎ方)
    - [ローワーキャメルケース(LCC：Lower Camel Case)/キャメルケース(Camel Case)](#ローワーキャメルケースlcclower-camel-caseキャメルケースcamel-case)
    - [アッパーキャメルケース(UCC：Upper Camel Case)/パスカルケース(Pascal Case)](#アッパーキャメルケースuccupper-camel-caseパスカルケースpascal-case)
    - [スネークケース(snake case)](#スネークケースsnake-case)
    - [アッパースネークケース(upper snake case)/コンスタントケース(constant case)](#アッパースネークケースupper-snake-caseコンスタントケースconstant-case)
    - [ケバブケース(kebab case)/チェーンケース(chain case)](#ケバブケースkebab-caseチェーンケースchain-case)
  - [命名規則でよく使われる英単語](#命名規則でよく使われる英単語)
    - [真偽値](#真偽値)
    - [文字列操作](#文字列操作)
    - [データ追加](#データ追加)
    - [データ変更](#データ変更)
    - [データ削除](#データ削除)
    - [データ書き込み](#データ書き込み)
    - [データ読み込み](#データ読み込み)
    - [データ検証](#データ検証)
    - [許可・禁止を表す](#許可禁止を表す)
  - [補足](#補足)
  - [作成者](#作成者)

## 基本概念

1. 開発者が一人なので集団での意識統一の面の実績はないのですが、**過去の自分と今の自分の意識統一**という考え方で規約を用意しています。一年後の自分が改めて見ても、読める(分かる)ソースコードを書く為の指針という事です。
2. それだけで分かる必要はなく、コメント等の説明を記述する事で分かれば良いです。規則による分かり易さと説明書きとのバランスです。
3. その上で、ツールを使っての文字列検索, 文字列更新のし易さを目的としています。つまり文字列としての区別の可否を意識するという事です。無駄に長い名称は避けるべきですが、略称, 記号化により文字列としての部分一致の危険性があるのは問題です。
4. ファイルに関しては、ツールのフィルタリングも意識した命名規則としています。
5. 明文化して清書する事によって、自分の理解度の**確認**も兼ねています。
6. **何故**そう決めるのかの部分も記述する事によって、自分の理解度を上げるようにしています。
7. 学ぶという点が含まれている事から、本来あるべき規約の書き方とは異なります。もし組織で規約を用意する場合は、当然ながら規則自体とその経緯は別々にするべきでしょう。

## 全体共通の命名規則

1. 変数やファイルなどの命名の仕方を、命名規則で定めます。
2. 意味の分かり易さを重視して、過度な記号化を避ける。記号化は覚える事が増えるし、文字列としての一意性の配慮が煩雑になる。
3. 探しやすさを意識する。主にエディタでの文字列検索を意識して、部分一致で他に紛れない様に配慮する。例えば a要素 は `a` 一文字ですが、`anchor` と記す事で部分一致での差別化がしやすくなります。尚その場合、システム内で統一する必要があるので注意。
4. 文字数の制限は、敢えて行わない。文字列検索を意識しつつも、長すぎれば記述ミスもし易いので適度に短くする事が望ましい。ただし環境によっては、環境による文字数の制限があるので注意が必要です。
5. 記号化する場合は、必ず説明を用意する。説明を書く手間だけでなく、記号の意味, 内容の変更に伴う説明の更新の手間も考慮して採用を検討する事。説明の放置が一番の害悪である。
6. この規則は、[コーディングルール(内部共通規約)](./codingrules.md) の一部です。矛盾や相反しない様に気を付ける事とする。一応はコーディングルールを上位として万一の場合は解釈する。その後、出来る限り早く矛盾や相反を解消する。

## フォルダの命名規則

1. **１桁目**:
    1. 英字大文字とする。(個人の習慣です)
2. **２桁目以降**:
    1. 英字小文字とする。
    2. 数字は出来るだけ避ける。
    3. `'-'`(ハイフン) `'_'`(アンダーバー) `'.'`(ピリオド) などの使用は禁止とする。(組み合わせて表記が必要な構成は避ける。どちらかと言うと、サブフォルダの使用)
3. **末尾２桁**:
    1. `'SV'`: 変更の為に、元の内容を保持する。最終的には外部に移動か破棄する。
    2. `'WK'`: 検証で当該フォルダを一時的に無効にする為に付与する。最終的には取って元に戻す。
    3. `'XX'`: 廃棄予定のフォルダに付与する。本当に廃棄して問題ないか確認するまでの仮の処置です。最終的には元に戻すか破棄する。
4. キャメルケースではありません。複数の単語を繋げた名称でも、全体の１文字目だけ大文字で他は小文字で繋げます。
5. スネークケース(単語の間をアンダーバーでつなぐ), ケバブケース(単語の間をハイフンでつなぐ) は、禁止です。
6. そのフォルダの意味を表す英字の名称を用いる。
7. 出来れば纏まりの中で一意となる事が望ましい。フォルダの配置の変更や名前空間を考慮しての事なので、それほど重要視する必要はない。
8. そのフォルダの所属(どのフォルダの下位か)を表すような名称にはしない。所属は配置で表せばよく、名前空間などで所属等を表したい時はそこでその様に名付ければよい。(それぞれの命名規則に従う必要はあります。)

## ファイルの命名規則

1. `index`, `README` など、一般的にファイル名として意味のある物はそのまま付ける。
2. 開発用でない(外部向けである)ファイルは、意味の分かり易さを最重視する。
3. 以下のファイルは、以下の名称とします。
    - `_common` 内部処理用の機能を集めたファイル
    - `_batch` 一括処理用の機能を集めたファイル
4. 開発用である上記以外のファイルは、`_risyugvxxxxxnnn` の形式とします。
    - **`_`**: 部品の様な物は、先頭に`'_'`(アンダーバー)を付ける。Sassのコンパイル対象外「パーシャル」の機能を意識しての規則です。
    - **`risyu`**: 外部のファイルとの識別用です。
    - `gv`: フォルダ区分を小文字で記しています。フォルダ区分はフォルダごと割り振られ、それによりどのフォルダか分かる様にしています。(プロジェクトで一意) 例示の`gv`は、共通変数のフォルダを表します。主にコンパイルエラーでのメッセージを読むのに役立ちます。
    - `xxxxx`: そのファイルの意味を表す英字の名称を用いる。この部分は英字の小文字で、`'-'`(ハイフン) `'_'`(アンダーバー) などの使用は禁止です。文字数は任意ですが、短すぎず長すぎずを心がけたいです。
    - `nnn`: この部分はバージョン管理用の数字です。実際にはバージョン管理は面倒なので、`000`の固定になると思います。
    - ファイルのフィルタリング等も意識して、命名しましょう。

## メンバの命名規則

1. メンバは、変数, 関数, mixinなどを想定しています。
2. スコープが mixin, function などのメンバ内の物を除き、名称はプロジェクトで一意になるようにする。(名称だけで、どこで定義されているか分かる事が目的です)
3. 例外として、引数は逆にプロジェクトで意味ごとに同一とする。尚、当該言語が用意している機能を意図した引数は、その機能と同じ引数名とする。Sassのビルトイン関数を意識しての規則です。
4. 例外として、キー項目とデータ項目からなるデータの項目名などは対象外とする。これは一般的な名称などのデータを、そのまま項目名とする事で索引の意味がある場合がある為です。
5. 上記を踏まえたうえで、名称は以下の形式とする。
    1. **１桁目**: メンバの種類とスコープを表します。言語によってスコープの判断は異なります。故に規約で意図を明示する事としています。
        |1  |メンバの種類とスコープ|
        |:-:|----|
        |_l|関数スコープを意図して、mixin, function などのメンバ内でのみ使用する変数。|
        |_g|ファイルをブロックとしたブロックスコープを意図して、ファイル内でのみ使用する変数。letでの定義相当。|
        |_c|ファイルをブロックとしたブロックスコープを意図して、ファイル内でのみ使用する定数(const) constの機能がない言語でも、意味的に定数である変数ならば採用してもよい。尚、メンバ内での関数スコープの定数も'_c'で表す。|
        |_s|ファイルをブロックとしたブロックスコープを意図して、ファイル内でのみ使用するプログラムの開始から終了まで値が保持され続ける静的変数(static)|
        |g|グローバルスコープを意図して、他のファイルでも使用する変数|
        |c|グローバルスコープを意図して、他のファイルでも使用する定数(const)。実際にはconstはブロックスコープを持つので varでの定義となります。|
        |s|他のファイルでも使用するプログラムの開始から終了まで値が保持され続ける静的変数(static)。区分として用意しているだけで、意味的に該当するものはないと思う。|
        |a|引数(mixin, function内ですが`'_'`(アンダーバー)は付けません)|
        |_f|ファイル内でのみ使用する関数|
        |f|他のファイルでも使用する関数|
        |_m|ファイル内でのみ使用するmixin|
        |m|他のファイルでも使用するmixin|
    2. **２桁目**: データの型(用途, 戻り値, 出力するスタイル)を表します。
        |2  |データの型(用途, 戻り値, 出力するスタイル)|
        |:-:|----|
        |v|型が任意である事を表します。戻り値, 出力がない場合も表します。|
        |n|型が 'number' (数) である事を表します。(「単位あり」も含みます)|
        |u|型が 'number' で単位なし (unitless)である事を表します。|
        |i|型が 'number' で整数 (integer) のみを保持する事を表します。(「単位あり」は含みません)|
        |s|型が 'string' (文字列) である事を表します。(「引用符なし」も含みます)|
        |c|型が 'color' (色) である事を表します。|
        |l|型が 'list' (リスト) である事を表します。|
        |m|型が 'map' (マップ) である事を表します。|
        |o|型が 'object' (オブジェクト) である事を表します。('map'という型が当該言語にない場合の表記です。)|
        |b|型が 'bool' (真偽値) である事を表します。|
        |f|型が 'function' (関数) である事を表します。Sassのmeta.get-function などで取得した関数を値として保持する事を表します。それ自体が関数であるかは、１桁目で表します。|
        |a|型が 'arglist' (引数リスト) である事を表します。|
        |s|mixinの出力の形: 文(ステートメント)|
        |d|mixinの出力の形: 宣言(プロパティと値の組)|
        |r|mixinの出力の形: ルールセット(セレクタと宣言ブロックの組)|
        |p|mixinの出力の形: ルールセット(プレースフォルダセレクタと宣言ブロックの組)|
        |a|mixinの処理: CSS At-Rules(@font-face等)|
        |e|mixinの処理: @extend(セレクタ拡張)|
        |v|mixinの処理: @contentなし(コンテンツブロックなし)|
        |c|mixinの処理: コメント付き一括処理|
        |r|Pugのmixinの処理: 一般|
        |s|Pugのmixinの処理: セット|
        |b|Pugのmixinの処理: ブロック|
        |i|Pugのmixinの処理: インライン|
        |v|Pugのmixinの処理: Pugブロックの出力なし(グローバルス変数を更新するだけ)|
        |c|Pugのmixinの処理: コメント付き一括処理|

        ※ `'c'`は、メンバの種類によって意味が異なります。
    3. **３,４桁目**: フォルダ区分を表します。
        - 所属するフォルダのフォルダ区分を付けます。これにより、所属が分かり易くなります。
        - フォルダ区分はその開発環境で一意となるようにする。
        - 引数, 属性引数は例外として、`'Ag'`, `'ag'`とします。
    4. **５,６桁目**: ファイル区分を表します。(フォルダ内でのみ一意であり、他のフォルダとの一意はフォルダ区分があるので考慮しない)
        - `'Cm'`: 一般(common)
        - `'Xx'`: 廃棄予定, 仮の記述
        - Xx: 英字大文字１文字から始まり、２文字目は英字小文字だけとします。必要に応じて各フォルダ内の内部規約に定めて使用します。
        - 引数, 属性引数は例外として、ファイル区分を使用しません。
        - 上記以外: 名称を表します。５-８桁目を省略として９桁目以降の規約に準じます。
    5. **７,８桁目**: ファイル内区分を表します。
        - nn: 数字だけとします。
        - ファイル区分を省略した場合は、指定は不可とします。
        - ファイル区分を指定した場合は、指定は任意とします。
        - ７桁目が英字大文字の場合、７桁目から名称と解釈します。
        - ７桁目が英字小文字の場合、５桁目から名称と解釈します。
    6. **下２桁**: 用途を表します。
        - `'00'`: 内部処理用(非公開)
        - `'01'`: 基本処理
        - `'02'-'09'`: 基本処理の臨時版数管理
        - `'11'`: 一括処理
        - `'12'-'19'`: 一括処理の臨時版数管理
        - `'xx'`: 廃棄予定(既存のものに付与して、仮の削除とする。)
        - 省略可能です。(名称の末尾に制限が付きます)
    7. **９桁目以降(下２桁除く)**: 名称を表します。
        - Xxxxx: 英字大文字１文字から始まり、２文字目は英字小文字, それ以降は０文字以上の英数字小文字だけとします。(キャメルケース)(一部区切りの頭を英字大文字にします)
        - 検索を容易にする為に、短すぎる名称は避ける。
        - 記述を容易にする為に、長すぎる名称は避ける。
        - 下２桁を省略した場合に末尾を数字とする場合は、１桁だけを可能とします。(末尾２桁以上の数字は、その下２桁を用途と判断します)
        - ８桁目以前で省略があった場合に、桁位置がずれるので注意

## セレクタ(CSS)の命名規則

1. BEM(MindBEMding), FLOCSS のクラス名の付け方も、考慮します。
2. 要素セレクタだけでも可能か否かも、考慮します。
3. オリジナル命名規約も、考慮します。

## 命名規則で複数の単語の繋ぎ方

|用例|名称|補足|
|----|----|----|
|toWord|ローワーキャメルケース||
|ToWord|アッパーキャメルケース||
|to_word|スネークケース|接頭子に注意|
|TO_WORD|アッパースネークケース|接頭子に注意|
|to-word|ケバブケース|演算子に注意|
|To-Word|トレインケース|演算子に注意|

### ローワーキャメルケース(LCC：Lower Camel Case)/キャメルケース(Camel Case)

- lowerCcamelCase: 先頭の単語だけ小文字に、後の単語の先頭を大文字にする。
- インスタンス化した全ての変数、関数等に使われる。

### アッパーキャメルケース(UCC：Upper Camel Case)/パスカルケース(Pascal Case)

- UpperCamelCase: 全ての単語の先頭を大文字にする。
- クラスに使われる。

### スネークケース(snake case)

- snake_case: 単語の間をアンダーバーでつなぐ。単語を小文字で揃える。
- `'_'`(アンダーバー)は、ローカルを表す時の接頭子としても用いる事があり、文字列検索で紛らわしい可能性があります。 (`_local` と `word_local` が、文字列検索で紛らわしい。)

### アッパースネークケース(upper snake case)/コンスタントケース(constant case)

- UPPER_SNAKE_CASE: 単語を大文字で揃えて、単語の間をアンダーバーでつなぐ。
- 定数, 環境変数, グローバル変数, その他強い意味を持たせたい時に使われる。
- `'_'`(アンダーバー)は、ローカルを表す時の接頭子としても用いる事があり、文字列検索で紛らわしい可能性があります。 (`_LOCAL` と `WORD_LOCAL` が、文字列検索で紛らわしい。)

### ケバブケース(kebab case)/チェーンケース(chain case)

- kebab-case: 単語の間をハイフンでつなぐ。
- `'-'`(ハイフン) は、演算子との兼ね合いで使えない場合がある。

## 命名規則でよく使われる英単語

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
