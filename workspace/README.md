# workspace/ — 仕事場

会社のすべての作業はここで起こります。タスクの進行状態（チケット）と成果物が一望できる場所です。

## ディレクトリ構成

```
workspace/
├── tickets/                     # タスク進捗管理（Git 管理）
│   ├── _template.md             # チケット雛形（_ 始まりはスキャン対象外）
│   ├── todo/                    # 未着手
│   ├── doing/                   # 作業中
│   ├── waiting/                 # 社長確認待ち
│   └── done/                    # 完了
├── output/                      # 成果物（.gitignore 対象）
│   ├── agent_output/            # 作業中の途中経過。監査用
│   └── final_output/            # 社長が確認する最終納品物
├── README.md                    # このファイル
└── SUBAGENT_PROTOCOL.md         # サブエージェント共通の受け取り/引き渡し手順
```

## チケット運用

1. **起票** — 秘書が依頼を受けたら必ず [_template.md](tickets/_template.md) をコピーして `tickets/todo/` に新規作成。
2. **遷移** — 状態が変わるたびにファイルを物理的に mv（todo → doing → waiting → done）。
3. **同期** — 秘書が遷移と同時に Notion カンバンへ反映。プロトコル詳細は [agents/secretary/skills/notion-ticket-sync.md](../agents/secretary/skills/notion-ticket-sync.md)。
4. **詳細手順** — 起票・編集・命名規則は [agents/secretary/skills/ticket-management.md](../agents/secretary/skills/ticket-management.md)。

## 成果物の管理

| フォルダ | 用途 | 社長が見るか |
|---------|------|------------|
| `output/agent_output/<ticket_id>/` | サブエージェントの作業中ファイル | 通常見ない（問題発生時の監査用） |
| `output/final_output/<ticket_id>/` | 社長確認用の最終納品物 | **常に見る** |

両フォルダとも `.gitignore` 対象。テンプレ複製時はクリーンな状態でスタートします。

## サブエージェントの作業ルール

サブエージェント（経理・法務・庶務・コンテンツ制作）は [SUBAGENT_PROTOCOL.md](SUBAGENT_PROTOCOL.md) に従って受け取り → 作業 → 引き渡しを行います。

## Notion 連携

- Notion DB 仕様: [docs/notion-board-schema.md](../docs/notion-board-schema.md)
- セットアップ手順: Phase 6 で `docs/notion-setup-guide.md` に整備予定
- MCP 設定スタブ: [.mcp.json.example](../.mcp.json.example)
