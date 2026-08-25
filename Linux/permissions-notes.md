Task 3 Scenario — PERMISSIONS AND OWNERSHIP
You're a junior DevOps engineer at a company. Your security team just flagged an issue:
"We have configuration files with database passwords scattered across our servers. The problem: they're readable by everyone on the system. We need you to:
1. Create a script that deploys these config files
2. Lock down permissions so ONLY the owner (you) can read AND write
3. Everyone else on the system can read it, but NOT modify it
4. Document the exact permissions command you used and explain why it works
5. Show proof that the permissions are correct
6. Try to delete/modify the file as a different user — show what happens"
_____________________________________________________________________________________________________________

Task 3 Scenario — PERMISSIONS AND OWNERSHIP

You're a junior DevOps engineer at a company. Your security team just flagged an issue:
"We have configuration files with database passwords scattered across our servers. The problem: they're readable by everyone on the system. We need you to:

Create a script that deploys these config files
Lock down permissions so ONLY the owner (you) can read AND write
Everyone else on the system can read it, but NOT modify it
Document the exact permissions command you used and explain why it works
Show proof that the permissions are correct
Try to delete/modify the file as a different user — show what happens"
______________________________________________________________________________________________________________

Solutions 

Vim depoly.sh , Inside the script that will i must tell kernel (the brain of linux) or operating systems how to understand this script.

Shebang line #!/bin/zsh - It tells the computer: "Hey, everything written inside this file is written in the Bash language. Use the Bash program located at /bin/bash to read and execute these instructions." If you put space between # ! it will break and if you put it other way round !# it will break.

I am still inside the depoly.sh i wrote this code echo “ Liverpool going to win the prem and ucl 26/27” > data.conf. The symbol > is redirection Operator which acts as funnels telling linux put that text liverpool into that file.  >> is used to add on to a file without deleting it content and > will remove everything if you doing it to existing file.

:wq - stands for write quit, this is used when saving the script you need to press ecs and :wq if the script is being stubborn use !! at the end of it 

chmod +x depoly.sh to make the script executable 

When i type ls -l i see -rw-r--r-- 1 mohamed-ashkir mohamed-ashkir   53 Aug 25 14:11 data.conf
which mean mohamed-ashkir who is the user has read and write permission, the group named mohamed-ashkir again has read permission and other have read permission.  
chmod 644 data.conf - this code mean the owner has read and write permission, group and other have only read permission 

Changing ownership- 
Sudo which means superuser do is a command with root privileges 
So:
chown owner:group file = change both the user (or owner) and the group
chown owner file = change owner only
chown :group file = change group only
