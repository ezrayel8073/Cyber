
ls = list files
ls -i = list files by inode number
ls -a = list all files, including hidden ones
ls -1 = list files one per line
ls -l = list files in long format
ls -la = list files in long format, including hidden ones
ls -al = list files in long format, including hidden ones
ls -b = list files in blocks
ls -B = list files in blocks, including hidden ones
ls -C = list files in columns
ls -d = list directories only
ls -D = list directories only, including hidden ones
ls -f = list files only
ls -F = list files only, including hidden ones
ls -g = list files by group
ls -G = list files by group, including hidden ones
ls -h = list files in human-readable format


file "xxx" = display information about a file
cat "xxx" = display the contents of a file
grep "xxx" = search for a pattern in a file
. = current directory
.. = parent directory
| = pipe
> = redirect output to a file or newpasswordline
< = redirect input from a file  or oldpasswordline
touch "xxx" = create a file
chmod 600 "xxx" = change file permissions
~ = home directory
mv "xxx" "yyy" = move a file or directory
cp "xxx" "yyy" = copy a file or directory
rm "xxx" = remove a file or directory
mkdir "xxx" = create a directory
cd "xxx" = change directory
pwd = print the current working directory
find "xxx" = search for a file or directory
find . -name "xxx" = search for a file or directory in the current directory
locate "xxx" = search for a file or directory using the locate command
locate "xxx" | xargs grep "yyy" = search for a file or directory using the locate command and then search for a pattern in the file
locate "xxx" | xargs grep "yyy" | xargs sed "zzz" = search for a file or directory using the locate command, search for a pattern in the file, and then replace a pattern in the file


