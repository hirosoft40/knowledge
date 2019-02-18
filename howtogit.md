# .gitignore not working

<a href='https://stackoverflow.com/questions/44810511/how-to-add-empty-spaces-into-md-markdown-readme-on-github'>stack overflow</a>
Even if you haven't tracked the files so far, git seems to be able to "know" about them even after you add them to .gitignore.

NOTE : First commit your current changes, or you will lose them.

Then run the following commands from the top folder of your git repo:

```
git rm -r --cached .
git add .
git commit -m "fixed untracked files"
```

# Delete Repo File

Use git rm:

git rm file1.txt
git commit -m "remove file1.txt"
But if you want to remove the file only from the Git repository and not remove it from the filesystem, use:

git rm --cached file1.txt
git commit -m "remove file1.txt"
And to push changes to remote repo

git push origin branch_name

# push commit to another branch

git push origin branch1:branch2
or
git push <remote> <branch with new changes>:<branch you are pushing to>

# Remote origin already exists

git remote add myorigin git@github.com:myname/oldrep.git  
git remote add testtest git@github.com:myname/oldrep.git

- remove a remote repository
  git remote rm origin
