---
name: release
description: "Ship open work: commit, push, open/merge the PR, clean up the branch, confirm the GitHub Pages deploy, move the board ticket. Use when the user says 'release', 'ship it', 'land this'. There are no PR checks; the gate for moving the board ticket to done is the Deploy run publishing the merge commit and the live site serving it."
---

Take one piece of open work from branch to merged, deployed, and cleaned up.
There is no CI on pull requests — the only workflow
(`.github/workflows/astro-gh-pages.yml`, "Deploy Astro site to GitHub Pages")
runs on pushes to `main` and builds and deploys in one go. So the local build is
the only check before merge. This is a single-PR flow with no batching.

### 1. Finish and push

- If there's uncommitted or unpushed work, commit it. **Never push known-red** —
  run `npm run build` first and fix any failure in the same commit before
  pushing. For a visual change, also check it in `npm run preview` (or
  `npm run dev`) at desktop and phone widths.
- Open the PR if there isn't one, or refresh the body (`gh pr edit`) so it
  describes everything on the branch.

### 2. Merge

- `gh pr checks <PR#>` will usually report none — that's expected. Make sure
  the PR is mergeable (`gh pr view <PR#> --json mergeable`).
- Merge with `gh pr merge <PR#> --merge --delete-branch`.

### 3. Clean up the branch

```
git checkout main && git pull --ff-only
```

`--delete-branch` removes the remote branch and the local one. If a local
branch is left behind, `git branch -d <branch>`; if that *refuses*, stop and
check why instead of forcing `-D`.

### 4. Confirm the deploy

The merge to `main` starts the deploy workflow. Wait for it, then check the
live site:

```
gh run list --workflow astro-gh-pages.yml --limit 1
curl -s -o /dev/null -w '%{http_code}\n' https://awesa.me/
```

The run's `headSha` (`gh run view <id> --json headSha`) should be the merge
commit. Also check any page the change touched (`/my-story/`, `/press/`). If
the deploy fails or a page doesn't return 200, stop and report — don't move
the board ticket. This, not the merge, is the real "done" signal.

### 5. Move the board ticket

Only after step 4 passes: if the released work corresponds to a story/subtask
on the tada board, move it to `done`: `mcp__tada__set_status` for the whole
story, or `mcp__tada__set_subtask_status` for just the subtask.

---

## After the release

Report what shipped: PR number, merged, deployed, branch cleaned up. Don't
claim a branch is done unless it's actually merged and gone, and don't move the
board ticket until step 4's check passes.
