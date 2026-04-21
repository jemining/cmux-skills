---
name: cmux
description: Use this skill when working inside cmux to inspect other panes, capture terminal output, send commands to background panes, manage pane layouts, or inspect the built-in browser. Especially useful for multi-agent workflows, debugging logs, frontend verification, and orchestration across panes.
---

# cmux

Use this skill when the task involves the cmux terminal environment.

Typical cases:
- The user asks you to inspect logs or errors in another pane.
- The user asks you to start or restart a service in a different pane.
- The user asks you to split the workspace or manage panes.
- The user asks you to inspect a frontend/UI rendered in the cmux browser.
- The user asks you to coordinate multiple agents or sessions inside the same cmux workspace.

## Operating principles

- Prefer reading only the minimum reference needed for the current task.
- Do not claim that you cannot access another pane until you have checked the cmux references.
- Do not invent pane IDs, surface IDs, browser state, or logs.
- When the task depends on live terminal state, inspect it first and then act.

## References

- For a quick mental model of cmux concepts, read `references/overview.md`
- For reading output from another pane, read `references/panes.md`
- For creating/splitting panes and layout operations, read `references/layout.md`
- For browser snapshots and UI inspection, read `references/browser.md`
- For common multi-agent operating patterns, read `references/workflows.md`
- For common failures and recovery steps, read `references/troubleshooting.md`
