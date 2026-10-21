# git-trash

Delete your old branches, including their linked worktrees, that you always
forget to remove when you're done!

## Problem

```sh
➜ git branch | wc -l
      325
```

## Solution

![trash](/trash.png?raw=true "trash")

By default the current branch along with the branches `master`, `main`, `develop` and
`development` will be ignored. The current branch, `master` and `main` can never be
trashed but you can customize other or additional branches to ignore by setting
`SKIP_BRANCHES`.

```sh
➜ SKIP_BRANCHES="branch-1|feature/v3" git-trash
```

Branches checked out in a linked worktree are marked with 󰙅 and the worktree is
removed together with the branch. Removal is never forced so a worktree with
uncommitted changes, or one that is locked, is kept along with its branch.
