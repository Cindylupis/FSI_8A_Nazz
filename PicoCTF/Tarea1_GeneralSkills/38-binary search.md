### **Descripción**

Want to play a game? As you use more of the shell, you might be interested in how they work! Binary search is a classic algorithm used to quickly find an item in a sorted list. Can you find the flag? You'll have 1000 possibilities and only 10 guesses.Cyber security often has a huge amount of data to look through - from logs, vulnerability reports, and forensics. Practicing the fundamentals manually might help you in the future when you have to write your own tools!You can download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_atlas/6/challenge.zip)

`ssh -p 57352 ctf-player@atlas.picoctf.net`Using the password `6dd28e9b`. Accept the fingerprint with `yes`, and `ls` once connected to begin. Remember, in a shell, passwords are hidden!
## Solución

**Solución 1- terminal
``` 
NazaretEsquivel-picoctf@webshell:~$ ssh -p 57352 ctf-player@atlas.picoctf.net
ctf-player@atlas.picoctf.net's password: 
Permission denied, please try again.
ctf-player@atlas.picoctf.net's password: 
Permission denied, please try again.
ctf-player@atlas.picoctf.net's password: 
Welcome to the Binary Search Game!
I'm thinking of a number between 1 and 1000.
Enter your guess: 500
Lower! Try again.
Enter your guess: 250
Lower! Try again.
Enter your guess: 125
Lower! Try again.
Enter your guess: 65
Lower! Try again.
Enter your guess: 20
Lower! Try again.
Enter your guess: 2
Higher! Try again.
Enter your guess: 8
Lower! Try again.
Enter your guess: 4
Higher! Try again.
Enter your guess: 6
Higher! Try again.
Enter your guess: 7
Congratulations! You guessed the correct number: 7
Here's your flag: picoCTF{g00d_gu355_de9570b0}
Connection to atlas.picoctf.net closed.


```

#### NOTAS
- Si dice "Higher" (Más alto)

- Si dice "Lower" (Más bajo)