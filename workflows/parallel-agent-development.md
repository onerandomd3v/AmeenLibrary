# Parallel agent development with Git worktrees

**Status:** Documented from firsthand development practice; commands cross-checked against official Git documentation. **Not a claim that this exact tutorial was executed end-to-end.**

Use separate Git worktrees to let coding agents work on independent tasks in parallel without sharing a working directory or index. Worktrees share repository history, so isolation is **not** a security sandbox.

## Before starting

- Git installed; repository cloned; clean working tree.
- Identify the repository's actual integration branch (e.g. `main` or `dev`); do not assume it is `main`.
- Select independent tasks with minimal overlapping files or migrations.
- Agree on test commands and PR requirements.

## Example: two parallel tasks

Run from the repository root, replacing `main` with your real integration branch:

```bash
git fetch origin
git worktree add -b task/auth-fix ../project-auth origin/main
git worktree add -b task/ui-fix ../project-ui origin/main
git worktree list
```

Each `-b` creates a new local branch at the specified starting point. The two linked worktrees have separate working directories. Use distinct task names and paths.

Start a separate agent session inside each worktree, e.g. `cd ../project-auth` for the authentication task and `cd ../project-ui` for the UI task. Tell each agent which branch and scope it owns. Do not let both agents edit the same shared checkout.

## Agent task contract

> Work only in this worktree on the assigned task. Inspect applicable repository instructions before changing code. Make the smallest scoped change, run relevant tests, report what ran and what could not run, and open a PR against the repository's integration branch. Do not merge or modify other worktrees.

## Review and integrate

1. Review each diff and verify tests, lint, and security-sensitive behavior.
2. Push each task branch and open separate PRs against the correct integration branch.
3. Resolve feedback and check for overlapping changes before merging.
4. Merge sequentially when tasks interact; rebase or update remaining branches and rerun affected checks. Never assume independent directories guarantee conflict-free merges.

## Cleanup

After the worktree's changes are safely committed/pushed and its PR is merged or intentionally abandoned:

```bash
git worktree remove ../project-auth
git worktree remove ../project-ui
git worktree list
```

Only remove **clean** worktrees; `git worktree remove` normally refuses dirty ones. Delete local branches separately when no longer needed (`git branch -d task/auth-fix`), after confirming their work is preserved. Use `git worktree prune` only to clear stale worktree metadata, not as the normal removal step.

## Pitfalls

- Do not share a single writable workspace between agents.
- Distinct worktrees can still conflict on shared files, database migrations, API contracts, ports, and external services.
- Do not run multiple migrations against the same shared database without coordination.
- Use distinct local ports, temporary directories, and development databases when tasks need them.
- Keep secrets out of agent instructions, commits, and PR logs.
- Require human review for destructive operations and production changes.

**References:** [Git worktree documentation](https://git-scm.com/docs/git-worktree.html).

**Verification checklist:** `git worktree list` shows distinct branches and paths; each task has its own PR; required checks pass; no unrelated files changed; cleanup leaves no stale worktrees.
