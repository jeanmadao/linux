# Bash environnement
## Environment variables
### Exercises 

1. On your student machine what is the value of the FLAG environment variable ?
> FLAG : 
```
BC{EXPORT_B4SH_FLAG}
```

1. Currently if you notice your machine, the variable you have created will be deleted. What should you do to make your variable persistent? (With a Bash shell).
> Commands :
```
EXPORT ENV=value
```


## History

In the terminal, have you ever tapped on the up or down arrows to return to a command you had previously used? 

![history](https://www.commitstrip.com/wp-content/uploads/2017/02/Strip-La-flemme-de-retaper-650-finalenglsih-1.gif)

Well, this is made possible by a file humbly named 'History'. This is located in your user file /home/user/. In the virtual machine, it is the file ``/home/student/.bash_history``

````sh
student@student:~$ ls -la
total 144
drwxr-xr-x 5 student student  4096 May  3 22:43 .
drwxr-xr-x 4 root    root     4096 May  1 17:39 ..
-rw------- 1 student student   863 May  2 08:30 .bash_history
-rw-r--r-- 1 student student   220 May  1 17:39 .bash_logout
-rw-r--r-- 1 student student  4003 May  3 22:43 .bashrc
drwx------ 2 student student  4096 May  1 17:40 .cache
-rw-r--r-- 1 root    root      209 May  1 23:12 employee.txt
drwxrwxr-x 2 student student  4096 May  1 21:25 findme
````

As you can see, the . in front of the file indicates that it is a hidden file.

> ⚠️ Depending on the shell used, the file name may change. You will often find it under .history 


````sh
student@student:~$ cat .bash_history 
sudo -l
dh
ls
cd /var
ls
cd /www
cd www
ls
cd html
ls
````

If we inspect the file, we can see all the history of our previously typed commands. There is also a command that displays the same thing: ``history``.
 
```sh
student@student:~$ history
    1  sudo -l
    2  dh
    3  ls
    4  cd /var
    5  ls
    6  cd /www
    7  cd www
    8  ls
```

When it is executed, history returns all the commands and their entry number (first column). We can use this number to re-run commands without having to type them again. For example, if you want to re-execute command number 42, you just have to enter :

````
student@student:~$ !42
````

The keyboard shortcut Ctrl+R allows you to enter the search mode in the history. The prompt looks like this:

```sh
(reverse-i-search):
```

You just have to enter the first characters of the command you want to search for so that the prompt offers you the most recent commands corresponding to your keystrokes, then Enter when you have found the right command.

> ⚠️ While this file can be useful for us users, it is also useful for hackers. Sometimes the history can 
> contain important information such as credentials that could help them escalate privileges.
>
> ⚠️ Also, when a machine has been compromised, it can be interesting for the analyst to check if the hacker has left some traces in the history.


### Exercises :

1. **From a hacker's perspective**, look for information that might be useful to you in the ``.history`` file. 
> There is some credentials using telnet that are available.
1. **From an analyst's perspective**, look for information that might be useful to you in the ``.history`` file. 
> 

## Custom aliases 
Linux users often need to use one command over and over again. Typing or copying the same command again and again reduces your productivity and distracts you from what you are actually doing.

You can save yourself some time by creating aliases for your most used commands. Aliases are like custom shortcuts used to represent a command (or set of commands) executed with or without custom options. Chances are you are already using aliases on your Linux system.

You can see a list of defined aliases on your profile by simply executing alias command.

````sh
student@student:~$ alias
alias alert='notify-send --urgency=low -i "$([ $? = 0 ] && echo terminal || echo error)" "$(history|tail -n1|sed -e '\''s/^\s*[0-9]\+\s*//;s/[;&|]\s*alert$//'\'')"'
alias egrep='egrep --color=auto'
alias fgrep='fgrep --color=auto'
alias grep='grep --color=auto'
alias l='ls -CF'
alias la='ls -A'
alias ll='ls -alF'
alias ls='ls --color=auto'

````

Here you can see the default aliases defined for your user in Ubuntu 16

Test it : 
````sh
student@student:~$ ll
total 148
drwxr-xr-x 5 student student  4096 May  3 23:36 ./
drwxr-xr-x 4 root    root     4096 May  1 17:39 ../
-rw------- 1 student student   863 May  2 08:30 .bash_history
-rw-r--r-- 1 student student   220 May  1 17:39 .bash_logout
-rw-r--r-- 1 student student  4003 May  3 22:43 .bashrc
drwx------ 2 student student  4096 May  1 17:40 .cache/
-rw-r--r-- 1 root    root      209 May  1 23:12 employee.txt
drwxrwxr-x 2 student student  4096 May  1 21:25 findme/
-rw-rw-r-- 1 student student  2330 May  3 23:40 .history
````

Is equivalent to running:

````sh
ls -alF
````

You can create an alias with a single character that will be equivalent to a command of your choice.

### How to Create Aliases in Linux

Creating aliases is relatively easy and quick process. You can create two types of aliases – temporary ones and permanent. We will review both types.

* **Creating Temporary Aliases** : What you need to do is type the word alias then use the name you wish to use to execute a command followed by "=" sign and quote the command you wish to alias.

    ````
    $ alias shortName="your custom command here"
    ````
* **To keep aliases between sessions**, you can save them in your user's shell configuration profile file. This can be:
    - Bash : ~/.bashrc
    - ZSH : ~/.zshrc
    - Fish : ~/.config/fish/config.fish

The syntax you should use is practically the same as creating a temporary alias. The only difference comes from the fact that you will be saving it in a file this time. So for example, in bash, you can open .bashrc file with your favorite editor like this:

````
nano ~/.bashrc
````

Find a place in the file, where you want to keep the aliases. For example, you can add them in the end of the file. For organizations purposes you can leave a comment before your aliases something like this:

````
#My custom aliases
alias home="ssh -i ~/.ssh/mykep.pem tecmint@192.168.0.100"
alias ll="ls -alF"
````

Save the file. The file will be automatically loaded in your next session. If you want to use the newly defined alias in the current session, issue the following command:

````
source ~/.bashrc
````

Well! Now it's time to optimize your workspace and create your own aliases!
