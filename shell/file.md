# count the number of lines in a file
```shell
wc -l filename
```

wc is the word count command.
-l flag tells to count the number of lines in the file.

# search for a string within a directory and its subdirectories. Limit the search to specific file types.
find . \( -name "*.md" -o -name "*.txt" \) -exec grep -l "Hello, world!" {} \;
