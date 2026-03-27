# C4 Diagram

ソフトウェアアーキテクチャの4層可視化。Context/Container/Component/Deploymentレベルの説明記事に活用。

## 図のタイプ

`C4Context`, `C4Container`, `C4Component`, `C4Dynamic`, `C4Deployment`

## System Context

```mermaid
C4Context
    title システムコンテキスト図
    Person(user, "ユーザー", "システムを利用する人")
    System(system, "メインシステム", "中核機能を提供")
    System_Ext(ext, "外部サービス", "連携先")
    Rel(user, system, "使用する")
    Rel(system, ext, "API連携")
```

## Container

```mermaid
C4Container
    title コンテナ図
    Person(user, "ユーザー")
    Container_Boundary(c1, "メインシステム") {
        Container(web, "Webアプリ", "React", "フロントエンド")
        Container(api, "APIサーバー", "Node.js", "バックエンド")
        ContainerDb(db, "DB", "PostgreSQL", "データ格納")
    }
    Rel(user, web, "HTTPS")
    Rel(web, api, "JSON/HTTPS")
    Rel(api, db, "SQL")
```

## 主要要素

- `Person(alias, label, ?descr)` / `Person_Ext`
- `System(alias, label, ?descr)` / `System_Ext`
- `Container(alias, label, ?techn, ?descr)` / `Container_Ext`
- `ContainerDb`, `ContainerQueue`
- `Component(alias, label, ?techn, ?descr)`
- `Deployment_Node(alias, label, ?type, ?descr)`

## 関係

```
Rel(from, to, label, ?techn)
BiRel(from, to, label)
Rel_U / Rel_D / Rel_L / Rel_R (方向指定)
```

## スタイル調整

```
UpdateElementStyle(elementName, ?bgColor, ?fontColor, ?borderColor)
UpdateRelStyle(from, to, ?textColor, ?lineColor, ?offsetX, ?offsetY)
UpdateLayoutConfig(?c4ShapeInRow, ?c4BoundaryInRow)
```
