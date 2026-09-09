# Install Git on Windows
https://git-scm.com/install/windows \
https://gitforwindows.org 

## Tools 
### Git in PowerShell
__posh-git__ \
https://git-scm.com/book/en/v2/Appendix-A%3A-Git-in-Other-Environments-Git-in-PowerShell \
https://github.com/dahlbyk/posh-git

# Useful git commands

### Check git version
```powershell
git --version
```
### Update git
```powershell
git update-git-for-windows
```
### View git configuration
```powershell
git config --list
```
### Configure name and email address for commits
```powershell
git config [--global] user.name "Full Name"
git config [--global] user.email "email@address.com"
```
### View remote origin
```
git remote -v
```
### Add remote origin
```
git remote add origin <remote_repository_url>
```
### Remove remote origin
```
git remote remove origin
```

## Branching
### View a Local Branch
- To see local branches
```
git branch
```
- To see remote branches
```
git branch -r
```
- To see all local and remote branches
```powershell
git branch -a
```
### Create a Local Branch
- Create a new branch
```
git checkout -b <my_branch_name>
```
### Switch branch
- Switch to a branch in local repo
```
git checkout <my_branch_name>
```

### Delete a Local Branch
- Delete the branch safely
```powershell
git branch -d branch_name
```

- Force-delete the branch
```powershell
git branch -D branch_name
```

## Other
### Discard Tracked Files (Modified Files)
- Discard unstaged changes in all files:
```powershell
git restore .
```
- Discard unstaged changes in a specific file:
```powershell
git restore <filepath>
```
- Discard both staged and unstaged changes entirely:
```powershell
git reset --hard
```

### Delete Untracked Files (New Files)
- See what untracked files will be deleted
```powershell
git clean -nd
```
- Permanently delete untracked files and directories:
```powershell
git clean -fd
```

### Nuke Everything
```powershell
git reset --hard
git clean -fd
```

### Clean Up Safely (Stashing)
```powershell
git stash -u
```

### Stashing file
```powershell
git stash push -m "your stash message" -- path/to/file1.txt path/to/file2.txt
```

### Stashing untracked file
```powershell
git stash push -u -m "your stash message" -- path/to/file1.txt path/to/file2.txt
```


<pre><code>
PS>git init
PS>git remote add origin <b>remote repository url</b> 
PS>git remote -v
PS>git add .
PS>git commit -m "Initial commit"
</code></pre>

PS>git clone

### Gitflow

flow for deployment is as follows:

1. 4 branches.
   i. Main
   ii. Test/Release
   iii.Develop
   iv. Feature

1. Decide on feature will go in release/prod
1. Feature branch is created from develop branch.
1. Work on new feature on separate Feature branch
1. Feature branch that will go on release will be merged to the Develop branch
1. Future features won't be merged to the Develop branch.
1. Testing
1. If all feature for release are complete and merged with Develop,
1. This will be cut-off/no new feature will go on.
1. Merge Develop branch to the Test/Release branch
1. Release branch is deployed to the Managed Test
1. Testing, any issues will be fixed in release branch
1. Release branch is merged to the Main and deployed to the Prod.
1. Release branch is merged to the Develop.

Reference:
https://www.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow

## Worktree Commands
### Create Worktree
```powershell
git worktree add -b new_branch_name ../path_to_dir existing_branch_name
```

### How to Merge Worktree changes
1. Commit and push
```powershell
cd /path/to/main-repository
```
2. Switch to your target branch
```powershell
git checkout main
git pull
```
3. Execute the merge
```powershell
git merge feature-branch-name
```

### Remove Worktree
- Basic removal
```powershell
git worktree remove ..\WSP-19711-Cordis\
```
- Force removal
```powershell
git worktree remove --force ..\WSP-19711-Cordis\
```
- Cleaning up
```powershell
git worktree prune
git branch -d <branch_name>
```


