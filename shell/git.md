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
