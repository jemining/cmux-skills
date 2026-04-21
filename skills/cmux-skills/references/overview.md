# cmux Overview

## Purpose

cmux is a terminal environment optimized for multitasking and agent-oriented workflows. It supports splitting the workspace into multiple panes, reading output from other panes, sending commands into those panes, and working with an integrated browser surface.

## Core concepts

- **Window**: A top-level application window.
- **Workspace**: A working context inside a window.
- **Pane**: A visible split region in the workspace.
- **Surface**: A concrete terminal or browser surface that can be targeted for reading or interaction.

In practice, tasks usually operate at the **pane** or **surface** level.

## Safety rules

- Always inspect before acting when the task depends on runtime state.
- Do not assume a pane contains what the user expects; verify first.
- Avoid long blocking work in the current interactive pane when another pane can be used.
- Prefer explicit, reversible actions.

## Common task mapping

- Need logs from another pane → see `panes.md`
- Need to start a service in background → see `panes.md` and `layout.md`
- Need to reorganize workspace → see `layout.md`
- Need to inspect frontend output → see `browser.md`
- Need coordinated multi-agent work → see `workflows.md`
