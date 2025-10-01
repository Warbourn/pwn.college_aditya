# Comprehending Commands

## 1. cat: not the pet, but the command!
Add challenge description here

### Solve
**Flag:** `pwn.college{gDGxkx7F8LA17byx689k1wB2PUV.QXxcTN0wiMxITNxEzW}`

cat the file to read the contents of the file (which contained flag)

```bash
hacker@commands~cat-not-the-pet-but-the-command:~$ cat flag
pwn.college{gDGxkx7F8LA17byx689k1wB2PUV.QXxcTN0wiMxITNxEzW}
```

### New Learnings
cat command

## 2. Catting absolute paths
In this directory, I will not copy it to your home directory, but I will make it readable. You can read it with cat at its absolute path: /flag.

### Solve
**Flag:** `pwn.college{8itbt8hLROIDCYL52xWUsClgJLR.QX5ETO0wiMxITNxEzW}`

cat command to an absolute path /flag

```bash
hacker@commands~catting-absolute-paths:~$ cat /flag
pwn.college{8itbt8hLROIDCYL52xWUsClgJLR.QX5ETO0wiMxITNxEzW}
```

### New Learnings
catting absolute path


## 3. More catting practice
You can specify all sorts of paths as arguments to commands, and we'll practice some more with cat. In this level, I'll put the flag in some crazy directory, and I will not allow you to change directories with cd, so no cat flag for you. You must retrieve the flag by absolute path, wherever it is.

### Solve
**Flag:** `pwn.college{EmRtBUgZyrKhfztO0Wz1mzKTf2K.QXwITO0wiMxITNxEzW}`

without using cd I cat through the flag wherever it was stored.

```bash
You cannot use the 'cd' command in this level, and must retrieve the flag by 
absolute path. Plus, I hid the flag in a different directory! You can find it 
in the file /lib/sysusers.d/flag. Go cat it out **without** cding into that 
directory!
hacker@commands~more-catting-practice:~$ cat /lib/sysusers.d/flag
pwn.college{EmRtBUgZyrKhfztO0Wz1mzKTf2K.QXwITO0wiMxITNxEzW}
```

### New Learnings
catting asbolute paths.

## 4. Grepping for a needle in a haystack
In this challenge, I've put a hundred thousand lines of text into the /challenge/data.txt file. grep it for the flag!

### Solve
**Flag:** `pwn.college{YFU51wBOx-31f3Dc2lvEpsRFlZz.QX3EDO0wiMxITNxEzW}`

grep SEARCH_STRING /path/to/file.

```bash
hacker@commands~grepping-for-a-needle-in-a-haystack:~$ grep pwn.college /challenge/data.txt
pwn.college{YFU51wBOx-31f3Dc2lvEpsRFlZz.QX3EDO0wiMxITNxEzW}
```

### New Learnings
Grepping command

## 5. Comparing files
Now for your challenge! There are two files in /challenge:

/challenge/decoys_only.txt contains 100 fake flags
/challenge/decoys_and_real.txt contains all 100 fake flags plus the one real flag
Use diff to find what's different between these files and get your flag! 
using diff i compared these and got the flag

### Solve
**Flag:** `pwn.college{YRYYCSOZWZcTrxfEFKGH2Y1PvkL.01MwMDOxwiMxITNxEzW}`


When looking for changes between similar files, eyeballing them might not be the most efficient approach! This is where the diff command becomes invaluable.

diff compares two files line by line and shows you exactly what's different between them. 

```bash
hacker@commands~comparing-files:~$ diff /challenge/decoys_only.txt /challenge/decoys_and_real.txt 
71a72
> pwn.college{YRYYCSOZWZcTrxfEFKGH2Y1PvkL.01MwMDOxwiMxITNxEzW}
```

### New Learnings
compared two files using diff

## 6. listing files
In this challenge, we've named /challenge/run with some random name! List the files in /challenge to find it.


### Solve
**Flag:** `pwn.college{cHnf4pz_tdwb4oiJDgY5HVLAnBR.QX4IDO0wiMxITNxEzW}`


When looking for changes between similar files, eyeballing them might not be the most efficient approach! This is where the diff command becomes invaluable.

diff compares two files line by line and shows you exactly what's different between them. 

```bash
hacker@commands~listing-files:~$ ls /challenge
7846-renamed-run-21858  DESCRIPTION.md
hacker@commands~listing-files:~$ /challenge/7846-renamed-run-21858 
Yahaha, you found me! Here is your flag:
pwn.college{cHnf4pz_tdwb4oiJDgY5HVLAnBR.QX4IDO0wiMxITNxEzW}
```

### New Learnings
listing fiels

## 7. Touching files 
It's that simple! In this level, please create two files: /tmp/pwn and /tmp/college, and run /challenge/run to get your flag!

### Solve
**Flag:** `pwn.college{8zwQB5DDoOpBqc6qV03WhdDlQHB.QXwMDO0wiMxITNxEzW}`


When looking for changes between similar files, eyeballing them might not be the most efficient approach! This is where the diff command becomes invaluable.

diff compares two files line by line and shows you exactly what's different between them. 

```bash
hacker@commands~touching-files:~$ cd /tmp
hacker@commands~touching-files:/tmp$ touch pwn
hacker@commands~touching-files:/tmp$ ls
bin  hsperfdata_root  pwn  tmp.TpSOPGOVKK
hacker@commands~touching-files:/tmp$ touch college
hacker@commands~touching-files:/tmp$ /challenge/run
Success! Here is your flag:
pwn.college{8zwQB5DDoOpBqc6qV03WhdDlQHB.QXwMDO0wiMxITNxEzW}
```

### New Learnings
creating fiels using touch command

## 8. removing files
This challenge will create a delete_me file in your home directory! Delete it, then run /challenge/check, which will make sure you've deleted it and then give you the flag!

### Solve
**Flag:** `pwn.college{kbXIomkDzw7jcYwN6LzHteA3mg9.QX2kDM1wiMxITNxEzW}`

In Linux, you remove files with the rm command, as so:

```bash
hacker@commands~removing-files:~$ rm delete_me
hacker@commands~removing-files:~$ /challenge/check
Excellent removal. Here is your reward:
pwn.college{kbXIomkDzw7jcYwN6LzHteA3mg9.QX2kDM1wiMxITNxEzW}
```

### New Learnings
removing files using rm

## 9. moving files
This challenge wants you to move the /flag file into /tmp/hack-the-planet (do it)! When you're done, run /challenge/check, which will check things out and give the flag to you.

### Solve
**Flag:** `pwn.college{0ixzi6C4twDgKlSlU6aTLW6B1-F.0VOxEzNxwiMxITNxEzW}`

You can also move files around with the mv command. The usage is simple:

```bash
hacker@commands~moving-files:~$ mv /flag /tmp/hack-the-planet
Correct! Performing 'mv /flag /tmp/hack-the-planet'.
hacker@commands~moving-files:~$ /challenge/check
Congrats! You successfully moved the flag to /tmp/hack-the-planet! Here it is:
pwn.college{0ixzi6C4twDgKlSlU6aTLW6B1-F.0VOxEzNxwiMxITNxEzW}
```

### New Learnings
moving files using mv

## 10. hidden files
Now, it's your turn! Go find the flag, hidden as a dot-prepended file in /.

### Solve
**Flag:** `pwn.college{QR50Pa8hB9tjl2yHWrqegAz4Gzr.QXwUDO0wiMxITNxEzW}`

Interestingly, ls doesn't list all the files by default. Linux has a convention where files that start with a . don't show up by default in ls and in a few other contexts. To view them with ls, you need to invoke ls with the -a flag, as so:

```bash
hacker@commands~hidden-files:~$ cd /
hacker@commands~hidden-files:/$ ls -a
.                     bin        etc    lib64   nix   run   tmp
..                    boot       home   libx32  opt   sbin  usr
.dockerenv            challenge  lib    media   proc  srv   var
.flag-18937858520539  dev        lib32  mnt     root  sys
hacker@commands~hidden-files:/$ cat .flag-18937858520539
pwn.college{QR50Pa8hB9tjl2yHWrqegAz4Gzr.QXwUDO0wiMxITNxEzW}
```

### New Learnings
accesing hidden file (.flag) using ls -a

## 11. An Epic Filesystem Quest
In this challenge, I have hidden the flag! Here, you will use ls and cat to follow my breadcrumbs and find it! Here's how it'll work:

1. Your first clue is in /. Head on over there.
2. Look around with ls. There'll be a file named HINT or CLUE or something along those lines!
3. cat that file to read the clue!
4. Depending on what the clue says, head on over to the next directory (or don't!).
5. Follow the clues to the flag!

### Solve
**Flag:** `pwn.college{QR50Pa8hB9tjl2yHWrqegAz4Gzr.QXwUDO0wiMxITNxEzW}`

Interestingly, ls doesn't list all the files by default. Linux has a convention where files that start with a . don't show up by default in ls and in a few other contexts. To view them with ls, you need to invoke ls with the -a flag, as so:

```bash
hacker@commands~an-epic-filesystem-quest:~$ cd /
hacker@commands~an-epic-filesystem-quest:/$ ls
MEMO  challenge  flag  lib32   media  opt   run   sys  var
bin   dev        home  lib64   mnt    proc  sbin  tmp
boot  etc        lib   libx32  nix    root  srv   usr
hacker@commands~an-epic-filesystem-quest:/$ cat MEMO
Tubular find!
The next clue is in: /usr/local/lib/python3.8/dist-packages/jupyterlab/galata/@jupyterlab/galata-extension

The next clue is **hidden** --- its filename starts with a '.' character. You'll need to look for it using special options to 'ls'.
hacker@commands~an-epic-filesystem-quest:/$ ls -a /usr/local/lib/python3.8/dist-packages/jupyterlab/galata/@jupyterlab/galata-extension
.  ..  .LEAD  build_log.json  package.json  static
hacker@commands~an-epic-filesystem-quest:/$ cat /usr/local/lib/python3.8/dist-packages/jupyterlab/galata/@jupyterlab/galata-extension/.LEAD
Lucky listing!
The next clue is in: /usr/local/lib/python3.8/dist-packages/pwnlib/shellcraft/templates/i386/android

The next clue is **hidden** --- its filename starts with a '.' character. You'll need to look for it using special options to 'ls'.
hacker@commands~an-epic-filesystem-quest:/$ ls -a /usr/local/lib/python3.8/dist-packages/pwnlib/shellcraft/templates/i386/android
.                    dupio.asm           kill.asm           setresuid.asm
..                   dupsh.asm           killparent.asm     setreuid.asm
.HINT                echo.asm            loader.asm         sh.asm
__doc__              egghunter.asm       loader_append.asm  sleep.asm
acceptloop_ipv4.asm  findpeer.asm        mprotect_all.asm   socket.asm
cat.asm              findpeersh.asm      pidmax.asm         socketcall.asm
cat2.asm             findpeerstager.asm  readfile.asm       stage.asm
connect.asm          forkbomb.asm        readn.asm          stager.asm
connectstager.asm    forkexit.asm        recvsize.asm       syscall.asm
dir.asm              i386_to_amd64.asm   setregid.asm       syscalls
hacker@commands~an-epic-filesystem-quest:/$ cat /usr/local/lib/python3.8/dist-packages/pwnlib/shellcraft/templates/i386/android/.HINT
Tubular find!
The next clue is in: /usr/share/doc/sgml-base/examples

The next clue is **delayed** --- it will not become readable until you enter the directory with 'cd'.
hacker@commands~an-epic-filesystem-quest:/$ cd /usr/share/doc/sgml-base/examples
hacker@commands~an-epic-filesystem-quest:/usr/share/doc/sgml-base/examples$ ls -a
.  ..  BRIEF  postinst  postrm  prerm
hacker@commands~an-epic-filesystem-quest:/usr/share/doc/sgml-base/examples$ cat BRIEF
Lucky listing!
The next clue is in: /usr/lib/x86_64-linux-gnu/perl/5.30.0/auto/Encode
hacker@commands~an-epic-filesystem-quest:/usr/share/doc/sgml-base/examples$ ls /usr/lib/x86_64-linux-gnu/perl/5.30.0/auto/Encode
Byte  CN  EBCDIC  Encode.so  JP  KR  Symbol  TIP  TW  Unicode
hacker@commands~an-epic-filesystem-quest:/usr/share/doc/sgml-base/examples$ cat TIP
cat: TIP: No such file or directory
hacker@commands~an-epic-filesystem-quest:/usr/share/doc/sgml-base/examples$ cat /usr/lib/x86_64-linux-gnu/perl/5.30.0/auto/Encode/TIP
Congratulations, you found the clue!
The next clue is in: /usr/local/lib/python3.8/dist-packages/h11-0.16.0.dist-info
hacker@commands~an-epic-filesystem-quest:/usr/share/doc/sgml-base/examples$ ls /usr/local/lib/python3.8/dist-packages/h11-0.16.0.dist-info
INSTALLER  METADATA  RECORD  WHEEL  WHISPER  licenses  top_level.txt
hacker@commands~an-epic-filesystem-quest:/usr/share/doc/sgml-base/examples$ cat /usr/local/lib/python3.8/dist-packages/h11-0.16.0.dist-info/top_level.txt
h11
hacker@commands~an-epic-filesystem-quest:/usr/share/doc/sgml-base/examples$ cat /usr/local/lib/python3.8/dist-packages/h11-0.16.0.dist-info/top_level.txt/WHISPER
cat: /usr/local/lib/python3.8/dist-packages/h11-0.16.0.dist-info/top_level.txt/WHISPER: Not a directory
hacker@commands~an-epic-filesystem-quest:/usr/share/doc/sgml-base/examples$ cat /usr/local/lib/python3.8/dist-packages/h11-0.16.0.dist-info/WHISPER
Yahaha, you found me!
The next clue is in: /usr/lib/python3/dist-packages/sympy/crypto/tests/__pycache__
hacker@commands~an-epic-filesystem-quest:/usr/share/doc/sgml-base/examples$ ls /usr/lib/python3/dist-packages/sympy/crypto/tests/__pycache__
REVELATION  __init__.cpython-38.pyc  test_crypto.cpython-38.pyc
hacker@commands~an-epic-filesystem-quest:/usr/share/doc/sgml-base/examples$ cat /usr/lib/python3/dist-packages/sympy/crypto/tests/__pycache__/REVELATION
Lucky listing!
The next clue is in: /usr/share/perl/5.30.0/unicore/lib/Ideo

The next clue is **delayed** --- it will not become readable until you enter the directory with 'cd'.
hacker@commands~an-epic-filesystem-quest:/usr/share/doc/sgml-base/examples$ cd /usr/share/perl/5.30.0/unicore/lib/Ideo
hacker@commands~an-epic-filesystem-quest:/usr/share/perl/5.30.0/unicore/lib/Ideo$ ls -a
.  ..  INSIGHT  Y.pl
hacker@commands~an-epic-filesystem-quest:/usr/share/perl/5.30.0/unicore/lib/Ideo$ cat INSIGHT
Lucky listing!
The next clue is in: /opt/linux/linux-5.4/fs/notify

Watch out! The next clue is **trapped**. You'll need to read it out without 'cd'ing into the directory; otherwise, the clue will self destruct!
hacker@commands~an-epic-filesystem-quest:/usr/share/perl/5.30.0/unicore/lib/Ideo$ ls /opt/linux/linux-5.4/fs/notify
Kconfig          built-in.a  fdinfo.c  fsnotify.c  group.c  mark.c          notification.o
Makefile         dnotify     fdinfo.h  fsnotify.h  group.o  mark.o
SPOILER-TRAPPED  fanotify    fdinfo.o  fsnotify.o  inotify  notification.c
hacker@commands~an-epic-filesystem-quest:/usr/share/perl/5.30.0/unicore/lib/Ideo$ cat /opt/linux/linux-5.4/fs/notify/SPOILER-TRAPPED
CONGRATULATIONS! Your perserverence has paid off, and you have found the flag!
It is: pwn.college{svCADGYbZa8gN-UI6pXXz-XqtLE.QX5IDO0wiMxITNxEzW}

```

### New Learnings
Brief note on what you learned from the challenge

## 12. making directories 
go forth and create a /tmp/pwn directory and make a college file in it! Then run /challenge/run, which will check your solution and give you the flag!

### Solve
**Flag:** `pwn.college{sh8yTDEJQR85OmldHFjfytNXlKH.QXxMDO0wiMxITNxEzW}`

We can create files. How about directories? You make directories using the mkdir command. Then you can stick files in there!

```bash
hacker@commands~making-directories:~$ mkdir /tmp/pwn
hacker@commands~making-directories:~$ cd /tmp/pwn
hacker@commands~making-directories:/tmp/pwn$ touch college
hacker@commands~making-directories:/tmp/pwn$ /challenge/run
Success! Here is your flag:
pwn.college{sh8yTDEJQR85OmldHFjfytNXlKH.QXxMDO0wiMxITNxEzW}
```

### New Learnings
Combining all my knowledge

## 13. finding files
First, there are other files named flag on the filesystem. Don't panic if the first one you try doesn't have the actual flag in it. Second, there're plenty of places in the filesystem that are not accessible to a normal user. These will cause find to generate errors, but you can ignore those; we won't hide the flag there! Finally, find can take a while; be patient!

### Solve
**Flag:** `pwn.college{0gg7DUkND5PfkiYs6nWu64Wb94o.QXyMDO0wiMxITNxEzW}`

We can create files. How about directories? You make directories using the mkdir command. Then you can stick files in there!

```bash
hacker@commands~finding-files:~$ find / -name "flag"
find: ‘/root’: Permission denied
find: ‘/etc/ssl/private’: Permission denied
find: ‘/tmp/tmp.TpSOPGOVKK’: Permission denied
/usr/local/lib/python3.8/dist-packages/pwnlib/flag
/usr/lib/python3/dist-packages/sage_setup/autogen/interpreters/specs/flag
^C
hacker@commands~finding-files:~$ cat /usr/local/lib/python3.8/dist-packages/pwnlib/flag
cat: /usr/local/lib/python3.8/dist-packages/pwnlib/flag: Is a directory
hacker@commands~finding-files:~$ cat /usr/lib/python3/dist-packages/sage_setup/autogen/interpreters/specs/flag
pwn.college{0gg7DUkND5PfkiYs6nWu64Wb94o.QXyMDO0wiMxITNxEzW}
```

### New Learnings
Find command using it to find files

## 14. linking files 
In this level the flag is, as always, in /flag, but /challenge/catflag will instead read out /home/hacker/not-the-flag. Use the symlink, and fool it into giving you the flag!

### Solve
**Flag:** `pwn.college{oEvfxyMkpXdyn6Hq47Ao1sUWIzv.QX5ETN1wiMxITNxEzW}`

We can create files. How about directories? You make directories using the mkdir command. Then you can stick files in there!

```bash
/challenge/catflag
About to read out the /home/hacker/not-the-flag file!
pwn.college{oEvfxyMkpXdyn6Hq47Ao1sUWIzv.QX5ETN1wiMxITNxEzW}
```

### New Learnings
Using a softlink or a symlink 
