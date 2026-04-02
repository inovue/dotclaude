# Block Diagram

システム構成、ネットワーク、プロセスフローの可視化に最適。著者がレイアウトを制御できる。

## 基本構文

```mermaid
block
    columns 3
    A["コンポーネントA"] B["コンポーネントB"] C["コンポーネントC"]
    D["コンポーネントD"] E["コンポーネントE"]
```

## カラム定義

```mermaid
block
    columns 4
    A B C D
    E F
```

## ブロック幅（スパン）

```mermaid
block
    columns 4
    A:2 B C
    D:3 E
```

`A:2`でAが2カラム分の幅。

## ネスト（複合ブロック）

ネストには `columns` を使って親ブロック内にサブブロックを配置する:

```mermaid
block
    columns 2
    A["Parent"]
    B["Child 1"] C["Child 2"]
    A --> B
    A --> C
```

## ブロック形状

Flowchartと同じ形状構文: `()`, `(())`, `[]`, `[[]]`, `[()]`, `{}`, `{{}}`, `[//]`, `[\\]`, `>]`, `((()))` 等

スペースブロック: `space` または `space:3`

## 接続（エッジ）

```mermaid
block
    A --> B
    B --- C
    C -->|ラベル| D
```

## スタイリング

```mermaid
block
    A B
    style A fill:#f96,stroke:#333,color:#fff
    classDef blue fill:#4a90e2,color:#fff
    class B blue
```
