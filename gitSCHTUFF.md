Git: How-to
=

...create / checkout new branch
-

`git checkout -b new-branch` - make a 	new branch and make it HEAD

...make changes in new branch & push to github
-

`git add .`
`git commit -m ""`

`git push origin new-branch` - push the new branch's changes to github 

...pull changes from main/master
-

`git pull origin master/main` - pull changes from remote upstream 

...travel back to old commit
-
`git checkout *commit hash*`