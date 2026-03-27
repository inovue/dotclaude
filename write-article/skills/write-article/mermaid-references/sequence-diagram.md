# Sequence Diagram

時系列の対話・メッセージの流れを可視化。システム間連携やユーザーとサービスのやり取りを説明する記事に最適。

## 基本構文

```mermaid
sequenceDiagram
    participant A as Alice
    participant B as Bob
    A->>B: Hello
    B-->>A: Hi
```

## 参加者の宣言

```mermaid
sequenceDiagram
    participant A as Alice
    actor U as User
```

タイプ指定: `participant A {"type": "database"}` (boundary, control, entity, database, collections, queue)

## グループ化（Box）

```mermaid
sequenceDiagram
    box rgb(135,206,250) Group
        participant A
        participant B
    end
```

色は `rgb(r,g,b)` 形式で指定。色名（Aqua等）はレンダラーによって非対応の場合がある。

## メッセージ矢印

| 構文 | 種類 |
|------|------|
| `->` | 実線（矢印なし） |
| `-->` | 点線（矢印なし） |
| `->>` | 実線＋矢印 |
| `-->>` | 点線＋矢印 |
| `<<->>` | 双方向（実線） |
| `<<-->>` | 双方向（点線） |
| `-x` | 実線＋×（失敗） |
| `--x` | 点線＋× |
| `-)` | 非同期（実線） |
| `--)` | 非同期（点線） |

## アクティベーション

```mermaid
sequenceDiagram
    Alice->>+Bob: Request
    Bob->>-Alice: Response
```

明示的: `activate Bob` / `deactivate Bob`

## ノート

```mermaid
sequenceDiagram
    Note right of Alice: メモ
    Note over Alice,Bob: 共有メモ
```

改行: `<br/>`

## 制御構造

### ループ
```mermaid
sequenceDiagram
    loop 毎日
        Alice->>Bob: 確認
    end
```

### 分岐（Alt/Else）
```mermaid
sequenceDiagram
    alt 条件A
        Alice->>Bob: パスA
    else 条件B
        Alice->>Bob: パスB
    end
```

### オプション（Opt）
```mermaid
sequenceDiagram
    opt 任意の処理
        Alice->>Bob: 実行するかも
    end
```

### 並列（Par）
```mermaid
sequenceDiagram
    par アクション1
        Alice->>Bob: メッセージ1
    and アクション2
        Alice->>Charlie: メッセージ2
    end
```

### クリティカル
```mermaid
sequenceDiagram
    critical 必須処理
        Alice->>Bob: 重要な呼び出し
    option 例外A
        Alice->>Bob: ハンドリング
    end
```

### ブレイク
```mermaid
sequenceDiagram
    break エラー発生
        Alice->>Bob: 中断
    end
```

## 背景色ハイライト

```mermaid
sequenceDiagram
    rect rgb(200, 230, 255)
        Alice->>Bob: ハイライト区間
    end
```

## 連番表示

```mermaid
sequenceDiagram
    autonumber
    Alice->>Bob: 1番目
    Bob->>Alice: 2番目
```

## 参加者の生成・破棄

```mermaid
sequenceDiagram
    create participant B
    A->>B: 生成
    destroy B
    B->>A: 終了
```
