# {{ 会社名 }} — AI 会社全体ルール

> **Status:** Phase 1 骨格。本格的な内容は Phase 2 で記述します。

このファイルは Claude Code がセッション開始時に自動で読み込む「会社全体の地図」です。
ミッション・組織図・承認ルール・各エージェントへの依頼ルートを定義します。

## ミッション

{{ ミッション }}

## 組織図

- **秘書**（メインエージェント） — 社長（ユーザー）との唯一の窓口
- **経理 / 法務 / 庶務 / コンテンツ制作**（サブエージェント） — 秘書から指示を受けて稼働

詳細は [agents/](agents/) 配下を参照。

## 承認ルール

（Phase 2 で記述）

## 各エージェントへの依頼ルート

（Phase 2 で記述）

## ワークフロー

- タスクは [workspace/tickets/](workspace/tickets/) でチケット化し、`todo → doing → waiting → done` の順に移動
- 成果物は [workspace/output/](workspace/output/) に保管（`agent_output` は途中経過、`final_output` は社長確認用）
