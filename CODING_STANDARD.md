# Coding Standard

## Priorities

- User experience, data accuracy, and data integrity come first. Nothing outranks them.
- Never trade them away for refactors, performance, or convenience.
- Verify every change against reality with real tests. No assumptions.

## Data Integrity

- No shallow caching: users see the complete session and the complete scope, never only the cached slice.
- Every statistic covers the full session and full scope, and reflects real content and real changes.
- Async, progressive loading is fine for first paint, but must never require extra user actions. Load or refresh more in the background automatically.

## Efficiency

- Make the smallest change that fully solves the problem, with the most efficient implementation.
- Keep code and tests small, modular, and loosely coupled. No duplication.
- Reuse existing test suites, cases, and assertions. Delete tests and code that are outdated or no longer needed.
- Reuse what DeepSeek Harness already provides: classes, utilities, styles, style tokens, events, presets, lifecycles.

## Comments

- Default to none.
- Write one only for a critical, non-obvious decision, constraint, or invariant the code cannot express. If you cannot name it, delete it.
- Never narrate what the code does, restate names or types, or explain your own change.
- While editing, delete or shrink comments that are obvious, redundant, or stale.

## Tests

- Reuse existing specs, suites, cases, and assertions. Drop tests no longer needed.
- Iterate with the narrowest run first:
  `pnpm exec vitest run tests/<area>/<name>.spec.ts -t "<case name>"` (regex, e.g. `"a|b"`).

## Verification

- `pnpm run check` must pass before commit: lint, typecheck, and 100% per-file coverage.
- Fix every failure. Never suppress, skip, or lower a gate.

## Language

- English only: code, comments, tests, docs, PR descriptions, commit messages.

## Temporary Files

- Create them only in `./.tmp`.
- Delete them immediately after use.

## File Size

- Every source and test file stays under 1000 lines.
