# Thinking Tools Reference

Use this reference when AskQuestion needs deeper prompts for the Shannon -> Ockham -> Feynman loop.

The loop is recursive: Feynman compresses the current state, then Shannon can digest that compressed state again.

## Shannon

Purpose: clarify the problem before solving it.

Shannon moves:

1. Simplify the problem
   - Remove noise, secondary constraints, and decorative context.
   - Ask: if only one problem can be solved, what is it?
   - Output: the smallest root problem worth solving.

2. Find similar problems
   - Search for solved neighboring cases.
   - Ask: what previous project, product, decision, or failure looks like this?
   - Output: comparable pattern, borrowed lesson, and mismatch.

3. View from multiple angles
   - Reframe through user, business, execution, finance, risk, and time.
   - Ask: does the same recommendation survive each angle?
   - Output: blind spots and perspective conflicts.

4. Think backward
   - Assume the desired result already happened, or assume the project failed.
   - Ask: what must be true for success? where would failure start?
   - Output: necessary conditions and likely failure points.

5. Split into smaller problems
   - Break the problem into research, decision, pilot, delivery, and review.
   - Ask: what is the smallest validation that reduces the biggest uncertainty?
   - Output: validation path and staged plan.

6. Extend the solution as far as possible
   - Generalize the solution after it works.
   - Ask: what template, mechanism, checklist, or reusable asset remains?
   - Output: reusable asset and next application.

Shannon output shape:

```text
Root problem:
Similar pattern:
Angle conflicts:
Backward condition:
Smallest validation:
Reusable extension:
Re-digestion target:
```

## Ockham

Purpose: cut anything that does not improve the decision.

Ockham cuts:

- unsupported background
- abstract motivation without evidence
- goals that cannot be observed or tested
- deliverables nobody will use
- tasks without owners
- scope without non-goals
- risks without validation paths
- complexity added for elegance, completeness, or status

Ockham questions:

```text
Does this sentence change the decision?
Does this goal have an observable success signal?
Does this deliverable have a user?
Does this task have an owner?
Does this risk have a test?
Can this branch disappear instead of being handled?
```

Ockham output shape:

```text
Keep:
Cut:
Non-goals:
Remaining decision gaps:
```

## Feynman

Purpose: compress the result until a non-expert can repeat it.

Feynman method:

1. State the problem in plain words.
2. Name who is affected.
3. Explain why now matters.
4. Name what this round will and will not do.
5. Define the success signal.
6. Name the biggest risk.
7. Give the recommendation.

Feynman questions:

```text
Can a smart outsider repeat this after one reading?
Which word is vague?
Which claim needs an example?
Which sentence can be shorter?
What is the one sentence decision-maker version?
```

Feynman output shape:

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
1. Is the root problem still accurate?
2. Which assumption remains untested?
3. Does another angle change the conclusion?
4. Where would this fail?
5. Can this be split smaller?
6. What reusable asset can remain?
Next:
```

The `Shannon hooks` field is mandatory in continuing conversations. It is the interface that lets the next loop consume the current conclusion.

## Judge

Purpose: decide whether another loop is needed.

Pass criteria:

- root problem is explicit
- evidence is named, or the evidence gap is named
- scope includes non-goals
- success can be observed
- owner is clear when action is requested
- riskiest assumption has a test
- final explanation fits in 60 seconds
- output includes Shannon hooks when the conversation should continue

If any criterion fails, return the weakest gap and send it back to the right agent:

```text
Unclear problem -> Shannon
Bloated plan -> Ockham
Unrepeatable explanation -> Feynman
No next-loop hooks -> Feynman
```
