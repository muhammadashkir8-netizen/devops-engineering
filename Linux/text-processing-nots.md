TASK 5: TEXT PROCESSING

Scenario:
Your DevOps team needs to audit the system. You need to:
Search /etc/passwd for all users who use /bin/bash as their shell
Count how many "error" messages are in /var/log/syslog
Find all unique usernames in the first 50 lines of /var/log/auth.log
Use grep, awk, sed, and pipes. Document your commands and what each does.
In your notes, explain: Why pipe instead of running commands separately? What's the advantage?

_____________________________________________________________________________________________________________
Solution 

cat /etc/paswd - /etc folder is basically the system setting on the linux 
grep “/bin/zsh” /etc/passwd will show me the user that are have /bin/zsh as their shell 
grep “error” /var/log/syslog | wc -1 = Count how many "error" messages 

head -n 50 /var/log/auth.log | grep "user\|username" | awk '{print $X}' | sort | uniq

Quick explanation:
head -n 50 /var/log/auth.log — shows first 50 lines
| — pipe: sends those 50 lines to the next command
grep "user\|username" — filters for lines containing "user" or "username"
| — pipe again: sends filtered lines to awk
awk '{print $X}' — extracts column X (you determine which column has the username by looking at the file structure)
| — pipe: sends usernames to sort
sort — arranges them alphabetically
| — pipe: sends sorted list to uniq
uniq — removes duplicates, leaving only unique usernames
Why pipes? Each command does one thing. Pipes chain them together so output from one becomes input to the next. More efficient than running each separately.
