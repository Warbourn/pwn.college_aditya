# Data Manipulation

## 1. Translating Characters
Now, you try it! In this level, /challenge/run will print the flag but will swap the casing of all characters (e.g., A will become a and vice-versa). Can you undo it with tr and get the flag?

### Solve
**Flag:** `pwn.college{wYsNyLoV2RIFw-_25MggSZGvLfU.01MxEzNxwiMxITNxEzW}`
**Flag:** 

type in your solve and your thought process behind solving the challenge. Include as much as info as possible. Use triple ticks for any bash commands and output you type on the terminal.

```bash
hacker@data~translating-characters:~$ /challenge/run | tr 'a-zA-Z' 'A-Za-z'
yOUR CASE-SWAPPED FLAG:
pwn.college{wYsNyLoV2RIFw-_25MggSZGvLfU.01MxEzNxwiMxITNxEzW}
```

ABCDEFGHIJKLMNOPQRSTUVWXYZ
abcdefghijklmnopqrstuvwxyz

### New Learnings
Brief note on what you learned from the challenge

### References 
Add any references or videos you used while solving the challenge.


## 2. Deleting Characters
Now you give it a try. I'll intersperse some decoy characters (specifically: ^ and %) among the flag characters. Use tr -d to remove them!

### Solve
**Flag:** `pwn.college{oWKhtZ0BUd_dRSJ3FDAnFkuGOlx.0FNxEzNxwiMxITNxEzW}`

type in your solve and your thought process behind solving the challenge. Include as much as info as possible. Use triple ticks for any bash commands and output you type on the terminal.

```bash
hacker@data~deleting-characters:~$ /challenge/run | tr -d  "% ^"
Yourcharacter-stuffedflag:
pwn.college{oWKhtZ0BUd_dRSJ3FDAnFkuGOlx.0FNxEzNxwiMxITNxEzW}
```

### New Learnings
Brief note on what you learned from the challenge

### References 
Add any references or videos you used while solving the challenge.

## 3. Deleting Newlines
Now, let's combine this with deletion. In this challenge, we'll inject a bunch of newlines into the flag. Delete them with tr's -d flag and the escaped newline specification!

### Solve
**Flag:** `pwn.college{8iezUtVasa0SRBe4RRgUz_kTXb3.0VNxEzNxwiMxITNxEzW}`

type in your solve and your thought process behind solving the challenge. Include as much as info as possible. Use triple ticks for any bash commands and output you type on the terminal.

```bash
hacker@data~deleting-newlines:~$ /challenge/run | tr -d  "\n"
Your line-split flag: pwn.college{8iezUtVasa0SRBe4RRgUz_kTXb3.0VNxEzNxwiMxITNxEzW}
```

### New Learnings
Brief note on what you learned from the challenge

### References 
Add any references or videos you used while solving the challenge.

## 4. Extracting the first lines with head
This challenge's /challenge/pwn outputs a bunch of data, and you'll need to pipe it through head to grab just the first 7 lines and then pipe them onwards to /challenge/college, which will give you the flag if you do this right! Your solution will be a long composite command with two pipes connecting three commands. Good luck!

### Solve
**Flag:** `pwn.college{AMzyfeXrFirD7Doi1pxSvOkkRAn.0lNxEzNxwiMxITNxEzW}`

type in your solve and your thought process behind solving the challenge. Include as much as info as possible. Use triple ticks for any bash commands and output you type on the terminal.

```bash
hacker@data~extracting-the-first-lines-with-head:~$ /challenge/pwn | head -n 7 | /challenge/college
Congratulations, you piped the right codes!
pwn.college{AMzyfeXrFirD7Doi1pxSvOkkRAn.0lNxEzNxwiMxITNxEzW}
```

### New Learnings
Brief note on what you learned from the challenge

### References 
Add any references or videos you used while solving the challenge.

## 5. Translating Characters
In this challenge, the /challenge/run program will give you a bunch of lines with random numbers and single characters (characters of the flag) as columns. Use cut to extract the flag characters, then pipe them to tr -d "\n" (like the previous level!) to join them together into a single line. Your solution will look something like /challenge/run | cut ??? | tr ???, with the ??? filled out.

### Solve
**Flag:** `pwn.college{4jRrYeEytpYIaKWnBZpJrNr8zTu.01NxEzNxwiMxITNxEzW}}`

type in your solve and your thought process behind solving the challenge. Include as much as info as possible. Use triple ticks for any bash commands and output you type on the terminal.

```bash
hacker@data~extracting-specific-sections-of-text:~$ /challenge/run | cut -d " " -f 1 | tr -d "\n"
2653573772440810724192841212225929125942231438623047710869866630522255322480162661205213241223899083077819375366010370980219052402928047269342773728471128812841062712536215518160031588330242257044022311992071216260280128878114661911823613838288981728263262494861824444308541673612449hacker@data~extracting-specific-sections-of-text:~$ /challenge/run | cut -d " " -f 5 | tr -d "\n"
hacker@data~extracting-specific-sections-of-text:~$ /challenge/run | cut -d " " -f 3 | tr -d "\n"
hacker@data~extracting-specific-sections-of-text:~$ /challenge/run | cut -d " " -f 2 | tr -d "\n"
pwn.college{4jRrYeEytpYIaKWnBZpJrNr8zTu.01NxEzNxwiMxITNxEzW}
```

### New Learnings
Brief note on what you learned from the challenge

### References 
Add any references or videos you used while solving the challenge.

## 6. Sorting data

In this challenge, there's a file at /challenge/flags.txt containing 100 fake flags, with the real flag mixed among them. When sorted alphabetically, the real flag will be at the end (we made sure of this when generating fake flags). Go get it!

### Solve
**Flag:** `pwn.college{s6ZHvPEQQftMcM8yPvA3Mv-Bm7u.0FM0MDOxwiMxITNxEzW}`

type in your solve and your thought process behind solving the challenge. Include as much as info as possible. Use triple ticks for any bash commands and output you type on the terminal.

```bash
hacker@data~sorting-data:~$ sort /challenge/flags.txt -r
pwn.college{s6ZHvPEQQftMcM8yPvA3Mv-Bm7u.0FM0MDOxwiMxITNxEzW}
pwn.college{s6ZHvPEQQftMcM8yPvA3Mv-Bm7u.0FM0MDOxwhMxHTNxEzW}
pwn.college{s6ZHvPEQQftMcM8yPvA3Mv-Bm7t.0FM0MDOxwiMxITNxEzW}
pwn.college{s6ZHvPEQQftMcM8yPvA3Mv-Bm7t.0FM0MDOxwiMxISNxEzW}
pwn.college{s6ZHvPEQQftMcM8yPvA3Mv-Am6u.0FM0MDOxwiMxITNxEzW}
pwn.college{s6ZHvPEQQftMcM8yPvA2Lv-Bm7u.0FM0MDOxwiMxITNxEzW}
pwn.college{s6ZHvPEQQftMcM7yPuA3Mu-Bm7u.0FM0MDOxwiLxITNxEzV}
pwn.college{s6ZHvPEQQftMcM7yOvA2Mv-Bm7u.0EM0MDNwviMxISNxDyW}
pwn.college{s6ZHvPEQQftLcM8yPvA3Mv-Bm7u.0FL0MDOxwiMxITNxEzW}
pwn.college{s6ZHvPEQQfsMcM8yPvA3Mv-Bm7u.0FM0MDOxwiMxITNxEzW}
pwn.college{s6ZHvPEQQetMbM8yPvA3Mv-Bm7t.0FM0MDOxwiMxITNxEyW}
pwn.college{s6ZHvPEPQftMcM8yPvA3Mv-Bm7u.0EM0MDOxwhLxISNxDyW}
pwn.college{s6ZHvPEPQftMcM8yPvA3Lv-Bm7u.0FM0MDOxwiMxITNxEzW}
pwn.college{s6ZHuPEQPftMcM8yPvA3Lv-Bm7u.0FM0MDOxwhMxHTNxEzW}
pwn.college{s6YGvOEQPetMcM8xPvA2Mv-Bm6u.0FM0MDOwviLxITNxEyW}
pwn.college{s5ZHvPEQQftMcL8yPvA3Mv-Am7u.0FL0MDOwwhLwISNxEzW}
pwn.college{s5ZHvPEQQetMcL8yPvA3Mv-Am7u.0FM0LDOxviMxITNxEzW}
pwn.college{s5ZHvPDQPftLcM8yPuA3Mv-Bl7u.0FM0MDNxviMxITMxEzW}
pwn.college{s5YHvPEQQfsMbM7yPvA2Mv-Bm7t.0FM0LDOwwhMxITNwEyW}
pwn.college{r6ZHvPEQQftMcM8yPvA3Mv-Bm7u.0FM0MDOxwiMxITNxEzW}
pwn.college{r5YHvPEPQetLcM8yPvA3Lv-Bm7u.0FM0MDOxwiMwHTNxEzV}
pwn.college{r5YHuPEQQetLbL8yPvA3Lv-Bl6u.0FM0MDOxwiMxITNxDzW}
pwn.collegd{s6ZGvPEQQftMcM8yPuA3Mv-Al7u.0FM0MDOxwiMxITMxEyW}
pwn.collefe{s6ZHvPEQQftMcM8yPvA3Lv-Am7u.0FM0LDOxwiMxITNxEzW}
pwn.collefe{s5ZHvPEQQftMcM8yPvA3Mv-Am7u.0FM0MCOxwiMxITNxEzW}
pwn.collefe{s5ZHvPEQQftMcM8yPvA3Lv-Bm7u.0FM0MDOxwiMxITNxEzW}
pwn.collefd{s5ZHvODQQfsMcL8xPvA3Mv-Bl7t.0EM0MCOwvhMxITMxEyV}
pwn.colldge{s6ZHvPEQPftMcM8yPvA3Mv-Bm7u.0EM0MDOwwhMxITNxEzW}
pwn.colldge{s6ZHuPEQQftMcM8yPvA3Mv-Bm7u.0FM0MDOxwiMxITNxEyW}
pwn.colldge{s5ZHvODQPesLcM8xPvA2Mu-Am7t.0FM0MDNxwhMxITNxEyV}
pwn.colldge{s5ZGvPDQQftMbL8xPvA2Lu-Bm6u.0FM0LDOxwhLxITNwEzW}
pwn.colldgd{s6ZHvPEQQftMcM8yPvA3Mv-Bm7u.0FM0MDOxwiMxITNxEzW}
pwn.colldfe{s6ZGvPEPQesLbL8yPvA3Lu-Bl7u.0EM0MDNxviMxITMxEzW}
pwn.colkege{s6YHvPEQQfsMcM8xOuA3Mv-Am7u.0FM0MDOxwiMxITNxEzW}
pwn.colkefe{s6YGvPEQPetLcM8yPvA3Mv-Bm7u.0FM0MDOxwhMxITMxEzW}
pwn.colkefe{s5ZHvPDQQftMbL8yPuA3Mv-Am6t.0FM0MCNxwiLxISNxEzW}
pwn.coklege{s6ZGvPEQPftMcM8xPvA3Mv-Bm7u.0FM0MDOxwiMxITNxEzW}
pwn.cokldge{s6ZHvPEQPftMcM8xPuA2Lv-Bl6t.0EM0MCNxviMwHTMxEzW}
pwn.cokldge{s6ZHvPEPQetMcM8yPvA3Mv-Bl7u.0FL0MDOwwiMxITNxEzW}
pwn.cnllege{s6ZGvPDQPftMcM7yPvA3Mu-Al7u.0FL0MDOxviMxITNxEzW}
pwn.cnllefe{s5ZHuODPQetMcL8yPvA2Mv-Bm6u.0EM0LCNxviMxISNwEzV}
pwn.cnlldfe{s6ZHvPDQQetMbM8yOvA3Mv-Bm6u.0FM0MDNxwhMxISNxEyV}
pwn.cnlkege{s6ZHvPEQQftMcM8yOvA3Mv-Al7u.0FM0LDNxwiMxITNxEzV}
pwn.cnlkege{s6YHvODPQftMcM8yPvA3Mv-Bm7u.0FM0MDOxwiMxHTNwDzW}
pwn.cnlkdge{s6ZGvPEQQftMcM8yPuA3Lv-Am7t.0FL0MDOwwiMwITMwEzW}
pwn.cnlkdge{s5YGuPEQQftMcL7yPuA3Mv-Bl7u.0FM0LCNwwhMxISNxDyV}
pwn.cnklege{r6ZGvOEQQftLcM8yOvA3Mu-Am6u.0EM0MDNxwiLxITNxEzW}
pwn.cnklege{r5ZHuPEQQetMcM8xPuA3Mv-Bm7u.0FM0MDOxwiMxHTNxEzW}
pwn.cnklegd{s6ZHuPEQQftLcM8yPvA3Mv-Bm7u.0EM0MDOxwiMxITNxEzW}
pwn.cnkkdge{r6ZHvPEQQfsLbM8yOvA3Mv-Am7u.0FM0MDOwvhLxISNxEzW}
pwn.bollege{s6YHvPDQQfsLcM8yPvA3Mv-Bm7u.0FM0MDOxwhMxITMxDyV}
pwn.bollege{s5YHuPEQQftMcM8yPvA3Mv-Bm7u.0FM0MDOxwhMxITNxDzW}
pwn.bollegd{s5ZHvOEQQftMcM7yPvA3Mv-Bm7u.0FM0MDOxwiMwITNxEzV}
pwn.bollegd{r6ZHvPEQPetMcM7yOuA3Mv-Bl6t.0FL0LDOxwiMxITNwEyW}
pwn.boklege{s6ZHuPDPPftMcL7yPvA3Mv-Al7t.0FM0MDOxviMwITNxDzW}
pwn.bnlkdfd{s6ZHvPEQPftMcM8yPvA3Mv-Am7u.0FM0MDOxwhMxITNxEzW}
pwm.college{s6ZHvPEQQftMcM8xPvA2Mv-Bl7t.0FM0LDOxwiMxITMxEyV}
pwm.college{s6ZHvPEQQetLcM8yPvA3Mv-Bm7u.0EM0MDOxwhMxITNxEzW}
pwm.college{s6ZHuOEQPftMcM8yPuA2Lv-Bm6u.0FM0MCNxvhMwISNwEyV}
pwm.college{s6ZGvPEPQfsMcM8yOvA3Mv-Bl7u.0FL0MDOwwiMwITNxEzW}
pwm.collegd{s5ZHvPEQQfsMcM7yPuA3Mv-Bm7u.0FM0LDOwwiMxITNxEzW}
pwm.colldge{s5ZHvPEQQftMcL8yOvA2Mv-Bm7u.0FM0MDOxwhMxITNxEzV}
pwm.colldge{s5ZHuPEQQetMcM7yPvA3Lu-Am6u.0FM0MCOxwiMxITNxEzW}
pwm.cokkege{s6ZHvOEQQfsMcM8yOvA2Mu-Bl7u.0FM0MDNxwhLxITNxEzV}
pwm.cnllefd{r6ZHvPEQPftLcL8yPuA3Mv-Bm7u.0FM0LCOxvhLxISNwEzW}
pwm.bolkdge{s5YGvPDQQftMbL7yPuA2Mu-Al7u.0EM0MDNwwiMxITNxEzW}
pwm.bokldge{r6ZGvOEQQfsMcL8yPvA3Mv-Bm7u.0EM0MCOxviMxITNxEzW}
pwm.bnkkege{s6ZGuPEQQfsMcM8yPvA3Lu-Bm7u.0EM0MDNxwhLxITNwEzW}
pvn.college{s5ZHvPEQQfsMbM8yPvA3Lv-Bm7u.0FL0MDOxwiMxHTNxEzV}
pvn.colldge{s6ZGvPDQQetLcM8yOvA2Lv-Bm7u.0FM0MDOxviLxHSNwEyW}
pvn.colkdge{s6YHvODQQetLbM7xPvA2Mv-Bl6t.0EM0MCOxwiMxISNwEzV}
pvn.colkdgd{s6YGvPDQQftMbL7xPuA3Mu-Bm7u.0FM0LDOwwhMxITNxEyW}
pvn.coklefe{s5ZHvPEPQfsMbL7yOvA3Lv-Bm7u.0FM0MCOxwiMxITNxEzV}
pvn.cnllege{s5ZGvPDPQetMcM8yPvA3Lv-Bl7u.0FM0MCNxwiMxITNwEzW}
pvn.cnlldge{r6ZHvPEPQesMcM8yPvA3Mv-Bm7u.0FM0MCOxwiMxITNwEzW}
pvn.cnlldge{r6YHvPEQQftMcM8yPvA2Mu-Bm6u.0FM0MDNxwiMxITNxEzW}
pvn.cnlldgd{r6ZHvPEPQftLcM8yPvA2Mv-Bm7t.0FL0MDNxwiMxHTNxEyV}
pvn.cnkldge{s5YHuPDPQetLbM8yPuA3Lv-Bl7t.0FL0LDOxwhMxHTNxEzV}
pvn.bollege{s5ZHvPEQQftMbL8xOuA3Lv-Bl7t.0FM0MDOxviMxISNxDzW}
pvn.bolldge{s6ZHuPDQQftMcL8xPvA3Mv-Am6t.0FM0MCNxwhMwITMwEyW}
pvn.bnlkdgd{s6ZGuPDQPftMcM7yPuA3Mv-Al7u.0FL0MDOxwiMxHTNxDzV}
pvm.collegd{s5ZHvPEQQftLcL7yOvA3Lu-Bl6t.0FM0MDOwwiMwISMwEzW}
pvm.colldfe{s6YHvPEQQftMcL8yPvA3Mv-Bl7u.0FM0MDOxwhMxISNwEyV}
pvm.bollege{r6ZHvPEQQftLcL7xOvA3Lu-Al7u.0FM0LDOwwiLxITNxEyW}
own.college{s6ZHuPEQQftLcM8yPvA3Mv-Bm6u.0FM0MDNxwiMwISNxEzW}
own.collegd{s6ZGvPDQPesMcM7yPvA3Lv-Bm6u.0FL0MDOxviMxITMwDzW}
own.collefe{r6ZHvPDPQetMcL8yOvA3Lv-Am7u.0EM0MDOwviMwHTNxEzV}
own.collefd{r6ZHuOEQQfsLbM8xPvA2Mv-Bl7u.0FL0MDNxwhMxITNxEzW}
own.colldge{s6ZHvPDQQetMcM8yPvA3Mv-Bm7t.0FL0MCOxwiMwITNxEzW}
own.colldfe{s5ZHuPEQQesMcM8xPvA2Lv-Bm6u.0FL0LDOwviLxHTNxEzW}
own.cnklegd{s5ZGvOEQQfsMcM7yOuA3Mv-Al7t.0FM0MCOwwiLxITMwDzW}
own.cnkkdfd{s5ZHuPDQQfsMcL8xPvA3Mv-Bl7t.0FL0MDNxviLxHSMxDyW}
own.bollefe{s6ZHvPEQQftMcM8yPvA3Mv-Bm6u.0FL0LDOxwiMxHTNxEzW}
own.boklege{s6YHuPEPQftMbM8yPuA2Lu-Al7t.0EL0MDNxviMxISNxEyV}
own.bokkege{s6ZHvPEQQftLcM8yPvA3Mv-Bm7t.0FM0MCOwwhMxITNxEyW}
own.bnllege{s5ZHvOEQPftLbL7yPuA3Mv-Am7u.0EL0MDOxviMxITNxEzW}
owm.colkege{s6ZHvPEPQesLbM8yPuA2Lv-Bm7u.0FL0MDOxwiMwITMwEzW}
ovn.colkege{s6ZHvPEPQfsMcM8yPvA2Mu-Am7t.0EM0MDOxwiLxHSNxEzW}
ovn.coklege{r6YHvPEQQftMcL7xOvA3Lu-Bm7u.0EM0MDNwvhLwHTNwDzW}
ovm.bolldge{s5ZHvPEQQftMcL8xOvA3Lv-Al6u.0EM0MCOwvhLxITMwEyV}
ovm.bnllege{r6ZHuPEPQetMcL8yOvA2Mu-Bl7u.0FM0LDOxwiLxISNxEyW}
```

### New Learnings
Brief note on what you learned from the challenge

### References 
Add any references or videos you used while solving the challenge.
