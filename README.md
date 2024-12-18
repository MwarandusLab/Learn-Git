# Git
## Configure Git
Type the following in your command line after installing git...or on the git bash </br>
  ```git config --global user.name "Enter Your Username"```</br>
  ```git config --global user.email example@gmail.com```</br>
  ```git config --global core.editor "code --wait"``` </br>
If you want to edit the config setting then you type the following command</br>
```git config --global -e``` </br>
How to configure end of lines or carriage returns on code pushed on the github </br>
```git config --global core.autorcrlf true``` If you using windows </br>
```git config --global core.autorcrlf input``` If you using mac or linux </br>

## Creating Snapshots
Initializing a repository </br>
```git init```</br>
Staging files </br>
```git add file1.js``` # Stages a single file </br>
```git add file1.js``` file2.js # Stages multiple files </br>
```git add *.js``` # Stages with a pattern </br>
```git add . ```# Stages the current directory and all its content </br>
Viewing the status </br>
```git status``` # Full status </br>
```git status -s``` # Short status </br>
Committing the staged files </br>
```git commit -m “Message”``` # Commits with a one-line message </br>
```git commit``` # Opens the default editor to type a long message </br>
Skipping the staging area </br>
```git commit -am “Message”``` </br>
Removing files </br>
```git rm file1.js``` # Removes from working directory and staging area</br>
```git rm --cached file1.js``` # Removes from staging area only</br>
Renaming or moving files</br>
```git mv file1.js file1.txt```</br>
Viewing the staged/unstaged changes</br>
```git diff``` # Shows unstaged changes</br>
```git diff --staged``` # Shows staged changes</br>
```git diff --cached``` # Same as the above</br>
Viewing the history</br>
```git log``` # Full history</br>
```git log --oneline``` # Summary</br>
```git log --reverse``` # Lists the commits from the oldest to the newest</br>
Viewing a commit</br>
```git show 921a2ff``` # Shows the given commit</br>
```git show HEAD``` # Shows the last commit</br>
```git show HEAD~2``` # Two steps before the last commit</br>
```git show HEAD:file.js``` # Shows the version of file.js stored in the last commit</br>
Unstaging files (undoing git add)</br>
```git restore --staged file.js``` # Copies the last version of file.js from repo to index</br>
Discarding local changes</br>
```git restore file.js```# Copies file.js from index to working directory</br>
```git restore file1.js file2.js``` # Restores multiple files in working directory</br>
```git restore .``` # Discards all local changes (except untracked files)</br>
```git clean -fd```# Removes all untracked files</br>
Restoring an earlier version of a file</br>
```git restore --source=HEAD~2 file.js```</br>
