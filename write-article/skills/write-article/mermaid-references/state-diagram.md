# State Diagram

状態遷移、ライフサイクル、ステータスフローの可視化に最適。ワークフローや状態管理の説明記事に活用。

## 基本構文

```mermaid
stateDiagram-v2
    [*] --> Idle
    Idle --> Processing : 開始
    Processing --> Done : 完了
    Done --> [*]
```

## 状態の定義

```mermaid
stateDiagram-v2
    state "待機中" as idle
    state "処理中" as proc
    idle --> proc
```

コロン記法: `StateA: この状態の説明`

## 開始・終了

`[*]`を使用。矢印の方向で開始/終了を区別:
```mermaid
stateDiagram-v2
    [*] --> Active
    Active --> [*]
```

## 遷移ラベル

```mermaid
stateDiagram-v2
    Idle --> Active : トリガー名
```

## 複合状態

```mermaid
stateDiagram-v2
    state Processing {
        Validating --> Executing
        Executing --> Saving
    }
```

ネスト可能。

## 選択（分岐）

```mermaid
stateDiagram-v2
    state check <<choice>>
    Idle --> check
    check --> Success : 条件OK
    check --> Failure : 条件NG
```

## フォーク・ジョイン

```mermaid
stateDiagram-v2
    state fork <<fork>>
    state join <<join>>
    Idle --> fork
    fork --> TaskA
    fork --> TaskB
    TaskA --> join
    TaskB --> join
    join --> Done
```

## 並行状態

```mermaid
stateDiagram-v2
    state Concurrent {
        StateA
        --
        StateB
    }
```

## ノート

```mermaid
stateDiagram-v2
    Active
    note right of Active
        この状態の説明
    end note
```

## 方向

```mermaid
stateDiagram-v2
    direction LR
```

`LR`, `RL`, `TB`, `BT`

## スタイリング

```mermaid
stateDiagram-v2
    classDef active fill:#f00,color:white
    Active:::active
```
