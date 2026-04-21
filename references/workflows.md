# Multi-Agent Workflows

## Goal

Use cmux to coordinate multiple agents or tasks in a structured way without relying only on static files.

## Recommended patterns

### 1. Read-from-pane pattern

Use when one pane contains logs or runtime output and another pane is the active reasoning/editing pane.

Flow:
1. Discover panes.
2. Capture the target pane's text.
3. Summarize the findings.
4. Make changes in the active pane.
5. Re-run or re-check.

Best for:
- backend debugging
- test failure diagnosis
- runtime error investigation

### 2. Background-service pattern

Use when the main pane must remain interactive.

Flow:
1. Create or identify a dedicated service pane.
2. Start the service there.
3. Return to the main pane.
4. Inspect the service pane when errors occur.

Best for:
- Node.js dev server
- test watch mode
- local DB or tunnel processes

### 3. Verify-after-change pattern

Use when code changes affect runtime or UI behavior.

Flow:
1. Make code changes.
2. Trigger build/test/server restart in a target pane.
3. Read the pane output.
4. If frontend-related, inspect browser state.
5. Report only verified results.

### 4. Coordinated-agent pattern

Use when multiple agents share one workspace.

Recommended pane roles:
- Pane A: primary coordinator agent
- Pane B: backend or service execution
- Pane C: testing, logs, or secondary worker
- Optional browser surface: visual verification

Rules:
- Use runtime panes as evidence sources.
- Use the coordinator pane for planning and code edits.
- Verify any claimed fix against the pane or browser that demonstrates the issue.

## Anti-patterns

Avoid:
- claiming another pane is inaccessible before checking
- making large speculative edits without reading runtime output
- overusing file-based handoff when a live pane already contains the needed evidence
- mixing too many responsibilities into one pane
