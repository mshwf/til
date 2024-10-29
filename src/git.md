**Change last commit message:**
1. `git commit --amend -m "<NEW MESSAGE>"`
2. `git push --force`

**Delete local branch:**  
`git branch -d branchName`

**Delete remote branch:**  
`git push origin --delete remoteBranchName`

**Sync local branches with remote:**  
`git fetch -p`  
_The -p or --prune argument will update the local database of remote branches._

**Squashing N commits in a branch**  
`git reset --soft HEAD~<N>`  
`git commit -m "MESAAGE"`  
`git push --force`  

**Merge changes of source branch into target (current) branch as uncommitted changes:**  
`git checkout origin/<source-branch> -- .`
