# Working with Panes

## Discovery workflow

When you need to work with another pane:

1. Identify available panes or surfaces.
2. Determine which target is most likely relevant.
3. Inspect the target contents.
4. Act only after confirming the target.

## Read workflow

Use this workflow when the user says things like:
- "Check the error in the right pane"
- "See what the backend server is doing"
- "Read the output from the test pane"

Suggested process:
1. List panes/surfaces.
2. Capture text from the candidate pane.
3. If multiple panes are plausible, compare briefly and choose the one that matches the user's intent.
4. Analyze the captured output.
5. Report findings or fix the issue.

## Execute workflow

Use this workflow when the user says:
- "Restart the server in another pane"
- "Run tests in the background"
- "Start the watcher in a separate pane"

Suggested process:
1. Identify an idle or dedicated pane.
2. Send the command to that pane.
3. Wait briefly.
4. Re-read the pane output.
5. Confirm success or report failure.

## Recommended command patterns

These are examples. Adjust to the user's environment.

```bash
# Discovery
cmux list-panes
cmux list-pane-surfaces [--pane <PANE_ID>]
cmux identify [--surface <SURFACE_ID>]
cmux tree [--all]

# Read output
cmux read-screen --surface <SURFACE_ID> [--scrollback] [--lines <n>]

# Send commands
cmux send --surface <SURFACE_ID> "npm run dev"
cmux send-key --surface <SURFACE_ID> Enter
```

## Verification pattern

After running a background command:
1. Wait a short time.
2. Capture the target pane again.
3. Look for success indicators, prompts, stack traces, port-binding errors, or crash messages.

## Constraints

- Do not invent output that has not been captured.
- Do not use another pane blindly for destructive commands.
- Avoid interactive full-screen commands unless the user explicitly wants them.
- If the pane contents are huge, inspect the most relevant tail or error segment first.

## Good behaviors

- State which pane/surface you inspected.
- Distinguish between observed facts and assumptions.
- Prefer incremental diagnosis over large speculative changes.
