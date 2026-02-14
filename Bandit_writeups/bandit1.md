Hello guys 
Today I will let you guys know how I completed the level 1 in BAndit

First as usual I connected to the shell via

>ssh bandit1@bandit.labs.overthewire.org -p 2220

with the password I previously got in level 0 .

Then as soon I was connected what I did was list everything in the home dir.

>bandit1@bandit:~$ ls
-

Got to know there's a file named as hyphen '-' 

I tried opening it but I couldn't

>bandit1@bandit:~$ cat -
^C

Then I accessed the tab of Level 1 on overthewire website 
Which provided me with some learning materials as follow 
Helpful Reading Material

    Google Search for “dashed filename”
I searched this and got to know that file starting with '-' can't be opened by just 'cat -' coz terminal might think there's some type of options you
want to add to that command so we have to add './' before the file name and so I did.

>bandit1@bandit:~$ cat ./-
263JGJPfgU6LtdEvgfWU1XP5yac29mFx

And here's the password.

Thank you.
