# Qiita プラットフォームガイド

## Front Matter（必須）

```yaml
---
title: "記事タイトル"
tags:
  - React
  - Next.js
  - TypeScript
private: false
---
```

| フィールド | 説明 |
|---|---|
| `title` | 記事タイトル（必須） |
| `tags` | タグ一覧。最大5つ。各タグは大文字始まりも可（`React`, `TypeScript`） |
| `private` | `false` で公開、`true` で限定公開。常に `false` で出力 |

### tags選定のコツ

- Qiitaで既に使われているタグ名に合わせる（`React` not `react`、`Next.js` not `nextjs`）
- メインの技術 + 関連技術 + 抽象カテゴリの組み合わせ
  - 例: `React`, `TypeScript`, `hooks`, `フロントエンド`, `初心者`
- 「初心者」タグは初学者向け記事で有効（読者層が広がる）

## Qiita独自のMarkdown拡張

### 注意書き

```markdown
:::note info
補足情報をここに書く
:::

:::note warn
注意事項をここに書く
:::

:::note alert
重要な警告をここに書く
:::
```

### コードブロックのファイル名

````markdown
```typescript:src/app/page.tsx
export default function Home() {
  return <h1>Hello</h1>
}
```
````

### 数式（KaTeX）

```markdown
```math
e^{i\pi} + 1 = 0
```
```
