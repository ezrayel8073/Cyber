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
 



🎯 Goal (Level 0 → Level 1)

Read the password stored in a file called readme in the home directory, then use it to log into bandit1 via SSH.

📁 Step 1: List files in the home directory

You should already be logged in as bandit0.

Run:

ls


You’ll see:

readme

📄 Step 2: Read the file

Use cat to print the contents:

cat readme


➡️ This will output the password for bandit1.
Copy it somewhere safe (notes file, password manager, etc.).

🔐 Step 3: Log into bandit1

Exit the current session (or open a new terminal):

exit


Now log in using the password you just found:

ssh bandit1@bandit.labs.overthewire.org -p 2220


Paste the password when prompted.

✅ What success looks like

You’ll land at:

bandit1@bandit:~$


Congrats — Level 1 unlocked 🗝️

📝 Pro tip (seriously, do this)

On your local machine, create a notes file like:

Bandit0 → Bandit1: <password>
How: cat readme


Future-you will thank present-you. Trust me.



















## Level 1 - Level 2
commands + explination
ls = list files                 
hidden file  - 

password: 







🎯 Goal (Level 1 → Level 2)

The password is stored in a file named - in the home directory.

🧠 Why this is tricky

In Linux, a leading dash (-) usually means “this is an option/flag”.

So if you try the obvious:

cat -


❌ That doesn’t work the way you expect — cat thinks - is a special argument (stdin), not a filename.

📁 Step 1: Verify the file exists

Run:

ls


You should see something like:

-


Yep. That’s the filename. Linux is being rude on purpose.

✅ Step 2: Read the file correctly

You have two clean solutions. Either one works.

✅ Option 1: Use ./ (recommended)

This tells the shell: “I mean the file in this directory”.

cat ./-

✅ Option 2: Use -- to end options

-- tells commands: “stop parsing flags after this”.

cat -- -

🔑 Result

One of those commands will print the password for bandit2.

Copy it exactly.

➡️ Next Step

Log into the next level:

ssh bandit2@bandit.labs.overthewire.org -p 2220


Paste the password you just found when prompted.

🧠 Pro tip (this will come up again)

Any time a filename starts with -, remember:

./filename

or -- filename

Linux loves testing whether you really understand what you’re typing 😄

Ready for Level 2 → Level 3? That one introduces spaces in filenames… which is another classic trap 👀









## 
