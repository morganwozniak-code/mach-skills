# Mach Skills - Project Checklist

Tracking doc for building out the Mach skills marketplace. Update this as work
progresses; treat it as the single source of truth for status, not the chat history
that produced it.

## Phase 1 - Foundation

- [x] Decide on structure: department-tab plugins under one marketplace repo
- [x] Decide on format: agnostic markdown content + thin Factory `SKILL.md` wrapper
- [x] Scaffold repo (`.factory-plugin/marketplace.json`, `plugins/`, `README.md`)
- [x] Verify marketplace installs locally (`droid plugin marketplace add` + `install`)
- [x] Push to GitHub (`morganwozniak-code/mach-skills`)

## Phase 2 - Company-wide skills

- [x] `how-to-use-factory-ai` - core concepts, prompting basics, data-handling rules
- [x] `writing-good-prompts` - goal/constraints/scope/success-criteria framework
- [x] `factory-connectors-and-capabilities` - connecting apps, capability survey
- [ ] `when-to-escalate-to-a-human` (proposed, not started)
- [ ] `data-classification-quick-reference` (proposed, not started)
- [ ] `how-to-request-a-new-skill` (proposed, not started)
- [ ] `reviewing-ai-generated-work-before-you-ship-it` (proposed, not started)

## Phase 3 - Public marketplace decision

- [x] Decide: make repo public
- [x] Switch license from UNLICENSED to MIT (plugin manifest + all skill frontmatter)
- [x] Add root `LICENSE` file
- [x] Update README with external-install instructions and pinning guidance
- [ ] Decide: department skills stay in this public repo, or move to a separate
      private companion repo (see Phase 4 - this is a real open decision, not a
      formality)

## Phase 4 - Department skills

- [ ] Decide public-vs-private home for department content (blocks work below)
- [ ] Legal: first skill drafted
- [ ] Legal: plugin scaffolded (`plugins/legal/`)
- [ ] Mechanical Engineering: first skill drafted
- [ ] Mechanical Engineering: plugin scaffolded
- [ ] Operations: first skill drafted
- [ ] Operations: plugin scaffolded
- [ ] Programs: first skill drafted
- [ ] Programs: plugin scaffolded
- [ ] Identify a department owner/reviewer per plugin for PR approval

## Phase 5 - Org rollout

- [ ] Move repo into a Mach GitHub org (currently under personal account)
- [ ] Confirm who has Factory org-admin access to edit managed settings
- [ ] Register marketplace org-wide via `extraKnownMarketplaces`
- [ ] Decide which plugins are `enabledPlugins` (pre-installed for everyone) vs.
      opt-in install
- [ ] Communicate rollout to the company (where/how to announce)

## Phase 6 - Optional: browsable site

- [ ] Decide if a non-Droid-user-facing site is still wanted (nice-to-have, not
      required for Droid users - they get it via `/plugins`)
- [ ] Pick a static site generator (MkDocs / Docusaurus / custom script)
- [ ] Build tabs from `plugins/*` folder structure
- [ ] Set up CI to rebuild + deploy on push to `main`
- [ ] Decide hosting: public site (fine now, repo is public) vs. internal-only later
      if private department content gets added elsewhere

## Phase 7 - Governance and maintenance

- [ ] Write a short contribution/review process doc (who approves what)
- [ ] Decide a versioning/tagging convention (e.g. `v1.0.0` releases) if pinning
      matters for stability
- [ ] Set a periodic review cadence (e.g. quarterly) to catch stale skills
- [ ] Track adoption (who's installed what) if that becomes relevant at scale

---

**Repo**: https://github.com/morganwozniak-code/mach-skills (public, MIT licensed)
