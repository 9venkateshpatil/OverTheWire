Hello guys!
As usual I joined the level 4 shell
And executed the ls cmd

And there was the same inhere dir in the ~ dir

then I navigated myself into that dir and accessed its list of files 
and there were multiple files prefixed with - .

>bandit4@bandit:~$ ls
inhere
>bandit4@bandit:~$ cd inhere
>bandit4@bandit:~/inhere$ ls
-file00  -file01  -file02  -file03  -file04  -file05  -file06  -file07  -file08  -file09
>bandit4@bandit:~/inhere$ la
-file00  -file01  -file02  -file03  -file04  -file05  -file06  -file07  -file08  -file09

So I manually accessed every one of them and found the password in the -file07

>bandit4@bandit:~/inhere$ cat ./-file00
�=
I�� ��V`n�5���ѳ��*�G^7cO�bandit4@bandit:~/inhere$ cat ./-file01
���0��w�8���q����Y���d����ZCF��+bandit4@bandit:~/inhere$ cat ./-file02
���     L����Q�.��`▒/▒��r
�P{bandit4@bandit:~/inhere$ cat ./-file03
���?�▒��1'�JV����,��2��
                       f�=����bandit4@bandit:~/inhere$ cat ./-file04
��us���*��w��Z ��Ї|��@�Sq-bandit4@bandit:~/inhere$ cat ./-file05
W�cF���[Q
�
 ��a~���\0�ed(��ڨWbandit4@bandit:~/inhere$ cat ./-file06
?z=J"��oyvbandit4@bandit:~/inhere$ cat ./-file07
4oQYVPkxZOOEOO5pTW81FB8j8lxXGUQw
bandit4@bandit:~/inhere$ cat ./-file08
Z���I��$ȩ�D��d���B~o�bandit4@bandit:~/inhere$ cat ./-file09
BG����`@J��eD֍�l�\���`�bandit4@bandit:~/inhere$ exit
logout
Connection to bandit.labs.overthewire.org closed.

And that's it guys 
Simple as that

Thank you !

_________

EDIT:

Guys it took me a while to understand that the thing we did is kinda long and too much manual
We could've just checked the file type and got to know which actually was a text file with the help of 'file' cmd

>bandit4@bandit:~/inhere$ file ./*
./-file00: data
./-file01: OpenPGP Public Key
./-file02: OpenPGP Public Key
./-file03: data
./-file04: data
./-file05: data
./-file06: data
./-file07: ASCII text
./-file08: data
./-file09: data

That clearly screams that -file07 is a ascii text file and then we access it .

Sorry for that silly mistake.
