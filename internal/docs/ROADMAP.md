# ROADMAP

## 開発ワークフロー（SharpHdl と同型）

- **実装は人手**。エージェントは調査・設計・レビュー・Git 区切り（`.cursor/rules/`）
- **Milestone → Issue（≈1 PR）→ PR 内コミット**。`main` 直の機能／リファクタは避ける
- マージは `gh pr merge --merge` のみ
- 仕様の正 = `internal/docs/`（Git で追跡）、公開利用者向けのみ = `docs/`
- 作業の正 = GitHub Issue／PR
- 詳細正本: [dev-workflow](dev-workflow.md)

---

## マイルストーン

### M0 — 設計凍結（現フェーズ）

- 8 スコープの役割・責務境界を `internal/docs/` に固定する（[VISION](VISION.md)、[scopes/](scopes/)）
- 共通語彙を [GLOSSARY](GLOSSARY.md) に固定する
- SharpHdl 同型の開発ルールを設置する

**成功条件:** 各スコープの入力・保証・出力が文書として並立し、スコープ間で用語の意味が食い違わないこと

### M1 以降 — 未定

M0 の設計が固まってから、どのスコープから縦に通すか・技術選定をどう記録するかを決める。  
決めたら本ファイルにマイルストーンとして追記し、GitHub Milestone を作る。

---

## 後回し

- 実装技術・言語・規格の選定（設計は技術中立のまま固める）
- 特定センサー・特定機材への依存
