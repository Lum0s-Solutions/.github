# Copilot Instructions — Lum0s Solutions (Organization-Wide)

These instructions apply to ALL repositories in the Lum0s-Solutions organization.
Repository-specific instructions in each repo's `.github/copilot-instructions.md` take precedence.

## Organization Context

**Lum0s Solutions** — AI-native offensive security studio.
**Primary project:** Syn_OS — a sovereign, AI-assisted cognitive hyper-OS built on Arch Linux, written primarily in Rust.
**Approach:** development is structured around a governed, multi-agent workflow under a constitutional framework — the human is always the final authority.

## Universal Coding Standards

- Conventional Commits enforced across all repos: `type(scope): description`
- Types: `feat`, `fix`, `security`, `docs`, `refactor`, `test`, `ci`, `chore`
- No emojis in code, comments, commit messages, or documentation
- No hardcoded secrets — ever. Use environment variables or secret management.
- Line endings: LF (Unix-style) everywhere. Never CRLF.
- Final newline: always include in every file.

## Security-First Principles

- All code changes go through security review before merge
- Dependencies must be audited before adoption (cargo deny, pip audit, npm audit)
- No `unsafe` code without documented justification and SAST audit
- No force-push to default branches
- No `--no-verify` flags in any context
- Secrets exposure = immediate rotation + incident report

## Language Preferences

- **Rust** is the primary language (Syn_OS). 2021 edition, `clippy::pedantic`, `thiserror`/`anyhow`.
- **Bash** for scripting. Always `set -euo pipefail`. Shellcheck clean.
- **Python** when Rust is overkill. Type hints required, pathlib over os.path.
- **NEVER suggest:** Kubernetes, Helm, cloud providers, OpenSSL, native-tls, `todo!()` stubs.

## AI Orchestration Awareness

When working in any Lum0s repo, be aware that:
- GitHub Copilot is one of several AI tools in the stack.
- Copilot's role: inline completions and tab-complete — it complements, not replaces, the primary orchestration workflow.
- Agents operate under a written constitutional governance framework; agent/governance changes require an alignment check.

## PR Standards

- Every PR needs a security checklist (no secrets, no unsafe, dependencies audited)
- Destructive changes require explicit human approval
- Agent/governance changes require a constitutional alignment check
- Use the PR templates defined in each repository
