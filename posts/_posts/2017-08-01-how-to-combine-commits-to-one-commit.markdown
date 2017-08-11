---
title: How combine git commits in one commit
description: git,commit,squash
---

Suppose you have many commits in branch *feature/story_1* and need to
prepare pull request with one commit to *release/dev* branch.
For that use temporary branch to backup and take changes.

```bash
$ git checkout release/dev
$ git pull
$ git checkout feature/story_1
$ git checkout -b feature/story_1_backup
$ git checkout feature/story_1
$ git reset --hard release/dev
$ git merge --squash feature/story_1_backup
```


All changes would be in your files but **NOT** commited.



