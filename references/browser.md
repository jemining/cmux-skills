# Browser Inspection

## When to use

Read this reference when you need to:
- inspect a frontend rendered inside the cmux browser
- verify whether a UI change is visible
- inspect browser-side errors
- confirm layout, text, or interaction outcomes

## General rules

- Prefer browser inspection for questions about visual results.
- Do not claim the UI is correct without checking the browser state.
- Distinguish browser observations from code assumptions.

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
cmux browser snapshot -i
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
