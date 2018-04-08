# Git
1. **fork:** repo: makes an exact copy of repo and puts it into your repo
2. **git clone:** creates local copy (on machine) of remote repo (origin)
3. **git branch [name of branch]:** creates a new branch from the current branch
4. **git checkout [name of branch]:** switches to the specified branch
5. **git add src/** add all files in src/
6. **git merge [name of branch to merge to master]**
7. **git push**: shortcut command `git push origin person`   
		- origin: branch from which you initially cloned
		- master: branch

		
### pulling changes on assessment
- pull part1 of assessment: `git pull origin part1`
- merge with master: `git merge`
- `git remote add zipcoder [url to zipcoder repo]`
- `git pull zipcoder [part1]` : pull changes made to part 1 of test