# Cheat Sheet
Save ("commit"): `git commit -a -m "message here"`
- or `git commit --amend` if you want to fix the last commit (and it wasn't published)

Show saves ("commits"): `git log`
- Also `git log origin/main`

Upload online: `git push origin --all`

Temporarily saves current changes: `git stash`
- `git stash pop` will apply the latest stash and remove it from list
- `git stash list` will show all stashes

Open a save ("commit"): `git checkout`
- `git checkout HEAD^` for last commit
	– `HEAD^^or HEAD~2` for two commits ago, etc
- `git checkout main` brings you pack to the top of the branch
- `git checkout [commit hash]` for any commit (get commit hash from git hist, GitHub, etc)

Upload just one branch: `git push origin [branch name]`

Create a simple tag: `git tag [tag name]`

See history: `git hist`
- At the :prompt type qto quit
- Very helpful for moving around past commits
- Not a native command, must be added as [alias] in .gitconfig

Reference log: `git reflog`
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

## GitHub Desktop
- Useful, use it

# Git Flow
- Cool in theory, looks hard
