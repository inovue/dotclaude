# Sankey Diagram

フロー量・資源の流れ・変換過程の可視化に最適。エネルギーフロー、予算配分、コンバージョンの説明に活用。

## 基本構文

> **重要: データ行はインデントしないこと。** 行頭からカンマ区切りで記述する。

```mermaid
sankey
Source A,Target B,5
Source A,Target C,3
Target B,Final D,4
```

## CSV形式

3列: ソース, ターゲット, 値

```mermaid
sankey
Budget,Development,50
Budget,Marketing,30
Budget,Operations,20
Development,Frontend,25
Development,Backend,25
```

## ルール

- カンマ含む値はダブルクォートで囲む
- 空行可（整理用）
- 3列固定

## 設定

```
---
config:
  sankey:
    linkColor: gradient
    nodeAlignment: justify
---
```

- `linkColor`: `source`, `target`, `gradient`, `#hexcode`
- `nodeAlignment`: `justify`, `center`, `left`, `right`
