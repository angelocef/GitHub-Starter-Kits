# GitHub-Starter-Kits
All the necessary tutorials for newbies to get started with GitHub.


## How to Search a String in a Directory

`grep -Hrn 'search term' path/to/files`

- `-H` causes the filename to be printed (implied when multiple files are searched)
- `-r` does a recursive search
- `-n` causes the line number to be printed
`path/to/files` can be . to search in the current directory

Further options that I find very useful:

- `-I` ignore binary files (complement: -a treat all files as text)
- `-F` treat search term as a literal, not a regular expression
- `-i` do a case-insensitive search
- `--color=always` to force colors even when piping through `less`. To make `less` support colors, you need to use the `-r` option:
`grep -Hrn search . | less -r`
- `--exclude-dir=dir` useful for excluding directories like `.svn` and `.git`


## Navigate around 
**change to home directory**  
`$ cd ~ `  
**creates a folder**  
`$ mkdir <folder name> `    
**change to folder**    
`$ cd <folder name> `  
**prints current directory**    
`$ pwd`   
**list folder contents**    
`$ ls –a `  

## Clone github repository       
`$ git clone https://github.com/your-name/your-repo  ` 

## Add, Commit, Status, Push   
**check working directory changes**        
`$ git status `        
**add changes to index**    
`$ git add <folder> `    
`$ git add <file>`     
**commit a new version**        
`$ git commit -m <comment>`      
**push new version to GitHub**        
`$ git push origin master`     

## Check which Branch you are in    
**identify remote repository**        
`$ git remote `    
`$ git remote show <repo name> `  
**list local branches**      
`$ git branch`   
**list remote-tracking branches**    
`$ git branch --remote `  
**list all branches**    
`$ git branch --all `  

## Create, Delete, Switch and Merge branch   
**create a branch locally**    
`$ git branch <branch name> `  
**creates a new branch and switches to it locally**        
`$ git checkout -b <branch name>    `  
**make created local branch online**    
`$ git push --set-upstream origin <branch_name> `    
**deletes a branch locally**        
`$ git branch -d  <branch name> `    
**delete a branch from remote**      
`$ git push origin --delete <branch_name> `   
**switch to another branch**      
`$ git checkout <branch name> `    
**merge from branch**      
`$ git merge <branch name> `    

## See committed histories, add tags      
**show history of commits**      
`$ git log --oneline --decorate `    
**apply tag to a version**      
`$ git tag -a <version> <commit> -m <comment>   `  
**tag the last commit**      
`$ git tag <version> -m <comment> `    

## Undo Changes to commits.      
**undo unstaged changes**      
`$ git checkout <file>   `  
**undo staged changes**      
`$ git reset HEAD <file> `     
**undo committed change**      
`$ git revert <commit> --no-edit `    

## Undo Changes to commits. ! Caution !    
**remove commits and change history. Use it locally please**    
`$ git reset --hard <commit>  `  
**go back to that commit and make a new commit. Use it remotely**     
`$ git revert HEAD\~<number>  `
 
## Move, Delete and Rename Files    
**move or rename a file and stage the change**      
`$ git mv <source> <destination>    `  
**delete a file and stage the change**      
`$ git rm <file>`     

## Create files     
**creates an empty file**    
`$ touch <file name>`   
**open a text file in Notepad**    
`$ notepad <file name>`   
**inserts a string into a text file**    
`$ echo "some string" >> <file name>`   
**show contents of text file**    
`$ cat <file name>`   

## Misc   
**initializes a local repo inside current directory**    
`$ git init `  
**goes back in history to the specified commit**    
`$ git checkout <commit> `  
**move HEAD pointer to specified commit**    
`$ git reset --hard <commit>`   
**replay commits on current branch**    
`$ git rebase <branch name> `  

## Compare Versions   
**view changes not yet staged**    
`$ git diff <file>`     
**view the changes between the index and the last commit**    
`$ git diff --cached <file> `    
**view the changes in the working tree since the last commit**    
`$ git diff HEAD <file>`     
**view changes between two commits**    
`$ git diff <commit1> <commit2> <file> `     

## Basic Git Configuration    
**tells git who you are**    
`$ git config --global user.name "your name"`   
**tells git your email**    
`$ git config --global user.email "your.email@domain.com"`   
**handles end-of-line character differences**    
`$ git config --global core.autocrlf true`   
**prevents conversion warning messages**    
`$ git config --global core.safecrlf false`   
**sets Notepad as the default editor**    
`$ git config --global core.editor notepad `  
**list all current configuration settings**    
`$ git config --list `  
 
## Keep your Fork Synchronized      
**add a new remote identified by upstream**      
`$ git remote add upstream https://github.com/user-name/repo-name  `   
**list remotes with URL**      
`$ git remote --verbose`     
**fetch the latest commits from remote identified by upstream**      
`$ git fetch upstream `    
**update local master from remote identified by upstream**      
`$ git checkout master   `  
`$ git merge upstream/master  `    
 
## Stash: Saving Changes      
**saves changes and clear working directory**      
`$ git stash`     
**list saved changes**      
`$ git stash list  `   
**show saved changes**      
`$ git stash show  `   
**restore saved changes**      
`$ git stash apply`     
 
## The Repository Database      
**list repository folder**      
`$ ls .git`     
**look at HEAD pointer**      
`$ cat .git/HEAD `    
**list refs directory tree**      
`$ find .git/refs `    
**last commit on master**      
`$ cat .git/refs/heads/master`     
**list objects directory tree**      
`$ find .git/objects`     
**displays type of a Git object**      
`$ git cat-file -t <hash> `    
**displays the content of a Git object**      
`$ git cat-file -p <hash>`     
 
## A More Sophisticated History View      
**convert end-of-line to DOS format**      
`$ unix2dos <file>`     
**convert end-of-line to Unix format**      
`$ dos2unix <file> `    
**formatting history log**      
`$ git log --pretty=format:'%h %ad | %s%d [%an]' --graph --date=short `    
**using an alias**      
`$ git <alias>`      
