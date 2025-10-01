# Processing and Jobs

## 1. Listing Processes
In this level, I have once again renamed /challenge/run to a random filename, and this time made it so that you cannot ls the /challenge directory! But I also launched it, so you can find it in the running process list, figure out the filename, and relaunch it directly for the flag! Good luck!

### Solve
**Flag:** `pwn.college{AmOn26Kk7JMtese4a8O8ekpvAcR.QX4MDO0wiMxITNxEzW}`
**Flag:** 

did the ps -ef command to see running processes  -e to list "every" process and -f for a "full format" output and run the renamed run

```bash
hacker@processes~listing-processes:~$ ps -ef
UID          PID    PPID  C STIME TTY          TIME CMD
root           1       0  0 20:15 ?        00:00:00 /sbin/docker-init -- /nix/var/nix/profiles/dojo-
root           7       1  0 20:15 ?        00:00:00 /run/dojo/bin/sleep 6h
root         132       1  0 20:15 ?        00:00:00 /challenge/23091-run-26680
root         135     132  0 20:15 ?        00:00:00 sleep 6h
hacker       146       1  0 20:15 ?        00:00:00 /nix/store/g0q8n7xfjp7znj41hcgrq893a9m0i474-ttyd
hacker       149       0  0 20:15 pts/0    00:00:00 /nix/store/0nxvi9r5ymdlr2p24rjj9qzyms72zld1-bash
hacker       156     149  0 20:15 pts/0    00:00:00 /run/dojo/bin/bash --login
hacker       165     146  0 20:15 pts/1    00:00:00 /run/dojo/bin/bash --login
hacker       177     156  0 20:47 pts/0    00:00:00 ps -ef
hacker@processes~listing-processes:~$ /challenge/23091-run-26680
Yahaha, you found me! Here is your flag:
pwn.college{AmOn26Kk7JMtese4a8O8ekpvAcR.QX4MDO0wiMxITNxEzW}
```

### New Learnings
ps -ef

## 2. Killing Proccess
it's time to terminate your first process! In this challenge, /challenge/run will refuse to run while /challenge/dont_run is running! You must find the dont_run process and kill it. If you fail, pwn.college will disavow all knowledge of your mission. Good luck.

### Solve
**Flag:** `pwn.college{c00f3cCc8N9fNJzcFUpWjgUNn6C.QXyQDO0wiMxITNxEzW}`

did a ps -ef to see every process used kill command after finding the PID of process that was dont run and killed it then got the flag

```bash
hacker@processes~killing-processes:~$ ps -ef
UID          PID    PPID  C STIME TTY          TIME CMD
root           1       0  0 20:50 ?        00:00:00 /sbin/docker-init -- /nix/var/nix/profiles/dojo-
root           7       1  0 20:50 ?        00:00:00 /run/dojo/bin/sleep 6h
root         135       1  0 20:50 ?        00:00:00 su -c /challenge/.launcher hacker
hacker       136     135  0 20:50 ?        00:00:00 /challenge/dont_run
hacker       137     136  0 20:50 ?        00:00:00 sleep 6h
hacker       139       0  0 20:50 pts/0    00:00:00 /nix/store/0nxvi9r5ymdlr2p24rjj9qzyms72zld1-bash
hacker       145     139  0 20:50 pts/0    00:00:00 /run/dojo/bin/bash --login
hacker       163       1  0 20:50 ?        00:00:00 /nix/store/g0q8n7xfjp7znj41hcgrq893a9m0i474-ttyd
hacker       167     163  0 20:50 pts/1    00:00:00 /run/dojo/bin/bash --login
hacker       177     145  0 20:55 pts/0    00:00:00 ps -ef
hacker@processes~killing-processes:~$ kill 136
hacker@processes~killing-processes:~$ /challenge/run
Great job! Here is your payment:
pwn.college{c00f3cCc8N9fNJzcFUpWjgUNn6C.QXyQDO0wiMxITNxEzW}
```

### New Learnings
kill command 

## 3. Interrupting Processes
/challenge/run will refuse to give you the flag until you interrupt it. Good luck!

### Solve
**Flag:** `pwn.college{IX7DCyfpnwM9pmt_9XIOT6PYFu2.QXzQDO0wiMxITNxEzW}`

The /challenge/run was running a process and i had to exit it out vy using crtl + C

```bash
hacker@processes~interrupting-processes:~$ /challenge/run
I could give you the flag... but I won't, until this process exits. Remember, 
you can force me to exit with Ctrl-C. Try it now!
^C
Good job! You have used Ctrl-C to interrupt this process! Here is your flag:
pwn.college{IX7DCyfpnwM9pmt_9XIOT6PYFu2.QXzQDO0wiMxITNxEzW}
```

### New Learnings
Quitting process

## 4. Kill Misbehaving Processes
Your general workflow should be:

1. Check what processes are running.
2. Find /challenge/decoy in the list and figure out its process ID.
3. kill it.
4. Run /challenge/run to get the flag without being overwhelmed by decoys (you don't need to redirect its output; it'll write to the FIFO on its own).

### Solve
**Flag:** `pwn.college{AMzyfeXrFirD7Doi1pxSvOkkRAn.0lNxEzNxwiMxITNxEzW}`

just like the kill process challenge I killed the decoy file running process and then did cat flag_fifo. A lot of decoys got printed but got the flag

```bash
hacker@processes~killing-misbehaving-processes:~$ ps -ef
UID          PID    PPID  C STIME TTY          TIME CMD
root           1       0  0 21:32 ?        00:00:00 /sbin/docker-init -- /nix/var/nix/profiles/dojo-
root           7       1  0 21:32 ?        00:00:00 /run/dojo/bin/sleep 6h
root         137       1  0 21:32 ?        00:00:00 /bin/bash /challenge/.init
root         138       1  0 21:32 ?        00:00:00 /bin/bash /challenge/.init
root         139       1  0 21:32 ?        00:00:00 su -c exec /challenge/decoy > /tmp/flag_fifo hac
root         140     137  0 21:32 ?        00:00:00 sleep 6h
root         141     138  0 21:32 ?        00:00:00 sleep 6h
hacker       142     139  0 21:32 ?        00:00:00 /usr/bin/python /challenge/decoy
hacker       144       0  0 21:32 pts/0    00:00:00 /nix/store/0nxvi9r5ymdlr2p24rjj9qzyms72zld1-bash
hacker       150     144  0 21:32 pts/0    00:00:00 /run/dojo/bin/bash --login
hacker       168       1  0 21:32 ?        00:00:00 /nix/store/g0q8n7xfjp7znj41hcgrq893a9m0i474-ttyd
hacker       172     168  0 21:32 pts/1    00:00:00 /run/dojo/bin/bash --login
hacker       182     150  0 21:32 pts/0    00:00:00 ps -ef
hacker@processes~killing-misbehaving-processes:~$ kill 142
hacker@processes~killing-misbehaving-processes:~$ /challenge/run
Sending the flag to /tmp/flag_fifo!

hacker@processes~killing-misbehaving-processes:~$ /challenge/run
Sending the flag to /tmp/flag_fifo!

cat /tmp/flag_fifo
decoys...
hacker@processes~killing-misbehaving-processes:~$ /challenge/run
Sending the flag to /tmp/flag_fifo!
pwn.college{YrSoIBX2IAGv8aBdC_00fWcJDIu.0FNzMDOxwiMxITNxEzW}

```

### New Learnings
Killing files extended

## 5.  Suspending processes
This level's run wants to see another copy of itself running and using the same terminal. How? Use the terminal to launch it, then suspend it, then launch another copy while the first is suspended!

### Solve
**Flag:** `pwn.college{ccYutf5L_Cg36Oo3TnAugnKY4bn.QX1QDO0wiMxITNxEzW}`

Did the command mentioned in the decription, pressed Crtl+Z to suspend the process and hence got the flag

```bash
hacker@processes~suspending-processes:~$ /challenge/run
I'll only give you the flag if there's already another copy of me running in 
this terminal... Let's check!

UID          PID    PPID  C STIME TTY          TIME CMD
root         162     138  0 21:39 pts/0    00:00:00 bash /challenge/run
root         164     162  0 21:39 pts/0    00:00:00 ps -f

I don't see a second me!

To pass this level, you need to suspend me and launch me again! You can 
background me with Ctrl-Z or, if you're not ready to do that for whatever 
reason, just hit Enter and I'll exit!
^Z
[1]+  Stopped                 /challenge/run
hacker@processes~suspending-processes:~$ /challenge/run
I'll only give you the flag if there's already another copy of me running in 
this terminal... Let's check!

UID          PID    PPID  C STIME TTY          TIME CMD
root         162     138  0 21:39 pts/0    00:00:00 bash /challenge/run
root         169     138  0 21:39 pts/0    00:00:00 bash /challenge/run
root         171     169  0 21:39 pts/0    00:00:00 ps -f

Yay, I found another version of me! Here is the flag:
pwn.college{ccYutf5L_Cg36Oo3TnAugnKY4bn.QX1QDO0wiMxITNxEzW}
```

### New Learnings
Suspending a process

## 6. Resuming Proccesses

Go try it out! This challenge's run needs you to suspend it, then resume it. Good luck!

### Solve
**Flag:** `pwn.college{8MuxKj8jqZ5JbjyV9csuVGwXeIw.QX2QDO0wiMxITNxEzW}`

resumed the process by using the fg (foreground) command

```bash
hacker@processes~resuming-processes:~$ /challenge/run
Let's practice resuming processes! Suspend me with Ctrl-Z, then resume me with 
the 'fg' command! Or just press Enter to quit me!
^Z
[1]+  Stopped                 /challenge/run
hacker@processes~resuming-processes:~$ fg
/challenge/run
I'm back! Here's your flag:
pwn.college{8MuxKj8jqZ5JbjyV9csuVGwXeIw.QX2QDO0wiMxITNxEzW}
Don't forget to press Enter to quit me!

Goodbye!
```

### New Learnings
fg or the foreground command

## 7. Background Proccesses

Go try it out! This challenge's run needs you to suspend it, then resume it. Good luck!

### Solve
**Flag:** `pwn.college{QF1O_mTmZ2HkamhQ8FU_ipUXga0.QX3QDO0wiMxITNxEzW}`

I ran the /challenge/run process and suspeneded it by crtl+Z and agian backgrounded it by doing the bg command which gave me the flag by running the process again

```bash
hacker@processes~backgrounding-processes:~$ /challenge/run
I'll only give you the flag if there's already another copy of me running *and 
not suspended* in this terminal... Let's check!

UID          PID STAT CMD
root         185 S+   bash /challenge/run
root         187 R+   ps -o user=UID,pid,stat,cmd

I don't see a second me!

To pass this level, you need to suspend me, resume the suspended process in the 
background, and then launch a new version of me! You can background me with 
Ctrl-Z (and resume me in the background with 'bg') or, if you're not ready to 
do that for whatever reason, just hit Enter and I'll exit!
^Z
[1]+  Stopped                 /challenge/run
hacker@processes~backgrounding-processes:~$ bg
[1]+ /challenge/run &
hacker@processes~backgrounding-processes:~$ 


Yay, I'm now running the background! Because of that, this text will probably 
overlap weirdly with the shell prompt. Don't panic; just hit Enter a few times 
to scroll this text out.

hacker@processes~backgrounding-processes:~$ /challenge/run
I'll only give you the flag if there's already another copy of me running *and 
not suspended* in this terminal... Let's check!

UID          PID STAT CMD
root         185 S    bash /challenge/run
root         195 S    sleep 6h
root         196 S+   bash /challenge/run
root         198 R+   ps -o user=UID,pid,stat,cmd

Yay, I found another version of me running in the background! Here is the flag:
pwn.college{QF1O_mTmZ2HkamhQ8FU_ipUXga0.QX3QDO0wiMxITNxEzW}

```

### New Learnings
bg background command


## 8. Foreground Proccesses

Imagine that you have a backgrounded process, and you want to mess with it some more. What do you do? Well, you can foreground a backgrounded process with fg just like you foreground a suspended process! This level will walk you through that!

### Solve
**Flag:** `pwn.college{oaKgWOHsVUOzTVY24PgFi5ducUM.QX4QDO0wiMxITNxEzW}`

I backgrounded the process then i foregorunded it (bg then fg) and hence got the output

```bash
hacker@processes~foregrounding-processes:~$ /challenge/run
To pass this level, you need to suspend me, resume the suspended process in the 
background, and *then* foreground it without re-suspending it! You can 
background me with Ctrl-Z (and resume me in the background with 'bg') or, if 
you're not ready to do that for whatever reason, just hit Enter and I'll exit!
^Z
[1]+  Stopped                 /challenge/run
hacker@processes~foregrounding-processes:~$ bg
[1]+ /challenge/run &
hacker@processes~foregrounding-processes:~$ 


Yay, I'm now running the background! Because of that, this text will probably 
overlap weirdly with the shell prompt. Don't panic; just hit Enter a few times 
to scroll this text out. After that, resume me into the foreground with 'fg'; 
I'll wait.
fg
/challenge/run
YES! Great job! I'm now running in the foreground. Hit Enter for your flag!

pwn.college{oaKgWOHsVUOzTVY24PgFi5ducUM.QX4QDO0wiMxITNxEzW}
```

### New Learnings
You can foreground a background process

## 9. Starting Backgrounded Processes

Here, sleep is actively running in the background, not suspended. Now it's your turn to practice! Launch /challenge/run backgrounded for the flag!
### Solve
**Flag:** `pwn.college{Ik05jef2vrEODvkrFqo6mOtmWZe.QX5QDO0wiMxITNxEzW}`

Used the & to start the process backgrounded (/challenge/run being the process)

```bash
hacker@processes~starting-backgrounded-processes:~$ /challenge/run &
[1] 176
hacker@processes~starting-backgrounded-processes:~$ 


Yay, you started me in the background! Because of that, this text will probably 
overlap weirdly with the shell prompt, but you're used to that by now...

Anyways! Here is your flag!
pwn.college{Ik05jef2vrEODvkrFqo6mOtmWZe.QX5QDO0wiMxITNxEzW}
```

### New Learnings
Starting a process backgrounded


## 10. Process Exit codes

In this challenge, you must retrieve the exit code returned by /challenge/get-code and then run /challenge/submit-code with that error code as an argument. Good luck!

### Solve
**Flag:** `pwn.college{41Lx0xTGs0PuMwkIGlNl4V8KzIt.QX5YDO1wiMxITNxEzW}`

typed out /challenge/get-code to exit with the error code did echo $? to find the PID using variable of the exit code and then did PID in front of submit code

```bash
hacker@processes~process-exit-codes:~$ /challenge/get-code
Exiting with an error code!
hacker@processes~process-exit-codes:~$ echo $?
159
hacker@processes~process-exit-codes:~$ /challenge/submit-code 159
CORRECT! Here is your flag:
pwn.college{41Lx0xTGs0PuMwkIGlNl4V8KzIt.QX5YDO1wiMxITNxEzW}
```

### New Learnings
getting the error code
