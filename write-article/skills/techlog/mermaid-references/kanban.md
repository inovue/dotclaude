# Kanban

タスク管理・ワークフローステータスの可視化。プロジェクト管理やアジャイル手法の記事に活用。

## 基本構文

```mermaid
kanban
    todo[Todo]
        task1[ドキュメント作成]
        task2[設計レビュー]
    inProgress[進行中]
        task3[コード実装]
    done[完了]
        task4[テスト完了]
```

## カラム定義

```
カラムID[カラムタイトル]
```

## タスク定義

カラムの下にインデントして配置:
```
タスクID[タスク説明]
```

## メタデータ

```mermaid
kanban
    todo[Todo]
        task1[重要タスク]@{assigned: "Alice", ticket: "PROJ-101", priority: "High"}
```

- `assigned`: 担当者
- `ticket`: チケット番号
- `priority`: `Very High`, `High`, `Low`, `Very Low`

## チケットリンク設定

```
---
config:
  kanban:
    ticketBaseUrl: 'https://project.atlassian.net/browse/#TICKET#'
---
```
