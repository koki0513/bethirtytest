# keymap-drawer

このプロジェクトには、keymap-drawerでキーマップ図を作る仕組みを入れています。

## 使い方

GitHub Actionsの `Draw Keymap` を手動実行します。

また、次のファイルを変更してpushしたときも自動で実行します。

- `config/boards/shields/bethirty_ortho/bethirty_ortho.keymap`
- `config/bethirty_ortho.json`
- `.github/workflows/draw.yml`

実行後、`keymap-drawer/` フォルダに `.yaml` と `.svg` が作られ、コミットされます。
ActionsのArtifactsにも出力されます。

## レイアウト

BeThirty Orthoは、上3段が10キー、最下段が9キーです。
最下段は中央に1キー分の空きを置く形で、次の並びとして定義しています。

```text
0 1 2 3 4   6 7 8 9
```

そのため、デフォルトレイヤー右下の2キーに置いている `&bootloader` と `&sys_reset` も、図の右下に出る想定です。

## 注意

この仕組みは、CLine46プロジェクトの `draw.yml` と同じ流れを参考にしています。
keymap-drawerが生成する表示名は、ZMKのキーコード名に依存します。
見た目をさらに整えたい場合は、あとから `keymap_drawer.config.yaml` を追加してラベルを調整できます。
