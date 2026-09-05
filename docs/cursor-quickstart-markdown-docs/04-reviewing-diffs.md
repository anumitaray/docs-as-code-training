# Step 4: Review the Diff and Verify the Result

> Part of the [Cursor Quickstart Guide](./quickstart.md)

As Cursor executes your request, you can watch the changes happen in real time. The interactive diff viewer highlights all edits proposed by the agent across the project.

## Verification Checklist

1. **Review the Diff View**:
   - Inspect green lines (additions) and red lines (deletions).
   - Ensure the agent respected project conventions and style guides.
2. **Run Verification Commands**:
   - Once Cursor finishes editing, instruct it to run the verification tools your project uses:
     - **Tests**: `npm test`, `pytest`, `cargo test`, `go test ./...`
     - **Type Checker**: `tsc --noEmit`, `mypy .`
     - **Linter & Formatter**: `eslint .`, `ruff check .`, `biome check .`
     - **Build**: `npm run build`, `make build`

---
*Want a stronger review workflow? See the official guide: [Reviewing and testing code](https://cursor.com/docs/agent/review).*
