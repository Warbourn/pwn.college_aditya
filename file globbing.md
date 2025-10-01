# File Globbing

## 1. Matching with *
Now, practice this yourself! Starting from your home directory, change your directory to /challenge, but use globbing to keep the argument you pass to cd to at most four characters! Once you're there, run /challenge/run for the flag!

### Solve
**Flag:** `pwn.college{UYVX51vjl71oY8q24CclAls8QKI.QXxIDO0wiMxITNxEzW}`

type in your solve and your thought process behind solving the challenge. Include as much as info as possible. Use triple ticks for any bash commands and output you type on the terminal.

```bash
hacker@globbing~matching-with-:~$ cd /ch*
hacker@globbing~matching-with-:/challenge$ /challenge/run
You ran me with the working directory of /challenge! Here is your flag:
pwn.college{UYVX51vjl71oY8q24CclAls8QKI.QXxIDO0wiMxITNxEzW}
```

### New Learnings
Brief note on what you learned from the challenge

## 2. Matching with ?
Now, practice this yourself! Starting from your home directory, change your directory to /challenge, but use the ? character instead of c and l in the argument to cd! Once you're there, run /challenge/run for the flag!

### Solve
**Flag:** `pwn.college{UYVX51vjl71oY8q24CclAls8QKI.QXxIDO0wiMxITNxEzW}`

type in your solve and your thought process behind solving the challenge. Include as much as info as possible. Use triple ticks for any bash commands and output you type on the terminal.

```bash
hacker@globbing~matching-with-:~$ cd /ch*
hacker@globbing~matching-with-:/challenge$ /challenge/run
You ran me with the working directory of /challenge! Here is your flag:
pwn.college{UYVX51vjl71oY8q24CclAls8QKI.QXxIDO0wiMxITNxEzW}
```

### New Learnings
Brief note on what you learned from the challenge

## 3. Matching with []
We've placed a bunch of files in /challenge/files. Change your working directory to /challenge/files and run /challenge/run with a single argument that bracket-globs into file_b, file_a, file_s, and file_h!

### Solve
**Flag:** `pwn.college{MVBpvVWyqkOar6HUUkvLEEN9YaA.QXzIDO0wiMxITNxEzW}`

type in your solve and your thought process behind solving the challenge. Include as much as info as possible. Use triple ticks for any bash commands and output you type on the terminal.

```bash
hacker@globbing~matching-with-:~$ cd /challenge/file[s]
hacker@globbing~matching-with-:/challenge/files$ echo Look: file_[bash]
Look: file_a file_b file_h file_s
hacker@globbing~matching-with-:/challenge/files$ /challenge/run Look: file_[bash]
Error: you called this command with more than 1 argument (pre-globbing)! Please 
call me with one argument.
hacker@globbing~matching-with-:/challenge/files$ /challenge/run file_[bash]
You got it! Here is your flag!
pwn.college{MVBpvVWyqkOar6HUUkvLEEN9YaA.QXzIDO0wiMxITNxEzW}
```

### New Learnings
Brief note on what you learned from the challenge

## 4. Matching paths with []
Now it's your turn. Once more, we've placed a bunch of files in /challenge/files. Starting from your home directory, run /challenge/run with a single argument that bracket-globs into the absolute paths to the file_b, file_a, file_s, and file_h files!

### Solve
**Flag:** `pwn.college{AvgM0uXMqvKHBANAIfciV72uxd7.QX0IDO0wiMxITNxEzW}`

type in your solve and your thought process behind solving the challenge. Include as much as info as possible. Use triple ticks for any bash commands and output you type on the terminal.

```bash
hacker@globbing~matching-paths-with-:/challenge/files$ /challenge/run /challenge/files/file_[bash]
Error: please run with a working directory of /home/hacker!
hacker@globbing~matching-paths-with-:/challenge/files$ cd ~
hacker@globbing~matching-paths-with-:~$ /challenge/run /challenge/files/file_[bash]
You got it! Here is your flag!
pwn.college{AvgM0uXMqvKHBANAIfciV72uxd7.QX0IDO0wiMxITNxEzW}
hacker@globbing~matching-paths-with-:~$ 

```

### New Learnings
Brief note on what you learned from the challenge

## 5. Multiple globs
Now you try it. We put a few happy, but diversely-named files in /challenge/files. Go cd there and run /challenge/run, providing a single argument: a short (3 characters or less) globbed word with two * globs in it that covers every word that contains the letter p.

### Solve
**Flag:** `pwn.college{AvgM0uXMqvKHBANAIfciV72uxd7.QX0IDO0wiMxITNxEzW}`

type in your solve and your thought process behind solving the challenge. Include as much as info as possible. Use triple ticks for any bash commands and output you type on the terminal.

```bash
hacker@globbing~multiple-globs:~$ cd /challenge/files
hacker@globbing~multiple-globs:/challenge/files$ ls
amazing      fantastic   kind        pwning     uplifting   zesty
beautiful    great       laughing    queenly    victorious
challenging  happy       magical     radiant    wonderful
delightful   incredible  nice        splendid   xenial
educational  jovial      optimistic  thrilling  youthful
hacker@globbing~multiple-globs:/challenge/files$ challenge/run p**
bash: challenge/run: No such file or directory
hacker@globbing~multiple-globs:/challenge/files$ /challenge/run p**
Your expansion did not expand to the requested files (happy optimistic pwning 
splendid uplifting).
Instead, it expanded to:
pwning
hacker@globbing~multiple-globs:/challenge/files$ /challenge/run *p*
You got it! Here is your flag!
pwn.college{IGDcyzrdVqctx_KuTUGldiq9AgA.0lM3kjNxwiMxITNxEzW}
```

### New Learnings
Brief note on what you learned from the challenge

## 6. Mixing globs
Now, let's put the previous levels together! We put a few happy, but diversely-named files in /challenge/files. Go cd there and, using the globbing you've learned, write a single, short (6 characters or less) glob that (when passed as an argument to /challenge/run) will match the files "challenging", "educational", and "pwning"!

### Solve
**Flag:** `pwn.college{glEkyC3xDywx02cGl5mmUW2p9HE.QX1IDO0wiMxITNxEzW}`

type in your solve and your thought process behind solving the challenge. Include as much as info as possible. Use triple ticks for any bash commands and output you type on the terminal.

```bash
hacker@globbing~matching-with-:~$ cd /challenge/files
hacker@globbing~mixing-globs:/challenge/files$ /challenge/run [cep]*
You got it! Here is your flag!
pwn.college{glEkyC3xDywx02cGl5mmUW2p9HE.QX1IDO0wiMxITNxEzW}
```

### New Learnings
Brief note on what you learned from the challenge


## 7. Exclusionary Globbing
go forth to /challenge/files and run /challenge/run with all files that don't start with p, w, or n!

### Solve
**Flag:** `pwn.college{0F3vm9qD1hs51C47P4EqKRQY5rf.QX2IDO0wiMxITNxEzW}`

type in your solve and your thought process behind solving the challenge. Include as much as info as possible. Use triple ticks for any bash commands and output you type on the terminal.

```bash
/challenge/run [^pwn]*
You got it! Here is your flag!
pwn.college{0F3vm9qD1hs51C47P4EqKRQY5rf.QX2IDO0wiMxITNxEzW}

```

### New Learnings
Brief note on what you learned from the challenge

## 8. Tab completion
This challenge has copied the flag into /challenge/pwncollege, and you can freely cat that file. But you can't type the filename: we used some serious trickery to make sure that you must tab-complete it. Try it out!

### Solve
**Flag:** `pwn.college{wAcaYXdSVqMxmD42aANgSJ0RYad.0FN0EzNxwiMxITNxEzW}`

As the description had already said, all you needed to do is press tab. Untill /challenge/pwn I typed then i  pressed <tab> and hence it got tabbed and gave the flag.

```bash
hacker@globbing~tab-completion:~$ cat /challenge/pwnncollege​ 
pwn.college{wAcaYXdSVqMxmD42aANgSJ0RYad.0FN0EzNxwiMxITNxEzW}
```

### New Learnings
Brief note on what you learned from the challenge

## 9. Multiple options for Tab completion
This challenge has copied the flag into /challenge/pwncollege, and you can freely cat that file. But you can't type the filename: we used some serious trickery to make sure that you must tab-complete it. Try it out!

### Solve
**Flag:** `pwn.college{I5FUNxF998Dv4q-_xHMcq49BzWy.0lN0EzNxwiMxITNxEzW}`

As the description had already said, all you needed to do is press tab. Untill /challenge/pwn I typed then i  pressed <tab> and hence it got tabbed and gave the flag.

```bash
hacker@globbing~multiple-options-for-tab-completion:~$ cd /challenge/files 
hacker@globbing~multiple-options-for-tab-completion:/challenge/files$ cat //challenge/files/pwn
pwn                    pwncollege-family      pwncollege-flyswatter
pwn-college            pwncollege-flag        pwncollege-hacking
hacker@globbing~multiple-options-for-tab-completion:/challenge/files$ cat /challenge/files/pwn
pwn                    pwn-the-planet         pwncollege-flag        pwncollege-flyswatter
pwn-college            pwncollege-family      pwncollege-flamingo    pwncollege-hacking
hacker@globbing~multiple-options-for-tab-completion:/challenge/files$ cat /challenge/files/pwn
No flag in this file!
hacker@globbing~multiple-options-for-tab-completion:/challenge/files$ cat /challenge/files/pwn
pwn                    pwn-the-planet         pwncollege-flag        pwncollege-flyswatter
pwn-college            pwncollege-family      pwncollege-flamingo    pwncollege-hacking
hacker@globbing~multiple-options-for-tab-completion:/challenge/files$ cat /challenge/files/pwn
pwn                    pwn-the-planet         pwncollege-flag        pwncollege-flyswatter
pwn-college            pwncollege-family      pwncollege-flamingo    pwncollege-hacking
hacker@globbing~multiple-options-for-tab-completion:/challenge/files$ cat /challenge/files/pwn
No flag in this file!
hacker@globbing~multiple-options-for-tab-completion:/challenge/files$ cat /challenge/files/pwncollege-
pwncollege-family      pwncollege-flamingo    pwncollege-hacking     
pwncollege-flag        pwncollege-flyswatter  
hacker@globbing~multiple-options-for-tab-completion:/challenge/files$ cat /challenge/files/pwncollege-fl
pwncollege-flag        pwncollege-flamingo    pwncollege-flyswatter  
hacker@globbing~multiple-options-for-tab-completion:/challenge/files$ cat /challenge/files/pwncollege-fla
pwncollege-flag      pwncollege-flamingo  
hacker@globbing~multiple-options-for-tab-completion:/challenge/files$ cat /challenge/files/pwncollege-flag 
pwn.college{I5FUNxF998Dv4q-_xHMcq49BzWy.0lN0EzNxwiMxITNxEzW}
```

### New Learnings
Brief note on what you learned from the challenge

## 10. Tab completion on commands
Tab completion is for more than files! You can also tab-complete commands. This level has a command that starts with pwncollege, and it'll give you the flag. Type pwncollege and hit the tab key to auto-complete it!

### Solve
**Flag:** `pwn.college{w0U6pkLpAvV9JOP_cRt2fYFgTQA.0VN0EzNxwiMxITNxEzW}`

As the description had already said, all you needed to do is press tab. Untill /challenge/pwn I typed then i  pressed <tab> and hence it got tabbed and gave the flag.

```bash
hacker@globbing~tab-completion-on-commands:~$ pwncollege-9432 
Correct! Here is your flag:
pwn.college{w0U6pkLpAvV9JOP_cRt2fYFgTQA.0VN0EzNxwiMxITNxEzW}
```

### New Learnings
Brief note on what you learned from the challenge
