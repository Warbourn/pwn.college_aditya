# Untangling Users

## 1. Becoming root with su
But THIS challenge (and only this challenge) does have a root password. That password is hack-the-planet, and you must provide it to su to become root! Go do that, and read the flag!

### Solve
**Flag:** `pwn.college{kEixyZycFooUI-spP6-WA550a8G.QX1UDN1wiMxITNxEzW}`

type in your solve and your thought process behind solving the challenge. Include as much as info as possible. Use triple ticks for any bash commands and output you type on the terminal.

```bash
hacker@users~becoming-root-with-su:~$ su
Password: 
root@users~becoming-root-with-su:/home/hacker# /challenge/run
It's not just hackers that need to become `root`.
Oftentimes, you, as the owner of your computer, need to use `root` access to administer it.
Becoming `root` is a fairly common action that Linux users take, and there are two utilities that exist for this purpose: `su` and `sudo`.

In this challenge, we will cover the older one, `su` (the **s**ubstitute **u**ser command).
This is not typically used to elevate to `root` access anymore, but it is an elegant utility from a more civilized time, and we'll cover it first.
root@users~becoming-root-with-su:/home/hacker# cat /flag
pwn.college{kEixyZycFooUI-spP6-WA550a8G.QX1UDN1wiMxITNxEzW}
```

### New Learnings
Brief note on what you learned from the challenge

### References 
Add any references or videos you used while solving the challenge.

## 2. Other users with su
Awesome! In this level, you must switch to the zardus user and then run /challenge/run. Zardus' password is dont-hack-me. Good luck!

### Solve
**Flag:** `pwn.college{0uDCzoJ8xnq3DlEadXmgXEMrLZy.QX2UDN1wiMxITNxEzW}`

type in your solve and your thought process behind solving the challenge. Include as much as info as possible. Use triple ticks for any bash commands and output you type on the terminal.

```bash
hacker@users~other-users-with-su:~$ su zardus
Password: 
zardus@users~other-users-with-su:/home/hacker$ /challenge/run
Congratulations, you have become Zardus! Here is your flag:
pwn.college{0uDCzoJ8xnq3DlEadXmgXEMrLZy.QX2UDN1wiMxITNxEzW}
```

### New Learnings
Brief note on what you learned from the challenge

### References 
Add any references or videos you used while solving the challenge.

## 3. Cracking passwords
This level simulates this story, giving you a leak of /etc/shadow (in /challenge/shadow-leak). Crack it (this could take a few minutes), su to zardus, and run /challenge/run to get the flag!

### Solve
**Flag:** `pwn.college{helloworld}`

type in your solve and your thought process behind solving the challenge. Include as much as info as possible. Use triple ticks for any bash commands and output you type on the terminal.

```bash
hacker@users~cracking-passwords:~$ john /challenge/shadow-leak
Loaded 1 password hash (crypt, generic crypt(3) [?/64])
Press 'q' or Ctrl-C to abort, almost any other key for status
aardvark         (zardus)
1g 0:00:00:20 100% 2/3 0.04803g/s 279.6p/s 279.6c/s 279.6C/s Johnson..buzz
Use the "--show" option to display all of the cracked passwords reliably
Session completed
hacker@users~cracking-passwords:~$ su zardus
Password: 
zardus@users~cracking-passwords:/home/hacker$ /challenge/run
Congratulations, you have become Zardus! Here is your flag:
pwn.college{Ux-TXH1LWnvvlrbJnHApvflufZG.QX3UDN1wiMxITNxEzW}
```

### New Learnings
Brief note on what you learned from the challenge

### References 
Add any references or videos you used while solving the challenge.

## 4. Using Sudo
In this level, we will give you sudo access, and you will use it to read the flag. Nice and easy!

### Solve
**Flag:** `pwn.college{Al68neY9sjFeM7QU4JWhMZcGqCc.QX4UDN1wiMxITNxEzW}`

type in your solve and your thought process behind solving the challenge. Include as much as info as possible. Use triple ticks for any bash commands and output you type on the terminal.

```bash
hacker@users~using-sudo:~$ sudo cat /flag
pwn.college{Al68neY9sjFeM7QU4JWhMZcGqCc.QX4UDN1wiMxITNxEzW}
```

### New Learnings
Brief note on what you learned from the challenge

### References 
Add any references or videos you used while solving the challenge.
