Hello guys ! 
The webpage says this level is about strings cmd
The password for the next level is stored in the file data.txt in one of the few human-readable strings, preceded by several ‘=’ characters.

so i thought this might be a mixture of the usage of strings and grep using pipelining .

It was quite simple as I finished this level with just one command 

>bandit9@bandit:~$ strings data.txt | grep =
========== the
9=H`
[!#=Z
========== password
xWf=
f\Z'========== is
e=i{\#
/1=s
nS=F
M=Sl
=LGT
y =1
========== FGUW5ilLVJrxX9kMYMmlN4MgbpfMiqey

And here we go !
