# Installing Linux

## Scenario

Now that your preparations are complete, you're ready to install Linux on the various systems you selected. You'll start by installing CentOS 7 on the VM you created earlier. As you go through the installation, you'll configure various options so that the base environment will be automatically set up to your specifications.

### Objectives

- > Completing this activity will help you to use content examples from the following syllabus objectives:
  - > 1.3 Given a scenario, configure and verify network connection parameters
  - > 1.4 Given a scenario, manage storage in a Linux environment
  - > 1.5 Compare and contrast cloud and virtualization concepts and technologies
  - > 1.6 Given a scenario, configure localization options

1. Load the previously created VM

   - You will work with the VM you created in the previous exercise.
   - Log in as `student01` with `Pa22w0rd` as the password.
   - At a terminal, enter `sudo virsh restore saved-vm`
   - This restores the VM you created earlier from its saved state. This may impact the performance of your lab computer for a few minutes.
   - From the desktop menu, select `Applications→System Tools→Virtual Machine Manager`.
   - Enter the `root` password.
   - Right-click the `devtech-install VM` and select `Open`.
   - Wait for the installation media to finish its check. You can press `Esc` to skip the check, but it's wise to check the media at least once when setting up production systems.

2. Configure localization settings

   - If necessary, expand the virtual machine window so it's easier to see.
     - You can also select the `Switch to fullscreen view button`.
   - On the `WELCOME TO CENTOS 7` page, select `Continue` to accept the default language settings.
   - On the INSTALLATION SUMMARY page, under the `LOCALIZATION` section, select `DATE & TIME`.
   - Select your time zone, then select Done.

3. Select the software components and base environment to install

   - Under the `SOFTWARE` section, select `SOFTWARE SELECTION`.
   - From the Base Environment list, select `Server with GUI`.
   - From the Add-Ons for Selected Environment list, check the `KDE` check box.
   - By default, the Server with GUI selection will install most tools necessary for the configuration and maintenance of general server infrastructure, along with `GNOME` as the default GUI. You're also installing `KDE` alongside that for users to have a choice of desktop environment.
   - Select `Done`.

4. Wipe the storage device to start fresh

   - Under the `SYSTEM` section, select `INSTALLATION DESTINATION`.
   - On the Device Selection page, observe the `Virtio Block Device`.
   - This is the `12 GB` virtual storage device that was created when you first installed the `VM`.
   - Under Other Storage Options, ensure Automatically configure partitioning is selected.
   - Check the I would like to make additional space available check box.
   - Select `Done`.
   - In the `RECLAIM DISK SPACE` dialog box, verify that the vda device is selected, and that it has `12 GB` of free space. This is because the virtual storage device you created is currently empty. Still, it's useful to practice wiping a storage device in order to start fresh.
   - Select `Delete all`.
   - Select `Reclaim space.`

5. Configure the partitioning scheme to use

   - On the `INSTALLATION SUMMARY` page, select `INSTALLATION DESTINATION` again.
   - Under Other Storage Options, select I will configure partitioning.
   - Select `Done.`
   - Under `New CentOS 7 Installation`, verify that no mount points have been created yet, and that the default partitioning scheme will use `LVM.`
   - Select Click here to create them automatically.
   - Verify that three `partitions/volumes` were created: `/boot`, `/ (root)`, and `swap`. Notice that there is no separate `/home` volume. This is because the `CentOS 7` installer only creates a separate `/home` volume by default when the storage device is 50 GB or more. In this case, the `/home` directory will be located within the root volume.
   - Select the `/boot` partition and note its default capacity, device type (partitioning scheme), and file system type.
   - Select the `/ (root)` volume and the swap volume and note their defaults as well.
   - These will be created as logical volumes within the centos volume group.
   - At the bottom-left of the page, note the total space of the storage device as well its available space.
   - This reflects the intended partitioning scheme; no changes will be made to the drive until installation begins in earnest.
   - Select `Done`.
   - In the `SUMMARY OF CHANGES` dialog box, select `Accept Changes`.

6. Configure networking

   - On the `INSTALLATION SUMMARY` page, select `NETWORK & HOST NAME`.
   - In the Host name text box at the bottom-left, type `devtech-vm01` then select Apply.
   - In the list of devices on the left, verify that Ethernet (`eth0`) is selected.
   - This is the virtual network interface that was created for the VM to use.
   - Select Configure at the bottom-right of the page.
   - In the Editing `eth0 dialog box`, select the `IPv4 Settings` tab.
   - From the Method drop-down list, select `Manual.`
   - To the right of the Addresses list, select the `Add` button.
   - For the Address, type `10.50.1.201`
     - Your lab environment might require different addresses than those listed in these steps.
   - Press `Tab`, then for the Netmask, type `255.255.255.0`
   - Press `Tab`, then for the Gateway, type `10.50.1.1` and press Enter.
   - In the `DNS Servers` text box, type `8.8.8.8`
   - Select `Save.`
   - Select the slider at the top-right to turn the interface On.
   - Verify that the interface details are as you expect, then select`Done`.

7. Begin installation and configure user accounts

   - Select Begin Installation.
   - Observe the progress bar at the bottom, indicating that `CentOS` is in the process of being installed.
   - Under `USER SETTINGS,` select `ROOT PASSWORD`.
   - In the Root Password text box, type `Pa22w0rd`
   - In the Confirm text box, type`Pa22w0rd`
   - Select `Done`, then, at the bottom of the screen, verify that`CentOS` points out that this password is weak because it's based on a dictionary word. In a production environment, you'd want to choose a much stronger password.
   - Select `Done` again to agree to use the password.
   - Select `USER CREATION`.
   - In the User name text box, type `student01`
   - Check the `Make this user administrator` check box.
   - In the `Password` and `Confirm password` text boxes, type `Pa22w0rd`
   - Select Done twice to confirm the password.
   - In addition to creating a stronger password, you'd also want to make your user password different than the root password in a production environment.
   - Wait for the system to finish installing.
      - The remainder of the installation process may take up to 30 minutes.

8. Complete the installation process

   - When installation finishes, select `Reboot`.
   - From the `VM` window, select `Virtual Machine→Run` to restart the `VM`.
   - On the `INITIAL SETUP` page, select `LICENSING INFORMATION`.
   - Check I accept the license agreement and select Done.
   - Select `FINISH CONFIGURATION`.
   - Verify that you are greeted with the sign in screen, indicating that `CentOS 7` was successfully installed.

9. Verify your new system's configurations

- Sign in as your student account.
- Using what you've learned, check the `VM` for the following:

---

```md
       - Storage partition and logical volume configurations.
       - User accounts.
       - Networking configurations.
       - Connectivity with other classroom computers.
       - Internet connectivity.
       - Additional software packages.
```

- When you're done, from the `VM` window, select `Virtual Machine→Shut Down→Shut Down`.
- Close the VM window.
