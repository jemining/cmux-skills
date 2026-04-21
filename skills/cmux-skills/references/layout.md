# Layout Management

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
# Split the current pane in a direction (shorthand)
cmux new-split right
cmux new-split down

# Create a new independent pane (not tied to current pane's split axis)
cmux new-pane [--direction <left|right|up|down>]

# List and focus
cmux list-panes
cmux focus-pane --pane <PANE_ID>
```

Use `new-split` when you want to divide the current pane. Use `new-pane` when you want a new pane added to the workspace independently.

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
