# hedwigai for Claude Code

A system of record for the spreadsheets and documents your agent keeps.

Claude Code is good at changing code. The state around the work (a decision log, a migration's progress, a lead tracker, a handoff for tomorrow's session, eval results other agents append to) usually ends up in a loose local file that the next session never finds, or that two writers overwrite. This plugin keeps that state in a hedwigai workbook:

- **Versioned.** Every write is a new version, and any earlier one can be restored.
- **Checked.** A workbook's schema declares each table's columns, types, required cells and keys. An edit that breaks it is refused with the cells that broke it.
- **Never merged over.** A write made on an old version is refused, so an edit in Excel, by a colleague or by another agent is never lost.
- **Where you keep it.** Link a workbook to a file in Google Drive or Dropbox, and each version is written back to that file, its sharing and history kept. Excel keeps its formulas and formats; Word keeps its styles.

## Install

```
/plugin marketplace add un-seen/hedwigai-claude-plugin
/plugin install hedwigai@hedwigai
```

Then run `/mcp`, choose **hedwigai** and sign in. The first workbook is free.

Without the plugin, the server alone:

```
claude mcp add --transport http --scope user hedwigai https://mcp.hedwigai.com
```

## What it adds

- **The hedwigai MCP server** (`https://mcp.hedwigai.com`): workbooks, schemas, versions, Drive and Dropbox links, and the account's data programs.
- **The `workbook-state` skill**: tells Claude when state belongs in a workbook rather than a local file, and how to write it safely (find before making, write against the version read, schema for shared tables).

Reading, searching and writing workbooks is free. Research runs, started only when you ask for research, are billed to your account.

## Links

- [hedwigai.com](https://www.hedwigai.com)
- [Claude Connectors Directory listing](https://claude.ai/directory/hedwigai)
- [MCP Registry: com.hedwigai/hedwigai](https://registry.modelcontextprotocol.io/v0/servers?search=com.hedwigai)
- Support: hello@hedwigai.com

- [Privacy](https://www.hedwigai.com/privacy) · [Terms](https://www.hedwigai.com/terms)
