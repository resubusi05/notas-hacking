# Retos bandit

# Level 28

## Objetivo

There is a git repository at `ssh://bandit29-git@localhost/home/bandit29-git/repo` via the port `2220`. The password for the user `bandit29-git` is the same as for the user `bandit29`.

Clone the repository and find the password for the next level.
## Datos de acceso al nivel
Contraseña del nivel: 4pT1t5DENaYuqnqvadYs1oE4QLCdjmJ7

## Solución
Contraseña **bandit30**: qp30ex3VLz5MDG1n91YowTv4Q8l7CDZL

```
bandit29@bandit:~$ mktemp -d
/tmp/tmp.6JtAUT4IcT
bandit29@bandit:~$ cd /tmp/tmp.6JtAUT4IcT
bandit29@bandit:/tmp/tmp.6JtAUT4IcT$ git clone ssh://bandit29-git@localhost:2220/home/bandit29-git/repo
Cloning into 'repo'...
The authenticity of host '[localhost]:2220 ([127.0.0.1]:2220)' can't be established.
ED25519 key fingerprint is SHA256:C2ihUBV7ihnV1wUXRb4RrEcLfXC5CXlhmAAM/urerLY.
This key is not known by any other names.
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Could not create directory '/home/bandit29/.ssh' (Permission denied).
Failed to add the host to the list of known hosts (/home/bandit29/.ssh/known_hosts).
                         _                     _ _ _
                        | |__   __ _ _ __   __| (_) |_
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_
                        |_.__/ \__,_|_| |_|\__,_|_|\__|


                      This is an OverTheWire game server.
            More information on http://www.overthewire.org/wargames

bandit29-git@localhost's password:
remote: Enumerating objects: 16, done.
remote: Counting objects: 100% (16/16), done.
remote: Compressing objects: 100% (11/11), done.
remote: Total 16 (delta 2), reused 0 (delta 0), pack-reused 0
Receiving objects: 100% (16/16), 1.43 KiB | 734.00 KiB/s, done.
Resolving deltas: 100% (2/2), done.
bandit29@bandit:/tmp/tmp.6JtAUT4IcT$ ls
repo
bandit29@bandit:/tmp/tmp.6JtAUT4IcT$ cd repo
bandit29@bandit:/tmp/tmp.6JtAUT4IcT/repo$ ls -la
total 16
drwxrwxr-x 3 bandit29 bandit29 4096 Sep 10 06:32 .
drwx------ 3 bandit29 bandit29 4096 Sep 10 06:31 ..
drwxrwxr-x 8 bandit29 bandit29 4096 Sep 10 06:32 .git
-rw-rw-r-- 1 bandit29 bandit29  131 Sep 10 06:32 README.md
bandit29@bandit:/tmp/tmp.6JtAUT4IcT/repo$ cat README.md
# Bandit Notes
Some notes for bandit30 of bandit.

## credentials

- username: bandit30
- password: <no passwords in production!>

bandit29@bandit:/tmp/tmp.6JtAUT4IcT/repo$ git log
commit efa5bd803f8335e5e5e9da5c4c7c876aefc9f8b4 (HEAD -> master, origin/master, origin/HEAD)
Author: Ben Dover <noone@overthewire.org>
Date:   Wed Jul 17 15:57:31 2024 +0000

    fix username

commit 5a53eb83a43bac1f0b4e223e469b40ef68a4b6e6
Author: Ben Dover <noone@overthewire.org>
Date:   Wed Jul 17 15:57:31 2024 +0000

    initial commit of README.md
bandit29@bandit:/tmp/tmp.6JtAUT4IcT/repo$ git show efa5bd803f8335e5e5e9da5c4c7c876aefc9f8b4
commit efa5bd803f8335e5e5e9da5c4c7c876aefc9f8b4 (HEAD -> master, origin/master, origin/HEAD)
Author: Ben Dover <noone@overthewire.org>
Date:   Wed Jul 17 15:57:31 2024 +0000

    fix username

diff --git a/README.md b/README.md
index 2da2f39..1af21d3 100644
--- a/README.md
+++ b/README.md
@@ -3,6 +3,6 @@ Some notes for bandit30 of bandit.

 ## credentials

-- username: bandit29
+- username: bandit30
 - password: <no passwords in production!>

bandit29@bandit:/tmp/tmp.6JtAUT4IcT/repo$ git show 5a53eb83a43bac1f0b4e223e469b40ef68a4b6e6
commit 5a53eb83a43bac1f0b4e223e469b40ef68a4b6e6
Author: Ben Dover <noone@overthewire.org>
Date:   Wed Jul 17 15:57:31 2024 +0000

    initial commit of README.md

diff --git a/README.md b/README.md
new file mode 100644
index 0000000..2da2f39
--- /dev/null
+++ b/README.md
@@ -0,0 +1,8 @@
+# Bandit Notes
+Some notes for bandit30 of bandit.
+
+## credentials
+
+- username: bandit29
+- password: <no passwords in production!>
+
bandit29@bandit:/tmp/tmp.6JtAUT4IcT/repo$ ls -la
total 16
drwxrwxr-x 3 bandit29 bandit29 4096 Sep 10 06:32 .
drwx------ 3 bandit29 bandit29 4096 Sep 10 06:31 ..
drwxrwxr-x 8 bandit29 bandit29 4096 Sep 10 06:32 .git
-rw-rw-r-- 1 bandit29 bandit29  131 Sep 10 06:32 README.md
bandit29@bandit:/tmp/tmp.6JtAUT4IcT/repo$ cat .git
cat: .git: Is a directory
bandit29@bandit:/tmp/tmp.6JtAUT4IcT/repo$ cd .git
bandit29@bandit:/tmp/tmp.6JtAUT4IcT/repo/.git$ ls -la
total 52
drwxrwxr-x 8 bandit29 bandit29 4096 Sep 10 06:32 .
drwxrwxr-x 3 bandit29 bandit29 4096 Sep 10 06:32 ..
drwxrwxr-x 2 bandit29 bandit29 4096 Sep 10 06:31 branches
-rw-rw-r-- 1 bandit29 bandit29  281 Sep 10 06:32 config
-rw-rw-r-- 1 bandit29 bandit29   73 Sep 10 06:31 description
-rw-rw-r-- 1 bandit29 bandit29   23 Sep 10 06:32 HEAD
drwxrwxr-x 2 bandit29 bandit29 4096 Sep 10 06:31 hooks
-rw-rw-r-- 1 bandit29 bandit29  137 Sep 10 06:32 index
drwxrwxr-x 2 bandit29 bandit29 4096 Sep 10 06:31 info
drwxrwxr-x 3 bandit29 bandit29 4096 Sep 10 06:32 logs
drwxrwxr-x 4 bandit29 bandit29 4096 Sep 10 06:31 objects
-rw-rw-r-- 1 bandit29 bandit29  252 Sep 10 06:32 packed-refs
drwxrwxr-x 5 bandit29 bandit29 4096 Sep 10 06:32 refs
bandit29@bandit:/tmp/tmp.6JtAUT4IcT/repo/.git$ cat config
[core]
        repositoryformatversion = 0
        filemode = true
        bare = false
        logallrefupdates = true
[remote "origin"]
        url = ssh://bandit29-git@localhost:2220/home/bandit29-git/repo
        fetch = +refs/heads/*:refs/remotes/origin/*
[branch "master"]
        remote = origin
        merge = refs/heads/master
bandit29@bandit:/tmp/tmp.6JtAUT4IcT/repo/.git$ cat description
Unnamed repository; edit this file 'description' to name the repository.
bandit29@bandit:/tmp/tmp.6JtAUT4IcT/repo/.git$ cat HEAD
ref: refs/heads/master
bandit29@bandit:/tmp/tmp.6JtAUT4IcT/repo/.git$ cd ..
bandit29@bandit:/tmp/tmp.6JtAUT4IcT/repo$ git branch
* master
bandit29@bandit:/tmp/tmp.6JtAUT4IcT/repo$ git branch -a
* master
  remotes/origin/HEAD -> origin/master
  remotes/origin/dev
  remotes/origin/master
  remotes/origin/sploits-dev
bandit29@bandit:/tmp/tmp.6JtAUT4IcT/repo$ git checkout dev
branch 'dev' set up to track 'origin/dev'.
Switched to a new branch 'dev'
bandit29@bandit:/tmp/tmp.6JtAUT4IcT/repo$ ls -la
total 20
drwxrwxr-x 4 bandit29 bandit29 4096 Sep 10 06:41 .
drwx------ 3 bandit29 bandit29 4096 Sep 10 06:31 ..
drwxrwxr-x 2 bandit29 bandit29 4096 Sep 10 06:41 code
drwxrwxr-x 8 bandit29 bandit29 4096 Sep 10 06:41 .git
-rw-rw-r-- 1 bandit29 bandit29  134 Sep 10 06:41 README.md
bandit29@bandit:/tmp/tmp.6JtAUT4IcT/repo$ cat README.md
# Bandit Notes
Some notes for bandit30 of bandit.

## credentials

- username: bandit30
- password: qp30ex3VLz5MDG1n91YowTv4Q8l7CDZL

bandit29@bandit:/tmp/tmp.6JtAUT4IcT/repo$

```
## Notas


## Referencias


