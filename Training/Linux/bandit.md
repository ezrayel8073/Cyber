# BANDIT LABS
## Important Points 
    1.ctrl+1 = " commit "
    1.1 Ctrl+shift+i = " inspect "
    1.2 Ctrl+shift++ = " zoom in "
    1.3 Ctrl+shift+- = " zoom out "
    1.4 Ctrl+shift+0 = " reset zoom "
    1.5 ctrl+c = " exit "
    1.6 ctrl+X = " save and exit "
2.ctrl+k then leave them thenpress v = you can able to see  the updated git 
    that means your not goto the git otherthan you will able see updated git by your own correctons on Vs code 
3.In a system you have file Like in a Notepad there is a resume file then you can able to see the resume file
 4.It has a properties. In a File properties you can able to see that 3 types  modules

        1.System
        2.You (your mail)
        3.Administrator
 5.These 3 have right on a file Authorization  
 6.Like  The Root is a Administrator in Linux setup
## Terminal
1.First you can start the terminal you will see the starting stage of terminal the you need to go that terminal you can access that terminal by " sudo su " 
2.After that terninal can ask you the password 
3. Password : " kali "
4. then you enter the password you will not able to see that password but it can automatically access
 5. It will navigate Home that means Root
6. Looks like  " root@kali "
 7. It will shows in red color. It is the simple checking that  you are in root or not and below that root you will see " #  " in red color 
   8. Finally you can start the Terminal
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
  ls = list files
  ls  -i =
  find = Find the files and directories Based on    Name, size, Modification time
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
You’ll see something like:
1234567 spaces in this file name
Now run:

    find . -inum 1234567 -exec cat {} \;
(replace 1234567 with the actual number)
## Level-3
+ Username : bandit3   
+  Password :                 
+ Domain :   ssh bandit3@bandit.labs.overthewire.org -p 2220
+ Port Num : 2220
### Commands
ls = list files
 cd = change directory 
ls -a =
  find = Find the files and directories Based on    Name, size, Modification time
### Explination
List files in the home directory:

     ls
     
You type ls and the output literally says:
      
      inhere
So the file is inside a directory named inhere, not directly in your home folder.
Here is the 100% correct command sequence you need.

    cd inhere
When your prompt changes to:

     ~/inhere$
it means:
➡️ You are now inside the inhere directory
Run this command instead:

     ls -a
When ls shows:

    Hiding from you
Type exactly this while you are in ~/inhere:

    find . -type f -exec cat {} \;
Why this works
find . -type f → finds the file no matter how strange its name is
-exec cat {} \; → prints the contents directly
No quotes, no guessing, no typing the filename
## Level-4
+ Username : bandit4   
+  Password :                        
+ Domain :   ssh bandit4@bandit.labs.overthewire.org -p 2220 
+ Port Num : 2220
### Commands
ls = list files  
+ cd = change directory
ls or ls -a = list files
  find = Find the files and directories Based on    Name, size, Modification time
  cat = read file
### Explination
What’s going on
The password is inside the inhere directory
The file is hidden, meaning its name starts with a .
Normal ls won’t show it unless you ask nicely

    ls
Step-by-step solution
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
You must see something like:
file00  file01  file02  file03  file04  file05  file06  file07  file08  file09
Why ls -1 helps

      ls -1
You should see something like:
-file00
-file01
-file02
-file03
...
✅ Correct way to read the file
Option 1 (best & cleanest)

    cat ./-file02
Option 2 (also valid)

     cat -- -file02
-- means: stop reading options after this
It shows diamond symboles along with charecteres in a password
Run:

    cat ./-file02 | od -An -tx1
This shows the password in hex bytes, proving it’s longer than 4 characters.
You’ll see output like:
61 7f 9a e2 ...
2️⃣ Identify the ONLY valid password file
Run:

      file ./* or file ./-*
You must see exactly ONE line like:
./-file07: ASCII text
⚠️ If it does NOT say ASCII text, it is NOT the password.
3️⃣ Read ONLY that ASCII file
Example:

     cat ./-file07
## Level-5
+ Username : bandit5   
+  Password :                         
+ Domain :  ssh bandit5@bandit.labs.overthewire.org -p 2220  
+ Port Num : 2220
### Commands
ls = list files  
+ cd = change directory
ls or ls -1 = list files
  find = Find the files and directories Based on    Name, size, Modification time
  cat = read file
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
You must see something like:
file00  file01  file02  file03  file04  file05  file06  file07  file08  file09
Why ls -1 helps

         ls -1
This lists one filename per line, making copy-paste and reading easier.
You should see something like:
-file00
-file01
-file02
-file03
...
Then use this command it will shows the inner file names.
 
    file ./*
But this time it shows directories.
Because it has num of files in their directories thats why file ./* command cannot find exact one 
Run this exact command:

    find . -type f -size 1033c ! -executable
Why this works
-type f → files only
-size 1033c → exactly 1033 bytes
! -executable → excludes executable files
find → searches recursively under inhere 
Example:

./maybehere07/.file2
4️⃣ Read the file

       cat ./maybehere07/.file2
## Level-6
+ Username : bandit6   
+  Password :                     
+ Domain :  ssh bandit6@bandit.labs.overthewire.org -p 2220 
+ Port Num : 2220
### Commands
find = Find the files and directories Based on    Name, size, Modification time
  cat = Display the file contents on terminal
### Explination
Level 6 has a completely different task:
The password for the next level is stored somewhere on the server and has all of the following properties:
owned by user bandit7
owned by group bandit6
33 bytes in size
Correct solution for Level 6 → 7
Run this from your home directory:

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
grep = 
### Explination
data.txt contains many words/lines. One of them includes the word millionth, and the password is on that same line.
The fastest way to do this is with grep.
Run this in the Bandit Level 7 shell:

     grep millionth data.txt
grep searches through data.txt
It prints the entire line containing the word millionth
## Level-8
+ Username : bandit8   
+  Password :                     
+ Domain : ssh bandit8@bandit.labs.overthewire.org -p 2220  
+ Port Num : 2220
### Commands
ls = list files 
sort = 
uniq =
### Explination
Goal (rephrased)
Find the only line in data.txt that appears exactly once. That line is the password for the next level.
The classic UNIX pipeline for this task is:

sort data.txt | uniq -u

     sort data.txt
Groups identical lines together (required for uniq to work correctly).

     uniq -u
Prints only lines that occur once.
Then:
   
    sort data.txt | uniq
And finally:

    sort data.txt | uniq -u
## Level-9
+ Username : bandit9   
+  Password :                     
+ Domain : ssh bandit9@bandit.labs.overthewire.org -p 2220  
+ Port Num : 2220
### Commands
ls = list files 
strings = 
grep =
### Explination
Inspect data.txt
data.txt is mostly binary, so opening it with cat won’t help.

Use strings to extract human-readable text:

    strings data.txt

Filter for lines with = characters
The password is preceded by several = characters, so pipe the output to grep:

    strings data.txt | grep "==="
Why this works
strings → extracts readable ASCII text from a binary file
grep "===" → narrows results to lines matching the level hint
The password is intentionally easy to spot once filtered correctly
## Level-10
+ Username : bandit10   
+  Password :                     
+ Domain :  ssh bandit10@bandit.labs.overthewire.org -p 2220 
+ Port Num : 2220
### Commands
ls = list files 
cat = Display the file contents on terminal
 base64 =  
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
cat = Display the file contents on terminal
tr = 
### Explination
The password is in data.txt.
All letters (a–z, A–Z) are rotated by 13 positions (ROT13).
Numbers and symbols are unchanged.
ROT13 is symmetric: applying it once decodes the text.
How to solve it
Use tr to rotate the characters back:

    cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'
This command:
Reads the file
Translates:
A–Z → N–Z A–M
a–z → n–z a–m
Prints the decoded password to the terminal
Why this works
ROT13 shifts each letter 13 places:
a ↔ n, b ↔ o, …, m ↔ z
Same logic for uppercase letters
Because the alphabet has 26 letters, rotating by 13 twice returns the original text.
## Level-12
+ Username : bandit12
+  Password : TguMNxKo1DSa1tujBLuZJnDUlCcUAPlI                       
+ Domain :  ssh bandit12@bandit.labs.overthewire.org -p 2220 
+ Port Num : 2220
### Commands
sort = 
uniq =
### Explination
## Level-13
+ Username : bandit13   
+  Password : FO5dwFsc0cbaIiH0h8J2eUks2vdTDwAn          
+ Domain : ssh bandit13@bandit.labs.overthewire.org -p 2220
below is the image of level-13
[image](./images/image-13.png)
### Commands
ls = list files
cat = Display the file contents on terminal
nano =
chmod =
### Explination
What’s different in this level?
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
copy the entire key 
Paste the key into a text editor means nano tool

     nano key 
then save it and rename it to key
key rename name is also a key
3. Fix the key’s permissions (important!)
SSH will refuse to use a private key if it’s too open.

      chmod 600 key
4. Use the private key to log in as bandit14
From inside bandit13, Example run:

      ssh -i sshkey.private bandit14@localhost
Correct command:

    ssh -i key bandit14@bandit.labs.overthewire.org -p 2220
Explanation:
-i sshkey.private → tells SSH which private key to use
bandit14@localhost → you’re logging into the same machine, just as a different user
#### 2nd Method
[image](./images/image-13-1.png)
✅ DOWNLOAD SSH KEY FROM BANDIT TO KALI (FINAL)
📌 Run this ON YOUR KALI TERMINAL, not on Bandit:

    scp -P 2220 bandit13@bandit.labs.overthewire.org:/home/bandit13/sshkey.private .
When asked, enter the bandit13 password.
The file will appear in your current Kali directory.
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
cat = Display the file contents on terminal
nc =
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
[image](./images/image-15.png)
### Explination
Step 1: Log into Bandit Level 15

    ssh bandit15@bandit.labs.overthewire.org -p 2220
Enter Password:    
Step 2: Connect securely to port 30001

    openssl s_client -connect localhost:30001
You should see a lot of SSL-related output — this is normal.
Step 3: Send the current password
Paste the Bandit 15 password and press Enter.
## Level-16
+ Username : bandit16
+  Password :
+ Domain : ssh bandit16@bandit.labs.overthewire.org -p 2220
+ Port Num : 2220
### Commands

