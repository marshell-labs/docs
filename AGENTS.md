# Documentation project instructions

## About this project

- This is a documentation site built on [Mintlify](https://mintlify.com).
- Pages are MDX files with YAML frontmatter (`title` + `description`).
- Configuration lives in `docs.json`.
- Run `mint dev` to preview locally. Run `mint broken-links` to check links.

## About the product

- **chifu** is dependency security for AI coding agents. It is two pieces: a
  CLI (`@marshell/chifu`, binary `chifu`) that detects known vulnerabilities in
  a project's dependencies, and an agent skill (`chifu-dep-guard`) that tells a
  coding agent when to check and how to fix. A wizard
  (`@marshell/chifu-wizard`) installs both. **There is no MCP server.**
- It is the product in the **Marshell** family. Company = Marshell,
  product = chifu, site = `marshell.dev`, dashboard = `marshell.dev/dashboard`,
  docs = `docs.marshell.dev`.
- The core loop: the CLI **detects** (matches `package.json` + lockfile against
  65,000+ CVEs from NVD + OSV), the agent **fixes** (edits `package.json` and
  `overrides`/`resolutions`, re-checks until clean). The CLI never installs or
  patches anything.
- The safety rule (load-bearing, repeat it): while checking or fixing, never
  run an install (`npm/yarn/pnpm/bun install`, `npm ci`, `npm audit fix`).
  Installs run untrusted lifecycle scripts. The only allowed command is
  `npm install --package-lock-only --ignore-scripts`.
- npm is the only supported ecosystem today. Do not promise others as shipped.

## Terminology

- Product name **chifu** is lowercase, even at the start of a sentence.
- The CLI command is `chifu check` (and `chifu login`). The skill is
  `chifu-dep-guard`. The installer is the "wizard".
- "dependency" / "package", "vulnerability" / "CVE", "finding", "synced check".
- Severities: Critical, High, Medium, Low (and Info).
- API keys start with `chf_`.
- Supported agents: Claude Code, Cursor, Windsurf, Codex, OpenCode, Gemini CLI,
  Cline.
- Plans meter **synced checks** (signed-in checks saved to the dashboard).
  Local `chifu check` is free and unlimited. Free = $0 / 100, Pro = $7.99 / 400,
  Max = $23.99 / 1,600 synced checks per month.

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
  CLI, the skill, the wizard, the dashboard, and the small REST API the CLI
  calls (`POST /api/v1/deps/check`, the `chifu login` device-pairing flow).
- Keep facts in sync with the CLI source: commands and flags (`chifu check`
  with `--json`, `--verbose`, `--fail-on-findings`, `--api-url`), exit codes
  (0 ok, 1 only with `--fail-on-findings`, 2 error), config location, and the
  `CHIFU_API_KEY` / `CHIFU_API_URL` / `CHIFU_WEB_URL` env vars.

## Assets

- Logo: `logo/chifu-dark.svg` (cream glyph, dark navbar) and
  `logo/chifu-light.svg` (warm-black glyph, light navbar). Favicon:
  `favicon.svg`. Hero animation: `images/hero.gif` (the koi motif from the
  landing page).
- Theme matches the app: dark by default, teal accent `#02E2BC`, background
  `#0A0E11`, Plus Jakarta Sans.
