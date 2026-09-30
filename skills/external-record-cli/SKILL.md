---
name: external-record-cli
description: "Start: the external record system is reached from {{PROJECT_NAME}} through {{EXTERNAL_RECORD_TOOL}} or its read tools. Action: apply the C12 external record row and the official command surface to the exact user-named record. End: the named record is read, or an explicitly instructed write is performed, with the exact invocation and its observed evidence."
---

# {{PROJECT_NAME}} External Record CLI ({{EXTERNAL_RECORD_TOOL}})

> **Template note.** This skill is the pattern for binding an external record system (a wiki, an issue tracker, a hosted database, a documentation service) to the harness. Replace every `{{...}}` placeholder with the project value. If the project has no external record system, delete this skill and remove its rows from [C01]({{SKILL_TO_ROOT}}{{CONVENTIONS_PATH}}#C01) and [C12]({{SKILL_TO_ROOT}}{{CONVENTIONS_PATH}}#C12).

This skill holds the `{{EXTERNAL_RECORD_TOOL}}` command surface for the [C12]({{SKILL_TO_ROOT}}{{CONVENTIONS_PATH}}#C12) external record row. It adds no authority, permission, exception, or stopping condition: [{{CONVENTIONS_PATH}}]({{SKILL_TO_ROOT}}{{CONVENTIONS_PATH}}) owns the tool contract and [AGENTS]({{SKILL_TO_ROOT}}AGENTS.md) section 2 owns the procedure.

Sources: the official reference for `{{EXTERNAL_RECORD_TOOL}}`. Command names, flags, and syntax come from that reference; the use constraints come from C12.

## Authority and project binding (C00, C01, C12)

| Start gate | Binding rule | End gate |
| --- | --- | --- |
| This skill applies | Use the [C12]({{SKILL_TO_ROOT}}{{CONVENTIONS_PATH}}#C12) external record row and [AGENTS]({{SKILL_TO_ROOT}}AGENTS.md) section 2 | The command surface is detailed; no new permission is created |
| A record is read | Read only records inside the workspace scope below, plus any record the user separately names; the read tools and the read commands are the read path (C12) | The named or in-scope record is retrieved; no unrelated workspace is swept |
| A write, publish, upload, move, or delete is proposed | Records inside the workspace scope are read-only, so any write there is banned except for the designated worker; writes outside the scope require the user's explicit instruction for that exact target | No write without the instruction or the worker exception; the returned reason is kept |
| A call is denied | Do not route the same action through another tool, shell, or alias (C12) | The denial stands and independent authorized work continues |
| A shell command is run | {{SHELL}}, per the C12 shell row; translate any vendor POSIX examples to the host shell | No alternate shell, Unix path, or fabricated interpreter path is assumed |
| `{{EXTERNAL_RECORD_TOOL}}` is not present on the machine | Installation requires the user's explicit authorization (C12, AGENTS section 5) | The missing tool is reported with its exact command name; nothing is installed or cloned |
| A token, key, or credential appears | Never print, paste, or store it; use the redacting verbose mode, and ban the unsafe verbose mode everywhere (it prints the bearer token) | No secret reaches output, logs, the repository, or `{{TEMP_ROOT}}/` |
| A worker, sync, env, or database command is prepared | The command mutates or executes remote state; treat it as a write under the same instruction rule | No scheduled run, deployment, database attach, or secret push without the instruction |

## MCP registration (C12)

If the external record system offers a hosted remote MCP server, prefer it over a self-hosted package.

| Item | Value |
| --- | --- |
| Endpoint | {{EXTERNAL_RECORD_MCP_ENDPOINT}} |
| Auth | {{EXTERNAL_RECORD_AUTH}} |
| Tool name prefix | {{EXTERNAL_RECORD_TOOL_PREFIX}} |

The project registers the server in the file each harness reads:

| Harness | File | Server entry |
| --- | --- | --- |
| VS Code (GitHub Copilot) | `.vscode/mcp.json` | `servers.{{EXTERNAL_RECORD_SERVER_NAME}} = { "type": "http", "url": "{{EXTERNAL_RECORD_MCP_ENDPOINT}}" }` |
| Claude Code | `.mcp.json` | `mcpServers.{{EXTERNAL_RECORD_SERVER_NAME}} = { "type": "http", "url": "{{EXTERNAL_RECORD_MCP_ENDPOINT}}" }` |
| Qwen | `.qwen/settings.json` | `mcpServers.{{EXTERNAL_RECORD_SERVER_NAME}} = { "httpUrl": "{{EXTERNAL_RECORD_MCP_ENDPOINT}}" }` |
| Codex | `.codex/config.toml` | `[mcp_servers.{{EXTERNAL_RECORD_SERVER_NAME}}]` with `url = "{{EXTERNAL_RECORD_MCP_ENDPOINT}}"` |

Registration is not authentication: the first connection returns an auth challenge and the client opens the authorization flow, whose approval the user completes. After approval the client can read and update content the user can access in the selected workspace.

## Workspace scope and permission (C12)

The user fixes the working range. Record it here exactly, because the read-only boundary and the write exception depend on it.

| Item | Value |
| --- | --- |
| Range root | {{EXTERNAL_RECORD_RANGE_ROOT}} |
| In-range | The root and all descendant pages, databases, or projects |
| Permission | Read-only inside the range |
| Exception | The designated worker; the read-only limit does not apply to it |
| Outside the range | Only what the user separately names; read-only unless the user gives an explicit write instruction for that target |
| Read tools | {{EXTERNAL_RECORD_READ_TOOLS}} |

## Worker (C12)

The worker is the only component allowed to write inside the range. It records codebase facts as new rows in the designated database.

| Item | Value |
| --- | --- |
| Worker owner | {{EXTERNAL_RECORD_WORKER_PATH}} |
| Target database | {{EXTERNAL_RECORD_DATABASE}} |
| Deploy and status | Only through the tool's canonical worker entry point |
| Secret | The API token lives only as a worker secret, never in the repository or `{{TEMP_ROOT}}/` |

## Command surface

Document the exact commands the project uses, with their flags and the host-shell translation. Keep this section to the commands the project actually needs; do not paste the whole vendor reference.

| Command | Purpose | Notes |
| --- | --- | --- |
| `{{EXTERNAL_RECORD_TOOL}} {{CMD_1}}` | {{CMD_1_PURPOSE}} | {{CMD_1_NOTES}} |
| `{{EXTERNAL_RECORD_TOOL}} {{CMD_2}}` | {{CMD_2_PURPOSE}} | {{CMD_2_NOTES}} |

## Failure handling

| Start gate | Action | End gate |
| --- | --- | --- |
| A command fails | Keep the exact command, arguments, and returned reason; classify auth, scope, rate limit, or actual absence | The cause is identified without retrying the same call unchanged |
| A write is denied | Do not route it through another tool or alias | The denial stands and independent authorized work continues |
| A credential would be printed | Stop and use the redacting mode | No secret reaches output, logs, the repository, or `{{TEMP_ROOT}}/` |

## Verification

| Start gate | Action | End gate |
| --- | --- | --- |
| A read is claimed | Show the exact invocation and the observed record | The claim matches the observed record |
| A write is claimed | Show the exact invocation, the target, and the observed result | The write is confirmed by the tool's own output, not by assumption |
| The skill is edited | Check the C12 external record row, the C01 owned-document table, and the harness registration files for contradictions | No contradiction remains |
