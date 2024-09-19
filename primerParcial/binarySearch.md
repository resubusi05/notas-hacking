# Retos picoCTF

# Level Binary Search

## Objetivo
Want to play a game? As you use more of the shell, you might be interested in how they work! Binary search is a classic algorithm used to quickly find an item in a sorted list. Can you find the flag? You'll have 1000 possibilities and only 10 guesses. Cyber security often has a huge amount of data to look through - from logs, vulnerability reports, and forensics. Practicing the fundamentals manually might help you in the future when you have to write your own tools!

## Solución

```
┌──(kali㉿kali)-[~/retosPico/binary]
└─$     ssh -p 57495 ctf-player@atlas.picoctf.net
ctf-player@atlas.picoctf.net's password: 
Welcome to the Binary Search Game!
I'm thinking of a number between 1 and 1000.
Enter your guess: 500
Lower! Try again.
Enter your guess: 300 
Lower! Try again.
Enter your guess: 200
Lower! Try again.
Enter your guess: 100
Higher! Try again.
Enter your guess: 150
Lower! Try again.
Enter your guess: 125
Lower! Try again.
Enter your guess: 117
Higher! Try again.
Enter your guess: 121
Higher! Try again.
Enter your guess: 123
Lower! Try again.
Enter your guess: 122
Congratulations! You guessed the correct number: 122
Here's your flag: picoCTF{g00d_gu355_6dcfb67c}
Connection to atlas.picoctf.net closed.

```

## Notas adicionales
## Referencias


