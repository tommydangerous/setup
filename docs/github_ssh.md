```
$ ssh-keygen -t rsa -b 4096 -C "quantumventuress@gmail.com"
$ eval "$(ssh-agent -s)"
$ ssh-add ~/.ssh/id_rsa
$ cat ~/.ssh/id_rsa.pub
```
