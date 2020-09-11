# Bandit 11
Access the next challenge using `ssh bandit11@bandit.labs.overthewire.org -p 2220` and password `IFukwKGsFW8MOq3IRFqrxE1hxTNEbUPR`

Run the command `cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'`

The password is `5Te8Y4drgCRfCx8ugdwuEX8KFC6k2EUu`

# Bandit 12
Access the next challenge using `ssh bandit12@bandit.labs.overthewire.org -p 2220` and password `5Te8Y4drgCRfCx8ugdwuEX8KFC6k2EUu`

Make a random folder in the /tmp folder. For example, `/tmp/randomtempfolder123`. You can do this with `mkdir /tmp/randomtempfolder123`. Then, copy the datafile to that temp folder using `cp` and `cd` to that folder.

As the file is a hexdump, you need to reverse it using `xxd`. You should also put the output in a file. You can do this with `xxd -r data.txt >> data2`. 

As the file has been compressed multiple times, you need to uncompress it. Use `file file2` to figure out the file type`.

For gzip compressed files, use `gunzip [file]` on a .gz file. For bzip2 compressed files, use `bunzip2 [file]`. For a tar archive, use `tar -xf [file]`

The password is `8ZjyCRiBWFYkneahHwxCv3wb2a1ORpYL`

# Bandit 13
Access the next challenge using `ssh bandit13@bandit.labs.overthewire.org -p 2220` and password `8ZjyCRiBWFYkneahHwxCv3wb2a1ORpYL`

When you type `ls`, you should see a file named `sshkey.private`. Get the output of this file using `cat sshkey.private`. Once you do that logout of the challenge with `exit`. 

Make a file named `sshkey` on your own computer. Paste the content that y ou copied earlier into this file. Once you do that, set the proper permissions using `chmod 600 sshkey` and then login to `ssh bandit14@bandit.labs.overthewire.org -p 2220 -i sshkey`

Use `cat /etc/bandit_pass/bandit14` in order to see the password previously restricted in the last challenge. 

The password is `4wcYUJFw0k0XLShlDzztnTBHiqxU3b3e`

# Bandit 14
Access the next challenge using `ssh bandit14@bandit.labs.overthewire.org -p 2220` and password `4wcYUJFw0k0XLShlDzztnTBHiqxU3b3e`

As `ssh localhost -p 30000` does not work, `telnet localhost 30000` can be used instead. Once you are connected, enter `4wcYUJFw0k0XLShlDzztnTBHiqxU3b3e`. 

The password is `BfMYroe26WYalil77FoDi9qh59eK5xNr`

# Bandit 15
Access the next challenge using `ssh bandit15@bandit.labs.overthewire.org -p 2220` and password `BfMYroe26WYalil77FoDi9qh59eK5xNr`

To access port 30001 on localhost using SSL, use `openssl s_client -crlf -connect localhost:30001`. Once you have connected, enter `BfMYroe26WYalil77FoDi9qh59eK5xNr`.

The password is `cluFn7wTiGryunymYOu4RcffSxQluehd` 

# Bandit 16
Access the next challenge using `ssh bandit16@bandit.labs.overthewire.org -p 2220` and password `cluFn7wTiGryunymYOu4RcffSxQluehd`.

Find all open ports between ports 31000 to 32000 using `nmap localhost -p 31000-32000`. After running this command, you can see that ports 31046, 31518, 31691, 31790, and 31960 are open.

To find which of these ports use SSL, run `nmap -sV localhost -p 31046,31518,31691,31790,31960`. This command may take a while. Once this command is complete, find the port that does not echo and connect to it. Use `openssl s_client -crlf -connect localhost:31790`. Once you have connected, submit the password of `cluFn7wTiGryunymYOu4RcffSxQluehd`

Once you are done, the server will return a private SSH key. Make sure to copy this, add it to the file `sshkey` on your own computer, and run `chmod 600 sshkey` to ensure it has the proper permissions

# Bandit 17
Login to the next challenge using `ssh bandit17@bandit.labs.overthewire.org -p 2220 -i sshkey`. This assumes that your key obtained from the previous level is saved in the file `sshkey`.

To find the line that has been changed between the files, run `diff passwords.old passwords.new`. 

The password is `kfBf3eYk5BPBRzwjqutbbfE887SVc5Yd`

# Bandit 18
Access the next challenge with `ssh bandit18@bandit.labs.overthewire.org -p 2220` and password `kfBf3eYk5BPBRzwjqutbbfE887SVc5Yd`.

As you are being logged out when you ssh in, you need to run the command when you login. To run commands through ssh, just append them to the end of your ssh command. The full command that needs to be used would be `ssh bandit18@bandit.labs.overthewire.org -p 2220 cat readme`

The password is `IueksS7Ubh8G3DCwVzrTd8rAVOwq3M5x`

# Bandit 19
Access the next challenge with `ssh bandit19@bandit.labs.overthewire.org -p 2220` and password `IueksS7Ubh8G3DCwVzrTd8rAVOwq3M5x`.

Running the file `bandit20-do` allows you to run a command as bandit20. With this file, we can use `./bandit20-do cat /etc/bandit_pass/bandit20` to get the password for the next level. 

The password is `GbKksEFF4yrVs6il55v6gwY5aVje5f0j`

# Bandit 20
Access the next challenge with `ssh bandit21@bandit.labs.overthewire.org -p 2220` and password `GbKksEFF4yrVs6il55v6gwY5aVje5f0j`.

In order to run two commands, you will need a one terminal trying to connect and one terminal running the server. To run the server you can use `screen echo "GbKksEFF4yrVs6il55v6gwY5aVje5f0j` | nc -vlp 12345". Once you do that, press Ctrl + A then D. Then, run `./suconnect 12345`.

The password is `GbKksEFF4yrVs6il55v6gwY5aVje5f0j`
