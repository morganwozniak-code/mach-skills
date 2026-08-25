---
name: how-to-use-factory-ai
description: Explains how Factory/Droid works and how to use it effectively at Mach - core concepts, prompting practices, when to reach for skills vs subagents vs slash commands, and data-handling rules. Use when someone asks how Factory or Droid works, how to write a better prompt, or what they're allowed to paste into a Droid session.
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

# How to Use Factory/AI at Mach

This is the starting point for anyone using Factory (Droid) at Mach, regardless of
department. Read this before your first real session, and point new hires here.

## Instructions

When this skill is invoked (directly via `/how-to-use-factory-ai` or because someone
asked a "how do I use this" question), walk them through the sections below in order,
tailoring depth to what they actually asked. Don't dump the whole document if they
asked one narrow question - answer that, then mention the rest exists.

### 1. What Droid is

Droid is an AI agent that can read/write files, run commands, search the web, and call
connected tools (Jira, Slack, Confluence, GitHub, etc.) on your behalf inside a session.
It is not a search engine and not autocomplete - it can take multi-step action, so being
specific about what you want matters more than with a chatbot.

### 2. Core building blocks (know the vocabulary)

- **Session**: one conversation with Droid, scoped to a task.
- **Skill**: a reusable, packaged workflow (`SKILL.md`) Droid can find and follow for a
  recurring task - e.g. "how to file a compliance-review ticket." This marketplace
  (`mach-skills`) is a catalog of department-specific and company-wide skills.
- **Subagent / custom droid**: a specialized helper Droid delegates a bounded piece of
  work to, with its own instructions and tools.
- **Connector**: a bridge to an external tool (Slack, Jira, Confluence, GitHub) so Droid
  can read or act on real company data with your existing permissions - it does not
  bypass access controls.
- **Autonomy level**: how much Droid can do before it stops and asks you to approve
  (Off / Low / Medium / High). Higher autonomy is faster but means fewer checkpoints -
  match it to how reversible the task is.

### 3. Writing a good prompt

- Say the **goal**, not just the topic. "Summarize this contract's termination clauses"
  beats "look at this contract."
- Give **constraints up front**: format, length, audience, deadline, what NOT to touch.
- If the task has multiple steps, say so - Droid will plan across them rather than
  guessing scope from a one-liner.
- If you're not sure what you want yet, say that. Droid can ask clarifying questions
  instead of assuming.
- Correct course mid-task rather than starting over - Droid keeps context.

### 4. When to reach for what

| You want to... | Use |
| :--- | :--- |
| Get something done once, informally | Just ask in a session |
| Reuse a known department procedure every time it comes up | A **skill** from this marketplace |
| Hand off a large, semi-independent chunk of work | A **subagent** |
| Pull real data from Slack/Jira/Confluence/GitHub | A **connector** (must already be connected) |
| Run the same multi-step task on a schedule or trigger | Ask the platform team about automations |

### 5. Data-handling rules (read this one carefully)

Mach handles sensitive and controlled information. Before pasting anything into a Droid
session or asking it to fetch something:

- Never paste ITAR/CUI/export-controlled content, classified information, or customer
  proprietary data into a session unless you've confirmed with your department lead
  that this specific workflow and environment is approved for it.
- Don't put secrets, API keys, or credentials in a prompt, skill file, or committed
  file - ever. Treat anything you type as something that could end up in a log or a
  shared skill.
- If a task seems like it needs classified or export-controlled material to complete,
  stop and ask your department's security point of contact before proceeding, rather
  than assuming the AI environment is cleared for it.
- Skills in this marketplace must never contain secrets, real customer data, or
  internal-only identifiers - link to the source of truth instead of copying it in.

### 6. Where to find department skills

Browse `/plugins` inside Droid to see what's installed, or look at the `mach-skills`
repo directly (department folders under `plugins/`) to see what exists before asking
your platform team to build something new.

### 7. Getting help

- Something look wrong or unsafe? Stop and ask a human before proceeding.
- Want a new skill for your department? Open a PR against `mach-skills` or ask the
  platform team to help draft one - see that repo's `README.md` for the process.

## Success criteria

The person leaves knowing: what Droid is, the five vocabulary terms above, one concrete
prompting tip they'll actually use, and the one data-handling rule that matters most for
their situation.
