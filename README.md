# CS190 Lab 3 - My New Shell #

The purpose of this lab is for you to learn and customize parts of your shell in order become more efficient. After you finish this lab, you will have a colorful terminal and be able to create short programs and run them from your home directory.

Before starting the lab, please navigate to [this website](https://docs.google.com/presentation/d/1VATjJcOHZicGWOyQ9hW5EvMA9wTf8-Y9qsLiQtsaY7Q/pub?start=false&loop=false&delayms=3000) and review all of the material from Lecture 3.

## Setup ##

Depending on your working environment, perform the appropriate action:

| Environment   | Action        |
| ------------- | ------------- |
| Linux Lab Machine            | Open a terminal window        |
| Windows or Personal Computer | SSH into `data.cs.purdue.edu`*  |

----

\* You must have X11 forwarding enabled. If you are on the Windows Lab Computer, follow the instructions below:

1. Search for 'Xming' in the start menu and run it.
2. Open PuTTy
3. Expand the 'SSH' tab from the 'Category' list
4. Choose 'X11' from 'SSH' list
5. Check 'Enable X11 Forwarding'
6. Connect like normal to `data.cs.purdue.edu` within PuTTy.

----

### The Magic Command ###

**ONLY RUN THIS ONCE.**

    cd; curl -sL http://cs.purdue.edu/homes/hoffmant/lab3/lab3init | /bin/bash

Copy the command above and run it within the terminal. It will create a folder named `cs190lab3` located within your home directory. 


> You may delete the folders `cs190lab1` and `cs190lab2`. You may also delete the old answers.txt files, wherever they are located.

----

## Things To Know ##

##### \` - backtick #####

- This is the key at the top left of the keyboard, just below the ESC key. 
- No shift is needed
- Shares a key with the ~ symbol.

##### PWD Environment Variable #####

- There is an environment variable called PWD, among many other ones
- To print it, you can execute `echo $PWD`

##### Opening Files in gedit #####

    gedit <filename>  # ex. gedit ~/.zshrc

##### Ampersand #####

    gedit <filename>    # locks up the terminal, when you quit terminal, gedit gets killed.

    gedit <filename> &  # terminal is not lock up, gedit is detached, terminal and gedit 
                        # are not linked in any way



## Part 1 - The Usual ##

There are only two tasks in this part, and they both produce the same output. 

> CWD = Current Working Directory

#### Task 1 - subshell ####

You may want to review the [subshell/backticks slide](https://docs.google.com/presentation/d/1VATjJcOHZicGWOyQ9hW5EvMA9wTf8-Y9qsLiQtsaY7Q/pub?start=false&loop=false&delayms=3000#slide=id.g11e26992d_1184) in Lecture 3


    Working Directory:  not important

    Desired Action:     print "CWD: " and the current working directory on the same line.
                        MUST USE BACKTICKS

    Example Output:     CWD: /homes/hoffmant/cs190lab3

    You will use the answer in Part 2. No answers.txt this week.

#### Task 2 - environment variables ####

In this task, you will be working with the environment variable named `PWD`. 

    Working Directory:  not important

    Desired Action:     print "CWD: " and the current working directory on the same line.
                        MUST USE ENVIRONMENT VARIABLES

    Example Output:     CWD: /homes/hoffmant/cs190lab3

    You will use the answer in Part 2. No answers.txt this week.


## Part 2 - CWD Info Script ##

There is a shell script named `dirinfo` in your `~/bin` directory. You will edit this file in a text editor (gedit) to satisfy the follow requirements. 

1. Prints the current working directory in the format of Task 1/Task 2
2. Prints the *contents* of the working directory. 
3. The command used to satisfy #2 must contain two relavent arguments. Your choice. Be prepared to explain your choice of arguments.

Detailed instructions are included in the comments of the `dirinfo` script.

#### Man Pages ####

To help you in the search for arguments, you may find the `man` program helpful.

    man <command_name>  # ex. man pwd

To navigate the man pages, you can click `d` and `u` to navigate down and up the page, and can click `q` to exit the man page.

#### Testing Script ####

If we tried to run the `dirinfo` command right now, it would say "Permission Denied". To fix this, we need to make the `dirinfo` executable. Run the command below to give your command executable rights.

    chmod +x ~/bin/dirinfo

Finally, run the command

    dirinfo

## Part 3 - Upgrade Your Shell ##

This is the section that makes the terminal more personalized and usable. I have included a script named `install.sh` that will guide you through the process.

Run the command below

> NOTE: If you have already customized your shell, I would advise against using the script. 
> Just show the TA you already customized it before and that will work for grading.

    bash ~/cs190lab3/install.sh

Most users will want to select `Install_CS190_Shell` and change the default shell to `Zsh`. If you like bash, then don't change the default shell. Remember, in future classes, you may need to switch to bash, especially if you use `lore.cs.purdue.edu` (please don't use it unless you are required to).

#### After running the script ####

Run the following command for `zsh`

    zsh

Run the following command for `bash`

    bash


#### Terminal Colors #### 
It might help to change the color scheme if you are using the Linux terminal. Go to `Edit -> Profile Preferences -> Colors` then next to "Built-in schemes", select "White on black". 

If you are on PuTTy and want to change this preference now for future use, run the command below and follow the same instructions.

    gnome-terminal

## Part 4 - Aliases ##

Depending on which shell you chose as default, edit the `~/.bashrc` or `~/.zshrc` file in a text editor. 

You should create two aliases:

1. Shorten the command `dirinfo` to just `i`
2. Your choice.

> NOTE: Everyone has to do this, even if you've already customized your terminal before this lab.

#### After creating aliases ####
 
Run the following command for `zsh`

    source ~/.zshrc

Run the following command for `bash`

    source ~/.bashrc

## Grading ##

In a terminal, with the TA present:

1. run and explain answers to both Task 1 and Task 2
2. run `dirinfo`
3. run `i`
4. run your personal alias
5. ask a question about something you don't understand.


## End of Lab ##


*If you find any bugs within the code or misspellings in the write-up, please tell the TA. Thanks!*