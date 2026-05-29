# AskQuestion

[中文](README.zh.md) / [日本語](README.ja.md) / [한국어](README.ko.md)

AskQuestion is a question-driven agent loop for conversations that keep refining themselves.

It turns fuzzy ideas into a compact loop state: clear enough to use now, structured enough for Shannon to digest again in the next turn.

## Flow

```text
Input -> Shannon -> Ockham -> Feynman -> Judge -> Loop State -> next Shannon pass or stop
```

- Shannon clarifies the problem.
- Ockham cuts the noise.
- Feynman compresses the current conclusion until a human can repeat it.
- Judge checks whether to stop or send the compressed state back into Shannon.

Feynman is not the endpoint. Its output becomes the next input when the conversation should continue.

## Default Output

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

## Use Cases

- project initiation
- proposal compression
- requirement clarification
- decision briefs
- interview question design
- agent-loop design

## Repository Contents

```text
SKILL.md
references/thinking-tools.md
README.md
README.zh.md
README.ja.md
README.ko.md
```

The root `SKILL.md` is the skill. There is no extra `skills/askquestion` wrapper.

Optional global memory lives at `~/.askquestion/memory.md`. It is user-level state, not repository content.

## Install

Install for Codex with the [skills CLI](https://www.skills.sh/docs):

```bash
npx skills add hiyeshu/askquestion -g --agent codex --skill askquestion
```

To opt out of skills CLI telemetry:

```bash
DISABLE_TELEMETRY=1 npx skills add hiyeshu/askquestion -g --agent codex --skill askquestion
```

## Sixty-Second Version

```text
What problem do we have?
Who does it affect?
Why handle it now?
What will this round do and not do?
What change proves success?
What is the biggest risk?
What should Shannon inspect next?
```
