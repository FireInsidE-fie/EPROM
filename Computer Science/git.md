---
tags:
  - tool
  - programming
---
based version control system
# Useful Commands
```sh
# In case you created some commits before pulling new work from the remote.
# This will recreate the commit history, adding the new commits before yours.
git pull --rebase

# "Rebase" your branch onto another, effectively adopting its commit history
# and adding your branch's on top
git rebase <branch>

# Removes all untracked files from the working tree.
git clean

# Instead of just force pushing stuff with --force, use --force-with-lease
# This checks whether someone else pushed stuff in the meantime, preventing the force push if that's the case
git push --force-with-lease
```
