*** Important Commands in bash ***
Create a folder:
mkdir myfolder

Change directory:
cd myfolder

Make folder a Git folder (this will be your local master):
git init

Create a file with text:
- echo "my text" > myfile.txt

Append text to a file:
- echo "my new row of text" >> myfile.txt

Add file into git:
git add .
git add myfile.txt
git add myfile.txt myfile2.txt

Stage file in git:
git stage myfile.txt

Commit file to git:
git commit -m "my commit comment"

Create a new local branch:
git branch --create dev

Create connection to remote origin in GitHub (Create the remote origin in git hub first)
git remote add origin <url>

Check out branch (change branch):
git checkout dev
git checkout -b dev

Log decorate:
git log --oneline --graph --decorate

Rebase (https://medium.com/datadriveninvestor/git-rebase-vs-merge-cc5199edd77c):
git rebase master

Merge:
git merge master

Reset change:
git reset HEAD^

You need original file after a change:
git checkout -- file2.txt

Prune:
git fetch -p

Remote:
git remote -v
git remote add ref ssh://git@stash.srv.volvo.com:7999/esw/jcasc-ref.git (this is when cloned from enother repo and then add the ref)
git remote set-url ref ssh://git@stash.srv.volvo.com:7999/esw/jcasc-ref.git

Push:
git push -u ref --all

Diff:
git diff origin/master README.md

Delete local branch:
git branch -d feature_jcasc

Create a pull request:
git checkout -b feature_jcasc
git push -u origin feature_jcasc

Got to BitBucket
Create Pull request
Select source branch
Select reviewer

Tag:
git lo (git log)
git tag -a -m '1.0.0' 1.0.0 bee4184 (sha1)
git describe

added alias git lo and git graph
cat ~/.gitconfig
git config --global alias.lo "log --graph --pretty=format:'%C(bold red)%h%Creset -%C(bold yellow)%d%Creset %s %C(bold green)(%cr) %C(blue)<%an>%Creset' --abbrev-commit"
 



