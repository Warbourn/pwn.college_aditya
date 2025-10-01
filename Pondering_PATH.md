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

type in your solve and your thought process behind solving the challenge. Include as much as info as possible. Use triple ticks for any bash commands and output you type on the terminal.

```bash
hacker@path~adding-commands:~$ PATH=$PATH:~/bin
hacker@path~adding-commands:~/bin$ nano win
inside win -
/bin/cat
hacker@path~adding-commands:~/bin$ /challenge/run
Invoking 'win'....
challenge didn't go past invoking win...
```

### New Learnings
nano command

### References 
(https://www.youtube.com/watch?v=hk0RwVC6uts&t=803s)

## 5. Detaching and Attaching (tmux)
For this challenge:

1. Launch tmux
2. Detach from it.
3. Run /challenge/run (this will send the flag to your detached session!)
4. Reattach to see your prize

### Solve
**Flag:** `pwn.college{UBWGBd8SaBkAoWwL_eAkl-3uu71.0VO4IDOxwiMxITNxEzW}`

type in your solve and your thought process behind solving the challenge. Include as much as info as possible. Use triple ticks for any bash commands and output you type on the terminal.

```bash
hacker@terminal-multiplexing~detaching-and-attaching-tmux:~$ tmux
[detached (from session 0)]
hacker@terminal-multiplexing~detaching-and-attaching-tmux:~$ /challenge/run
Found detached tmux session: 0
Sending flag to your tmux session...

Flag sent! Now reattach to your tmux session with:
  tmux attach

You'll find the flag waiting for you there!
hacker@terminal-multiplexing~detaching-and-attaching-tmux:~$ tmux -r
tmux: unknown option -- r
usage: tmux [-2CDlNuVv] [-c shell-command] [-f file] [-L socket-name]
            [-S socket-path] [-T features] [command [flags]]
hacker@terminal-multiplexing~detaching-and-attaching-tmux:~$ tmux a
[detached (from session 0)]
hacker@terminal-multiplexing~detaching-and-attaching-tmux:~$  echo Congratulations, here is your flag: pwn.college{UBWGBd8SaBkAoWwL_eAkl-3uu71.0VO4IDOxwiMxITNxEzW}
Congratulations, here is your flag: pwn.college{UBWGBd8SaBkAoWwL_eAkl-3uu71.0VO4IDOxwiMxITNxEzW}
```

### New Learnings
nano command

### References 
Add any references or videos you used while solving the challenge.

## 6. Switching Windows (tmux)
That's it! You're now inside a screen session. It looks exactly like a terminal, but there are new capabilities there, waiting to be discovered.

For this challenge, we've hooked things up so that just launching screen will get you the flag. Easy!

### Solve
**Flag:** `pwn.college{MRod1Ug3DUobySh_0JIY2bgBjXl.0VN4IDOxwiMxITNxEzW}`
a
type in your solve and your thought process behind solving the challenge. Include as much as info as possible. Use triple ticks for any bash commands and output you type on the terminal.

```bash
hacker@terminal-multiplexing~switching-windows-tmux:~$  cat <<MSG
> Excellent work! You found window 0!
> Here is your flag: pwn.college{8uTzMTXWy1bauHduuz5J--e4ubD.0FM5IDOxwiMxITNxEzW}
> MSG
Excellent work! You found window 0!
Here is your flag: pwn.college{8uTzMTXWy1bauHduuz5J--e4ubD.0FM5IDOxwiMxITNxEzW}
```

### New Learnings
Brief note on what you learned from the challenge

### References 
Add any references or videos you used while solving the challenge.


