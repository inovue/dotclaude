# GitGraph

Gitのブランチ戦略・コミット履歴の可視化に最適。Git運用やブランチモデルの説明記事に活用。

## 基本構文

```mermaid
gitGraph
    commit id: "初期コミット"
    branch develop
    commit id: "機能追加"
    checkout main
    merge develop id: "マージ" tag: "v1.0"
    commit id: "修正"
```

## コミット

```mermaid
gitGraph
    commit id: "custom_id" tag: "v1.0" type: NORMAL
```

タイプ: `NORMAL`（通常）、`REVERSE`（×印）、`HIGHLIGHT`（強調）

## ブランチ操作

mainに最低1つコミットしてからブランチを作成すること:

```mermaid
gitGraph
    commit id: "init"
    branch feature
    checkout feature
    commit
    checkout main
    merge feature
```

`checkout`と`switch`は同義。

## チェリーピック

```mermaid
gitGraph
    commit id: "a"
    branch dev
    commit id: "b"
    checkout main
    cherry-pick id: "b"
```

## 方向

```mermaid
---
config:
  gitGraph:
    direction: "TB"
---
gitGraph
    commit
    branch dev
    commit
```

方向は設定ブロックで指定: `LR`（左→右、デフォルト）、`TB`（上→下）、`BT`（下→上）

## 設定

```
%%{init: { 'gitGraph': { 'showBranches': true, 'showCommitLabel': true, 'mainBranchName': 'main' } } }%%
```
