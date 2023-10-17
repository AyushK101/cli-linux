## grep  
- searches for patterns in each file's `contents ` or search's within files .
-`grep "<pattern>" <file-name>`
### recursive search in grep
- `grep -r "<pattern>" <path>`
- ex: `grep -ri "ind[ie]go  ~`

## grep options 
1. `-c` : how many matches 
2. `-B` : 

## regrex / regular expression crash course 
- pattern matching language or syntax 
- `.` matches any single character  `grep "p..." hello.txt`
- `^` matches the start of a line 
- `$` matches the end of a line 
- `[abc]` matches any character in the set 
- `[^abc]` matches any character expect those mentioned
- `[A-Z]` matches character in a range 
- `*` repeats previous expression 0 or more times 
- `\` escape meta-characters 

## piping to grep 
- common use-case: use grep to filter a large chunk of data.
- ex: `ps -aux | grep ayush` will output huge data , we pipe data to grep , and then filter it down to only process that include "ayush" .
- `man grep | grep "count"` 



# permissions

- unix and unix-like systems are `multi-user` OS . More than one person can be using the same computer at the same time (ex: in different window terminals )
- on unix , users can be `single owner` or can  belong to `groups` which are given access to particular files and folders by their owners.
## file attributes 
- 10 characters printed out first are file attributes.
- tells us : `type of fie` , `read , write and execute permissions` for file's owner , the `file's group owner ` and everyone else.
-` x xxx xxx xxx` syntax 
### file type 
- `-` regular file 
- `d` directory 
- `c` character special file 
- `l` symbolic link 


## reading permissions
- `r` file can be read 
- `w` file can be modified 
- `x` file can be treated as a program to be executed 
- `-` file cannot to read , modified or executed depending on the location of the `-` character 
- 