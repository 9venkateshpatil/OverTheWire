Hello guys!

This level's mentioned goal is :
The password for the next level is stored in the file data.txt, where all lowercase (a-z) and uppercase (A-Z) letters have been rotated by 13 positions

So it is a combination of both cat and tr cmd 

It was by far the most simple level of this  module

>bandit11@bandit:~$ cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'
The password is 7x16WNeHIi5YkIhWsfFIqoognUTyj9Q4

That's it ! 
