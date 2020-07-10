
# Quick Start Guide to Use the Remote Server
This is a simple example  showing how to run MATLAB code using the remote server. 

Hereinafter, "terminal" refers to "Powershell" in Windows or "Terminal" in Mac OS. Both of them are built-in terminals in corresponding operating system.

## Login the server and change the default password
1. Please contact the administrators of the remote server to apply for an account.
2. Open the terminal. Type `ssh <username>@202.121.180.27 -p 996` in the terminal and press Enter button to login.  For instance, `ssh abc@202.121.180.27 -p 996` (note: do not type "<" and ">" in the terminal. If you type the wrong characters, press C key while holding down the Ctrl key to abort.)
3. Type the default password: `123`. (Note: since it is a password, you will not see what you type.) 
4. Change the default password using the command `passwd`. The terminal will ask for the current password. Type `123`. Then, the terminal will ask for the new password. Type your new password to replace the old one.

## Copy a file from the local computer to the server
1. In the remote server, create a new folder named 'example': `mkdir example`. 
2. Type `exit` to logout the server and return to local. 
3. Create a new file named 'demo.m' in the local computer. Write in `a=1; save('a','a');`.
4. Type `scp <path>/demo.m <username>@202.121.180.27:example` to copy the file to the remote server. `<path>` is referred to as the path of 'demo.m' in the local computer. Note that `\` in ` <path>` should be replaced by `/`, and do not type '<' and '>'. Also, Chinese and space should not appear in `<path>`. You will need to type the password to run this command. 
5. Open the terminal. Login the server. Use `cd example` command to go into the 'example' folder. Use `ls` command to check the files and folders in the current path. If you see 'demo.m', then it means that you have successfully copied the file to the remote server.

## Run the MATLAB script in the server
1. In the 'example' folder in the remote server, run MATLAB by silent mode: `matlab -nodesktop -nosplash`.
4.   Type 'run demo.m' to run the script. 
5. List all files in folder 'example' using command `ls`. A file 'a.mat' should appear.

## Copy a file from the server to the local computer
1. Type `exit` to return to the local.
2. Use `scp <username>@202.121.180.27:example/a.mat <local_destination_path>` to copy the file to the local computer. Again, `\` in `<local_destination_path>` should be replaced by `/`, do not type '<' and '>', and Chinese and space should not appear in `<local_destination_path>`. 
3. You will see a file 'a.mat' copied to your local computer in `<local_destination_path>`.

## Useful commands
1. If your programs are running in the server, you have to keep connecting the server all the time. However, the command [tmux](https://www.ocf.berkeley.edu/~ckuehl/tmux/) allows you to keep programs running after you disconnect. 
2. Copy multiple files and folders between the local computer and the server: [scp](https://linuxhandbook.com/scp-command/).  Windows users can also use a user-friendly software [WinSCP](https://winscp.net/eng/index.php) to copy files between the local and the remote.
3. [Basic shell commands in Linux](https://www.geeksforgeeks.org/basic-shell-commands-in-linux/) 
## Softwares installed in the server
1. Python 2.7.12, Python 3.5.2;
2. MATLAB 2018a.
3. R 4.0.2 + RStudio Server 1.3.959

## Contact 
Lab IT: Xueke Zheng, Yijie Wang, Tianyu Wang, Zixi Han.






Written by 

Lab IT 




