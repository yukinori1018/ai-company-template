# ai-company-template

ローカルフォルダで動く「AI 仮想会社」を構築するための**親テンプレート**です。
GitHub Template repository 機能から複製して、事業ごとの**子会社**リポジトリを作る運用を想定しています。

> **Status:** 構築中（Phase 1 / 全7フェーズ）。詳細な使い方ガイドは Phase 6 で記述します。

## このテンプレートの位置づけ

- このリポジトリには「**どの事業でも共通して使える型**」だけが入っています。
- 事業固有の内容（会社名・商品名・ミッション等）はすべて `{{ 事業名 }}` のような**プレースホルダー**になっており、子会社化時に穴埋めします。

## 構成（Phase 1 時点の骨格）

```
.
├── CLAUDE.md                 # 会社全体のルール（Phase 2 で本格化）
├── agents/                   # 各エージェント
│   ├── secretary/            # 秘書（メイン窓口）
│   ├── accounting/           # 経理
│   ├── legal/                # 法務
│   ├── general_affairs/      # 庶務
│   └── content_creator/      # コンテンツ制作
├── workspace/
│   ├── tickets/{todo,doing,waiting,done}/   # タスク管理（Git 管理）
│   └── output/{agent_output,final_output}/  # 成果物（.gitignore）
└── docs/
    └── reference/動画分析.md  # 設計の出典
```

各エージェントフォルダは `agent.md` / `memory/` / `skills/` の3点セットを持ちます。

## 参考

- 設計の出典: [docs/reference/動画分析.md](docs/reference/動画分析.md)
