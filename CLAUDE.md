# Claude Code — けん専用ルール（Web・全環境共通）

## ユーザー情報
- 名前: けん（安藤）/ LSIクーラー株式会社
- Gmail: kennami4887@gmail.com
- 回答スタイル: 基本は短文。知らないこと・初めての概念は詳しく説明する
- ここは「設計室」: 自動化・スクリプト・コードの作業場

---

## ⚡ セッション開始時（必須・スキップ禁止）

新しい会話の最初のメッセージで、以下を**この順番で**必ず実行する：

1. **Google Drive MCP** で以下を読む：
   - `Preferences/profile.md`（fileId: `1Fore1MXLC9nn7eROlRQ5ckHr3s0JdDMS`）
   - `Claude/context.md` → **フォルダ `1By-fpOtoIbp1YgCFjiCG4Qy0_I_YVqX7` 内の `context.md` を検索し、modifiedTimeが最新のものを読む**
   - `Knowledge/mistakes.md`（fileId: `1u6s3FBuXKOAkfi1nQnVoP2HouuY1aw4A`）

2. ユーザーの質問に関連するキーワードでVaultを検索し、ヒットしたノートも読む

3. 読んだことを報告する：
   ```
   Obsidian: profile.md・context.md・mistakes.md を読みました
   ```

**スキップ可**：「今何時?」「1+1は?」など明らかに無関係な単発質問

---

## 📝 セッション中の書き込み

「後で書く」はしない。該当したらその場で書く。

| 内容 | 保存先フォルダID |
|------|----------------|
| バグ解決・ツール発見・環境構築のハマり | `1PNdOHFANUWgmwC6yh94o1zrFgH3gnJAG`（Claude/knowledge/） |
| A vs B の判断・設計方針の決定 | `1Okmw-l-2tA4ae6Syn8uTJRO-cO4V6HYE`（Claude/decisions/） |
| プロジェクト状態の変化 | `1Fo0qvhlBRgshN3eRP9gg0UzJX2sAKDc1`（Claude/projects/） |
| ユーザーの好み・スタイルの新発見 | fileId `1Fore1MXLC9nn7eROlRQ5ckHr3s0JdDMS` を更新 |

### ファイル命名規則
- knowledge/: `topic-subtopic.md`
- decisions/: `YYYY-MM-DD-topic.md`
- projects/: `project-name.md`

### フロントマター（必須）
```yaml
---
date: YYYY-MM-DD
tags: [tag1, tag2]
project: project-name
---
```

---

## 🔚 セッション終了時（必須・スキップ禁止）

会話が自然に終わると判断した時点で、ユーザーへの確認なしに以下を実行する：

### 1. 今日のログを保存
- フォルダID: `1k7GeKxQErESo4WT-8IyGJuWLg6YNWBs9`（Claude/log/）
- ファイル名: `YYYY-MM-DD.md`
- 内容：
  ```markdown
  ---
  date: YYYY-MM-DD
  ---

  ## 今日のセッション

  ### 話したこと
  （主なトピックを箇条書き）

  ### 決めたこと・学んだこと
  （重要な決定・発見）

  ### 残タスク
  （続きがあれば）
  ```

### 2. context.md を更新
- フォルダ `1By-fpOtoIbp1YgCFjiCG4Qy0_I_YVqX7` に新しい `context.md` を作成する（Drive MCPは上書き不可のため新規作成。最新だけが読まれる）
- 「最近の決定・学び」に今日の内容を1行追記
- 「引き継ぎ事項」を必要に応じて更新

### 3. 完了報告
```
Obsidian: log/YYYY-MM-DD.md に保存しました
Obsidian: context.md を更新しました
```

---

## 📢 透明性ルール

読み書きしたら必ず明示する：
- `Obsidian: [ファイル名] を読みました`
- `Obsidian: [ファイル名] に書き込みました`

サイレントで読み書きしない。

---

## 🗂️ Google Drive フォルダ・ファイルID一覧

| パス | ID |
|------|-----|
| Vault root | `1CoIJ0q_bDUQ455RrwYh-k8ANGcKCJXx8` |
| Claude/ | `1By-fpOtoIbp1YgCFjiCG4Qy0_I_YVqX7` |
| Claude/log/ | `1k7GeKxQErESo4WT-8IyGJuWLg6YNWBs9` |
| Claude/knowledge/ | `1PNdOHFANUWgmwC6yh94o1zrFgH3gnJAG` |
| Claude/decisions/ | `1Okmw-l-2tA4ae6Syn8uTJRO-cO4V6HYE` |
| Claude/projects/ | `1Fo0qvhlBRgshN3eRP9gg0UzJX2sAKDc1` |
| Claude/memory/ | `1-b7erBMYFxNsT1NfyqVD4aY7i6WPm9_3` |
| Knowledge/ | `1HiVZtyeEC5DZAyVtiIvnAKYIbTUvb7Ek` |
| Decisions/ | `1Oci2GiyN_wLUcsh1ZVkU54tdAR2FP2Hd` |
| Projects/ | `1RE0JwNw6fHvRH5_dMa4I659x6VBHaBbV` |
| Preferences/ | `1Lx73Gai7r5bM_e-mzBt37-1vfB0fu4zT` |
| Preferences/profile.md | `1Fore1MXLC9nn7eROlRQ5ckHr3s0JdDMS` |
| Knowledge/mistakes.md | `1u6s3FBuXKOAkfi1nQnVoP2HouuY1aw4A` |
