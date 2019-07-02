# Git commands

Make folder a Git folder (this will be your local master):

```bash
git init
```

Create a file with text:

```bash
echo "my text" > myfile.txt
```

Append text to a file:

```bash
echo "my new row of text" >> myfile.txt
```

Add file into git:

```bash
git add .
git add myfile.txt
git add myfile.txt myfile2.txt
```

Stage file in git:

```bash
git stage myfile.txt
```

Commit file to git:

```bash
git commit -m "my commit comment"
```

Create a new local branch:

```bash
git branch --create dev
```

Create connection to remote origin in GitHub _(you need to Create the remote origin in git hub first)_:

```bash
git remote add origin <url>
```

Check out branch (change branch):

```bash
git checkout dev
git checkout -b dev
```

Log decorate:

```bash
git log --oneline --graph --decorate
```

Rebase: [Read more about git rebase](https://medium.com/datadriveninvestor/git-rebase-vs-merge-cc5199edd77c):

```bash
git rebase master
```

Merge:

```bash
git merge master
```

Reset change:

```bash
git reset HEAD~
```

Get original file after a change:

```bash
git checkout -- file2.txt
```

Prune:

```bash
git fetch -p
```

Remote:

```bash
git remote -v
git remote add ref ssh://git@stash.srv.volvo.com:7999/esw/jcasc-ref.git (this is when cloned from enother repo and then add the ref)
git remote set-url ref ssh://git@stash.srv.volvo.com:7999/esw/jcasc-ref.git
```

Push:

```bash
git push -u ref --all
```

Diff:

```bash
git diff origin/master README.md
```

Delete local branch:

```bash
git branch -d feature_jcasc
```

Create a pull request:

```bash
git checkout -b feature_jcasc
git push -u origin feature_jcasc
```

Got to BitBucket/GitHub/Azure DevOps:
* Create Pull request
* Select source branch
* Select reviewer

Tag:

```bash
git lo (git lo is an alias for git log)
git tag -a -m '1.0.0' 1.0.0 bee4184 (sha1)
git describe
```

Rename file:

```bash
git mv old_filename new_filename
git status
git commit -m "Rename file"
git push origin your-branch
```

### Add alias git lo

```bash
cat ~/.gitconfig
git config --global alias.lo "log --graph --pretty=format:'%C(bold red)%h%Creset -%C(bold yellow)%d%Creset %s %C(bold green)(%cr) %C(blue)<%an>%Creset' --abbrev-commit"
```
