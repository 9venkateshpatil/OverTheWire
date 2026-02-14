Hello guys !

At first I examined what this level is actually about and it explicityly mentioned 
The password for the next level is stored in the file data.txt next to the word millionth

So it was clearly a grep command level 

So as soon as I entered the shell I executed the ls command and there was only one file called data.txt as I expected.
I was curious so i view the content of the file, which was so much, that it would be impossible to manually find the millionth.

>bandit7@bandit:~$ grep millionth data.txt
millionth       dfwvzFQi4mU0wfNbFOe9RoWskMLg7eEc

That's it 

Thank you ! 
