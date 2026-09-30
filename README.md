<div align="center">
<img src="bg.png" alt="harn" width="100%">

# harn

*A project harness that pins every AI model to one written contract — one AI, one IDE, no WSL.*

*Markdown and a single MCP config: a conventions core, a binding agent contract, skills, and per-model system prompts.*

![status](https://img.shields.io/badge/status-template-informational?style=flat-square)
![license](https://img.shields.io/badge/license-attribution--redistribution-blue?style=flat-square)
![lang](https://img.shields.io/badge/lang-en%20%7C%20ko-lightgrey?style=flat-square)
![format](https://img.shields.io/badge/format-Markdown-black?style=flat-square&logo=markdown&logoColor=white)

![conventions](https://img.shields.io/badge/conventions-C00--C20-success?style=flat-square)
![AGENTS](https://img.shields.io/badge/AGENTS-sections_0--7-blueviolet?style=flat-square)
![skills](https://img.shields.io/badge/skills-2-9cf?style=flat-square)
![runtime](https://img.shields.io/badge/runtime-single_AI_%C2%B7_one_IDE_%C2%B7_no_WSL-orange?style=flat-square)

![Claude](https://img.shields.io/badge/Claude-6E56CF?style=flat-square)
![Copilot](https://img.shields.io/badge/Copilot-181717?style=flat-square)
![Codex](https://img.shields.io/badge/Codex-412991?style=flat-square)
![Qwen](https://img.shields.io/badge/Qwen-615CED?style=flat-square)

[English](README.md) · [한국어](README.ko.md)

[![CONVENTIONS](https://img.shields.io/badge/DOCS-conventions-6E56CF?style=flat-square)](conventions.md)
[![AGENT RULES](https://img.shields.io/badge/DOCS-agent_rules-4D4D4D?style=flat-square)](AGENTS.md)
[![WORK LOG](https://img.shields.io/badge/DOCS-work_log-2E7D32?style=flat-square)](ai-tracking.md)
[![SESSION AUDIT](https://img.shields.io/badge/DOCS-session_audit-B45309?style=flat-square)](session-audit.md)
[![SKILLS](https://img.shields.io/badge/DOCS-skills-2563EB?style=flat-square)](skills/project-conventions/SKILL.md)
[![LICENSE](https://img.shields.io/badge/DOCS-license-111827?style=flat-square)](LICENSE)

</div>

---

## What this is

`harn` is a project harness template. It pins any AI model — Claude, Codex, Qwen, Copilot, or another — to one written contract, so the model's actions conform to the project's conventions instead of the model's own habits.

The harness is documentation and configuration only: Markdown plus a single MCP config file. There is no build, no runtime, and no dependency. Every rule lives in one owner document, and every other file points back to it.

`harn` is a template, not a project. Project facts — name, paths, commands, structure, assets, tools — are left as `{{...}}` placeholders. The normative sentences and the clause structure are kept exactly, because that is the harness's identity.

## Architecture

One AI, one IDE, no WSL.

The harness assumes a single AI model working inside one IDE on the native host — VS Code or an equivalent single editor. It does not assume WSL, a container, a second shell, or a distributed agent fleet. The model edits files directly, runs commands in the host's native shell, and reads evidence from real tool output.

Authority flows one way only:

```
user instruction → conventions → AGENTS → skills → action → evidence
```

Nothing lower may redefine, reduce, defer, or make an exception to anything higher. The user is the final superior and the sole decision owner. The model is the executor: it has no authority to refuse, reduce, or postpone an instruction because of token volume, cost, workload, elapsed time, context length, or difficulty.

Every shared concept has exactly one owner:

| Concept | Owner |
| --- | --- |
| Authority, direction, definitions, fixed decisions | `conventions.md` |
| Always-on behavior and procedure | `AGENTS.md` |
| Detailed procedure | `skills/` |
| Per-model prompt | `instructions/` |
| Completed-session record | `ai-tracking.md` |
| Violation and unfinished-work record | `session-audit.md` |
| Tool registration | `config.toml` |

## Documents

| File | What it is | Language | Owner |
| --- | --- | --- | --- |
| `conventions.md` | The absolute definition document and the core of the harness. Owns authority and direction, the single standard, fixed decisions, architecture and owners, role-group division, the execution/compute/platform architecture, the production troubleshooting log, structure and dependency direction, the low-level path contract, naming, the execution environment, evidence and acceptance, FIX and exception definitions, process-type definitions, inference and verification, the work lifecycle and GOAL tracking, change prohibitions, tool contracts, version and material preservation, enforcement limits, and the data catalog. Clauses C00–C20. | Korean | C01 |
| `AGENTS.md` | The binding AI behavior contract that enforces `conventions.md`. Section 0 hard rules, 1 direction, 2 operating procedure, 3 authority and document ownership, 4 per-action evidence, 5 explicit prohibitions, 6 proven failure bans (S01–S20), 7 failure, correction, and completion invariants. | English | C01, AGENTS §3 |
| `skills/project-conventions/SKILL.md` | The shared workflow that details AGENTS section 2: authority gates, the shared-decision philosophy, the ordered work cycle (G1–G10), the six-question proposition, the change decision procedure (D1–D7), FIX and tool recovery, process-specific application, and state, history, and delivery. It adds no authority, exception, or stopping condition. | English | C01 |
| `skills/external-record-cli/SKILL.md` | Optional. Binds an external record system (a wiki, an issue tracker, a hosted database) to the harness. Owns the command surface and the read/write boundary for the C12 external-record row and the MCP registration for each harness. Delete it when the project has no external record system. | English | C01, C12 |
| `instructions/model-system-prompt.md` | A per-model system prompt. Every sentence restates a clause of `conventions.md` or `AGENTS.md` with its bracket reference; duplicate one file per model. It adds no rule of its own. | English | C01 |
| `ai-tracking.md` | Completed-session GOAL summaries: one line per requirement with target, method, result, verification, and unverified boundary, plus the clause-by-clause comparison result and the repository commit flow. Written only after the GOAL completes. | Korean | C14, C15 |
| `session-audit.md` | Violation evidence for rules that exist only as documents, the ban-behavior rows M01–M27, and the unfinished-instruction TODO rows that carry work across sessions. | Korean | C15, C16 |
| `config.toml` | MCP server registration for Codex (`.codex/config.toml`): the runtime observation server with per-tool approval modes, and the optional external-record server. Registration is not authorization; the C12 tool contract still governs. | Config | C12 |
| `LICENSE` | The license terms: free use, modification, and redistribution, on the single condition that the copyright notice, the copyright holder, and the license text are preserved. Redistribution that removes them is unauthorized and prohibited. | English | C11 |
| `README.md` · `README.ko.md` | Introduction, architecture, and the owned-document guide — two language editions of the same content. | English / Korean | C01 |
| `bg.png` | The banner image used by both README editions. | Image | — |

## What the harness preserves

Filling the placeholders does not change any of the following. This is the harness's identity.

| Principle | Owner clause |
| --- | --- |
| Authority flows one way: user instruction → conventions → AGENTS → skills → action → evidence | C00 |
| The user is the final superior and the sole decision owner; the AI is the executor and has no authority to refuse, reduce, or defer an instruction for tokens, cost, time, or difficulty | C00 |
| Everything the user enters in a session is that session's GOAL and a binding contract | C00, C15 |
| Only reasoning whose every link is established by evidence justifies an action; a missing link is filled by obtaining the fact, not by a guess | C00, C09 |
| A value is never derived by a pattern, mapping, or matching rule; every item is defined explicitly | C00 |
| Every change completes all seven steps of the change decision procedure (①–⑦) before it is executed | C14 |
| Verification is bidirectional: forward proves zero omissions, backward proves zero inventions | C14 |
| Every action needs a direct 1:1 proposition identifying who, what, when, where, why, and how | C09 |
| A failure is handled by a FIX that corrects its causal owner; guards, defaults, fallbacks, and retries that hide a failure are banned | C06 |
| Every warning and error is critical; unused, undefined, and disconnected code is traced as a missing connection, never deleted | C06, C13 |
| A document does not guarantee behavior; the closest thing to a guarantee is mechanical enforcement | C16 |
| No tracking, worklog, or handoff is written before the GOAL completes; the summary is written after completion and compared clause by clause immediately | C15 |
| Every sentence the user sees is in {{USER_LANGUAGE}} with a tone fixed to {{RESPONSE_TONE}} | C15 |
| Failure modes that actually occurred are closed as S rows, with the evidence owned by the session audit | AGENTS section 6 |

## Placeholders

Replace every `{{...}}` with the project value. The tables below group the placeholders. A placeholder not listed here is filled the same way, because its name is its meaning.

### 3.1 Identity

| Placeholder | Meaning | Example |
| --- | --- | --- |
| `{{PROJECT_NAME}}` | Project identifier (short name) | `evt` |
| `{{PROJECT_PURPOSE}}` | One-line purpose | game engine and native client |
| `{{PROJECT_STACK}}` | Stack summary | C++26, xmake, TypeScript, SolidJS |
| `{{PROJECT_ROOT}}` | Absolute repository root | `D:\26_project\ev_three` |
| `{{MODEL_NAME}}` | Model the prompt targets | `GPT-6 Astra` |
| `{{DECISION_DATE}}` | Date of the fixed decision a row cites | `2026-09-24 directive` |

### 3.2 Document paths

| Placeholder | Meaning | Example |
| --- | --- | --- |
| `{{CONVENTIONS_PATH}}` | Path to the conventions document | `docs/conventions.md` |
| `{{AGENTS_PATH}}` | Path to AGENTS | `AGENTS.md` |
| `{{TRACKING_PATH}}` | Path to the tracking log | `docs/ai-tracking.md` |
| `{{AUDIT_PATH}}` | Path to the session audit | `docs/claude-session-audit.md` |
| `{{README_PATH}}` | Path to the README | `README.md` |
| `{{SKILL_ROOT}}` | Skills root | `.codex/skills` |
| `{{SKILL_TO_ROOT}}` | Relative path from the skills directory to the project root | `../../../` |
| `{{INSTRUCTION_ROOT}}` | Model instruction root | `.codex/instructions` |
| `{{INSTRUCTION_TO_ROOT}}` | Relative path from the instruction directory to the project root | `../../` |
| `{{HOOK_PATH}}` | Project hook path | `.claude/hooks` |
| `{{MEMORY_PATH}}` | Model project memory path | the model's own memory folder |

### 3.3 Language and tone

| Placeholder | Meaning | Example |
| --- | --- | --- |
| `{{CONVENTIONS_LANGUAGE}}` | Language of the conventions | Korean |
| `{{AGENTS_LANGUAGE}}` | Language of AGENTS | English |
| `{{SKILL_LANGUAGE}}` | Language of the skills and prompts | English |
| `{{README_LANGUAGE}}` | Language of the README | English and Korean |
| `{{USER_LANGUAGE}}` | Language of every sentence the user sees | Korean |
| `{{RESPONSE_TONE}}` | Fixed tone of the response | polite formal speech |
| `{{JOURNAL_TIMEZONE}}` | Time base for journal entries | KST |

### 3.4 Structure and paths

| Placeholder | Meaning | Example |
| --- | --- | --- |
| `{{SOURCE_ROOT}}` | Own source root | `src` |
| `{{LOWLEVEL_ROOT}}` | Low-level source root | `native/src` |
| `{{PRODUCER_ROOT}}` | Producer tool root | `tools` |
| `{{CONSUMER_ROOT}}` | Consumer code root | `src`·`native` |
| `{{MANAGED_ASSET_ROOT}}` | Managed asset root | `data` |
| `{{SOURCE_OF_TRUTH}}` | Source of truth | `research/unity-bundles` |
| `{{GENERATED_ROOT}}` | Generated output root | `dist`·`Release` |
| `{{TEMP_ROOT}}` | Temporary artifact root | `tmp-codex` |
| `{{MANIFEST_PATH}}` | Version source | `package.json` |
| `{{CATALOG_PATH}}` | Catalog | `data/catalog.tsv` |
| `{{SCHEMA_PATH}}` | Schema | `data/schema.json` |
| `{{DOMAIN_LIST}}` | Domain list | `type, constant, logic, …` |
| `{{DOMAIN_1}}`·`{{DOMAIN_2}}` | Domain names | `logic` |
| `{{DOMAIN_1_CLASSES}}`·`{{DOMAIN_2_CLASSES}}` | Class folders per domain | `catalog, combat, engine` |
| `{{DOMAIN_1_ALLOWED}}`·`{{DOMAIN_2_ALLOWED}}` | Allowed dependency domains | `type, constant, logic` |
| `{{DOMAIN_RULE_OWNER}}` | Owner of the format check | path of the checker file |
| `{{LOWLEVEL_LANGUAGE}}` | Low-level language | `C++26` |
| `{{LOWLEVEL_FILE_CONVENTION}}` | Low-level file rule | one `.hpp`·`.cpp` pair per type |
| `{{AREA_1}}`·`{{AREA_2}}` | Low-level areas | `gpu` |
| `{{AREA_1_FEATURES}}`·`{{AREA_2_FEATURES}}` | Feature folders | `d3d12, vulkan` |
| `{{AREA_1_RESPONSIBILITY}}`·`{{AREA_2_RESPONSIBILITY}}` | Responsibility | device, resources, swap chain |
| `{{BUILD_TARGETS}}` | Build targets | executable and library list |
| `{{MAPPING_TARGET_KINDS}}` | Manually designated target kinds | spirit, skin, monster, boss |
| `{{TARGET_KIND_LIST}}` | Complete target-kind list | the same kind list |
| `{{ROLE_GROUP_LIST}}` | Role group list | character, effect, map, common |
| `{{ROLE_GROUP_1}}`~`{{ROLE_GROUP_3}}` | Role group names | character render |
| `{{ROLE_GROUP_1_PATHS}}`~`{{ROLE_GROUP_3_PATHS}}` | Paths a group owns | path list |
| `{{ROLE_GROUP_1_RULE}}`~`{{ROLE_GROUP_3_RULE}}` | Change rule per group | changed only by a directive that names it |
| `{{ROLE_GROUP_COMMON_PATHS}}` | Common group paths | common path list |
| `{{CROSS_1}}`·`{{CROSS_1_CALLER}}`·`{{CROSS_1_OWNER}}`·`{{CROSS_1_CONTRACT}}` | Cross consumption | call contract between groups |
| `{{BOUNDARY_1_NAME}}`~`{{BOUNDARY_3_NAME}}` | Architecture boundary names | game and scene meaning |
| `{{BOUNDARY_1_OWNER}}`~`{{BOUNDARY_3_OWNER}}` | Boundary owner and contract | owning path |
| `{{SERVING_OWNER}}` | Owner of data serving | serving module |
| `{{SHARED_DATA_1}}`·`{{SHARED_DATA_2}}` | Shared data | draw list |
| `{{SHARED_DATA_1_OWNER}}`·`{{SHARED_DATA_2_OWNER}}` | Contract owners | owning file |
| `{{SHARED_DATA_1_BOUNDARY}}`·`{{SHARED_DATA_2_BOUNDARY}}` | Boundary that must agree | header, entries, lifetime |
| `{{ASSET_DOMAIN_LIST}}` | Asset domain list | `models, effect, scene, …` |
| `{{ASSET_DOMAIN_1}}`·`{{ASSET_DOMAIN_2}}` | Asset domains | `models` |
| `{{ASSET_DOMAIN_1_CATALOG}}`·`{{ASSET_DOMAIN_2_CATALOG}}` | Domain catalog files | `characterCatalog.json` |
| `{{ASSET_DOMAIN_1_UNIT}}`·`{{ASSET_DOMAIN_2_UNIT}}` | Item unit | spirit |
| `{{ASSET_DOMAIN_1_FIELDS}}`·`{{ASSET_DOMAIN_2_FIELDS}}` | Schema and fields to state | field list |
| `{{PATTERN_1}}`·`{{PATTERN_1_SHAPE}}`·`{{PATTERN_1_COUNT}}`·`{{PATTERN_1_PRODUCER}}`·`{{PATTERN_1_CONSUMER}}`·`{{PATTERN_1_FIELDS}}` | Asset pattern row | pattern, shape, count, producer, consumer, fields |
| `{{SCHEMA_RECORD_OWNER}}` | Owner of the schema declaration | declaration script |

### 3.5 Commands and tools

| Placeholder | Meaning | Example |
| --- | --- | --- |
| `{{SHELL}}` | Shell | `Windows PowerShell` |
| `{{CHECK_COMMAND}}` | Static check | `npm run c` |
| `{{BUILD_COMMAND}}` | Build | `npm run build:native` |
| `{{RELEASE_BUILD_COMMAND}}` | Release build | `npm run build:release` |
| `{{CATALOG_COMMAND}}` | Catalog gate | `npm run data:catalog` |
| `{{VERIFY_COMMAND}}` | Asset verification | `npm run data:verify` |
| `{{VERSION_COMMAND}}` | Version change | `npm run version:set` |
| `{{DEV_COMMAND}}` | Development run | `npm run dev` |
| `{{PROD_COMMAND}}` | Production run | `npm run prod` |
| `{{TIME_TOOL}}` | Time tool | a time-read script |
| `{{SCRIPT_RUNTIME}}` | Script runtime | path to the Python executable |
| `{{RUNTIME_TOOL}}` | Runtime observation tool | Runtime Lab |
| `{{RUNTIME_STATUS_TOOL}}`·`{{RUNTIME_START_TOOL}}`·`{{RUNTIME_STOP_TOOL}}`·`{{RUNTIME_OBSERVE_TOOL}}`·`{{RUNTIME_DEBUG_TOOL}}` | Observation session tools | `ev_runtime_*` |
| `{{RUNTIME_SERVER_NAME}}`·`{{RUNTIME_SERVER_ENTRY}}` | Observation MCP server | server name and entry point |
| `{{RE_TOOL}}` | Reverse-engineering tool | `IDA Pro 9.4` |
| `{{INDEX_TOOL}}` | Source indexing tool | index script |
| `{{EXTERNAL_RECORD_TOOL}}` | External record CLI | `ntn` |
| `{{EXTERNAL_RECORD_SERVER_NAME}}`·`{{EXTERNAL_RECORD_MCP_ENDPOINT}}`·`{{EXTERNAL_RECORD_AUTH}}`·`{{EXTERNAL_RECORD_TOOL_PREFIX}}` | External record MCP | server, auth, prefix |
| `{{EXTERNAL_RECORD_RANGE_ROOT}}`·`{{EXTERNAL_RECORD_READ_TOOLS}}`·`{{EXTERNAL_RECORD_WORKER_PATH}}`·`{{EXTERNAL_RECORD_DATABASE}}` | External record scope and worker | range root, read tools, worker, database |
| `{{CMD_1}}`·`{{CMD_1_PURPOSE}}`·`{{CMD_1_NOTES}}`·`{{CMD_2}}`·`{{CMD_2_PURPOSE}}`·`{{CMD_2_NOTES}}` | External record commands | command, purpose, notes |

### 3.6 Checks and enforcement

| Placeholder | Meaning | Example |
| --- | --- | --- |
| `{{CHECKED_LANGUAGE_1}}`·`{{CHECKED_LANGUAGE_2}}` | Languages under the static check | `TS`·`GLSL` |
| `{{BUILT_LANGUAGE_1}}`·`{{BUILT_LANGUAGE_2}}` | Languages under the build check | `HLSL`·`C++` |
| `{{CHECK_SCOPE}}` | Static-check scope | list of checked items |
| `{{CHECK_GAPS}}` | Static-check gaps | items the check does not cover |
| `{{COMMIT_HOOK_SCOPE}}` | Commit hook scope | large-file blocking |
| `{{PERMISSION_SCOPE}}`·`{{PERMISSION_LEVEL}}` | Harness permission settings | scope and enforcement level |
| `{{RUNTIME_GUARD}}` | Runtime guard | catalog verification |
| `{{INLINE_STYLE_SCOPE}}`·`{{INLINE_STYLE_ALLOWED}}`·`{{INLINE_STYLE_CHECKED}}` | Inline-style ban | scope, allowed form, check |
| `{{INLINE_TYPE_SCOPE}}`·`{{INLINE_TYPE_ALLOWED}}`·`{{INLINE_TYPE_CHECKED}}` | Inline-type ban | scope, allowed form, check |
| `{{TYPE_ESCAPE_SCOPE}}`·`{{TYPE_ESCAPE_ALLOWED}}`·`{{TYPE_ESCAPE_CHECKED}}` | Type-escape ban | scope, allowed form, check |
| `{{COMMENT_SCOPE}}`·`{{COMMENT_CHECKED}}` | Comment ban | scope, check |

### 3.7 Product, process, and naming

| Placeholder | Meaning | Example |
| --- | --- | --- |
| `{{PROCESS_1}}`·`{{PROCESS_1_ENTRY}}`·`{{PROCESS_1_BOUNDARY}}` | Product process | launcher and game |
| `{{PROCESS_2}}`·`{{PROCESS_2_ENTRY}}`·`{{PROCESS_2_BOUNDARY}}` | Product process | second entry point |
| `{{DEV_BOUNDARY}}`·`{{PROD_BOUNDARY}}`·`{{RUNTIME_BOUNDARY}}` | Execution boundaries | boundary description |
| `{{DELIVERY_PIPELINE}}`·`{{DELIVERY_BOUNDARY}}` | Delivery pipeline | stages and boundary |
| `{{COMMAND_SOURCE}}` | Source that defines the commands | `package.json` |
| `{{LOG_OWNER}}`·`{{LOG_LOCATION}}` | Troubleshooting log | owner and location |
| `{{LAYER_OWNERSHIP}}`·`{{PRODUCT_DEFINITION}}`·`{{PERFORMANCE_DEFINITION}}`·`{{DELIVERY_DEFINITION}}`·`{{RENDER_COMPUTE_PLATFORM_DEFINITION}}` | Fixed decisions | the decision content |
| `{{RUNTIME_ARCHITECTURE_INTRO}}`·`{{EXECUTION_LINE_DEFINITION}}`·`{{HARDWARE_INTERFACE_DEFINITION}}`·`{{COMPUTE_LINE_DEFINITION}}`·`{{SELECTION_DEFINITION}}`·`{{PRESET_VALIDATION_DEFINITION}}`·`{{PLATFORM_LAYER_DEFINITION}}` | Execution, compute, platform | layer definitions |
| `{{VERSION_FORMAT}}` | Version format | `V<major>.<minor>.<patch>` |
| `{{LANG_1}}`·`{{LANG_1_FUNCTION_CASE}}`·`{{LANG_1_FILE_RULE}}`·`{{LANG_1_TYPE_CASE}}`·`{{LANG_1_TYPE_FILE_RULE}}` | Language 1 naming rules | TS |
| `{{COMPONENT_CASE}}` | Component naming | `PascalCase` |
| `{{LANG_2}}`·`{{LANG_2_FUNCTION_CASE}}`·`{{LANG_2_FILE_RULE}}` | Language 2 naming rules | C++ |
| `{{SHADER_FUNCTION_CASE}}` | Shader function naming | `lowerCamelCase` |

### 3.8 Records

| Placeholder | Meaning | Example |
| --- | --- | --- |
| `{{AUDIT_SESSION_RANGE}}`·`{{AUDIT_METHOD}}`·`{{AUDIT_RESULT}}` | Audit basis | target, method, result |
| `{{M01_BEHAVIOR}}`·`{{M01_EVIDENCE}}`·`{{M02_BEHAVIOR}}`·`{{M02_EVIDENCE}}`·`{{M03_BEHAVIOR}}`·`{{M03_EVIDENCE}}` | Banned recurring behavior | behavior and evidence |
| `{{TODO_ID}}`·`{{TODO_SOURCE}}`·`{{TODO_STATE}}`·`{{TODO_REMAINING}}`·`{{TODO_ACCEPTANCE}}` | Unfinished TODO row | id, verbatim source, state, remaining work, acceptance |
| `{{COMMIT_HASH}}`·`{{COMMIT_TIME}}`·`{{COMMIT_MESSAGE}}`·`{{COMMIT_SUMMARY}}` | Commit flow row | hash, time, message, summary |

## Apply order

1. **Place the files.** Copy this directory's files into the target project at the same relative positions. Put `conventions.md` at `{{CONVENTIONS_PATH}}`, the skills under `{{SKILL_ROOT}}`, and the model prompts under `{{INSTRUCTION_ROOT}}`.
2. **Fill identity and language.** Fill 3.1 and 3.3 first. The language contract decides the language of every other document.
3. **Fill paths and commands.** Fill 3.2 and 3.5. The cross-document links resolve from these values.
4. **Fill structure.** Fill 3.4. Replace the example tables in C02, C03, C04, C10, C17, C18, and C19 with project facts.
5. **Fill checks and enforcement.** Fill 3.6. Write the C16 enforcement table from real settings and checker files only.
6. **Reset the records.** Clear the example rows in `ai-tracking.md` and `session-audit.md` and start empty. Add S and M rows only when a real failure occurs.
7. **Connect the harness entry points.** Point each harness entry file (Claude, Qwen, Codex, Copilot) at `AGENTS.md` and the shared skill only. Put no independent rules in an entry file.
8. **Compare.** After filling, compare `conventions.md` ↔ `AGENTS.md` ↔ skills ↔ model prompts by clause number and confirm zero conflicts. Check that every link and anchor points at a real file.

## Maintenance rules

- Change a convention clause and fix `AGENTS.md`, the skills, and the model prompts in the same task so no conflict remains (C01).
- Never make an independent copy of the same rule. `AGENTS.md` and the skills are the clause sentences moved with their clause numbers; they are not independent rules.
- Manage a rule that exists only as a document with its violation evidence in the session audit, and move it to a mechanical enforcement measure when the same violation repeats (C16).
- When editing this template itself, do not rename a placeholder. The name is the contract.

## License

`harn` is released under the **harn Attribution-Redistribution License 1.0**. You may use, modify, and redistribute it freely, in source or another form, on one condition: the copyright notice, the copyright holder, and the license text must stay in place. Redistribution that removes, alters, or hides them is unauthorized and prohibited. See [LICENSE](LICENSE).
