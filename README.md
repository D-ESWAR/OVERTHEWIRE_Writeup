OVER THE WIRE BANDIT
(write up)
Level 0
This is a pretty simple level. It teaches us to connect to a host using SSH. This is going to teach players the usage of SSH command.
We got the required information from reading the instruction page.
Host: bandit.labs.overthewire.org
Port: 2220
Username: bandit0
Password: bandit0    [Like once you find level exit from current ssh and next level:no and prev passwd to enter to next next ssh ]
We used the above information to login using ssh as shown in the given image.
COMMAND
ssh bandit0@bandit.labs.overthewire.org -p 2220
<img width="602" height="149" alt="image" src="https://github.com/user-attachments/assets/6036e333-86a4-4b38-91f6-28effb1a5c21" />

--------------------------------------------------------------------------------------------------------------------------
Bandit Level 0 → Level 1
Level Goal
The password for the next level is stored in a file called readme located in the home directory. 
Use this password to log into bandit1 using SSH. Whenever you find a password for a level, use SSH (on port 2220) to log into that level and continue the game.
COMMAND
ls -la(list the file and also show hidden file)
cat readme(show the content of file)
Password:ZjLjTmM6FvvyRnrb2rfNWOZOTa6ip5If
----------------------------------------------------------------------------------------------------------------------------
 

Bandit Level 1 → Level 2
Level Goal
The password for the next level is stored in a file called - located in the home directory
 
Ls – to make list file
The file contain ‘–‘ file we using 
Cat  ./-             to  execute 
Password: 263JGJPfgU6LtdEvgfWU1XP5yac29mFx
Bandit Level 2 → Level 3
Level Goal
The password for the next level is stored in a file called --spaces in this filename-- located in the home directory
 
Password : MNk8KNH3Usiio41PRUEoDFPqfxLPlSmx
--------------------------------------------------------------------------------------------------------------


Bandit Level 3 → Level 4
Level Goal
The password for the next level is stored in a hidden file in the inhere directory.
Cd – changing the directries
Ls -a =list show “hidden files”
 
Password: 2WmrDFRmJIq3IPxneAaMGhap0pFhF3NJ
-------------------------------------------------------------------------------------------------------------------------------------- Bandit Level 4 → Level 5
Level Goal
The password for the next level is stored in the only human-readable file in the inhere directory. Tip: if your terminal is messed up, try the “reset” command.
File = to make Wheater the file type content.
File  ./* =all the files in directories  
 
Password: 4oQYVPkxZOOEOO5pTW81FB8j8lxXGUQw

Bandit Level 5 → Level 6
Level Goal
The password for the next level is stored in a file somewhere under the inhere directory and has all of the following properties:
•	human-readable
•	1033 bytes in size
•	not executable
find . =searches in current directories 
-size to make to finding c=bytes
 
Password: HWasnPhtq9AVKe0dmk45nxy20cvUa6EG
Bandit Level 6 → Level 7
Level Goal
The password for the next level is stored somewhere on the server and has all of the following properties:
•	owned by user bandit7
•	owned by group bandit6
•	33 bytes in size
find / -user bandit7 -group bandit6 -size 33c

/var/lib/dpkg/info/bandit7.password
Find some like  this when enter the command and others show the permission denied
So fixing the given condition like user bandit7 and group bandit6 also size 33c
Using this combine we get fetch details from inside the sensitive information behind 
 
bandit6@bandit:~$    cat /var/lib/dpkg/info/bandit7.password
Password: morbNTDkSW6jIlUc0ymOdMaLnOlFVAaj

Bandit Level 7 → Level 8
Level Goal
The password for the next level is stored in the file data.txt next to the word millionth
Using ‘grep’ specific things to find in the file
ls
cat data.txt | grep millionth
its show near values of the given word
 
Password: dfwvzFQi4mU0wfNbF0e9RoWskMLg7eEc

Bandit Level 8 → Level 9
Level Goal
The password for the next level is stored in the file data.txt and is the only line of text that occurs only once
WAY
We are informed that the password for the next level is stored inside a file named data.txt. It is hinted that the password is the only line of text that occurs only once. Here we are going to use sort command to sort the text inside the data.txt file. But still, the file contains a lot of repeating statements so we will use the uniq command to print the not repeating statement
 
Sort = sorting the same thing in a line by line 
Uniq -q = finding uniq thing in the sort to make work easy 
| = and once the statement true and go into other step ,otherwise not
Password: 4CKMh1JI91bUIZZPXDqGanal4xvAg0JM
--------------------------------------------------------------------------------------------------------------------------------------
Bandit Level 9 → Level 10
Level Goal
The password for the next level is stored in the file data.txt in one of the few human-readable strings, preceded by several ‘=’ characters.
Using the same concept her ‘grep’ after =
New things that we unreadable text 
Using “Strings” we make readable and specific lines after the “=”
 
Password: FGUW5ilLVJrxX9kMYMmlN4MgbpfMiqey
--------------------------------------------------------------------------------------------------------------------------------------
Bandit Level 10 → Level 11
Level Goal
The password for the next level is stored in the file data.txt, which contains base64 encoded data
 
Showing the content in data.txt of base 64
How could know is base 64 they {hint = end with “==”}
Base64 -d to decrypt the following text
Password: dtR173fZKb0RRsDFSGsg2RWnpNVj3qRr
--------------------------------------------------------------------------------------------------------------------------------------
Bandit Level 11 → Level 12
Level Goal
The password for the next level is stored in the file data.txt, where all lowercase (a-z) and uppercase (A-Z) letters have been rotated by 13 positions
Cat shows the letters are inter changing of file
 
We are informed that the password for the next level is stored inside a file named data.txt. So, to find it we use the ls command. Now, we are hinted that the file containing the password has changed the format of letters in such a way that all the lowercase and uppercase letters have been rotated by 13 positions. If we can remember right that exactly what happens in ROT13 encryption. Now, to convert the text, we can use the ‘tr’ command. This command translates characters depending on the parameters provided. We used n-z and a-m because tr won’t continue to translate after the Z.
Password: 7x16WNeHIi5YkIhWsfFIqoognUTyj9Q4
--------------------------------------------------------------------------------------------------------------------------------------
Bandit Level 12 → Level 13
Level Goal
The password for the next level is stored in the file data.txt, which is a hexdump of a file that has been repeatedly compressed. For this level it may be useful to create a directory under /tmp in which you can work. Use mkdir with a hard to guess directory name. Or better, use the command “mktemp -d”. Then copy the datafile using cp, and rename it using mv (read the manpages!)
Gunzip,bunzip and xxd commands are going to used 
 cd /
 Cd tmp/any directories make 

 
mkdir /tmp/pavan
cp data.txt /tmp/pavan
cd /tmp/pavan
ls
file data.txt
xxd -r data.txt data1
file data1
mv data1 data2.gz 
gzip -d data2.gz
xxd -r	                       Convert hex → binary
gzip -d	                      Decompress gzip
bzip2 -d	                    Decompress bzip2
tar -xvf	                     Extract tar
cat	                             Read final password

Password: FO5dwFsc0cbaIiH0h8J2eUks2vdTDwAn
--------------------------------------------------------------------------------------------------------------------------------------
Bandit Level 13 → Level 14
Level Goal
The password for the next level is stored in /etc/bandit_pass/bandit14 and can only be read by user bandit14. For this level, you don’t get the next password, but you get a private SSH key that can be used to log into the next level. Look at the commands that logged you into previous bandit levels, and find out how to use the key for this level.
 
We are informed that we are not going to get a password for the next level. Instead, we are given an ssh private key. So, to get to the next level we are going to use that ssh private key. Firstly, let’s find that private key using the ls command. We found the private key. Now we will use it to get an SSH connection as bandit14.
Step1:creat a file paste the key to your file
Step2:chmod 600 to file
Step3: ssh -i sshkey.private -p 2220 bandit14@bandit.labs.overthewire.org
Once we get login to bandit 14
From bandit we get 13 passwd
Password: MU4VWeTyJk8ROof1qqmcBPaLh7lDCPvS
--------------------------------------------------------------------------------------------------------------------------------------
Bandit Level 14 → Level 15
Level Goal
The password for the next level can be retrieved by submitting the password of the current level to port 30000 on localhost.
 
Once get we don’t know the password for before getting by
Cat /etc/bandit_pass/bandit14
To get password
Task using password submit to port 30000
cat /etc/bandit_pass/bandit14 | nc localhost 30000
nc -netcat 
or telnet
password: 8xCjnmgoKbGLhHFAZlGE5Tmu4M2tKJQo
--------------------------------------------------------------------------------------------------------------------------------------
Bandit Level 15 → Level 16
Level Goal
The password for the next level can be retrieved by submitting the password of the current level to port 30001 on localhost using SSL/TLS encryption.
Helpful note: Getting “DONE”, “RENEGOTIATING” or “KEYUPDATE”? Read the “CONNECTED COMMANDS” section in the manpage.
 
Using getting know the password of 14
 Port 30001 uses SSL encryption
Normal tools like nc won’t work
openssl s_client establishes a secure connection
-ign_eof keeps the connection open after input
 
Enter the previous passwd if correct then it procced
Password : kSkvUpMQ7lBYyCM4GBPvCvT1BfWRy0Dx
--------------------------------------------------------------------------------------------------------------------------------------
Bandit Level 16 → Level 17
Level Goal
The credentials for the next level can be retrieved by submitting the password of the current level to a port on localhost in the range 31000 to 32000. First find out which of these ports have a server listening on them. Then find out which of those speak SSL/TLS and which don’t. There is only 1 server that will give the next credentials, the others will simply send back to you whatever you send to it.
Helpful note: Getting “DONE”, “RENEGOTIATING” or “KEYUPDATE”? Read the “CONNECTED COMMANDS” section in the manpage.
Nmap
Chmod
Using nmap scan which port have valid or unknow 
Trying to give the password if give key its right otherwise not the right port
 
Openssl
echo "kSkvUpMQ7lBYyCM4GBPvCvT1BfWRy0Dx" | openssl s_client -connect localhost:31790 -ign_eof
 
Same procedure follow before 13 to 14 stage 
Save a key and chmod change 
Sshkey17.private chmod 600 
ssh -i sshkey17.private -p 2220 bandit17@bandit.labs.overthewire.org
cat /etc/bandit_pass/bandit16
Password: EReVavePLFHtFlFsjn3hyzMlvSuSAcRD
--------------------------------------------------------------------------------------------------------------------------------------
Bandit Level 17 → Level 18
Level Goal
There are 2 files in the homedirectory: passwords.old and passwords.new. The password for the next level is in passwords.new and is the only line that has been changed between passwords.old and passwords.new
NOTE: if you have solved this level and see ‘Byebye!’ when trying to log into bandit18, this is related to the next level, bandit19
 
Diff to compare finding two different line
 
Password:x2gLTTjFwMOhQ8oWNbMN362QKxfRqGlO
--------------------------------------------------------------------------------------------------------------------------------------
Bandit Level 18 → Level 19
Level Goal
The password for the next level is stored in a file readme in the homedirectory. Unfortunately, someone has modified .bashrc to log you out when you log in with SSH.
ssh bandit18@bandit.labs.overthewire.org. -p 2220 ask paswd 
logout immediately 
ssh bandit18@bandit.labs.overthewire.org. -p 2220 ls
ssh bandit18@bandit.labs.overthewire.org. -p 2220 cat readme
enter the password
of thr previous bandit 
it show for another level passwd
 
Password: cGWpMaKXVwDUNgPAVJbWYuGHVn9zl3j8
--------------------------------------------------------------------------------------------------------------------------------------
Bandit Level 19 → Level 20
Level Goal
To gain access to the next level, you should use the setuid binary in the homedirectory. Execute it without arguments to find out how to use it. The password for this level can be found in the usual place (/etc/bandit_pass), after you have used the setuid binary.
Think if user is inside 19 we can acces the bandit20 also 
We got it
 
Password: 0qXahG8ZjOVMN9Ghs7iOWsCfZyXOUbYO
--------------------------------------------------------------------------------------------------------------------------------------
Bandit Level 20 → Level 21
Level Goal
There is a setuid binary in the homedirectory that does the following: it makes a connection to localhost on the port you specify as a commandline argument. It then reads a line of text from the connection and compares it to the password in the previous level (bandit20). If the password is correct, it will transmit the password for the next level (bandit21).
 
On open terminal of two one of them run/sconnect 20000
Another one nc -lvnp 20000
 
After the listening port enter password level 20 paste you get next passwd
Password : EeoULMCra2q0dSkYj561DX7s1CpBuOBt
--------------------------------------------------------------------------------------------------------------------------------------
Bandit Level 21 → Level 22
Level Goal
A program is running automatically at regular intervals from cron, the time-based job scheduler. Look in /etc/cron.d/ for the configuration and see what command is being executed.
They said go and see cd /etc/cron.d
Ls to make listing next level password file
Using cat to they its in another path
Following the path open the file agin go to another
Finallu we get it
 
Password: tRae0UfB9v0UzbCdn9cY0gQnds9GF58Q
--------------------------------------------------------------------------------------------------------------------------------------

Bandit Level 22 → Level 23
Level Goal
A program is running automatically at regular intervals from cron, the time-based job scheduler. Look in /etc/cron.d/ for the configuration and see what command is being executed.
NOTE: Looking at shell scripts written by other people is a very useful skill. The script for this level is intentionally made easy to read. If you are having problems understanding what it does, try executing it to see the debug information it prints
 
Password: 0Zf11ioIjMVN551jX3CmStKLYqjk54Ga
--------------------------------------------------------------------------------------------------------------------------------------
Bandit Level 23 → Level 24
Level Goal
A program is running automatically at regular intervals from cron, the time-based job scheduler. Look in /etc/cron.d/ for the configuration and see what command is being executed.
NOTE: This level requires you to create your own first shell-script. This is a very big step and you should be proud of yourself when you beat this level!
NOTE 2: Keep in mind that your shell script is removed once executed, so you may want to keep a copy around…
•	Cron jobs are stored here.
We must check what runs automatically.( cd /etc/cron.d)
•	To understand what the cron actually does.( cat /usr/bin/cronjob_bandit24.sh)
•	cd /var/spool/bandit24/foo("Run every file placed in this folder")
•	mkdir /tmp/level24 (We need a place where:
•	we have permission we can save the password
•	chmod 777 /tmp/level24(Cron runs as bandit24, not bandit23
So bandit24 must also be able to write here)
•	We create our script here safely (cd /tmp/level24)
#!/bin/bash	                                              run using bash
   cat /etc/bandit_pass/bandit24	          read password
	      >                                                               redirect output
   /tmp/level24/pass.txt	                           save where we can read

CODE: cat << 'EOF' > steal.sh
#!/bin/bash
cat /etc/bandit_pass/bandit24 > /tmp/level24/pass.txt
EOF
chmod +x steal.sh
cp steal.sh /var/spool/bandit24/foo/   =executed automatically 
sleep 75 make give time for it
then you can see pass.txt
 
Password: gb8KRRCsshuZXI0tUuR6ypOFjiZbf3G8
-------------------------------------------------------------------------------------------------------------------------------------
Bandit Level 24 → Level 25
Level Goal
A daemon is listening on port 30002 and will give you the password for bandit25 if given the password for bandit24 and a secret numeric 4-digit pincode. There is no way to retrieve the pincode except by going through all of the 10000 combinations, called brute-forcing.
You do not need to create new connections each time
Brute forcing given port 
Bru.sh
#!/bin/bash
passwd="UoMYTrfrBFHyQXmg6gzctqAwOmw1IohZ"
for i in {0000..9999}
do
 echo "$passwd $i"
done > output.txt
scan all the possible store in output.txt
finally make result find uniq -u to get passwd
 
Password: iCi86ttT4KSNe1armKiwbQNmB3YJP3q4
--------------------------------------------------------------------------------------------------------------------------------------
Bandit Level 25 → Level 26
Level Goal
Logging in to bandit26 from bandit25 should be fairly easy… The shell for user bandit26 is not /bin/bash, but something else. Find out what it is, how it works and how to break out of it.
NOTE: if you’re a Windows user and typically use Powershell to ssh into bandit: Powershell is known to cause issues with the intended solution to this level. You should use command prompt instead.
Open terminal ls make display the file bandit26.key 
Make copy of file 
Enter to cd /tmp key ,chmod 600 make not execute=its faile
Try in your our comp terminal
 
Same process make copy of key change permissions
Login ssh,with minium 5 rows included 
Press v
 
:etc/passwd make shows the information
 
Password: s0773xxkk0MXfdqOfPRVr9L3jJBUOgCZ
--------------------------------------------------------------------------------------------------------------------------------------
Bandit Level 26 → Level 27
Level Goal
Good job getting a shell! Now hurry and grab the password for bandit27!
Same process before done 
Shrink the terminal to load the process
Press v to make , :set shell=/bin/bash :!sh 
Eleminatel the shell , ./bandit27-do cat /etc/bandit_pass/bandit27
 
Password: upsNCc7vzaRDx6oZC6GiR6ERwe1MowGB
--------------------------------------------------------------------------------------------------------------------------------------
Bandit Level 27 → Level 28
Level Goal
There is a git repository at ssh://bandit27-git@bandit.labs.overthewire.org/home/bandit27-git/repo via the port 2220. The password for the user bandit27-git is the same as for the user bandit27.
From your local machine (not the OverTheWire machine!), clone the repository and find the password for the next level. This needs git installed locally on your machine.
In your terminal paste GitHub clone
Cd repo,ls cat make get the password
 
Password: Yz9IpL0sBcCeuG7m9uQFt8ZNpS4HZRcN
--------------------------------------------------------------------------------------------------------------------------------------
Bandit Level 28 → Level 29
Level Goal  There is a git repository at ssh://bandit28-git@bandit.labs.overthewire.org/home/bandit28-git/repo via the port 2220. The password for the user bandit28-git is the same as for the user bandit28.
From your local machine (not the OverTheWire machine!), clone the repository and find the password for the next level. This needs git installed locally on your machine.
In our terminal make git clone,open file repo and readme 
 
They removed the password finding by Git log and Git show changes
 
Password: 4pT1t5DENaYuqnqvadYs1oE4QLCdjmJ7
---------------------------------------------------------------------------------------------------------------------------
Bandit Level 29 → Level 30
Level Goal
There is a git repository at ssh://bandit29-git@bandit.labs.overthewire.org/home/bandit29-git/repo via the port 2220. The password for the user bandit29-git is the same as for the user bandit29.From your local machine (not the OverTheWire machine!), clone the repository and find the password for the next level. This needs git installed locally on your machine.
Here is error Branches
 
Password: qp30ex3VLz5MDG1n91YowTv4Q8l7CDZL
---------------------------------------------------------------------------------------------------------------------------
Bandit Level 30 → Level 31
Level Goal
There is a git repository at ssh://bandit30-git@bandit.labs.overthewire.org/home/bandit30-git/repo via the port 2220. The password for the user bandit30-git is the same as for the user bandit30.
From your local machine (not the OverTheWire machine!), clone the repository and find the password for the next level. This needs git installed locally on your machine.
Here tags using
 
Password; fb5S2xb7bRyFmAvQYQGEqsbhVyJqhnDy
---------------------------------------------------------------------------------------------------------------------------

Bandit Level 31 → Level 32
Level Goal
There is a git repository at ssh://bandit31-git@bandit.labs.overthewire.org/home/bandit31-git/repo via the port 2220. The password for the user bandit31-git is the same as for the user bandit31.
From your local machine (not the OverTheWire machine!), clone the repository and find the password for the next level. This needs git installed locally on your machine.
 
Password: 3O9RfhqyAlVBEZpVb6LYStshZoqoSx5K
---------------------------------------------------------------------------------------------------------------------------
Bandit Level 32 → Level 33
Level Goal
After all this git stuff, it’s time for another escape. Good luck!
 
Password: tQdtbs5D5i2vJwkO8mEyYEyTL8izoeJ0
--------------------------------------------------------------------------------------------------------------------------------------
Bandit Level 33 → Level 34
At this moment, level 34 does not exist yet.

