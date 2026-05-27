# RunDrill Rust

Your personal **Rust coach** inside your AI agent — built to get you over the **ownership wall**, the
place most Rust learners quit. Instead of watching code get generated, you **read it, trace ownership,
predict what the borrow checker will say, and review it for bugs** — treating the compiler as your
teacher. Short targeted drills, an honest picture of your level (novice → expert), and mistake memory
that resurfaces what you got wrong. Your level and progress live on the RunDrill MCP server
(`mcp.rundrill.com`), synced across machines — not in a local file.

**Why this course is different.** When an AI can write any Rust on demand, the real risk is the
*illusion of competence* — feeling fluent in code you never read, while the borrow checker quietly
saves you. RunDrill Rust trains reading, ownership-tracing, and **reviewing** code. Its signature
drill hands you plausible AI-written Rust with a real defect (a needless clone, a lifetime that won't
hold, an `unwrap` that should be `?`) and asks you to find it — like a pull request.

## One plugin, three hosts

The coaching skill (`skills/rust-coach/SKILL.md`) and `.mcp.json` are shared; each host reads its own
manifest and ignores the rest.

| Host | Reads |
|---|---|
| Claude Code / Claude Desktop | `.claude-plugin/plugin.json` + `.mcp.json` |
| OpenAI Codex | `.codex-plugin/plugin.json` + `.mcp.json` |
| Google Antigravity | `plugin.json` + `mcp_config.json` (+ `rules/`) |

The MCP endpoint is `https://mcp.rundrill.com/prog` — the programming-course host that Rust and Python
share, passing `language: "rust"`. On first use the host opens a browser tab for the OAuth handshake,
then closes it — no API key to paste.

## Install

- **Claude Code / Desktop** — via the RunDrill marketplace:
  ```
  /plugin marketplace add rundrill/marketplace
  /plugin install rundrill-rust@rundrill
  ```
  Then run `/rust-coach`.
- **OpenAI Codex** — `codex plugin marketplace add rundrill/marketplace`, then install `rundrill-rust`.
- **Google Antigravity** — drop this folder into `~/.gemini/config/plugins/rundrill-rust/` (global)
  or `<workspace>/.agents/plugins/rundrill-rust/` (workspace-scoped).

## License & attribution

© RunDrill. Licensed under **Creative Commons Attribution-NonCommercial-NoDerivatives 4.0
International (CC BY-NC-ND 4.0)** — full text in [LICENSE](LICENSE). You may view, run, and share this
plugin unchanged, non-commercially, with attribution; you may not use it commercially or publish
modified/derivative versions. For other licensing, contact **hello@rundrill.com**.
