Hello guys 
As you guys might know we got into the bandit14 user's shell via the sshkey 
It was cool to finally get access of the system.

Now let's see how will we get the password for the 15th level
This is the level goal :
The password for the next level can be retrieved by submitting the password of the current level to port 30000 on localhost.
So lets see for the password in the /etc dir first.

>bandit14@bandit:/etc$ ls /etc | grep bandit
bandit_pass
issue.bandit
issue.bandit.fail
issue.bandit.localhost

so the password is in the bandit_pass file

>bandit14@bandit:/etc$ cd bandit_pass
>bandit14@bandit:/etc/bandit_pass$ ls
bandit0   bandit11  bandit14  bandit17  bandit2   bandit22  bandit25  bandit28  bandit30  bandit33  bandit6  bandit9
bandit1   bandit12  bandit15  bandit18  bandit20  bandit23  bandit26  bandit29  bandit31  bandit4   bandit7
bandit10  bandit13  bandit16  bandit19  bandit21  bandit24  bandit27  bandit3   bandit32  bandit5   bandit8
>bandit14@bandit:/etc/bandit_pass$ cat bandit0
cat: bandit0: Permission denied
>bandit14@bandit:/etc/bandit_pass$ cat bandit14
MU4VWeTyJk8ROof1qqmcBPaLh7lDCPvS

bandit14@bandit:/etc/bandit_pass$ nc localhost 30000
MU4VWeTyJk8ROof1qqmcBPaLh7lDCPvS
Correct!
8xCjnmgoKbGLhHFAZlGE5Tmu4M2tKJQo

There we go !
Thank you !!

