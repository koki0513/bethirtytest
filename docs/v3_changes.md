# v3の変更点

## board指定をZMK variantに変更

ZMK main / Zephyr 4.1系では、通常の `rpi_pico` ではなく、`rpi_pico//zmk` を指定する必要があります。

```yaml
include:
  - board: "rpi_pico//zmk"
    shield: bethirty_ortho
```

## デフォルトレイヤー右下に復旧用キーを配置

デフォルトレイヤーの右下2キーを、次のように変更しました。

| 位置 | 動作 |
|---|---|
| 右下の左側 | `&bootloader` |
| 右下の右側 | `&sys_reset` |
