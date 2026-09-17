# 2026-09-17 continuation

## Source-tree consolidation

- Folded duplicate root `docs/`, `.github/`, `.githooks/`, `.agents/`, `AGENTS.md`, and `.cursorignore` into `.cursor` templates/payloads.
- Merged the GitHub landing README with `.cursor/README.md`. The repository now has a single content folder: `.cursor/`.
- Template-development history moved to `/memory/memories/template-source/`.

## Consumer overlay

- Installed this `.cursor` tree into 21 project folders under `/Users/camdouglas`.
- Preserved each consumer's `STATE.md`, `memory/`, `config/settings.json`, extra rules, extra runbooks, extra skills, and unique `USER.md` preferences via `.cursor/PROJECT.md`.
- Retired always-on routing rules (`00-read-*-context-first`, `01-per-turn-read-contract`, `core-operating-context`, `instruction-routing`, `root-canonical`, `skills-file`, `tools-file`, `working-memory`, `state-and-compactification`) in favor of `00-core-routing.mdc`.
- `validate-launch.mjs` now treats `PROJECT.md` directory routes as covering nested files, including names that contain parentheses.
