# BANDIT LABS
## Important Points 
    1.ctrl+1 = " commit "

    2.ctrl+k then leave them thenpress v = you can able to see the updated git 
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
+ Domain : bandit.labs.overthewire.org   
+ Port Num : 2220


### Commands

+ ls = list files  
+ cd = change directory  
+ cat = read file
 
### Explination
 

 
3️⃣ Accept the host key (first time only)

You’ll see something like:

Are you sure you want to continue connecting (yes/no)?


Type:

yes


and press Enter.

If you want, tell me:

what OS you’re on (Linux/macOS/Windows), or

whether you’re using PowerShell, WSL, or a Linux VM

and I’ll tailor the commands exactly for your setup.


Perfect 😄 Linux makes this nice and clean.

You can do everything for Bandit straight from your terminal.

Bandit Level 0 (Linux)

Step-by-step (from your terminal)

1.Open a terminal.

2.Run this command:


Run this command:

ssh bandit0@bandit.labs.overthewire.org -p 2220


-p 2220 is important — SSH defaults to port 22 otherwise.

When prompted for a password, type:

bandit0


(You won’t see the password as you type — that’s normal.)

What success looks like

If it works, you’ll see something like a welcome banner and land in a shell that looks roughly like:

bandit0@bandit:~$


Congrats 🎉 — you’re logged in.

Next step

Once logged in:

Read the on-screen message (or just know this)

Go to the Level 1 page on OverTheWire to see what to do next

Or list files with:

ls


You’ll see a file called readme.

Read it:

cat readme


That file gives you the password for Level 1.

Pro tip (you’ll use this a lot)

To log out later:

exit














      
 





## Level 0 - Level 1

### Commands

+ ls = list files  
+ cd = change directory       
+ cat = read file

### Explination
 


What the level is asking you to do

👉 The password for bandit1 is inside a file called readme
👉 That file is in bandit0’s home directory
👉 Read it, copy the password, then SSH into bandit1

Step-by-step solution
Step 1: Make sure you are logged in as bandit0

If you are not logged in yet, do:

ssh bandit0@bandit.labs.overthewire.org -p 2220


Password:

bandit0


You should see:

bandit0@bandit:~$

Step 2: List files in the home directory

Run:

ls


Output:

readme


✔️ That’s the file we need.

Step 3: Read the readme file

Use cat to display its contents:

cat readme


You’ll see something like:

The password for bandit1 is: XXXXXXXXXXXXX


📌 This string is the password for bandit1

Step 4: SAVE THE PASSWORD (important!)

On your own computer, save it somewhere safe:

Notes app

Text file

Password manager

Example:

Bandit Level 1 password: XXXXXXXXXXXXX


If you lose it, you must start over.

Step 5: Log out from bandit0

Type:

exit

Step 6: Log in as bandit1

Now use the password you just found:

ssh bandit1@bandit.labs.overthewire.org -p 2220


When prompted, paste/type the password from readme.

Step 7: Confirm success

If login works, you’ll see:

bandit1@bandit:~$


🎉 Congrats — Level 1 unlocked!

Commands you used (and what they mean)
Command	Purpose
ssh	Connect to a remote server
ls	List files
cat	Read a file
exit	Log out
What’s next?

Level 1 introduces a tricky filename problem that confuses many beginners 😈
If you want, I can:

Walk you through Level 1 → Level 2

Explain why Linux filenames can be “weird”

Help you build a clean notes template for all Bandit levels

Just say the word 👊


















## Level 1 - Level 2
+ commands 
+ explination


Level 1 → Level 2: What’s the trick?

👉 The password for bandit2 is stored in a file named:

-


Yes — the filename is literally a dash (-).

Step-by-step solution
Step 1: Confirm you are bandit1

Your prompt should look like this:

bandit1@bandit:~$


If not, log in:

ssh bandit1@bandit.labs.overthewire.org -p 2220


(use the password you got from Level 0 → 1)

Step 2: List files

Run:

ls


Output:

-


That’s the file containing the password.

⚠️ Common mistake (DO NOT do this)
cat -


❌ This makes cat wait for keyboard input because - means stdin.

Step 3: Correct way to read the file

You have two correct options.

✅ Option 1 (recommended): Use ./
cat ./-


Explanation:

./ means “current directory”

It tells Linux: “this is a filename, not an option”

✅ Option 2: Use full path
cat /home/bandit1/-

Step 4: Get the password

You’ll see output like:

XXXXXXXXXXXXXXXXXXXX


📌 This is the password for bandit2
➡️ SAVE IT immediately

Step 5: Log into Level 2

Exit bandit1:

exit


Now log in as bandit2:

ssh bandit2@bandit.labs.overthewire.org -p 2220


Paste the password you just found.

Step 6: Confirm success

If correct, you’ll see:

bandit2@bandit:~$


🎉 Level 2 unlocked

Commands used & why they matter
Command	Why it matters
ls	See hidden/tricky filenames
cat ./-	Read a file starting with -
exit	Leave the current level
Pro tip (you’ll use this a LOT later)

Whenever a filename starts with:

-

spaces

weird characters

Use:

./filename


or quote it:

"filename"

















## 
