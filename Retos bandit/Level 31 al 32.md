# Bandit Level 31 → Level 32


## Objetivo
There is a git repository at `ssh://bandit31-git@localhost/home/bandit31-git/repo`. The password for the user `bandit31-git` is the same as for the user `bandit31`.

Clone the repository and find the password for the next level.

## Datos de acceso al nivel
bandit31
47e603bb428404d265f59c42920d81e5
## Solucion

```bash

bandit31@bandit:~$ mkdir /tmp/plop12345
bandit31@bandit:~$ cd /tmp/plop12345
bandit31@bandit:/tmp/plop12345$ git clone ssh://bandit31-git@localhost/home/bandit31-git/repo
Cloning into 'repo'...
bandit31-git@localhost password: 

remote: Counting objects: 4, done.
remote: Compressing objects: 100% (3/3), done.
remote: Total 4 (delta 0), reused 0 (delta 0)
Receiving objects: 100% (4/4), done.
bandit31@bandit:/tmp/plop12345$ cd repo/
bandit31@bandit:/tmp/plop12345/repo$ ls
README.md
bandit31@bandit:/tmp/plop12345/repo$ cat README.md 
This time your task is to push a file to the remote repository.

Details:
    File name: key.txt
    Content: 'May I come in?'
    Branch: master

bandit31@bandit:/tmp/plop12345/repo$ echo "May I come in?">key.txt
bandit31@bandit:/tmp/plop12345/repo$ git add -f key.txt
bandit31@bandit:/tmp/plop12345/repo$ git commit -m key.txt
[master 1e7c122] key.txt
 1 file changed, 1 insertion(+)
 create mode 100644 key.txt
bandit31@bandit:/tmp/plop12345/repo$ git push origin master
bandit31-git@localhost password: 

Counting objects: 3, done.
Delta compression using up to 4 threads.
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 320 bytes | 0 bytes/s, done.
Total 3 (delta 0), reused 0 (delta 0)
remote: ### Attempting to validate files... ####
remote: 
remote: .oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.
remote: 
remote: Well done! Here is the password for the next level:
remote: 56a9bf19c63d650ce78e6ec0354ee45e
remote: 
remote: .oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.
remote: 
To ssh://localhost/home/bandit31-git/repo
 ! [remote rejected] master -> master (pre-receive hook declined)
error: failed to push some refs to 'ssh://bandit31-git@localhost/home/bandit31-git/repo'
```


## Notas adicionales
 | comando | descripcion |
|---------|-------------|
| |  |

## Referencias