
# Chaining Commands

## 1. Chaining with semi colons
But THIS challenge (and only this challenge) does have a root password. That password is hack-the-planet, and you must provide it to su to become root! Go do that, and read the flag!

### Solve
**Flag:** `pwn.college{4oKSea2pMgLzPoyA5WA6ltRXsTk.QX1UDO0wiMxITNxEzW}`
a
type in your solve and your thought process behind solving the challenge. Include as much as info as possible. Use triple ticks for any bash commands and output you type on the terminal.

```bash
hacker@chaining~chaining-with-semicolons:~$ /challenge/pwn ; /challenge/college
Yes! You chained /challenge/pwn and /challenge/college! Here is your flag:
pwn.college{4oKSea2pMgLzPoyA5WA6ltRXsTk.QX1UDO0wiMxITNxEzW}
```

### New Learnings
Brief note on what you learned from the challenge

### References 
Add any references or videos you used while solving the challenge.

## 2. Building on success
In this challenge, you need to chain the programs /challenge/first-success and /challenge/second using the && operator. Try running each command separately first to see what happens (which is that you will not get the flag). But if you chain them with &&, the flag will appear!

### Solve
**Flag:** `pwn.college{YITq1zn7dkz-SJUcDJ7-RQ4tIQb.0lM0MDOxwiMxITNxEzW}`

type in your solve and your thought process behind solving the challenge. Include as much as info as possible. Use triple ticks for any bash commands and output you type on the terminal.

```bash
hacker@chaining~building-on-success:~$ /challenge/first-success && /challenge/second
Nice chaining! Flag: pwn.college{YITq1zn7dkz-SJUcDJ7-RQ4tIQb.0lM0MDOxwiMxITNxEzW}
```

### New Learnings
&& is the and operator.

### References 
Add any references or videos you used while solving the challenge.

## 3. Handling Failure
In this challenge, you need to chain /challenge/first-failure and /challenge/second using the || operator. Go for it!

### Solve
**Flag:** ` pwn.college{09xKpZD5KmI55iObWFejUmVO0Gj.01M0MDOxwiMxITNxEzW}`

type in your solve and your thought process behind solving the challenge. Include as much as info as possible. Use triple ticks for any bash commands and output you type on the terminal.

```bash
hacker@chaining~handling-failure:~$ /challenge/first-failure || /challenge/second
Nice chaining! Flag: pwn.college{09xKpZD5KmI55iObWFejUmVO0Gj.01M0MDOxwiMxITNxEzW}

```

### New Learnings
|| is the if operator.

### References 
Add any references or videos you used while solving the challenge.

- your first shell script

## 4. Redirecting Script Output
In this level, we will practice piping (|) from your script to another program. Like before, you need to create a script that calls the /challenge/pwn command followed by the /challenge/college command, and pipe the output of the script into a single invocation of the /challenge/solve command!

### Solve
**Flag:** `pwn.college{ERjBfxoNQ17WezHssYxdywcrsEq.QX4ETO0wiMxITNxEzW}`

type in your solve and your thought process behind solving the challenge. Include as much as info as possible. Use triple ticks for any bash commands and output you type on the terminal.

```bash 
hacker@chaining~redirecting-script-output:~$ nano script.sh
hacker@chaining~redirecting-script-output:~$ bash script.sh | /challenge/solve
Correct! Here is your flag:
pwn.college{ERjBfxoNQ17WezHssYxdywcrsEq.QX4ETO0wiMxITNxEzW}
```

### New Learnings
nano command

### References 
Add any references or videos you used while solving the challenge.

## 5. Executable Shell Scripts
Make a shellscript that will invoke /challenge/solve, make it executable, and run it without explicitly invoking bash!

### Solve
**Flag:** `pwn.college{YcLVWUycmEKNeYj3_GX6qlvVU8k.QX0cjM1wiMxITNxEzW}`

type in your solve and your thought process behind solving the challenge. Include as much as info as possible. Use triple ticks for any bash commands and output you type on the terminal.

```bash
hacker@chaining~executable-shell-scripts:~$ touch minor.sh
hacker@chaining~executable-shell-scripts:~$ nano minor.sh
acker@chaining~executable-shell-scripts:~$ chmod +x minor.sh
hacker@chaining~executable-shell-scripts:~$ ./minor.sh
Congratulations on your shell script execution! Your flag:
pwn.college{YcLVWUycmEKNeYj3_GX6qlvVU8k.QX0cjM1wiMxITNxEzW}
```

### New Learnings
nano command

### References 
Add any references or videos you used while solving the challenge.

## 6. Understanding Shebangs
create a script at /home/hacker/solve.sh that has a proper shebang and outputs "hack the planet". Remember to make it executable, then run /challenge/run to verify your script works correctly!



### Solve
**Flag:** `pwn.college{YcLVWUycmEKNeYj3_GX6qlvVU8k.QX0cjM1wiMxITNxEzW}`

type in your solve and your thought process behind solving the challenge. Include as much as info as possible. Use triple ticks for any bash commands and output you type on the terminal.

```bash
hacker@chaining~understanding-shebangs:~$ touch solve.sh
hacker@chaining~understanding-shebangs:~$ nano solve.sh
hacker@chaining~understanding-shebangs:~$ nano solve.sh
hacker@chaining~understanding-shebangs:~$ chmod a+x /home/hacker/solve.sh
hacker@chaining~understanding-shebangs:~$ /challenge/run
Testing your script...
Perfect! Your flag:
Flag: pwn.college{UGLXaUEuGFC4K6QMez7g3r_kAyG.0VOzMDOxwiMxITNxEzW}
```

### New Learnings
nano command

### References 
[Add any references or videos you used while solving the challenge.](https://www.youtube.com/watch?v=LTuuMtQR1uQ&t=187s)

## 7. Scripting with Arguments
create a script at /home/hacker/solve.sh that has a proper shebang and outputs "hack the planet". Remember to make it executable, then run /challenge/run to verify your script works correctly!

### Solve
**Flag:** `pwn.college{Ue4toLW_okWD9c9RmTayYnIuYok.0VNzMDOxwiMxITNxEzW}`

type in your solve and your thought process behind solving the challenge. Include as much as info as possible. Use triple ticks for any bash commands and output you type on the terminal.

```bash
hacker@chaining~scripting-with-arguments:~$ nano solve.sh

inside solve.sh
#!/bin/bash

echo "$2 $1"
hacker@chaining~scripting-with-arguments:~$ /challenge/run
Correct! Your script properly reversed the arguments.
Here's your flag:
pwn.college{Ue4toLW_okWD9c9RmTayYnIuYok.0VNzMDOxwiMxITNxEzW}
```

### New Learnings
nano command

### References 
[Add any references or videos you used while solving the challenge.](https://www.youtube.com/watch?v=LTuuMtQR1uQ&t=187s)

## 8. Scripting with Conditionals
For this challenge, write a script at /home/hacker/solve.sh that:

- Takes one argument
- If the argument is "pwn", output "college"
- For any other input, output nothing
Once your script works correctly, run /challenge/run to get your flag!
### Solve
**Flag:** `pwn.college{EP0JoBcAftc2JL8Tk8vDJo9OPB2.0lNzMDOxwiMxITNxEzW}`

type in your solve and your thought process behind solving the challenge. Include as much as info as possible. Use triple ticks for any bash commands and output you type on the terminal.

```bash
hacker@chaining~scripting-with-conditionals:~$ nano solve.sh
solve.sh --
#!/bin/sh


if [ "$1" = "pwn" ]; then
  printf '%s\n' "college"
fi

hacker@chaining~scripting-with-conditionals:~$ bash /home/hacker/solve.sh pwn
college
hacker@chaining~scripting-with-conditionals:~$ /challenge/run
Correct! Your script properly handles all the conditions.
Here's your flag:
pwn.college{EP0JoBcAftc2JL8Tk8vDJo9OPB2.0lNzMDOxwiMxITNxEzW}
```

### New Learnings
nano command

### References 
Add any references or videos you used while solving the challenge.

## 9. Scripting with deafault cases
For this challenge, write a script at /home/hacker/solve.sh that:

- Takes one argument
- If the argument is "pwn", output "college"
- For any other input, output "nope"
### Solve
**Flag:** `pwn.college{gdX_XPZQns02mZzC6sOjec6971m.01NzMDOxwiMxITNxEzW}`

type in your solve and your thought process behind solving the challenge. Include as much as info as possible. Use triple ticks for any bash commands and output you type on the terminal.

```bash
hacker@chaining~scripting-with-default-cases:~$ nano solve.sh
solve.sh -- 
#!/bin/sh


if [ "$1" = "pwn" ]; then
  echo  "college"
else
  echo "nope"
fi
hacker@chaining~scripting-with-default-cases:~$ bash solve.sh pwn
college
hacker@chaining~scripting-with-default-cases:~$ bash solve.sh hack
nope
hacker@chaining~scripting-with-default-cases:~$ /challenge/run
Correct! Your script properly handles the if/else conditions.
Here's your flag:
pwn.college{gdX_XPZQns02mZzC6sOjec6971m.01NzMDOxwiMxITNxEzW}
```

### New Learnings
nano command

### References 
Add any references or videos you used while solving the challenge.

## 10. Executable Shell Scripts
For this challenge, write a script at /home/hacker/solve.sh that:

- Takes one argument
- If the argument is "hack", output "the planet"
- If the argument is "pwn", output "college"
- If the argument is "learn", output "linux"
- For any other input, output "unknown"

### Solve
**Flag:** `pwn.college{QcyLuLu8PaYxntr9rLzUh8sfWsl.0FOzMDOxwiMxITNxEzW}`

type in your solve and your thought process behind solving the challenge. Include as much as info as possible. Use triple ticks for any bash commands and output you type on the terminal.

```bash
hacker@chaining~scripting-with-multiple-conditions:~$ nano solve.sh
solve.sh -- 
#!/bin/sh


if [ "$1" = "hack" ]
then
  echo  "the planet"
elif [ "$1" = "pwn" ]
 then
  echo "college"
elif [ "$1" = "learn" ];
then
  echo "linux"
else
  echo "unknown"
fi
hacker@chaining~scripting-with-multiple-conditions:~$ /challenge/run
Correct! Your script properly handles all the conditions with elif.
Here's your flag:
pwn.college{QcyLuLu8PaYxntr9rLzUh8sfWsl.0FOzMDOxwiMxITNxEzW}
```

### New Learnings
nano command

### References 
Add any references or videos you used while solving the challenge.

## 11. Executable Shell Scripts
Make a shellscript that will invoke /challenge/solve, make it executable, and run it without explicitly invoking bash!

### Solve
**Flag:** `pwn.college{YcLVWUycmEKNeYj3_GX6qlvVU8k.QX0cjM1wiMxITNxEzW}`

type in your solve and your thought process behind solving the challenge. Include as much as info as possible. Use triple ticks for any bash commands and output you type on the terminal.

```bash
hacker@chaining~executable-shell-scripts:~$ touch minor.sh
hacker@chaining~executable-shell-scripts:~$ nano minor.sh
acker@chaining~executable-shell-scripts:~$ chmod +x minor.sh
hacker@chaining~executable-shell-scripts:~$ ./minor.sh
Congratulations on your shell script execution! Your flag:
pwn.college{YcLVWUycmEKNeYj3_GX6qlvVU8k.QX0cjM1wiMxITNxEzW}
```

### New Learnings
nano command

### References 
Add any references or videos you used while solving the challenge.


## 12. Reading Shell Scripts
Make a shellscript that will invoke /challenge/solve, make it executable, and run it without explicitly invoking bash!

### Solve
**Flag:** `pwn.college{84YyjiYRc6H9EcgETksHk3LNO8D.0lMwgDOxwiMxITNxEzW}`

type in your solve and your thought process behind solving the challenge. Include as much as info as possible. Use triple ticks for any bash commands and output you type on the terminal.

```bash
hacker@chaining~reading-shell-scripts:~$ cat /challenge/run
#!/opt/pwn.college/bash

read GUESS
if [ "$GUESS" == "hack the PLANET" ]
then
	echo "CORRECT! Your flag:"
	cat /flag
else
	echo "Read the /challenge/run file to figure out the correct password!"
fi
hacker@chaining~reading-shell-scripts:~$ cat /flag
cat: /flag: Permission denied
hacker@chaining~reading-shell-scripts:~$ cat /flag
cat: /flag: Permission denied
hacker@chaining~reading-shell-scripts:~$ /challenge/run
hack the PLANET
CORRECT! Your flag:
pwn.college{84YyjiYRc6H9EcgETksHk3LNO8D.0lMwgDOxwiMxITNxEzW}
```

### New Learnings
nano command

### References 
Add any references or videos you used while solving the challenge.

