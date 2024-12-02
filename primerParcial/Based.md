# Retos picoCTF

# Level Based

## Objetivo
To get truly 1337, you must understand different data encodings, such as hexadecimal or binary. Can you get the flag from this program to prove you are on the way to becoming 1337? Connect with nc jupiter.challenges.picoctf.org 29956.

## Solución

```
                                                               
┌──(kali㉿kali)-[~/Downloads]
└─$ nc jupiter.challenges.picoctf.org 29956 
Let us see how data is stored
lizard
Please give the 01101100 01101001 01111010 01100001 01110010 01100100 as a word.
...
you have 45 seconds.....

Input:
lizard
Please give me the  163 154 165 144 147 145 as a word.
Input:
Too slow!
                                                                         
┌──(kali㉿kali)-[~/Downloads]
└─$ nc jupiter.challenges.picoctf.org 29956
Let us see how data is stored
test
Please give the 01110100 01100101 01110011 01110100 as a word.
...
you have 45 seconds.....

Input:
test
Please give me the  164 141 142 154 145 as a word.
Input:
test
WRONG!
                                                                         
┌──(kali㉿kali)-[~/Downloads]
└─$ nc jupiter.challenges.picoctf.org 29956
Let us see how data is stored
colorado
Please give the 01100011 01101111 01101100 01101111 01110010 01100001 01100100 01101111 as a word.
...
you have 45 seconds.....

Input:
colorado
Please give me the  163 154 165 144 147 145 as a word.
Input:
sludge
Please give me the 736c75646765 as a word.
Input:
sludge
You've beaten the challenge
Flag: picoCTF{learning_about_converting_values_b375bb16}
                                                                         
┌──(kali㉿kali)-[~/Downloads]
└─$ 

```

