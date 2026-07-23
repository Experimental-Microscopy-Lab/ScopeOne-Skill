# ScopeOne Skill

Agent operating guidance and a Claude Code plugin for controlling a running
[ScopeOne](https://github.com/Experimental-Microscopy-Lab/ScopeOne)
microscopy application through its bundled MCP server.

This repository does not contain ScopeOne itself. Install ScopeOne first and
locate `ScopeOneMcpServer.exe` beside `ScopeOne.exe`. On Linux, use the
corresponding executable without the `.exe` suffix.

## Claude Code

Add this repository as a plugin marketplace and install the ScopeOne plugin:

```text
/plugin marketplace add Experimental-Microscopy-Lab/ScopeOne-Skill
/plugin install scopeone@scopeone
/reload-plugins
```

When prompted, select the `ScopeOneMcpServer` executable from the ScopeOne
installation. Start ScopeOne before asking Claude to inspect or control it. The
plugin supplies both the MCP configuration and the ScopeOne operating Skill.

## Codex

Ask Codex to install the Skill directly from GitHub:

```text
Install the ScopeOne Skill from
https://github.com/Experimental-Microscopy-Lab/ScopeOne-Skill/tree/main/skills/scopeone
```

Codex installs it through its built-in Skill Installer. The Skill becomes
available on the next turn. Then ask Codex to use the ScopeOne Skill to connect
to the running application. The Skill explains how to locate and register
`ScopeOneMcpServer` before controlling ScopeOne.

For an offline installation, copy or link [`skills/scopeone`](skills/scopeone)
to `$CODEX_HOME/skills/scopeone`, or to `~/.codex/skills/scopeone` when
`CODEX_HOME` is unset.

## Contents

- `skills/scopeone`: shared ScopeOne Skill for Claude Code and Codex
- `.mcp.json`: Claude Code MCP server configuration
- `.claude-plugin/plugin.json`: Claude Code plugin metadata
- `.claude-plugin/marketplace.json`: Claude Code marketplace metadata

ScopeOne remains the authority for operation schemas, validation, safety
classifications, and hardware read-back. Review physical, destructive, and
file-writing operations before allowing an agent to execute them.
