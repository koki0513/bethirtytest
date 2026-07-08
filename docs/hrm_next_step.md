# Home Row Mods を次に入れるときのメモ

この初期プロジェクトでは、安全のためHome Row Modsを入れていません。

全キー確認が終わったあと、まずは `S = Ctrl` だけを試すのがおすすめです。

ZMKでは、短押しと長押しを分ける設定を Hold-Tap と呼びます。
ZMK標準の `&mt` も使えますが、Home Row Modsでは設定を分けた専用動作を作る方が調整しやすいです。

例です。

```dts
/ {
    behaviors {
        hm_left: home_row_mod_left {
            compatible = "zmk,behavior-hold-tap";
            #binding-cells = <2>;

            flavor = "balanced";
            tapping-term-ms = <230>;
            quick-tap-ms = <175>;
            require-prior-idle-ms = <100>;

            bindings = <&kp>, <&kp>;
        };
    };
};
```

そのうえで、Sキーを次のように変えます。

```dts
&hm_left LCTRL S
```

意味はこうです。

| 操作 | 出るもの |
|---|---|
| Sを短く押す | `s` |
| Sを長押しする | `左Ctrl` |

慣れてから、D/F/G や右手側にも広げるのが安全です。

## 左右判定を入れる場合

ZMKには `hold-trigger-key-positions` があります。
これは、QMKのChordal Holdに近い考え方で、反対側の手のキーと組み合わせた時だけ長押し側を出しやすくします。

ただし、キー位置番号を実機配列に合わせる必要があります。
番号を間違えると挙動が分かりにくくなるので、最初のファームでは入れていません。
