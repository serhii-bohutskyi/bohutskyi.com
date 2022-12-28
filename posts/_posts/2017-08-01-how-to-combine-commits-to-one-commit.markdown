---
title: How combine git commits in one commit
description: git,commit,squash
---

Sometimes you need to squash all commits from your branch and prepare one commit, for example, for the PR. It can be required
to have one commit, which can be easily reverted in case of any issues, or it is just lovely to have one commit instead of a bunch of small commits.

### Template to copy

Input:

**target** - target branch for the PR
**custom_branch** - the branch with huge count of commits

---

```bash
git checkout {target}
git pull
git checkout {custom_branch}
git checkout -b {custom_branch}_backup
git checkout {custom_branch}
git reset --hard {target}
git merge --squash {custom_branch}_backup
```

### Example of usage

Suppose you have many commits in branch *feature/story_1* and must
prepare a pull request with one commit to the *release/dev* branch.
For that, use a temporary branch to the backup and make changes.

---

```bash
git checkout release/dev
git pull
git checkout feature/story_1
git checkout -b feature/story_1_backup
git checkout feature/story_1
git reset --hard release/dev
git merge --squash feature/story_1_backup
```

All changes would be in your files but **NOT** commited.

---
