# Copilot Instructions — Lum0s Solutions (Organization-Wide)

These instructions apply to ALL repositories in the Lum0s-Solutions organization.
Repository-specific instructions in each repo's `.github/copilot-instructions.md` take precedence.

## Organization Context

**Lum0s Solutions** — AI-native offensive security infrastructure startup.
**Founder:** Ty Limoges — SNHU cybersecurity, SBIR defense track.
**Primary project:** Syn_OS — sovereign AI-assisted Cognitive Hyper-OS (Arch Linux, 111 Rust crates).
**AI orchestration:** LumOs Virtual Enterprise — 20-agent system governed by constitutional framework.

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

## Infrastructure Context

- Bare metal homelab — no cloud infrastructure
- Tailscale mesh networking (WireGuard backbone)
- ARCANUM: 8-node encrypted mesh on VLAN 66
- Build oracle: the10thLayerVoidness (EndeavourOS, limited resources)
- Dev desktop: THEDARKNESS (Win10, i7-4790/16GB, Parrot WSL)

## AI Orchestration Awareness

When working in any Lum0s repo, be aware that:
- GitHub Copilot is one of 4 AI tools in the stack (Claude Code, Kilo Code, Copilot, Gemini)
- Copilot's role: inline completions and tab-complete. Don't compete with Claude Code's orchestration.
- Agent definitions live in `lumos-claude-config/agents/`
- Constitutional governance rules live in `lumos-claude-config/a2a/constitution.md`
- The Busytown/Rapture alignment axis governs agent behavior across the enterprise

## PR Standards

- Every PR needs a security checklist (no secrets, no unsafe, dependencies audited)
- Destructive changes require explicit human approval
- Agent/governance changes require constitutional alignment check
- Use the PR templates defined in each repository
