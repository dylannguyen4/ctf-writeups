# Bandit 0

Enter `ssh bandit0@bandit.labs.overthewire.org -p 2220` into your console

If you have other ssh keys installed, I recommend you use
`ssh -o 'PubkeyAuthentication no' bandit20@bandit.labs.overthewire.org -p 2220`

When it prompts you for a password, enter `bandit0`

You should be logged in

# Bandit 1

Type `ls`. You should see a file called `readme`. Execute `cat readme`.

The password for the next level is `boJ9jbbUNNfktd78OOpsqOltutMc3MY1`

Copy this password and type `exit`

# Bandit 2 

Login using `ssh bandit1@bandit.labs.overthewire.org -p 2220` and password `boJ9jbbUNNfktd78OOpsqOltutMc3MY1`

Type `ls`. You should see a file called `-`. However, `cat -` does not seem to work. 

To circumvent this, use `cat ~/-`

The password is `CV1DtqXWVFXTvM2F0k09SHz0YwRINYA9`

Type `exit

# Bandit 3

Login using `ssh bandit2@bandit.labs.overthewire.org -p 2220` and password `CV1DtqXWVFXTvM2F0k09SHz0YwRINYA9`

Type `cat spaces` then enter the tab button. It should autocomplete. 

The password is `UmHadQclWmgdLOKQ3YNgjWxGoRMb5luK`

# Bandit 4

Login using `ssh bandit3@bandit.labs.overthewire.org -p 2220` and password `UmHadQclWmgdLOKQ3YNgjWxGoRMb5luK`

Naviagte to the `inhere` directory using `cd inhere`

Type `ls`. There shouldn't be any files. Type `find .`. You should see a file named `.hidden`

Input `cat .hidden`

The password is `pIwrPrtPN36QITSp3EQaw936yaFoFgAB`

# Bandit 5

Login using `ssh bandit4@bandit.labs.overthewire.org -p 2220` and password `pIwrPrtPN36QITSp3EQaw936yaFoFgAB` and then type `cd inhere`

The only human-readable file will contain ASCII text. You can find this file using `file ~/inhere/*`

You should see that the only file that uses ASCII text is `-file07`

Type `cat ~/inhere/-file07`

The password is `koReBOKuIDDepwhWk7jZC0RTdopnAYKh`

# Bandit 6

Login using `ssh bandit5@bandit.labs.overthewire.org -p 2220` and password `pIwrPrtPN36QITSp3EQaw936yaFoFgAB`

In order to find a file that is human-readable, 1033 bytes in size, and not executable, you must use the command `find . -size 1033c -readable ! -executable`

The command points at the file `./inhere/maybehere07/.file2`

Type `cat ./inhere/maybehere07/.file2`

The password is `DXjZPULLxYr17uwoI01bNLQbtFemEgo7`

# Bandit 7

Login using `ssh bandit6@bandit.labs.overthewire.org -p 2220` and password `DXjZPULLxYr17uwoI01bNLQbtFemEgo7`

Use the command `find / -size 33c -user bandit7 -group bandit6` to find all files owned by user bandit7, owned by group bandit6, and 33 bytes in size. You can change the command to `find / -size 33c -user bandit7 -group bandit6 2> /dev/null` in order to get rid of useless errors.

It should return `/var/lib/dpkg/info/bandit7.password`. `cat` the file.

The password is `HKBPTKQnIay4Fw76bEy8PVxKEDQRKTzs`

# Bandit 8

Login using `ssh bandit7@bandit.labs.overthewire.org -p 2220` and password `HKBPTKQnIay4Fw76bEy8PVxKEDQRKTzs`

Use `cat data.txt | grep "millionth"` to find the line with `millionth`

The password is `cvX2JJa4CFALtqS87jk27qwqGhBM9plV`

# Bandit 9

Login using `ssh bandit8@bandit.labs.overthewire.org -p 2220` and password `cvX2JJa4CFALtqS87jk27qwqGhBM9plV`

Use `cat data.txt | sort | uniq -u` to search for unique lines

The password is `UsvVyFSfZZWbi6wgC7dAFyFuR6jQQUhR`

# Bandit 10

Login using `ssh bandit9@bandit.labs.overthewire.org -p 2220` and password `UsvVyFSfZZWbi6wgC7dAFyFuR6jQQUhR`

Use `strings data.txt | grep "=="` to find all lines with strings that start with "==".

The password is `truKLdjsbJ5g7yyJ2X2R0o3a5HQJFuLk`


