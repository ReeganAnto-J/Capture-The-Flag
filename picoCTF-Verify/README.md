# Verify (Forensics)
[Link](https://play.picoctf.org/practice?difficulty=1&page=1)

Tags:
- Easy
- Forensics
- picoCTF 2024
- grep
- browser_webshell_solvable
- checksum

## Description
People keep trying to trick my players with imitation flags. I want to make sure they get the real thing! I'm going to provide the SHA-256 hash and a decrypt script to help you know that my flags are legitimate. You can download the challenge files here:

[challenge.zip](https://artifacts.picoctf.net/c_rhea/10/challenge.zip)

Additional details will be available after launching your challenge instance.

## Introduction
This challenge zip contains 2 files and a folder, the checksum.txt file contines the hash required to be found, the decrypt.sh is a shell command that decrypts the file and the files folder contains a list of files containing flags, one of which contains the correct flag.

## Solution
#### grep 
This command is used to match a specific word in a text

#### sha256sum 
This command is used to obtain the sha256 hash code of a file

#### Answer
- Use the cat command to get the sha256 code from the checksum.txt file
- Use sha256sum ./files/* | grep `paste the copied checksum`
- This filters all the unnecessary files and gives the name of the file that matches the hash code from the question.
- Use the decrypt.sh command to read the contents of the file and that is the required flag

#### Explanation
The sha256sum command obtains the checksum of the files in the files directory and the * denotes that all the files must be checked. <br>

The pipe (|) symbol gives the output of the checksums into the grep command which pattern matches for all the files containing the checksum value. 