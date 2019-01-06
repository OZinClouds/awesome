# Git Cheat
* [git_restart](#git_restart)
* [reset remote](#reset-remote)

## git_restart
git start from scratch  
remove all files and init again with an initial commit

	`git_restart(){
	echo "this may take some time, be patient..."

	rm -rf .git
	git init
	git add .
	git commit -am "initial commit"

	echo "restarted git..."}`

## reset remote
Delete everything and reset remote, then push mirror origin  
*assumes git restarted*

add remote:  
`git remote add origin https://github.com/ozinclouds/<REPO>`

push entire local repo to remote:  
`git push origin --mirror`

## Jeffrey Way goodies
###jeffreyWay alias for git 
 nah : undo everything since last commit, incl new files
alias nah="git reset --hard && git clean -df"
alias wip="git add . && git commit -m 'wip'"
alias gitlog="git log --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit"
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE0NjM2NTI1MDMsODIzNzAzNTksNzc5Nz
IyMTQxLDcxMDY5NDM4XX0=
-->