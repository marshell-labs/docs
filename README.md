# chifu docs

User-facing documentation for **chifu**, dependency security for AI coding
agents. Built on [Mintlify](https://mintlify.com).

- Product: a CLI (`@marshell/chifu`) that detects vulnerable dependencies, plus
  an agent skill (`chifu-dep-guard`) that drives the fix. Installed by
  `@marshell/chifu-wizard`. No MCP server.
- Live site: [docs.marshell.dev](https://docs.marshell.dev)
- Product site: [marshell.dev](https://marshell.dev)

See `AGENTS.md` for product facts, terminology, and the house style before
editing pages.

## Structure

- `docs.json` — site config (navigation, theme, logo, fonts).
- `index.mdx` — welcome hub with card navigation.
- `*.mdx` — content pages (`quickstart`, `how-it-works`, `capabilities`, `cli`,
  `ecosystems`, `ci`, `skill`, `agents`, `dashboard`, `plans`, `troubleshooting`).
- `images/` — fish logo, hero gif, agent icons.
- `style.css` — neutral theme overrides.

## Develop

Install the [Mintlify CLI](https://www.npmjs.com/package/mint):

```bash
npm i -g mint
```

Run it from this folder (where `docs.json` lives):

```bash
mint dev              # preview at http://localhost:3000
mint broken-links     # check internal links
```

## Publish

Changes deploy automatically after pushing to the default branch, via the
Mintlify GitHub app.
