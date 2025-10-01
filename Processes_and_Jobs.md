# Shell Variables

## 1. Print Variables 
Have your shell print out the FLAG variable and solve this challenge!

### Solve
**Flag:** `pwn.college{ktlxg-Y-XDN_KYllLB1dX103Vb_.QX3UTN0wiMxITNxEzW}`

printed the variable flag by echo $FLAG

```bash

hacker@variables~printing-variables:~$ echo $FLAG
pwn.college{ktlxg-Y-XDN_KYllLB1dX103Vb_.QX3UTN0wiMxITNxEzW}
```

### New Learnings
Variables and printing them


## 2. Setting Variables
To solve this level, you must set the PWN variable to the value COLLEGE. Be careful: both the names and values of variables are case-sensitive! PWN is not the same as pwn and COLLEGE is not the same as College.

### Solve
**Flag:** `pwn.college{cka2dOotszioz4KY7AINHMYFJNF.QX5UTN0wiMxITNxEzW}`

set a variable PWN that is equal to college PWN=COLLEGE

```bash
hacker@variables~setting-variables:~$ PWN=COLLEGE
You've set the PWN variable properly! As promised, here is the flag:
pwn.college{cka2dOotszioz4KY7AINHMYFJNF.QX5UTN0wiMxITNxEzW}
```

### New Learnings
settings variables

## 3. Multi Word Variables
Here, the shell reads 1337 SAUCE as a single token, and happily sets that value to VAR. In this level, you'll need to set the variable PWN to COLLEGE YEAH. Good luck!

### Solve
**Flag:** `pwn.college{cSTZTNErVfNVggxQAp5LxpifKuK.QXwYTN0wiMxITNxEzW}`

set "" marks to make it one token and stored words inside that for it to store in the variable.

```bash
hacker@variables~multi-word-variables:~$ PWN="COLLEGE YEAH"
You've set the PWN variable properly! As promised, here is the flag:
pwn.college{cSTZTNErVfNVggxQAp5LxpifKuK.QXwYTN0wiMxITNxEzW}
```

### New Learnings
Multi-word variables (1 token only)

## 4. Exporting Variables
In this challenge, you must invoke /challenge/run with the PWN variable exported and set to the value COLLEGE, and the COLLEGE variable set to the value PWN but not exported (e.g., not inherited by /challenge/run). Good luck!

### Solve
**Flag:** `pwn.college{cPOIYiL2g-Mw9y01qcXtHwiurwk.QXyYTN0wiMxITNxEzW}`

```bash 
hacker@dojo:~$ VAR=1337
hacker@dojo:~$ export VAR
hacker@dojo:~$ sh
$ echo "VAR is: $VAR"
VAR is: 1337
```
Here, the child shell received the value of VAR and was able to print it out! This gave me the gist of it. the export command helped me export the variable. then i did put PWN value in college variable

```bash
hacker@variables~exporting-variables:~$ export PWN=COLLEGE
You've set the PWN variable to the proper value!
hacker@variables~exporting-variables:~$ COLLEGE=PWN
You've set the PWN variable to the proper value!
You've set the COLLEGE variable to the proper value!
hacker@variables~exporting-variables:~$ sh
sh-5.2$ echo $PWN
COLLEGE
sh-5.2$ echo $COLLEGE

sh-5.2$ /challenge/run
CORRECT!
You have exported PWN=COLLEGE and set, but not exported, COLLEGE=PWN. Great 
job! Here is your flag:
pwn.college{cPOIYiL2g-Mw9y01qcXtHwiurwk.QXyYTN0wiMxITNxEzW}
```

### New Learnings
exporting a variable 

## 5. Exporting Printed Variables
Try the env command: it'll print out every exported variable set in your shell, and you can look through that output to find the FLAG variable!

### Solve
**Flag:** `pwn.college{U06tn0C80Va9MEE3AE7lS2GNn59.QX4UTN0wiMxITNxEzW}`

I did env command and it printed each exported variable. The variable FLAG contained the flag

```bash
hacker@variables~printing-exported-variables:~$ env
SHELL=/run/dojo/bin/bash
HOSTNAME=variables~printing-exported-variables
PWD=/home/hacker
MANPATH=/run/dojo/share/man:
DOJO_AUTH_TOKEN=e3a56075969c3e31a1ddd97627bb43e79572a96bd59a38ebb91b7b1dbb14b0e6
HOME=/home/hacker
LANG=C.UTF-8
FLAG=pwn.college{U06tn0C80Va9MEE3AE7lS2GNn59.QX4UTN0wiMxITNxEzW}
TERMINFO=/run/dojo/share/terminfo
TERM=xterm-256color
SHLVL=2
LC_CTYPE=C.UTF-8
SSL_CERT_FILE=/run/dojo/etc/ssl/certs/ca-bundle.crt
PATH=/run/challenge/bin:/run/dojo/bin:/root/.cargo/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
DEBIAN_FRONTEND=noninteractive
_=/run/dojo/bin/env
```

### New Learnings
env command

## 6. Storing Command Output
Read the output of the /challenge/run command directly into a variable called PWN, and it will contain the flag!

### Solve
**Flag:** `pwn.college{wVl253_vc1bcDm6tNfyHZtSr6nu.QX1cDN1wiMxITNxEzW}`

I read the flag into the PWN variable by doing $(/absolute/path) and printed the variable out using echo $PWN since the flag was read into the PWN variable 

```bash
hacker@variables~storing-command-output:~$ PWN=$(/challenge/run)
Congratulations! You have read the flag into the PWN variable. Now print it out 
and submit it!
hacker@variables~storing-command-output:~$ cat PWN
COLLEGE
hacker@variables~storing-command-output:~$ echo "$PWN" 
pwn.college{wVl253_vc1bcDm6tNfyHZtSr6nu.QX1cDN1wiMxITNxEzW}
```

### New Learnings
Storing command output

## 7. Reading Input
In this challenge, your job is to use read to set the PWN variable to the value COLLEGE. Good luck!

### Solve
**Flag:** `pwn.college{whBjBaeNvpQnLnamI1XMSiR_jqG.QX4cTN0wiMxITNxEzW}`

I used read to set the value I needed inside the PWN hence by doing read command I typed COLLEGE by my keyboard and it stored that value and gave the flag

```bash
hacker@variables~reading-input:~$ read PWN
COLLEGE
You've set the PWN variable properly! As promised, here is the flag:
pwn.college{whBjBaeNvpQnLnamI1XMSiR_jqG.QX4cTN0wiMxITNxEzW}
```

### New Learnings
Read command


## 8. Reading Files 
read /challenge/read_me into the PWN environment variable, and we'll give you the flag! The /challenge/read_me will keep changing, so you'll need to read it right into the PWN variable with one command!

### Solve
**Flag:** `pwn.college{4PpcLcx-a2MbbP-uZmysFGn4Qgh.QXwIDO0wiMxITNxEzW}`

I did the read command and put /challenge/read_me as the std in of the read pwn which made the PWN read to the read_me file

```bash
hacker@variables~reading-files:~$ read PWN  < /challenge/read_me
You've set the PWN variable properly! As promised, here is the flag:
pwn.college{4PpcLcx-a2MbbP-uZmysFGn4Qgh.QXwIDO0wiMxITNxEzW}
```

### New Learnings
Reading files and storing them in a variable

