# Stabilising Netcat Shells:

Netcat shells are unsteady by default. Also, they are non-interactive, and frequently have strange formatting mistakes.

The following three ways are used to stabilise net cat shells:

**Technique 1:**

Important things to bear in mind before attempting to use this technique:

* This technique is applicable only to Linux boxes.
* This technique utilizes *Python*, so Python need to be installed on the target machine.
* Some target machines may need the version of Python to be specified. If this is the case, replace python with python2 or python3 as required.

Here are the three steps:

1<sup>st</sup> Step:

```
python	 -c 'import pty;pty.spawn("/bin/bash")'
```

2<sup>nd</sup> Step:

```
export TERM=xterm
```

3<sup>ed</sup> Step:

In this step you need to background the shell using `Ctrl + Z` . And then, in our terminal we type:

```
stty raw -echo; fg
```

Note:
The third step turns off our own terminal echo, so in case of the shell dies, any input in your own terminal will not be visible. To fix this, type `reset` and press enter.
