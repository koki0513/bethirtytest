# Vialレイアウト変換メモ

`bethirty.vil` の内容を `bethirty_ortho.keymap` に反映しました。

## 右下2キー

ユーザー指定により、デフォルトレイヤー右下2キーは次を維持しています。

| 位置 | ZMK |
|---|---|
| 右下の左側 | `&bootloader` |
| 右下の右側 | `&sys_reset` |

元のVialでは `KC_HOME` / `KC_END` でしたが、ZMK運用の安全性を優先して上書きしています。

## Home Row Mods

Vialの `LCTL_T(KC_S)` などは、ZMKの専用Hold-Tap動作に変換しています。

左手側は右手側キーと組み合わせたときに長押し判定しやすくし、
右手側は左手側キーと組み合わせたときに長押し判定しやすくしています。

これはQMKのChordal Holdに近い使い方です。

## コンボ

Vialのコンボ2件を、ZMKのcomboへ変換しています。

| Vial | ZMK |
|---|---|
| `S + X` | `&kp LS(N9)` |
| `X + C` | `&kp LS(LEFT_BRACKET)` |

どちらもデフォルトレイヤーだけで有効です。
