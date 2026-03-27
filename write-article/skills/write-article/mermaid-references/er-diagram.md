# Entity Relationship Diagram

データ構造、エンティティ間の関係の可視化に最適。DB設計やデータモデルの説明記事に活用。

## 基本構文

```mermaid
erDiagram
    CUSTOMER ||--o{ ORDER : "places"
    ORDER ||--|{ LINE_ITEM : "contains"
    PRODUCT ||--o{ LINE_ITEM : "included in"
```

## カーディナリティ記号

| 左側 | 右側 | 意味 |
|------|------|------|
| `\|o` | `o\|` | 0または1 |
| `\|\|` | `\|\|` | ちょうど1 |
| `}o` | `o{` | 0以上 |
| `}\|` | `\|{` | 1以上 |

## 関係の線種

- `--`: 実線（識別関係）
- `..`: 点線（非識別関係）

## 属性

```mermaid
erDiagram
    CUSTOMER {
        int id PK
        string name
        string email UK
        date created_date
    }
```

キー指定: `PK`（主キー）、`FK`（外部キー）、`UK`（ユニークキー）

コメント: `string email UK "連絡先"`

## エンティティ別名

```mermaid
erDiagram
    CUSTOMER [顧客エンティティ]
```

## 方向

`TB`, `BT`, `LR`, `RL`

## スタイリング

```mermaid
erDiagram
    style CUSTOMER fill:#f9f,stroke:#333
    classDef highlight fill:#f96
    CUSTOMER:::highlight
```
