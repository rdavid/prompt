# Repository Guidelines

Keep chat replies and answers short and easy to understand.
These guidelines apply to every repository.
A repository-level AGENTS.md or CLAUDE.md wins when the two conflict.

## Style

Match the existing style of each repository before introducing anything new.
Follow its indentation, naming, comment density, and file layout.
Keep lines to roughly 79 characters unless the project sets another limit.
Prefer portable, minimal solutions over clever ones.

## Comments

Write comments in third-person singular, starting each with a capital letter.
Avoid semicolons in comments and prose. Split clauses into sentences instead.
Keep all of a function's commentary in one block above its name.
Leave function bodies free of comments.

## Shell

Write portable `sh` first and avoid Bash-specific features.
Use Bash features only when the file already depends on them.
Prefer the long form of a flag, such as `--force` over `-f`.
Do so in scripts and in documentation examples.
Use the short form only when the command has no long form.

## Licensing

Preserve SPDX headers and add them to new files in repositories that use them.
Update the copyright year and version only in files with a substantive change.
Bump metadata only alongside a substantive change.
A metadata-only diff is noise.
If a pass makes no meaningful change to a file, revert its year and version.
When versions are date-based, such as 0.9.YYYYMMDD, same-day commits share
one value. Do not bump a version that is already set to today.

## Build

Use the project's task runner instead of invoking tools directly.
Add or update tests for every behavior change.
Run the lint and test targets before submitting.
Keep tests deterministic and portable across every supported environment.

## Commits

Use Conventional Commits for every commit, with a scope when one exists.
Favor scoped forms such as `build(deps): ...` and `chore(deps): ...`.
Write concise, imperative subjects.
Credit every commit to the human author alone.
Apply the same rule to pull requests, issues, and code comments.

## Pull Requests

Explain the user-visible change and confirm the lint and test results.
Link related issues where applicable.
Skip UI screenshots unless they are necessary.
