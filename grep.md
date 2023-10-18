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
-` x xxx xxx xxx` == `x owner group world` syntax and `xxx == write read execute`
### file type 
- `x=>(for this) xxx xxx xxx` 
- `-` regular file 
- `d` directory 
- `c` character special file 
- `l` symbolic link 


## reading permissions
- `r` file can be read 
- `w` file can be modified . (but only if executable attribute is also set)
- `x` file can be treated as a program to be executed . ex: file can be `cd`ed into 
- `-` file cannot to read , modified or executed depending on the location of the `-` character 

# altering permissions
- `chmod mode file` : change mode 
- `who` we are changing permissions for 
- `what` change are we making ? adding ? removing ?
- `which` permissions are we setting ?

#### for `who` 
- `u` user (the owner of the file)
- `g` group (members of the group the file belongs to)
- `o` others (the "world")
- `a` all of the above 

#### for `what` operation
- `-` remove permission 
- `+` grants the permission
- `=` set a permission and removes others (previous) 

#### for `which` permission 
- `r` read permission
- `w` write permission 
- `x` execute permission 

> ex: `chmod g+w file.txt` 

### chmod octal
- `octal binary file mode`
- `0 000 ---`
- `1 001 --x`
- `2 010 -w-`
- `3 011 -wx` 
- `4 100 r--` 
- `5 101 r-x` 
- `6 110 rw-` 
- `7 111 rwx` 

> ex: `chmod 755 file.txt` 


## su user (substitute user and group ID) 
- there may be times we want to start a shell as another user  , from within our own shell session .
- `su - <user-name>` 
- to leave type : `exit` 

> in `su <user>` some environment information can be mixed . therefore `su - <user>` is recommended .


## Root User 
- in linux systems , there is a `super user` called `root` . 
- root user can do anything in the system . 
> very risky 
- ubuntu locks the root user by default .

### sudo 
- we can still run specific commands as the root user by using the `sudo` command .
- the first user has full  access to sudo , while users made after that don't by default but the original user can grant them .
- `sudo <command>`

### chown (change ownership)
- is used to change the owner and/or the group owner of a specific file or directory .
- `chown <USER> FILES(S)`    
- `chown :<GROUP> FILE(S)`
- `chown <USER>:<GROUP> FILE(S)` 

## groups 
- `group USERNAME` to view the groups that a user belongs to .
> creating groups : `addgroup GROUPNAME` 
> adding group members : `adduser USER GROUP` 


# the environment 
- the shell maintains a set of key:value pairs during a shell session , known as the `environment`.
- key:value : home-directory , working-directory , name of your shell , the name of the logged in user .
- `printenv` to view the environment variables and their current values .

## parameter expansion
- if we write out the name of an environment variable prefixed with a dollar sign ($) , the shell will replaced it with the actual value .
- `echo $<variable>`
### defining variable 
- `variable="value"`
- `export variable="value"` for using variable in child shell session .
> prompt : PROMPT VARIABLE :`PS1` in ~/.bashrc 

## startup files 
- when we log in the shell reads information from startup files. First , read from global config files that effect the environment for all users. Then , shell reads startup files for specific users.

> two type of sessions 
#### for login sessions :
- `/etc/profile` 
- `~/.bash_profile` 
- `~/.bash_login`
- `~/.profile`
#### for non-login sessions : 
- `etc/bash.bashrc` - global config for all users 
- `~/.bashrc` - specific settings for each user . This is where we can define our own settings and configuration .

## alias 
- we can define out own commands using the `alias` keyword .
- ex: `alias ll="ls -al"` in .bashrc 
> search for `useful bash aliases ?`

# script 
- the first line of our script should read `#!/bin/bash`=="use bash to interpret this file"
- `#!` is called shebang , used to tell the OS which interpreter it should use when parsing this file.
- after shebang , we need to include the path to the Bash binary. This is not bash specific . if we want to write python script , we would include the path to the python script . 
- comments : `# asdf`
## path variable 
- a list of directories where shell looks for executables .Run `echo $PATH`
- in `.profile` 
> `curl "URL"` enables data transfer over various network protocols. ex: `curl "wttr.in"`

## cron
- 
- the cron service allows us to schedule commands to run at regular intervals.
- `a`: 0-59 minute 
- `b`: 0-23 hours
- `c`: 1-31 day
- `d`: 1-12 month
- `e`: 0-6  day(of week) 
- `a b c d e command` : syntax

- cron characters 
- `*` : any value 
- `5,6`: list of values (5,6)
- `1-4`: range of values (1 to 4)
- `*/5`: step values
