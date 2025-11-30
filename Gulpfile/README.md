# Gulpfileフォルダ readme

この `README.md` ファイルは、このフォルダに関しての説明を記述したファイルです。

## 概要

- このフォルダは、gulp の gulpfile.js のフォルダです。(フォルダ構成は「[フォルダ構成・方針](../Document/00_Materials/folder_policy.md)」で記しています。)
- [開発フォルダ](../README.md)の下位フォルダとする事を、想定しています。
- gulpfile.js ファイルを分割する事が目的です。
- 名称: **Gulpfile**, 区分: **Gu** です。

## 用語説明

### [gulp](https://gulpjs.com/)

タスクランナーです。開発作業を自動化する事に用います。

### [Node.js](https://nodejs.org/ja)

Node.jsのモジュール解決機能を使用すると、gulpfile.js ファイルを gulpfile.js というディレクトリに置き換え、その中に index.js ファイルを配置することで、gulpfile.js として扱うことができます。それを意識しつつ、gulp の公式で同等の事を行おうとしているのが現状です。gulpfile.js ファイル から Gulpfile というディレクトリの index.js というファイルを読み込むという方法で実現しています。

### ファクトリー関数(Factory function)

関数を生成して返す関数。本プロジェクトでは主に Gulp タスクを構成するために使用する。

### インナー関数(Inner Function)

ファクトリー関数によって生成され、実際に実行される関数。主に Gulp タスク本体として機能する。ストリームを返す事で、タスクの完了を通知。ストリームを使用していない場合は、callback関数でタスクの完了を通知。

## 内部規約

1. 主に [コーディングルール](../Document/codingrules.md) に準じます。
2. このフォルダのフォルダ区分は、'**Gu**' です。
3. このフォルダのファイルに関する規約は、以下の通りとする。
    1. 説明ファイル, index.jsファイル以外のファイルを置かない。
    2. 上記以外のファイルは、種類別にフォルダを用意して、そこに纏める。

## 構成

- [Component/](./Component/README.md)
- [Global/](./Global/README.md)
- [Project/](./Project/README.md)
- [`index.js`](./index.js)
- `README.md` 説明ファイル(このファイルです)

## 作成者

Copyright(C) 2023-2025 KOUTAN
