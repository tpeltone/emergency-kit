# My Git Kit

## Commands

### Good links

[Jakub Pawlowicz Git Cheat Sheet](https://github.com/jakubpawlowicz/git-cheat-sheet/blob/master/README.md)

### Make folder a Git folder (this will be your local master)

```bash
git init
```

### Create a file with text

```bash
echo "my text" > myfile.txt
```

### Append text to a file

```bash
echo "my new row of text" >> myfile.txt
```

### Add file into git

```bash
git add .
git add myfile.txt
git add myfile.txt myfile2.txt
```

### Stage file in git

```bash
git stage myfile.txt
```

### Commit file to git

```bash
git commit -m "my commit comment"
```

### Create a new local branch

```bash
git branch --create dev
```

### Create connection to remote origin in GitHub

```bash
# You need to Create the remote origin in git hub first
git remote add origin <url>
```

### Check out branch (change branch)

```bash
git checkout dev
git checkout -b dev
```

### Log decorate

```bash
git log --oneline --graph --decorate
```

### Rebase

[Read more about git rebase](https://medium.com/datadriveninvestor/git-rebase-vs-merge-cc5199edd77c):

```bash
# rebase the 21 last changes to one commit
git rebase  -i HEAD~21

# abort un going rebase
git rebase --abort

# to rewrite/amend the current history of the latest commit
git commit --amend

# once you are satisfied with your changes
git rebase --continue

# Edits the todo
git rebase --edit-todo

# targeting
git rebase master
```

### Merge

```bash
git merge master
```

### Reset change

```bash
git reset HEAD~
```

### Get original file after a change

```bash
git checkout -- file2.txt
```

### Prune

```bash
git fetch -p
```

### Remote

```bash
git remote -v

# this is when cloned from another repo and then add the ref
git remote add ref ssh://git@stash.srv.volvo.com:7999/esw/jcasc-ref.git 
git remote set-url ref ssh://git@stash.srv.volvo.com:7999/esw/jcasc-ref.git
```

### Push

```bash
git push -u ref --all
```

### Diff

```bash
git diff origin/master README.md
```

### Delete local branch

```bash
git branch -d feature_jcasc
```

### Create a pull request

```bash
git checkout -b feature_jcasc
git push -u origin feature_jcasc
```

Got to BitBucket/GitHub/Azure DevOps:

* Create Pull request
* Select source branch
* Select reviewer

### Tags

Get the latest commits SHA-1

```bash
git log --oneline --graph --decorate
```

```bash
* b38d91e (HEAD -> master, origin/master, origin/HEAD) added new files and cleaned up
* 3928431 Typeo
* 855daee Typeo
* 8073651 Added docker-commands.md
```

Create annotated tag

```bash
git tag -a -m 'The first v1.0.0' v1.0.0 b38d91e
```

Delete

* local

```bash
git tag -d v1.0.0  
```

* remote

```bash
  git tag -d v1.0.0
  git push origin :refs/tags/v.1.0.0
```

Get

```bash
git describe --tags --long
```

Push

Tags are not sent to the remote repository by the git push command. We need to explicitly send these tags to the remote server by using the following command:

```bash
git push origin <tagname>
````

We can push all the tags at once by using the below command:

* light weight tags

```bash
git push origin --tags
```

* annotated tags

 ```bash
git push origin --follow-tags
 ```

#### Read more about tags

[How to delete a tag in Git](http://www.manikrathee.com/how-to-delete-a-tag-in-git.html)

[How do you push a tag to a remote repository using Git?](https://stackoverflow.com/questions/5195859/how-do-you-push-a-tag-to-a-remote-repository-using-git)

[What is the difference between an annotated and unannotated tag?](https://stackoverflow.com/questions/11514075/what-is-the-difference-between-an-annotated-and-unannotated-tag)

How to get the latest git commit SHA-1 in a repository:

* How to get the latest git commit SHA-1 id in a repository?

* And how to get the first 8 digits of the SHA-1?

Get the commit SHA-1 hash ID:

```bash
git rev-parse HEAD
```

If you want to get the first 8 digits only, use

```bash
git rev-parse HEAD | cut -c 1-8
```

Here, cut -c 1-8 gives you bytes 1 to 8.

BTW: if you have tags tagging the versions, you may use

```bash
git describe --tags --long
```

to get a better string for IDs like

v2.0-40-gdc25d60
Here, ‘v2.0′ is the latest tag. ’40’ is the number of commits after the ‘v2.0’ tag and ‘gdc25d60’ is the first 8 digits of the commit sha-1 hash ID.

### Rename file

```bash
git mv old_filename new_filename
git status
git commit -m "Rename file"
git push origin your-branch
```

### Read the .gitconfig

```bash
cat ~/.gitconfig
```

### Add alias git lo

```bash
git config --global alias.lo "log --graph --pretty=format:'%C(bold red)%h%Creset -%C(bold yellow)%d%Creset %s %C(bold green)(%cr) %C(blue)<%an>%Creset' --abbrev-commit"
```
