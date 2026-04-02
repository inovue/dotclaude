# dotclaude

Claude Code plugins by inovue

## Plugins

### write-article

ソースマテリアル（URL、ファイル、テキスト）から、技術記事を生成する Claude Code プラグイン

**主な特徴:**

- 認知科学に基づいた「3秒で構造理解、読了後に完全理解」の記事設計
- 28種類の Mermaid ダイアグラムを適切に配置
- コピペで動くコード例
- Zenn / Qiita それぞれのプラットフォームに最適化された出力
- YAML 設定ファイルによるプリセット管理
- 6種類の記事テンプレート（逆説型、Before/After型、ステップバイステップ型、比較・選定型、トラブルシュート型、概念図解型）

**使い方:**

```
/write-article https://example.com/source-article
/write-article ./path/to/source.md
/write-article config
```

## インストール

### 1. マーケットプレイスを追加

Claude Code で以下のコマンドを実行し、マーケットプレイスを登録します。

```
/plugin marketplace add inovue/dotclaude
```

### 2. プラグインをインストール

マーケットプレイスからプラグインを選んでインストールします。

```
/plugin install write-article@inovue-dotclaude
```

または `/plugin` を実行して **Discover** タブからインタラクティブにインストールすることもできます。

### 3. プラグインを有効化

```
/reload-plugins
```

### その他のコマンド

| コマンド | 説明 |
|---|---|
| `/plugin marketplace list` | 登録済みマーケットプレイス一覧 |
| `/plugin marketplace update inovue-dotclaude` | マーケットプレイスを更新 |
| `/plugin` | プラグインマネージャを開く |
| `/plugin uninstall write-article@inovue-dotclaude` | プラグインをアンインストール |

## ライセンス

MIT
