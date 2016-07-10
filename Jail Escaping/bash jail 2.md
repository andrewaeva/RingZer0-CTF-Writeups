# Bash Jail 2


BASH Jail Level 2:
Current user is uid=1001(level2) gid=1001(level2) groups=1001(level2)

Flag is located at /home/level2/flag.txt

```bash
Challenge bash code:
-----------------------------

function check_space {
    if [[ $1 == *[bdks';''&'' ']* ]]
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
        output="echo Your command is: $input"
        eval $output
    fi
done

-----------------------------

```

```bash
Your input:
lol
Your command is: lol
Your input:
lol  2
Restricted characters has been used
Your input:
</home/level2/flag.txt
Your command is:
Your input:
`ls
Restricted characters has been used
`whoami`
Your command is: level2
Your input:
`</home/level2/flag.txt`
Your command is: FLAG-*****
```
