# BANDIT LABS
## Important Points 
    1.ctrl+1 = " commit "
    1.1 Ctrl+shift+i = " inspect "
    1.2 Ctrl+shift++ = " zoom in "
    1.3 Ctrl+shift+- = " zoom out "
    1.4 Ctrl+shift+0 = " reset zoom "
    1.5 ctrl+c = " exit "
    1.6 ctrl+X = " save and exit "
2.ctrl+k then leave them thenpress v 
 you can able to see  the updated git that means your not goto the git otherthan you will able see updated git by your own correctons on Vs code 
3.In a system you have file Like in a Notepad there is a resume file then you can able to see the resume file
 4.It has a properties. In a File properties you can able to see that 3 types  modules

        1.System
        2.You (your mail)
        3.Administrator
 5.These 3 have right on a file Authorization , Like  The Root is a Administrator in Linux setup
## Terminal
1.First you can start the terminal you will see the starting stage of terminal the you need to go that terminal you can access that terminal by " sudo su " 
2.After that terninal can ask you the password 
3. Password : " kali "
4. then you enter the password you will not able to see that password but it can automatically access
 5. It will navigate Home that means Root, it will shows " root@kali " 
 6. It will shows in red color. It is the simple checking that  you are in root or not and below that root you will see " #  " in red color that means Finally you can start the Terminal
## Level 0
What you Need to do :
+ Username : bandit0   
+  Password : bandit0                        
+ Domain : ssh bandit0@bandit.labs.overthewire.org -p 2220   
+ Port Num : 2220
### Commands
+ ls = list files  
+ cd = change directory  
+ cat = read file
### Explination 
 list files with:

    ls
You’ll see a file called readme.
Read it:

    cat readme
That file gives you the password for Level 1.
To log out later:
exit
##  Level 1
+ Username : bandit1   
+  Password :                        
+ Domain : ssh bandit1@bandit.labs.overthewire.org -p 2220   
+ Port Num : 2220
### Commands
+ ls = list files  
+ cd = change directory       
+ cat = read file
### Explination
Run:

     ls
Output:

     -
That’s the file containing the password.
⚠️ Common mistake (DO NOT do this)

       cat -
❌ This makes cat wait for keyboard input because - means 

       stdin.
Step 3: Correct way to read the file
You have two correct options.
✅ Option 1 (recommended): Use ./

        cat ./-
Step 4: Get the password
##  Level 2
+ Username : bandit2   
+  Password :                       
+ Domain :   ssh bandit2@bandit.labs.overthewire.org -p 2220 
+ Port Num : 2220
### commands 
-  ls = list files
 - ls  -i =
 - find = Find the files and directories Based on    Name, size, Modification time
### Explination
1️⃣ List the files

    ls
You should see something like:

     spaces in this filename
###### ✅ Step 1: List files exactly
Run this first and copy what you see character-for-character:

   ls -l
You will likely see something like:
-rw-r----- 1 bandit2 bandit2 33 spaces in this filename
#### 🚨 Common causes of your error
run:

     pwd
You should see:
/home/bandit2
If not:
cd ~
This bypasses the filename entirely.

     ls -i
You’ll see something like:1234567 spaces in this file name
Now run:

    find . -inum 1234567 -exec cat {} \;
(replace 1234567 with the actual number)
## Level-3
+ Username : bandit3   
+  Password :                 
+ Domain :   ssh bandit3@bandit.labs.overthewire.org -p 2220
+ Port Num : 2220
### Commands
- ls = list files
- cd = change directory 
- ls -a =
 - find = Find the files and directories Based on    Name, size, Modification time
### Explination
List files in the home directory:

     ls    
You type ls and the output literally says:
      
      inhere
So the file is inside a directory named inhere, not directly in your home folder.

    cd inhere
When your prompt changes to:

     ~/inhere$
➡️ You are now inside the inhere directory

     ls -a
When ls shows:

    Hiding from you
Type exactly this while you are in ~/inhere:

    find . -type f -exec cat {} \;
find . -type f → finds the file no matter how strange its name is
-exec cat {} \; → prints the contents directly
No quotes, no guessing, no typing the filename
## Level-4
+ Username : bandit4   
+  Password :                        
+ Domain :   ssh bandit4@bandit.labs.overthewire.org -p 2220 
+ Port Num : 2220
### Commands
- ls = list files  
+ cd = change directory
- ls or ls -a = list files
-  find = Find the files and directories Based on    Name, size, Modification time
  cat = read file
### Explination

      ls
1️⃣ Go into the inhere directory

        cd inhere
2️⃣ List all files, including hidden ones

          ls -a
Run:

    pwd
You must see:
/home/bandit4/inhere
If you do not, then run:

      cd inhere
Step 2️⃣ Confirm the files really exist

    ls
You must see something like: file00  file01  file02  file03  file04  file05  file06  file07  file08  file09
Why ls -1 helps

      ls -1
You should see something like:
-file00
-file01
-file02
-file03
...
✅ Correct way to read the file

    cat ./-file02
Option 2 (also valid)

     cat -- -file02
-- means: stop reading options after this, so It shows diamond symboles along with charecteres in a password

    cat ./-file02 | od -An -tx1
This shows the password in hex bytes, proving it’s longer than 4 characters.You’ll see output like:61 7f 9a e2 ...
2️⃣ Identify the ONLY valid password file

      file ./* or file ./-*
You must see exactly ONE line like:
./-file07: ASCII text
Example:

     cat ./-file07
## Level-5
+ Username : bandit5   
+  Password :                         
+ Domain :  ssh bandit5@bandit.labs.overthewire.org -p 2220  
+ Port Num : 2220
### Commands
- ls = list files  
+ cd = change directory
- ls or ls -1 = list files
 - find = Find the files and directories Based on    Name, size, Modification time
 - cat = read file
### Explination

     ls
1️⃣ Go into the inhere directory

        cd inhere
2️⃣ List all files, including hidden ones

         ls -a
Step 1️⃣ Check where you are
Run:
   
     pwd
You must see:

/home/bandit4/inhere
If you do not, then run:

     cd inhere
Step 2️⃣ Confirm the files really exist
Now run:

        ls
You must see something like: file00  file01  file02  file03  file04  file05  file06  file07  file08  file09
Why ls -1 helps

         ls -1
This lists one filename per line, making copy-paste and reading easier.You should see something like:
-file00
-file01
-file02
-file03
...
Then use this command it will shows the inner file names.
 
    file ./*
But this time it shows directories.
Because it has num of files in their directories thats why file ./* command cannot find exact one file.

    find . -type f -size 1033c ! -executable
-type f → files only
-size 1033c → exactly 1033 bytes
! -executable → excludes executable files
find → searches recursively under inhere 
Example:

./maybehere07/.file2 Read the file

       cat ./maybehere07/.file2
## Level-6
+ Username : bandit6   
+  Password :                     
+ Domain :  ssh bandit6@bandit.labs.overthewire.org -p 2220 
+ Port Num : 2220
### Commands
- find = Find the files and directories Based on    Name, size, Modification time
 - cat = Display the file contents on terminal
### Explination

     find / -type f -user bandit7 -group bandit6 -size 33c 2>/dev/null
This will return one file, usually:

/var/lib/dpkg/info/bandit7.password
Read it

    cat /var/lib/dpkg/info/bandit7.password
## Level-7
+ Username : bandit7   
+  Password :                     
+ Domain : ssh bandit7@bandit.labs.overthewire.org -p 2220  
+ Port Num : 2220
### Commands
- grep = 
### Explination

          ls
     
     grep millionth data.txt
grep searches through data.txt
It prints the entire line containing the word millionth
## Level-8
+ Username : bandit8   
+  Password :                     
+ Domain : ssh bandit8@bandit.labs.overthewire.org -p 2220  
+ Port Num : 2220
### Commands
- ls = list files 
- sort = 
- uniq =
### Explination
sort data.txt | uniq -u

     sort data.txt
Groups identical lines together (required for uniq to work correctly).

     uniq -u
Prints only lines that occur once.

    sort data.txt | uniq
And finally:

    sort data.txt | uniq -u
## Level-9
+ Username : bandit9   
+  Password :                     
+ Domain : ssh bandit9@bandit.labs.overthewire.org -p 2220  
+ Port Num : 2220
### Commands
- ls = list files 
- strings = 
- grep =
### Explination
Inspect data.txt Use strings to extract human-readable text:

    strings data.txt
Filter for lines with = characters
The password is preceded by several = characters, so pipe the output to grep:

    strings data.txt | grep "==="
strings → extracts readable ASCII text from a binary file
grep "===" → narrows results to lines matching the level hint
The password is intentionally easy to spot once filtered correctly
## Level-10
+ Username : bandit10   
+  Password :                     
+ Domain :  ssh bandit10@bandit.labs.overthewire.org -p 2220 
+ Port Num : 2220
### Commands
- ls = list files 
- cat = Display the file contents on terminal
- base64 =  
### Explination
List files

      ls
You should see:

         data.txt
Decode the Base64 data

           base64 -d data.txt
or equivalently:

      cat data.txt | base64 --decode
## Level-11
+ Username : bandit11   
+  Password :                     
+ Domain :  ssh bandit11@bandit.labs.overthewire.org -p 2220 
+ Port Num : 2220
### Commands
- cat = Display the file contents on terminal
- tr = 
### Explination
The password is in data.txt.
All letters (a–z, A–Z) are rotated by 13 positions (ROT13). Numbers and symbols are unchanged. ROT13 is symmetric: applying it once decodes the text.
Use tr to rotate the characters back:

    cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'
This command:
Reads the file
Translates:
A–Z → N–Z A–M
a–z → n–z a–m  Prints the decoded password to the terminal . ROT13 shifts each letter 13 places:
a ↔ n, b ↔ o, …, m ↔ z Same logic for uppercase letters
Because the alphabet has 26 letters, rotating by 13 twice returns the original text.
## Level-12
+ Username : bandit12
+  Password : TguMNxKo1DSa1tujBLuZJnDUlCcUAPlI                       
+ Domain :  ssh bandit12@bandit.labs.overthewire.org -p 2220 
+ Port Num : 2220
### Commands
- cp = copy
- mv = move
- xxd = 
- -r = 
- ls = list files
- file =
- file * = 
- cat =  read the contents of a file
### Explination
[image](./images/image-12.png)
1️⃣ Use a random temp directory (recommended):

     cd /tmp

     mktemp -d
Example output:

     /tmp/tmp.ABC123xyz
Move into it:

       cd /tmp/tmp.ABC123xyz
2️⃣ Copy the data file into your workspace
   
     cp ~/data.txt .
Rename it so it’s easier to work with:

      mv data.txt data.hex
3️⃣ Convert the hex dump back into a binary file

     xxd -r data.hex > data.bin
Now check what kind of file it is:

      file data.bin
You’ll see something like:

     data.bin: gzip compressed data
Example sequence (your exact order may vary):

       mv data.bin data.gz

         gunzip data.gz

         file data
You might then see:

      data: bzip2 compressed data

      mv data data.bz2

     bunzip2 data.bz2

     file data
Then:

       data: POSIX tar archive

        tar -xf data
2️⃣ Immediately list files
        
        ls
        file *
You may encounter gzip, bzip2, and tar multiple times. Just keep looping until file says something like: ASCII text
4️⃣ Repeatedly, Check file type, Rename with correct extension, Decompress, Repeat
Once you get a text file:like password.txt

        cat data
## Level-13
+ Username : bandit13   
+  Password : FO5dwFsc0cbaIiH0h8J2eUks2vdTDwAn 
+  Domain : ssh bandit13@bandit.labs.overthewire.org -p 2220     [or]
+ Domain 1: scp -P 2220 bandit13@bandit.labs.overthewire.org:/home/bandit13/sshkey.private .
below is the image of level-13
[image](./images/image-13.png)
### Commands
- ls = list files
- cat = Display the file contents on terminal
- nano =
- chmod =
### Explination
You do not get a password for bandit14.
Instead, you are given a private SSH key.
You must use that key to log in as bandit14.
1. Log in to Bandit Level 13 (as usual)

       ssh bandit13@bandit.labs.overthewire.org -p 2220
Once logged in, list the files:

        ls
You should see a file named:

     sshkey.private
  it will shows the key

      cat sshkey.private
copy the entire key and Paste the key into a text editor means nano tool

     nano key 
then save it and rename it to key, the key rename name is also a key
3. Fix the key’s permissions (important!)
SSH will refuse to use a private key if it’s too open.

      chmod 600 key
4. Use the private key to log in as bandit14, From inside bandit13, Example run:

    ssh -i key bandit14@bandit.labs.overthewire.org -p 2220
Explanation:
-i sshkey.private → tells SSH which private key to use
bandit14@localhost → you’re logging into the same machine, just as a different user
#### 2nd Method
[image](./images/image-13-1.png)
✅ DOWNLOAD SSH KEY FROM BANDIT TO KALI (FINAL)
📌 Run this ON YOUR KALI TERMINAL, not on Bandit:

    scp -P 2220 bandit13@bandit.labs.overthewire.org:/home/bandit13/sshkey.private .
When asked, enter the bandit13 password. The file will appear in your current Kali directory.
✅ FIX PERMISSIONS ON KALI (IMPORTANT)

    chmod 600 sshkey.private
✅ LOGIN TO BANDIT14 USING THE KEY

    ssh -i sshkey.private bandit14@bandit.labs.overthewire.org -p 2220
 ## Level-14
+ Username : bandit14
+  Password : 
+ Domain : ssh -i sshkey.private bandit14@bandit.labs.overthewire.org -p 2220
+ Port Num : 2220
### Commands
- cat = Display the file contents on terminal
- nc =
### Explination
[image](./images/image-14-1.png)
[image](./images/image-14.png)
Login: 

    ssh -i sshkey.private bandit14@bandit.labs.overthewire.org -p 2220
2️⃣ Get the current password

     cat /etc/bandit_pass/bandit14

3️⃣ Send it to port 30000 using nc

    cat /etc/bandit_pass/bandit14 | nc localhost 30000
## Level-15
+ Username : bandit15
+  Password :
+ Domain : ssh bandit15@bandit.labs.overthewire.org -p 2220
+ Port Num : 2220
### Commands
- openssl = encrypt and decrypt
### Explination
[image](./images/image-15.png)
Step 1: Log into Bandit Level 15

    ssh bandit15@bandit.labs.overthewire.org -p 2220
Enter Password:    
Step 2: Connect securely to port 30001

    openssl s_client -connect localhost:30001
You should see a lot of SSL-related output — this is normal.
Step 3: Send the current password to port 30001. Paste the Bandit 15 password and press Enter.
## Level-16
+ Username : bandit16
+  Password :
+ Domain : ssh bandit16@bandit.labs.overthewire.org -p 2220
+ Port Num : 2220
### Commands
- cat = Display the file contents on terminal
- nmap =
- openssl =
- -quit =
- nano =
- chmod = change permission

### Explination
[image](./images/image-16.png)
✅ Step 0: Get the current password

     cat /etc/bandit_pass/bandit16 
🔍 Step 1: Scan for open ports (31000–32000)
Use nmap to find listening services:
[image](./images/image-16-1.png)
🔐 Step 2: Identify which port uses SSL/TLS
Example:

    openssl s_client -connect localhost:31046
✅ Correct SSL service:
You see certificate details
Connection completes successfully
❌ Not SSL:
Errors like: wrong version number or handshake failure
Repeat this for each open port until one clearly supports SSL.
You wiil see the Difference between them
   But i found two ports are same How can i find that Correct one
✅ Correct:
If you find this one Protocol  : TLSv1.3
At the TLSv1.3 protocol, is also same in two ports. How can i find that Correct one
🔐Run exactly this:

    echo "$(cat /etc/bandit_pass/bandit16)" | openssl s_client -connect localhost:31518 -quiet
Does not show the password

    echo "$(cat /etc/bandit_pass/bandit16)" | openssl s_client -connect localhost:31790 -quiet
I found “RSA PRIVATE KEY” mean here
1️⃣ Copy the ENTIRE RSA key
Copy everything, including:
-----BEGIN RSA PRIVATE KEY-----
...
-----END RSA PRIVATE KEY-----
No missing lines. No extra spaces.
2️⃣ Before paste that we will do one thing exit that current domain 

          nano bandit17.key
and Save it to a file Create a file called bandit17.key:
3️⃣ Fix file permissions (VERY IMPORTANT)

       chmod 600 bandit17.key
4️⃣ Log in using the private key

        ssh -i bandit17.key bandit17@bandit.labs.overthewire.org -p 2220
✅ This will log you in without a password. Once logged in, You are now bandit17. To continue later:

       cat /etc/bandit_pass/bandit17

## Level-17
+ Username : bandit17
+  Password :
+ Domain : ssh bandit17@bandit.labs.overthewire.org -p 2220
+ Port Num : 2220
### Commands
- ls = list files
- diff = compare files
- grep = 
### Explination
[image](./images/image-17.png)

    ls
You should see:
 passwords.old  passwords.new
Compare the two files using diff:

     diff passwords.old passwords.new
You’ll see something like:
        < oldpasswordline
           ---
        > newpasswordline

    Lines starting with < come from passwords.old

    Lines starting with > come from passwords.new
Alternative (cleaner output)

    diff passwords.old passwords.new | grep ">"
^> → only lines starting with >
cut -c3- → removes > (greater-than + space)

    diff passwords.old passwords.new | grep "^>" | cut -c3-
## Level-18
+ Username : bandit18
+  Password :
+ Domain : ssh bandit18@bandit.labs.overthewire.org -p 2220 cat readme
+ Port Num : 2220
### Commands
- cat = Display the file contents on terminal
### Explination
[image](./images/image-18.png)
Why it immediately exits (“Byebye!”)
In Bandit18, your .bashrc is modified so that as soon as you log in, it prints:

    Byebye!

    ssh bandit18@bandit.labs.overthewire.org -p 2220
and it immediately exits, that means:
👉 Your password is correct 👉 You are now officially on Bandit18 👉 This behavior belongs to Level 18 → 19. How to actually stay in Bandit18. You must bypass .bashrc.
What you’re seeing now is normal SSH behavior, not a crash.
This is intentional for security.
 
    ssh bandit18@bandit.labs.overthewire.org -p 2220 cat readme
SSH logs in and prompts for a password. Enter Password: Does NOT start an interactive shell. Runs cat readme
Prints the password for bandit19
Immediately exits (this is normal)
    
    Can’t stay logged in    -	Bandit18 trap
    Blank screen	        -    Shell killed
    SSH works but exits	     -  Normal
    Best solution	         -   ssh ... cat readme
## Level-19
+ Username : bandit19
+  Password :
+ Domain : ssh bandit19@bandit.labs.overthewire.org -p 2220
+ Port Num : 2220
### Commands
- ls -1 = list files
- cat = Display the file contents on terminal
### Explination
[image](./images/image-19.png)

      ls -l
You’ll see something like:
-rwsr-x--- 1 bandit20 bandit19 7296 bandit20-do Owned by bandit20 Executing it runs as bandit20
3. Run the binary without arguments

       ./bandit20-do
Output :
Run a command as another user.
Usage: ./bandit20-do <command>
4. Use the binary to read the password
Tell it to run cat as bandit20:

    ./bandit20-do cat /etc/bandit_pass/bandit20
## Level-20
+ Username : bandit20
+  Password :  0qXahG8ZjOVMN9Ghs7iOWsCfZyXOUbYO
+ Domain : ssh bandit20@bandit.labs.overthewire.org -p 2220
+ Port Num : 2220
### Commands
- nc = netcat
### Explination
[image](./images/image-20.png)
[image](./images/image-20-1.png)
🔹 Terminal 1

    nc -l -p 4444
(wait — cursor blinking)
🔹 Terminal 2 (new SSH window)

    ./suconnect 4444
🔹 BACK TO TERMINAL 1
Now PASTE ONLY THIS LINE and press ENTER:That means bandit20 password

      0qXahG8ZjOVMN9Ghs7iOWsCfZyXOUbYO
✅ You will now see TWO lines:

    0qXahG8ZjOVMN9Ghs7iOWsCfZyXOUbYO
    <bandit21_password_here>
## Level-21
+ Username : bandit21
+  Password :  EeoULMCra2q0dSkYj561DX7s1CpBuOBt
+ Domain : ssh bandit21@bandit.labs.overthewire.org -p 2220
+ Port Num : 2220
### Commands
- ls = list files
- cat = Display the file contents on terminal
- echo = Display a string
### Explination
[image](./images/image-21.png)
List the files in /etc/cron.d/:

    ls /etc/cron.d/
You should see something like:

    cronjob_bandit22
Step 3: Read the cron job
    
    cat /etc/cron.d/cronjob_bandit22
Typical output:
    * * * * * bandit22 /usr/bin/cronjob_bandit22.sh
Meaning:
    * * * * * → runs every minute Runs as user bandit22
Executes /usr/bin/cronjob_bandit22.sh
Step 4: Read the script being executed

      cat /usr/bin/cronjob_bandit22.sh
You’ll see something like:
#!/bin/bash
chmod 644 /tmp/$(echo I am user bandit22 | md5sum | cut -d ' ' -f 1)
cat /etc/bandit_pass/bandit22 > /tmp/$(echo I am user bandit22 | md5sum | cut -d ' ' -f 1)
Step 5: Understand what it does

It computes:

    echo I am user bandit22 | md5sum
Uses the MD5 hash as a filename in /tmp/
Writes the bandit22 password into that file
Makes it readable
Example output:

    8169b67bd894ddbb4412f91573b38db3  -
The filename is:
/tmp/8169b67bd894ddbb4412f91573b38db3
Step 7: Read the password

    cat /tmp/8169b67bd894ddbb4412f91573b38db3
## Level-22
+ Username : bandit22
+  Password :  tRae0UfB9v0UzbCdn9cY0gQnds9GF58Q
+ Domain : ssh bandit22@bandit.labs.overthewire.org -p 2220
+ Port Num : 2220
### Commands
- ls = list files
- cat = Display the file contents on terminal
- echo = Display a string
### Explination
[image](./images/image-22.png)
List the files in /etc/cron.d/:

    ls /etc/cron.d/
You should see something like:

    cronjob_bandit23
Step 3: Read the cron job
    
    cat /etc/cron.d/cronjob_bandit23
Typical output:
    * * * * * bandit23 /usr/bin/cronjob_bandit23.sh
Meaning:
    * * * * * → runs every minute Runs as user bandit23
Executes /usr/bin/cronjob_bandit23.sh
Step 4: Read the script being executed

      cat /usr/bin/cronjob_bandit23.sh
You’ll see something like:
#!/bin/bash
chmod 644 /tmp/$(echo I am user bandit23 | md5sum | cut -d ' ' -f 1)
cat /etc/bandit_pass/bandit23 > /tmp/$(echo I am user bandit23 | md5sum | cut -d ' ' -f 1)
Step 5: Understand what it does

It computes:

    echo I am user bandit23 | md5sum
Uses the MD5 hash as a filename in /tmp/
Writes the bandit23 password into that file
Makes it readable
Example output:

    8ca319486bfbbc3663ea0fbe81326349  -
The filename is:
/tmp/8ca319486bfbbc3663ea0fbe81326349
Step 7: Read the password

    cat /tmp/8ca319486bfbbc3663ea0fbe81326349
## Level-23
+ Username : bandit23
+  Password :  0Zf11ioIjMVN551jX3CmStKLYqjk54Ga
+ Domain : ssh bandit23@bandit.labs.overthewire.org -p 2220
+ Port Num : 2220
### Commands
- ls = list files
- cat = Display the file contents on terminal
- nano = Edit a file
- chmod = Change file permissions
### Explination
[image](./images/image-23.png)
2️⃣ Inspect the cron configuration

     ls /etc/cron.d/
You should see something like: bandit24

     cat /etc/cron.d/bandit24
Output will look similar to:
     * * * * * bandit24 /usr/bin/cronjob_bandit24.sh
This means:
Every minute (* * * * *) User bandit24
Executes /usr/bin/cronjob_bandit24.sh
3️⃣ Read the cron script

    cat /usr/bin/cronjob_bandit24.sh

     export NANO_DISABLE_HISTORY=1
Quick check that your script is fine. After saving, verify:

     cat /tmp/getpass.sh
 Change the permissions:

    chmod +x /tmp/getpass.sh
Use it to get the password:
    
    cat /tmp/bandit24_pass
## Level-24
+ Username : bandit24
+  Password :  gb8KRRCsshuZXI0tUuR6ypOFjiZbf3G8
+ Domain : ssh bandit24@bandit.labs.overthewire.org -p 2220
+ Port Num : 2220
### Commands
### Explination
Strategy:
Generate all PINs from 0000 → 9999
Prefix each with the bandit24 password
Pipe everything into one nc (netcat) connection
Watch for the line that contains the bandit25 password
[image](./images/image-24-1.png)
👉 Replace BANDIT24_PASSWORD with the actual password for bandit24
[image](./images/image-24.png)
Why this works
seq -w keeps the PINs 4 digits (0001 instead of 1)
The loop sends all attempts at once
nc keeps one open TCP connection, which is exactly what the daemon wants
## Level-25
+ Username : bandit25
+  Password :  iCi86ttT4KSNe1armKiwbQNmB3YJP3q4
+ Domain : ssh bandit25@bandit.labs.overthewire.org -p 2220
+ Port Num : 2220
### Commands
### Explination 