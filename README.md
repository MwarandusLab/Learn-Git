# Git
## Configure Git
Type the following in your command line after installing git...or on the git bash </br>
  ```git config --global user.name "Enter Your Username"```</br>
  ```git config --global user.email example@gmail.com```</br>
  ```git config --global core.editor "code --wait"``` </br>
  </br>
If you want to edit the config setting then you type the following command</br>
```git config --global -e``` </br>
</br>
How to configure end of lines or carriage returns on code pushed on the github </br>
```git config --global core.autorcrlf true``` If you using windows </br>
```git config --global core.autorcrlf input``` If you using mac or linux </br>

## Creating Snapshots
Initializing a repository </br>
```git init```</br>
</br>
Staging files </br>
```git add file1.js``` # Stages a single file </br>
```git add file1.js``` file2.js # Stages multiple files </br>
```git add *.js``` # Stages with a pattern </br>
```git add . ```# Stages the current directory and all its content </br>
</br>
Viewing the status </br>
```git status``` # Full status </br>
```git status -s``` # Short status </br>
</br>
Committing the staged files </br>
```git commit -m “Message”``` # Commits with a one-line message </br>
```git commit``` # Opens the default editor to type a long message </br>
</br>
Skipping the staging area </br>
```git commit -am “Message”``` </br>
</br>
Removing files </br>
```git rm file1.js``` # Removes from working directory and staging area</br>
```git rm --cached file1.js``` # Removes from staging area only</br>
</br>
Renaming or moving files</br>
```git mv file1.js file1.txt```</br>
</br>
Viewing the staged/unstaged changes</br>
```git diff``` # Shows unstaged changes</br>
```git diff --staged``` # Shows staged changes</br>
```git diff --cached``` # Same as the above</br>
</br>
Viewing the history</br>
```git log``` # Full history</br>
```git log --oneline``` # Summary</br>
```git log --reverse``` # Lists the commits from the oldest to the newest</br>
</br>
Viewing a commit</br>
```git show 921a2ff``` # Shows the given commit</br>
```git show HEAD``` # Shows the last commit</br>
```git show HEAD~2``` # Two steps before the last commit</br>
```git show HEAD:file.js``` # Shows the version of file.js stored in the last commit</br>
</br>
Unstaging files (undoing git add)</br>
```git restore --staged file.js``` # Copies the last version of file.js from repo to index</br>
</br>
Discarding local changes</br>
```git restore file.js```# Copies file.js from index to working directory</br>
```git restore file1.js file2.js``` # Restores multiple files in working directory</br>
```git restore .``` # Discards all local changes (except untracked files)</br>
```git clean -fd```# Removes all untracked files</br>
</br>
Restoring an earlier version of a file</br>
```git restore --source=HEAD~2 file.js```</br>
</br>
## Browsing History
Viewing the history</br>
```git log --stat``` # Shows the list of modified files</br>
```git log --patch``` # Shows the actual changes (patches)</br>
</br>
Filtering the history</br>
```git log -3``` # Shows the last 3 entries</br>
```git log --author=“Kheri”```</br>
```git log --before=“2020-08-17”```</br>
```git log --after=“one week ago”```</br>
```git log --grep=“GUI”``` # Commits with “GUI” in their message</br>
```git log -S“GUI”``` # Commits with “GUI” in their patches</br>
```git log hash1..hash2``` # Range of commits</br>
```git log file.txt``` # Commits that touched file.txt</br>
</br>
Formatting the log output</br>
```git log --pretty=format:”%an committed %H”```</br>
</br>
Creating an alias</br>
```git config --global alias.lg “log --oneline"```</br>
</br>
Viewing a commit</br>
```git show HEAD~2```</br>
```git show HEAD~2:file1.txt``` # Shows the version of file stored in this commit</br>
</br>
Comparing commits</br>
```git diff HEAD~2 HEAD``` # Shows the changes between two commits</br>
```git diff HEAD~2 HEAD file.txt``` # Changes to file.txt only </br>
</br>
Checking out a commit</br>
```git checkout dad47ed``` # Checks out the given commit</br>
```git checkout master``` # Checks out the master branch</br>
</br>
Finding a bad commit</br>
```git bisect start```</br>
```git bisect bad``` # Marks the current commit as a bad commit</br>
```git bisect good ca49180``` # Marks the given commit as a good commit</br>
```git bisect reset``` # Terminates the bisect session</br>
</br>
Finding contributors</br>
```git shortlog```</br>
</br>
Viewing the history of a file</br>
```git log file.txt``` # Shows the commits that touched file.txt</br>
```git log --stat file.txt``` # Shows statistics (the number of changes) for file.txt</br>
```git log --patch file.txt``` # Shows the patches (changes) applied to file.txt</br>
</br>
Finding the author of lines</br>
```git blame file.txt``` # Shows the author of each line in file.txt</br>
</br>
Tagging</br>
```git tag v1.0```# Tags the last commit as v1.0</br>
```git tag v1.0 5e7a828``` # Tags an earlier commit</br>
```git tag``` # Lists all the tags</br>
```git tag -d v1.0``` # Deletes the given tag</br>
</br>
## Branching & Merging</br>
Managing branches</br>
```git branch bugfix``` # Creates a new branch called bugfix</br>
```git checkout bugfix``` # Switches to the bugfix branch</br>
```git switch bugfix``` # Same as the above</br>
```git switch -C bugfix``` # Creates and switches</br>
```git branch -d bugfix``` # Deletes the bugfix branch</br>
</br>
Comparing branches</br>
```git log master..bugfix``` # Lists the commits in the bugfix branch not in master</br>
```git diff master..bugfix``` # Shows the summary of changes</br>
</br>
Stashing</br>
```git stash push -m “New tax rules”``` # Creates a new stash</br>
```git stash list``` # Lists all the stashes</br>
```git stash show stash@{1}``` # Shows the given stash</br>
```git stash show 1``` # shortcut for stash@{1}</br>
```git stash apply 1``` # Applies the given stash to the working dir</br>
```git stash drop 1``` # Deletes the given stash</br>
```git stash clear``` # Deletes all the stashes</br>
</br>
Merging</br>
```git merge bugfix``` # Merges the bugfix branch into the current branch</br>
```git merge --no-ff bugfix``` # Creates a merge commit even if FF is possible</br>
```git merge --squash bugfix``` # Performs a squash merge</br>
```git merge --abort``` # Aborts the merge </br>
</br>
Viewing the merged branches</br>
```git branch --merged``` # Shows the merged branches</br>
```git branch --no-merged``` # Shows the unmerged branches</br>
</br>
Rebasing</br>
```git rebase master``` # Changes the base of the current branch</br>
</br>
Cherry picking</br>
```git cherry-pick dad47ed``` # Applies the given commit on the current branch </br>
</br>
## Collaboration</br>
Cloning a repository</br>
```git clone url```</br>
</br>
Syncing with remotes</br>
```git fetch origin master``` # Fetches master from origin</br>
```git fetch origin``` # Fetches all objects from origin</br>
```git fetch``` # Shortcut for “git fetch origin”</br>
```git pull``` # Fetch + merge</br>
```git push origin master``` # Pushes master to origin</br>
```git push``` # Shortcut for “git push origin master”</br>
</br>
Sharing tags</br>
```git push origin v1.0``` # Pushes tag v1.0 to origin</br>
```git push origin —delete v1.0```</br>
</br>
Sharing branches</br>
```git branch -r``` # Shows remote tracking branches</br>
```git branch -vv # Shows local``` & remote tracking branches</br>
```git push -u origin bugfix``` # Pushes bugfix to origin</br>
```git push -d origin bugfix``` # Removes bugfix from origin</br>
</br>
Managing remotes</br>
```git remote``` # Shows remote repos</br>
```git remote add upstream url``` # Adds a new remote called upstream</br>
```git remote rm upstream``` # Remotes upstream </br>
</br>
## Rewriting History</br></br>
Undoing commits</br>
```git reset --soft HEAD^``` # Removes the last commit, keeps changed staged</br>
```git reset --mixed HEAD^``` # Unstages the changes as well</br>
```git reset --hard HEAD^``` # Discards local changes</br>
</br>
Reverting commits</br>
```git revert 72856ea``` # Reverts the given commit</br>
```git revert HEAD~3..``` # Reverts the last three commits</br>
```git revert --no-commit HEAD~3..```</br>
</br>
Recovering lost commits</br></br>
```git reflog``` # Shows the history of HEAD</br>
```git reflog show bugfix``` # Shows the history of bugfix pointer</br>
</br>
Amending the last commit</br>
```git commit --amend```</br>
</br>
Interactive rebasing</br>
```git rebase -i HEAD~5```</br>
</br>
