# Digesting Documentation

## 1. Learning from documentation
Welcome to the documentation for /challenge/challenge! This program allows you to print arbitrary files to the terminal, when given the --printfile argument. The argument to the --printfile argument is the path of the flag to read. For example, /challenge/challenge --printfile /challenge/DESCRIPTION.md will print out the description of the level!

Given that documentation, go get the flag!

Given that knowledge, go get the flag!

### Solve
**Flag:** `pwn.college{helloworld}`

type in your solve and your thought process behind solving the challenge. Include as much as info as possible. Use triple ticks for any bash commands and output you type on the terminal.

```bash
/challenge/challenge --giveflag
Correct argument! Here is your flag:
pwn.college{0IkuAz1gm2z-EErXFkqaLOMEue4.QX0ITO0wiMxITNxEzW}
```

### New Learnings
Brief note on what you learned from the challenge

## 2. Learning complex usage
The program for this challenge is /challenge/challenge, and you'll need to invoke it properly in order for it to give you the flag. Let's pretend that this is its documentation:

Welcome to the documentation for /challenge/challenge! To properly run this program, you will need to pass it the argument of --giveflag. Good luck!

Given that knowledge, go get the flag!

### Solve
**Flag:** `pwn.college{gLes1tGXEdGG16HZatY2ScH-MNT.QX1ITO0wiMxITNxEzW}`

type in your solve and your thought process behind solving the challenge. Include as much as info as possible. Use triple ticks for any bash commands and output you type on the terminal.

```bash
hacker@man~learning-complex-usage:~$ /challenge/challenge --printfile /flag
Correct argument! Here is the /flag file:
pwn.college{gLes1tGXEdGG16HZatY2ScH-MNT.QX1ITO0wiMxITNxEzW}
```

### New Learnings
Brief note on what you learned from the challenge

## 3. Reading Manuals
The challenge in this level has a secret option that, when you use it, will cause the challenge to print the flag. You must learn this option through the man page for challenge!

### Solve
**Flag:** `pwn.college{gI22YP7qualuQqiYUqoOGApUYHd.QX0EDO0wiMxITNxEzW}`

The first comman dI had to run was the man challenge. in the synopsis it said -gqualu NUM and written below it was if num is correct print flag. Num is 227.

```bash
hacker@man~reading-manuals:~$ man challenge
hacker@man~reading-manuals:~$ /challenge/challenge --gqualu 227
Correct usage! Your flag: pwn.college{gI22YP7qualuQqiYUqoOGApUYHd.QX0EDO0wiMxITNxEzW}
```

### New Learnings
Reading manuals, man command.

## 4. Searching Manuals
Find the option that will give you the flag by reading the challenge man page.

### Solve
**Flag:** `pwn.college{MKUpZbN_xcZpsGL5WBwr41aKhDh.QX1EDO0wiMxITNxEzW}`

You can scroll man pages with the arrow keys (and PgUp/PgDn) and search with /. After searching, you can hit n to go to the next result and N to go to the previous result. Instead of /, you can use ? to search backwards! Just needed to go to the man for challenge, search flag using / two n pressed (next) and I found the argument that gives the flag/

```bash
hacker@man~searching-manuals:~$ man challenge
hacker@man~searching-manuals:~$ /challenge/challenge --ycxpy
Initializing...
Correct usage! Your flag: pwn.college{MKUpZbN_xcZpsGL5WBwr41aKhDh.QX1EDO0wiMxITNxEzW}

```

### New Learnings
Searching Manuals. / to search, n to next, ? to search backwards

## 5. Searching for Manuals
The challenge in this level has a secret option that, when you use it, will cause the challenge to print the flag. You must learn this option through the man page for challenge!

### Solve
**Flag:** `pwn.college{gI22YP7qualuQqiYUqoOGApUYHd.QX0EDO0wiMxITNxEzW}`

The first comman dI had to run was the man challenge. in the synopsis it said -gqualu NUM and written below it was if num is correct print flag. Num is 227.

```bash
hacker@man~reading-manuals:~$ man challenge
hacker@man~reading-manuals:~$ /challenge/challenge --gqualu 227
Correct usage! Your flag: pwn.college{gI22YP7qualuQqiYUqoOGApUYHd.QX0EDO0wiMxITNxEzW}
```

### New Learnings
Reading manuals, man command.

## 6. Helpful programs
In this level, you will practice reading a program's documentation with --help. Try it out!

### Solve
**Flag:** `pwn.college{wwgLeZHolP26GeG4di4sgw6wVja.QX3IDO0wiMxITNxEzW}`

The first comman dI had to run was the man challenge. in the synopsis it said -gqualu NUM and written below it was if num is correct print flag. Num is 227.

```bash
/challenge/challenge -h
usage: a challenge to make you ask for help [-h] [--fortune] [-v]
                                            [-g GIVE_THE_FLAG] [-p]

optional arguments:
  -h, --help            show this help message and exit
  --fortune             read your fortune
  -v, --version         get the version number
  -g GIVE_THE_FLAG, --give-the-flag GIVE_THE_FLAG
                        get the flag, if given the correct value
  -p, --print-value     print the value that will cause the -g option to give
                        you the flag
hacker@man~helpful-programs:~$ /challenge/challenge -p
The secret value is: 264
hacker@man~helpful-programs:~$ /challenge/challenge -g 264
Correct usage! Your flag: pwn.college{wwgLeZHolP26GeG4di4sgw6wVja.QX3IDO0wiMxITNxEzW}

```

### New Learnings
Reading manuals, man command.

## 5. Searching for Manuals
In this challenge, we'll practice using help to look up help for builtins. This challenge's challenge command is a shell builtin, rather than a program. Like before, you need to lookup its help to figure out the secret value to pass to it!

### Solve
**Flag:** `pwn.college{glu5IPJBcVOs3DKPFjqHFWH2DIA.QX0ETO0wiMxITNxEzW}`

The first comman dI had to run was the man challenge. in the synopsis it said -gqualu NUM and written below it was if num is correct print flag. Num is 227.

```bash
hacker@man~help-for-builtins:~$ help challenge
challenge: challenge [--fortune] [--version] [--secret SECRET]
    This builtin command will read you the flag, given the right arguments!
    
    Options:
      --fortune		display a fortune
      --version		display the version
      --secret VALUE	prints the flag, if VALUE is correct

    You must be sure to provide the right value to --secret. That value
    is "glu5IPJB".

hacker@man~help-for-builtins:~$ challenge --secret glu5IPJB
Correct! Here is your flag!
pwn.college{glu5IPJBcVOs3DKPFjqHFWH2DIA.QX0ETO0wiMxITNxEzW}
```

### New Learnings
Reading manuals, man command.