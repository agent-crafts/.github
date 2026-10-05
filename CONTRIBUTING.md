# Agent Crafts workflow

Small, mobile-first web apps, built by agents.

## Responsibilities
- Project chat owns planning, issues, priorities, dependencies, review comments, merge decisions, board updates, deployment verification and story acceptance.
- Codex reads a ready task issue, implements code on a dedicated branch, runs checks, opens a linked PR, and addresses review comments on that PR. Codex does not merge or manage the board.
- GitHub is the shared record. Chats must read current issues, PRs and checks; they do not automatically share context.
- Cloudflare provides previews and production deployment according to each application's configuration.

## Planning before implementation
Read the business brief, identify open questions, and create the full initial backlog of user stories and task sub-issues in each application's repository. Record dependencies and acceptance criteria. Keep unresolved tasks in Backlog; refine the backlog when requirements change.

## Suggested task states
Backlog -> Ready -> In Progress -> In Review -> Ready to Merge -> Merged -> Done.
Blocked is a separate state for work awaiting a dependency, access or decision.
These are conventions, not automatically configured board fields.

Ready requires a clear scope, acceptance criteria, dependencies and validation instructions.

## Execution and review
Use one branch and PR per implementation task unless the task explicitly specifies otherwise.
Review against the issue, current diff, required checks and preview where applicable.
For code corrections, comment on the PR and ask Codex to update the same branch.
For business scope changes, update the issue before implementation continues.
Merge only after required checks pass and blocking review comments are resolved.
A merged task is Done after appropriate target-environment verification; a story is Done only when its complete acceptance criteria pass.

## Repository setup
Each application owns its code, issues, tests, deployment configuration and AGENTS.md.
AGENTS.md must include repository-specific run/build/test commands and reference this workflow. This repository does not automatically distribute AGENTS.md, labels, board fields or CI workflows.
GitHub can supply these default issue/PR templates and contribution guidance when the application repository has no corresponding local override.
