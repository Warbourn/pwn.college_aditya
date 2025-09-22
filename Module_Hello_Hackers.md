# Hello Hackers

## Intro to commands.
Here, the user executed the whoami command, which simply prints the username (hacker) to the terminal. When the command terminates, the shell once again displays the prompt, ready for the next command.

### Solve
**Flag:** `pwn.college{g7bM_vQZcrI_PViRFmxVKjf8aOk.QX3YjM1wiMxITNxEzW}`

 The description said to type a 'hello' and that linux is case sensitive so, i typed 'hello' and whoami just to make sure that I'm in the right environment.

```bash
hacker@hello~intro-to-commands:~$ whoami
hacker
hacker@hello~intro-to-commands:~$ hello
Success! Here is your flag:
pwn.college{g7bM_vQZcrI_PViRFmxVKjf8aOk.QX3YjM1wiMxITNxEzW}
```

### New Learnings
single command results

### References 
None


## Intro to Arguments
Let's try something more complicated: a command with arguments, which is what we call additional data passed to the command. When you type a line of text and hit enter, the shell actually parses your input into a command and its arguments. The first word is the command, and the subsequent words are arguments.

### Solve
**Flag:** `pwn.college{s2MhvcQHIeNN15F6fq4eTkKACUn.QX4YjM1wiMxITNxEzW}`

In this case, the command was echo, and the argument was Hello. echo is a simple command that "echoes" all of its arguments back out onto the terminal. But for the flag, simply hello with the argument hackers needed to be typed, hence hello hackers

```bash
hacker@hello~intro-to-arguments:~$ echo hello hackers 
hello hackers
hacker@hello~intro-to-arguments:~$ hello hackers 
Success! Here is your flag:
pwn.college{s2MhvcQHIeNN15F6fq4eTkKACUn.QX4YjM1wiMxITNxEzW}
```

### New Learnings
Arguments and Echos.

### References 
None

## Command History
You're going to type a lot of commands, and typing everything from scratch can be annoying. Luckily, the shell saves a history of every command you invoke.

You can scroll through those saved commands with the up/down arrow keys, and we'll practice that in this challenge. This challenge will inject the flag into your history. Bring up a terminal, hit the up arrow, and grab it! In other challenges, the history will contain the log of the commands you've run, so if you need to run a similar command again, you can use the arrow keys to scroll through and find it!

### Solve
**Flag:** `pwn.college{kjWMiHw5Bk28C6u0Pkpvmjmsj_u.0lNzEzNxwiMxITNxEzW}`

Just the up arrow key worked fine. The pwn.college injected the flag into my computer.

```bash
hacker@hello~command-history:~$ the flag is pwn.college{kjWMiHw5Bk28C6u0Pkpvmjmsj_u.0lNzEzNxwiMxITNxEzW}
```

### New Learnings
Command History that stores each command you type in your terminal

### References 
None.
