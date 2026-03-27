# Venn Diagram

集合の重なり・共通点・差異の可視化に最適。概念の比較や分類の記事に活用。(v11.12.3+ beta)

## 基本構文

```mermaid
venn-beta
    set A["集合A"]
    set B["集合B"]
    union A,B
```

## セット定義

```mermaid
venn-beta
    set A["フロントエンド"]
    set B["バックエンド"]
    set C["インフラ"]
```

## ユニオン（共通部分）

```mermaid
venn-beta
    set A
    set B
    union A,B
```

参照するIDは事前に`set`で定義済みであること。

## サイズ指定

```mermaid
venn-beta
    set A:100
    set B:80
    union A,B:50
```

`:N`でサイズを制御。

## カスタムラベル

```mermaid
venn-beta
    set A["セットAlpha"]
    set B["セットBeta"]
```

## スタイリング

`fill`, `color`, `stroke`, `stroke-width`, `fill-opacity`
