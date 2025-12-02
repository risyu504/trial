# 開発環境

開発フォルダに於ける環境のメモ書きです。

このフォルダに関しての説明は、[`README.md`](./README.md) に記述しています。

## OS

windows10: 単に使い慣れているからです。

## テキストエディタ

VSCode: ソースコードの記述としては、単に使い慣れているから。後に SCSS や Pug をコンパイルするのに Node.js を採用して実行するのに、この環境で行ったからです。

## プリプロセッサの採用

### CSS

Sass: CSSのセレクタの管理の為に採用。尚、ここでは**SCSS構文**を採用します。

### HTML

Pug: CSSのセレクタの管理に合わせて、class属性の値の管理の為に採用。

## 環境一覧

- os:windows10
- `nvm-windows v1.1.9`
- `Node.js v18.12.1`
- Node.jsのパッケージ
  - globalモード
    - `corepack v0.14.2`
    - `gulp-cli@2.3.0`
    - `jsdoc@4.0.0`
    - `npm v8.19.2`
    - `pug-cli@1.0.0-alpha6`
    - `sassdoc@2.7.4`
    - `typescript@4.9.3`
  - localモード
    - `docdash@2.0.0`
    - `fs@0.0.1-security`
    - `gulp-concat@2.6.1`
    - `gulp-data@1.3.1`
    - `gulp-debug@3.2.0`
    - `gulp-filter@6.0.0`
    - `gulp-json-sass@0.0.2`
    - `gulp-merge-json@2.1.2`
    - `gulp-notify@4.0.0`
    - `gulp-plumber@1.2.1`
    - `gulp-pug@5.0.0`
    - `gulp-rename@2.0.0`
    - `gulp-sass@5.1.0`
    - `gulp@4.0.2`
    - `json-sass@1.3.5`
    - `nan@2.17.0 extraneous`
    - `npm-run-all@4.1.5`
    - `pug@3.0.2`
    - `sass@1.69.3`
    - `sassdoc@2.7.4`
    - `ts-loader@9.4.2`
    - `webpack-cli@5.0.1`
    - `webpack@5.89.0`

※ 環境を更新した場合は、ここと下記の「環境の構築方法」に追記して下さい。

## 作成者

Copyright(C) 2023-2025 KOUTAN
