# *nix Scavenger Hunt

Complete the following challenges using the command-line interface on your favorite
Unix or Linux operating system. You are welcome and encouraged to consult any
additional documentation online or in books.

Please add your answers/responses/text pastes to the document after each prompt.

Note: For some of the challenges you will need to reference files included with
this repository, so you will need to fork the repo into your own Github account
and then clone it to your development environment.

## The Challenges

### Navigating the Filesystem

* Get an idea of where you are in the operating system. Use the `pwd` command to find your "path to working directory"--your current location in the filesystem of your devbox. *Paste the output of the `pwd` command here:* 
$ pwd
/c/Users/a_mas/projects/wats3030/wats1030-intro-to-unix

* Discover more about this filesystem. Use `ls` (the "list" command)to see what is in this directory. *What directories and files do you see when you run `ls`?*
$ ls
challenge_files  LICENSE  nix_scavenger_hunt.md  nix_scavenger_hunt_stretch.md  README.md  super_scavengers.md

* You can use *options* to modify how a command runs. Try using `ls -alh` to see the contents of your current directory. *How are the results different when you use the `-alh` options?*
$ ls -alh
total 74K
drwxr-xr-x 1 a_mas 197609    0 Jan 18 12:58 .
drwxr-xr-x 1 a_mas 197609    0 Jan 18 12:57 ..
drwxr-xr-x 1 a_mas 197609    0 Jan 18 12:58 .git
drwxr-xr-x 1 a_mas 197609    0 Jan 18 12:58 challenge_files
-rw-r--r-- 1 a_mas 197609 1.1K Jan 18 12:57 LICENSE
-rw-r--r-- 1 a_mas 197609 5.5K Jan 18 12:58 nix_scavenger_hunt.md
-rw-r--r-- 1 a_mas 197609  325 Jan 18 12:58 nix_scavenger_hunt_stretch.md
-rw-r--r-- 1 a_mas 197609 2.8K Jan 19 17:23 README.md
-rw-r--r-- 1 a_mas 197609  268 Jan 18 12:58 super_scavengers.md

* The `man` ("manual") command tells you more about how any given command works. (*WARNING:* CodeAnywhere does not support the man command. You can click the following link to complete this task:). Run `man` to see instructions about how to use `man`. Then use `man` to learn what the `a`, `l`, and `h` options mean when used with the `ls` command. *Write down what those options do?*
man is the system's manual pager. Each page argument given  to  man  is
normally  the  name of a program, utility or function.  The manual page
associated with each of these arguments is then found and displayed.  A
section,  if  provided, will direct man to look only in that section of
the manual.  The default action is to search in all  of  the  available
sections following a pre-defined order ("1 n l 8 3 2 3posix 3pm 3perl 5
4 9 6 7" by default, unless overridden  by  the  SECTION  directive  in
/etc/manpath.config),  and  to  show only the first page found, even if
page exists in several sections.

man -a 
Display,  in  succession,  all  of the available intro manual pages
contained within the manual.  It is possible to quit  between  suc-
cessive displays or skip any of them.
man -l
This  command  will  decompress  and format the nroff source manual
page ./foo.1x.gz into a device independent (dvi) file.   The  redi-
rection is necessary as the -T flag causes output to be directed to
stdout with no pager.  The output could be viewed  with  a  program
such  as  xdvi or further processed into PostScript using a program
such as dvips.
man -h
This  option  will  cause groff to produce HTML output, and will
display that output in a web browser.  The choice of browser  is
determined  by the optional browser argument if one is provided,
by the $BROWSER  environment  variable,  or  by  a  compile-time
default  if  that  is unset (usually lynx).  This option implies
-t, and will only work with GNU troff

* Commands can also take *arguments*, which are usually the names of files or locations that you want the command to work with. Try running `ls /` to see what files are in the *root* directory of the filesystem. *What files and directories do you see listed?*
$ ls /
bin  cmd  dev  etc  git-bash.exe  git-cmd.exe  LICENSE.txt  mingw64  proc  ReleaseNotes.html  tmp  unins000.dat  unins000.exe  unins000.msg  usr

* A Unix filesystem has a few special shortcuts to refer to specific locations. `/` indicates the *root* of the filesystem, meaning the top-most directory in the filesystem hierarchy. Use the `cd` ("change directory") command to move to the root directory. (Hint: Use `man` to look up the `cd` command if you have any issues) *Then run `pwd` and paste the output here:*
$ pwd
/c/Users/a_mas

* Another special shortcut in Unix is the `~` location. This indicates the *user root* directory, meaning the top-most directory in the hierarchy that comes below your user account. Use `cd` to move to `~`. *Run `pwd` and paste the response here:*
$ pwd
/c/Users/a_mas

* Change directory into the `challenge_files` directory. Use `ls` to find only the files with a `.demo` pattern. *How many files do you find?*
$ find . -type f -name "*.demo*"
./2015_special_stuff.demo
./cloaked-wookie.demo
./scooter-double-mamba.demo

* Use the `cd` command to move "up" one directory. *Where are you in the filesystem now?*
a_mas@DESKTOP-EVQN9L9 MINGW64 ~/projects/wats3030/wats1030-intro-to-unix/challenge_files (master)
$ cd ..
a_mas@DESKTOP-EVQN9L9 MINGW64 ~/projects/wats3030/wats1030-intro-to-unix (master)

* Press the up arrow on your keyboard. *What just happened?*
displays command entered earlier.

* Press the up arrow a few more times. *What do you see?*
cycles through commands enter earlier

* Run the `history` command. *What do you see?*
I see all the commands I have entered in ther terminal.

### Observing the System

* Discover what account you are logged into using the `whoami` command. *What username are you currently using?*
$ whoami
a_mas
* Discover who else is on your system with the `who` command. *Are any other users using your system? If so, list them here:*
no other users currently.

* How long has your system been running? Use `uptime` to see, and *paste the result here:*
uptime did not work, I tried with -p, and -s.
man: /var/run/utmp
information about who is currently logged on

* Run `ps aux` and review the results. (Hint: Use `man` to learn more about the `ps` command and options.) *How do you interpret what you see here?*
$ ps aux
      PID    PPID    PGID     WINPID   TTY         UID    STIME COMMAND
    14836       1   14836      14836  cons2     197609   Jan 19 /usr/bin/bash
    17032   13636   17032      18676  cons0     197609 18:27:17 /usr/bin/ps
    13636       1   13636      13636  cons0     197609   Jan 19 /usr/bin/bash
The POSIX and UNIX standards require that "ps -aux" print all processes owned by a user
named "x", as well as printing all processes that would be selected by
the -a option.  If the user named "x" does not exist, this ps may
interpret the command as "ps aux" instead and print a warning.  This
behavior is intended to aid in transitioning old scripts and habits.
It is fragile, subject to change, and thus should not be relied upon.

* Run `top` and review the results. (Hint: You may need to use `ctrl-c` to get out of this app.) *How do you interpret what you see here?*
top did not work, ctrl-c is suppose to stop surrent command.

### Finding and Viewing Files

* Make sure you are in the `challenge_files` directory. Use the `*` wildcard to find all the files that have the word "credit" in the filename. *How many files did you find?*
$ ls credit*
credit_cards.txt  credit_cards2.txt

* Use the `more` command to view one of the `credit_cards` files you just discovered. (Hint: Type `q` to quit viewing the file. Press the `spacebar` to page down. Use your keyboard arrows to move up/down.) *What is the date in the file you have viewed?*
more command dose not work. 
$ cat credit_cards2.txt
lists credit card numbers

* Use the `find` command to search for files more effectively. Search the sub-directories under `challenge_files` to find the location of the file named `modi_laboriosam.txt`. *Where is that file located?*
$ find . -type f -name "modi_laboriosam.txt"
./tmp/modi_laboriosam.txt

* Use the `grep` command to search for text within a file. Use `grep` on all the `.user` files in `challenge_files` to find which files contain "WA" (the abbreviation for Washington state). *How many files did you find?*
$ grep WA * user
grep: 01: Is a directory
Britt-Erdman.user:O'Harachester, WA 37261
Lissie-Strosin.user:Jewessfurt, WA 00816-7241
grep: serial-numbers: Is a directory
grep: test2: Is a directory
grep: tmp: Is a directory
grep: wow: Is a directory
grep: user: No such file or directory

* Use the `-r` option of `grep` to *recursively* find the text "Waldo" hidden in a file somewhere under the `challenge_files` directory. *Paste the result showing the file and line where the word "Waldo" shows up.*
$ grep -r Waldo
serial-numbers/eaque_molestiae.txt:Ut est maiores quia autem. Nisi modi Waldo sed corporis sit explicabo ut est. Et est placeat ea sunt sunt consectetur sunt incidunt. Explicabo vel esse blanditiis dolorem culpa non quia.

### Pipes and Connecting Commands

* Sometimes it's useful to output the results of a command to a text file for further analysis, reference, or processing. Try running `ls > files.txt`. Notice that the file `files.txt` was created. View that file using `more`. *What do you see in the `files.txt` file?*
$ ls > files.txt
files.txt empty

* Notice that if you run `ls -alh` in the `challenge_files` directory, the files scroll by very quickly. Sometimes it would be better to get the results in a paginated format. Try running `ls -alh | more`. *Describe what you see when you run `ls -alh | more`.*
$ ls -alh | more
bash: more: command not found

* Earlier, when you viewed the list of active processes on your devbox using `ps aux`, the list was probably really long. You can make this list more manageable by using the pipe (`|`) to filter the results of `ps` using `grep`. Run `ps aux | grep <your_username>` to see what processes are running for your specific user. *Paste the list of processes that reference your username here:*
$ ps aux | grep a_mas
list is blank
