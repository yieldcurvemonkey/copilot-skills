# copilot-skills

Curated, vetted agent skills (`SKILL.md` format) for GitHub Copilot in VS Code (also work in Claude Code).

## Use

Clone, then either:

- copy/clone into `~/.copilot/skills/` (personal, all workspaces), or
- point VS Code setting `chat.agentSkillsLocations` at `<clone>/skills`.

Update by hand only: diff upstream, review, then copy. Never auto-sync.

## Skills

| Skill | Upstream | Version copied |
|---|---|---|
| ponytail | [DietrichGebert/ponytail](https://github.com/DietrichGebert/ponytail) | 4.10.0 (e3ba2aa) |
| caveman | [JuliusBrussee/caveman](https://github.com/JuliusBrussee/caveman) | plugin cache 24e6ee9ea827 |
| karpathy-guidelines | [forrestchang/andrej-karpathy-skills](https://github.com/forrestchang/andrej-karpathy-skills) | 1.0.0 (2c60614), MIT |
| verification-before-completion | [obra/superpowers](https://github.com/obra/superpowers) | 7.0.0 |
| systematic-debugging | obra/superpowers | 7.0.0 |
| test-driven-development | obra/superpowers | 7.0.0 |
| receiving-code-review | obra/superpowers | 7.0.0 |
| doubt-driven-development | [addyosmani/agent-skills](https://github.com/addyosmani/agent-skills) | installed 2026-09-26 |
| interview-me | addyosmani/agent-skills | installed 2026-09-26 |
| constraint-driven-development | addyosmani/agent-skills | installed 2026-09-26 |
| source-driven-development | addyosmani/agent-skills | installed 2026-09-26 |
| incremental-implementation | addyosmani/agent-skills | installed 2026-09-26 |

Licenses for upstreams that shipped one are in `licenses/`. agent-skills license not copied locally; check upstream before sharing this repo.

## Review notes (2026-11-01)

- No network calls, destructive commands, or secrets in any file.
- Only executable: `systematic-debugging/find-polluter.sh` (runs `npm test` per file to find a test that leaves state behind).
- Claude-specific references that Copilot ignores or handles loosely:
  - `doubt-driven-development`: mentions Claude Code subagents for the fresh-context review.
  - `systematic-debugging`, `test-driven-development`: cross-links as `superpowers:<name>`.
  - `constraint-driven-development`: mentions `CLAUDE.md` (use `.github/copilot-instructions.md` instead).
- caveman/ponytail auto-activate in Claude Code via a session hook; Copilot has none. For always-on, paste their core rules into `.github/copilot-instructions.md`.
