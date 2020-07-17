
# Quick Start Guide to Use the Remote Server
This is a simple guide showing how to run your scripts (like MATLAB code) using the remote server. 

In general, to run your script, you need to:

1. Apply for an account on the remote server.
2. Copy your code from your local computer to the remote server.
3. Run your script.
4. Fetch the result from the remote server.

(Note that except copying your code to the remote server, you can also code directly on the remote server. Similarly, you can also check the result directly on the remote server. However, always make a backup on your local computer.)

Inexperienced user of Linux can read the basic part of section 'Useful commands' first.

Hereinafter, "terminal" refers to "Powershell" in Windows or "Terminal" in Mac OS. Both of them are built-in terminals in corresponding operating system.

## How to apply for the account?
Please contact the administrators of the remote server to apply for an account.

## How to login the server?

To login, do the following steps:

1. Open the terminal. Type `ssh <username>@202.121.180.27 -p 996` in the terminal and press Enter button to login. For instance, `ssh abc@202.121.180.27 -p 996` (note: do not type "<" and ">" in the terminal. If you type the wrong characters, press C key while holding down the Ctrl key to abort.)
2. Type the password and press Enter. For the first time you login, please type the default password: `123`. (Note: since it is a password, you will not see what you type.) 
3. For the first time you login, please **change the default password** using the command `passwd`. The terminal will ask for the current password. Type `123`. Then, the terminal will ask for the new password. Type your new password to replace the old one. This is very important because your weak password will expose the whole Linux server to danger.

To logout, type `exit`.

## How to transfer files between your local computer and the remote server?
If you want to copy your code to the remote server, or fetch the result from the remote server, you need to know how to transfer files between the your local computer and the remote server. Generally, there are many ways to do this. 

### Approach 1: `scp` command

In the terminal, `scp <source> <destination>` can copy the files from `source` to `destination`. You will need to type the password to run this command. 

**Example 1**: You (with account name `abc`) want to copy a file in your local computer whose path is `D:\demo.m` into the folder `example` in the remote server. Type `scp D:/demo.m abc@202.121.180.27:example` without login. (To make a directory, please read the section 'Useful commands'.)

**Explanation**: Since you are not logged in, `D:/demo.m` refers to a path on your local computer. Due to the same reason, to refer to a path on the remote server, `abc@202.121.180.27:` is necessary. This is also why you need to input your password. 

Note that `\` in ` <path>` should be replaced by `/`, and do not type '<' and '>'. Also, Chinese and space should not appear in `<path>`. 

**Example 2**: You want to copy the result `a.mat` in the folder `example` to your local path `D:\`. Type `scp abc@202.121.180.27:example/a.mat D:/a.mat `.

### Approach 2: WinSCP software (for Windows)

Windows users can use a user-friendly software [WinSCP](https://winscp.net/eng/index.php) to copy files between the local and the remote. It is really easy.

## How to run the MATLAB script on the server?
There are two ways to run the MATLAB script.

### Approach 1: Run using command line

This is the typical way to run MATLAB code.

1. Go to the directory of your code using `cd` command. (See the section 'Useful commands'.)
2. Open MATLAB by silent mode: `matlab -nodesktop -nosplash`.
3. Run the code using `run <MATLAB file>`. For example, `run demo.m`. 

### Approach 2: Run using graphic user interface

You can use the graphic interface of MATLAB on the remote server. 

First install [Xming](https://sourceforge.net/projects/xming/) and [PuTTY](https://www.chiark.greenend.org.uk/~sgtatham/putty/). Then do the following steps:

1. Open Xming.
2. Open PuTTY. In the 'PuTTY Configuration', input the Host Name (202.121.180.27) and Port (996). Make sure the 'Connection type' is 'SSH'. In the left menu 'Category - Connection - SSH - X11', click 'Enable X11 forwarding'. Click Open.
3. Login.
4. Run `matlab`.
5. Enjoy!

## How to run the R script on the server?

There are two ways to run the R script.

### Approach 1: Run using command line

1. Open R by `R`.
2. Run your script by `source` command. Example: `source('demo.R', echo = TRUE)`.

### Approach 2: Run using browser based interface

1. Open your web browser.
2. Open the web page `http://202.121.180.27:8787/`.
3. Login with your Linux account.
4. Enjoy!

## Useful commands

**Basic:**

[Basic shell commands in Linux](https://www.geeksforgeeks.org/basic-shell-commands-in-linux/)

**Advanced:**

1. If your programs are running in the server, you have/ to keep connecting the server all the time. However, the command [tmux](https://www.ocf.berkeley.edu/~ckuehl/tmux/) allows you to keep programs running after you disconnect. 

2. Copy multiple files and folders between the local computer and the server: [scp](https://linuxhandbook.com/scp-command/). 

## Softwares installed on the server
1. Python 2.7.12, Python 3.5.2;
2. MATLAB 2018a.
3. R 4.0.2 + RStudio Server 1.3.959

## Contact 
Lab IT: Xueke Zheng, Yijie Wang, Tianyu Wang, Zixi Han.






Written by 

Lab IT
