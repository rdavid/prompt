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
Put all of a function's commentary in one block above its name.
Leave the body free of comments.

## Shell

Write portable `sh` first and avoid Bash-specific features.
Use Bash features only when the file already depends on them.
Prefer the long form of a flag, such as `--force` over `-f`.
Apply this in scripts and in documentation examples.
Use the short form only when the command has no long form.
Order functions with main first, then the rest alphabetically by name.
Put a shellcheck disable directive on its own line.
Precede it with a description line that ends with a colon.
Indent the directive one extra space to mark it as subordinate.
Prefer the single-quoted printf format over backslash escapes.
Choose the escaped form only when it takes fewer characters.

## Licensing

Preserve SPDX headers and add them to new files in repositories that use them.
Update the copyright year and version only in files with a substantive change.
A metadata-only diff is noise, so revert year and version edits when a pass
makes no meaningful change to a file.
When versions are date-based, such as 0.9.YYYYMMDD, same-day commits share
one value. Leave a version that already shows today's date unchanged.

## Build

Use the project's task runner instead of invoking tools directly.
Add or update tests for every behavior change.
Run the lint and test targets before submitting.
Keep tests deterministic and portable across every supported environment.
In scripts that run under errexit, capture an expected failure with
|| ret=$? and compare ret afterward.
Write success cases and failure cases as separate test scripts.

## Commits

Use Conventional Commits for every commit, with a scope when one exists.
Favor scoped forms such as `build(deps): ...` and `chore(deps): ...`.
Write concise, imperative subjects.
Credit every commit to the human author alone.
Omit AI signatures, generated-by trailers, and co-authors.
Apply the same rule to pull requests, issues, and code comments.
Apply the semicolon rule to commit messages and pull request descriptions.

## Pull Requests

Explain the user-visible change and note any portability implications.
Confirm the lint and test results.
Link related issues where applicable.
Skip UI screenshots unless they are necessary.

## Documentation

Link another project through its GitHub Pages site when it publishes one.
Fall back to the repository URL otherwise.
