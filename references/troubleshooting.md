# Troubleshooting

## Problem: Cannot find the right pane

Possible causes:
- The workspace has multiple similar panes.
- The relevant process was restarted in a different pane.
- The pane contains a shell prompt rather than the expected process.

Response:
1. Re-list panes.
2. Inspect likely candidates.
3. Match by observed output, not assumption.

## Problem: The pane output is too large

Response:
- Inspect only the most relevant part first.
- Focus on recent output, stack traces, or error sections.
- Avoid loading massive buffers unless necessary.

## Problem: A background command may not have started correctly

Response:
1. Re-capture the pane.
2. Look for crash output, port conflicts, missing env vars, or dependency failures.
3. Report the observed failure mode before retrying.

## Problem: Browser state is unavailable

Response:
- Confirm whether a browser surface exists.
- If not, explain that visual verification cannot proceed until a browser surface is available.

## Problem: Multiple agents are stepping on each other

Response:
- Separate responsibilities by pane.
- Dedicate panes to runtime, logs, and coordination.
- Use verification steps after each change instead of assuming consistency.
