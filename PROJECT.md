# Mach Skills Marketplace - Project Checklist

This tracks the work of building the marketplace itself: structure, decisions,
distribution, governance. It does not track which individual skills get written -
that's a separate, ongoing backlog (see `SKILLS_BACKLOG.md`) that grows over time and
isn't part of "finishing" this project.

Status legend: `Done` / `Not started` / `Blocked` / `Decision needed`

## 1. Foundational setup

| Task | Description | Status |
| :--- | :--- | :--- |
| Choose the structure | One marketplace repo, with each department as its own "plugin" folder (`plugins/legal`, `plugins/operations`, etc.) so Droid's `/plugins` UI shows department-like tabs. | Done |
| Choose the skill format | Agnostic markdown content wrapped in a thin Factory `SKILL.md` (frontmatter + instructions), so content survives a future AI-tool change. | Done |
| Scaffold the repo | Created `.factory-plugin/marketplace.json`, the `plugins/` tree, and `README.md`. | Done |
| Prove it actually works | Registered the repo as a local Droid marketplace and installed a plugin from it, before writing more content, to validate the format. | Done |
| Push to GitHub | Repo created and pushed as `morganwozniak-code/mach-skills`. | Done |

## 2. Visibility and licensing decisions

| Task | Description | Status |
| :--- | :--- | :--- |
| Decide repo visibility | Chose public: browsable with no GitHub account, installable by anyone. | Done |
| Fix the license | Changed `UNLICENSED` (grants no reuse rights) to `MIT` in the plugin manifest and every skill's frontmatter. | Done |
| Add a LICENSE file | Root MIT `LICENSE` added to match. | Done |
| Update README for outside users | Install instructions, ref/commit pinning guidance, and an explicit "this repo is public - no secrets or internal detail" rule. | Done |

## 3. Governance decisions still open

| Task | Description | Status |
| :--- | :--- | :--- |
| Public vs. private home for department content | Should Legal/MechE/Ops/Programs skills live in this same public repo, or move to a separate private companion repo if any content isn't appropriate to share externally? Blocks starting department plugins. | Decision needed |
| Who owns/reviews each department plugin | Need one named reviewer per department who approves PRs to their `plugins/<dept>/` folder - otherwise anyone's PR sits unreviewed. | Decision needed |
| Contribution process doc | A short written process (propose -> draft -> review -> merge) beyond the informal steps already in README, so it doesn't depend on asking the platform team each time. | Not started |
| Versioning convention | Decide whether to cut tagged releases (`v1.0.0`, `v1.1.0`, ...) so people who want stability can pin instead of tracking `main`. | Decision needed |
| Review cadence | Decide a recurring cycle (e.g. quarterly) to catch skills that go stale or reference outdated processes/tools. | Not started |

## 4. Org-wide rollout

| Task | Description | Status |
| :--- | :--- | :--- |
| Move repo into a Mach GitHub org | Currently under a personal account; move to an org so access follows normal employee onboarding/offboarding rather than one person's account. | Not started |
| Identify who can edit Factory org-managed settings | Need to know who at Mach has org-admin access in Factory to register a company-wide marketplace. | Decision needed |
| Register the marketplace org-wide | Add the repo under `extraKnownMarketplaces` in org-managed settings so every Droid user sees it automatically, without each person manually adding it. | Not started |
| Decide what's pre-installed vs. opt-in | Choose which plugins go in `enabledPlugins` (installed for everyone automatically on first session) versus staying available-but-optional. | Decision needed |
| Decide how to announce it | Pick the channel/format for telling the company this exists - all-hands, Slack post, onboarding docs, etc. | Decision needed |

## 5. Optional: browsable site for non-Droid-users

| Task | Description | Status |
| :--- | :--- | :--- |
| Decide if it's actually needed | Droid users already get this content via `/plugins` with zero setup; a site only adds value for people who don't use Droid at all. Worth confirming there's real demand before building it. | Decision needed |
| Choose a static site generator | MkDocs, Docusaurus, or a small custom script that renders `SKILL.md` files as pages. | Not started |
| Auto-generate department tabs | Site navigation should be built from the `plugins/*` folder structure, not hand-maintained, so it can't drift out of sync. | Not started |
| Set up CI to deploy on push | GitHub Action rebuilds and redeploys the site whenever `main` changes. | Not started |
| Decide hosting | Public hosting is fine while the repo itself is public; revisit if department content ever moves to a private companion repo. | Decision needed |

## 6. Ongoing maintenance (not a one-time finish line)

| Task | Description | Status |
| :--- | :--- | :--- |
| Track adoption | Optional: know who's installed what, if usage data becomes useful once this scales past a handful of people. | Not started |
| Periodic content audit | Pair with the review cadence above - actually check skills still match current tools/process, not just that they exist. | Not started |
| Retire or update stale skills | Process for what happens when a skill's guidance is outdated - edit in place, version-bump, or deprecate with a note pointing to the replacement. | Not started |

---

**Repo**: https://github.com/morganwozniak-code/mach-skills (public, MIT licensed)
