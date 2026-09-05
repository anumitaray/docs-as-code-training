# Step 2: Ask Cursor to Explain Your Codebase

> Part of the [Cursor Quickstart Guide](./quickstart.md)

After you select and open your project folder in Cursor, launch the Agent pane:

- **macOS**: `Cmd + I`
- **Windows / Linux**: `Ctrl + I`

## Recommended Exploration Prompt

Copy and paste the following prompt into Agent:

```text
Explain this codebase. Point me to the main entry points, key modules, and anything I should read before making changes.
```

## How Cursor Analyzes Your Project

When you submit this prompt, Cursor will:
1. **Search your repository**: Utilizes semantic codebase indexing to trace entry points and import trees.
2. **Read key files**: Identifies configuration manifests, routing tables, and core domain modules.
3. **Synthesize an architecture summary**: Outlines how the project fits together, highlighting critical files and recommended reading order.

This is one of the fastest and most reliable ways to get oriented in an unfamiliar or legacy repository.

---
*For a deeper walkthrough, see the official guide: [Understand your codebase](https://cursor.com/learn/understanding-your-codebase).*
