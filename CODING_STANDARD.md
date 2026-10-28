## Principles
- User Experience
- Data Accuracy & Integrity
- Code Efficiency

- User experience, features, and especially the data accuracy and integrity are the top priority. Never sacrifice them for code refactors, performance, or any other reason. Dive deep and run real tests to verify the correctness of every change.

## Data Integrity
- 反对“浅缓存”，也就是只允许用户访问和用到缓存的数据而不是整个会话或者整个范围的内容
- 所有统计指标必须有效覆盖整个会话、整个范围，准确反映整个会话的内容和变化，而不是只反映缓存的部分内容
- 支持为了首次加载而采取异步、渐进式加载的方式，但不得引入用户额外触发的动作，倾向于在后台自动加载更多或者更新，保证用户看到的内容是完整、准确、最新的

## Efficiency
- Make the minimal change that fully solves the problem, with the most efficient implementation.
- Keep code and tests small, loosely coupled, and modular; avoid duplication. Reuse existing test suites, cases and assertions where possible. Drop and shrink any code or test that is outdated and no longer needed.
- Reuse the classes, utilities, styles, style tokens, events, presets, and lifecycles that DeepSeek Harness already provides.

## Comments in Source Code
- Always default to none. Try to skip or cleanup all comments in source code.
- Never add one unless it records a critical, non-obvious decision, constraint, or invariant the code cannot express — if you cannot name that reason, do not write it.
- Never narrate what the code does, restate names or types, or explain the change you just made.
- When touching code, delete or shrink comments that repeat the code, state the obvious, or are outdated; reducing the comment as much as possible.

## Tests
- Try to reuse existing test suites, cases and assertions where possible. Drop and shrink any test that is outdated and no longer needed.

## Test Validation
- Minimized test runs first for every test changes in place
  - firstly run `pnpm exec vitest run tests/<area>/<name>.spec.ts -t "<test case name>"` (regex, use `"a|b"`) to iterate on the touched test cases.

## Language
- English only for all code, comments, tests, documentation, PR descriptions, and commit messages.

## Temporary Files
- Generate one-time temp files ONLY in the `./.tmp` directory
- Clean them up right after use as soon as possible.

## Contracts
- <1000 lines for ALL source code/test files.