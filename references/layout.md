# Layout Management

## When to use

Read this reference when you need to:
- split the workspace
- create space for a new service or log stream
- set up a dedicated pane for tests, backend, database, or browser work
- reorganize the workspace for multi-agent tasks

## General rules

- Prefer creating a new pane when the current pane must remain interactive.
- Keep long-running services in dedicated panes.
- Keep logs and active editing separated when possible.

## Split workflow

Use this when the user asks:
- "Open another pane"
- "Split the screen"
- "Create a pane for the database"
- "Put the server on the right and logs below"

Suggested process:
1. Determine whether the new pane should appear to the right or below.
2. Split the workspace.
3. Identify the new pane.
4. If needed, send startup commands into that pane.

## Example command patterns

```bash
cmux split --direction right
cmux split --direction down
cmux list-panes
```

## Layout conventions

Good default layouts:
- Backend dev: editor/main agent on left, app server on top-right, tests/logs on bottom-right
- Frontend debug: editor/main agent on left, dev server on top-right, browser or test runner on bottom-right
- Multi-agent: coordinator on left, worker agent on top-right, worker agent on bottom-right

## Constraints

- Do not keep splitting indefinitely; prefer readable layouts.
- Avoid changing the user's layout without reason.
- If all panes are busy, explain why a new pane is being created.

## Decision guide

- Need a second long-running process → split
- Need only a one-off quick command → use an existing idle pane
- Need clearer isolation between agents → split
