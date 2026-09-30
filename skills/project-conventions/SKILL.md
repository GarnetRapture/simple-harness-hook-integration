---
name: project-conventions
description: "Start: authorized {{PROJECT_NAME}} work. Apply the shared evidence-bound workflow. End: requested result and fixed verification, or an observed external dependency."
---

# {{PROJECT_NAME}} Shared Workflow

> **Template note.** Replace every `{{...}}` placeholder with the project value; the placeholder list is owned by the README.md in this template directory. The gate structure and the normative sentences are the harness philosophy and process, so keep them.

This skill details the procedure in AGENTS section 2 under [{{CONVENTIONS_PATH}}]({{SKILL_TO_ROOT}}{{CONVENTIONS_PATH}}), the core definition document. It adds no authority, exception, or stopping condition. Every section names the convention clauses it applies.

## Authority (C00, C01)

| Start gate | Action | End gate |
| --- | --- | --- |
| This skill applies | Follow [AGENTS]({{SKILL_TO_ROOT}}AGENTS.md) and [conventions]({{SKILL_TO_ROOT}}{{CONVENTIONS_PATH}}) under the latest user instruction | No skill grants scope, exception, installation, or stopping authority |
| Another harness or specialty skill applies | Use this same workflow and the specialty only for its affected boundary | No restart of gates or competing verification policy |
| An action is being selected | Bind it to a 1:1 evidence proposition with who, what, when, where, why, and how | Exact authority, target, method, lifecycle, and expected result are established |
| Any read, search, edit, command, wait, message, or completion is proposed | Check [conventions]({{SKILL_TO_ROOT}}{{CONVENTIONS_PATH}}) C00 through C20 one clause at a time for that exact action. Retain O, X, or ? and the evidence for each clause in the existing working context; for a clause outside the action's scope, retain the exact scope reason. Resolve every applicable X or ? by obtaining the missing fact or correcting the action before using the tool or making the claim (C00, C09, C14) | Every applicable clause is O for the action; no bundled judgment substitutes for an individual clause check |
| A tool call, judgment, mutation, or completion is proposed | Apply its entry conditions before acting and assess its result afterward; do not turn gates into a response template | Concrete prerequisites and acceptance govern execution |
| A document priority or a shared record write is decided | Project-internal Markdown ([conventions]({{SKILL_TO_ROOT}}{{CONVENTIONS_PATH}}), [tracking]({{SKILL_TO_ROOT}}{{TRACKING_PATH}}), [session audit]({{SKILL_TO_ROOT}}{{AUDIT_PATH}})) and the project skills are the primary authority, and the external record system is reference and record support used only when needed; an external-only rule is not a behavior authority until it is written into the internal documents (C01) | The internal document wins and the external record stays supplementary |

## Philosophy: shared decisions across models (C00, C14)

| Start gate | Principle and reason | End gate |
| --- | --- | --- |
| A requirement seems optional, deferrable, reducible, or too costly in tokens, time, or effort | The user is the final superior who owns scope and priority, and the executor carries out every recorded requirement with no authority to cite token volume, cost, workload, time, context length, or difficulty (C00 role), because executor-side reduction hides omissions from the owner and shifts re-instruction cost to the owner | No stop, deferral, partial execution, reinterpretation, substituted approach, self-invented alternatives such as plan A / plan B, or distortion of the instruction (C00) |
| A reasoning link lacks evidence | Only reasoning whose every link is established by evidence may justify an action (C00, C09) | The next action obtains the missing fact; no guess fills the link |
| Any model takes the task | The user's requirement determines the outcome; model preference cannot become a competing objective because changing the goal makes the result answer a different request | The same requirement remains binding across every model and human developer |
| A model selects an action | Use the same current instruction, authoritative owner, input identity, and evidence; model familiarity and confidence do not establish correctness | Another model or developer can identify the same justified action from the same recorded premises |
| A correction is proposed | A correction is right only when it repairs the demonstrated violated contract and preserves the required producer-to-consumer behavior | The reason for the change and its observable acceptance are explicit |
| A statement is treated as a proposition | State something whose truth or falsity can be checked against an exact source or result; vague labels cannot distinguish success from failure | A concrete confirming observation or counterexample can decide the statement |
| Evidence is used for authority | Separate normative premises from factual premises: the user authorizes what must happen, while source and results establish what does happen | Technical plausibility does not grant permission, and permission does not prove implementation |
| A complete result is claimed | Every required causal connection must agree because one broken producer, selector, consumer, or lifecycle can invalidate the visible result | No percentage, majority, subset, or local pass substitutes for the requested whole |
| Models disagree | Locate the exact differing premise, source revision, input, or contract and resolve it through direct evidence | No model vote, reputation, self-authored rule, or historical assertion settles correctness |
| A failure occurs | Keep the same authority and evidence obligations because failure is information about the method, not permission to invent a new goal | Recovery preserves the user's outcome and all still-valid evidence |
| A warning, error, or disconnected item appears | Treat it as critical evidence of a required unresolved connection; apparent age or lack of callers cannot justify erasing required implementation | Diagnosis leads to the causal owner and complete repair |
| A practice is described as standard | Identify the exact official source and applicability, or label it as a user rule, project choice, observation, or proposal | No unsupported claim that the industry or other developers require the model's choice |
| Shared instructions are edited | Keep definitions in the conventions (the core), behavior and the always-on procedure in AGENTS, and detailed procedures in this skill, because duplicate authorities can direct different models to incompatible actions | All harness entry points resolve to the same owners without asserting automatic enforcement |

## Ordered work cycle (C14, C15)

| Start gate | Action | End gate |
| --- | --- | --- |
| G1: a user request or compatible correction exists | Record every atomic requirement verbatim with its target and acceptance (AGENTS 2.2); retain the exact outcome, scope, location, method, order, and fixed verification; use the newest tracking summary, the open session-audit TODO rows, and retained context | G1: one current task, zero unrecorded requirements, explicit acceptance |
| G2: the target is fixed | Attach the exact user requirement or observed violated invariant to that target | G2: a direct proposition explains why the action is necessary |
| G3: purpose is established | Read only unresolved input→producer→owner→boundary→consumer connections | G3: cause, selector, required inputs, and observable result are identified |
| G4: the affected connection is known | Establish initialization, async completion, replacement, cancellation, teardown, and failure timing that affect it | G4: ownership and lifecycle are explicit; inapplicable boundaries have a concrete reason |
| G5: G1–G4 are satisfied and every step of the change decision procedure (C14, AGENTS 2.3.5) is recorded through step 7 | Implement the coherent correction at the owner and affected interfaces; retain its rationale and the procedure record for the session-end tracking entry | G5: the authorized change is connected and its rationale retained |
| G6: the change exists | Backward check: trace every change and result to its requirement or convention clause, and compare its behavior against the fixed target, reason, and causal path | G6: zero inventions, no unexplained behavior or scope drift |
| G7: alignment is established | Close the retained list of affected callers, declarations, schemas, bindings, configuration, and checks | G7: only unanswered or newly affected dependencies remain eligible for investigation |
| G8: affected owners are known | Complete registration, imports, selectors, producers, consumers, and lifecycle cleanup | G8: the actual selected path consumes the result |
| G9: the connected change is ready | Forward check: confirm every recorded requirement has the result and acceptance evidence of its C07 process type (implementation and observation only for implementation and FIX); then perform only the fixed required checks (AGENTS 2.5) after all requested items are implemented | G9: zero omissions, zero unresolved errors/warnings in required checks, with runtime evidence limited to exercised paths |
| G10: required checks are resolved | Compare shared types, utilities, state, and rules with their canonical owners using retained evidence | G10: no duplicate owner; requested acceptance is supported |
| Later evidence contradicts an earlier gate | Reopen only the contradicted fact and its affected connections | Unaffected facts and passed checks remain retained |

## Six-question proposition (C09)

| Start gate | Action | End gate |
| --- | --- | --- |
| Any action is proposed | Retain: who acts and owns the boundary; what operation and result; when in the lifecycle; where exactly; why this requirement; how through the supported invocation | One direct evidence-to-action proposition, without set arithmetic |
| An action has several independent effects | Assign each effect its own proposition while sharing established facts | No authorization is inferred from another action's success |
| A premise is missing | Read the specific owner, configuration, or tool metadata that answers that missing question | The next implementation or invocation has its required basis |
| A conclusion appears correct | Tie the exact requirement to the owner, implementation, consumer, and observed result, explaining why each connection supports the next | The conclusion has a complete direct evidence chain |
| A conclusion appears incorrect | Identify the contradicting input, source behavior, or observed result and the violated requirement | Rejection has factual counterevidence rather than a heuristic label or omitted evidence |
| A connection does not agree | Correct its causal owner and rerun only the affected required verification | The mismatch is resolved without weakening acceptance or restarting unrelated checks |
| Cause and correction are already established through all seven steps of the change decision procedure | Implement immediately unless a new contradiction changes that correction | No confidence-seeking analysis loop |

## Change decision procedure (C14, AGENTS 2.3.5)

Every change to code, data, tools, or documents passes these steps in order. A step whose record is empty blocks the change and makes that step's fact the next action (C00); it never becomes a stopping condition for the task.

| Start gate | Action | End gate |
| --- | --- | --- |
| D1: an issue is observed | Lay out the operating order of the whole pipeline that produces the observed result, from source data through producer tools, `{{MANAGED_ASSET_ROOT}}/`, loaders, runtime owners, low-level execution, and output; identify the exact step number where the issue is detected | D1: the issue has one step number in a complete, source-backed pipeline order |
| D2: the step is fixed | List the entire range of effects that changes when that step is modified: every producer, consumer, shared type, selector, binding, lifecycle, and screen that reaches it | D2: the effect range is enumerated from source, not from the single issue |
| D3: the effect range is enumerated | For every item, state whether the change affects it or not, why the change must be made that way, and, if it is wrong, why it is wrong | D3: every item has an affected or unaffected verdict with its reason |
| D4: candidate directions exist | Check C00 through C20 one clause at a time for each approach direction, including clauses that do not apply with the exact source-backed reason. Record O, X, or ? for each clause; select the direction with the most O only among directions without an unresolved X | D4: one direction is selected with its complete clause-by-clause judgment retained |
| D5: a direction is selected | Perform the measurement that proves the approach: original data comparison, owning tool output, or runtime observation | D5: measured evidence exists for the approach |
| D6: measurement exists | Confirm or reject the judgment from the measured result; a rejection returns to D4 with the counterexample | D6: the judgment is confirmed by measurement |
| D7: the judgment is confirmed | Recheck C00 through C20 one clause at a time against the measured result and affected producer-to-consumer path. Resolve every X and ? before executing the change; a nonapplicable clause needs its exact scope reason | D7: every applicable clause is O; the change proceeds to G5 |
| One issue suggests a hypothesis | Treat the hypothesis only as input to D1–D3; never implement it before D7 | No implementation from a single-issue hypothesis |

## FIX and tool recovery (C06, C12)

| Start gate | Action | End gate |
| --- | --- | --- |
| A failure occurs | Retain command/tool, arguments, cwd, input identity, diagnostics, exit status, and affected requirement | Failure evidence is available without rerunning it |
| Any warning or error appears | Record it as critical and trace trigger, violated contract, owner, and affected consumers | No filtering, downgrade, suppression, or dismissal as pre-existing |
| An unused, undefined, or disconnected item appears | Trace declaration, production, selection, registration, import, caller, and lifecycle to the missing required connection | The implementation gap is identified; deletion and legacy labels cannot substitute for repair |
| The trigger is known | Compare expected and observed values through the affected producer and lifecycle | The earliest demonstrated invariant violation and responsible owner are identified |
| Multiple causes remain possible | Use a bounded observation that distinguishes their predicted results | The correction is based on evidence, not the most recent log line |
| The owner and cause are established | Correct the owner and all affected declarations, callers, schema, data, bridge, and cleanup together | A complete causal correction is ready for its affected check |
| A boundary guard or recovery is needed | Match it to an independently established external failure contract | Required behavior is preserved; internal defects remain visible |
| A path or executable fails | Classify resolution, cwd, quoting, arguments, input, access, or actual absence; correct from authoritative configuration | A changed supported invocation addresses the demonstrated cause |
| An owning production, sync, or check tool fails or lacks a capability | Fix the cause inside that owning tool (C12 tool integration, AGENTS S19) and rerun it through its canonical entry point; `{{TEMP_ROOT}}/` scripts may only read facts | No runner, wrapper, or duplicate script calls the tool's internals with changed arguments or skips its failing step |
| An operation is denied | Preserve the rejection and continue independent authorized work | No alternate mechanism bypasses the denial |
| A required check failed and its cause changed | Rerun only that failed or invalidated required check unless the user prohibits it | The changed boundary has honest acceptance evidence |
| A user corrects behavior | Identify the preceding action, violated instruction, affected artifacts, and replacement action | The replacement is executed without cancelling the unfinished objective |

## Process-specific application (C07, C12, C13)

| Start gate | Action | End gate |
| --- | --- | --- |
| Implementation or FIX is authorized | Apply G1–G10 to the named behavior and actual consumer | No unselected variant is counted as integration |
| Review only is authorized | Trace the bounded reachable path and report location, trigger, violated contract, impact, and minimum correction | No unauthorized edits or speculative findings |
| Source investigation is authorized | Query only task-relevant original evidence and label inference | The concrete question is answered without initiating unrequested extraction or reverse engineering |
| Extraction, conversion, or bulk I/O is authorized | Establish input count/bytes from available metadata, producer, consumer, destination, required passes, concurrency, and output growth | The bounded run produces the specified contract without redundant traversal or uncontrolled fan-out |
| Reverse engineering is explicitly authorized | Create and run the task-specific script with the installed reverse-engineering tool ({{RE_TOOL}}) | Only task-relevant evidence is returned |
| Source changes are ready | Run `{{CHECK_COMMAND}}` from the project root and retain full diagnostics under `{{TEMP_ROOT}}/` | The integrated checker reports error 0 and warn 0 |
| Low-level changes are ready | Apply the ownership/ABI/lifecycle criteria and run `{{BUILD_COMMAND}}` from the root, then the affected authorized runtime path | Compiler/linker diagnostics and runtime evidence remain distinct |
| An explicit release build is required | Complete connected changes and required static validation, then run `{{RELEASE_BUILD_COMMAND}}` from the root | The current artifact is produced without warnings or errors |
| A full build is proposed | Require an explicit user requirement or affected integration contract requiring that breadth | Full builds do not discover design or chase successive compiler errors |
| Runtime, low-level, shader, UI, or observable work is active | Check `{{RUNTIME_STATUS_TOOL}}`, start a session with `{{RUNTIME_START_TOOL}}` if none runs (it refreshes the managed-asset catalog and the program packs first), keep it running for the whole task, and observe the product window with `{{RUNTIME_OBSERVE_TOOL}}` and the separate debug window with `{{RUNTIME_DEBUG_TOOL}}` before and after each controlled input | Same-session screen, debug snapshot, logs, and metrics answer the fixed question |
| Human runtime input is active | Yield agent input and preserve the running session | Human control is uninterrupted |
| Relevant code changes during a runtime task | Allow the required reload/build lifecycle and observe only the affected result | Old frames are not used as evidence for new code |
| Document or harness changes are requested | Edit the canonical owner and route consumers; check language, gates, 1:1 evidence rules, local links, ownership, and contradictions once | Document acceptance only; no application run or enforcement claim |
| Artifact cleanup is explicitly requested | Resolve identified obsolete producer outputs and approved host target bounds, then use literal-path operations | Only the authorized obsolete artifacts are removed |
| A commit is explicitly requested | Inspect the exact staging targets and applicable ignore rules, use the one commit message the user gives verbatim, and keep the author and committer unchanged with no AI co-author trailer | Authorized source/config/docs only; no hook bypass, unsolicited commit, or author change |
| A push fails or a large file is staged | Identify the blocking guard from its own output; for a size guard, untrack the file that exceeds the configured limits, keep it covered by the backup, then commit and push the single message to the remote | The push reaches the remote and the large file is preserved in the backup |
| A version change is explicitly requested | Use `{{VERSION_COMMAND}}` and its existing consumers | Version values agree without hand-edited copies |

## State, history, and delivery (C15)

| Start gate | Action | End gate |
| --- | --- | --- |
| A session resumes, including after compaction | Before the first action, read {{CONVENTIONS_PATH}} and this skill in full (AGENTS section 0, rule 6); treat a compaction summary as history, not an instruction; apply the latest request, read the newest tracking summary and the open session-audit TODO rows, preserve valid settled facts, and resume the first applicable unfinished action | The resumed work continues the same objective with retained evidence |
| The GOAL is complete | Write the session summary in the C15 format, then immediately compare it with the conventions clause by clause and redo any violated work; write no tracking session summary, worklog, or handoff before completion; update the tracking commit-flow section only when the user orders it (C15) | Another developer can trace every requirement and its evidence without interrogating the previous model; no invented historical facts |
| A log, tracking, or record needs a time | Run `{{TIME_TOOL}}` for the current {{JOURNAL_TIMEZONE}} value and use that value instead of computing the time zone by hand (C12, C15) | Journal times come from the single time source |
| Existing history is summarized | Preserve every dated entry and same-date order, distinguish earlier failure from later repair, and retain explicit unverified boundaries | A concise trend remains without fabricating a pass or rewriting past architecture as current |
| Unfinished requirements must survive the session | Only when the user orders a TODO update, or an observed external dependency, a governing constraint, or the user ending the session leaves a requirement unfinished (C15), keep each as its own row in the session-audit TODO; never create a handoff, plan, or second ledger | The next session has the objective, owner, evidence, remaining work, and fixed acceptance |
| A process remains running | Use its existing handle and supported wait/completion mechanism; perform independent work when possible | No duplicate run and no premature completion |
| An executable authorized action remains | Perform the first unfinished dependent action | No final response substitutes for execution |
| Every remaining path has an observed external dependency | Finish independent work and report the exact dependency and preserved requirement | No invented stop condition or false completion |
| Requested acceptance is satisfied | Deliver a short {{USER_LANGUAGE}} result in the fixed tone ({{RESPONSE_TONE}}, C15) with concrete evidence and exact unverified boundaries | No gate wrappers, discretionary recheck, or unsupported claim of harness enforcement |
