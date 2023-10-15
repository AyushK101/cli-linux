# ;) 

 ## kernel 
- Its a low level program interfacing with the hardware (CPU, RAM, disks) on top of which applications are running.
- Kernel directly interacts with the hardware by accepting machine understandable language from the shell.

 ## console
- A `physical or virtual device` that allows users to interact with a computer system, often providing a combination of text-based input and output.

 ## terminal 
- A program that `provides a user interface` to interact with a computer system through text-based input and output.

## shell
- A `command interpreter program` (like a `compiler`) that enables users to interact with an operating system, executing commands and scripts.
- A shell is basically an interface present between the kernel and the user.

## CLI (command line interface)
- The `interface(provided by terminal)` where users can input commands and execute them to perform specific tasks or operations.

## __shell scripting__ 
- Shell scripting is simply taking all the commands you would type in to do something and putting them in a text file so you don't have to type them in every time. 


1.  __there are many tasks where a GUI would require many clicks around different windows. But on the CLI these tasks can be executed with a single command.__

2. __The second reason is that by using commands you can easily automate tasks. examples, we could build a script that creates a new online repo for us, or that creates a certain infrastructure on a cloud provider for us, or that executes a simpler task like changing our screen wallpaper every hour.__

3. __The third reason is that sometimes the CLI will be the only way in which we'll be able to interact with a computer.  for example, the case when you would need to interact with a cloud platform server__

> how to know which shell is i'm running ? `echo $0`

## prompt 
- `username@machinename` followed by `~` and `$`. it can be modified !

## command structure
- `command `_-options_  _arguments_
- `arguments` : values that we provide to commands.
- `options/flags` : modify the behavior of the commands in predefined way. Prefixed by `-`. ex : `-m`

> Options and flags are both types of parameters that you can add to a command after its name. However, they have some differences in how they are written and what they do. Options are usually single letters that start with a dash (-), such as -a, -b, or -c. Flags are usually longer words that start with two dashes (--), such as --all, --verbose, or --help. Options can sometimes take an additional value after them, such as -n 5 or -f filename. Flags usually do not take values, but they can be combined with an equal sign and a value, such as --size=10 or --color=red.

### combining options 
- we can provide multiple options at once in 2 ways 
1. ex: `ncal -3 -h`
2. ex: `ncal -3h`

### long form options 
- short form options get confusing , therefore some options support equivalent long format options.
- usually full words and prefixed with two dashes instead of just one. ex: `date --universal`.
- we can use multiple long form options in a single command . ex: `sort --reverse --<file-name>.txt`

### options with parameter 
- some options requires us to pass in an additional value. 
- ex: `ncal -A 1` or `ncal -A1`

## man pages
- `manual pages` built in form of documentation 
- `man ` _command_  ; ex: `man echo`    
- to exit type `q`
### man pages content
- title/name 
- synopsis of command's syntax 
- description of all command's options 
- anything in square brackets is OPTIONAL  {  parameter required options are listed uniquely } and anything which is NOT wrapped in square brackets is required operand.
- an ellipsis `...` indicates that one or more of the proceeding operand are allowed .

## manual section 
- run command `man man` and `man -k` _command_ for knowing what sections are available for that command  
       1   Executable programs or shell commands   
       2   System calls (functions provided by the kernel)  
       3   Library calls (functions within program libraries)  
       4   Special files (usually found in /dev)  
       5   File formats and conventions, e.g. /etc/passwd  
       6   Games  
       7   Miscellaneous (including macro packages and conventions), e.g. man(7), groff(7), man-pages(7)  
       8   System administration commands (usually only for root)  
       9   Kernel routines [Non standard]  

## navigation : file-system 
> xdg-open / : for unbuntu 
- the root directory ( `/` ) : starting point of system 
- `ls /` for all directories.
-  `home` directory (  `~` ) : contains a home folder for each user on the system . 
- `pwd` : prints the path of current working directory and that directory will be know as `working directory ` for that terminal window , starting form the root `/`.
- `ls ` : lists the content of a directory. IMPORTANT OPTIONS : `-l` and `-a`
> by default : `~` is shortly return for `/home/ayush` in prompt.
- `cd` : used to change the current working directory .
- BACKING UP : `.` : represents present working directory  and `..` takes back one level hierarchy

## relative vs absolute paths
- relative to your present working directory . ex: present on `/` and want to go in ayush : `cd home/ayush`
- absolute from root every time . ex: present on `/` and want to go to in ayush : `cd /home/ayush`

## overview of some other folders in /
- bin (binary) : executable programs 
- etc : configuration files and bunch of scripts 

## creating files 
- `touch <file-name>` 

> in linux , the file extension don't tell the `extension(type)` , to check the actual type of file `file <file-name>` , but system will treat it according to its extension like .txt will open in text editor , does'nt matter if it was a .jpg and we rename it .txt .

## making directories 
- `mkdir <directory-name>`
- nested directories : `mkdir -p <name>/<name>/...`


## nano 
- `nano <file-name>`
- shortcuts :  https://www.geeksforgeeks.org/linux-commands-cheat-sheet/#nano
- (spell checker not working)

## deleting 
- hard delete files : `rm <file-name>`
- delete folders : 1. empty `rm -d <name>` OR  `rmdir <fileName> `   
2. non-empty `rm -r <name>`  
> use `-i` option for protection .

## moving items
- `mv <source> <destination>` 
## rename-ing 
- `mv <current> <newname>`
## copying
- `cp <source> <destination>`
## shortcuts 
- `ctrl+l` clear entire screen
- `ctrl+a` move cursor to beginning of line and `ctrl+e` end of line 
- `ctrl+f` move 1 char forward and `ctrl+b` move 1 char backward.
- `alt+f`  move cursor 1 word forward and `alt+b` move cursor 
- `ctrl+t` swaps the current char with preceding
- `alt+t`  swaps the current word with preceding 
- `ctrl+k` kill the text from the cursor till the end of line 
- `ctrl+u` kill the text from the cursor till the beginning of line.
- `alt+d`  kill the text from the cursor till the end of word.
- `ctrl+w` / `alt+delete` to kill the text from the current cursor through the beginning of the word.
- `ctrl-y` retrieve most recently killed text.

## history 
- `history` or `history | less` or `!<command-number-in-history>`
- searching a command in history :  `ctrl+r` and hit `ctrl+r` again and again to cycle through potential history.
- OR bash keeps record of previously entered commands at  `~/.bash_history`

## working with files 
- `cat <file1> ...` : concatenates and print content of files.
- `less <file>` : displays content of file , one page at a time. Man pages uses less. 
- `tac`: (cat spelled backward) will concatenate and print files in reverse line by line vertically.
- `rev`: reverse each line horizontally.
- `head -n  <filename>` : prints first n lines of file
- `tail -n  <filename>` : prints last n lines of file
- `wc` : tell count of words or lines or bytes 
- `sort`: by default sort a file alphabetically. : `-k<n>`sorting of column number n. , `-u` unique flag
- 

# redirection 
- redirection describes the way we can alter the source of standard input , and the destinations for standard output and error.
### __standard streams__ : the 3 standard streams are communication channels between a computer program and its environment.
>each stream gets it own numeric file descriptor , std input (0)  , std output (1)  , std error (2).
1. __standard output__ : place to which a program or command can send information.Ex: screen(default) , printer , file or other devices.  

2. __standard input__ : is where a program or command gets its input from. by default , the shell directs standard input from the keyboard .  ex: input info can come from a keyboard , file , or another command etc.  

> there is a difference between providing command line arguments (like we did till now )  and  then having a command read from the standard input 

3. __standard error__ : command and programs also have a destination to send error messages. By default, the shell directs standard error information to the screen for us to read , but we can change that also !


## redirect output symbol 

- `>`OR `1>`: tells the shell to redirect the output of a command to a specific file instead of the screen. BUT it overwrite the content of the directed file. ex: `echo "hello world" > index.txt`
- `>>` : to keep the existing content in the file and add new content ot the end of file. (APPENDING) 


## redirecting input 
> empty cat command can take standard input from keyboard and print it .
- `<` OR `0<`: to pass the content of a file to command via standard input . ex : `cat < hello.txt`
- end result of  `cat hello.txt ` and `cat < hello.txt ` looks identical but the way we get there is different.

## redirecting standard error
- by default , output on screen .
- `2>` : standard error redirecting operator OR `2>>` for preventing overriding .

## redirect multiple streams
- `cat < original.txt >> output.txt` using cat to read in the contents of original.txt and redirecting the output to a file called output.txt .
- if we have to redirect both standard output and standard error to the same file ,
1. `ls docs >> output.txt 2> output.txt`
2. `ls docs >> output.txt > 2>&`
3. `ls docs &>> output.txt`
> order matters : redirect std output first !


## piping 
- The pipe is used to redirect a stream from one program(command) to another program . Takes standard input and gives standard output.
- `|` : pipe character : to separate two commands . The output of the first command will be passed to the standard input of the second command .
- `command 1 | command 2 | command 3 | ...` can pipe multiple commands.
- read-as : piping the output to command 2 ....

## __>__ vs __|__ 
- `>` : connects a command to some file 
- `|` : connects to another command

## tr command !
- translate , delete , squeeze characters from std input , writing to standard output . ex: `cat hello-world.txt | tr l L` : translate all `l` to `L`.
- character class :    
[:alnum:]	letters and digits  
[:alpha:]	letters  
[:blank:]	usually Spaceand TAB  
[:cntrl:]	all control characters  
[:digit:]	digits  
[:graph:]	printable characters excluding Space  
[:lower:]	lower-case letters  
[:print:]	all printable characters  
[:punct:]	punctuation marks  
[:space:]	whitespace characters  
[:upper:]	upper-case letters  
[:xdigit:]	hexadecimal digits (0-9A-Fa-f)   

## tee command 
- tee reads standard input and copies both to standard output and to a file . This allows us to capture information part of the way through a pipeline , without interrupting the flow .
- `cat file1.txt file2.txt ... | tee <saving-file> | commands ...`





# expansion & substitution 
- __wildcard characters__ : special characters that can `stand in for unknown characters in a text value`. These are expanded by shell (before command execution). ex: ` * , ? , [] , ^ , character classes `

## pathname expansion 

### * 
- the * represents __zero or more__ character in a file name. ex: ` ls *.html` , `cat *b* ` , `ls blue*` 

### ? 
- the ? represents any __single__ character . ex: `ls app.??` , `ls pic?ero.png`, `echo *.???`etc 

### []
- inside [] we can specify a range of characters to match .
ex: `ls pic[123],png` will only match pic1.png , pic2.png and pic3.png  
`ls file[0-9]` will match from file1 to file9  
`ls [A-F]*` , `ls *[a-z]` etc 

### negative ranges [^]
- `ls [^a]*` will match any file that don't start with "a"  

## tilde expansion 
- `~` == home directory 

## brace expansion 
- used to generate multiple arbitrary strings based on a pattern . We provide a set of strings inside `{}` 
and optional surrounding prefixes and suffixes .
- `touch Day-{M,T,W,T,F,S,23}-planner_{am,pm}.txt` 
> __ranges__ : we can provide a numeric range , which will be used to generate a sequence    
ex: `mkdir jan{1..31}`|| `echo {2..10..2}`(interval) || `touch group-{a..e}.txt` || `mkdir -p {mon,tue,wed}/{breakfast,lunch,dinner}` || ` echo {x,y{1..5},z,g}`

## arithmetic expansion 
- the shell will perform , using the `$((expression))` syntax. `+,-,*,/,%,**`   
ex: `echo $((43982*32))`
> always whole number 

## quoting 
- shell ignore two or more spaces , bcz it performs `word splitting`.
- when hit `$` , it tells shell to find variable 
> double quote ""
- respect spacing , but ignore special character expect  ` $ , \ , backtick `
> single quote ''
- suppress all forms of substitution 

## command substitution 
- `$(command)` syntax to display the output of another command .  
ex: `echo today is $(date -l)`
> another syntax : `command` ex: `echo who am i ? `whoami` !`


# finding files 
- 
