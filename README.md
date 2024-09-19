# BFG-learn
Learn to use BFG Repo-Cleaner to delete files with sensitive data in your project and remove the git commit logs of files.



### First clone a fresh copy of your repo, using the --mirror flag, --mirror followed by the address of the repository, you can use https or ssh

git clone --mirror https://github.com/SUS0a/BFG-learn.git


### Delete all files named 'env' file :
java -jar bfg.jar --delete-files env BFG-learn.git
