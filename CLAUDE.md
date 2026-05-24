# Claude Code — グローバル行動ルール（けん専用）

## このリポジトリについて

`kennami4887-cell/vs-` は、Claude Code のグローバル設定リポジトリ。
コードプロジェクトではなく、AI アシスタントの行動ルールと外部脳プロトコルを定義するファイル群。

- **主な用途**: Claude Code on the Web セッションに読み込まれる `CLAUDE.md` の管理
- **ブランチ戦略**: `claude/*` ブランチで変更 → PR → マージ
- **変更頻度**: ユーザープロファイル・プロトコルの更新時のみ

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

## AI アシスタント向け規約

### コーディングスタイル（将来のスクリプト追加時）

- コメントは「なぜ」だけ書く。「何をしているか」は書かない
- 絵文字は使わない（明示的に求められた場合のみ）
- ドキュメントファイル（*.md）は明示的に求められた場合のみ作成

### このリポジトリへの変更ルール

- **CLAUDE.md を更新する場合**: 必ず `claude/*` ブランチを切り、PR経由でマージ
- **直接 main への push は禁止**
- 変更内容は Obsidian の `Projects/vs-.md` に記録する

### コミットメッセージ規約

```
<動詞（英語）>: <変更内容（日本語可）>

例:
update: Obsidian プロトコルにフォルダID一覧を追加
add: Google Drive フォルダID テーブルを整理
fix: セッション開始時の読み込み手順を修正
```
