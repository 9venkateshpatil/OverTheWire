Hello guys 
The level 19 of bandit is nothing but a introductory level to the suid or setuid which stands for set user id.
Now what is this?
it is nothing but another permissions like rwx but here only catch is that whoever or whichever user will run such a file with s permission to the owner
here bandit20 and the user is bandit19
will run that particular file as the owner of the file thats it 

And it's clearly mentioned on the webpage of the level that the password is in the bandit_pass dir in /etc so bandit19 will access this file as bandit20
So we could see the password.

>bandit19@bandit:~$ ll
total 36
drwxr-xr-x   2 root     root      4096 Oct 14 09:26 ./
drwxr-xr-x 150 root     root      4096 Oct 14 09:29 ../
-rwsr-x---   1 bandit20 bandit19 14884 Oct 14 09:26 bandit20-do*
-rw-r--r--   1 root     root       220 Mar 31  2024 .bash_logout
-rw-r--r--   1 root     root      3851 Oct 14 09:19 .bashrc
-rw-r--r--   1 root     root       807 Mar 31  2024 .profile

Here the x is replaced by s for the bandit20-do file so you know the thing now .

>bandit19@bandit:~$ ./bandit20-do
Run a command as another user.
  Example: ./bandit20-do whoami
>bandit19@bandit:~$ ./bandit20-do cat /etc/bandit_pass/bandit_19
cat: /etc/bandit_pass/bandit_19: No such file or directory
>bandit19@bandit:~$ ./bandit20-do cat /etc/bandit_pass/bandit19
cat: /etc/bandit_pass/bandit19: Permission denied
>bandit19@bandit:~$ ./bandit20-do cat /etc/bandit_pass/bandit20
0qXahG8ZjOVMN9Ghs7iOWsCfZyXOUbYO

There it is !
Thank you !
