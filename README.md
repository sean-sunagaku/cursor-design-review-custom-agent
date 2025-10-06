# cursor-design-review-custom-agent

開発設計の壁打ちに特化した Cursor カスタムエージェントの土台です。ベースプロンプトと 3 種類のカスタムコマンドを用意し、SOLID 原則・各種設計原則・主要デザインパターンの観点でレビューや改善提案を引き出せます。

## 構成
- `agent/base_prompt.md`: エージェントのシステムプロンプト。
- `agent/manifest.json`: エージェント設定メタデータ。
- `.cursor/commands/design-review-solid.md`: `/design-review-solid` で呼び出す SOLID 原則チェックテンプレート。
- `.cursor/commands/design-review-principles.md`: `/design-review-principles` で呼び出す 原則バランス診断テンプレート。
- `.cursor/commands/design-review-pattern.md`: `/design-review-pattern` で呼び出す デザインパターン適用チェックテンプレート。

## 使い方
1. Cursor の「Custom Agent」を開き、新規エージェントを追加します。
2. 手早く設定したい場合は `agent/setup_template.md` を開き、セクションごとにコピー & ペーストします。
3. テンプレートを使わない場合は、`agent/base_prompt.md` の内容をシステムプロンプト欄に貼り付けます。
4. `agent/manifest.json` の情報を参考に、エージェント名・説明などのメタ情報を設定します。
5. Custom Command を 3 つ追加し、それぞれの設定に該当する JSON ファイルの `name` `description` `prompt` を貼り付けてください。
   - 入力欄のプレースホルダーも `input_placeholder` を参考に設定できます。
6. エージェントを保存し、設計相談時に呼び出してください。

- `.cursor/commands` に用意した Markdown を置いた状態で Cursor を開くと、チャット入力欄で `/` を押すだけでコマンド一覧に表示されます。
- `/design-review-solid`, `/design-review-principles`, `/design-review-pattern` を選ぶと、それぞれの指示テンプレートがチャットに差し込まれます。
- チーム共有したい場合は `.cursor/commands` フォルダをリポジトリに含めておけば同じコマンドを利用できます。

## 運用メモ
- レビュー対象の素材（設計書・ユースケースメモ・UML 等）は、コマンド実行時に入力欄へ貼り付けます。
- 返答は箇条書きで読みやすく整理されるため、必要に応じてタスク化やドキュメント更新に転記してください。
- プロンプトはプレーンテキストなので、プロジェクトごとに調整・拡張しても構いません。
