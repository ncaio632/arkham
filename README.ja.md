# arkham

状況に応じた登録設計。

[English](README.md) · [Português](README.pt-BR.md) · [日本語](README.ja.md)

位置情報、サーバーで管理する募集範囲、参加条件、申請レビューを結び付ける登録仕様です。

## はじめに

[実装手引き](engineering/index.ja.md)

## ドキュメント

- [アーキテクチャと不変条件](docs/architecture.ja.md)
- [データ契約と合成サンプル](docs/contracts.ja.md)
- [設計判断と影響](docs/decisions.ja.md)
- [検証基準](docs/validation.ja.md)
- [エージェント指示](AGENTS.md) · [役割定義](agents/)

## 範囲

エンジニアリング文書と合成サンプルです。提案した動作、実装タスク、観測した証拠を区別します。エージェントは明示的に呼び出し、同期処理はAIモデルを実行しません。
