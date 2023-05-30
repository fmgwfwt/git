git config --global user.name "username"
git config --global user.email "youremailaddress"

git init // initialize the project
git add . // add the project to the stage
git commit -m 'message' // commit with the message
git add file1 file2 file3
git diff --cached // to see what is now ready to commit 
git status // shows the status
git diff // 
git log // view the history of your changes
git log -p // see complete diffs at each step
git log --stat --summary // overview of the change 
git branch new_branch // to create a new branch
git switch new_branch // to switch from master to new_branch
git merge new_branch // in master merge
git diff // is gonna show the conflicts 
gitk // will show a nice graphical representation of resulting history
git branch -d new_branch // delete the new_branch this ensures that changes in the branch are already in the current branch
git branch -D new_branch // delete the new_branch
git clone /home/alice/project myrepo
git commit -a
cd /home/alice/project
git pull /home/bob/myrepe master


