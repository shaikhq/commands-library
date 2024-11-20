# history
__check the number of commands are preserved in command history__
```shell
echo $HISTSIZE
```

# linux distribution
__find my linux distribution__
```shell
cat /etc/os-release
```

# shell
__finding my shell type__
```shell
echo $SHELL
```

# tar
__uncompress__
```shell
tar -xzf file.tar.gz
```

-x: Extract files from an archive.
-z: Decompress the archive with gunzip.
-v: Verbosely list the files processed.
-f: Use archive file.

__compress__
```shell
tar -czvf compressed_file.tar.gz directory_to_compress
```

-c: Create a new archive.
-z: Compress the archive using gzip.
-v: Verbosely list the files processed.
-f: Use archive file name provided as input

__when compressing a directory, how to skip any subdirectory with a given name?__
```shell
tar -czvf compressed.tar.gz --exclude='*subdir_to_exclude*' /directory/to/compress
```

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

__password-less SSH to a Linux machine__

From my MacOS, I wanted to SSH to a RedHat Linux VM without typing password. Here are the steps that made it work:
1. On MacOS, I generated a SSH public key using the following command:
```shell
ssh-keygen -t rsa -b 4096
```

2. Copied the above SSH key from MacOS to the remote Linux VM with the following command:
```shell
ssh-copy-id sq@linux-vm-address
```

After that, I could SSH to the Linux VM from my MacOS without typing password. Also, it worked with remote explorer in VSCode, which was running on my MacOS, and I was using it for remotely connecting to the Linux VM. 

# files and folders
__sort files in a directory by their names, using numerical order__
```shell
ls -1v *.msg .
```
for reverse numerical order,
```shell
ls -1vr *.msg .
```
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

__from a directory, see only the most recent file__
```shell
ls -lt | head -n 2
```

The first part of the above composite command will sort the list of files by their udpate timestamp. The 2nd part of the 
command, after `|`, will show the top 2 results from the sorted result list. Since the first entry in the results show some directory 
information. So, to see the actual first file  name, use `n -2` with `head`.

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

__search a string within a file__
```shell
grep "mystring" filename
```

__download a file from the internet__
```shell
curl -O https://www.python.org/ftp/python/3.12.3/Python-3.12.3.tgz
```
Note: `-O` is letter O, not digit 0. 

# vi
__how to search for a string inside vi editor?__
1. Open the file in vi editor.
2. Press / to start a forward search or ? to start a backward search.
3. Type the string you are looking for.
4. Press Enter to start the search.
e.g.,
`/mystring`

or `?mystring`
5. `n` will take you through each match at a time. 

__how to see line numbers in vi?__
`:set number`

__how to delete a range of lines from a file using vi?__
`:start_line_no,end_line_no d`
e.g., `:5,10 d`

__how to delete from a line to the end of the file?__
`:start_line_no,$d`

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

__bring remote repo content to local__
```shell
git clone https://github.com/myrepo.git
```

Replace the URL with the actual repo URL from Github. 

## Create a new branch of a Github repository
Creating a branch allow you to make a copy of the code from the main branch and make changes in the copy without overwritting the copy in the main 
branch. This can be useful when adding a new feature or fixing bug or adding any code that you don't to push in the main branch. 

1. Navigate to the local copy of the repo. 
2. Fetch the latest copy of the code from the remote repo (main):
```shell
git pull origin main
```

3. Create a new branch locally
```shell
git checkout -b new-branch-name
```
Running this command will take you to the new branch locally. 

4. Make necessary changes and then commit these changes to the remote repo:
```shell
git add .
git commit -m "Committing from my new branch"
```

5. Push the new branch and its content, including changes, to the remote repo:
```shell
git push origin new-branch-name
```

## Check out code from a git branch
```shell
git clone -b branch_name --single-branch repo_URL
```

e.g., 
```shell
git clone -b idugemea2024 --single-branch https://github.com/shaikhq/db2ml-labs.git
```

## Clone a branch from a git repo
```shell
git clone -b branch-name remote_repo_url
```

e.g.
```shell
git clone -b db2 https://github.com/shaikhq/QueryFormer.git
```

## List branches from the remote
```shell
git branch -r
```

# pyenv
__installing pyenv on MacOS__
```shell
brew install pyenv
```

__listing available pythons that can be installed via pyenv__
```shell
pyenv install --list
```

__pyenv - installing a new python (e.g., 3.12)__
```shell
pyenv install 3.12
```

While installing python using pyenv, I got errors that `ssl` and `readline` modules 
were missing. I installed them using the following commands:






