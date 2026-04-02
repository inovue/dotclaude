# XY Chart

数値データの比較・推移の可視化に最適。棒グラフと折れ線グラフを組み合わせ可能。

> **制約: X軸のカテゴリラベルに日本語は使用不可。** 英語・数字で記述し、記事本文で日本語の説明を添えること。タイトルやY軸タイトルはクォート付きで日本語可。

## 基本構文

```mermaid
xychart
    title "Sales Trend"
    x-axis [Jan, Feb, Mar, Apr]
    y-axis "Sales" 0 --> 100
    bar [20, 35, 50, 45]
    line [15, 40, 45, 50]
```

## 方向

```mermaid
xychart horizontal
    title "横向きチャート"
    x-axis [A, B, C]
    bar [10, 20, 30]
```

## 軸設定

### X軸（カテゴリまたは数値）

カテゴリ: `x-axis "タイトル" [cat1, "cat 2", cat3]`
数値: `x-axis タイトル min --> max`

### Y軸（数値のみ）

`y-axis "タイトル" min --> max`（省略時は自動）

## チャートタイプ

- `bar [値1, 値2, ...]`: 棒グラフ
- `line [値1, 値2, ...]`: 折れ線グラフ

小数・負の値に対応。

## データラベル表示

```
---
config:
  xyChart:
    showDataLabel: true
---
```

## テーマ設定

```
---
config:
  themeVariables:
    xyChart:
      titleColor: "#ff0000"
      plotColorPalette: "#f00,#0f0,#00f"
---
```
