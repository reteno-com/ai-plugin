# Reteno Plugins for Claude Code

> **Research Preview** — This plugin is in early development. Skills, MCP tools, and plugin structure may change without notice.

A Claude Code plugin marketplace providing Reteno integration skills.

## Installation

Add the marketplace:

```
/plugin marketplace add reteno-com/claude-plugin
```

Install the plugin:

```
/plugin install reteno@reteno-plugins
```

## Authenticate with Reteno

After installation, authenticate with the Reteno MCP server:

```
/mcp
```

Select "reteno" and follow the OAuth flow in your browser.

## Available Skills

| Skill | Description |
|-------|-------------|
| `/reteno:reteno-email-editor` | Read, clone, and update Reteno email templates via MCP |
| `/reteno:web-funnel-analyzer` | Capture and analyze onboarding funnel quizzes |

## Local Development

Test locally without installing:

```bash
claude --plugin-dir ./plugins/reteno
```
