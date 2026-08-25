TASK 4: PROCESS MANAGEMENT

Scenario:

You're on-call for a production system. The application keeps spawning background worker processes to handle jobs. One of them is stuck in an infinite loop consuming CPU and memory.

Your job:

1. Start a long-running background process (use sleep 1000 &)
2. Find its PID using ps aux
3. Monitor it in real-time with top or htop
4. Bring it to the foreground with fg
5. Send it to background with bg
6. Kill it using the PID with kill
7. Verify it's dead with ps aux
____________________________________________________________________________________________________________

Solutions 

sleep function i used to make the computer pause and wait in the background so sleep 1000 & mean the system to need to sit in idle for set period of 1000 seconds and & is an operator that prevents your terminal screen to freeze for literally 1000 sec which is 16 min. & tells linux to run the task in the background 

Brief explanation of PID - process ID which is basically id card number or like a student id for running programs. As devops engineer we need to manage servers and also kill frozen program by finding their pid, check system resources - seeing whihc program is stealing all of the cpu or ram,  To Track Logs: When debugging a crash, system log files (/var/log/syslog) will often print the PID next to the error message so you know exactly which background service caused the failure.

ps aux this command break down means - ps report a snapshot of every single program running on the entire computer. aux is the flag each letter stands for different thing a (all) shows process for all user, not just own account, u (user) display information about the cpu/ram and who owns the process x(eXtended) includes process that dont have background system processes.

As a DevOps engineer, ps aux is your essential troubleshooting tool for checking the health of a server whenever it acts up. You use it in four main scenarios: to find out which program is stealing system resources when a server is slow or frozen, to verify that background services like Nginx or Docker are actually running by filtering with grep, to check for active users or scripts before rebooting or upgrading a server, and to find the hidden tracking number (PID) of a crashed program so you can force it shut using the kill command.

sleep 1000 & gave me the PID 8180

Top & Htop - both of these command are used to display linux process a dashboard that is live and is simply any program or task that is currently running on my computer. Top is built-in and htop is modern so you need to upgrade it give you color-coded version.

To understand the linux processes - you see the following PID(process ID), Owner(user), resource the percentage of the cpu and ram memory and status of the task either running, sleeping or crashed.

Summary for a DevOps Engineer- Think of a process as a live worker inside your server. You use top or htop to look down at the factory floor in real-time, see exactly what each worker (PID) is doing, and check if any single worker is stealing all the server's resources. 

fg and bg - use fg at your normal terminal prompt to pull a paused or background program back to your screen, and use bg to push a paused task to run quietly behind the scenes so you get your prompt back.kill <PID> and killall - use kill <PID> to safely stop one specific program using its unique tracking number, or use killall like a grenade to instantly wipe out every_
