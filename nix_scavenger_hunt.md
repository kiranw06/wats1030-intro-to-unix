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
/home/cabox/workspace

* Discover more about this filesystem. Use `ls` (the "list" command)to see what is in this directory. *What directories and files do you see when you run `ls`?*
I found the two files liested below and the challenge_files directory
LICENSE          nix_scavenger_hunt.md                       
README.md        nix_scavenger_hunt_stretch.md               
challenge_files  

* You can use *options* to modify how a command runs. Try using `ls -alh` to see the contents of your current directory. *How are the results different when you use the `-alh` options?*
ls -alh command give a more thourgh directory list including all of my development boxes and the README file. 
drwxrwxr-x 4 cabox cabox 4.0K Jan 16 18:38 .                 
drwxr-xr-x 7 cabox cabox 4.0K Jan 16 18:38 ..                
drwxrwxr-x 8 cabox cabox 4.0K Jan 16 18:38 .git              
-rw-rw-r-- 1 cabox cabox 1.1K Jan 16 18:38 LICENSE           
-rw-rw-r-- 1 cabox cabox 1.4K Jan 16 18:38 README.md         
drwxrwxr-x 7 cabox cabox 4.0K Jan 16 18:38 challenge_files   
-rw-rw-r-- 1 cabox cabox 5.5K Jan 16 18:38 nix_scavenger_hunt.md                                                          
-rw-rw-r-- 1 cabox cabox  317 Jan 16 18:38 nix_scavenger_hunt_stretch.md  


* The `man` ("manual") command tells you more about how any given command works. (*WARNING:* CodeAnywhere does not support the man command. You can click the following link to complete this task: http://linux.die.net/man/)Run `man` to see instructions about how to use `man`. Then use `man` to learn what the `a`, `l`, and `h` options mean when used with the `ls` command. *Write down what those options do?*
-a, --all:
do not hide entries starting with .
-l
use a long listing format
-h, --human-readable
print sizes in human readable format (e.g., 1K 234M
   2G)

* Commands can also take *arguments*, which are usually the names of files or locations that you want the command to work with. Try running `ls /` to see what files are in the *root* directory of the filesystem. *What files and directories do you see listed?*
bin   etc       lib    mnt   root  srv  usr                  
boot  fastboot  lib64  opt   run   sys  var                  
dev   home      media  proc  sbin  tmp    

* A Unix filesystem has a few special shortcuts to refer to specific locations. `/` indicates the *root* of the filesystem, meaning the top-most directory in the filesystem hierarchy. Use the `cd` ("change directory") command to move to the root directory. (Hint: Use `man` to look up the `cd` command if you have any issues) *Then run `pwd` and paste the output here:*
/home/cabox  

* Another special shortcut in Unix is the `~` location. This indicates the *user root* directory, meaning the top-most directory in the hierarchy that comes below your user account. Use `cd` to move to `~`. *Run `pwd` and paste the response here:*
cabox@box-codeanywhere:~$ ~                                  
-bash: /home/cabox: Is a directory                           
cabox@box-codeanywhere:~$ pwd                                
/home/cabox 

* Change directory into the `challenge_files` directory. Use `ls` to find only the files with a `.demo` pattern. *How many files do you find?*
Changed directory:
cabox@box-codeanywhere:~/workspace$ cd challenge_files  
cabox@box-codeanywhere:~/workspace/challenge_files$ pwd 
/home/cabox/workspace/challenge_files 
3 .demo files:
cabox@box-codeanywhere:~/workspace/challenge_files$ ls *
.demo                                                   
2015_special_stuff.demo  scooter-double-mamba.demo      
cloaked-wookie.demo                                     

* Use the `cd` command to move "up" one directory. *Where are you in the filesystem now?*
Moved to workspace directory:
cabox@box-codeanywhere:~/workspace/challenge_files$ cd ..                                                       
cabox@box-codeanywhere:~/workspace$                     
                                                
* Press the up arrow on your keyboard. *What just happened?*
Repeated previous command:
cabox@box-codeanywhere:~/workspace$ cd ..               
                                             
* Press the up arrow a few more times. *What do you see?*
This command continued to retreive previous commands: 
cabox@box-codeanywhere:~/workspace$ ls *.demo

* Run the `history` command. *What do you see?*
The history command logged a history of all my commands:
cabox@box-codeanywhere:~/workspace$ history             
    1  ls challenge_files                               
    2  cd challenge                                     
    3  cd challenge files                               
    4  cd challenge_files                               
    5  pwd                                              
    6  ls.demo                                          
    7  ls .demo                                         
    8  ls -a .demo                                      
    9  ls -A .demo                                      
   10  ls --all .demo                                   
   11  ls .demo                                         
   12  .demo                                            
   13  ls .demo                                         
   14  ls {.demo}                                       
   15  ls *{.demo}                                      
   16  ls -l                                            
   17  ls -l .demo                                      
   18  ls*.demo                                         
   19  ls *.demo                                        
   20  cd ..                                            
   21  pwd                                              
   22  history           
   

### Observing the System

* Discover what account you are logged into using the `whoami` command. *What username are you currently using?*
cabox user:
cabox@box-codeanywhere:~/workspace$ whoami              
cabox  

* Discover who else is on your system with the `who` command. *Are any other users using your system? If so, list them here:*
No other users:
cabox@box-codeanywhere:~/workspace$ who                 
cabox    pts/0        Jan 17 12:18 (54.186.244.104) 

* How long has your system been running? Use `uptime` to see, and *paste the result here:*
cabox@box-codeanywhere:~/workspace$ uptime              
 12:44:54 up 29 min,  1 user,  load average: 0.00, 0.00,
 0.00                                                   
 
* Run `ps aux` and review the results. (Hint: Use `man` to learn more about the `ps` command and options.) *How do you interpret what you see here?*
This seems to have logged statistics of all the commands that I've ran, interpreting when they started, how long it took to process, what directory was used etc. 
cabox@box-codeanywhere:~/workspace$ ps aux              
USER       PID %CPU %MEM    VSZ   RSS TTY      STAT STAR
T   TIME COMMAND                                        
root         1  0.0  0.4  33208  2544 ?        Ss   12:1
5   0:00 init                                           
root         2  0.0  0.0      0     0 ?        S    12:1
5   0:00 [kthreadd/539000]                              
root         3  0.0  0.0      0     0 ?        S    12:1
5   0:00 [khelper/539000]                               
root       148  0.0  0.1  19428   832 ?        S    12:1
5   0:00 upstart-udev-bridge --daemon                   
root       186  0.0  0.2  49216  1392 ?        Ss   12:1
5   0:00 /lib/systemd/systemd-udevd --daemon            
syslog     274  0.0  0.2 184188  1444 ?        Ssl  12:1
5   0:00 rsyslogd                                       
root       377  0.0  0.5  61316  3052 ?        Ss   12:1
5   0:00 /usr/sbin/sshd -D                              
root       414  0.0  0.1  12740   844 tty1     Ss+  12:1
5   0:00 /sbin/getty 38400 console                      
root       416  0.0  0.1  12740   852 tty2     Ss+  12:1
5   0:00 /sbin/getty 38400 tty2                         
root       426  0.0  0.1  15492   892 ?        S    12:1
5   0:00 upstart-file-bridge --daemon                   
root       435  0.0  0.2  15768  1104 ?        S    12:1
5   0:00 upstart-socket-bridge --daemon                 
root       468  0.0  0.6  63876  3468 ?        Ss   12:1
8   0:00 sshd: cabox [priv]                             
cabox      470  0.0  0.2  63876  1472 ?        R    12:1
8   0:00 sshd: cabox@pts/0                              
cabox      471  0.0  0.3  18128  2044 pts/0    Ss   12:1
8   0:00 -bash                                          
cabox      503  0.0  0.2  15520  1148 pts/0    R+   12:5
2   0:00 ps aux                                         

* Run `top` and review the results. (Hint: You may need to use `ctrl-c` to get out of this app.) *How do you interpret what you see here?*
This command seems to be giving a summary of all the tasks being completed and details of this work session in real time. It's interesting to see this command tracking the activity and time instantaniously.
top - 13:13:24 up 57 min,  1 user,  load average: 0.00, 
Tasks:  15 total,   1 running,  14 sleeping,   0 stopped
%Cpu(s):  0.0 us,  0.0 sy,  0.0 ni,100.0 id,  0.0 wa,  0
KiB Mem:    524288 total,    21528 used,   502760 free, 
KiB Swap:   524288 total,        0 used,   524288 free. 
                                                        
  PID USER      PR  NI    VIRT    RES    SHR S  %CPU    
    1 root      20   0   33208   2544   1436 S   0.0    
    2 root      20   0       0      0      0 S   0.0    
    3 root      20   0       0      0      0 S   0.0    
  148 root      20   0   19428    832    596 S   0.0    
  186 root      20   0   49216   1392    944 S   0.0    
  274 syslog    20   0  184188   1444    940 S   0.0    
  377 root      20   0   61316   3052   2372 S   0.0    
  414 root      20   0   12740    844    692 S   0.0    
  416 root      20   0   12740    852    700 S   0.0    
  426 root      20   0   15492    892    396 S   0.0    
  435 root      20   0   15768   1104    416 S   0.0    
  468 root      20   0   63876   3468   2716 S   0.0    
  470 cabox     20   0   63876   1472    720 S   0.0    
  471 cabox     20   0   18128   2044   1552 S   0.0    
  504 cabox     20   0   19828   1444   1068 R   0.0    

### Finding and Viewing Files

* Make sure you are in the `challenge_files` directory. Use the `*` wildcard to find all the files that have the word "credit" in the filename. *How many files did you find?*
Moved to challenge_files directory:
cabox@box-codeanywhere:~/workspace$ cd challenge_files  
cabox@box-codeanywhere:~/workspace/challenge_files$ pwd 
/home/cabox/workspace/challenge_files  
Found files with "credit" string:
cabox@box-codeanywhere:~/workspace/challenge_files$ ls credit*                  
credit_cards.txt  credit_cards2.txt                             


* Use the `more` command to view one of the `credit_cards` files you just discovered. (Hint: Type `q` to quit viewing the file. Press the `spacebar` to page down. Use your keyboard arrows to move up/down.) *What is the date in the file you have viewed?*
More command and date: 
Last updated: 01-15-2015                                                        
                                                                                
38419076308558                                                                  
5196941482180427                                                                
6011648902145507                                                                
6011541522810495                                                                
2100438118121208                                                                
340330340261288                                                                 
201489234446831                                                                 
4486721091429528                                                                
214921348106690                                                                 
2100590354720042                                                                
4539858868193585                                                                
2100183923553803                                                                
4532777298371                                                                   
346539747941995                                                                 
2100687370647553                                                                
869913584571073                                                                 
347621194459918                                                                 
4532736972558173                                                                
1800681788742606                                                                
4024007195437                                                                   
374000604532174                                                                 
869950509948366                                                                 
375397178069750                                                                 
4283634711938841                                                                
869959826071596                                                                 
6011480509444137                                                                
4916906561213771                                                                
30352350795307                                                                  
343095106548585                                                                 
311284586352522                                                                 
5422475408970062                                                                
2100462008739531                                                                
4716507869121278                                                                
378861005007611                                                                 
6011525210032934                                                                
6011150846314711                                                                
6011436738361518                                                                
5249270105996531                                                                
214979058870483                                                                 
4916875596958868                                                                
4556066335068640                                                                
4024007164037                                                                   
201411505671046                                                                 
--More--(4%) 
 
* Use the `find` command to search for files more effectively. Search the sub-directories under `challenge_files` to find the location of the file named `modi_laboriosam.txt`. *Where is that file located?*
found in the tmp subdirectory:
_files$ find . -name "modi_laboriosam.txt" -print                                       
./tmp/modi_laboriosam.txt 

* Use the `grep` command to search for text within a file. Use `grep` on all the `.user` files in `challenge_files` to find which files contain "WA" (the abbreviation for Washington state). *How many files did you find?*
found 2 files:
_files$ grep -l 'WA' *.user                 
Britt-Erdman.user                           
Lissie-Strosin.user      

* Use the `-r` option of `grep` to *recursively* find the text "Waldo" hidden in a file somewhere under the `challenge_files` directory. *Paste the result showing the file and line where the word "Waldo" shows up.*
serial-numbers/eaque_molestiae.txt:Ut est ma
iores quia autem. Nisi modi Waldo sed corpor
is sit explicabo ut est. Et est placeat ea s
unt sunt consectetur sunt incidunt. Explicab
o vel esse blanditiis dolorem culpa non quia
.                                           

### Pipes and Connecting Commands

* Sometimes it's useful to output the results of a command to a text file for further analysis, reference, or processing. Try running `ls > files.txt`. Notice that the file `files.txt` was created. View that file using `more`. *What do you see in the `files.txt` file?*
01                                          
2015_special_stuff.demo                     
Afton-Jast.user                             
Aimee-Maggio.user                           
Alfonso-Gottlieb.user                       
Allen-Kemmer.user                           
Almina-Cormier.user                         
Alta-Lemke.user                             
Amina-McGlynn.user                          
Anabel-Hammes.user                          
Ancel-Conn.user                             
Anjali-Halvorson.user                       
Ardath-Kuvalis.user                         
Avah-Dickinson.user                         
Ayaan-Stiedemann.user                       
Aylin-Grant.user                            
Bedford-Sipes.user                          
Benita-King.user                            
Benito-Stoltenberg.user                     
Beverlee-Moen.user                          
Brad-Thiel.user                             
Brayan-Douglas.user                         
Bria-Satterfield.user                       
Bridgette-Reichel.user                      
Britt-Erdman.user                           
Britta-Hammes.user                          
Bryant-Kuhic.user                           
Bryton-Aufderhar.user                       
Caitlin-Grady.user                          
Carroll-Hartmann.user                       
Claudie-McClure.user                        
Clemente-Haley.user                         
Cleo-VonRueden.user                         
Codie-Romaguera.user                        
Cooper-Reynolds.user                        
Corrie-Bogisich.user                        
Dannielle-Green.user                        
Deedee-Jacobson.user                        
Desiree-Marks.user                          
Deven-Rutherford.user                       
Doyle-Jones.user                            
Dustyn-O'Connell.user                       
Elza-Mraz.user                              
Emory-Crona.user                            
Erin-Walker.user    

* Notice that if you run `ls -alh` in the `challenge_files` directory, the files scroll by very quickly. Sometimes it would be better to get the results in a paginated format. Try running `ls -alh | more`. *Describe what you see when you run `ls -alh | more`.*
ls -alh v.s. ls -alh | more:  After running the more command the results displayed simmilarly but required you to press spacebar to view more of the results. 
-rw-rw-r-- 1 cabox cabox   91 Jan 16 18:38 Kirstin-Hoppe.user            
-rw-rw-r-- 1 cabox cabox   93 Jan 16 18:38 Kwame-Schmitt.user            
-rw-rw-r-- 1 cabox cabox   78 Jan 16 18:38 Ladonna-Lueilwitz.user        
-rw-rw-r-- 1 cabox cabox   64 Jan 16 18:38 Lala-Will.user                
-rw-rw-r-- 1 cabox cabox   71 Jan 16 18:38 Leia-Hudson.user              
-rw-rw-r-- 1 cabox cabox   76 Jan 16 18:38 Leia-Ziemann.user             
-rw-rw-r-- 1 cabox cabox   87 Jan 16 18:38 Lillard-Purdy.user            
-rw-rw-r-- 1 cabox cabox   67 Jan 16 18:38 Lilly-Kohler.user             
-rw-rw-r-- 1 cabox cabox   70 Jan 16 18:38 Lissie-Strosin.user           
-rw-rw-r-- 1 cabox cabox   73 Jan 16 18:38 Mannie-Ritchie.user           
-rw-rw-r-- 1 cabox cabox  104 Jan 16 18:38 Masako-Lind.user              
-rw-rw-r-- 1 cabox cabox   89 Jan 16 18:38 Melisa-Yundt.user             
-rw-rw-r-- 1 cabox cabox   90 Jan 16 18:38 Michelina-Kuphal.user         
-rw-rw-r-- 1 cabox cabox   93 Jan 16 18:38 Minnie-Jacobi.user            
-rw-rw-r-- 1 cabox cabox   80 Jan 16 18:38 Murdock-Leffler.user          
-rw-rw-r-- 1 cabox cabox   77 Jan 16 18:38 Mychal-Corkery.user           
-rw-rw-r-- 1 cabox cabox   74 Jan 16 18:38 Nakita-Nader.user             
-rw-rw-r-- 1 cabox cabox   68 Jan 16 18:38 Nayely-Dare.user              
-rw-rw-r-- 1 cabox cabox   76 Jan 16 18:38 Nicholas-Strosin.user         
-rw-rw-r-- 1 cabox cabox   88 Jan 16 18:38 Niles-Runte.user              
-rw-rw-r-- 1 cabox cabox   81 Jan 16 18:38 Nina-Sporer.user              
-rw-rw-r-- 1 cabox cabox   70 Jan 16 18:38 Noreta-Steuber.user           
-rw-rw-r-- 1 cabox cabox   79 Jan 16 18:38 Ovid-Bogan.user               
-rw-rw-r-- 1 cabox cabox   78 Jan 16 18:38 Randell-Sauer.user            
-rw-rw-r-- 1 cabox cabox   78 Jan 16 18:38 Remy-Renner.user              
-rw-rw-r-- 1 cabox cabox  103 Jan 16 18:38 Ronna-Hermann.user            
-rw-rw-r-- 1 cabox cabox  100 Jan 16 18:38 Rosalind-Wisozk.user          
-rw-rw-r-- 1 cabox cabox  102 Jan 16 18:38 Rosena-Simonis.user           
-rw-rw-r-- 1 cabox cabox   96 Jan 16 18:38 Sandie-Balistreri.user        
-rw-rw-r-- 1 cabox cabox   93 Jan 16 18:38 Sharen-Hansen.user            
-rw-rw-r-- 1 cabox cabox   97 Jan 16 18:38 Sherrill-Russel.user          
-rw-rw-r-- 1 cabox cabox   84 Jan 16 18:38 Sherwin-Kovacek.user          
-rw-rw-r-- 1 cabox cabox   96 Jan 16 18:38 Sherwood-Rath.user            
-rw-rw-r-- 1 cabox cabox   77 Jan 16 18:38 Shyheim-Murazik.user          
-rw-rw-r-- 1 cabox cabox   96 Jan 16 18:38 Siobhan-Kirlin.user           
-rw-rw-r-- 1 cabox cabox   75 Jan 16 18:38 Tomas-Kutch.user              
-rw-rw-r-- 1 cabox cabox    0 Jan 16 18:38 cloaked-wookie.demo           
-rw-rw-r-- 1 cabox cabox  16K Jan 16 18:38 credit_cards.txt              
-rw-rw-r-- 1 cabox cabox  16K Jan 16 18:38 credit_cards2.txt             
-rw-r--r-- 1 cabox cabox 2.1K Jan 17 20:32 files.txt                     
-rw-rw-r-- 1 cabox cabox    0 Jan 16 18:38 scooter-double-mamba.demo     
drwxrwxr-x 2 cabox cabox 4.0K Jan 16 18:38 serial-numbers                
drwxrwxr-x 2 cabox cabox 4.0K Jan 16 18:38 test2                         
drwxrwxr-x 2 cabox cabox 4.0K Jan 16 18:38 tmp                           
drwxrwxr-x 2 cabox cabox 4.0K Jan 16 18:38 wow 
                       

* Earlier, when you viewed the list of active processes on your devbox using `ps aux`, the list was probably really long. You can make this list more manageable by using the pipe (`|`) to filter the results of `ps` using `grep`. Run `ps aux | grep <your_username>` to see what processes are running for your specific user. *Paste the list of processes that reference your username here:*
cabox@box-codeanywhere:~/workspace/challenge_files$ ps aux | grep cabox  
root       449  0.0  0.6  63876  3468 ?        Ss   19:11   0:00 sshd: ca
box [priv]                                                               
cabox      452  0.0  0.2  63876  1472 ?        S    19:11   0:00 sshd: ca
box@pts/0                                                                
cabox      454  0.0  0.3  18140  2044 pts/0    Ss   19:11   0:00 -bash   
root       507  0.0  0.6  63876  3468 ?        Ss   20:15   0:00 sshd: ca
box [priv]                                                               
cabox      509  0.0  0.2  63876  1472 ?        S    20:15   0:00 sshd: ca
box@pts/1                                                                
cabox      510  0.0  0.3  18124  2008 pts/1    Ss+  20:15   0:00 -bash   
cabox      520  0.0  0.1   8816   752 pts/0    S+   20:16   0:00 grep --c
olor=auto WA                                                             
root       555  0.0  0.6  63876  3468 ?        Ss   20:23   0:00 sshd: ca
box [priv]                                                               
cabox      557  0.0  0.2  64012  1492 ?        S    20:23   0:00 sshd: ca
box@pts/2                                                                
cabox      558  0.0  0.3  18140  2044 pts/2    Ss   20:23   0:00 -bash   
cabox      590  0.0  0.2  15520  1148 pts/2    R+   21:07   0:00 ps aux  
cabox      591  0.0  0.1   8816   748 pts/2    S+   21:07   0:00 grep --c
olor=auto cabox 
