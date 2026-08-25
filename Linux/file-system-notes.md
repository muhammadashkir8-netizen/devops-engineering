File system navigation Task

i will practice different commands till i have good understanding it's functions

Task 2 - 

BEGINNER, FILE SYSTEM NAVIGATION FOCUS:
You're a junior DevOps engineer. Your lead asks you to:
"I need you to explore the Linux filesystem and understand how it's organized. Go to /var/log, see what log files exist, check their sizes, and understand the directory structure. Then create a backup copy of one log file in a safe location. Finally, show me the commands you used and what you learned about how Linux organizes system files."

Step 1- cd /var/log i typed this command get inside the linux file system cd mean change directory.
-rw-r-----  1 syslog            adm               43510 Aug 13 20:30 auth.log

This is what i can see on the linux file systems; this is just an example i want to use. -rw-r——- is the file permission read, write and execute who out the user (or owner),  group and public can modify the file.  Syslog is the owner of the file, adm is the group, 43510 is the file size and auth.log is the file name. When a log starts with - this mean it is a normal file and d is a directory.

step 2 - I then navigate to a temporary directory called /tmp/ this is where users can store file they need for short time and it delete itself everything the computer restart.

step3- when copying the log file i need to use the correct file path instead of typing cp auth.log backups i n
eed tell it where to get it from. Which is the /var/log so the code would be cp /var/log/auth.log backups

Step 4- rename the file i used mv, i was in the directory /tmp/backups i typed this command mv auth.log auth.log-2026-08-25.

Step 5- head and tail are used to print out the first 10 lines (head) and last 10 line (tail) of a file. The flag option -n i used to tell the linux what number of lines you want so head -n 10 and tail -n 5 mean first 10 line when used head and for tail -n last 5 lines.
