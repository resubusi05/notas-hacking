# Retos picoCTF

# Level b00tl3gRSA2

## Objetivo
In RSA d is a lot bigger than e, why don't we use d to encrypt instead of e? Connect with nc jupiter.challenges.picoctf.org 19566.
## Solucion
´´´
┌──(kali㉿kali)-[~/Downloads/b00tl3gRSA2/RsaCtfTool]
└─$ python RsaCtfTool.py -e 126644442293383234193134389304396568512945759903313063723153704562809466983118920048101734627335941655723269463182003773885088627014439152735362956336733956735299157128634362283044147198148811912698467953972959596403545270081208072865511692958578580149929566686365661758870240014792922627976417371174316324097 -n 134016289068356536512876194404221370384178232041326426681268558030304915676430030730356574666920422532634759265138522594605487524198238370354864723720217896345732854619747407760443665837867941123880962780123977232509138762968530305877062790761520518974670473480377586104344966536891622687866178755495887178241 --decrypt 3851390294786113113097116335398843242105660803677256543798628350341990289433824728730163726013346781370675686865185263466008455137500305740523754130549415323475152179314316515824534718571620586959873047320918474941863105850468886526710388787477078197645572655745648090875356494722036990538493533765771334609




private argument is not set, the private key will not be displayed, even if recovered.                                                              
['/tmp/tmpc22a3681']

[*] Testing key /tmp/tmpc22a3681.
attack initialized...
attack initialized...
[*] Performing lucas_gcd attack on /tmp/tmpc22a3681.
100%|█████████████████████████████| 9999/9999 [00:00<00:00, 127072.01it/s]
[+] Time elapsed: 0.0890 sec.
[*] Performing mersenne_primes attack on /tmp/tmpc22a3681.
 27%|█████████                        | 14/51 [00:00<00:00, 331752.86it/s]
[+] Time elapsed: 0.0008 sec.
[*] Performing smallq attack on /tmp/tmpc22a3681.
[+] Time elapsed: 0.3228 sec.
[*] Performing rapid7primes attack on /tmp/tmpc22a3681.
[+] loading prime list file data/ea229f977fb51000.pkl.bz2...
loading pickle data/ea229f977fb51000.pkl.bz2...
100%|██████████████████████████| 61174/61174 [00:00<00:00, 1180275.05it/s]
[+] loading prime list file data/fbcc4333b5f183fc.pkl.bz2...
loading pickle data/fbcc4333b5f183fc.pkl.bz2...
100%|██████████████████████████| 21048/21048 [00:00<00:00, 1271466.17it/s]
[+] Time elapsed: 0.3144 sec.
[*] Performing nonRSA attack on /tmp/tmpc22a3681.
[+] Time elapsed: 0.0025 sec.
[*] Performing factordb attack on /tmp/tmpc22a3681.
[!] Composite not in factordb, couldn't factorize...
[+] Time elapsed: 0.9254 sec.
[*] Performing system_primes_gcd attack on /tmp/tmpc22a3681.
100%|█████████████████████████████| 7007/7007 [00:00<00:00, 788979.55it/s]
[+] Time elapsed: 0.0227 sec.
[*] Performing fibonacci_gcd attack on /tmp/tmpc22a3681.
100%|█████████████████████████████| 9999/9999 [00:00<00:00, 124999.54it/s]
[+] Time elapsed: 0.0808 sec.
[*] Performing pastctfprimes attack on /tmp/tmpc22a3681.
[+] loading prime list file data/pastctfprimes.txt...
100%|███████████████████████████████| 121/121 [00:00<00:00, 985457.83it/s]
[+] loading prime list file data/visa_emv.txt...
100%|████████████████████████████████████| 2/2 [00:00<00:00, 98689.51it/s]
[+] loading prime list file data/ti_rsa_signing_keys.txt...
100%|█████████████████████████████████| 34/34 [00:00<00:00, 880286.02it/s]
[+] Time elapsed: 0.0019 sec.
[*] Performing cube_root attack on /tmp/tmpc22a3681.
[+] Time elapsed: 0.0002 sec.
[*] Performing factor_2PN attack on /tmp/tmpc22a3681.
[+] Time elapsed: 0.0006 sec.
[*] Performing pollard_p_1 attack on /tmp/tmpc22a3681.
  8%|███                                 | 84/997 [00:59<10:39,  1.43it/s][!] Timeout.                                                              
  8%|███                                 | 84/997 [01:00<10:52,  1.40it/s]
[+] Time elapsed: 60.0451 sec.
[*] Performing small_crt_exp attack on /tmp/tmpc22a3681.
Can't load small_crt_exp because sage binary is not installed
[*] Performing primorial_pm1_gcd attack on /tmp/tmpc22a3681.
100%|████████████████████████████| 10000/10000 [00:00<00:00, 13973.11it/s]
[+] Time elapsed: 0.7169 sec.
[*] Performing noveltyprimes attack on /tmp/tmpc22a3681.
100%|█████████████████████████████████| 21/21 [00:00<00:00, 225269.52it/s]
[+] Time elapsed: 0.0030 sec.
[*] Performing partial_q attack on /tmp/tmpc22a3681.
[!] partial_q attack is only for partial private keys not pubkeys...
[+] Time elapsed: 0.0005 sec.
[*] Performing wiener attack on /tmp/tmpc22a3681.
  3%|▉                                | 10/332 [00:00<00:00, 69905.07it/s]
[*] Attack success with wiener method !
[+] Total time elapsed min,max,avg: 0.0002/60.0451/4.1684 sec.

Results for /tmp/tmpc22a3681:

Decrypted data :
HEX : 0x0000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000007069636f4354467b6261645f31643361355f323433383132357d
INT (big endian) : 180638594769037903267909311328535969949661653321164402927482237
INT (little endian) : 87923905202948747929485038101145329885662780869068806205906271807473816988775402377418682719649444868445877187610551753882344266036512845152388442597497763549412614116667294842294702404159096025700144848141669615740427973401517228342036689222651463969509806913768511268619595560075969805973031692663984750592
utf-8 : picoCTF{bad_1d3a5_2438125}
utf-16 : 楰潣呃筆慢彤搱愳張㐲㠳㈱紵
STR : b'\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00picoCTF{bad_1d3a5_2438125}'
                                                                          
┌──(kali㉿kali)-[~/Downloads/b00tl3gRSA2/RsaCtfTool]
└─$ 

´´´
## Referencias


