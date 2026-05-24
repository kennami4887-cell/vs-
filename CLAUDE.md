# Claude Code — グローバル行動ルール（けん専用）

## このリポジトリについて

`vs-` は Claude Code のグローバル設定リポジトリ。アプリケーションコードは存在しない。
CLAUDE.md 1ファイルのみで構成され、Claude の振る舞い・記憶プロトコル・ユーザー設定を定義する。

### リポジトリ構造

```
vs-/
└── CLAUDE.md   ← このファイル。Claude の行動規範すべてを記述
```

### 開発ワークフロー

- 変更はすべて CLAUDE.md の編集のみ
- ブランチ: `claude/` プレフィックスで作業ブランチを切る
- コミット後、`git push -u origin <branch>` でリモートに反映
- PRは明示的に依頼された場合のみ作成する

---

## ユーザー情報
- 名前: けん（安藤）/ LSIクーラー株式会社
- Gmail: kennami4887@gmail.com
- 回答スタイル: 基本は短文。知らないこと・初めての概念は詳しく説明する

---

## Obsidian 外部脳プロトコル（Google Drive MCP経由）

### セッション開始時（必須）

新しい会話の最初のメッセージで以下を実行する:

1. Google Drive MCP で以下のファイルを読む（フォルダID: `1By-fpOtoIbp1YgCFjiCG4Qy0_I_YVqX7`）
   - `context.md` — 現在地サマリー（必須）
   - `protocol.md` — 行動プロトコル（必須）
   - `Preferences/profile.md` — ユーザープロファイル
   - `Knowledge/mistakes.md` — 過去のミス

2. ユーザーの質問に関連するキーワードでVault内を検索し、ヒットしたノートも読む

3. 読んだ内容を踏まえて回答する

スキップ可: 「今何時?」「1+1は?」など明らかに無関係な単発質問

### 書き込みタイミング

後で書くはしない。該当したらその場で書く:

| フォルダ | 書くとき |
|---|---|
| `Knowledge/` | バグ解決・ツール発見・環境構築ハマりと解決策 |
| `Decisions/` | A vs B の判断・設計方針の決定 |
| `Projects/` | プロジェクト状態の変化 |
| `Preferences/` | ユーザーの好み・スタイルの新発見 |

### 透明性ルール

Obsidianを読み書きしたら必ず報告:
- `Obsidian: Claude/context.md を読みました`
- `Obsidian: Knowledge/xxx.md に書き込みました`

---

## Google Drive フォルダID一覧

| パス | フォルダID |
|---|---|
| Vault root | `1CoIJ0q_bDUQ455RrwYh-k8ANGcKCJXx8` |
| Claude/ | `1By-fpOtoIbp1YgCFjiCG4Qy0_I_YVqX7` |
| Claude/memory/ | `1-b7erBMYFxNsT1NfyqVD4aY7i6WPm9_3` |

---

## AIアシスタント向け規約

### 回答スタイル
- 短文を優先。冗長な説明・箇条書きの羅列を避ける
- 初めて出てくる概念・ツールは簡潔に説明する
- 絵文字は使わない（明示的に求められた場合のみ）
- コメントは書かない（WHYが非自明な場合のみ1行）

### git 操作
- プッシュ: `git push -u origin <branch>` を使う
- コミット: 明示的に依頼された場合のみ作成する
- 破壊的操作（`--force`, `reset --hard` 等）は確認を取ってから実行する
- PRは明示的に依頼された場合のみ作成する

### ツール使用
- ファイル読み書きは Read / Edit / Write ツールを優先（Bash の cat/echo より）
- 独立した操作は並列で実行する
- 不確かなURLは提示しない

### セキュリティ
- コード変更でセキュリティ脆弱性（SQLインジェクション、XSS、コマンドインジェクション等）を導入しない
- `.env` や認証情報ファイルをコミットしない
