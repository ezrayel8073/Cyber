ls = list files and directories
ls -i = list files with inode numbers
ls -a = list all files including hidden files
ls -1 = list one file per line
ls -l = list files in long format
ls -la = list files in long format including hidden files
ls -al = list files in long format including hidden files
ls -lh = list files in long format with human-readable sizes
ls -C = list files in columns
ls -d */ = list directories only
ls -f = list files without sorting, including hidden files
ls -F = list files with type indicators
ls -g = list files in long format without owner
ls -G = list files with colorized output
ls -b = list files with escaped special characters
ls -B = list files excluding backup files




## File & Directory Commands
mv "xxx" "yyy" = move or rename a file or directory
cp "xxx" "yyy" = copy a file
cp -r "xxx" "yyy" = copy a directory recursively
rm "xxx" = remove a file
rm -r "xxx" = remove a directory
mkdir "xxx" = create a directory
cd "xxx" = change directory
touch "xxx" = create an empty file or update timestamp
. = current directory
.. = parent directory
~ = home directory

## Permissions & File Info
chmod 600 "xxx" = change file permissions
file "xxx" = display file type information
cat "xxx" = display the contents of a file
grep "pattern" "xxx" = search for text in a file
whereis "xxx" = locate binary, source, and manual files
pwd = print the current working directory
chown user:group "xxx" = change file owner and group



## Redirection & Pipes
| = pipe output from one command to another
> = redirect output to a file (overwrite)
>> = redirect output to a file (append)
< = redirect input from a file


## User & Help
whoami = display the current user
man "xxx" = display the manual page for a command
info "xxx" = display GNU info documentation


## Process Management
ps = display processes of the current shell
ps aux = display all running processes


##  Date & Calendar
date = display the current date and time
date "+%Y-%m-%d" = display date in YYYY-MM-DD format
date "+%Y-%m-%d %H:%M:%S" = display date and time
date "+%Y-%m-%d %H:%M:%S %Z" = display date, time, and timezone
cal = display current month calendar
cal 2023 = display calendar for year 2023
cal 2 2023 = display calendar for February 2023



## System Information
uname = display system information
uname -a = display all system information
uname -r = display kernel release
uname -v = display kernel version
uname -m = display machine hardware name
uname -o = display operating system
uname -s = display kernel name
uname -p = display processor type
uname -i = display hardware platform


## File Searching
find . -name "xxx" = search for a file or directory by name
locate "xxx" = search for a file using indexed database
locate "xxx" | xargs grep "yyy" = search for text inside located files

## Disk Usage
df = display filesystem disk usage
du = display directory disk usage
du -h = display disk usage in human-readable format
du -s = display summary of directory size
du -sh . = display size of current directory

## Download Commands
wget "URL" = download a file from the internet
curl "URL" = fetch content from a URL
curl -O "URL" = download file using original filename



## Sorting & Counting
sort "xxx" = sort a file alphabetically
sort -r "xxx" = sort file in reverse order
sort -n "xxx" = sort file numerically
sort -nr "xxx" = sort file numerically in reverse order
sort -u "xxx" = sort file and remove duplicates
sort -ur "xxx" = sort file in reverse order and remove duplicates
sort "xxx" | uniq -c = count repeated lines in a file


## Word Count
wc "xxx" = count lines, words, and bytes
wc -l "xxx" = count lines in a file
wc -w "xxx" = count words in a file
wc -c "xxx" = count bytes in a file



| = pipe
     > = redirect output to a file or newpasswordline
< = redirect input from a file  or oldpasswordline
