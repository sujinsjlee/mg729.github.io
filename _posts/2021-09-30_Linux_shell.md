---
layout: post
title: Linux - How to write and execute Linux Shell scripts
description: "Shell Script"
modified: 2021-09-30
tags: [Linux]
categories: [Linux]
---

# shell script
> # shell script
> To put it simply, a shell script expresses the each of the commands in the command line in Linux as a kind of file, and when the file is executed, it gives the effect that the commands were executed at just one command line.



# Shell script characteristics
- It is not compiled but interpreted by the operating system.
- There are many types of shell scripts. (sh, dash, bash, rbash) What we're going to cover in this post is bash scripts.
- bash : rebuilt the existing basic shell
    -  It is currently most widely used in linux-based operating systems. 
    - When writing a bash script `#! /bin/bash` You can see that it starts like this, and it means the type of shell script.

# Loop
- example

```
#!/bin/bash

while [ $n -le 10 ] # (( $n <= 10 ))
do
    echo $n
    (( n++ )) #$(( n+1 ))
done
```

# Example in steps

### Edit mode after creating a shell file

- `vi [shell file name]` 

```console
$ vi atest_100
```

### atest_100.ksh 
- line 1 : `#!/bin/bash`

```
#!/bin/sh

int=0
while test "$int" -lt "100"

do
  a module --force
  int=`expr $int + 1`
done
```

### Grant permission to execute shell file
- `ls -al` : -rw-r--r--  --> -rwxr-xr-x

```console
$ chmod 755 atest_100
```

### Execute Shell script 
    - ./ atest_100
    - sh atest_100
    - bash atest_100
    - run test 100 times

```console
$ sh atest_100
```
