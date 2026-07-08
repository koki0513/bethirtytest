# GitHub Actionsの注意

ZMKの再利用ワークフローは、標準ではリポジトリ直下の `build.yaml` を読みます。
そのため、このプロジェクトでは `build.yaml` を `config/` の中ではなく、直下に置いています。

もし `Error: 1:1: lexer: invalid input text "build.yaml"` が出る場合は、`build.yaml` がリポジトリ直下にあるか確認してください。
