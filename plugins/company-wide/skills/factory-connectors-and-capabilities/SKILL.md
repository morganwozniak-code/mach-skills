---
name: factory-connectors-and-capabilities
description: Explains how to connect third-party apps (Slack, Jira, Confluence, GitHub, etc.) to Factory/Droid, and surveys the broader Factory capability set so people use it to their advantage instead of only chatting. Use when someone asks how to connect an app, why a tool isn't available, or what else Factory can do beyond a basic Q&A session.
allowed-tools: []
enabled: true
user-invocable: true
disable-model-invocation: false
license: UNLICENSED
compatibility: droid
version: 1.0.0
metadata:
  owner: platform-team
  department: company-wide
---

# Factory Connectors and Capabilities

Most people only ever use Droid as a chat window. The bigger wins come from connecting
it to real company tools and reaching for the right capability instead of always
starting a plain conversation.

## Instructions

When this skill is invoked, cover connecting an app first if that's what was asked,
then use the capability survey to point out one or two things the person probably
isn't using yet that would help their actual workflow.

### 1. What a connector is

A connector lets Droid read or act on a real third-party app - Slack, Jira,
Confluence, GitHub, Linear, Notion, Sentry, Google Workspace, and others - using your
own permissions. It is not a shared company credential; each person authorizes their
own connection, scoped to them and to the active organization.

### 2. How to connect an app

**In the Factory App:**

1. Open **Settings -> Connectors**.
2. Search the catalog or browse featured/full lists. If Mach restricts which apps are
   available org-wide, only approved ones show up here.
3. Select **Connect**. A browser tab opens the app's own sign-in and permission
   approval screen - review what access it's requesting before approving.
4. Return to your session. Droid picks up the new connector automatically when a task
   needs it; you don't need to reference it by name.

**From inside a chat session**, you can just ask in plain language:

```
Connect my Jira account so you can look up the status of this ticket.
```

Droid returns an authorization link, you approve it in the browser, then tell Droid to
continue. (This only works in an interactive session - not in unattended/scripted
`droid exec` runs, which need the connection set up ahead of time in the Factory App.)

### 3. If the app you want isn't available

Two possibilities:

- **It's in Factory's catalog but disabled for Mach.** An Owner/Manager controls this
  under Enterprise Controls -> Connectors. Ask your platform team to enable it if
  there's a real business need.
- **It's not in Factory's catalog at all.** Use "Suggest a connector" in Settings ->
  Connectors, or ask the platform team about wiring it up as an MCP server instead
  (the right fit for self-hosted or custom internal tools).

Never put passwords, API keys, or tokens into a connector suggestion or into a chat
message - always use the app's own authorization flow.

### 4. Managing your connections

- **Disconnect** anytime from Settings -> Connectors - this only removes your own
  connection, not the app's availability for teammates.
- Disconnect promptly if you roll off a project that required a connection you no
  longer need, or if you're not sure the access is still appropriate.
- Connector calls still go through the same approval rules as everything else: read-only
  actions run automatically at your autonomy level, writes/destructive actions ask for
  confirmation first.

### 5. The rest of what Factory can do (use this to your advantage)

Most of the value people miss isn't connectors - it's not knowing these exist:

| Capability | What it's for | When to reach for it |
| :--- | :--- | :--- |
| **Connectors** | Read/act on Slack, Jira, Confluence, GitHub, etc. with your own access | Any task that needs real company data instead of a copy-paste |
| **Skills** (this marketplace) | Reusable, department-owned procedures Droid can follow every time | A recurring task your team does the same way repeatedly |
| **Subagents / custom droids** | Delegate a bounded chunk of work to a specialized helper | Large or multi-part tasks where one focused pass per piece is cleaner |
| **MCP servers** | Connect custom, private, or self-hosted tools Factory doesn't have a built-in connector for | Internal systems, self-hosted GitLab, proprietary databases |
| **Missions** | Plan and execute a large multi-step project with structured checkpoints | Something too big for a single session - a rollout, a migration, a multi-week build |
| **Autonomy levels** | Control how much Droid does before stopping to ask | Dial up for low-stakes/reversible work, dial down for anything sensitive |
| **Slash commands** | Quick, repeatable one-liners (`/skills`, `/plugins`, `/review`, etc.) | Anything you'd otherwise re-type the same instructions for |

### 6. Practical ways to use this well

- Connect the two or three apps you actually touch daily (e.g. Jira + Slack) rather
  than everything in the catalog - fewer, well-used connections beat many unused ones.
- Chain connectors in one request instead of doing each step by hand: "read the
  unresolved thread in #contracts-help, summarize it, and file a Jira ticket with that
  summary" is one ask, not three.
- If you catch yourself doing the same multi-step thing for the third time, that's a
  signal to propose a skill for it (see `how-to-use-factory-ai` for the process),
  not to keep doing it manually.
- Before connecting an app, glance at the permissions it's requesting during
  authorization - the third-party app's permission screen is the real boundary on what
  it can read or change, not Factory.

## Success criteria

The person leaves knowing how to connect an app themselves, what to do if an app isn't
available, and can name at least one Factory capability beyond plain chat that's
relevant to their own work.
