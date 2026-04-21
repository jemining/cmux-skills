# cmux-skills

A skill for AI coding assistants working inside the [cmux](https://cmux.dev) terminal environment.

## What it does

Enables AI assistants to interact with the cmux workspace:

- Inspect logs and output from other panes
- Send commands to background panes
- Create and manage pane layouts
- Automate the integrated browser surface (navigate, click, type, snapshot, eval, and more)
- Coordinate multi-agent workflows across panes

## Usage

Once installed, your AI assistant will automatically invoke this skill when you ask it to:

- "Check the error in the right pane"
- "Restart the server in another pane"
- "Split the screen and start the dev server"
- "Inspect the UI in the browser"
- "Navigate to a URL and check the result"
- "Click the submit button and verify the response"
- "Coordinate agents across panes"

## Structure

```
cmux-skills/
└── skills/
    └── cmux-skills/
        ├── SKILL.md                  # Skill entry point — includes cmux concepts and reference routing table
        └── references/
            ├── panes.md              # Reading output and sending commands to panes
            ├── layout.md             # Splitting and managing pane layouts
            ├── browser.md            # Browser surface inspection
            ├── workflows.md          # Multi-agent workflow patterns
            └── troubleshooting.md    # Common failures and recovery steps
```

`SKILL.md` contains a routing table that maps each request type to exactly one reference file. The AI reads only the matched file, not all references. cmux core concepts (Window, Workspace, Pane, Surface) are inlined in `SKILL.md` so no extra file read is needed for orientation.

## Requirements

- [cmux](https://cmux.dev) terminal environment
