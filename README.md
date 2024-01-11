# Git Notes

## Working with git locally 

- `git init`: initialize current folder as a git repository
- `git clone <URL>`: brings the git repo from <URL> to current folder
- `git status`: telss us what we need to know about our repository
- `git add <FILE>`: adds <FILE> to the staging area
- `git commit` open a text editor to wirte commit message
	- `git commit -m "MESSAGE"`: writes MESSAGE as a commit without a text editor
- `git log`: shows the log (history) of our commits
	- `git log --oneline`: show the shorter oneline commit
- `git diff`: compare current uncommited stat with last know igt state
	- `git diff --staged`: runs git diff between the staging area and last know state
- `git diff HEAD~<NUMBER>`: compares HEAD with commit <NUMBER> ago (relative)
- `git diff <HASH>`: compares HEAD with the commit in <HASH>
- `git restore --source <HASH OR HEAD~> <FILE>`: restore file to <HASH OR HEAD~>
	- `git checkout <HASH OR HEAD~>`: restore file to <HASH OR HEAD~>	
		- `git checkout <HASH OR HAED~>`: if you forget the file, you end up in detach state
		- `git switch main`: go back to main
 
## Working with remotes

- `git remote add <NAME> <URL>`: adds the <URL> as a remote with the name <NAME>
	- <NAME> is by convention called `origin`
- `git remote rm <NAME>`: removes the remote called <NAME>
- ` git remote -v`: look at all the remotes you have
- `git push <WHERE> <WHAT>`: pushes the <WHAT> branch to <WHERE>
	`git push origin main`
- `git pull <WHERE> <WHAT>`: pulls the <WHAT> branch in <WHERE> to local computer
- 

## Branches 

- `git branch <NAME>`: crate branch <NAME> where you are (HEAD)
- `git switch -c <NAME>`: move to the branch <NAME>
	- `git checkout -b <NAME>`: create and move to the branch <NAME> in 1 command


- `git merge <BRANCH>`: merge <BRANCH> into your current branch
- `git rebase`: command to change the history of a commit
	- Commits from `git merge` can be automatically combined
- `git rebase <BRANCH>`: incorporate changes from <BRANCH> into current branch
	- `git status`: is your friend
	- `git add <FILE>`: to mark conflict resolution
	- `git rebase --continue`: move to next commit in rebase
	- `git rebase --abort`: undo git rebase step
- `git rebase -i <COMMIT>` `HEAD~` or <HASH> of commit to go into interactive rebase
	- you can make multiple commit changes here, e.g., `squash`/`s`
	- `git rebase -i <HASH>^`: use ^ to include that commit in interactive rebase
- `git stash` or `git commit`: to save work before moving branches
	- `stash` is temporary
	- `git stach list`: see your stashed commits
	- `git stash apply`: apply your last stash commits
	- `git stash clear`: clean up your stashes

- A `merge` on the remote is called a "pull request" or "merge request"
	- `git push <WHERE> <WHAT>`
	- To updae a PR, we make the changes to the branch locally and re-`push`


- `git fetch`: update your git log without making any changes to your files
	- `git fetch --rune`: update your log and also remove delted remote branches
- a merge conflict can happen after a PR is issued

