## 一言で言うと

[mtei配列][https://github.com/mtei/SemiErgo_Layout]で入力するためのコラムスタカード5段BMP対応キーボード。

## キー配列

- 6行5段の内側に3つのキー
- 最下段は親指用斜め1.5u/1u1個づつ。ALT/GUI。小指用レイヤーキー。
- ergodashとlily58の中間のキー数
  - mtei配列が可能なように内側キーを3つに増やしたlily58
  - あるいは親指キーをコンパクトにしたergodash

## ソフトウェア

- COL0-6はpin20-14、ROW0-4はpin7-11で、helixと互換
- ブザーはpin12で、helix picoと同じ

## [BLE Micro Pro][https://github.com/sekigon-gonnoc/BLE-Micro-Pro]対応

- 13pinは使用しないため、片側の12pinコンスルーヘッダを一段ずらして使用できる。

- 昇圧回路により単4電池1本で動作
  - 片側ごとに1つづつ

- 昇圧回路は選択式
  - 基板上に部品を実装
  - 秋月基板[M-05720][http://akizukidenshi.com/catalog/g/gM-05720/]を実装

- オンボード昇圧回路
  - [TPS61221][http://www.tij.co.jp/product/jp/TPS61221] を使用
    - SC-70パッケージ。SOパッケージなので手で半田付けできる…はず。
    - 静止時自己消費電流5.5uA。
    - 低電流時の効率が良い。
      - 待機時/打鍵時の100-200uAの時 80%弱
      - 通信時の 6,7mAのとき 80%強
    - 4.7uH程度のインダクタで動作するためコンパクト
    - 0.7V以上で動作するため、NiMH電池などでは過放電になる。注意すること。

