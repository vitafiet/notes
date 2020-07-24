# Create a new GitHub repository with contents from a local directory

1) Create the GitHub repository.

![Image](git-media/repo-create.png)

*Tip*: do not initialize the repository with `readme`, `license` or `gitignore`.

2) On your local machine, open GitBash and navigate to the location/directory you are looking to add to the repository created in Step-1 above.

3) Initialize the local directory as a Git repo.

```
$> git init
```

4) Add the local files/directories in the new local repository. (Staging for commit).

```
$> git add .
```

5) Commit the staged files/directories.

```
$> git commit -m "Initial commit"
```

6) Use the remote repository's GIT URL and run `git remote add origin`.

![Image](git-media/copy-remote-repository-url.png)

```
$ git remote add origin remote repository URL
# Sets the new remote
$ git remote -v
# Verifies the new remote URL
```

7) Push the changes from the local repo. to GitHub.

```
$ git push origin master
```
