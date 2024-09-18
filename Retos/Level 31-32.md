# Retos bandit

# Level 30

## Objetivo

There is a git repository at `ssh://bandit31-git@localhost/home/bandit31-git/repo` via the port `2220`. The password for the user `bandit31-git` is the same as for the user `bandit31`.

Clone the repository and find the password for the next level.

## Datos de acceso al nivel
Contraseña del nivel: fb5S2xb7bRyFmAvQYQGEqsbhVyJqhnDy

## Solución
Contraseña **bandit32**:  3O9RfhqyAlVBEZpVb6LYStshZoqoSx5K

```
PS C:\Users\vitoe> ssh bandit31@bandit.labs.overthewire.org -p 2220
                         _                     _ _ _
                        | |__   __ _ _ __   __| (_) |_
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_
                        |_.__/ \__,_|_| |_|\__,_|_|\__|


                      This is an OverTheWire game server.
            More information on http://www.overthewire.org/wargames

bandit31@bandit.labs.overthewire.org's password:

      ,----..            ,----,          .---.
     /   /   \         ,/   .`|         /. ./|
    /   .     :      ,`   .'  :     .--'.  ' ;
   .   /   ;.  \   ;    ;     /    /__./ \ : |
  .   ;   /  ` ; .'___,/    ,' .--'.  '   \' .
  ;   |  ; \ ; | |    :     | /___/ \ |    ' '
  |   :  | ; | ' ;    |.';  ; ;   \  \;      :
  .   |  ' ' ' : `----'  |  |  \   ;  `      |
  '   ;  \; /  |     '   :  ;   .   \    .\  ;
   \   \  ',  /      |   |  '    \   \   ' \ |
    ;   :    /       '   :  |     :   '  |--"
     \   \ .'        ;   |.'       \   \ ;
  www. `---` ver     '---' he       '---" ire.org


Welcome to OverTheWire!

If you find any problems, please report them to the #wargames channel on
discord or IRC.

--[ Playing the games ]--

  This machine might hold several wargames.
  If you are playing "somegame", then:

    * USERNAMES are somegame0, somegame1, ...
    * Most LEVELS are stored in /somegame/.
    * PASSWORDS for each level are stored in /etc/somegame_pass/.

  Write-access to homedirectories is disabled. It is advised to create a
  working directory with a hard-to-guess name in /tmp/.  You can use the
  command "mktemp -d" in order to generate a random and hard to guess
  directory in /tmp/.  Read-access to both /tmp/ is disabled and to /proc
  restricted so that users cannot snoop on eachother. Files and directories
  with easily guessable or short names will be periodically deleted! The /tmp
  directory is regularly wiped.
  Please play nice:

    * don't leave orphan processes running
    * don't leave exploit-files laying around
    * don't annoy other players
    * don't post passwords or spoilers
    * again, DONT POST SPOILERS!
      This includes writeups of your solution on your blog or website!

--[ Tips ]--

  This machine has a 64bit processor and many security-features enabled
  by default, although ASLR has been switched off.  The following
  compiler flags might be interesting:

    -m32                    compile for 32bit
    -fno-stack-protector    disable ProPolice
    -Wl,-z,norelro          disable relro

  In addition, the execstack tool can be used to flag the stack as
  executable on ELF binaries.

  Finally, network-access is limited for most levels by a local
  firewall.

--[ Tools ]--

 For your convenience we have installed a few useful tools which you can find
 in the following locations:

    * gef (https://github.com/hugsy/gef) in /opt/gef/
    * pwndbg (https://github.com/pwndbg/pwndbg) in /opt/pwndbg/
    * peda (https://github.com/longld/peda.git) in /opt/peda/
    * gdbinit (https://github.com/gdbinit/Gdbinit) in /opt/gdbinit/
    * pwntools (https://github.com/Gallopsled/pwntools)
    * radare2 (http://www.radare.org/)

--[ More information ]--

  For more information regarding individual wargames, visit
  http://www.overthewire.org/wargames/

  For support, questions or comments, contact us on discord or IRC.

  Enjoy your stay!

bandit31@bandit:~$ mktemp -d
/tmp/tmp.m0V40IoFZS
bandit31@bandit:~$ cd /tmp/tmp.m0V40IoFZS
bandit31@bandit:/tmp/tmp.m0V40IoFZS$ git clone ssh://bandit31-git@localhost:2220/home/bandit31-git
/repo
Cloning into 'repo'...
The authenticity of host '[localhost]:2220 ([127.0.0.1]:2220)' can't be established.
ED25519 key fingerprint is SHA256:C2ihUBV7ihnV1wUXRb4RrEcLfXC5CXlhmAAM/urerLY.
This key is not known by any other names.
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Could not create directory '/home/bandit31/.ssh' (Permission denied).
Failed to add the host to the list of known hosts (/home/bandit31/.ssh/known_hosts).
                         _                     _ _ _
                        | |__   __ _ _ __   __| (_) |_
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_
                        |_.__/ \__,_|_| |_|\__,_|_|\__|


                      This is an OverTheWire game server.
            More information on http://www.overthewire.org/wargames

bandit31-git@localhost's password:
remote: Enumerating objects: 4, done.
remote: Counting objects: 100% (4/4), done.
remote: Compressing objects: 100% (3/3), done.
remote: Total 4 (delta 0), reused 0 (delta 0), pack-reused 0
Receiving objects: 100% (4/4), 382 bytes | 382.00 KiB/s, done.
bandit31@bandit:/tmp/tmp.m0V40IoFZS$ ls -la
total 10868
drwx------     3 bandit31 bandit31     4096 Sep 10 06:57 .
drwxrwx-wt 10351 root     root     11116544 Sep 10 06:57 ..
drwxrwxr-x     3 bandit31 bandit31     4096 Sep 10 06:57 repo
bandit31@bandit:/tmp/tmp.m0V40IoFZS$ cd repo
bandit31@bandit:/tmp/tmp.m0V40IoFZS/repo$ ls -la
total 20
drwxrwxr-x 3 bandit31 bandit31 4096 Sep 10 06:57 .
drwx------ 3 bandit31 bandit31 4096 Sep 10 06:57 ..
drwxrwxr-x 8 bandit31 bandit31 4096 Sep 10 06:57 .git
-rw-rw-r-- 1 bandit31 bandit31    6 Sep 10 06:57 .gitignore
-rw-rw-r-- 1 bandit31 bandit31  147 Sep 10 06:57 README.md
bandit31@bandit:/tmp/tmp.m0V40IoFZS/repo$ cat README.md
This time your task is to push a file to the remote repository.

Details:
    File name: key.txt
    Content: 'May I come in?'
    Branch: master

bandit31@bandit:/tmp/tmp.m0V40IoFZS/repo$ echo 'May I come in?' > key.txt
bandit31@bandit:/tmp/tmp.m0V40IoFZS/repo$ ls -la
total 24
drwxrwxr-x 3 bandit31 bandit31 4096 Sep 10 07:00 .
drwx------ 3 bandit31 bandit31 4096 Sep 10 06:57 ..
drwxrwxr-x 8 bandit31 bandit31 4096 Sep 10 06:57 .git
-rw-rw-r-- 1 bandit31 bandit31    6 Sep 10 06:57 .gitignore
-rw-rw-r-- 1 bandit31 bandit31   15 Sep 10 07:00 key.txt
-rw-rw-r-- 1 bandit31 bandit31  147 Sep 10 06:57 README.md
bandit31@bandit:/tmp/tmp.m0V40IoFZS/repo$ cat key.txt
May I come in?
bandit31@bandit:/tmp/tmp.m0V40IoFZS/repo$ cat .gitignore
*.txt
bandit31@bandit:/tmp/tmp.m0V40IoFZS/repo$ git add -f
Nothing specified, nothing added.
hint: Maybe you wanted to say 'git add .'?
hint: Turn this message off by running
hint: "git config advice.addEmptyPathspec false"
bandit31@bandit:/tmp/tmp.m0V40IoFZS/repo$ git add -f key.txt
bandit31@bandit:/tmp/tmp.m0V40IoFZS/repo$ git commit -a
Unable to create directory /home/bandit31/.local/share/nano/: No such file or directory
It is required for saving/loading search history or cursor positions.

[master 16f15e4] Holaaaaaa
 1 file changed, 1 insertion(+)
 create mode 100644 key.txt
bandit31@bandit:/tmp/tmp.m0V40IoFZS/repo$ git push -u origin msater
error: src refspec msater does not match any
error: failed to push some refs to 'ssh://localhost:2220/home/bandit31-git/repo'
bandit31@bandit:/tmp/tmp.m0V40IoFZS/repo$ git push -u origin master
The authenticity of host '[localhost]:2220 ([127.0.0.1]:2220)' can't be established.
ED25519 key fingerprint is SHA256:C2ihUBV7ihnV1wUXRb4RrEcLfXC5CXlhmAAM/urerLY.
This key is not known by any other names.
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Could not create directory '/home/bandit31/.ssh' (Permission denied).
Failed to add the host to the list of known hosts (/home/bandit31/.ssh/known_hosts).
                         _                     _ _ _
                        | |__   __ _ _ __   __| (_) |_
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_
                        |_.__/ \__,_|_| |_|\__,_|_|\__|


                      This is an OverTheWire game server.
            More information on http://www.overthewire.org/wargames

bandit31-git@localhost's password:
Enumerating objects: 4, done.
Counting objects: 100% (4/4), done.
Delta compression using up to 2 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 321 bytes | 321.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
remote: ### Attempting to validate files... ####
remote:
remote: .oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.
remote:
remote: Well done! Here is the password for the next level:
remote: 3O9RfhqyAlVBEZpVb6LYStshZoqoSx5K
remote:
remote: .oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.
remote:
To ssh://localhost:2220/home/bandit31-git/repo
 ! [remote rejected] master -> master (pre-receive hook declined)
error: failed to push some refs to 'ssh://localhost:2220/home/bandit31-git/repo'
bandit31@bandit:/tmp/tmp.m0V40IoFZS/repo$

```
## Notas

## Referencias


