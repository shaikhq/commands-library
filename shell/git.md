# Pushing code - new content - e.g., file and changes to existing files - to github
1. navigate to local repo:
```shell
cd /local_git_proj
```
2. Add new changes to git
``` shell
git add .
```
. will add everything. Alternatively, you can add selectively. 

3. commit changes
``` shell
git commmit -m "Commit comment"
```

4. push changes to github
``` shell
git push origin main
```

In case the remote repo (github) has some changes that are not present in your local repo, you'll first need to bring those remote changes to the local copy and merge them. In 
order to do so, first fetch and merge remote changes:
```shell
git pull origin main
```

Then do the push (step 4 above)

# Creating a new branch
- create a branch:
```shell
git branch branch-name
```

- switch to the new branch:
```shell
git checkout branch-name
```

- creating a new branch and switching to it using a single command:
```shell
git checkout -b branch-name
```

# Adding a fork URL to a local repo, which currently only has the origin repo link
```shell
git remote add sq_queryformer https://github.com/shaikhq/QueryFormer.git
```

Here, `sq_queryformer` is my fork whose link is above. 

# Pushing a branch to my fork, instead of the origin repo
```shell
git push sq_queryformer main-copy
```

# How to remove a file from last commit
```shell
git reset --soft HEAD~1
git restore --staged <file>
git commit -m "Updated commit without the file"
```

