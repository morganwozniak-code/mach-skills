---
name: writing-good-prompts
description: Teaches how to write an effective prompt for Droid - goal-first framing, constraints, scope, and success criteria - with before/after examples. Use when someone's request to Droid is vague, when a task went off track because of unclear instructions, or when someone asks how to get better results from Droid.
allowed-tools: []
enabled: true
user-invocable: true
disable-model-invocation: false
license: MIT
compatibility: droid
version: 1.0.0
metadata:
  owner: platform-team
  department: company-wide
---

# Writing Good Prompts

A prompt to Droid is a work order, not a search query. The clearer the work order, the
less back-and-forth and the fewer wrong guesses about scope.

## Instructions

When this skill is invoked, or when you notice a request is too vague to act on
confidently, use the framework below - either to improve the request yourself (ask one
or two clarifying questions) or to coach the person asking on how to phrase it next
time.

### The four things a good prompt states

1. **Goal** - the outcome, not the topic. "Draft a one-page summary of this contract's
   termination clauses for the program manager" beats "look at this contract."
2. **Constraints** - format, length, audience, deadline, tone, and anything that must
   NOT be touched or changed. Silence on a constraint means Droid will guess.
3. **Scope** - is this one step or several? Is it one file/system or many? Say so
   explicitly if it's bigger than it looks from a one-line ask.
4. **Success criteria** - how will you know it's done right? "Matches the template in
   the shared drive," "passes the existing tests," "under 200 words" are all concrete;
   "looks good" is not.

If any of the four is missing and the task has real consequences (money, external
communication, irreversible changes), ask for it before proceeding rather than
assuming.

### Before / after examples

| Vague | Better |
| :--- | :--- |
| "Look at this proposal" | "Check this proposal draft against the RFP's mandatory requirements list and flag anything missing or non-compliant." |
| "Fix the report" | "The Q3 cost report's totals don't match the CLIN breakdown on page 4 - find the discrepancy and fix the total, don't change the CLIN figures." |
| "Summarize this" | "Summarize this 40-page spec in 5 bullets for someone who hasn't read it, focused on schedule and cost impact." |
| "Set up the thing we talked about" | "Create a new skill folder under plugins/legal/skills/ for the NDA redline checklist we discussed, following the same SKILL.md pattern as how-to-use-factory-ai." |

### Common failure patterns to watch for

- **Topic instead of goal** - describing the subject matter without saying what should
  happen to it.
- **No stated boundary** - not saying what must stay untouched, so Droid has to guess
  and may change more than intended.
- **Hidden multi-step scope** - a request that sounds like one step but is actually
  three or four; call out the steps if you know them.
- **No definition of done** - if you can't say how you'd check the work, say that, and
  ask Droid to propose a way to verify it.
- **Assuming shared context** - referencing "the doc we discussed" without saying which
  one, where it lives, or what changed since last time.

### Mid-task correction beats starting over

If a task drifts off track, correct it in place - "actually, don't touch the CLIN
figures, just fix the total" - rather than abandoning the session and re-explaining
everything from scratch. Droid keeps context within a session.

### Quick template

For anything non-trivial, a prompt can follow this shape:

```
Goal: <what outcome you want>
Constraints: <format / length / audience / deadline / do-not-touch>
Scope: <one step or several; which files/systems>
Done when: <how you'll know it's right>
```

## Success criteria

The person leaves able to name the four elements (goal, constraints, scope, done-when)
and has seen at least one before/after example close enough to their own work to be
useful.
