# Project instructions for coding agents

> Template: replace all bracketed placeholders before use. This is not a ready-to-run policy for every repository.

## Project overview

- Purpose: [What this project does]
- Primary stack: [Languages, frameworks, database]
- Integration branch: [main, dev, or another branch]
- Important directories: [Paths and responsibilities]

## Before changing code

- Read the task and inspect relevant code and existing tests.
- Read applicable instructions in nested directories.
- State assumptions when requirements are ambiguous; ask before risky or irreversible changes.
- Do not modify unrelated modules or reformat unrelated files.

## Implementation expectations

- Follow existing architecture, naming, and formatting conventions.
- Prefer small, reviewable changes over broad refactors.
- Add or update tests when behavior changes.
- Do not introduce dependencies without justification and approval where required.
- Preserve public interfaces unless the task explicitly authorizes changes.

## Security and data handling

- Never commit secrets, access tokens, private keys, or personal data.
- Do not expose credentials in logs, tests, screenshots, or PR descriptions.
- Do not change production infrastructure, permissions, billing, or data without explicit authorization.
- Flag security-sensitive changes and describe their risk.

## Validation

Run the checks relevant to your changes. Replace these placeholders with commands that exist in this repository:

- Lint: [command]
- Typecheck: [command]
- Tests: [command]
- Build: [command]

If a check cannot run, explain why. Never claim an unrun check passed.

## Git and pull requests

- Use a dedicated branch for each task, based on [integration branch].
- Do not push directly to protected branches.
- Keep commits and PRs focused; describe behavior changes, risks, and verification.
- Address review findings with code changes or a documented technical rationale.
- Do not merge a PR unless explicitly authorized.

## Definition of done

- Requirements are met and scoped changes are reviewed.
- Relevant tests and checks have been run or limitations disclosed.
- Documentation is updated where behavior or setup changed.
- The PR clearly describes changes, verification, and remaining risks.
