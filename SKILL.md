---
name: askquestion
description: "Use this skill to adjust fuzzy requests through an agent loop where Shannon clarifies the problem, Ockham cuts the noise, and Feynman compresses the conclusion until a human can repeat it. Trigger for problem framing, project initiation, proposal compression, decision briefs, question design, and agent-loop workflows."
---

# AskQuestion

Use this skill as an agent loop, not as a static template.

Load `~/.askquestion/memory.md` first when it exists. It is user-level memory for the loop.

If the global memory file is missing, continue with the loop contract in this skill. Do not create global memory unless the user asks for it.

## Loop

```text
Input
  -> Shannon
  -> Ockham
  -> Feynman
  -> Judge
  -> Loop State
  -> next Shannon pass or stop
```

Run the loop until the result is clear enough to decide, execute, and repeat.

Feynman output is not the final endpoint. It is a compressed state that the next Shannon pass can digest again.

For detailed method prompts, load `references/thinking-tools.md`. Use it when the task needs deeper problem framing, when the user explicitly mentions Shannon, Ockham, or Feynman, or when the first loop is too vague.

## Agent Contracts

### Shannon

Mission: make the problem clear.

Do:

- simplify the request to one root problem
- compare it with similar solved problems
- inspect it from multiple angles
- invert it by asking how it would fail
- split it into the smallest useful validation path
- ask what reusable asset remains if it succeeds

Return:

```text
Root problem:
Comparable pattern:
Key assumptions:
Missing evidence:
Failure points:
Smallest validation:
Reusable asset:
Re-digestion target:
```

### Ockham

Mission: cut the noise.

Remove:

- unsupported background
- vague goals
- unverifiable success criteria
- unused deliverables
- ownerless tasks
- unbounded scope
- untestable risks
- decorative completeness

Return:

```text
Kept:
Cut:
Non-goals:
Decision-critical gaps:
```

### Feynman

Mission: compress the conclusion until a human can repeat it.

Use:

```text
We have ______ problem.
It affects ______.
It matters now because ______.
This loop should do ______ and should not do ______.
Success means ______ changes.
The biggest risk is ______.
Recommendation: start / pause / reject.
```

Return:

```text
Current conclusion:
Compression:
Shannon hooks:
Next:
```

### Judge

Mission: decide whether to repeat the loop.

Pass only if:

- the root problem is explicit
- evidence is named or the evidence gap is explicit
- scope has both goals and non-goals
- success is observable
- ownership is clear
- the riskiest assumption can be tested
- the final answer supports a decision
- a non-expert can repeat it in one minute
- the output exposes hooks for the next Shannon pass

If weak, return:

```text
Repeat needed: yes
Gap:
Return to: Shannon / Ockham / Feynman
```

If strong, return:

```text
Repeat needed: no
Loop state:
```

## Default Output

Use this form unless the user asks for another format:

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

## Operating Rules

- Prefer a first loop over many clarifying questions.
- Ask one question only when the loop cannot start.
- Keep the output as short as the decision allows.
- Make every output digestible by a future Shannon pass.
- Show the loop result, not private chain-of-thought.
- Preserve useful user wording, but remove vague adjectives.
- When editing a file, rewrite toward the loop instead of adding more sections.

## Common Modes

- `quick verdict`: one decision and one reason
- `sixty-second brief`: Feynman-only compressed output
- `loop state`: current conclusion plus Shannon hooks
- `decision brief`: full Shannon/Ockham/Feynman/Judge output when the user needs an approval artifact
- `question script`: interview questions generated from Shannon gaps
- `agent-loop spec`: reusable loop definition for another agent
