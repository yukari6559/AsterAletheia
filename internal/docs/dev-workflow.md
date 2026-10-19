# 開発ワークフロー（SharpHdl と同型）

**目的:** 就活作品・OSS として見られる履歴を残す。枚数稼ぎではなく、**普通のチーム開発に見える粒度**にする。  
**役割:** 実装は人手（原則）。**ブランチ作成・Issue／Milestone・PR・コメント編集・マージはエージェント**が行う。

関連: [ROADMAP.md](ROADMAP.md) / [VISION.md](VISION.md)

---

## 0. 階層の正

```
Milestone …… テーマ全体（例: M0 設計凍結、S4 観測セッション、版 v0.1.0）
  └─ Issue …… レビュー可能な 1 ステップ（≒ 後で 1 PR）
        ├─ 本文チェックリスト …… 細かい手順（Issue にしない）
        └─ PR
              └─ コミット …… PR 内の論理単位（Issue にしない）
```

| 層 | 役割 | 例 |
|----|------|-----|
| **Milestone** | テーマ全体を束ねる | `m0-design-freeze` |
| **Issue** | マージ可能な成果 1 つ | `#3 docs: Define session bundle boundary (S4)` |
| **チェックリスト** | Issue 内の手順メモ | `- [ ] 入力の列挙` `- [ ] 出力の定義` |
| **PR** | Issue を閉じる差分 | `Closes #3` |
| **コミット** | PR 内の読みやすい区切り | スコープ文書 → 用語集 → 索引更新 |

### 採用しない点
- **サブIssue をコミット単位まで切る**
- **サブIssue 完了＝1コミットで Issue を閉じる**

理由: 評価者が見るのは主に **PR の質・説明・テスト** と **Issue の意図**。Issue の枚数ではない。OSS／業務の定石は **Milestone → Issue → PR**。コミットは PR の内部履歴。

### サブIssueを使ってよい例外
別 PR になりうる・長いブロッカー・明確に並列できるときだけ。それでも **1 サブIssue ≈ 1 PR 候補** であり、1 コミットではない。

---

## 1. 新しいタスクを立てるときのフロー（必須）

1. **テーマを決める** → Milestone があるか確認。無ければ作成
   - フェーズ: `m0-design-freeze`
   - スコープ束: `s4-session-bundle` など
   - 版: `v0.1.0`
2. **レビュー可能な塊に分割** → 各塊を **Issue** にする
   - 目安: 半日〜数日、1 PR で見られる差分
   - スコープをまたぐ変更は、境界の変更（[VISION](VISION.md) の責務境界表）を先に 1 Issue にする
3. **細かい手順** → Issue 本文の **チェックリスト**（サブIssueにしない）
4. **実装** → `feat|refactor|…/<issue>-<short>` ブランチ → 論理単位でコミット → **PR**（`Closes #N`）
5. **完了** → PR マージで Issue クローズ。`internal/docs/` の状態も更新

「タスク生成」の出力は、少なくとも次を含む文案にする:  
Milestone 名、Issue タイトル、本文（スコープ ID・完了条件・チェックリスト案）、ブランチ名案、想定コミット分割（PR 内）。

---

## 2. 役割分担

| 置き場 | 役割 |
|--------|------|
| `internal/docs/`（Git で追跡。`internal/` のそれ以外はローカル専用） | 設計・スコープ定義・ロードマップ・用語 |
| `docs/` | 公開する利用者向けのみ |
| **GitHub Milestone** | テーマ／版の束 |
| **GitHub Issue** | 公開される作業単位（1 Issue ≈ 1 PR） |
| **PR + コミット** | 実装履歴（コミットは Issue にしない） |

仕様の正本 = `internal/docs/`。作業トラッキングの正本 = GitHub Issue／PR。

---

## 3. Milestone

- オープン Issue はいずれかの Milestone に属させる
- スコープ単位の大きな仕事は Milestone にし、中のステップを Issue にする

---

## 4. Issue

### 立て方
- タイトル例: `docs: Define measurement proof categories (S6)`
- 本文: スコープ ID、完了条件、触る文書／パッケージ、**チェックリスト（細ステップ）**
- ラベル: 種別 `feat` / `refactor` / `fix` / `docs` / `test` / `chore` ＋ スコープ `s1`〜`s8`
- Milestone 必須

### 粒度
| ダメ | よい |
|------|------|
| Milestone 無しで巨大 Issue 1 本 | テーマは Milestone、中身は複数 Issue |
| 細手順をサブIssue＋1コミット | 同じ内容を親 Issue の `- [ ]` に書く |
| 1 スコープ全部を 1 Issue | 機能単位（例: S4 の束ね／不変性／遅延同期）に割る |

### 閉じ方
- PR の `Closes #N`
- `internal/docs/` も更新

---

## 5. ブランチ

```
main
feat/<issue>-<short>
refactor/<issue>-<short>
fix/<issue>-<short>
docs/<issue>-<short>
chore/<issue>-<short>
```

- Issue 番号を含める
- `main` から切る。共有ブランチへの force push 禁止
- 機能・リファクタは原則 `main` 直コミットしない

---

## 6. Pull Request とコミット

**PR**
- 1 PR ≈ 1 Issue
- Summary / Test plan / `Closes #N` / スコープ ID
- 自分のみレビューでも PR を残す（履歴が目的）
- **マージは merge commit のみ**（squash / rebase はリポで無効）。`gh pr merge` は `--merge` を使う

**コミット（PR 内）**
- **1 コミット = 説明できる一塊**。複数単位なら分ける
- ユーザーが「コミットして」だけでも、エージェントは差分を見て **必要なだけ複数コミット**する（都度確認しない）
- Conventional 寄り: `feat:` / `refactor:` / `fix:` / `docs:` / `chore:` / `test:`
- **コミットごとに Issue／サブIssueを増やさない**
- 版上げは `chore: bump …` ＋タグ `vX.Y.Z`（実装 PR と分ける）

### `main` 直コミットの例外
- リポジトリ初期化（初回コミット）
- typo・1 行 docs（できれば Issue）
- ユーザーが「main に直接」と明示した場合

---

## 7. エージェント向け

`no-concrete-code`（実装は明示依頼があるまで人手）は継続。  
**リポジトリ操作（GitHub / ブランチ）はエージェントが担う**（ユーザーが都度指示しなくてよい。区切りが来たら実行する）。

| タイミング | 内容 |
|------------|------|
| **作業開始** | Milestone の有無を確認し、無ければ作成。対応 Issue を作成または既存に紐づけ。`feat|refactor|fix|docs|chore/<issue>-<short>` を **作成して checkout** |
| **マージ可能な品質になったとき** | push → **PR 作成**（タイトル Conventional、本文に Summary / Test plan / `Closes #N` / スコープ ID）→ 必要に応じて PR 説明やレビューコメントを編集 → **マージ**（`gh pr merge --merge`）。Issue／Milestone の状態を確認 |
| **版上げ** | 実装 PR と分け、chore Issue＋PR |
| **「次へ」** | 次 Milestone／Issue を案内し、着手するならブランチまで切る |

**常時委任（2026-10-19〜）:** コミット・PR・マージまで常に許可。ただし任意／必須のやり残し指摘があるときは進めず確認する（`.cursor/rules/dev-workflow.mdc`）。

### やらない／推さない
| 内容 | 代わり |
|------|--------|
| サブIssue＝1コミット | Issue チェックリスト＋PR 内コミット |
| 勝手な `main` 直コミット（機能） | ブランチ＋PR |
| 実装の先回り | 明示「実装して」等があるまで案内のみ |
| 技術選定の先回り | 設計が固まってから根拠を残して決める |

---

## 改版履歴

| 版 | 日付 | 変更 |
|----|------|------|
| 1.0 | 2026-10-19 | SharpHdl の dev-workflow 1.3 を基に初版。スコープ ID（S1〜S8）とラベルを追加 |
