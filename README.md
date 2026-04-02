# dotclaude

Claude Code plugins by inovue

## Plugins

### techlog

AIっぽさを排除し、人間の声で書くZenn/Qiita向け技術記事ライター

**主な特徴:**

- 「声の原則」に基づいたAIっぽさゼロの文体
- 6つの記事型（逆説型、Before/After型、ステップバイステップ型、比較・選定型、トラブルシュート型、概念図解型）
- ユーモアトーンをデフォルトで適用
- 28種類の Mermaid ダイアグラムを適切に配置
- コピペで動くコード例
- Zenn / Qiita それぞれのプラットフォームに最適化された出力
- YAML 設定ファイルによるプリセット管理

**使い方:**

```
/techlog https://example.com/source-article
/techlog ./path/to/source.md
/techlog config
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
/plugin install techlog@inovue-dotclaude
```

または `/plugin` を実行して **Discover** タブからインタラクティブにインストールすることもできます。

### 3. プラグインを有効化

```
/reload-plugins
```

### 旧バージョン（write-article）からの移行

```
/plugin uninstall write-article@inovue-dotclaude
/plugin marketplace update inovue-dotclaude
/plugin install techlog@inovue-dotclaude
```

### その他のコマンド

| コマンド | 説明 |
|---|---|
| `/plugin marketplace list` | 登録済みマーケットプレイス一覧 |
| `/plugin marketplace update inovue-dotclaude` | マーケットプレイスを更新 |
| `/plugin` | プラグインマネージャを開く |
| `/plugin uninstall techlog@inovue-dotclaude` | プラグインをアンインストール |

## ライセンス

MIT
