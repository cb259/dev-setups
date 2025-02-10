# GIT Reference

# Re-Evaluate .gitignore
This process can be used to re-evaluate a .gitignore file and ensure the files in the repository do not include those that should be ignored. This comes in handy when files are synched to the repo before a gitignore entry is added.

Note: That a history of the files may still exist in the repo.

1. Remove cached files (Run from root folder of the repo):
```
git rm -r --cached .
```

2. Re-add all files.
```
git add .
```

3. Push new commit.
```
git commit -m "Commit with .gitignore"
```