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


-------------------------<br />
to push you need to create an ssh key with the command <br />
ssh-keygen -t rsa -b 4096 -C "emaladdress" <br />
there are two keys key and key.pub you can share key.pub(public) <br />
then go to your account in settings add ssh and gpg keys add you public key there <br />
then comeback to cli run these commands <br />
eval "$(ssh-agent -s)" <br />
ssh-add -K ~/.ssh/key(private) <br />
 
