# Pondering Paths

## 1. The Root
Alright, so the filesystem starts at /. Under that, there are a whole mess of other directories, configuration files, programs, and, most importantly, flags. In this level, we've added a program right in /, called pwn, that will give you the flag. All you need to do for this level is to invoke this program!

### Solve
**Flag:** `pwn.college{Q7wXxU_PTXGxTPbXwuFZBogaI39.QX4cTO0wiMxITNxEzW}`
The challenge was simply asking for the "Absolute path" invocation and since we were already at root all i had to do was /pwn which changed the directory for pwn where the flag was there.

```bash
hacker@paths~the-root:~$ /pwn
BOOM!!!
Here is your flag:
pwn.college{Q7wXxU_PTXGxTPbXwuFZBogaI39.QX4cTO0wiMxITNxEzW}
```

### New Learnings
You can invoke a program by providing its path on the command line. In this case, you'll be giving the exact path, starting from /, so the path would be /pwn. This style of path, one that starts with the root directory, is referred to as an "absolute path". and the root directory which is the main directory for all operations.

## 2. Program and Absolute Pahts
Let's explore a slightly more complicated path! Except for in the previous level, challenges in pwn.college are in the challenge directory and the challenge directory is, in turn, right in the root directory (/). The path to the challenge directory is, thus, /challenge. The name of the challenge program in this level is run, and it lives in the /challenge directory. Thus, the path to the run challenge program is /challenge/run.

### Solve
**Flag:** `pwn.college{A5bdz3HW6Uv012dUU39rpcVZluy.QX1QTN0wiMxITNxEzW}`

this challenge required the absolute path for the /challenge/run <- absolute path. It showed how to directly access files from root.

```bash
hacker@paths~program-and-absolute-paths:~$ /challenge/run
Correct!!!
/challenge/run is an absolute path! Here is your flag:
pwn.college{A5bdz3HW6Uv012dUU39rpcVZluy.QX1QTN0wiMxITNxEzW}
```

### New Learnings
Accessing files directly from root.

## 3. Position thy self
The Linux filesystem has tons of directories with tons of files. You can navigate around directories by using the cd (change directory) command and passing a path to it as an argument, as so:

hacker@dojo:~$ cd /some/new/directory
hacker@dojo:/some/new/directory$
This affects the "current working directory" of your process (in this case, the bash shell). Each process has a directory in which it's currently hanging out. The reasons for this will become clear later in the module.
As an aside, now you can see what the ~ was in the prompt! It shows the current path that your shell is located at.
This challenge will require you to execute the /challenge/run program from a specific path (which it will tell you). You'll need to cd to that directory before rerunning the challenge program. Good luck!

### Solve
**Flag:** `pwn.college{An9clqpQl1Ul-3C2Stfz_p2cwaP.QX2QTN0wiMxITNxEzW}`

first, i had to do the ~ to find where i am currently and then cd to that directory then tried the absolute path to which it denied acces. It told the directory i needed to change to so i changed to that directory cd /tmp and hence applied absolute path.

```bash
hacker@paths~position-thy-self:~$ ~
bash: /home/hacker: Is a directory
hacker@paths~position-thy-self:~$ cd /home/hacker
hacker@paths~position-thy-self:~$ /challenge/run
Incorrect...
You are not currently in the /tmp directory.
Please use the `cd` utility to change directory appropriately.
hacker@paths~position-thy-self:~$ cd /tmp
hacker@paths~position-thy-self:/tmp$ /challenge/run
Correct!!!
/challenge/run is an absolute path, invoked from the right directory!
Here is your flag:
pwn.college{An9clqpQl1Ul-3C2Stfz_p2cwaP.QX2QTN0wiMxITNxEzW}
hacker@paths~position-thy-self:/tmp$ 
```

### New Learnings
Changin directory or CD 

## 4. Position elsewhere
This challenge will require you to execute the /challenge/run program from a specific path (which it will tell you). You'll need to cd to that directory before rerunning the challenge program. Good luck!

### Solve
**Flag:** `pwn.college{YMh0rlaEDeCIGDpzro_Ap-ki-AH.QX3QTN0wiMxITNxEzW}`

This challenge required me to use cd to go to /home directory just like the previous one running absolute path there worked.

```bash
hacker@paths~position-elsewhere:~$ ~
bash: /home/hacker: Is a directory
hacker@paths~position-elsewhere:~$ cd /home/hacker
hacker@paths~position-elsewhere:~$ /challenge/run
Incorrect...
You are not currently in the /home directory.
Please use the `cd` utility to change directory appropriately.
hacker@paths~position-elsewhere:~$ cd /home
hacker@paths~position-elsewhere:/home$ /challenge/run
Correct!!!
/challenge/run is an absolute path, invoked from the right directory!
Here is your flag:
pwn.college{YMh0rlaEDeCIGDpzro_Ap-ki-AH.QX3QTN0wiMxITNxEzW}
hacker@paths~position-elsewhere:/home$ 

```

### New Learnings
Changing directory elsewhere.

## 5. Position yet elsewhere
This challenge will require you to execute the /challenge/run program from a specific path (which it will tell you). You'll need to cd to that directory before rerunning the challenge program. Good luck!

### Solve
**Flag:** `pwn.college{Iw_d9iq2YTOPMKZARmuXsjUkqQB.QX4QTN0wiMxITNxEzW}`

This challenge had me run the absolute path to find out the absolute path to invoke run is in the /sys directory to which I changed by cd.

```bash
hacker@paths~position-yet-elsewhere:~$ cd /home/hacker
hacker@paths~position-yet-elsewhere:~$ /challenge/run
Incorrect...
You are not currently in the /sys directory.
Please use the `cd` utility to change directory appropriately.
hacker@paths~position-yet-elsewhere:~$ cd /sys
hacker@paths~position-yet-elsewhere:/sys$ /challenge/run
Correct!!!
/challenge/run is an absolute path, invoked from the right directory!
Here is your flag:
pwn.college{Iw_d9iq2YTOPMKZARmuXsjUkqQB.QX4QTN0wiMxITNxEzW}
```

### New Learnings
Positioning yourself elsewhere and invoking same absolute path.

## 6. implicit relative paths, from /
However, the current working directory does matter for relative paths.

A relative path is any path that does not start at root (i.e., it does not start with /).
A relative path is interpreted relative to your current working directory (cwd).
Your cwd is the directory that your prompt is currently located at.
This means how you specify a particular file, depends on where the terminal prompt is located.

Imagine we want to access some file located at /tmp/a/b/my_file.

If my cwd is /, then a relative path to the file is tmp/a/b/my_file.
If my cwd is /tmp, then a relative path to the file is a/b/my_file.
If my cwd is /tmp/a/b/c, then a relative path to the file is ../my_file. The .. refers to the parent directory.

### Solve
**Flag:** `pwn.college{0qVGxlYwQuXMgtZ3rIvv1uYJ93E.QX5QTN0wiMxITNxEzW}`

Needed to go to root and run the relative path challenge/run

```bash
hacker@paths~implicit-relative-paths-from-:~$ cd /
hacker@paths~implicit-relative-paths-from-:/$ ls
bin   challenge  etc   home  lib32  libx32  mnt  opt   root  sbin  sys  usr
boot  dev        flag  lib   lib64  media   nix  proc  run   srv   tmp  var
hacker@paths~implicit-relative-paths-from-:/$ cd challenge
hacker@paths~implicit-relative-paths-from-:/challenge$ cd /
hacker@paths~implicit-relative-paths-from-:/$ challenge/run
Correct!!!
challenge/run is a relative path, invoked from the right directory!
Here is your flag:
pwn.college{0qVGxlYwQuXMgtZ3rIvv1uYJ93E.QX5QTN0wiMxITNxEzW}
```

### New Learnings
Invoking from relative paths.


## 7. Explicit relative paths, from /
The following relative paths are also all identical to each other:

challenge
./challenge
./././challenge
challenge/.
Of course, if your current working directory is /, the above relative paths are equivalent to the above absolute paths.

This challenge will get you using . in your relative paths. Get ready!

### Solve
**Flag:** `pwn.college{gCvvrmR5ajnhcrWYj2pN55uq-Lc.QXwUTN0wiMxITNxEzW}`

relative path ./ meant the same as invoking the absolute path /challenge/run

```bash
./challenge/run
Correct!!!
./challenge/run is a relative path, invoked from the right directory!
Here is your flag:
pwn.college{gCvvrmR5ajnhcrWYj2pN55uq-Lc.QXwUTN0wiMxITNxEzW}
```

### New Learnings
./ means to stay in the present working directory and ../ means to go to the parent directory


## 8. paths implicit relative path
We'll explore the mechanisms behind this concept later, but in this challenge, we'll learn how to explicitly use relative paths to launch run in this scenario. The way to do this is to tell Linux that you explicitly want to execute a program in the current directory, using . like in the previous levels. Give it a try now!

### Solve
**Flag:** `pwn.college{cz9T1odqxEKDEoRAtP0LFD8RiME.QXxUTN0wiMxITNxEzW}`

same logic here just using cd to change to the challenge directory and then invoking run **relatively** from there

```bash
hacker@paths~implicit-relative-path:~$ ls
Desktop  Downloads
hacker@paths~implicit-relative-path:~$ cd /
hacker@paths~implicit-relative-path:/$ cd challenge 
hacker@paths~implicit-relative-path:/challenge$ ./run
Correct!!!
./run is a relative path, invoked from the right directory!
Here is your flag:
pwn.college{cz9T1odqxEKDEoRAtP0LFD8RiME.QXxUTN0wiMxITNxEzW}
```

### New Learnings
Invoking of programs through relative

## 9. home sweet home
Now it's your turn to play! In this challenge, /challenge/run will write a copy of the flag to any file you specify as an argument on the commandline, with these constraints:

Your argument must be an absolute path.
The path must be inside your home directory.
Before expansion, your argument must be three characters or less.
Again, you must specify your path as an argument to /challenge/run as so:

### Solve
**Flag:** `pwn.college{IQnk84stjWYraUcfpW7vIkdz4--.QXzMDO0wiMxITNxEzW}`

The problem description itself said to copy the file to a specified dierctory which was /home/hacker which is ~ the home directory for the dojo. The instructions were clear I invoked an absolute path and then copied the flag program to another directory.

```bash
hacker@paths~home-sweet-home:~$ /challenge/run ~/a
Writing the file to /home/hacker/a!
... and reading it back to you:
pwn.college{IQnk84stjWYraUcfpW7vIkdz4--.QXzMDO0wiMxITNxEzW}
```

### New Learnings
copying the flag to a specified file 
