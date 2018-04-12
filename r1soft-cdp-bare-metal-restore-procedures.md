---

copyright:
  years: 2017, 2018
lastupdated: "2018-04-08"

---
{:new_window: target="_blank"}
{:shortdesc: .shortdesc}

# Restoring your bare metal server from an R1Soft image

Below is the process for completing a bare metal restore to public/private {{site.data.keyword.BluVirtServers_full}} or {{site.data.keyword.BluBareMetServers_full}}. This process would be followed in the case of a server failure that causes data/OS loss. This process will restore all file system blocks backed up (including the OS and any files that were not excluded from backups). This process should not be followed if the restoration of a subset of files is the objective (Refer to [R1Soft Wiki](http://wiki.r1soft.com/display/CDP/Restoring+Files){:new_window} for restotration of the files only).

## Restoring your device

1. Click into the device you wish you restore in the [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}.
2. Click the **Actions** menu and choose **Boot from image** you get a list of private images.
3. Choose **Public Images** from the drop-down menu.
4. Choose the appropriate R1Soft agent boot image for your version of R1Soft server (serverbackup-centos-bootcd-agent.iso) and click **Boot From This Image** link on the right.
5. From the **Device Details** page for the server that you are restoring, click **Actions** > **KVM Console**.
6. After the console is up and the image boots, you will see a Debian bootloader screen with some options. Press the Enter key to boot from the default option.
7. After the OS is booted, type `netconfig` and press **Enter**.
8. Choose **Yes** to configure the networking.
9. Enter networking configuration details from device details in the Control portal.
10. Choose **Yes** when prompted to restart networking.
11. Optionally, type `passed root` to set a root password for SSH logins and type service ssh start to allow SSH login. This step might be useful if your KVM console is slow.
12. Type `service cdp-agent restart` (This command starts the Tivoli Continuous Data Protection for Files agent if it isn't already running).

## Selecting the R1Soft server and other restore parameters and options

Refer to the R1Soft documentation for [Performing a Bare Metal Restore](http://wiki.r1soft.com/display/ServerBackup/Perform+a+bare-metal+restore)
You need to select the server to restore and select the file system, portion tables, and other restore options.
