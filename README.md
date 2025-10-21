# cursor-design-review-custom-agent

開発設計の壁打ちに特化した Cursor カスタムエージェントのプロンプトとカスタムコマンドです。SOLID 原則・各種設計原則・主要デザインパターンから実装/インフラ再設計までシームレスにサポートします。

## 構成
- `agent/base_prompt.md`: エージェントのシステムプロンプト本体。
- `.cursor/commands/design-review/design/solid.md`: SOLID 原則観点のレビューコマンド定義。
- `.cursor/commands/design-review/design/principles.md`: DRY/KISS/YAGNI/LoD 観点のレビューコマンド定義。
- `.cursor/commands/design-review/design/pattern.md`: 主要デザインパターン 20 種の適合性チェックコマンド定義。
- `.cursor/commands/design-review/alternative-patterns.md`: 既存案に対する代替パターン提案コマンド定義。
- `.cursor/commands/design-review/summary.md`: 各レビュー結果を統合するサマリーコマンド定義。
- `.cursor/commands/design-review/recreate.md`: レビュー結果を踏まえた設計書再構築コマンド定義。
- `.cursor/commands/design-review/implement/basic.md`: 基本設計レベルの実装ドキュメント生成コマンド定義。
- `.cursor/commands/design-review/implement/detail.md`: 詳細設計レベルの実装ドキュメント生成コマンド定義。
- `.cursor/commands/design-review/implement/infra-recreate.md`: インフラ構成の再設計ドキュメント生成コマンド定義。

## セットアップ手順
1. Cursor の「Custom Agent」を開き、新規エージェントを追加します。
2. System Prompt 欄には `agent/base_prompt.md` の内容を貼り付けます。
3. エージェント名・説明・言語などのメタ情報は、Cursor の作成画面で直接設定します。
4. 設定を保存し、チャットから呼び出してレビューや再設計の相談に利用します。

`.cursor/commands` フォルダをプロジェクトに含めた状態で Cursor を開くと、チャット入力欄で `/` を押すだけでコマンド一覧に表示されます。UI ではパス形式で表示されるため、`/design-review/design/solid` など任意のコマンドを選択すると、対応する指示テンプレートが自動で差し込まれます。

## カスタムコマンド一覧
### 設計観点チェック
- `/design-review/design/solid` (`.cursor/commands/design-review/design/solid.md`): SOLID 原則ごとの判定・根拠・改善策を整理します。
- `/design-review/design/principles` (`.cursor/commands/design-review/design/principles.md`): DRY/KISS/YAGNI/LoD の観点から複雑さや重複度を診断します。
- `/design-review/design/pattern` (`.cursor/commands/design-review/design/pattern.md`): 主要 20 パターンの適用可否と注意点を精査します。

### 洞察の統合・再設計
- `/design-review/alternative-patterns` (`.cursor/commands/design-review/alternative-patterns.md`): 既存設計に対する代替パターン候補を 3 案提示します。
- `/design-review/summary` (`.cursor/commands/design-review/summary.md`): 各コマンドの知見を俯瞰し、重複やトレードオフを整理します。
- `/design-review/recreate` (`.cursor/commands/design-review/recreate.md`): レビュー結果を踏まえて新しい設計書を再構築します。

### 実装・インフラドキュメント
- `/design-review/implement/basic` (`.cursor/commands/design-review/implement/basic.md`): 基本設計レベルの実装ドキュメントを生成します。
- `/design-review/implement/detail` (`.cursor/commands/design-review/implement/detail.md`): 詳細設計レベルのドキュメントを作成します。
- `/design-review/implement/infra-recreate` (`.cursor/commands/design-review/implement/infra-recreate.md`): インフラアーキテクチャを再設計するドキュメントをまとめます。

## 運用メモ
- `/summary` → `/recreate` → `/implementation` など連鎖的に使うと、レビューから再設計・アウトプット作成までを一気通貫で進められます。
- プロンプトは、プロジェクトに合わせて調整・拡張してください。
