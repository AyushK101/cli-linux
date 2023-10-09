# ;)

 ## console
- A `physical or virtual device` that allows users to interact with a computer system, often providing a combination of text-based input and output.

 ## terminal 
- A program that `provides a user interface` to interact with a computer system through text-based input and output.

## shell
- A `command interpreter program` (like a `compiler`) that enables users to interact with an operating system, executing commands and scripts.

## CLI (command line interface)
- The `interface(provided by terminal)` where users can input commands and execute them to perform specific tasks or operations.

## __shell scripting__ 
- Shell scripting is simply taking all the commands you would type in to do something and putting them in a text file so you don't have to type them in every time. 


1.  __there are many tasks where a GUI would require many clicks around different windows. But on the CLI these tasks can be executed with a single command.__

2. __The second reason is that by using commands you can easily automate tasks. examples, we could build a script that creates a new online repo for us, or that creates a certain infrastructure on a cloud provider for us, or that executes a simpler task like changing our screen wallpaper every hour.__

3. __The third reason is that sometimes the CLI will be the only way in which we'll be able to interact with a computer.  for example, the case when you would need to interact with a cloud platform server__

> how to know which shell is i'm running ? `echo $0`

## prompt 
- `username@machinename` followed by `~` and `$`.

## command structure
- `command `_-options_  _arguments_
- `arguments` : values that we provide to commands.
- `options/flags` : modify the behavior of the commands in predefined way.Prefixed by `-`. ex: `-m`

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

> in linux , the file extension don't tell the extension , to check the actual type of file `file <file-name>` , but system will treat it according to its extension like .txt will open in text editor.

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



## redirection 
- redirection describes the way we can alter the source of standard input , and the destinations for standard output and error.

#### __standard streams__ : the 3 standard streams are communication channels between a computer program and its environment.
1. __standard output__ : place to which a program or command can send information.Ex: screen(default) , printer , file or other devices.  

2. __standard input__ : is where a program or command gets its input from. by default , the shell directs standard input from the keyboard .  ex: input info can come from a keyboard , file , or another command etc.  
> there is a difference between providing command line arguments (like we did till now )  and  then having a command read from the standard input 

3. __standard error__ : command and programs also have a destination to send error messages. By default, the shell directs standard error information to the screen for us to read , but we can change that also !










