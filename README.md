git config --global user.name "username" <br />
git config --global user.email "youremailaddress" <br />
<br />
git init // initialize the project <br />
git add . // add the project to the stage <br />
git commit -m 'message' // commit with the message <br />
git add file1 file2 file3 <br />
git diff --cached // to see what is now ready to commit <br />
git status // shows the status <br />
git diff // <br />
git log // view the history of your changes <br />
git log -p // see complete diffs at each step <br />
git log --stat --summary // overview of the change <br />
git branch new_branch // to create a new branch <br />
git switch new_branch // to switch from master to new_branch <br />
git merge new_branch // in master merge <br />
git diff // is gonna show the conflicts <br />
gitk // will show a nice graphical representation of resulting history <br />
git branch -d new_branch // delete the new_branch this ensures that changes in the branch are already in the current branch <br />
git branch -D new_branch // delete the new_branch <br />
git clone /home/alice/project myrepo <br />
git commit -a <br />
cd /home/alice/project <br />
git pull /home/bob/myrepe master <br />


<br />
<br />
to push you need to create an ssh key with the command <br />
ssh-keygen -t rsa -b 4096 -C "emaladdress" <br />
there are two keys key and key.pub you can share key.pub(public) <br />
then go to your account in settings add ssh and gpg keys add you public key there <br />
then comeback to cli run these commands <br />
eval "$(ssh-agent -s)" <br />
"ssh-add -K ~/.ssh/key(private)" <br />
<br />
suppose you created a new folder and want to push that folder to your github account first you need to create a new repository in there and with the command <br />
git remote add "https or ssh " address <br /> 
git remote -v // shows the any remote repositories that connected <br />
now you can add commit and push <br />
git push -u origin master (-u means --set-upstream)<br /> 
<br />
git checkout -b new_branch // new_branch <br />
git pull // to see the updates on the local <br />
you staged some file and then git -reset [filename] will unstage <br />
if you commit something git reset HEAD~1 will come back <br />
git reset (any commit number) you will be there <br />
git reset --hard (any commit number) you will be there and other changes will be deleted <br />

imagine you cloned a repository from someone's account to your local
you cannot push you can pull request but if you work you clone it to your github account then you can push clone to your local change and pull request <br /> 

git push origin master = push changes to github master <br />
git push origin new_branch = push changes to github new_branch <br />
git config --list <br />

git config --global core.autocrlf true in windows <br />
git config --global core.autocrlf input in windows <br />

staging area = index <br />
when you commit the staging area is not emptied <br />

sometimes we don't want to add or commit some files so we need to create a file .gitignore we can put *logs /logs main.log or similar names to ignore <br />
git add .gitignore <br />

imagine a case you commit a file but then you noticied you don't want it and you put it in to .gitignore when you do that you need to add commit .gitignore <br /> 
but when you modify your file which you don't want to commit because it's in still staging area you can remove it from your staging area = index <br /> 
git rm --cached file <br />
git rm --cached -r folder <br /> 

git status -s  the output of this command left column shows the staging area right column shows the working directory <br />
git diff --staged <br />
git diff (unstaged) <br /> 
git diff --cached // like staged <br />

git log <br /> 
git log --oneline <br /> 
git log --reverse <br />

git show 921a2ff // shows the given commit <br /> 
git show HEAD // shows the last commit <br />
git show HEAD~2 // two steps before the last commit <br />
git show HEAD:file.js // shows the version of file.js stored in the last commit <br />
git restore --staged file.js // copies the latest version of file.js from repo to index // unstaging files undoing git add <br />

git restore file.js // copies file.js from index to working directory <br />
git restore file1.js file2.js // restores multiple files in working directory <br />
git restore . // discards all local changes (except untracked files) <br />
git clean -fd // removes all untracked files <br />

git restore --source=HEAD~2 file.js // restoring an early version of a file  <br />

git log --stat // shows the list of modified files <br />
git log --patch // shows the actual changes (patches) <br />

git log -3 // shows the last three entries <br />
git log --author="name" <br />
git log --before="2013-02-12" <br />
git log --after="one week ago" <br />
git log --grep="GUI"  // commits with GUI in their message <br />
git log -S"GUI"   // commits with GUI in their patches <br />
git log hash1..hash2 // range of commits <br />
git log file.txt // commits that touched file.txt <br />

git log --pretty=format:"%an committed%H" // formatting the log output <br />

git config --global alias.lg "log --online" // creating an alias <br />

git show HEAD~2 // viewing a commit <br />
git show HEAD~2:file1.txt // shows the version of file stored in this commit <br />
git diff HEAD~2 HEAD // shows the changes between two commits <br />
git diff HEAD~2 HEAD file.txt // changes to file.txt only <br />

git bisect start // finding a bad commit <br />
git bisect bad  // marks the current commit as a bad commit <br />
git bisect good ca49180 // marks the given commit as a good commit <br />
git bisect reset // terminates the bisect session <br />

git shortlog // finding contributors <br />

git log file.txt // shows the commits that touched that file <br />
git log --stat file.txt // shows the number of changes for file.txt <br />
git log --patch file.txt // shows the patches(changes) applied to file.txt <br />

git blame file.txt // shows the author of each line in file.txt <br />

git tag v1.0 // tags the last commit as v1.0 <br />
git tag v1.0 5e7a828 // tags an earlier commit <br />
git tag // lists all the tags <br />
git tag -d v1.0 // deletes the given tag <br />

git log master..bugfix // lists the commits in the bugfix branch not in master <br />
git diff master..bugfix // shows the summary of changes <br />

git stash push -m 'New tax rules' // creates a new stash <br />
git stash list // list all the stashes <br />
git stash show stash@{1} // shows the given stash <br />
git stash show 1 // shortcut for stash@{1} <br />
git stash apply 1 // applies the given stash to the working dir <br />
git stash drop 1 // deletes the given stash <br />
git stash clear // deletes all the stashes <br />

git merge bugfix // merge bugfix branch into the current branch <br />
git merge --no-ff bugfix // creates a merge commit even if FF is possible <br />
git merge --squash bugfix // performs a squash merge <br /> 
git merge --abort // aborts the merge <br />

git branch --merged // shows the merged branches <br />
git branch --no--merged // shows the unmerged branches <br />

git rebase master // changes the base of the current branch <br />

git cherr-pick dad47ed //applies the given commit on the current branch <br />

git clone url <br />

git fetch origin master // fetches master from origin <br />
git fetch origin // fetches all objects from origin <br />
git fetch // same as above <br />
git pull // fetch + merge <br />
git push origin master // pushes master to origin <br />
git push // same as above <br />

git push origin v1.0 pushes tag v1.0 to origin <br />
git push origin --delete v1.0 <br />

git branch -r // shows remote tracking branches <br />
git branch -vv // shows local remote tracking branches <br />
git push -u origin bugfix // pushes bugfix to origin <br />
git push -d origin bugfix // removes bugfix from origin <br />

git remote // shows remote repos <br />
git remote add upstream url // adds a new remote called upstream <br />
git remote rm upstream // removes upstream <br />

git reset --soft HEAD^ // removes the last commit keeps the changes staged <br />
git reset --mixed HEAD^ // unstages the changes as well <br />
git reset --hard HEAD^ // discards the local changes <br />

git revert 72856ea // reverts the given commmit <br />
git revert HEAD~3.. //reverts the last three commits <br />
git revet --no-commit HEAD~3..  <br />

git reflog // shows the history of HEAD <br />
git reflog show bugfix // shows the history of bugfix pointer  <br />

git commit --amend // amending the last commit <br />

git rebase -i HEAD~5 // interactive rebasing <br />







