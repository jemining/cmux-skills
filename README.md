# cmux-skills

A skill for AI coding assistants working inside the [cmux](https://cmux.dev) terminal environment.

## What it does

Enables AI assistants to interact with the cmux workspace:

- Inspect logs and output from other panes
- Send commands to background panes
- Create and manage pane layouts
- Inspect the integrated browser surface
- Coordinate multi-agent workflows across panes

## Installation

Add this repository as a marketplace:

```
/plugin add-marketplace jemining/cmux-skills
```

Then install the skill:

```
/plugin install cmux-skills
```

## Usage

Once installed, your AI assistant will automatically invoke this skill when you ask it to:

- "Check the error in the right pane"
- "Restart the server in another pane"
- "Split the screen and start the dev server"
- "Inspect the UI in the browser"
- "Coordinate agents across panes"

## Structure

```
cmux-skills/
└── skills/
    └── cmux-skills/
        ├── SKILL.md                  # Skill entry point
        └── references/
            ├── overview.md           # Core concepts and safety rules
            ├── panes.md              # Reading and writing to panes
            ├── layout.md             # Splitting and managing pane layouts
            ├── browser.md            # Browser surface inspection
            ├── workflows.md          # Multi-agent workflow patterns
            └── troubleshooting.md    # Common failures and recovery steps
```

## Requirements

- [cmux](https://cmux.dev) terminal environment
