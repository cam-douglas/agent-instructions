# Agent Instructions

A portable, agent-agnostic control plane for coding agents. Drop it into any repository to give your agent consistent operating rules, phased project planning, memory, skills, and runbooks.

This repo ships the files under `.cursor/` as the reference layout. **Rename that folder** to match your agent before use.

## Quick start

### 1. Copy into your project

Copy this entire folder into your project repository root:

```text
your-project/
  .cursor/          ← rename in step 2
  src/
  package.json
  ...
```

### 2. Rename for your agent

Rename `.cursor` to whatever your coding agent expects:

| Agent / tool | Typical folder name |
|---|---|
| Cursor | `.cursor` (default — no rename needed) |
| Claude Code | `.claude` |
| OpenClaw | `.openclaw` |
| Hermes | `.hermes` |
| Other | `.your-agent` or follow your tool's docs |

The contents stay the same. Only the directory name changes.

> **Cursor users:** keep the folder as `.cursor`. The `rules/*.mdc` files are loaded automatically with `alwaysApply: true`.

> **Other agents:** point your agent at `AGENTS.md` inside the renamed folder (system prompt, project instructions, or rules file — whatever your tool supports). The `rules/` files are concise enforcement snippets; load them if your agent can ingest rule files, or rely on `AGENTS.md` alone.

### 3. Bootstrap the workspace

From your project root, run:

```bash
bash .your-agent/scripts/bootstrap.sh
```

Replace `.your-agent` with your actual folder name. The script is idempotent — safe to run on every new session. It creates `docs/` scaffolding (plans, blueprints, decisions, handover) without overwriting existing project files.

### 4. Start your agent

On the first message of a new session, tell your agent:

> Read `AGENTS.md` in the agent config folder, run `scripts/bootstrap.sh`, then follow the per-turn read contract.

The agent will handle startup from there.

## What you get

```text
<agent-config-root>/
  AGENTS.md              # Canonical operating contract — start here
  BOOTSTRAP.md           # Session startup procedure
  INSTRUCTIONS.md        # Routes to detailed task modes
  USER.md                # Your durable preferences (edit this)
  STATE.md               # Live objective, phase, plan, blockers
  SKILLS.md + skills/    # Repeatable procedures (Vercel, Supabase, etc.)
  TOOLS.md               # Capability registry
  instructions/          # Project planning, strategy, sub-agents
  memory/                # Durable memory, blockers, runbooks, continuations
  rules/                 # Always-applied enforcement (Cursor-native .mdc)
  scripts/bootstrap.sh   # Idempotent workspace materialization
  templates/             # Phase plan and docs templates
  config/settings.json   # Optional host-specific settings
```

After bootstrap, your repo also gets:

```text
docs/
  plans/                 # Sequential phase plans + final checklist
  blueprints/            # Product/strategy outputs
  decisions/             # Architecture decision records
  handover/              # Operational handovers
```

## How it works

1. **`AGENTS.md`** defines precedence, autonomy limits, phased lifecycle, and the per-turn read contract.
2. **`INSTRUCTIONS.md`** activates detailed modes (project planning, strategy, sub-agents) only when needed.
3. **`STATE.md`** tracks what is in flight so work survives context loss between sessions.
4. **`memory/`** stores blockers, runbooks, and dated continuation logs — not secrets.
5. **`skills/`** holds stable, repeatable multi-step procedures promoted from runbooks.

For a new project or major feature, the agent creates `docs/plans/phase_0_foundations_plan.md` first, then generates one phase plan at a time until a `final_implementation_checklist.md` closes remaining human-only work.

## Customize for yourself

Edit these files to match your workflow:

- **`USER.md`** — standing directives, platform preferences, deployment defaults
- **`STATE.md`** — reset or resume active work
- **`memory/MEMORY.md`** — durable decisions and architecture notes
- **`config/settings.json`** — optional editor/host settings

Do not store passwords, tokens, or API keys in any of these files.

## Included skills

| Skill | Purpose |
|---|---|
| `vercel-deploy-workflow` | Deploy Next.js to Vercel via Git or CLI |
| `supabase-linked-migrations` | Ship SQL migrations to a linked Supabase project |

Add your own under `skills/<skill-id>/SKILL.md` and register them in `SKILLS.md`.

## License

MIT — see [LICENSE](LICENSE).
