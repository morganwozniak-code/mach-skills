# Mach Skills

Mach's internal catalog of approved Droid skills, organized by department. This is a
Factory "internal plugin marketplace" - a private Git repo of skills that any Droid
user at Mach can browse and install without needing a new license or seat.

## Why this exists

- **One place** for department know-how (Legal, Mechanical Engineering, Operations,
  Programs, etc.) instead of scattered docs and tribal knowledge.
- **Vendor-agnostic content**: every skill's actual instructions are written as plain
  markdown. The only Factory-specific part is the thin `SKILL.md` frontmatter
  (`name`, `description`) that tells Droid when to use it. If Mach ever changes AI
  tools, the content survives - only the wrapper needs to change.
- **No per-seat cost to browse**: skills are just files in a private repo. Reading them
  doesn't require a GitHub account or a Factory license - only contributing does.
- **Governed like code**: every change to a skill is a pull request, reviewable and
  versioned like any other change.

## Structure

```
mach-skills/
  .factory-plugin/marketplace.json   # marketplace manifest - lists every plugin below
  plugins/
    company-wide/                    # skills every employee should have
      skills/how-to-use-factory-ai/
    legal/                           # (coming soon)
    mechanical-engineering/          # (coming soon)
    operations/                      # (coming soon)
    programs/                        # (coming soon)
```

Each top-level folder under `plugins/` is a Factory "plugin" - a `.factory-plugin/plugin.json`
manifest plus a `skills/` folder containing one or more skills (each its own
`SKILL.md`).

## Using this marketplace in Droid

To try it locally before any org-wide rollout:

```bash
droid plugin marketplace add /Users/morganwozniak/mach-skills
droid plugin install company-wide@mach-skills --scope user
```

Once pushed to GitHub, anyone with repo access can instead add it by URL:

```bash
droid plugin marketplace add https://github.com/morganwozniak-code/mach-skills
droid plugin install company-wide@mach-skills --scope user
```

## Rolling this out to everyone (no manual install needed)

An org admin can register the marketplace once in Factory's org-managed settings so it
is available to every user automatically, with critical skills pre-installed:

```json
{
  "extraKnownMarketplaces": {
    "mach-skills": {
      "source": { "source": "github", "repo": "your-org/mach-skills" }
    }
  },
  "enabledPlugins": {
    "company-wide@mach-skills": true
  }
}
```

This repo currently lives under a personal GitHub account for prototyping. Before an
org-wide rollout, move it into Mach's GitHub org so access follows normal employee
offboarding/permissions.

## Adding a new skill

1. Pick (or create) the department folder under `plugins/`.
2. Add a new folder under that plugin's `skills/` with a `SKILL.md`:
   - `name`: lowercase, hyphenated identifier.
   - `description`: what it does and when Droid (or a person) should use it. This is
     the only text Droid sees before deciding the skill is relevant, so be specific.
   - Body: step-by-step instructions, written so a human could also follow them
     without Droid.
3. Never put secrets, customer data, classified/export-controlled content, or
   internal-only identifiers in a skill file. Link to the source of truth instead.
4. Open a pull request. The relevant department owner reviews and merges.

## Status

- [x] `company-wide` plugin scaffolded with `how-to-use-factory-ai`
- [ ] `legal` plugin
- [ ] `mechanical-engineering` plugin
- [ ] `operations` plugin
- [ ] `programs` plugin
- [ ] Move repo into Mach's GitHub org
- [ ] Register marketplace in org-managed settings for automatic rollout
- [ ] Optional: static docs site for non-Droid-user browsing
