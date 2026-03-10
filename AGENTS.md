# AGENTS.md

## Project
- Name: Portfolio
- Description: My Portfolio website
- Language: javascript
- Language version: ES2023 / Node 22
- Framework: Vue
- Deploy with Docker: no
- Database: none
- Stack: Vuejs
- Primary IDE: vscode
- Enabled providers: gemini

## Working agreement
- Before making non-trivial changes, create a short plan.
- Prefer small, focused edits over broad rewrites.
- Do not invent APIs, commands, or file paths. Verify them first.
- Preserve existing architecture unless there is a clear reason to refactor.
- Respect language version, framework constraints, deploy mode, and database specifics.
- If changing behavior, update tests or add tests when practical.
- After code changes, run the most relevant verification commands.

## Verification commands
- Dev: `npm run dev`
- Build: `npm run build`
- Test: `npm test`
- Lint: `npm run lint`

## Output style
- Be direct.
- Surface assumptions early.
- Call out risks, migrations, and breaking changes explicitly.
- When a task is ambiguous, prefer the smallest safe implementation.

## Roles enabled
- plan
- review
- test
- code
