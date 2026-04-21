# Browser Inspection

## Browser workflow

Use this when the user says:
- "Check the page"
- "See if the button is aligned"
- "Inspect the UI after the fix"
- "Look at the frontend output"

Suggested process:
1. Ensure a browser surface exists.
2. Capture a browser snapshot.
3. Inspect visual state, text, or errors.
4. If needed, update code.
5. Re-check after changes.

## Example command patterns

```bash
# Open a browser surface
cmux browser open <url>
cmux browser open-split <url>          # open in a split pane

# Navigation
cmux browser <surface> navigate <url>
cmux browser <surface> reload
cmux browser <surface> back
cmux browser <surface> forward
cmux browser <surface> url            # get current URL

# Snapshot / inspection
cmux browser snapshot -i              # interactive snapshot
cmux browser <surface> snapshot --compact
cmux browser <surface> screenshot --out <path>

# Wait for page state before acting
cmux browser <surface> wait --load-state complete
cmux browser <surface> wait --selector <css>
cmux browser <surface> wait --url-contains <text>

# Interact with elements
cmux browser <surface> click --selector <css>
cmux browser <surface> type --selector <css> --text <text>
cmux browser <surface> fill --selector <css> --text <text>
cmux browser <surface> scroll --selector <css> --dy <n>

# Read page content
cmux browser <surface> get url
cmux browser <surface> get title
cmux browser <surface> get text --selector <css>

# Console and errors
cmux browser <surface> console list
cmux browser <surface> errors list

# Run JavaScript
cmux browser <surface> eval <js>
```

## What to look for

- Missing elements
- Incorrect text
- Broken layout
- Console-visible failures reflected in UI state
- Styling regressions
- Wrong route/page state

## Constraints

- Do not infer exact pixel-perfect layout from code alone.
- Re-check after CSS or frontend logic changes.
- If no browser surface exists, say so and suggest creating one.
