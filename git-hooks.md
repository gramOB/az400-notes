# what are they

### make sure bad code doesn't get committed locally, protecting the remote

- stored in .git/hooks
- run scripts upon git commands, can do anything you want
  - they should be named to match the related events
- usual examples:
  - Enforcing preconditions for merging
  - Verifying work Item ID association in your commit message
  - Preventing you & your team from committing faulty code
  - Sending notifications to your team's chat room (Teams, Slack, HipChat, etc.)

## .git/hooks

```powershell
	PS C:\Users\gobrien\az-400> ls .git

    Directory: C:\Users\az-400\.git

Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
lar--           5/30/2025  3:17 PM                hooks
lar--           5/30/2025  3:17 PM                info
d----           5/30/2025  3:18 PM                logs
lar--           5/30/2025  3:18 PM                objects
lar--           5/30/2025  3:17 PM                refs
la---           5/30/2025  3:17 PM            130 config
la---           5/30/2025  3:17 PM             73 description
la---           5/30/2025  3:18 PM             72 FETCH_HEAD
la---           5/30/2025  3:17 PM             21 HEAD
-a---           5/30/2025  3:18 PM           1234 index
```

```powershell
    Directory: C:\Users\gobrien\\Documents\az-400\.git\hooks

Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
la---           5/30/2025  3:17 PM            478 applypatch-msg.sample
la---           5/30/2025  3:17 PM            896 commit-msg.sample
la---           5/30/2025  3:17 PM           4726 fsmonitor-watchman.sample
la---           5/30/2025  3:17 PM            189 post-update.sample
la---           5/30/2025  3:17 PM            424 pre-applypatch.sample
la---           5/30/2025  3:17 PM           1649 pre-commit.sample
la---           5/30/2025  3:17 PM            416 pre-merge-commit.sample
la---           5/30/2025  3:17 PM           1374 pre-push.sample
la---           5/30/2025  3:17 PM           4898 pre-rebase.sample
la---           5/30/2025  3:17 PM            544 pre-receive.sample
la---           5/30/2025  3:17 PM           1492 prepare-commit-msg.sample
la---           5/30/2025  3:17 PM           2783 push-to-checkout.sample
la---           5/30/2025  3:17 PM           2308 sendemail-validate.sample
la---           5/30/2025  3:17 PM           3650 update.sample

```

### the .sample prevents them from running

Try out the pre-commit.sample. Remove the .sample extension. Change it to run on windows git shell in the shebang

```powershell
#!C:/Program\ Files/Git/usr/bin/sh.exe
```

Change contents to match on password/secret

```powershell
#!C:/Program\ Files/Git/usr/bin/sh.exe
matches=$(git diff-index --patch HEAD | grep '^+' | grep -Pi 'password|secret')
if [ ! -z "$matches" ]
then
  cat <<\EOT
Error: Words from the blocked list were present in the diff:
EOT
echo $matches
exit 1
fi
```

"Once invoked, the pre-commit hook script uses the git diff and grep commands to identify keywords or patterns within the incremental changes to the code that are being committed"

### try it out

```powershell
PS C:\Users\gobrien\\Documents\az-400> echo "password=1234" >> secrets.txt
PS C:\Users\gobrien\\Documents\az-400> git add . 
PS C:\Users\gobrien\\Documents\az-400> git commiti -m "adding file"
git: 'commiti' is not a git command. See 'git --help'.

The most similar command is
        commit
PS C:\Users\gobrien\\Documents\az-400> git commit -m "adding file" 
Error: Words from the blocked list were present in the diff:
+++ b/secrets.txt +password=1234
PS C:\Users\gobrien\\Documents\az-400> 
```

Another pre-commit to add branch name:

```powershell
#!C:/Program\ Files/Git/usr/bin/sh.exe
# Get the current branch name
branch_name=$(git branch --show-current)
# Check if the commit message file exists
if [[ -f "$1" ]]; then
  # Prepend the branch name to the commit message
  sed -i "1s/^/$branch_name: /" "$1"
fi
```

## post commit hooks

- mainly usedf to generate messages and documentation
