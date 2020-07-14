1. Some basic GIT commands:
     - git init
     - git status
     - git add . / git add <file-name>
     - git commit -m <main-content-of-the-commit>

2. Some basic commands for displaying commits:
     - git log: show commits history
     - git show <commit-ID>: only show updated content of the commit
     - git diff: not only show code has been updated but also display the previous code of the newly changed files, only available before that file is committed

3, Some common terms in GIT:
     - working directory: is our project folder which is under GIT management; newly created files and recently modified files are stored here
     - staging area: when we first initialize git project, all the files are in working directory. When we use 'git add', they will be moved to 'staging area'
     - git repository: after our files are committed, they will be moved to git repository and the working directory is completely clean

4. Discard changes using 'git checkout' and 'git reset':
     - git checkout -- <file-name> to discard changes in working directory
     - git reset HEAD <file-name> to un-stage the file (move it from staging area down to working directory; then, we can use git checkout like above again)
     => available only after 'git add' has been applied

5. Using git reset to discard commit:
     - git reset --hard <commit-ID>: restore our code in the selected commit as well as delete all other commits we created after adding this selected one
     - git reset --soft <commit-ID>: maintain our code in the selected commit. However, this commit is now moved down to staging area
     => From here, we can use 'git reset HEAD...' to un-stage it or 'git commit -m...' to commit it again
     - git reset --mixed <commit-ID>: maintain our code in the selected commit. However, this commit is now moved down 2 levels to working directory
     => from here, we can use 'git add' to move it back to staging area and then use 'git commit -m...' to make a new commit
                         or we can use use 'git checkout -- <file-name>' to discard any changes

6. How to use .gitignore:
     - this folder is used to store dummy files, especially the node_modules folder that we don't want to add into working directory so that GIT won't track them
     - How to use .gitignore:
          + create a new file in our project folder named: .gitignore
          + in this new file, simply type the name of the files we want to be ignored
          + then, run 'git add .gitignore' and 'git commit -m ...'