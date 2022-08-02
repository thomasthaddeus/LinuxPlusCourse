# Exploring the Linux+ Lab Environment

## Scenario

> In this activity, you will familiarize yourself with the systems you will be using in the course activities.

### Using the Lab Interface

To complete most of the labs in this course, you will use one or more Virtual Machines (VM) hosted on a cloud platform. Each VM works very much like a physical computer, but you access them via your browser. The main thing to remember is that your `WINDOWS/START` key will work on your own computer not the VM. Take a few moments to familiarize yourself with some other features of the lab browser controls.

> In this pane, click the Resources tab heading. Click the `Instructions` tab to view these steps again when you have had a look.

    `Resources tab`

## Resources tab.

1. The Resources area is used to show the VMs you have available to you plus any downloadable files that may be useful during a lab. You can choose a different `ISO` disc to load in each VM's DVD drive and also change the virtual network that the VM is connected to. You can also open each VM in a new window if you find it easier to switch between them that way.
2. Looking at the Instructions tab again, notice that each of these tasks has a check box for you to use to record your progress. As you complete each step, click the box to mark it as complete.
3. Click the `Help` tab. Click the Instructions tab to view these steps again when you have had a look.
4. You can use the `Help` page to get assistance with technical issues and view more advanced information about using the lab interface.
5. Also, note that the `Help` tab features a zoom control to allow you to make these instructions appear in larger or smaller font.
   - Finally, note the timer counting down below the lab title. You will have the option of extending the lab for a limited amount of time, so please plan accordingly. If you run out of time, don't worry you will always be able launch the lab again.
   - > Aim to complete assisted labs in 15-30 minutes.
   - > Aim to complete applied labs in 30-45 minutes.
6. Looking at the pane containing the VM, in the top-left corner, click the Display icon Display icon and select Full Screen.
7. Working in full screen mode is usually best because it allows the maximum possible screen resolution for the VM you are operating. The other options in this menu allow you to fit the VM screen to the browser window or refresh the display, if it does not seem to be updating.
8. If you are using a Windows computer to access these labs, press the START key on your keyboard. Notice that this activates the Taskbar on your PC. In some browsers, this might also cause the lab environment to exit full screen mode.
9. If necessary, switch to Full Screen mode again then click the Lightning icon lod icon `lightning.png` to open the menu—do not select anything from the menu yet.
10. This menu allows you to send START key combinations and the CTRL+ALT+DEL key sequence to the VM.
11. There is also a virtual keyboard for use if you find you have trouble typing particular characters. The VM uses a US keyboard layout so if your own physical keyboard has a different layout you may find that some keys do not type the same symbols.
12. You can also use the Power menu to reset or turn off the VM. You should generally only do this if instructed.
13. Now that you are familiar with the lab interface, let's look at the guest VMs you will be using. Click the Next button to continue.

## Explore Linux command line

1. The Linux environment has two virtual machines (some labs only use one VM). Both VMs are running `CentOS7`.
2. Virtual machines may be accessed by selecting the link in the instructions. For example, to select the `CentOS7` virtual machine, you would click on the following link: `CentOS 7 (vSphere)`
   - Virtual machines may also be selected from a menu at the top of the lab user interface or from the Resources tab in this pane.
3. Type `root` in the login prompt and then press Enter.
4. Type `Pa22w0rd` in the password prompt and then press Enter.
5. This `Linux` VM has been configured to boot to the `command line interface (CLI)`. This is very common for Linux servers.
6. Type whoami to display your current logon credentials.
   - You cannot use the automatic Type Text feature with `Linux` virtual machines, and all commands and input in Linux are case-sensitive. Linux commands will be displayed by using the monospace font: `hostname`
7. Type `hostname` to display the VM's `hostname`.
8. Type ip a to check the network adapter configuration.
   - Remember that the `Linux` command-line is case-sensitive. You will have to manually enter commands when using the `Linux` virtual machines. Carefully check your syntax before you press Enter!

## Explore the CentOS7 graphical user interface

1. Log in and then take a few moments to familiarize yourself with the desktop.
2. Select the `CentOS 7 (vSphere #2) (L14) VM`.
   - If the virtual machine in asleep (displaying only the clock), press `Enter`.
3. If prompted, select `Student02` from the list.
4. Enter `Pa22w0rd` as the password, and then press Enter.
5. Select the Applications menu in the top left to gain access to applications.
6. Use the Applications menu to discover Terminal and Firefox.
7. Explore the icons in the upper right corner of the screen. Can you find the Settings interface?
8. Close Settings.
9. Right-click the desktop and select Open Terminal.
10. Type `whoami` to display your current logon credentials.
11. Type `exit` to close the Terminal window.
