Hello guys !
I hope you guys would not expect me to show the connection command and the password authentication in every level so lets skip that from now on.

Now lets go ahead and ls everything as usual.

>andit2@bandit:~$ ls
--spaces in this filename--

there's this file called --spaces in this filename-- in the ~ dir 

I thought it was same like previous level we will have to view it with './' .

>bandit2@bandit:~$ cat ./--spaces in this filename--
cat: ./--spaces: No such file or directory
cat: in: No such file or directory
cat: this: No such file or directory
cat: filename--: No such file or directory

It didn't worked so tried what I might get on the web page of level 2 
And they told to search for 
Google Search for “spaces in filename”

so I did and came back with incomplete info and tried few things:

>bandit2@bandit:~$ cat "--spaces in this filename--"
cat: unrecognized option '--spaces in this filename--'
Try 'cat --help' for more information.
>bandit2@bandit:~$ cat '--spaces in this filename--'
cat: unrecognized option '--spaces in this filename--'
Try 'cat --help' for more information.
>bandit2@bandit:~$ cat --spaces\ in\ this\ filename--
cat: unrecognized option '--spaces in this filename--'
Try 'cat --help' for more information.

And I failed miserably, so I tried to access more information on google and then I found out we have to something like this :

>bandit2@bandit:~$ cat "./--spaces in this filename--"
MNk8KNH3Usiio41PRUEoDFPqfxLPlSmx

That's it guys we found our password .

And i exited from the shell.

>bandit2@bandit:~$ exit
logout
Connection to bandit.labs.overthewire.org closed.

