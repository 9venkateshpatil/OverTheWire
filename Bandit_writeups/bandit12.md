Hello guys !

I would definitely call this level the hardest till now coz it has no shortcuts 
It is supposed to be procedural.

Let's dive in .

First the level goals :
The password for the next level is stored in the file data.txt, which is a hexdump of a file that has been repeatedly compressed. For this level it may be useful to create a directory under /tmp in which you can work. Use mkdir with a hard to guess directory name. Or better, use the command “mktemp -d”.
Then copy the datafile using cp, and rename it using mv (read the manpages!)

As it suggested to create a dir using mktemp -d , i did created one .
>bandit12@bandit:~$ mktemp -d
/tmp/tmp.MTooLNWL1G

>bandit12@bandit:~$ cd /tmp/tmp.MTooLNWL1G
>bandit12@bandit:/tmp/tmp.MTooLNWL1G$ 

Here every compression and decompression will take place !

>bandit12@bandit:/tmp/tmp.MTooLNWL1G$ cp ~/data.txt .
>bandit12@bandit:/tmp/tmp.MTooLNWL1G$ ls
data.txt

>bandit12@bandit:/tmp/tmp.MTooLNWL1G$ xxd -r data.txt > data.bin
>bandit12@bandit:/tmp/tmp.MTooLNWL1G$ cat data.bin
���▒�4z�i�F�hh▒@hh91AY&SY�v��▒�����������W����׋���������=������:��
a�E~^��U▒�drc|Y����8���5!�a&�E����y�m")����F��@���L�H@�M4212aF��▒�
         �
          ���>w7:�+2W�
{�3��ק|ڰ��G�[ڷ�%s     ▒���b���2bj���2+o�D�,I������]N�D��Ł�����)����5d`c��luy��T�&!ֈ�$i�.B)oz�XJ.�#�%/+�V�_�C-O%��)N����a
                 ����!�PS�$���a"��+�=h�G��!�Xz2gƗ^�%|(*������$izt�g>�#^m��      :��nDM���g��d���_�K���)A0!A�\(��_s���7���/��Ak���T��
                                                                                                                                   -q`!]��̰�G�<Ҧ������)���XV[�

This was the data.bin. Then I tried to understand its type 

>bandit12@bandit:/tmp/tmp.MTooLNWL1G$ file data.bin
data.bin: gzip compressed data, was "data2.bin", last modified: Tue Oct 14 09:26:06 2025, max compression, from Unix, original size modulo 2^32 564

It is a gzip compressed data so we will have to gunzip it.

>bandit12@bandit:/tmp/tmp.MTooLNWL1G$ mv data.bin data.gz
>bandit12@bandit:/tmp/tmp.MTooLNWL1G$ gunzip data.gz
>bandit12@bandit:/tmp/tmp.MTooLNWL1G$ ls
data  data.txt

First I renamed it to data.gz so it would be capable of getting gunzipped .

Then again we gotta identify its type as it is compressed multiple times 

>bandit12@bandit:/tmp/tmp.MTooLNWL1G$ file data
data: bzip2 compressed data, block size = 900k

compression is now bzip2

>bandit12@bandit:/tmp/tmp.MTooLNWL1G$ mv data data.bz2
>bandit12@bandit:/tmp/tmp.MTooLNWL1G$ bunzip2 data.bz2
>bandit12@bandit:/tmp/tmp.MTooLNWL1G$ ls
data  data.txt

Then ones more

>bandit12@bandit:/tmp/tmp.MTooLNWL1G$ mv data data.gz
>bandit12@bandit:/tmp/tmp.MTooLNWL1G$ gzip data.gz
gzip: data.gz already has .gz suffix -- unchanged
>bandit12@bandit:/tmp/tmp.MTooLNWL1G$ gunzip data.gz
>bandit12@bandit:/tmp/tmp.MTooLNWL1G$ ls
data  data.txt
>bandit12@bandit:/tmp/tmp.MTooLNWL1G$ file data
data: POSIX tar archive (GNU)

Now we are with a tar file

bandit12@bandit:/tmp/tmp.MTooLNWL1G$ tar -xf data
bandit12@bandit:/tmp/tmp.MTooLNWL1G$ ls
data  data5.bin  data.txt
bandit12@bandit:/tmp/tmp.MTooLNWL1G$ file data5.bin
data5.bin: POSIX tar archive (GNU)
bandit12@bandit:/tmp/tmp.MTooLNWL1G$ tar -xf data5.bin
bandit12@bandit:/tmp/tmp.MTooLNWL1G$ ls
data  data5.bin  data6.bin  data.txt
bandit12@bandit:/tmp/tmp.MTooLNWL1G$ file data6.bin
data6.bin: bzip2 compressed data, block size = 900k
bandit12@bandit:/tmp/tmp.MTooLNWL1G$ mv data6.bin data6.bz2
bandit12@bandit:/tmp/tmp.MTooLNWL1G$ bunzip data6.bz2
Command 'bunzip' not found, did you mean:
  command 'lunzip' from deb lunzip (1.13-6)
  command 'gunzip' from deb gzip (1.12-1ubuntu3.1)
  command 'ebunzip' from deb eb-utils (4.4.3-14)
  command 'bunzip3' from deb bzip3 (1.3.2-1)
  command 'unzip' from deb unzip (6.0-28ubuntu4.1)
  command 'funzip' from deb unzip (6.0-28ubuntu4.1)
  command 'bunzip2' from deb bzip2 (1.0.8-5.1build0.1)
  command 'runzip' from deb rzip (2.1-4.1)
Try: apt install <deb name>
bandit12@bandit:/tmp/tmp.MTooLNWL1G$ bunzip2 data6.bz2
bandit12@bandit:/tmp/tmp.MTooLNWL1G$ ls
data  data5.bin  data6  data.txt
bandit12@bandit:/tmp/tmp.MTooLNWL1G$ file data6
data6: POSIX tar archive (GNU)
bandit12@bandit:/tmp/tmp.MTooLNWL1G$ tar -xf data6
bandit12@bandit:/tmp/tmp.MTooLNWL1G$ ls
data  data5.bin  data6  data8.bin  data.txt
bandit12@bandit:/tmp/tmp.MTooLNWL1G$ file data8.bin
data8.bin: gzip compressed data, was "data9.bin", last modified: Tue Oct 14 09:26:06 2025, max compression, from Unix, original size modulo 2^32 49
bandit12@bandit:/tmp/tmp.MTooLNWL1G$ mv data8.bin data8.gz
bandit12@bandit:/tmp/tmp.MTooLNWL1G$ gunzip data8.gz
bandit12@bandit:/tmp/tmp.MTooLNWL1G$ file data8
data8: ASCII text

After so many indentification and decompression We finally got our ASCII text.
Which was what we were looking for .

That's it I outputted it and voila !

>bandit12@bandit:/tmp/tmp.MTooLNWL1G$ cat data8
The password is FO5dwFsc0cbaIiH0h8J2eUks2vdTDwAn

