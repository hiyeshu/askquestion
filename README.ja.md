# AskQuestion

[中文](README.zh.md) / [English](README.md) / [한국어](README.ko.md)

AskQuestion は、対話の中で自分自身を更新し続ける質問型 agent loop です。

あいまいなアイデアを、今使えるだけでなく次の Shannon が再び読み解ける loop state に圧縮します。

## 流れ

```text
Input -> Shannon -> Ockham -> Feynman -> Judge -> Loop State -> next Shannon pass or stop
```

- Shannon：問題を明確にする。
- Ockham：不要な情報を削る。
- Feynman：現在の結論を、人が言い直せる形まで圧縮する。
- Judge：止めるか、圧縮した状態を次の Shannon に戻すかを判断する。

Feynman は終点ではありません。対話を続ける必要があるとき、その出力は次の Shannon の入力になります。

## 既定の出力

```text
Current conclusion:

Compression:

Why:

Loop state:
- Root problem:
- Scope:
- Success signal:
- Biggest risk:

Shannon hooks:
1.
2.
3.

Next:
```

## 向いている用途

- プロジェクト立ち上げ
- 提案の圧縮
- 要件の明確化
- 意思決定メモ
- インタビュー質問設計
- agent loop 設計

## リポジトリ内容

```text
SKILL.md
references/thinking-tools.md
README.md
README.zh.md
README.ja.md
README.ko.md
```

ルートの `SKILL.md` が skill 本体です。追加の `skills/askquestion` ラッパーはありません。

任意のグローバルメモリは `~/.askquestion/memory.md` に置きます。これはユーザーレベルの状態であり、リポジトリの内容ではありません。

## インストール

[skills CLI](https://www.skills.sh/docs) で Codex にインストールします：

```bash
npx skills add hiyeshu/askquestion -g --agent codex --skill askquestion
```

skills CLI のテレメトリを無効にする場合：

```bash
DISABLE_TELEMETRY=1 npx skills add hiyeshu/askquestion -g --agent codex --skill askquestion
```

## 60 秒版

```text
どんな問題があるのか？
誰に影響するのか？
なぜ今扱うのか？
今回は何をやり、何をやらないのか？
成功はどんな変化でわかるのか？
最大のリスクは何か？
次の Shannon は何を確認すべきか？
```
