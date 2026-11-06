# Guidelines

Keep chat replies short and easy to understand.
These guidelines apply to every repository.
A repository-level AGENTS.md overrides them on any conflict.
Favor aesthetics over functionality.

## Style

Match the existing style of each repository before introducing anything new.
Follow its indentation, naming, comment density, and file layout.
Keep lines to roughly 79 characters unless the project sets another limit.
Start every sentence on a new line in README and Markdown files.
Prefer portable, minimal solutions over clever ones.
Write comments in third-person singular, starting each with a capital letter.
Avoid semicolons in comments and prose.
Split clauses into sentences instead.
Allow multiple sentences on one line in comments.
Place comments in the file description or the function description.
Put a function's description in one block above its name.
Avoid comments in the function body.
Link another project through its GitHub Pages site when it publishes one.
Fall back to the repository URL otherwise.

## Shell

Write portable sh first and avoid Bash-specific features.
Use Bash features only when the file already depends on them.
Prefer the long form of a flag, such as --force over -f.
Apply this in scripts and in documentation examples.
Use the short form only when the command has no long form.
Order functions with main first, then the rest alphabetically by name.
Put a shellcheck disable directive on its own line.
Precede it with a description line that ends with a colon.
Indent the directive one extra space to mark it as subordinate.
Prefer the single-quoted printf format over backslash escapes.
Choose the escaped form only when it takes fewer characters.
Open each script with the shebang, the modeline, and the SPDX lines.
Then add any shellcheck disable block or description comment.
Omit the shebang in files that a task runner executes directly.
Use this modeline:
  # vi: lbr noet sw=2 ts=2 tw=79 wrap

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
Favor scoped forms such as these:
  build(deps): ...
  chore(deps): ...
Write concise, imperative subjects.
Keep each commit subject within 72 characters.
Credit every commit to the human author alone.
Omit AI signatures, generated-by trailers, and co-authors.
Apply the same rule to pull requests, issues, and code comments.
Apply the semicolon rule to commit messages and pull request descriptions.
Preserve SPDX headers and add them to new files in repositories that use them.
Update BASE_APP_VERSION in each changed file that declares it.
Update the SPDX-FileCopyrightText year in each changed file.
When versions are date-based, such as 0.9.YYYYMMDD, same-day commits share
one value.
Leave a version that already shows today's date unchanged.
Update the version and year before committing, not after.
