# humanizer-ja

日本語の説明文・ブログ記事から「AIが書いた感」を取り除き、自然な日本語に書き換える Claude Code / opencode 向け skill。

300〜700字程度の解説・ブログを推敲・リライトするときに使う。事実・数値・固有名詞・主張・結論はそのまま保ったうえで、「近年〜」のような定型の出だし、重要性の水増し、冗長な接続、過剰な体言止め、曖昧な伝聞、無意味な絵文字や太字などの不自然さを直す。診断レポートではなく、**読める日本語そのもの**を返すことを最優先にする。

## 使い方

```
# Claude Code / opencode に skill として追加
npx skills add https://github.com/Ran350/humanizer-ja
```

追加後、次のように頼む:

> 次の文章を humanizer-ja で自然な日本語に直して: ...

## スコープ

- **対象**: 300〜700字程度の説明文・解説記事・ブログ。
- **対象外**: SNS投稿、文学作品、ビジネスメール、法律・医療など正確な定型表現が要る専門領域。

## 安全側のガード

- 事実・主張・結論を変えない。新しい情報を足さない。
- 固有名詞・数値・引用・URL を保持する。
- 元のトーン（敬体／常体）を勝手に切り替えない。

skill の中身はすべて [`SKILL.md`](./SKILL.md) にあり、Markdown のみ・外部スクリプトなし・`allowed-tools` は `Read` / `Write` / `Edit` / `AskUserQuestion` に限定している（任意コマンド実行はしない）。

## クレジット

- ベース: [blader/humanizer](https://github.com/blader/humanizer)（MIT License）
- パターンの出典: [Wikipedia: Signs of AI writing](https://en.wikipedia.org/wiki/Wikipedia:Signs_of_AI_writing)（WikiProject AI Cleanup）
