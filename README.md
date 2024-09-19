# BFG-learn
Learn to use BFG Repo-Cleaner to delete files with sensitive data in your project and remove the git commit logs of files.


## Pre-preparation:
- Copy the env_back file, to the env file, this file protects sensitive data
## Destination:
- Remove env file records from git commit logs

### First clone a fresh copy of your repo, using the --mirror flag, --mirror followed by the address of the repository, you can use https or ssh
```shell
git clone --mirror https://github.com/SUS0a/BFG-learn.git
```

### Delete all files named 'env' file :
```shell
java -jar .\bfg-1.14.0.jar --delete-files env .\BFG-learn.git\
```

### The BFG will update your commits and all branches and tags so they are clean, but it doesn't physically delete the unwanted stuff. Examine the repo to make sure your history has been updated, and then use the standard git gc command to strip out the unwanted dirty data, which Git will now recognise as surplus to requirements:
```shell
cd .\BFG-learn.git\
git reflog expire --expire=now --all && git gc --prune=now --aggressive
```

### Finally, once you're happy with the updated state of your repo, push it back up (note that because your clone command used the --mirror flag, this push will update all refs on your remote server):
```shell
git push
```
