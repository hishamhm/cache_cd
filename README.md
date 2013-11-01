cache_cd
========

A smarter cd for your shell.

Installation
------------

Copy the script somewhere and call it from your shell initialization script
with the "source" command. For example, copying it in ~/bin/cache_cd, copy
this to your ~/.bashrc or ~/.zshrc:

```
   source ~/bin/cache_cd
```

And restart your shell: close and reopen your terminal or simply type

```
   exec $SHELL
```

Usage
-----

```
   cd
   cd <directory>
```

Changes to your home directory or to your given directory as usual.

```
   cd <substring>
```

Tries to find substring in the list of directories you used previously.
Presents a numbered list of matches and changes to the first.

```
   cd <number>
```

Changes to the numbered directory of the previously presented list.
This directory is also moved to the top of the cache, so it comes first
when the same search is performed again in the future.

Whenever the given argument matches an existing directory, it is interpreted
as a directory (so yes, you can still "cd 2" if you have a directory called
"2").

Example
-------

```shell
hisham@parser ~]cd src
        1/Users/hisham/luarocks/src
        2/Users/hisham/luarocks/src/luarocks
        3/Users/hisham/luarocks/src/luarocks/fs/win32
        4/Users/hisham/luarocks/luarocks-2.1.0/src/luarocks
        5/Users/hisham/luarocks/luarocks-2.1.0/src
hisham@parser ~/luarocks/src/luarocks]e ~/bin/cache_cd  
hisham@parser ~/luarocks/src/luarocks]exit
hisham@parser ~]bash
hisham@parser ~]. ~/bin/cache_cd 
hisham@parser ~]cd src
        1/Users/hisham/luarocks/src/luarocks
        2/Users/hisham/luarocks/src
        3/Users/hisham/luarocks/src/luarocks/fs/win32
        4/Users/hisham/luarocks/luarocks-2.1.0/src/luarocks
        5/Users/hisham/luarocks/luarocks-2.1.0/src
hisham@parser ~/luarocks/src/luarocks]cd 2
hisham@parser ~/luarocks/src]cd
hisham@parser ~]cd src
        1/Users/hisham/luarocks/src
        2/Users/hisham/luarocks/src/luarocks
        3/Users/hisham/luarocks/src/luarocks/fs/win32
        4/Users/hisham/luarocks/luarocks-2.1.0/src/luarocks
        5/Users/hisham/luarocks/luarocks-2.1.0/src
hisham@parser ~/luarocks/src]
```


Compatibility
-------------

Tested with Bash 4.0.35 and zsh 4.3.10 on Linux. Should work in other places
and versions too.
