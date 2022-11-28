# Cheat Sheet

git log
- Show commits
- Also git log origin/main
  - Old: " " origin/master

git stash
- Saves current changes to current commit
- git stash popwill apply the latest stash and remove it from list
- git stash listwill show all stashes

git checkout
- git checkout HEAD^for last commit
	– HEAD^^or HEAD~2for two commits ago, etc
- git checkout mainbrings you pack to the top of the branch
	– Old: " " master
- git checkout [commit hash]for any commit (get commit hash from git hist, GitHub, etc)

git push origin [branch name]
- To push just one branch
- First do git checkout [branch name]

git tag [tag name]
- Create a simple tag

git commit -a -m "message here"
- or git commit --amendif you want to fix the last commit (and it wasn't published)

git hist
- At the :prompt type qto quit
- Very helpful for moving around past commits
- Not a native command, must be added as [alias] in .gitconfig

git reflog
- Useful

# GitHub
- Compare any two commits 
	– github.com/woodjmichael/{repo}/compare 
	– Choose branches from drop down menu, or..
	– Use commit ID (long or short version) of any non-current commits
- GitHub desktop okay but doesn't let you checkout old commits
	– GitKracken better
- Authentication
	– Since 2021.9 is done by Personal Access Token (saved in lastpass) 
	– Seems like no file that lives on local machine, just a very long password

# GitHub Desktop
- Useful, use it

# Git Flow
- Cool in theory, looks hard
