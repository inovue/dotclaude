# Class Diagram

オブジェクト間の関係、型の構造、システム設計の可視化に最適。技術記事でのアーキテクチャ説明に活用。

## 基本構文

```mermaid
classDiagram
    class Animal {
        +String name
        +int age
        +makeSound()
    }
    class Dog {
        +fetch()
    }
    Animal <|-- Dog
```

## メンバー定義

括弧`()`で属性とメソッドを区別:
```mermaid
classDiagram
    class MyClass {
        +String attribute
        -int privateAttr
        +publicMethod()
        -privateMethod() String
    }
```

## 可視性

- `+` Public
- `-` Private
- `#` Protected
- `~` Package/Internal

メソッド修飾子: `method()*`（Abstract）、`method()$`（Static）

## 関係

| 構文 | 種類 |
|------|------|
| `A <\|-- B` | 継承 |
| `A *-- B` | コンポジション |
| `A o-- B` | 集約 |
| `A --> B` | 関連 |
| `A -- B` | リンク（実線） |
| `A ..> B` | 依存 |
| `A ..\|> B` | 実現 |
| `A .. B` | リンク（点線） |

## カーディナリティ

```mermaid
classDiagram
    Customer "1" --> "*" Order : places
```

`1`, `0..1`, `1..*`, `*`, `n`, `0..n`

## アノテーション

```mermaid
classDiagram
    class Shape {
        <<Interface>>
        +draw()
    }
    class Color {
        <<Enumeration>>
        RED
        BLUE
    }
```

## ジェネリクス

```mermaid
classDiagram
    class List~T~ {
        +add(T item)
        +get(int index) T
    }
```

## 名前空間

```mermaid
classDiagram
    namespace MyApp {
        class Service
        class Repository
    }
```

## ノート

```mermaid
classDiagram
    note "全体メモ"
    note for Animal "Animalクラスの説明"
```

## 方向

```mermaid
classDiagram
    direction LR
```

## スタイリング

```mermaid
classDiagram
    style Animal fill:#f9f,stroke:#333
    classDef highlight fill:#f96
    class Dog:::highlight
```
