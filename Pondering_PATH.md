# Pondering PATH

## 1. The PATH variable
In this level, you will disrupt the operation of the /challenge/run program. This program will DELETE the flag file using the rm command. However, if it can't find the rm command, the flag will not be deleted, and the challenge will give it to you! Thus, you must make it so that /challenge/run also can't find the rm command!

### Solve
**Flag:** `pwn.college{Y1S79BVjt0qqAeuG5oFaZy0elID.QX2cDM1wiMxITNxEzW}`

type in your solve and your thought process behind solving the challenge. Include as much as info as possible. Use triple ticks for any bash commands and output you type on the terminal.

```bash
hacker@path~the-path-variable:~$ rm 
rm: missing operand
Try 'rm --help' for more information.
hacker@path~the-path-variable:~$ PATH=""
hacker@path~the-path-variable:~$ rm
bash: rm: No such file or directory
hacker@path~the-path-variable:~$ /challenge/run
Trying to remove /flag...
/challenge/run: line 4: rm: No such file or directory
The flag is still there! I might as well give it to you!
pwn.college{Y1S79BVjt0qqAeuG5oFaZy0elID.QX2cDM1wiMxITNxEzW}
hacker@path~the-path-variable:~$ 
```

### New Learnings
Brief note on what you learned from the challenge

### References 
Add any references or videos you used while solving the challenge.

## 2. Setting PATH
Let's practice. This level's /challenge/run will run the win command via its bare name, but this command exists in the /challenge/more_commands/ directory, which is not initially in the PATH. The win command is the only thing that /challenge/run needs, so you can just overwrite PATH with that one directory. Good luck!

### Solve
**Flag:** `pwn.college{QiyuWdCmmG6sOO-StencoGK6M6s.QX1cjM1wiMxITNxEzW}`

type in your solve and your thought process behind solving the challenge. Include as much as info as possible. Use triple ticks for any bash commands and output you type on the terminal.

```bash
hacker@path~setting-path:~$ PATH=/challenge/more_commands
hacker@path~setting-path:~$ win
It looks like 'win' was improperly launched. Don't launch it directly; it MUST 
be launched by /challenge/run!
hacker@path~setting-path:~$ /challenge/run win
Invoking 'win'....
Congratulations! You properly set the flag and 'win' has launched!
pwn.college{QiyuWdCmmG6sOO-StencoGK6M6s.QX1cjM1wiMxITNxEzW}
```

### New Learnings
&& is the and operator.

### References 
Add any references or videos you used while solving the challenge.

## 3. Finding Commands
In this challenge, we added a win command somewhere in your $PATH, but it won't give you the flag. Instead, it's in the same directory as a flag file that we made readable by you! You must find win (with the which command), and cat the flag out of that directory!

You'll need to check each one until you find it. Don't forget to detach (Ctrl-A d) before trying the next session!

### Solve
**Flag:** `pwn.college{A9-VKaLfdJJH4bxAsIMOIG2LH1s.01NzEzNxwiMxITNxEzW}`

type in your solve and your thought process behind solving the challenge. Include as much as info as possible. Use triple ticks for any bash commands and output you type on the terminal.

```bash
hacker@path~finding-commands:~$ which win
/challenge/paths/14592/win
hacker@path~finding-commands:~$ ls /challenge/paths/14592
flag  win
hacker@path~finding-commands:~$ cat /challenge/paths/flag
cat: /challenge/paths/flag: No such file or directory
hacker@path~finding-commands:~$ cat /challenge/paths/14592/flag
pwn.college{A9-VKaLfdJJH4bxAsIMOIG2LH1s.01NzEzNxwiMxITNxEzW}
```

### New Learnings
|| is the if operator.

### References 
Add any references or videos you used while solving the challenge.

## 4. Adding Commands
Previously, the win command that /challenge/run executed was stored in /challenge/more_commands. This time, win does not exist! Recall the final level of Chaining Commands, and make a shell script called win, add its location to the PATH, and enable /challenge/run to find it!

### Solve
**Flag:** `pwn.college{helloworld]`

I added the path of win to the PATH variable and inside win i typed #!bin/bash to let it know it's bash coding, and then i put the location of cat which is /bin/cat /flag, the flag to ofcourse read the flag out
```bash
hacker@path~adding-commands:~$ cd bin
hacker@path~adding-commands:~/bin$ nano win
hacker@path~adding-commands:~/bin$ /challenge/run
Invoking 'win'....
/challenge/run: line 4: win: command not found
It looks like that did not work... Did you set PATH correctly?
hacker@path~adding-commands:~/bin$ PATH=/home/hacker/bin
hacker@path~adding-commands:~/bin$ /challenge/run
Invoking 'win'....
pwn.college{YQ-rJ3gXPndRZ36VcIRCdFmbHeB.QX2cjM1wiMxITNxEzW}
```

### New Learnings
adding a path

### References 
(https://www.youtube.com/watch?v=hk0RwVC6uts&t=803s)

## 5. Hijacking
For this challenge:

1. Launch tmux
2. Detach from it.
3. Run /challenge/run (this will send the flag to your detached session!)
4. Reattach to see your prize

### Solve
**Flag:** `pwn.college{UBWGBd8SaBkAoWwL_eAkl-3uu71.0VO4IDOxwiMxITNxEzW}`

type in your solve and your thought process behind solving the challenge. Include as much as info as possible. Use triple ticks for any bash commands and output you type on the terminal.

```bash
```

### New Learnings
...



