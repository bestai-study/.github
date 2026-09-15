# bestai-study

Utilities and install scripts for [bestai.study](https://bestai.study) — AI tutorials, pricing comparisons, and technical guides.

## Repositories

- **scripts** — tested install scripts for terminal AI coding agents on Ubuntu 24.04.
- **bestai.study** (private, `site/`) — Hugo source for the bestai.study site.

## scripts

Each script installs one terminal AI coding agent on Ubuntu 24.04 LTS (Noble) using the vendor's official installer or repository. Every script passed `bash -n` and was tested end to end in a clean `ubuntu:24.04` Docker container before publishing; the test matrix for each is documented in the matching article on bestai.study.

| Script | Installs | How it works | Options |
|---|---|---|---|
| `install-opencode-ubuntu24.sh` | OpenCode | apt dependencies plus an optional kitty terminal, then the official OpenCode installer in `--binary` mode as your user (binary in `~/.opencode/bin`, PATH updated). | `--version`, `--skip-terminal`, `--no-modify-path` |
| `install-codex-ubuntu24.sh` | Codex CLI (OpenAI) | apt dependencies, a retry-wrapped fetch of the official installer (`chatgpt.com/codex/install.sh`), then the official installer as your user (native binary in `~/.local/bin`, PATH updated). | `--version`; proxy via `HTTPS_PROXY`/`ALL_PROXY`; `CODEX_INSTALLER_URL` mirror override |
| `install-claude-code-ubuntu24.sh` | Claude Code (Anthropic) | apt dependencies, download and fingerprint-verification of the Claude Code signing key, registration of the official signed apt repository, then `apt install claude-code`. | `--channel stable|latest`; proxy via `HTTPS_PROXY`/`ALL_PROXY` |

The same files are served for download from bestai.study (prefer those links for the live copy):

- https://bestai.study/downloads/install-opencode-ubuntu24.sh
- https://bestai.study/downloads/install-codex-ubuntu24.sh
- https://bestai.study/downloads/install-claude-code-ubuntu24.sh

---

![Profile views](https://komarev.com/ghpvc/?username=bestai-study)