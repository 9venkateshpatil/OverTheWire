Hello guys !

Bandit5 level was kinda long for me lol. But eventually I found the password.
Like last time I connected to shell and got to know there is inhere dir again 
And I navigated to it and did a ls again and there were like 20 more directories 

I don't know why I didn't accessed the level 5 webpage and just 'cd' my way to all dirs and listed the contents of all of them,
although each and every one of em had the same content. I thought there might be something unique for one of them but I was unsuccessful.

>bandit5@bandit:~$ ls
inhere
>bandit5@bandit:~$ cd inhere
>bandit5@bandit:~/inhere$ ls
maybehere00  maybehere02  maybehere04  maybehere06  maybehere08  maybehere10  maybehere12  maybehere14  maybehere16  maybehere18
maybehere01  maybehere03  maybehere05  maybehere07  maybehere09  maybehere11  maybehere13  maybehere15  maybehere17  maybehere19

>bandit5@bandit:~/inhere$ cd maybehere00
bandit5@bandit:~/inhere/maybehere00$ ls
-file1  -file2  -file3  spaces file1  spaces file2  spaces file3
bandit5@bandit:~/inhere/maybehere00$ cd
bandit5@bandit:~$ cd inhere/maybehere00
bandit5@bandit:~/inhere/maybehere00$ cd ../maybehere01
bandit5@bandit:~/inhere/maybehere01$ ls
-file1  -file2  -file3  spaces file1  spaces file2  spaces file3
bandit5@bandit:~/inhere/maybehere01$ cd ../maybehere02
bandit5@bandit:~/inhere/maybehere02$ ls
-file1  -file2  -file3  spaces file1  spaces file2  spaces file3
bandit5@bandit:~/inhere/maybehere02$ cd ../maybehere03
bandit5@bandit:~/inhere/maybehere03$ ls
-file1  -file2  -file3  spaces file1  spaces file2  spaces file3
bandit5@bandit:~/inhere/maybehere03$ cd ../maybehere04
bandit5@bandit:~/inhere/maybehere04$ ls
-file1  -file2  -file3  spaces file1  spaces file2  spaces file3
bandit5@bandit:~/inhere/maybehere04$ cd ../maybehere05
bandit5@bandit:~/inhere/maybehere05$ ls
-file1  -file2  -file3  spaces file1  spaces file2  spaces file3
bandit5@bandit:~/inhere/maybehere05$ cd ../maybehere06
bandit5@bandit:~/inhere/maybehere06$ ls
-file1  -file2  -file3  spaces file1  spaces file2  spaces file3
bandit5@bandit:~/inhere/maybehere06$ cd ../maybehere07
bandit5@bandit:~/inhere/maybehere07$ ls
-file1  -file2  -file3  spaces file1  spaces file2  spaces file3
bandit5@bandit:~/inhere/maybehere07$ cd ../maybehere08
bandit5@bandit:~/inhere/maybehere08$ ls
-file1  -file2  -file3  spaces file1  spaces file2  spaces file3
bandit5@bandit:~/inhere/maybehere08$ cd ../maybehere09
bandit5@bandit:~/inhere/maybehere09$ ls
-file1  -file2  -file3  spaces file1  spaces file2  spaces file3
bandit5@bandit:~/inhere/maybehere09$ cd ../maybehere10
bandit5@bandit:~/inhere/maybehere10$ ls
-file1  -file2  -file3  spaces file1  spaces file2  spaces file3
bandit5@bandit:~/inhere/maybehere10$ cd ../maybehere11
bandit5@bandit:~/inhere/maybehere11$ ls
-file1  -file2  -file3  spaces file1  spaces file2  spaces file3
bandit5@bandit:~/inhere/maybehere11$ cd ../maybehere12
bandit5@bandit:~/inhere/maybehere12$ ls
-file1  -file2  -file3  spaces file1  spaces file2  spaces file3
bandit5@bandit:~/inhere/maybehere12$ cd ../maybehere13
bandit5@bandit:~/inhere/maybehere13$ ls
-file1  -file2  -file3  spaces file1  spaces file2  spaces file3
bandit5@bandit:~/inhere/maybehere13$ cd ../maybehere14
bandit5@bandit:~/inhere/maybehere14$ ls
-file1  -file2  -file3  spaces file1  spaces file2  spaces file3
bandit5@bandit:~/inhere/maybehere14$ cd ../maybehere15
bandit5@bandit:~/inhere/maybehere15$ ls
-file1  -file2  -file3  spaces file1  spaces file2  spaces file3
bandit5@bandit:~/inhere/maybehere15$ cd ../maybehere16
bandit5@bandit:~/inhere/maybehere16$ ls
-file1  -file2  -file3  spaces file1  spaces file2  spaces file3
bandit5@bandit:~/inhere/maybehere16$ cd ../maybehere17
bandit5@bandit:~/inhere/maybehere17$ ls
-file1  -file2  -file3  spaces file1  spaces file2  spaces file3
bandit5@bandit:~/inhere/maybehere17$ cd ../maybehere18
bandit5@bandit:~/inhere/maybehere18$ 
bandit5@bandit:~/inhere/maybehere18$ ls
-file1  -file2  -file3  spaces file1  spaces file2  spaces file3

And then I felt to visit the webpage and it mentioned that the password was in a file which had this attributes:

    human-readable
    1033 bytes in size
    not executable

So I started accessing the long lists of every dir by the 'll' command which is short for 'ls -l'
This time I followed reverse approach like from maybehere19 to maybehere00 dir
Only thing I was looking for a file sized 1033.

bandit5@bandit:~/inhere/maybehere18$ ls
-file1  -file2  -file3  spaces file1  spaces file2  spaces file3
bandit5@bandit:~/inhere/maybehere18$ ll
total 68
drwxr-x---  2 root bandit5 4096 Oct 14 09:26 ./
drwxr-x--- 22 root bandit5 4096 Oct 14 09:26 ../
-rwxr-x---  1 root bandit5 9697 Oct 14 09:26 -file1*
-rwxr-x---  1 root bandit5 5702 Oct 14 09:26 .file1*
-rw-r-----  1 root bandit5   77 Oct 14 09:26 -file2
-rw-r-----  1 root bandit5 2084 Oct 14 09:26 .file2
-rwxr-x---  1 root bandit5 2306 Oct 14 09:26 -file3*
-rwxr-x---  1 root bandit5  154 Oct 14 09:26 .file3*
-rwxr-x---  1 root bandit5 7334 Oct 14 09:26 spaces file1*
-rw-r-----  1 root bandit5 6348 Oct 14 09:26 spaces file2
-rwxr-x---  1 root bandit5 7040 Oct 14 09:26 spaces file3*
bandit5@bandit:~/inhere/maybehere18$ cd ../maybehere19
bandit5@bandit:~/inhere/maybehere19$ ll
total 76
drwxr-x---  2 root bandit5 4096 Oct 14 09:26 ./
drwxr-x--- 22 root bandit5 4096 Oct 14 09:26 ../
-rwxr-x---  1 root bandit5 6302 Oct 14 09:26 -file1*
-rwxr-x---  1 root bandit5 7209 Oct 14 09:26 .file1*
-rw-r-----  1 root bandit5 5594 Oct 14 09:26 -file2
-rw-r-----  1 root bandit5 4740 Oct 14 09:26 .file2
-rwxr-x---  1 root bandit5 7965 Oct 14 09:26 -file3*
-rwxr-x---  1 root bandit5  494 Oct 14 09:26 .file3*
-rwxr-x---  1 root bandit5 7186 Oct 14 09:26 spaces file1*
-rw-r-----  1 root bandit5 8785 Oct 14 09:26 spaces file2
-rwxr-x---  1 root bandit5 2307 Oct 14 09:26 spaces file3*
bandit5@bandit:~/inhere/maybehere19$ cd ../maybehere17
bandit5@bandit:~/inhere/maybehere17$ ll
total 72
drwxr-x---  2 root bandit5 4096 Oct 14 09:26 ./
drwxr-x--- 22 root bandit5 4096 Oct 14 09:26 ../
-rwxr-x---  1 root bandit5 1133 Oct 14 09:26 -file1*
-rwxr-x---  1 root bandit5  895 Oct 14 09:26 .file1*
-rw-r-----  1 root bandit5 1791 Oct 14 09:26 -file2
-rw-r-----  1 root bandit5 8341 Oct 14 09:26 .file2
-rwxr-x---  1 root bandit5 4422 Oct 14 09:26 -file3*
-rwxr-x---  1 root bandit5 5094 Oct 14 09:26 .file3*
-rwxr-x---  1 root bandit5 8361 Oct 14 09:26 spaces file1*
-rw-r-----  1 root bandit5 3387 Oct 14 09:26 spaces file2
-rwxr-x---  1 root bandit5 6381 Oct 14 09:26 spaces file3*
bandit5@bandit:~/inhere/maybehere17$ cd ../maybehere16
bandit5@bandit:~/inhere/maybehere16$ ll
total 80
drwxr-x---  2 root bandit5 4096 Oct 14 09:26 ./
drwxr-x--- 22 root bandit5 4096 Oct 14 09:26 ../
-rwxr-x---  1 root bandit5 4277 Oct 14 09:26 -file1*
-rwxr-x---  1 root bandit5 5426 Oct 14 09:26 .file1*
-rw-r-----  1 root bandit5 5301 Oct 14 09:26 -file2
-rw-r-----  1 root bandit5 8472 Oct 14 09:26 .file2
-rwxr-x---  1 root bandit5 8085 Oct 14 09:26 -file3*
-rwxr-x---  1 root bandit5 1148 Oct 14 09:26 .file3*
-rwxr-x---  1 root bandit5 9773 Oct 14 09:26 spaces file1*
-rw-r-----  1 root bandit5 3146 Oct 14 09:26 spaces file2
-rwxr-x---  1 root bandit5 7509 Oct 14 09:26 spaces file3*
bandit5@bandit:~/inhere/maybehere16$ cd ../maybehere15
bandit5@bandit:~/inhere/maybehere15$ ll
total 64
drwxr-x---  2 root bandit5 4096 Oct 14 09:26 ./
drwxr-x--- 22 root bandit5 4096 Oct 14 09:26 ../
-rwxr-x---  1 root bandit5 8794 Oct 14 09:26 -file1*
-rwxr-x---  1 root bandit5 2159 Oct 14 09:26 .file1*
-rw-r-----  1 root bandit5 9499 Oct 14 09:26 -file2
-rw-r-----  1 root bandit5  279 Oct 14 09:26 .file2
-rwxr-x---  1 root bandit5 6299 Oct 14 09:26 -file3*
-rwxr-x---  1 root bandit5  742 Oct 14 09:26 .file3*
-rwxr-x---  1 root bandit5 1623 Oct 14 09:26 spaces file1*
-rw-r-----  1 root bandit5   51 Oct 14 09:26 spaces file2
-rwxr-x---  1 root bandit5 1637 Oct 14 09:26 spaces file3*
bandit5@bandit:~/inhere/maybehere15$ cd ../maybehere14
bandit5@bandit:~/inhere/maybehere14$ ll
total 60
drwxr-x---  2 root bandit5 4096 Oct 14 09:26 ./
drwxr-x--- 22 root bandit5 4096 Oct 14 09:26 ../
-rwxr-x---  1 root bandit5 4282 Oct 14 09:26 -file1*
-rwxr-x---  1 root bandit5 3427 Oct 14 09:26 .file1*
-rw-r-----  1 root bandit5 8351 Oct 14 09:26 -file2
-rw-r-----  1 root bandit5 1503 Oct 14 09:26 .file2
-rwxr-x---  1 root bandit5 3756 Oct 14 09:26 -file3*
-rwxr-x---  1 root bandit5 4821 Oct 14 09:26 .file3*
-rwxr-x---  1 root bandit5 1382 Oct 14 09:26 spaces file1*
-rw-r-----  1 root bandit5  871 Oct 14 09:26 spaces file2
-rwxr-x---  1 root bandit5  376 Oct 14 09:26 spaces file3*
bandit5@bandit:~/inhere/maybehere14$ cd ../maybehere13
bandit5@bandit:~/inhere/maybehere13$ ll
total 64
drwxr-x---  2 root bandit5 4096 Oct 14 09:26 ./
drwxr-x--- 22 root bandit5 4096 Oct 14 09:26 ../
-rwxr-x---  1 root bandit5 1359 Oct 14 09:26 -file1*
-rwxr-x---  1 root bandit5 5258 Oct 14 09:26 .file1*
-rw-r-----  1 root bandit5 1423 Oct 14 09:26 -file2
-rw-r-----  1 root bandit5 8952 Oct 14 09:26 .file2
-rwxr-x---  1 root bandit5 3014 Oct 14 09:26 -file3*
-rwxr-x---  1 root bandit5 6965 Oct 14 09:26 .file3*
-rwxr-x---  1 root bandit5 3952 Oct 14 09:26 spaces file1*
-rw-r-----  1 root bandit5  952 Oct 14 09:26 spaces file2
-rwxr-x---  1 root bandit5 4389 Oct 14 09:26 spaces file3*
bandit5@bandit:~/inhere/maybehere13$ cd ../maybehere12
bandit5@bandit:~/inhere/maybehere12$ ll
total 72
drwxr-x---  2 root bandit5 4096 Oct 14 09:26 ./
drwxr-x--- 22 root bandit5 4096 Oct 14 09:26 ../
-rwxr-x---  1 root bandit5 9678 Oct 14 09:26 -file1*
-rwxr-x---  1 root bandit5 5815 Oct 14 09:26 .file1*
-rw-r-----  1 root bandit5  251 Oct 14 09:26 -file2
-rw-r-----  1 root bandit5 8244 Oct 14 09:26 .file2
-rwxr-x---  1 root bandit5 9076 Oct 14 09:26 -file3*
-rwxr-x---  1 root bandit5 1022 Oct 14 09:26 .file3*
-rwxr-x---  1 root bandit5 2157 Oct 14 09:26 spaces file1*
-rw-r-----  1 root bandit5 2460 Oct 14 09:26 spaces file2
-rwxr-x---  1 root bandit5 1639 Oct 14 09:26 spaces file3*
bandit5@bandit:~/inhere/maybehere12$ cd ../maybehere11
bandit5@bandit:~/inhere/maybehere11$ ll
total 72
drwxr-x---  2 root bandit5 4096 Oct 14 09:26 ./
drwxr-x--- 22 root bandit5 4096 Oct 14 09:26 ../
-rwxr-x---  1 root bandit5 1211 Oct 14 09:26 -file1*
-rwxr-x---  1 root bandit5  452 Oct 14 09:26 .file1*
-rw-r-----  1 root bandit5 4559 Oct 14 09:26 -file2
-rw-r-----  1 root bandit5 2501 Oct 14 09:26 .file2
-rwxr-x---  1 root bandit5 8854 Oct 14 09:26 -file3*
-rwxr-x---  1 root bandit5 8261 Oct 14 09:26 .file3*
-rwxr-x---  1 root bandit5 3147 Oct 14 09:26 spaces file1*
-rw-r-----  1 root bandit5  503 Oct 14 09:26 spaces file2
-rwxr-x---  1 root bandit5 8845 Oct 14 09:26 spaces file3*
bandit5@bandit:~/inhere/maybehere11$ cd ../maybehere10
bandit5@bandit:~/inhere/maybehere10$ ll
total 56
drwxr-x---  2 root bandit5 4096 Oct 14 09:26 ./
drwxr-x--- 22 root bandit5 4096 Oct 14 09:26 ../
-rwxr-x---  1 root bandit5 1052 Oct 14 09:26 -file1*
-rwxr-x---  1 root bandit5 7092 Oct 14 09:26 .file1*
-rw-r-----  1 root bandit5 1991 Oct 14 09:26 -file2
-rw-r-----  1 root bandit5   99 Oct 14 09:26 .file2
-rwxr-x---  1 root bandit5 1237 Oct 14 09:26 -file3*
-rwxr-x---  1 root bandit5 2961 Oct 14 09:26 .file3*
-rwxr-x---  1 root bandit5 8269 Oct 14 09:26 spaces file1*
-rw-r-----  1 root bandit5 3570 Oct 14 09:26 spaces file2
-rwxr-x---  1 root bandit5 2155 Oct 14 09:26 spaces file3*
bandit5@bandit:~/inhere/maybehere10$ cd ../maybehere09
bandit5@bandit:~/inhere/maybehere09$ ll
total 76
drwxr-x---  2 root bandit5 4096 Oct 14 09:26 ./
drwxr-x--- 22 root bandit5 4096 Oct 14 09:26 ../
-rwxr-x---  1 root bandit5 3628 Oct 14 09:26 -file1*
-rwxr-x---  1 root bandit5 6763 Oct 14 09:26 .file1*
-rw-r-----  1 root bandit5  774 Oct 14 09:26 -file2
-rw-r-----  1 root bandit5 8517 Oct 14 09:26 .file2
-rwxr-x---  1 root bandit5 7961 Oct 14 09:26 -file3*
-rwxr-x---  1 root bandit5 3798 Oct 14 09:26 .file3*
-rwxr-x---  1 root bandit5 5301 Oct 14 09:26 spaces file1*
-rw-r-----  1 root bandit5 8716 Oct 14 09:26 spaces file2
-rwxr-x---  1 root bandit5 7569 Oct 14 09:26 spaces file3*
bandit5@bandit:~/inhere/maybehere09$ cd ../maybehere08
bandit5@bandit:~/inhere/maybehere08$ ll
total 56
drwxr-x---  2 root bandit5 4096 Oct 14 09:26 ./
drwxr-x--- 22 root bandit5 4096 Oct 14 09:26 ../
-rwxr-x---  1 root bandit5 1077 Oct 14 09:26 -file1*
-rwxr-x---  1 root bandit5 8169 Oct 14 09:26 .file1*
-rw-r-----  1 root bandit5 3825 Oct 14 09:26 -file2
-rw-r-----  1 root bandit5  747 Oct 14 09:26 .file2
-rwxr-x---  1 root bandit5 2650 Oct 14 09:26 -file3*
-rwxr-x---  1 root bandit5 2217 Oct 14 09:26 .file3*
-rwxr-x---  1 root bandit5  215 Oct 14 09:26 spaces file1*
-rw-r-----  1 root bandit5 3693 Oct 14 09:26 spaces file2
-rwxr-x---  1 root bandit5 9138 Oct 14 09:26 spaces file3*
bandit5@bandit:~/inhere/maybehere08$ cd ../maybehere07
bandit5@bandit:~/inhere/maybehere07$ ll
total 56
drwxr-x---  2 root bandit5 4096 Oct 14 09:26 ./
drwxr-x--- 22 root bandit5 4096 Oct 14 09:26 ../
-rwxr-x---  1 root bandit5 3663 Oct 14 09:26 -file1*
-rwxr-x---  1 root bandit5 3065 Oct 14 09:26 .file1*
-rw-r-----  1 root bandit5 2488 Oct 14 09:26 -file2
-rw-r-----  1 root bandit5 1033 Oct 14 09:26 .file2
-rwxr-x---  1 root bandit5 3362 Oct 14 09:26 -file3*
-rwxr-x---  1 root bandit5 1997 Oct 14 09:26 .file3*
-rwxr-x---  1 root bandit5 4130 Oct 14 09:26 spaces file1*
-rw-r-----  1 root bandit5 9064 Oct 14 09:26 spaces file2
-rwxr-x---  1 root bandit5 1022 Oct 14 09:26 spaces file3*

And voila! I found a non executable file sized exactly 1033 in bytes
I accessed it and got the password 

>bandit5@bandit:~/inhere/maybehere07$ cat .file2
HWasnPhtq9AVKe0dmk45nxy20cvUa6EG
                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       bandit5@bandit:~/inhere/maybehere07$ exit
logout
Connection to bandit.labs.overthewire.org closed.


Thank you !
Until next time.

____________________________________

EDIT:

Guys I just realized we should've used find command instead of just manually trying to find the file with 1033 bytes in size 

Im so dumb 

The syntax is as follows 
>bandit5@bandit:~/inhere$ find . -type f -size 1033c ! -executable
./maybehere07/.file2

It directly gives the path of the file of this type .
Man it was no baller but I messed up .

Thank you !
