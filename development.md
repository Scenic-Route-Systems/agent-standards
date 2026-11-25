# Development Guidelines

## Commits and Pull Requests

### When Working Locally

- When creating commit messages and pull request descriptions:
    - NEVER mention Claude nor URLs with Claude Code sessions.
    - NEVER mention Slack or include a Slack URL.
    - Use a simple, concise statement, NOT a detailed description listing out everything that changed.
- All commits must be under the local environment's .gitconfig username/email, NEVER Claude's own user.
- NEVER automatically commit, branch, or create pull requests. I will manually deal with all git/GitHub operations.

### When Triggered By GitHub Actions

When triggered by GitHub actions, follow these directives. Do NOT do the following when working locally.

- Always create pull requests with a feature branch, NEVER directly push to master.
- One feature branch per unit of work, NEVER stack commits for multiple distinct tasks in one branch.
- When working from an issue (where no open PR yet exists for your branch), after committing and pushing your
  feature branch you MUST open the pull request yourself by running `gh pr create` (base `master`). Do NOT include a prefilled PR link -- actually create the PR.
- If an open PR already exists for your branch (you were triggered from that PR), push to that PR's branch instead and do NOT open a new PR.

## Workflow

- NEVER make formatting changes unrelated to the current task in a file you're working on, even if you encounter spaces vs. tabs, style guide violations, and other best practice issues. Suggest reformatting follow-up work, which MUST be done in isolated commits/PRs outside of the current unit of work.
- NEVER touch blocks of code unrelated to the feature you implement. As much as possible try to minimize the number of changed lines when implementing a feature.
- Before implementing from-scratch utilities and approaches, first deeply check for other dependencies to introduce, especially if they're widely used or a best-practice within the given stack. Avoid reinventing any wheels.
- Before implementing workarounds for possible bugs or shortcomings in dependencies/libraries, first deeply check for existing bug reports and fixes in the upstream changelogs. Emphasize version upgrades over workarounds whenever possible.

## Code Style, Design Patterns, Other Guidance

- Even though agents will often be creating code, ALWAYS emphasize human readability and maintainability. Humans always ultimately own the code and will manually work on it alongside agents. Emphasize clarity instead of being clever or overly concise. Verbosity is preferred if it is more clear, self-documenting, and easily understood by a human developer.
- Narrowly scope the layers within this architecture. Ex: a file containing client code for integration with an external service should not also make database updates, instead isolating that to the view that called the client methods.
- Do NOT leave pointless code comments when the code itself is self-explanatory and self-documenting. When necessary, add a small, to the point, comment to explain *what* the block does and *why*. Use examples when possible.
- When writing something intended for human consumption, (comment, commit message, reply to prompt) use as few words as possible. Pick every word meticulously to reduce the volume to a strict minimum. Be down to the point. Less is more.
- Reduce code indentation. Avoid Arrow Anti-Pattern. Leverage early return and continue.
- Keep function names short. Less than 30 characters.
- Let the reader of the code breathe. Add empty lines between logical blocks of code.
- Always use {}, even on a one-line "if" statement.
- NEVER use align-when-multiline wrapping for things like method declaration parameters, method call arguments, import statements, and collection definitions. ALWAYS use basic indentation instead.
- NEVER use non-ASCII quotes, double quotes, em dashes, etc. Always `'`, `"`, `--`. These are just examples. The point applies to all other uses of non-ASCII characters.
- Headings, labels, and text content in general should always be capitalized and end with punctuation if it's a sentence, or ALL lowercase with no punctuation if it's not a sentence. IE, "Mark as read." and "mark as read" are fine, "Mark as read" is NOT ok.
- 2 spaces for all indentation, with the exception of Python being 4 spaces.
- ALWAYS use 120 character line limits, even when that violates rules like PEP 8's 72-99 characters in Python.