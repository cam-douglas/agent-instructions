# Working memory

## Durable directives

- Execute agent-capable work directly; do not delegate routine implementation or investigation to the user.
- Use the sequential planning lifecycle for new projects and major implementations: phase 0 maps the full project, each later phase plan is generated only after the previous phase is implemented and verified, and closure produces `docs/plans/final_implementation_checklist.md`.
- Defer non-blocking human-only actions and missing credential values to the final phase while completing all possible code, configuration, adapters, tests, documentation, and environment-variable wiring first.
- Read `/AGENTS.md` once per session, reuse it while it remains in context, re-read only after change or context loss, and route detailed instructions through `/INSTRUCTIONS.md`.
- Use `/launch-pipeline` and `/instructions/LAUNCH.md` only for explicitly requested complete lifecycle execution; natural-language project planning can load the planning instructions without launching that pipeline.
- Run read-only preflight when the host permits it. Bootstrap only when materialization or installation/repair is needed and implementation is authorized; Ask and Plan remain read-only. Already-ready workspaces need no repeated bootstrap.
- Use formal role routing and workstream artifacts when multi-role delivery or consequential release gates require them. Ordinary bounded changes and reviews need no six-role matrix or exhaustive role plans.
- Treat prompts and role identities as guidance, not production authorization; deterministic policy and external access controls govern sensitive actions.
- Never store passwords, tokens, private keys, or secret values in agent markdown, plans, memories, logs, or templates.
- Git writes must use `Cursor Agent <cursoragent@noreply.github.com>` or a GitHub noreply address. Never use a private inbox or `git config` identity changes. Canonical procedure: `/skills/git-safety/SKILL.md`.

## Memory role

This file is a concise durable memory and index. Store only standing directives, stable decisions, high-level architecture notes, and links to canonical detail.

Operational history belongs in `/memory/memories/YYYY-MM-DD-continuation.md` or a topic-specific memory. Unresolved issues belong in `blockers/`; exact procedures belong in `runbooks/`; stable repeatable procedures belong in `/skills/`.

## System index

- Operating contract: `/AGENTS.md`
- Startup: `/BOOTSTRAP.md` and `/scripts/bootstrap.sh`
- Instruction router: `/INSTRUCTIONS.md`
- Product lifecycle launcher: `/instructions/LAUNCH.md` and `/skills/launch-pipeline/SKILL.md`
- Project planning: `/instructions/PROJECT_PLANNING.md`
- Product strategy: `/instructions/STRATEGY.md`
- Sub-agent orchestration: `/instructions/SUBAGENTS.md`
- Canonical roles and stage gates: `/instructions/ROLES.md`
- Native role adapters: `/agents/`
- Live state: `/STATE.md`
- Plans: `docs/plans/`
- Strategic blueprints: `docs/blueprints/`
- Decisions: `docs/decisions/`
- Task workstreams and role handoffs: `docs/workstreams/`
- External governance setup: `docs/handover/agent-governance-operator-setup.md`
- Skills: `/SKILLS.md` and `/skills/`
- Git safety: `/skills/git-safety/SKILL.md`
- Tools: `/TOOLS.md`
- Active blockers: `/memory/blockers/`
- Runbooks: `/memory/runbooks/`
- Agent workspace layout: `/memory/runbooks/agent-workspace.md`
- Bootstrap procedure: `/memory/runbooks/agent-config-bootstrap.md`

## Existing workflow references

- Vercel: `/skills/vercel-deploy-workflow/SKILL.md` and `/memory/runbooks/vercel-workflow.md`
- Supabase: `/skills/supabase-linked-migrations/SKILL.md` and `/memory/runbooks/supabase-cli-macos.md`
