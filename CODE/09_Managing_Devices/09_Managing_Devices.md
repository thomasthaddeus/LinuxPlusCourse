# 09: Managing Devices

## Configuring a Virtual (PDF) Printer

### Scenario

```text
HR wants to distribute the acceptable use policy (AUP) to employees at Develetech in both hardcopy and electronic form. Right now, you don't have an actual printer connected to your Linux system, but you can still print the AUP text file to a PDF, which is more suitable than a raw text file for distribution purposes. Before you can create the PDF, you'll need to set up a virtual printer.
```

### Objectives

```text
Completing this activity will help you to use content examples from the following syllabus objectives:
    2.7 Explain the use and operation of Linux devices
    4.4 Given a scenario, analyze and troubleshoot application and hardware issues
```

1. Examine the current list of printers
   + Log in as `student01` with `Pa22w0rd` as the password.
   + From the Desktop, select `Applications→System Tools→Settings.`
   + From the navigation menu, select Devices.
   + Select `Printers`.
   + Verify that no printers are currently listed.
   + Keep this window open.

1. Install the Cups-PDF package
   + In a terminal, enter `sudo yum -y install epel-release cups-pdf`

        You may need to issue this command twice in order to successfully download the package.

        You may receive a repeating messages that says an "`Existing lock /var/yum/yum.pid`: another copy is running." Open a second tab in the terminal (or a second instance of a terminal), and then enter the following command:

        ```text
        sudo systemctl kill packagekit
        ```

1. Make the `Cups-PDF` printer your default printer
   + Return to the Settings window and verify that `Cups-PDF` is listed in the printers list. If it is not listed, repeat the install command you just entered.
   + Select `Unlock`, then enter the `root` password.
   + Next to the Cups-PDF printer, select the options gear icon, then select Use Printer by Default.
   + Close the `Settings` window.

1. Print a text file to PDF
   + Open a terminal window and verify that you are in your home directory.
   + Enter `lpr policies/aup_v2.txt`
   + Verify that a printing notification pops up from the desktop.
   + On the desktop, double-click `aup_v2.pdf` to open it.
   + Close the *PDF viewer* when you're done.

## Monitoring Devices

### Scenario

```text
As part of your routine system administration tasks, you need to track the devices used on all the computers on the network and maintain a list of hardware resources that are in use.
```

### Objectives

```Text
Completing this activity will help you to use content examples from the following syllabus objectives:
    2.7 Explain the use and operation of Linux devices
    4.4 Given a scenario, analyze and troubleshoot application and hardware issues
```

1. Monitor any PCI devices that are connected to the system.
   + In a terminal window, enter `lspci`
   + Examine the brief list of hardware devices that are connected to __PCI buses__.
   + Each line lists the `PCI slot a device` is connected to, as well as the vendor and product model of the device.
   + Enter `sudo lspci -v` to view more information about each device.
   + Verify that you can see attributes of each device, such as:
       + Its __vendor and product model__.
       + Its `I/O ports`.
       + Its various capabilities.
       + The __kernel modules and drivers__ it uses.
       + In the virtual lab environment no USB drivers are loaded. In a real, physical environment, you’d also be able to enter the `lsusb` command to see USB devices on your system.

1. Monitor a print job.
   + Enter `base64 /dev/urandom | head -c 10000000 > printfile.txt`
       + There are `7 zeros`.
   + This will create a text file `10 MB` in size using random data encoded in readable text (`Base64`). This file is large enough to take some time to print, so you'll have a chance to monitor it in the queue.

1. Enter `lpr printfile.txt` to start a print job.
   + Enter `lpq` and note that you can see the print job in the queue, including information such as:
       + Its rank (status).
       + Who owns the print job.
       + The number of the job.
       + What file(s) are being printed.
       + The total size of the request.
   + Allow the print job to finish.
