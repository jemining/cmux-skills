---
name: cmux
description: Use this skill when the user explicitly mentions cmux, or when working inside a cmux workspace and the task involves interacting with panes, the cmux browser, or cross-pane coordination. Do NOT invoke for generic terminal, shell, or browser tasks outside of the cmux environment.
---

# cmux

Use this skill only when the task explicitly involves the cmux terminal environment — pane inspection, cross-pane commands, layout management, or the cmux browser surface.

## ⛔ Before reading any reference file

Classify the request first. Read exactly one file that matches. Do not read multiple files at once.

| Request type | Read only |
|---|---|
| Inspect logs, errors, or output in another pane / send a command to a pane | `references/panes.md` |
| Split workspace, create panes, manage layout | `references/layout.md` |
| Inspect frontend UI, browser snapshot, visual verification | `references/browser.md` |
| Coordinate multiple agents or sessions across panes | `references/workflows.md` |
| Something is not working, recovery, diagnosis | `references/troubleshooting.md` |

If the classification is ambiguous, pick the single most likely file. Do not read multiple files as a fallback.

## cmux concepts

- **Window**: A top-level application window.
- **Workspace**: A working context inside a window.
- **Pane**: A visible split region in the workspace.
- **Surface**: A concrete terminal or browser surface that can be targeted for reading or interaction.

Tasks usually operate at the **pane** or **surface** level.

## Operating principles

- Read one reference file per task. Stop after reading it.
- Do not claim that you cannot access another pane until you have checked the relevant reference.
- Do not invent pane IDs, surface IDs, browser state, or logs.
- When the task depends on live terminal state, inspect it first and then act.
- Always inspect before acting when the task depends on runtime state.
- Prefer explicit, reversible actions.
