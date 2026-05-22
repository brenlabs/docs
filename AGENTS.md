# brenlabs docs — instructions for agents

This is the public documentation site for **brenlabs**, an evaluation platform
that runs AI coding agents (Claude Code, Codex, …) against products in
sandboxed environments and judges the result.

The site is built on [Mintlify](https://mintlify.com). Pages are MDX files
with YAML frontmatter. Configuration lives in `docs.json`. Run `mint dev` to
preview locally and `mint broken-links` to check links.

For Mintlify product knowledge (components, configuration, writing standards),
the Mintlify MCP at `https://mintlify.com/docs/mcp` is wired in user-level
Claude Code config — query it before guessing component shapes.

## Terminology

Use these terms consistently across all pages:

| Use | Not |
|---|---|
| **brenlabs** (lowercase, one word) | Brenlabs, Bren Labs, BrenLabs |
| **org** | tenant, account, workspace |
| **member** | user, seat |
| **product** | app, system under test |
| **product environment** | env, instance, target |
| **agent** | bundle, configuration (the user-defined Claude Code / Codex config) |
| **agent type** | integration, provider (the underlying tool: `claude-code`, `codex`) |
| **scenario** | task, test case |
| **skill** | (no synonym — same word Claude Code uses) |
| **plugin** | (no synonym — same word Claude Code uses for Git-imported bundles) |
| **MCP server** | tool server (do not call it "plugin" — plugin is a separate entity in brenlabs) |
| **secret** | credential, API key (the stored encrypted value) |
| **run** | execution, invocation |
| **judge verdict** | evaluation, score |

Codename `axp-api` is **internal-only** — never use it in public docs.

## Style preferences

- Active voice, second person ("you").
- Sentence case for headings ("Get started", not "Get Started").
- Bold for UI elements: click **New agent**.
- Code formatting for file names, commands, paths, identifiers: `docs.json`, `mint dev`, `ag_edd1j1ln`.
- One idea per sentence.
- No marketing words: "powerful", "seamless", "robust", "cutting-edge".
- No filler: "it's important to note", "in order to".
- No emoji decoration.
- Cards in `<Columns cols={2}>` for landing pages. Plain prose for detail pages.

## Content boundaries

- **Do document**: API endpoints, entity model, scenario authoring, skill format, MCP wiring, run lifecycle, error catalogue.
- **Do not document**: internal infra (Modal, Neon, R2), staff workflows, billing internals, ops runbooks. Those belong in `project-vault`, not here.
- **Pricing & plans**: live on the marketing site, not here.

## Source of truth

When in doubt about the API or entity model, the running API's OpenAPI export
(`api-reference/openapi.json`) is canonical. Refresh it with:

```bash
curl -sS http://localhost:8000/openapi.json > api-reference/openapi.json
```

When in doubt about Claude Code or Codex behaviour, query the Mintlify MCP or
the tool's own CLI (`claude --help`, `codex --help`) — do not rely on training
data, especially for flag names and skill discovery semantics.
