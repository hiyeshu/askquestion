# AskQuestion

[English](README.md) / [日本語](README.ja.md) / [한국어](README.ko.md)

AskQuestion 是一个用于持续对话的提问式 agent loop。

它把模糊想法压成一个紧凑的 loop state：当下能用，下一轮又能继续被 Shannon 消化。

## 流程

```text
Input -> Shannon -> Ockham -> Feynman -> Judge -> Loop State -> next Shannon pass or stop
```

- Shannon：把问题想清楚。
- Ockham：把废话砍干净。
- Feynman：把当前结论压到人能复述。
- Judge：判断是停止，还是把压缩状态送回 Shannon。

Feynman 不是终点。对话需要继续时，它的输出就是下一轮 Shannon 的输入。

## 默认输出

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

## 适合

- 项目立项
- 方案压缩
- 需求澄清
- 决策简报
- 访谈提问设计
- agent loop 设计

## 仓库内容

```text
SKILL.md
references/thinking-tools.md
README.md
README.zh.md
README.ja.md
README.ko.md
```

根目录 `SKILL.md` 就是 skill 本体。这里没有额外的 `skills/askquestion` 包装层。

可选的全局记忆放在 `~/.askquestion/memory.md`。它是用户级状态，不属于仓库内容。

## 安装

使用 [skills CLI](https://www.skills.sh/docs) 安装到 Codex：

```bash
npx skills add hiyeshu/askquestion -g --agent codex --skill askquestion
```

如需关闭 skills CLI 遥测：

```bash
DISABLE_TELEMETRY=1 npx skills add hiyeshu/askquestion -g --agent codex --skill askquestion
```

## 60 秒版本

```text
我们遇到什么问题？
它影响谁？
为什么现在要处理？
本轮做什么，不做什么？
成功意味着什么变化？
最大风险是什么？
下一轮 Shannon 应该继续检查什么？
```
