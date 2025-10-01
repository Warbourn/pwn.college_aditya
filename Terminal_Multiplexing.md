# Terminal Multiplexing

## 1. Launching Screen
That's it! You're now inside a screen session. It looks exactly like a terminal, but there are new capabilities there, waiting to be discovered.

For this challenge, we've hooked things up so that just launching screen will get you the flag. Easy!

### Solve
**Flag:** `pwn.college{MRod1Ug3DUobySh_0JIY2bgBjXl.0VN4IDOxwiMxITNxEzW}`

screen started the screen and took me inside it

```bash
hacker@terminal-multiplexing~launching-screen:~$ screen
screen - 

Congratulations! You're inside a screen session!
Here's your flag:
pwn.college{MRod1Ug3DUobySh_0JIY2bgBjXl.0VN4IDOxwiMxITNxEzW}

[screen is terminating]
```

### New Learnings
screen command


## 2. Detaching and Attaching
For this challenge, you'll need to:

Launch screen
Detach from it.
Run /challenge/run (this will secretly send the flag to your detached session!)
Reattach to see your prize

### Solve
**Flag:** `pwn.college{IFiwIccCzO0LLJY-jp26optXkgr.0lN4IDOxwiMxITNxEzW}`

type in your solve and your thought process behind solving the challenge. Include as much as info as possible. Use triple ticks for any bash commands and output you type on the terminal.

```bash
hacker@terminal-multiplexing~detaching-and-attaching:~$ screen
[detached from 162.pts-0.terminal-multiplexing~detaching-and-attaching]
hacker@terminal-multiplexing~detaching-and-attaching:~$ /challenge/run
Found detached screen session: 162.pts-0.terminal-multiplexing~detaching-and-attaching
Sending flag to your screen session...

Flag sent! Now reattach to your screen session with:

  screen -r

You'll find the flag waiting for you there!
hacker@terminal-multiplexing~detaching-and-attaching:~$ screen -r
hacker@terminal-multiplexing~detaching-and-attaching:~$
hacker@terminal-multiplexing~detaching-and-attaching:~$ echo Yes! Flag is: pwn.college{IFiwIccCzO0LLJY-jp26optXkgr.0lN4IDOxwiMxITNxEzW}
Yes! Flag is: pwn.college{IFiwIccCzO0LLJY-jp26optXkgr.0lN4IDOxwiMxITNxEzW}
```

### New Learnings
&& is the and operator.

### References 
Add any references or videos you used while solving the challenge.

## 3. Finding Sessions
In this challenge, we've created three screen sessions for you. One of them contains the flag. The other two are decoys!

You'll need to check each one until you find it. Don't forget to detach (Ctrl-A d) before trying the next session!

### Solve
**Flag:** `pwn.college{4B1ydTHWwNqPgwzsYkzgNFnEE7A.01N4IDOxwiMxITNxEzW}`

type in your solve and your thought process behind solving the challenge. Include as much as info as possible. Use triple ticks for any bash commands and output you type on the terminal.

```bash
hacker@terminal-multiplexing~finding-sessions:~$ screen -ls
There are screens on:
	162.pts-0.terminal-multiplexing~detaching-and-attaching	(Remote or dead)
	144.session_e2902c1337e45c5c	(Detached)
	147.session_3af21194e690c8d7	(Detached)
	150.session_48a76e537154d468	(Detached)
4 Sockets in /home/hacker/.screen.
hacker@terminal-multiplexing~finding-sessions:~$ screen -r 150.session_48a76e537154d468
[detached from 150.session_48a76e537154d468]
hacker@terminal-multiplexing~finding-sessions:~$ screen -r 147.session_3af21194e690c8d7 (Detached)
bash: syntax error near unexpected token `('
hacker@terminal-multiplexing~finding-sessions:~$ screen -r 147.session_3af21194e690c8d7 (Detached
bash: syntax error near unexpected token `('
hacker@terminal-multiplexing~finding-sessions:~$ screen -r 147.session_3af21194e690c8d7 
[detached from 147.session_3af21194e690c8d7]
hacker@terminal-multiplexing~finding-sessions:~$ screen -r 144.session_e2902c1337e45c5c
[detached from 144.session_e2902c1337e45c5c]

hacker@terminal-multiplexing~finding-sessions:~$  echo 'Congratulations! You found the right session!'
Congratulations! You found the right session!
hacker@terminal-multiplexing~finding-sessions:~$  echo pwn.college{4B1ydTHWwNqPgwzsYkzgNFnEE7A.01N4IDOxwiMxITNxEzW}
pwn.college{4B1ydTHWwNqPgwzsYkzgNFnEE7A.01N4IDOxwiMxITNxEzW}
hacker@terminal-multiplexing~finding-sessions:~$
```

### New Learnings
|| is the if operator.

### References 
Add any references or videos you used while solving the challenge.

## 4. Switching Windows
For this challenge, we've set up a screen session with two windows:

- Window 0 has... well, you'll have to switch there to find out!
- Window 1 has a welcome message

Attach to the session with screen -r, then use one of the key combinations above to switch to Window 1. Go get that flag!

### Solve
**Flag:** `pwn.college{I4B44CSVzPiQ7hqlX86lue-cBkc.0FO4IDOxwiMxITNxEzW}`

type in your solve and your thought process behind solving the challenge. Include as much as info as possible. Use triple ticks for any bash commands and output you type on the terminal.

```bash
Welcome to the window switching challenge!
You are currently in window 1.
The flag is hidden in window 0.
Use Ctrl-A 0 to switch to window 0!
hacker@terminal-multiplexing~switching-
hacker@terminal-multiplexing~switching-windows:~$  cat <<MSG
> Excellent work! You found window 0!
> Here is your flag: pwn.college{I4B44CSVzPiQ7hqlX86lue-cBkc.0FO4IDOxwiMxITNxEzW}
> MSG
Excellent work! You found window 0!
Here is your flag: pwn.college{I4B44CSVzPiQ7hqlX86lue-cBkc.0FO4IDOxwiMxITNxEzW}
hacker@terminal-multiplexing~switching-windows:~$
```

### New Learnings
nano command

### References 
Add any references or videos you used while solving the challenge.

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


