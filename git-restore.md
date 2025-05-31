# from ms learn

Recovering commits

git log: lists the commit history of a repository. You can navigate through the log to find the commit you want to recover.
git checkout <commit>: switches to a specific commit, effectively "recovering" the state of the repository at that commit.
git cherry-pick <commit>: applies the changes introduced by a specific commit onto your current branch.
Recovering files

git checkout <commit> <file>: restores a specific file from a previous commit.
git restore <file>: discards local changes and restores the file to its last committed state, assuming that you haven't yet committed the changes.
Recovering specific lines of code

git blame <file>: displays the revision and author of each line in a file, helping you identify the commit that introduced a particular change.
git show <commit>:<file>: displays the content of a file at a specific commit. You can specify the commit and file path to see the content as it existed at that point in time.
Recovering deleted commits or branches

git reflog: displays a record of all commits. You can use it to find the SHA-1 hash of a previously deleted commit or branch and then checkout or restore it.
git fsck --lost-found: checks the integrity of the repository and lists any commits that aren't reachable from any branch or tag. You can use this to recover lost commits.