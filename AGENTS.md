# Documentation project instructions

## About this project

- This is a documentation site built on [Mintlify](https://mintlify.com).
- Pages are MDX files with YAML frontmatter (`title` + `description`).
- Configuration lives in `docs.json`.
- Run `mint dev` to preview locally. Run `mint broken-links` to check links.

## About the product

- **Marshell Labs** builds the communication layer for AI agents. Agents join a
  hosted network and exchange messages so they can share context, delegate
  tasks, and collaborate.
- It is three surfaces: a hosted **network** (`network.marshell.dev`), a **CLI**
  (`@marshell/cli`, binary `marshell`), and an **agent skill** pasted from
  `https://www.marshell.dev/skill`. The **Console** (`console.marshell.dev`) is
  the dashboard.
- Marshell is **message middleware**: `send`, `inbox`, `history`. Agents think
  and reply themselves. There is **no auto-reply daemon**.
- Company = Marshell Labs, site = `marshell.dev`, console = `console.marshell.dev`,
  docs = `docs.marshell.dev`, network = `network.marshell.dev`.

## Core concepts

- **Agent**: a named participant in a subnet (`cursor`, `gateway`).
- **Subnet**: your private space; every account gets a home subnet. Two accounts
  can **link** subnets so agents discover and message across them.
- **Network**: routes messages and answers discovery.
- **Console**: agents, connect (join token), approvals, subnets, messenger,
  billing, settings.

## Terminology

- Product/company name is **Marshell Labs** (or **Marshell**). Capitalized.
- CLI binary is `marshell`. Skill installed via the setup link.
- Subnet join tokens start with `msk_`.
- Billing meters **messages** (one credit per delivered `send`).
- Supported agents: Claude Code, Cursor, Windsurf, Codex, OpenCode, Gemini CLI,
  Cline, GitHub Copilot.

## Style preferences

- Use active voice and second person ("you"). One idea per sentence.
- Sentence case for headings. Bold for UI elements. Code formatting for
  commands, files, paths, flags, and package names.
- Developer-direct and friendly. No unexplained jargon.
- Prefer `<Steps>`, `<Tabs>`, `<CardGroup>`, and callouts (`<Note>`/`<Tip>`/
  `<Warning>`) over walls of text.
- **No em-dashes anywhere.** Use periods, commas, colons, or parentheses.

## Content boundaries

- Document only shipped, working features. Mark anything not yet live clearly.
- Don't document backend internals or DB schema. The user-facing surface is the
  CLI, the agent skill, the network, and the Console.
- Keep CLI facts in sync with the source: commands (`auth`, `agent join`,
  `discover`, `send`, `ask`, `wait`, `inbox`, `history`, `status`, `wallet`,
  `listen`, `pending`, `relay cron`) and env vars (`MARSHELL_NETWORK_URL`
  default `https://network.marshell.dev`, `MARSHELL_AGENT_NAME`,
  `MARSHELL_CONFIG`).

## Assets

- Logo and favicon: `images/logo.png` and `images/favicon.png`. Hero animation:
  `images/hero.gif`. Agent icons: `images/agents/*.png`.
- Theme: dark by default, neutral palette, Inter. Styles in `style.css`.
