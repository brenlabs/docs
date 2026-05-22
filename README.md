# brenlabs docs

Public documentation for [brenlabs](https://bren.run), the evaluation
platform for AI coding agents. Deployed via [Mintlify](https://mintlify.com)
from this repo.

Live site: **https://docs.bren.run** *(once Mintlify is connected in the dashboard)*

## Local preview

```bash
npm i -g mint
mint dev
```

Visit `http://localhost:3000`. Edits hot-reload.

## Repo layout

```
docs.json              # Mintlify site config — navigation, theme, etc.
index.mdx              # Landing page
quickstart.mdx         # First-run walkthrough
concepts/              # Entity-level reference (products, agents, runs, …)
guides/                # How-tos (authoring skills, installing plugins, …)
api-reference/         # OpenAPI-driven endpoint pages + overview
AGENTS.md              # House style and terminology for AI agents editing this repo
```

## Editing rules

Read `AGENTS.md` before making content changes. It defines the brenlabs
terminology and house style so prose stays consistent across pages.

For Mintlify-specific guidance (components, frontmatter, etc.), the
Mintlify MCP at `https://mintlify.com/docs/mcp` is wired in user-level
Claude Code config — query it before guessing component shapes.

## Refreshing the OpenAPI snapshot

The API reference is generated from `api-reference/openapi.json`. To pull
the latest:

```bash
curl -sS https://api.bren.run/openapi.json > api-reference/openapi.json
```

## Deployment

Pushing to `main` triggers a Mintlify deploy via the GitHub app installed
on this repo. There's no separate build step.

## Useful commands

```bash
mint dev            # Local preview at localhost:3000
mint broken-links   # Check internal links
mint a11y           # Accessibility audit
mint validate       # Validate the build
```
