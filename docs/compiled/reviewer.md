# Working with the shell - I

### Introduction to Shell

- Take me to the [Video Tutorial](https://kodekloud.com/topic/introduction-to-shell/)

In this section, we will take a look at linux shell in detail. 
- We will learn how to use linux commands and understand how to work with files and directories. 
- We will also see different ways to get help with linux commands. 
- Finally, we will learn about different types of shells used in Linux (particulary focusing on the bash shell)

#### Linux shell

![Shell](../../images/Shell.PNG)

- This command line interface (CLI) will enable you to effectively work on linux laptop/server/virtual machine.
- While the graphical version may see more appealing to the users but can be limited in case of functionality. These is where the Linux command line commonly known as **`Linux Shell`** shines.

  #### What is a shell?

  - Linux shell is a program that allows text based interaction between the user and the operating system, this interaction is carried out by typing commands into the interface and receving the response in the same way.
  - The Linux shell is a powerful tool with which you can navigate between different locations within the system, however when you login to the shell the very first directory you were take into is your home directory.

#### The Home Directory

![The-Home-Directory](../../images/The_Home_Directory.JPG)
 
- A user **`michael`** home directory created under **`/home/michael`**, where **`/home`** is a system created home directory that contains the home directories for almost all users in the linux system. 
- The name of the home directory is by default identical to the name of the user, hence **`michael's`** home directory is **`/home/michael`**.
- Remember the home directory is unique for each user. Another user called **`allen`** will have a different home directory which by default created under **`/home/allen`**.

  ##### Why do we need a home directoy?
  - The home directory allows users to store their personal data in the form of files and directories
  - Each user in the system gets their own unique home directory with complete access to it (to be able to save, retreive , delete data).
  - Think of it as a dedicated locker assign to you in which you can store or retreive items.
  - Other users can't access your files and folders with in your home directory (only you can).

**Note** : The representation of the home directory is represented as by the `~ (tilde symbol).`

#### Command Prompt

- You can configure the command prompt to show whatever you want, such as the **`hostname`** , **`date`** or **`time`**. 
- It is currently configured to show the current working directory. The **`~` symbol**  here represents the home directory

#### Command and Arguments

- To interact with the linux system using the shell, a user has to type in commands
- When a command is run it executes a program to achieve a specific task.
  - **`For example`**: The **`echo`** command is used to print a line of text on the screen.
  ```
                          $ echo 
  ```
- An argument acts as an input to command
  - **`For example`**: To print a **`hello`** message type **`echo hello`** command.
  ```
                          $ echo hello
  ```
- There are several commands that can work without an argument too.
  - **`For example`**: Type in the command called **`uptime`**, this is used to print information about how long a system has been running for since the last reboot along with the other information (This command doesn't need an argument)
  ```
                          $ uptime 
  ```
- A command can also have options that modify its behaviour in some predetermine way. The option also sometime referred to as a switch or a flag 
  - **`For example`**: To print a same word `hello` but without a trailing line, use **`echo`** command with **`-n`** flag.
  ```
                          $ echo -n hello
  ```
  
![Command-and-Arguments](../../images/Command-and-Arguments.PNG)

#### Command Types

Command types in linux can be generally categorized in two types
 1. Internal or Built-in Commands 
    - Internal commands are part of the shell itself. It come bundled with it, there are in total about 30 such commands
    - **`For example`**: echo, cd, pwd, set e.t.c.
 1. External Commands
    - External commands on the other hand are binary programs or scripts which are usually located in distinct files in the system. They either come with pre-install with the distribution package manager or can be created or installed by the user
    - **`For Example`**: mv, date, uptime, cp e.t.c.
    
To determine a command is internal or external, use **`type`** command
 
![Command-Types](../../images/Command-Types.PNG)

# Basic Linux Commands

- Take me to the [Video Tutorial](https://kodekloud.com/topic/basic-linux-commands-3/)

In this section, we will take a look at basic linux commands 
- Specifically related to navigation and creating new files and directories.
- We will do this by completing a simple task using a linux shell.

#### Our goal is to create a directory structure, the top most directory which is **`/home/michael`** which is already created as it as a home directory but everything else underneath has to be created. 

![mkdir_cd_working_with_shell_I](../../images/mkdir_cd_working_with_shell_I.PNG)

To print the present working directory. Run **`pwd`** command
```
$ pwd
```

To see the contents of the directory. Run **`ls`** command
```
$ ls 
````

To make (or) create a directory. Run **`mkdir`** command
```
$ mkdir Asia
```

To make (or) create multiple directories. Run **`mkdir`** command followed by **`<directory_name1> <directory_name2> .. <directory_nameN>`**
```
$ mkdir Europe Africa America
```

To change a directory from the current directory. Run **`cd <directory_name>`**
```
$ cd Asia
```

To recursively created directories. Run **`mkdir -p <directory_name1>/<sub_directory_of_name1>`**
```
$ mkdir -p India/Mumbai
```

To go back to one directory up. Run **`cd ..`**
```
$ cd ..
```

To go back directly to a home directory of the current user from any location in the system. Run **`cd`**
```
$ cd
```

#### Lets now look at absolute path and relative path



![Absolute_and_relative_path_working_with_shell_I](../../images/Absolute_and_relative_path_working_with_shell_I.PNG)

**Difference Between Absolute and Relative Path**

- **Absolute Path** : An absolute path is defined as specifying the location of a file or directory from the root directory(/).
- **Relative Path** : Relative path is defined as the path related to the present working directly(pwd).

To change to a directory with absolute path. Run **`cd <directory_path>`**
```
$ cd /home/michael
```

To Change to a directory with relative path. Run **`cd <directoryName>`**
```
$ cd Asia
```

#### Lets now take a look at alternatives to the **`cd`** command

![pushd_popd](../../images/pushd_popd.PNG)

Alternative to the **`cd`** is the **`pushd\popd`** command. To change directory using pushd, run **`pushd <directory_name>`**
```
$ pushd /etc
```

You can change to subdirecties under /etc as many times as you wish
```
$ pushd /var
$ pushd /tmp
$ pwd
/etc/var/tmp
```

To return back to origin directory(say your home directory), use the **`popd`** command
```
$ popd
```

#### Now lets move on to look some more basic commands in linux. To learn these commands we will make use of the same directory structure as before, however now there are some new files and directories added as shown in the diagram. The goal of this task is to make sure the directory structure looks like the below diagram .

![before_after_commands](../../images/before_after_commands.PNG)

To move file or directory. Run **`mv <source> <destination>`** command
```
$ mv /home/michael/Europe/Morocco /home/michael/Africa/ (Absolute path)
$ mv Europe/Morocco Africa/ (Relative Path)
```

To rename a directory. Run **`mv <oldname> <newname>`** command
```
$ mv Asia/India/Munbai Asia/India/Mumbai
```

To copy a file to a directory. Run **`cp <filename> <destination_directorypath>`** command
```
$ cp Asia/India/Mumbai/City.txt Africa/Egypt/Cairo
```

To delete a file from a directory. Run **`rm /path/<filename>`** command
```
$ rm Europe/UK/London/Tottenham.txt
```

To copy a directory recursively. Run **`cp -r <sourcepath> <destinationPath>`** command
```
$ cp -r Europe/UK Europe/UnitedKingdom
```

To print the content of a file. Run **`cat /path/to/<filename>`** command
```
$ cat Asia/India/Mumbai/City.txt
```

To add a content to a file with cat(redirect) . Run **`cat > /path/to/<filename>`** command
```
$ cat > Africa/Egypt/Cairo/City.txt
  Cairo
  `Type Ctrl + d from keyboard`
```

To create an empty file. Run **`touch /path/to/filename`** command
```
$ touch /home/michael/Asia/China/Country.txt
```

To see the content of a file in a scrollable manner. Run **`more /path/to/filename`** command <-- not recommended for large files
```
$ more new_file.txt
```

To see the content of a file and navigate throught the file. Run **`less /path/to/filename`** command
```
$ less new_file.txt
```

To get the long list of files and directories. Run **`ls -l`** command
```
$ ls -l
```

To list all files including the hidden. Run **`ls -la`** command
```
$ ls -a
```

To list all the files in the order they were modified. Run **`ls -lt`** command
```
$ ls -lt
```

To list all the files form oldest to newest. Run **`ls -ltr`** command
```
$ ls -ltr
```

# Using command line to get help

- Take me to the [Video Tutorial](https://kodekloud.com/topic/command-line-help-3/)

In this section we will learn how to use **`help`** command to get help in command line
- If you are new to using `linux` or `bash shell`  or if you are not sure which command does what, there are few commands in bash that can help get started. 
- Lets take a look of those

First command is **`whatis`** , this command will displays a one line description of a command does. 

**`Syntax: whatis <command>`**

```
$ whatis date
```

Most of the commands internal or external come bundled with **`man pages`** which provides information about the command in detail (with examples, usecases and with command options)

**`Syntax: man <command>`**

```
$ man date
```

Several commands will provide **`-h`** or **`--help`** to provide users with the options and usecases available in a command

```
$ date -h
$ date --help
```

To search through the man page names and descriptions for instances of the keyword use **`apropos`**. This is useful if you want to look for all commands within the system that contains the specifc keyword.

**`Syntax: apropos <keyword>`**
```
$ apropos modpr
```

# Lab - Working with shell

- Access Hands-On Labs here [Hands-On-Labs](https://kodekloud.com/topic/lab-working-with-the-shell/)

1. To check the home directory for a particular user say **`bob`**
   ```
   $ grep bob /etc/passwd | cut -d ":" -f6
   ```
1. To check the home directory for a particular user using built in shell variables
   ```
   $ echo $HOME
   ```
1. In the command **`echo Welcome`**, what does the word Welcome represent with respect to the command?
   ```
   $ echo Welcome 
     - Where Welcome is an argument
   ```
   
1. To check **`git`** command type
   ```
   $ type git
   ```
1. To create a directory
   ```
   $ mkdir /home/bob/birds
   ```
1. To create directories recursively
   ```
   $  mkdir -p /home/bob/fish/salmon
   ```
1. Create few more directories
   ```
   $ mkdir -p /home/bob/mammals/elephant
   $ mkdir -p /home/bob/mammals/monkey
   $ mkdir /home/bob/birds/eagle
   $ mkdir -p /home/bob/reptile/snake
   $ mkdir -p /home/bob/reptile/frog
   $ mkdir -p /home/bob/amphibian/salamander
   ```
1. To move a directory
   ```
   $ mv /home/bob/reptile/frog /home/bob/amphibian
   ```
1. To rename a directory
   ```
   $ mv /home/bob/reptile/snake /home/bob/reptile/crocodile
   ```
1. To delete a directory
   ```
   $ rm -r /home/bob/reptile
   ```
# Bash Shell

- Take me to the [Video Tutorial](https://kodekloud.com/topic/bash-shell/)

## Different types of Shells

In this section, we will take a look at different types of shells.
- There are different types of shells in linux, some of the popular ones are below
  - Bourne Shell (sh)
  - C Shell (csh or tsh)
  - Korn Shell (ksh)
  - Z Shell (zsh)
  - Bourne again shell (Bash)
  
To check the shell being used. Use the command **`echo $SHELL`**
```
$ echo $SHELL
```

To change the default shell. Use the command chsh, you will be prompted for the password and following that input the name of the new shell. You have to login into new terminal session to see this change though.
```
$ chsh
```

## Bash Shell Features

1. Bash supports command auto-completion. What this means is bash means to auto-complete commands for you if you type part of it and press the **`tab`** key
   
   ![bash-auto](../../images/bash-auto.PNG)
   
   ![bash-auto1](../../images/bash-auto1.PNG)

1. In Bash we can set custom aliases for the actual commands
   ```
   $ date
   $ alias dt=date
   $ dt
   ```
1. Use the **`history`** command to list the previous run commands that you ran earlier
   ```
   $ history
   ```
   
 ## Bash environment variables
 
 To print **`SHELL`** environment variable
 ```
 $ echo $SHELL
 ```
 
 To see a list of all environment variables. Run **`env`** from the terminal
 ```
 $ env
 ```
 
 To set an environment variable with in the shell. The value is not carry forward to any other process.
 ```
 $ OFFICE=caleston
 ```
 
 To set an environment variable we can use the **`export`** command. To make the value carry forward to any other process. 
 ```
 $ export OFFICE=caleston
 ```
 
 To persistently set an environment variable over subsequent login or a reboot add them to the **`~/.profile`** or **`~/.pam_environment`** in the users home directory.
 
 ```
 $ echo "export OFFICE=caleston" >> ~/.profile (or)
 $ echo "export OFFICE=caleston" >> ~/.pam_environment
 ```
 
 To check the value of a environment variable called **`LOGNAME`**
 ```
 $ echo $LOGNAME
 ```
 
## Path Variable

#### Speaking about the environment variables, when a user issues an external command into the shell, the shell uses path variable to search for these external commands
 
To see the directories defined in path variable. Use the command **`echo $PATH`**.
```
$ echo $PATH
```

To check if the location of the command can be identified. Use the **`which`** command

**`Syntax: which <command>`**

```
$ which obs-studio
```

To define a command in the **`PATH`** variable. To add we can use the **`export`** command.
```
$ export PATH=$PATH:/opt/obs/bin
$ which obs-studio
```

## Customize Bash Prompt

Once you login into the shell, the line you see is the bash prompt.

![bash-prompt](../../images/bash-prompt.PNG)

It can be customized to see the **`username`** and the **`hostname`**

![bash-prompt1](../../images/bash-prompt1.PNG)

#### The bash prompt is set in control by a set of special shell environment variables. The most common of these and the one we will focus on is **`PS1`** variable.

![bash-prompt2](../../images/bash-prompt2.PNG)

To see the value assign to **`PS1`**, type **`echo $PS1`**
```
$ echo $PS1
```

To change the PS1 to only display the word **`ubuntu-server`**.
```
$ PS1="ubuntu-server"
$ echo $PS1
```

#### To customize further, have a look at the below special character.

![bash-prompt3](../../images/bash-prompt3.PNG)

To change the bash prompt to display **`date`**, **`time`**, **`username of the current user`**, the **`hostname`** and the **`current working directory`**
```
$ PS1="[\d \t \u@\h:\w ] $ "
```

# Lab - Linux Bash Shell

- Access Hands-On Labs here [Hands-On Labs](https://kodekloud.com/topic/lab-linux-bash-prompt/)

1. To check the default shell for the current user. Display the shell for the current user but not necessarily the shell that is running at the movement.
   ```
   $ echo $SHELL
   ```
2. To change the shell for bob from **`Bash`** to **`Bourne Shell`**
   ```
   $ chsh -s /bin/sh bob
   ```
3. What is the value of the environment variable **`TERM`**
   ```
   echo $TERM
   ```  
4. Create a new environment variable called **`PROJECT=MERCURY`** and make it persistent by adding the variable to the **`~/.profile`** file.
   ```
   echo export PROJECT=MERCURY >> ~/.profile
   ```
5. Which of the following directories is not part of the PATH variable?
   ```
   /opt/caleston-code
   ```
6. Set an alias called **`up`** for the command **`uptime`** and make it persistent by adding to **`~/.profile`** file.
   ```
   echo alias up=uptime >> ~/.profile
   ```
7. Update Bob's prompt so that it displays the date as per the format below:
Example: **`[Wed Apr 22]bob@caleston-lp10:~$`**
Make sure the change is made persistent.
   ```
   PS1='[\d]\u@\h:\w\$'
   or
   echo 'PS1=[\d]\u@\h:\w$' >> ~/.profile
   ```