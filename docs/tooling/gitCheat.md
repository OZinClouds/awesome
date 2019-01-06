# Git Cheat

## git_restart
git start-over
remove all files and init again with an initial commit
` 
git_restart(){
	echo "this may take some time, be patient..."

	rm -rf .git
	git init
	git add .
	git commit -am "initial commit"

	echo "restarted git..."
}
`
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE4NjgxOTQ2OTJdfQ==
-->