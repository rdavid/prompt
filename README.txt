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
Avoid semicolons in comments, prose, commit messages, and pull requests.
Split clauses into sentences instead.
Link another project through its GitHub Pages site when it publishes one.
Fall back to the repository URL otherwise.

## Comments

Write comments in third-person singular, starting each with a capital letter.
Comment only in file and function descriptions, never in function bodies.
Write a function's description as one block above its name.
Allow multiple sentences on one line in a comment.

## Shell

Write POSIX sh only and avoid Bash features, since scripts run on BusyBox.
Prefer a long flag that BSD, BusyBox, and GNU share.
For example, use git commit --all over -a.
Apply this in scripts and in documentation examples.
Order command parameters alphabetically, such as id -nu, not id -un.
Prefer the single-quoted printf format over backslash escapes.
Choose the escaped form only when it takes fewer characters.
Order functions with main first, then the rest alphabetically by name.
Declare function variables with local.
POSIX does not define it, but BusyBox, dash, and mksh support it.
Keep local variable names to one to three letters, such as i, ip, or fle.
Capitalize script-level variables, such as SRC or TGT.

## Scripts

Open each script with the shebang, the modeline, and the SPDX lines.
Then add any shellcheck disable block or description comment.
Separate the SPDX lines from a following comment with a bare # line.
Omit the shebang in files that a task runner executes directly.
Use this modeline:
  # vi: lbr noet sw=2 ts=2 tw=79 wrap
Put a shellcheck disable directive on its own line.
Precede it with a description line that ends with a colon.
Indent the directive one extra space to mark it as subordinate.

## Build

Use the project's task runner instead of invoking tools directly.
Add or update tests for every behavior change.
Run the lint and test targets before submitting.
Keep tests deterministic and portable across every supported environment.
In scripts that run under errexit, capture an expected failure with
|| ret=$? and compare ret afterward.
Write success cases and failure cases as separate test scripts.
Configure Dependabot to open one pull request per dependency.
Omit the groups key from every dependabot.yml.

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
Preserve SPDX headers and add them to new files in repositories that use them.
Update BASE_APP_VERSION in each changed file that declares it.
Update the SPDX-FileCopyrightText year in each changed file.
When versions are date-based, such as 0.9.YYYYMMDD, same-day commits share
one value.
Update the version and year before committing, not after.
