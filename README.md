# Reteno AI Plugin

Reteno bundles reusable AI-agent workflows for Reteno email editing and onboarding funnel analysis.

The repository now supports both:

- Claude Code plugins via Anthropic's `.claude-plugin` format
- Codex plugins via OpenAI's `.codex-plugin` format

Both platforms now install from the repository root.

## Repository Layout

- `.claude-plugin/plugin.json` - Claude plugin manifest at the repo root
- `.codex-plugin/plugin.json` - Codex plugin manifest at the repo root
- `skills/` - shared skill payload used by both platforms
- `.mcp.json` - shared MCP definition at the repo root
- `.claude-plugin/marketplace.json` - Claude marketplace catalog
- `.agents/plugins/marketplace.json` - Codex repo marketplace catalog

## Claude Code

Add the marketplace:

```bash
/plugin marketplace add reteno-com/ai-plugin
```

Install the plugin:

```bash
/plugin install reteno@reteno-plugins
```

For local development:

```bash
claude --plugin-dir ./
```

Skills are namespaced as:

- `/reteno:reteno-email-editor`
- `/reteno:web-funnel-analyzer`

## Codex

Codex currently supports plugin installation through a marketplace file. This repo includes a repo-scoped marketplace at `.agents/plugins/marketplace.json`, and that marketplace points to the repository root plugin.

To test this repo as a Codex plugin:

1. Open the repo in Codex.
2. Restart Codex so it picks up `.agents/plugins/marketplace.json`.
3. Open the plugin directory and select the repo marketplace.
4. Install or enable `Reteno`.

The Codex plugin manifest lives at:

```text
.codex-plugin/plugin.json
```

## Authenticate with Reteno

After installation, authenticate with the Reteno MCP server:

- Claude Code: open `/mcp`, select `reteno`, and complete the OAuth flow.
- Codex: enable the plugin and complete the MCP authentication prompt on install or first use.

## Included Workflows

### `reteno-email-editor`

Read, clone, and update Reteno email templates through the Reteno MCP server while preserving the original builder HTML and CSS structure.

### `web-funnel-analyzer`

Open an onboarding funnel in Playwright, capture screens and text step-by-step, and write a reusable funnel summary for email creation.

## References

- [Anthropic Claude Code plugins](https://code.claude.com/docs/en/plugins)
- [OpenAI Codex Build plugins](https://developers.openai.com/codex/plugins/build)
