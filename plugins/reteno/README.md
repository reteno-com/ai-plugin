# Reteno Plugin

Reteno email editor, web funnel analyzer, and MCP integration for Claude Code.

## Skills

### reteno-email-editor

Read, clone, and update Reteno email templates through the Reteno MCP server. Supports narrowly scoped text edits inside existing Reteno builder HTML while preserving the full template structure.

Modes:
- **read** — Export and download a Reteno email template locally
- **clone** — Create a new email from an edited local copy
- **update** — Overwrite an existing email with local edits

### web-funnel-analyzer

Automate onboarding quiz analysis. Opens a funnel URL in Playwright, walks through quiz steps, captures screenshots, extracts text, and generates a summary.

```bash
python3 skills/web-funnel-analyzer/scripts/analyze_funnel.py \
  --url https://example.com/quiz \
  --name example-quiz
```

## MCP Server

This plugin connects to the Reteno MCP server at `https://mcp.reteno.com` using OAuth 2.0. Authenticate via `/mcp` in Claude Code after installing the plugin.
