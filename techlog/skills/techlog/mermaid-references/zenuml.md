# ZenUML

シーケンス図の別記法。プログラミング言語風の構文でコード寄りの対話フローを記述。

> **制約: ZenUMLはMermaid標準バンドルに含まれない外部プラグイン。** Zenn/Qiitaでのレンダリングは非対応の可能性が高い。代わりに通常の `sequenceDiagram` を使用すること。どうしてもZenUMLが必要な場合は、読者の環境での表示を事前確認する旨を記事に明記する。

## 基本構文

```
zenuml
    Alice -> Bob: sync message
    Alice --> Bob: async message
```

## メッセージタイプ

- `->`: 同期（ブロッキング）
- `-->`: 非同期（ファイア&フォーゲット）
- `<-` / `<--`: 返信
- `@return`: レベルアップ返信

## オブジェクト生成

```
Alice -> new Bob: 生成
```

## ネスト

```
Alice -> Bob {
    Bob -> Charlie: ネスト呼び出し
}
```

## 制御構造

### ループ
```
while(条件) {
    Alice -> Bob: 繰り返し
}
```

`while`, `for`, `forEach`, `loop` が使用可能。

### 条件分岐
```
if(条件1) {
    Alice -> Bob: パスA
} else if(条件2) {
    Alice -> Bob: パスB
} else {
    Alice -> Bob: パスC
}
```

### オプション
```
opt {
    Alice -> Bob: 任意
}
```

### 並列
```
par {
    Alice -> Bob
    Alice -> Charlie
}
```

### 例外処理
```
try {
    Alice -> Bob
} catch {
    Alice -> Error
} finally {
    Alice -> Log
}
```
