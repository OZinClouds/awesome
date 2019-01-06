# Git Cheat
* [git_restart](#git_restart)

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
assume git restarted
`git remote add origin https://github.com/<>`
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE4NjMzOTUwNDksNzc5NzIyMTQxLDcxMD
Y5NDM4XX0=
-->