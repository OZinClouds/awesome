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
Delete everything and reset remote, then 
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTU0Mzg0MzYzNyw3Nzk3MjIxNDEsNzEwNj
k0MzhdfQ==
-->