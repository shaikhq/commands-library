# tmux (a tool equivalent to screen)
__create a session__
```shell
tmux new-session -s mysession
```
__detach from a session__
`Ctrl+b` followed by `d`

__list sessions__
```shell
tmux ls
```
__attach to a session__
```shell
tmux attach -t [session id]
```
__kill a session__
```shell
tmux kill-session -t [session id]
```
# files and folders
__count the number of lines in a file__
```shell
wc -l filename
```

wc is the word count command.
-l flag tells to count the number of lines in the file.

__search for a string within a directory and its subdirectories. Limit the search to specific file types.__
```shell
find . \( -name "*.md" -o -name "*.txt" \) -exec grep -l "Hello, world!" {} \;
```
__copy the first 10 lines from a file to a new file__
```shell
head -n 10 input.txt > output.txt
```

__search for a file with part of its name within a directory and its subdirectories__
```shell
find /search_dir -name '*partialname*'
```
__search for files that contain an input string__
```shell
grep -r "my_string" /search_dir
```

__search within files with an extension__
```shell
grep -r --include="*.extension" "my_string" /search_dir
```
# git
## Pushing code - new content - e.g., file and changes to existing files - to github
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


