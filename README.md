# README

## 概要

power bi プロジェクトのテンプレートです。(サンプル)

## 必要ソフトウェア

* [power bi desktop](https://powerbi.microsoft.com/ja-jp/downloads/)
* [pbi-tools](https://pbi.tools/)

## 開発方法

以下コマンドはpbi-toolsへのパスが通っていることを前提に作っています。
プロジェクトに合わせて `project_template` フォルダはプロジェクト名に変更するか、 コピーしてプロジェクト名のフォルダを作成してください。

1. まずはpower bi desktop で編集するためpbitファイルを作成する。

    ```bash
    pbi-tools compile .\project_template -format PBIT
    ```

1. 次に `power bi desktop` でpbitファイルを開く。
1. データを更新して、pbitファイルと同名（今回は `project_template.pbix`)で保存する。
1. 生成したpbixファイルを `power bi desktop` で開いてタスクマネージャーもしくは `tasklist` コマンドを使用して該当pbixファイルを開いているpower bi desktopのPIDを調べる。（[参考](https://support.kaspersky.co.jp/common/windows/6325#block2))
1. 下記コマンドを実行し、`Entering WATCH mode... (Exit via CTRL+C)` という文言が出力されることを確認する。

    ```bash
    pbi-tools extract -pid <power bi のPID> -watch
    ```

    例)

    ```bash
    pbi-tools extract -pid 10001 -watch
    ```

1. `power bi desktop` にて、編集し、保存する。（保存すると勝手に、プロジェクトに反映される）

## デプロイ方法

T.B.D.
