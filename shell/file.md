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

__search for a file with part of its name within a directory and its subdirectories__
```shell
find /search_dir -name '*partialname*'
```

