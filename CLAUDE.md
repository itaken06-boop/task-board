# Task Board — Project Guide

## Overview

タスク管理ボードアプリケーション。

## 技術スタック

| 種別 | 技術 |
|---|---|
| フレームワーク | React 18 |
| ビルドツール | Vite 5 |
| 言語 | JavaScript (JSX) |
| スタイリング | CSS Modules (`App.css`, `index.css`) |
| 状態管理 | React `useState` / `useEffect` |
| 永続化 | `localStorage` |

### 主要コマンド

```bash
npm run dev      # 開発サーバー起動 (http://localhost:5173)
npm run build    # 本番ビルド → dist/
npm run preview  # ビルド結果をローカルで確認
```

## コンポーネント命名規約

- コンポーネントファイル・関数名は **PascalCase** — 例: `App.jsx`, `TaskItem.jsx`
- CSSクラス名は **kebab-case** — 例: `.task-item`, `.add-btn`
- ハンドラ関数は **動詞 + 対象** の形式 — 例: `addTask`, `toggleTask`, `deleteTask`
- 状態変数は **名詞** または **is/has プレフィックス** — 例: `tasks`, `input`, `isDone`

## デプロイ先

- **GitHub Pages**: https://itaken06-boop.github.io/task-board/
- **リポジトリ**: https://github.com/itaken06-boop/task-board
- `main` ブランチへのプッシュで GitHub Actions が自動デプロイ

## Git 運用ルール

### コード変更後の必須手順

**コードを変更するたびに、必ずGitHubへプッシュすること。**

具体的な手順:

1. 変更をステージングに追加
   ```bash
   git add <変更ファイル>
   ```

2. コミット（変更内容を簡潔に記述）
   ```bash
   git commit -m "変更内容の説明"
   ```

3. GitHubへプッシュ
   ```bash
   git push origin main
   ```

### コミットメッセージ規約

| プレフィックス | 用途 |
|---|---|
| `feat:` | 新機能追加 |
| `fix:` | バグ修正 |
| `refactor:` | リファクタリング |
| `docs:` | ドキュメント変更 |
| `chore:` | ビルド・設定変更 |

例: `feat: タスク追加フォームを実装`

### ブランチ戦略

- `main` — 本番相当の安定ブランチ
- `feature/<機能名>` — 機能開発ブランチ
- `fix/<バグ名>` — バグ修正ブランチ

### 注意事項

- `main` へのforce pushは禁止
- コミット前にテストが通ることを確認する
- `.env` などの機密情報を含むファイルはコミットしない
