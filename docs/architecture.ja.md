# アーキテクチャ

[概要](../README.ja.md) · [English](architecture.en.md) · [Português](architecture.pt-BR.md)

位置情報、拠点に紐づくセッション、参加条件、書類メタデータを扱うモバイル登録フローの設計資料です。

## 処理の流れ

```text
Location input → validated session → base-scoped opportunity → eligibility → required document metadata → simulated receipt
```

## 不変条件

1. 拠点はサーバー側のセッションで決定し、募集情報はそのセッションに基づいて返します。
2. 既存セッションの拠点を暗黙に変更せず、競合として扱います。
3. 申請には有効なセッションを要求し、リクエストの送信元を検証します。
4. 確認したハンドラーはデモ用の書類メタデータのみを受け付け、実際の書類受付は無効です。
5. GPSの近接性は振り分けの入力であり、本人確認や居住地の証明にはなりません。

## 実装の境界

この公開版には技術文書と合成サンプルのみを含みます。公開していないソースや運用データを、公開成果物の一部として扱わないでください。
