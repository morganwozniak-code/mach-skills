# Mach Skills - Project Checklist

Tracking doc for building out the Mach skills marketplace. Update this as work
progresses; treat it as the single source of truth for status, not the chat history
that produced it.

Status legend: `Done` / `Not started` / `Blocked`

## Phase 1 - Foundation

| Task | Description | Status |
| :--- | :--- | :--- |
| Decide on structure | Chose department-tab plugins under one marketplace repo (`plugins/legal`, `plugins/operations`, etc.) instead of one flat skill list. | Done |
| Decide on skill format | Chose agnostic markdown content wrapped in a thin Factory `SKILL.md` (name + description + instructions) so content survives a future tool switch. | Done |
| Scaffold repo | Created `.factory-plugin/marketplace.json`, `plugins/` folder tree, and `README.md` describing the project. | Done |
| Verify local install | Ran `droid plugin marketplace add` and `droid plugin install` against the local repo to confirm the marketplace format actually works before building more content. | Done |
| Push to GitHub | Created `morganwozniak-code/mach-skills` and pushed the initial scaffold. | Done |

## Phase 2 - Company-wide skills

| Task | Description | Status |
| :--- | :--- | :--- |
| `how-to-use-factory-ai` | Core-concepts skill: what Droid is, vocabulary (session/skill/subagent/connector/autonomy), when to use what, and data-handling rules (ITAR/CUI/secrets). | Done |
| `writing-good-prompts` | Teaches the goal/constraints/scope/success-criteria framework for prompting, with before/after examples and a copy-paste template. | Done |
| `factory-connectors-and-capabilities` | How to connect third-party apps (Slack, Jira, etc.), what to do if an app isn't available, and a survey of Factory's broader capability set. | Done |
| `when-to-escalate-to-a-human` | Decision rules for when Droid should stop and hand off to a person: hard-stop triggers (classified/ITAR/CUI, irreversible actions, out-of-authority decisions) and who to route to. | Not started |
| `data-classification-quick-reference` | Fast lookup table (public / internal / CUI / ITAR / classified) with a one-line rule per tier for what's safe to put in a Droid session. | Not started |
| `how-to-request-a-new-skill` | Operationalizes the contribution workflow already referenced in skill #1: how to propose, draft, and get a skill reviewed and merged. | Not started |
| `reviewing-ai-generated-work-before-you-ship-it` | Checklist mindset for treating Droid output like a junior teammate's draft before sending/committing/filing it. | Not started |

## Phase 3 - Public marketplace decision

| Task | Description | Status |
| :--- | :--- | :--- |
| Decide repo visibility | Chose to make the repo public so it's browsable with no GitHub account and installable by anyone, not just Mach employees. | Done |
| Fix licensing | Switched every `license: UNLICENSED` field (plugin manifest + all `SKILL.md` frontmatter) to `MIT`, since `UNLICENSED` technically grants no reuse rights. | Done |
| Add LICENSE file | Added a root MIT `LICENSE` file matching the manifest/frontmatter license fields. | Done |
| Update README for external users | Rewrote install instructions for outside users, added ref/commit pinning guidance, and added an explicit "this repo is public - no secrets or internal detail" rule to the contribution steps. | Done |
| Decide department content's home | Open decision: do Legal/MechE/Ops/Programs skills go in this same public repo, or a separate private companion repo? This blocks Phase 4. | Blocked |

## Phase 4 - Department skills

| Task | Description | Status |
| :--- | :--- | :--- |
| Resolve public-vs-private home | Must be decided before any department skill work starts (see Phase 3 blocker above). | Blocked |
| Legal: first skill | Draft the first Legal-department skill (e.g. contract-review checklist or NDA redline flags - not yet chosen). | Not started |
| Legal: scaffold plugin | Create `plugins/legal/.factory-plugin/plugin.json` and `skills/` folder once the first skill content exists. | Not started |
| Mechanical Engineering: first skill | Draft the first MechE-department skill. | Not started |
| Mechanical Engineering: scaffold plugin | Create `plugins/mechanical-engineering/` plugin structure. | Not started |
| Operations: first skill | Draft the first Operations-department skill. | Not started |
| Operations: scaffold plugin | Create `plugins/operations/` plugin structure. | Not started |
| Programs: first skill | Draft the first Programs-department skill. | Not started |
| Programs: scaffold plugin | Create `plugins/programs/` plugin structure. | Not started |
| Assign department reviewers | Identify one owner per department plugin responsible for reviewing and approving PRs to their skills. | Not started |

## Phase 5 - Org rollout

| Task | Description | Status |
| :--- | :--- | :--- |
| Move repo into Mach's GitHub org | Currently under a personal account (`morganwozniak-code`); move to an org so access follows normal employee onboarding/offboarding. | Not started |
| Confirm Factory org-admin access | Identify who at Mach can edit Factory org-managed settings to register the marketplace company-wide. | Not started |
| Register marketplace org-wide | Add the repo to `extraKnownMarketplaces` in org-managed settings so it's available to every Droid user automatically. | Not started |
| Choose pre-installed plugins | Decide which plugins go in `enabledPlugins` (installed for everyone automatically) versus left as opt-in installs. | Not started |
| Announce the rollout | Decide where/how to tell the company this exists - all-hands, Slack, onboarding docs, etc. | Not started |

## Phase 6 - Optional: browsable site

| Task | Description | Status |
| :--- | :--- | :--- |
| Decide if still needed | Droid users already get this content via `/plugins`; decide if a separate human-readable site is still worth building for non-Droid-users. | Not started |
| Pick a static site generator | Choose MkDocs, Docusaurus, or a small custom script to render `SKILL.md` files as pages. | Not started |
| Build department tabs | Generate site navigation/tabs from the `plugins/*` folder structure automatically. | Not started |
| Set up CI deploy | GitHub Action to rebuild and redeploy the site on every push to `main`. | Not started |
| Decide hosting | Public site is fine while the repo is public; revisit if a private companion repo for department content gets created later. | Not started |

## Phase 7 - Governance and maintenance

| Task | Description | Status |
| :--- | :--- | :--- |
| Write contribution/review process doc | Short doc spelling out who approves what and how a PR gets merged, beyond what's already in `README.md`. | Not started |
| Set a versioning convention | Decide if/when to cut tagged releases (e.g. `v1.0.0`) for people who want to pin instead of tracking `main`. | Not started |
| Set a review cadence | Recurring check (e.g. quarterly) to catch skills that have gone stale or out of date. | Not started |
| Track adoption | Optional: monitor who's installed what if usage data becomes useful at scale. | Not started |

---

**Repo**: https://github.com/morganwozniak-code/mach-skills (public, MIT licensed)
