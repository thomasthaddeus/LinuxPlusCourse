# 01 Performing Basic Linux Tasks

## Entering Shell Commands

> Scenario

```plaintext
You are a systems administrator at Develetech. As a result of your earlier discussion with the IT team at Develetech, your CTO is becoming more and more convinced of the viability of switching the company's server infrastructure to Linux. The CTO wants you to become more familiar with using Linux, and he suggests doing so by booting up a test machine and trying it out. So, you'll start by entering some basic commands at the Bash shell to get a feel for the Linux environment.
```

> Objectives

```plaintext
Completing this activity will help you to use content examples from the following syllabus objectives:
  2.3 Given a scenario, create, modify, and redirect files.
  3.1 Given a scenario, apply or acquire the appropriate user and/or group permissions and ownership.
```

1. Whenever the instruction states "*enter command*", you are required to type the command and press Enter. Note that Linux commands, command-line options, and file names are case-sensitive.
   + Some of the commands in the course activity steps spill over onto the next line. Unless specified otherwise, all commands should be entered on the same line in the CLI.

1. Log in and use basic navigation commands
   + At the localhost login prompt, enter `student01`
   + At the Password prompt, enter `Pa22w0rd`
       + Be careful when you type in passwords, as the CLI does not show them on screen.
   + Verify that you are presented with a `[student01@localhost ~]$` prompt, indicating that you have successfully logged in.
   + At the prompt, enter `echo 'Hello, World!`'
       + Recall that you cannot use the automatic Type Text feature with Linux virtual machines and that all commands and input in Linux are case-sensitive. Linux commands will be displayed by using the monospace font: `hostname`
   + Verify that the console printed the string `Hello, World!` back to you.
   + Enter `pwd` to retrieve information about your current working directory.
   + Your current working directory is `/home/student01`
   + Enter `ls` (lower case L+s) and note the contents of your current working directory.
   + At the moment, there doesn't seem to be anything in your home directory.
   + Enter `ls -a` to display hidden items.
   + Now, you can see that there are files and folders in this directory, but they are hidden from a standard directory listing.
   + Enter `ls -al` and note that you are given more information about each item in the directory.

   + The name of the file or folder is on the right. The last modified date and time is to the left of the name, and to the left of that is the size of the file or folder (in bytes). Most of the other fields relate to permissions and ownership.
   + Enter `cd /etc` to change your current working directory.
   + Verify that the prompt has changed to `[student01@localhost etc]$`
   + Enter `pwd` to further verify that your current working directory is now `/etc`
   + Enter `cd /var/log` to move to the directory where system log files are stored.
   + Enter `ls -al` to see all of the files and folders that exist in this directory.
   + Enter `cd /home/student01` to move back to your home directory.
   + Enter `touch myfile` to create an empty file in your home directory.
   + Enter `ls` and verify that myfile is listed in the directory.
   + Enter `cat /etc/hostname` to view the hostname file by using the `cat` command.
   + Verify that the contents of the `/etc/hostname` file are printed at the CLI.
   + Enter `cat /var/log/dmesg` to display information about the boot process.
   + Verify that this log file is so long that much of its contents scroll past the screen.
   + The cat command has no navigational options, so you'll need to use a more advanced command to view all of the log file.
   + Enter `less /var/log/dmesg` to view the file by using the `less` command.
   + Instead of scrolling, the `less` command printed only the beginning contents of the file that fit on the screen. Your prompt has also changed to the name of the file, highlighted.
   + Scroll down by using `Enter` or the `Down Arrow` keys. Scroll down a few lines.
   + Press `y` or `Up Arrow` to scroll up one line.
   + Scroll up a few more lines.
   + Press `Spacebar` or `Page Down` to scroll down an entire screen.
   + Press `b` or `Page Up` to scroll up an entire screen.
   + Press `q` to quit viewing the file and return to your regular prompt.

1. dit a text file by using Vim
   + Enter `vim myfile` to open the file you created earlier in the Vim text editor.
   + Press `i` to switch to Insert mode.
   + Type `Hello, this is Student01`.
   + Press `Esc` to switch back to Command mode.
   + Enter `:wq` to write (save) the file and quit.
   + Enter `cat myfile` and verify that the contents of the file are printed to the CLI.

1. Create and edit a text file with GNU nano.
   + Enter `nano myfile2` to create and begin editing a new file.
   + Type `Hello, this is Student01.`
   + Press `Ctrl+O`, then press `Enter` to save the file.
   + Press `Ctrl+X` to quit.
   + Enter `cat myfile2` and verify that the contents of the file are printed to the CLI.
   + Enter `clear` to clear the screen.

1. Assume superuser privileges.
   + Enter `cat /var/log/boot.log`
   + Verify that you are given a Permission denied error.
   + As a regular user, you do not have permission to read this log file. You need to elevate your privileges to do so.
   + Enter `su - root` to switch user to the root (administrator) account.
   + There is a space on either side of the dash in the `su - root` command.
   + At the Password prompt, enter `Pa22w0rd`
       + The passwords for your student account and the root account are the same for lab convenience. In a production environment, the root password should be unique and not based on a common dictionary word.
   + Verify that your prompt has changed to `[root@localhost ~]#`
   + You are now logged in as the root user, the user with the highest level of privileges (superuser).
   + Enter `cat /var/log/boot.log` and verify that you can now read the file.
   + Enter `exit` to log out as root and switch back to your regular student account.

1. Use tab completion to make typing commands more efficient.
   + Enter `touch thisisalongfilename.txt`
   + Type `ls -l th` and then press `Tab`.
   + Verify that the rest of the file name is filled at the command-line.
   + Press `Enter` to execute the command.

1. View the command history.
   + Type `his` and press `Tab`.
   + Verify that the history command is populated at the command-line.
   + Tab completion works on file, directory, and even command names.
   + Press `Enter` to execute the command.
   + Verify that a list of the commands you recently entered is printed on the screen.

1. Restart the computer.
   + Enter `reboot`
   + Verify that the computer restarts, and then prompts you to log in.
   + Log in as `student01` with `Pa22w0rd` as the password.

## Accessing Help in Linux

> Scenario

```text
In order to be useful, Linux must have tools with certain capabilities that will be useful to the business. One of these capabilities is searching the contents of text files. This will come in handy for administrators who need to efficiently analyze text files like system logs, automated scripts, etc., for specific patterns. You'll need to find one or more Linux tools that can accomplish this and learn how to use them. So, you'll consult various help resources to get acquainted with the appropriate tool(s).
```

> Objectives
> Completing this activity will help you to use content examples from the following syllabus objectives:
   > 2.3 Given a scenario, create, modify, and redirect files

1. Look for a command that could help you search the contents of a text file.
   + If necessary, log in as `student01` with a password of `Pa22w0rd`
   + Enter `apropos search`
       + If you get nothing appropriate as the result of the apropos command, enter `su - root` and enter `Pa22w0rd` when prompted. Then, enter `mandb` to update the database. After the command finishes running, enter `exit` to return to your `student01` account and enter `apropos` search again.
   + Verify that multiple commands are listed in the output, each of which includes the term search in its name or brief description.
   + You could try to pick out the appropriate command from these results, but changing your search might narrow them down.
   + Enter `clear` to clear the screen.
   + Enter `apropos pattern`
   + Verify that you receive fewer results.
   + Looking at these results, which command(s) do you think would best fulfill the capabilities that you're looking for? Click here for the answer
       + Answers may vary, but one of the `grep` variants is likely the most appropriate command. The `awk` command and its variants could be helpful, but appear to be more advanced.

2. Read the manual page for a command that could be what you're looking for
   + Enter `man grep`
   + Verify that you see the manual page for the `grep` command.
   + Read the `SYNOPSIS` section to understand how to use the command.
   + Read the `DESCRIPTION` section to understand what the command does.
   + Navigate up and down the man page using the same keys as the `less` command.
   + Enter `/case` to search the man page for the term "`case`".
   + Press `n` to navigate to the next instance of the search term.
   + When you're at the end of the man page, press `Shift+N` to navigate to the previous instance of the search term.
   + Read the description for the command option that has to do with case.
   + Given what you've read in the `man` page for `grep` so far, answer what you think the following command does: `grep -i hello myfile`
   + Click here for the answer

3. Search for more information about the `grep` command.
   + Press `q` to quit the man page.
   + Enter `cd /usr/share/doc`
   + Enter `ls`
   + Verify that there are many subdirectories in this directory, each of which corresponds to a software package.
   + Type `cd grep` and press `Tab`.
       + Make sure not to add a space after `grep` before you press `Tab`.
   + Verify that the path to the specific version of `grep` is completed, then press `Enter`.
   + Enter `ls`
   + Enter `less NEWS` and then briefly skim the change notes for the `grep` command.
   + Press `q` to quit.
   + How confident are you that this command fulfills what you're looking for? Click here for the answer

        ```plaintext
        Answers may vary, but the grep command does generally meet your requirements. However, this doesn't mean it's the only command, or the best command, for the job.
        ```

   + You still want to learn more about other commands that your team could use to search the contents of a text file. Aside from the help options built into Linux, what other sources can you consult in your research? Click here for the answer

        ```plaintext
        Answers may vary, but there is a wide variety of useful sources on the Internet that could help you find what you're looking for. You could pose specific answers to Q&A sites like Stack Exchange; ask discussion questions on newsgroups, mailing lists, and forums dedicated to Linux support; consult supplementary and/or advanced documentation through a resource like the Linux Documentation Project; or consult distro-specific documentation on the relevant distro's website.
        ```
