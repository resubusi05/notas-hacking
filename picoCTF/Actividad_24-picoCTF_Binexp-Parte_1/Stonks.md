# Retos picoCTF

# Level Stonks

## Objetivo
I decided to try something noone else has before. I made a bot to automatically trade stonks for me using AI and machine learning. I wouldn't believe you if you told me it's unsecure! vuln.c nc mercury.picoctf.net 53437

## Solucion

```
┌──(kali㉿kali)-[~/Downloads/stonks]
└─$ wget https://mercury.picoctf.net/static/62f47b5b65ec7eadb96c4e34f016f68d/vuln.c 
--2024-11-15 18:34:00--  https://mercury.picoctf.net/static/62f47b5b65ec7eadb96c4e34f016f68d/vuln.c
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 2744 (2.7K) [application/octet-stream]
Saving to: ‘vuln.c’

vuln.c              100%[=================>]   2.68K  --.-KB/s    in 0s      

2024-11-15 18:34:01 (52.4 MB/s) - ‘vuln.c’ saved [2744/2744]

                                                                              
┌──(kali㉿kali)-[~/Downloads/stonks]
└─$ ls
vuln.c
                                                                              
┌──(kali㉿kali)-[~/Downloads/stonks]
└─$ cat vuln.c 
#include <stdlib.h>
#include <stdio.h>
#include <string.h>
#include <time.h>

#define FLAG_BUFFER 128
#define MAX_SYM_LEN 4

typedef struct Stonks {
        int shares;
        char symbol[MAX_SYM_LEN + 1];
        struct Stonks *next;
} Stonk;

typedef struct Portfolios {
        int money;
        Stonk *head;
} Portfolio;

int view_portfolio(Portfolio *p) {
        if (!p) {
                return 1;
        }
        printf("\nPortfolio as of ");
        fflush(stdout);
        system("date"); // TODO: implement this in C
        fflush(stdout);

        printf("\n\n");
        Stonk *head = p->head;
        if (!head) {
                printf("You don't own any stonks!\n");
        }
        while (head) {
                printf("%d shares of %s\n", head->shares, head->symbol);
                head = head->next;
        }
        return 0;
}

Stonk *pick_symbol_with_AI(int shares) {
        if (shares < 1) {
                return NULL;
        }
        Stonk *stonk = malloc(sizeof(Stonk));
        stonk->shares = shares;

        int AI_symbol_len = (rand() % MAX_SYM_LEN) + 1;
        for (int i = 0; i <= MAX_SYM_LEN; i++) {
                if (i < AI_symbol_len) {
                        stonk->symbol[i] = 'A' + (rand() % 26);
                } else {
                        stonk->symbol[i] = '\0';
                }
        }

        stonk->next = NULL;

        return stonk;
}

int buy_stonks(Portfolio *p) {
        if (!p) {
                return 1;
        }
        char api_buf[FLAG_BUFFER];
        FILE *f = fopen("api","r");
        if (!f) {
                printf("Flag file not found. Contact an admin.\n");
                exit(1);
        }
        fgets(api_buf, FLAG_BUFFER, f);

        int money = p->money;
        int shares = 0;
        Stonk *temp = NULL;
        printf("Using patented AI algorithms to buy stonks\n");
        while (money > 0) {
                shares = (rand() % money) + 1;
                temp = pick_symbol_with_AI(shares);
                temp->next = p->head;
                p->head = temp;
                money -= shares;
        }
        printf("Stonks chosen\n");

        // TODO: Figure out how to read token from file, for now just ask

        char *user_buf = malloc(300 + 1);
        printf("What is your API token?\n");
        scanf("%300s", user_buf);
        printf("Buying stonks with token:\n");
        printf(user_buf);

        // TODO: Actually use key to interact with API

        view_portfolio(p);

        return 0;
}

Portfolio *initialize_portfolio() {
        Portfolio *p = malloc(sizeof(Portfolio));
        p->money = (rand() % 2018) + 1;
        p->head = NULL;
        return p;
}

void free_portfolio(Portfolio *p) {
        Stonk *current = p->head;
        Stonk *next = NULL;
        while (current) {
                next = current->next;
                free(current);
                current = next;
        }
        free(p);
}

int main(int argc, char *argv[])
{
        setbuf(stdout, NULL);
        srand(time(NULL));
        Portfolio *p = initialize_portfolio();
        if (!p) {
                printf("Memory failure\n");
                exit(1);
        }

        int resp = 0;

        printf("Welcome back to the trading app!\n\n");
        printf("What would you like to do?\n");
        printf("1) Buy some stonks!\n");
        printf("2) View my portfolio\n");
        scanf("%d", &resp);

        if (resp == 1) {
                buy_stonks(p);
        } else if (resp == 2) {
                view_portfolio(p);
        }

        free_portfolio(p);
        printf("Goodbye!\n");

        exit(0);
}
                                                                              
┌──(kali㉿kali)-[~/Downloads/stonks]
└─$ nc mercury.picoctf.net 53437     
Welcome back to the trading app!

What would you like to do?
1) Buy some stonks!
2) View my portfolio
1
Using patented AI algorithms to buy stonks
Stonks chosen
What is your API token?
3
Buying stonks with token:
3
Portfolio as of Fri Nov 15 23:34:44 UTC 2024


3 shares of X
1 shares of E
1 shares of V
10 shares of LQY
111 shares of F
71 shares of GKIT
1752 shares of G
Goodbye!
                                                                              
┌──(kali㉿kali)-[~/Downloads/stonks]
└─$ %x
fg: job not found: x
                                                                              
┌──(kali㉿kali)-[~/Downloads/stonks]
└─$ nc mercury.picoctf.net 53437
Welcome back to the trading app!

What would you like to do?
1) Buy some stonks!
2) View my portfolio
%x
Goodbye!
                                                                              
┌──(kali㉿kali)-[~/Downloads/stonks]
└─$ nc mercury.picoctf.net 53437
Welcome back to the trading app!

What would you like to do?
1) Buy some stonks!
2) View my portfolio
%s
Goodbye!
                                                                              
┌──(kali㉿kali)-[~/Downloads/stonks]
└─$ vim resolver.py
                                                                              
┌──(kali㉿kali)-[~/Downloads/stonks]
└─$ python resolver.py 
  File "/home/kali/Downloads/stonks/resolver.py", line 33
    El código ASCII de `}`es `0x7d`que está en la posición 24. La bandera está entre las posiciones 15 y 24. Como las posiciones no cambiarán, tomemos estos valores y los decodifiquemos byte a byte. En realidad, extraeremos hasta la posición 23, ya que en la posición 24 solo tenemos `}`y el byte nulo (fin de cadena en C):
                        ^
SyntaxError: unmatched '}'
                                                                              
┌──(kali㉿kali)-[~/Downloads/stonks]
└─$ vim resolver.py   
                                                                              
┌──(kali㉿kali)-[~/Downloads/stonks]
└─$ python resolver.py
[▖] Opening connection to mercury.picoctf.net on port 20195: Trying 18.189.209[+] Opening connection to mercury.picoctf.net on port 20195: Done
[*] Closed connection to mercury.picoctf.net port 20195
[▁] Opening connection to mercury.picoctf.net on port 20195: Trying 18.189.209[+] Opening connection to mercury.picoctf.net on port 20195: Done
[*] Closed connection to mercury.picoctf.net port 20195
[▖] Opening connection to mercury.picoctf.net on port 20195: Trying 18.189.209[+] Opening connection to mercury.picoctf.net on port 20195: Done
[*] Closed connection to mercury.picoctf.net port 20195
[.] Opening connection to mercury.picoctf.net on port 20195: Trying 18.189.209[+] Opening connection to mercury.picoctf.net on port 20195: Done
[*] Closed connection to mercury.picoctf.net port 20195
[◐] Opening connection to mercury.picoctf.net on port 20195: Trying 18.189.209[+] Opening connection to mercury.picoctf.net on port 20195: Done
[*] Closed connection to mercury.picoctf.net port 20195
[.] Opening connection to mercury.picoctf.net on port 20195: Trying 18.189.209[+] Opening connection to mercury.picoctf.net on port 20195: Done
[*] Closed connection to mercury.picoctf.net port 20195
[▖] Opening connection to mercury.picoctf.net on port 20195: Trying 18.189.209[+] Opening connection to mercury.picoctf.net on port 20195: Done
[*] Closed connection to mercury.picoctf.net port 20195
[┤] Opening connection to mercury.picoctf.net on port 20195: Trying 18.189.209[+] Opening connection to mercury.picoctf.net on port 20195: Done
[*] Closed connection to mercury.picoctf.net port 20195
[.] Opening connection to mercury.picoctf.net on port 20195: Trying 18.189.209[+] Opening connection to mercury.picoctf.net on port 20195: Done
[*] Closed connection to mercury.picoctf.net port 20195
Leaked flag: picoCTF{I_l05t_4ll_my_m0n3y_6045d60d}
                                                                              
┌──(kali㉿kali)-[~/Downloads/stonks]
└─$ python resolver.py
[/.......] Opening connection to mercury.picoctf.net on port 20195: Trying 18.[+] Opening connection to mercury.picoctf.net on port 20195: Done
[*] Closed connection to mercury.picoctf.net port 20195
[|] Opening connection to mercury.picoctf.net on port 20195: Trying 18.189.209[+] Opening connection to mercury.picoctf.net on port 20195: Done
[*] Closed connection to mercury.picoctf.net port 20195
[|] Opening connection to mercury.picoctf.net on port 20195: Trying 18.189.209[+] Opening connection to mercury.picoctf.net on port 20195: Done
[*] Closed connection to mercury.picoctf.net port 20195
[|] Opening connection to mercury.picoctf.net on port 20195: Trying 18.189.209[+] Opening connection to mercury.picoctf.net on port 20195: Done
[*] Closed connection to mercury.picoctf.net port 20195
[▖] Opening connection to mercury.picoctf.net on port 20195: Trying 18.189.209[+] Opening connection to mercury.picoctf.net on port 20195: Done
[*] Closed connection to mercury.picoctf.net port 20195
[<] Opening connection to mercury.picoctf.net on port 20195: Trying 18.189.209[+] Opening connection to mercury.picoctf.net on port 20195: Done
[*] Closed connection to mercury.picoctf.net port 20195
[┤] Opening connection to mercury.picoctf.net on port 20195: Trying 18.189.209[+] Opening connection to mercury.picoctf.net on port 20195: Done
[*] Closed connection to mercury.picoctf.net port 20195
[▖] Opening connection to mercury.picoctf.net on port 20195: Trying 18.189.209[+] Opening connection to mercury.picoctf.net on port 20195: Done
[*] Closed connection to mercury.picoctf.net port 20195
[<] Opening connection to mercury.picoctf.net on port 20195: Trying 18.189.209[+] Opening connection to mercury.picoctf.net on port 20195: Done
[*] Closed connection to mercury.picoctf.net port 20195
Leaked flag: picoCTF{I_l05t_4ll_my_m0n3y_6045d60d}
                                                                              
┌──(kali㉿kali)-[~/Downloads/stonks]
└─$ vim resolver.py   
                                                                              
┌──(kali㉿kali)-[~/Downloads/stonks]
└─$ python resolver.py
[▁] Opening connection to mercury.picoctf.net on port 53437: Trying 18.189.209[+] Opening connection to mercury.picoctf.net on port 53437: Done
[*] Closed connection to mercury.picoctf.net port 53437
[┤] Opening connection to mercury.picoctf.net on port 53437: Trying 18.189.209[+] Opening connection to mercury.picoctf.net on port 53437: Done
[*] Closed connection to mercury.picoctf.net port 53437
[◐] Opening connection to mercury.picoctf.net on port 53437: Trying 18.189.209[+] Opening connection to mercury.picoctf.net on port 53437: Done
[*] Closed connection to mercury.picoctf.net port 53437
[┤] Opening connection to mercury.picoctf.net on port 53437: Trying 18.189.209[+] Opening connection to mercury.picoctf.net on port 53437: Done
[*] Closed connection to mercury.picoctf.net port 53437
[<] Opening connection to mercury.picoctf.net on port 53437: Trying 18.189.209[+] Opening connection to mercury.picoctf.net on port 53437: Done
[*] Closed connection to mercury.picoctf.net port 53437
[|] Opening connection to mercury.picoctf.net on port 53437: Trying 18.189.209[+] Opening connection to mercury.picoctf.net on port 53437: Done
[*] Closed connection to mercury.picoctf.net port 53437
[q] Opening connection to mercury.picoctf.net on port 53437: Trying 18.189.209[+] Opening connection to mercury.picoctf.net on port 53437: Done
[*] Closed connection to mercury.picoctf.net port 53437
[.] Opening connection to mercury.picoctf.net on port 53437: Trying 18.189.209[+] Opening connection to mercury.picoctf.net on port 53437: Done
[*] Closed connection to mercury.picoctf.net port 53437
[/.......] Opening connection to mercury.picoctf.net on port 53437: Trying 18.[+] Opening connection to mercury.picoctf.net on port 53437: Done
[*] Closed connection to mercury.picoctf.net port 53437
Leaked flag: picoCTF{I_l05t_4ll_my_m0n3y_bdc425ea}
                                                                              
┌──(kali㉿kali)-[~/Downloads/stonks]
└─$ 
```

## Referencias


