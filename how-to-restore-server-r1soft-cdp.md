---

copyright:
  years: 2017, 2018
lastupdated: "2018-04-08"

keywords: R1Soft

subcollection: software

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}

# Restoring a Server with R1Soft Tivoli Continuous Data Protection for Files

Use this process to complete a [bare metal restore](http://wiki.r1soft.com/display/CDP/Bare-Metal+Restore){:new_window} to an {{site.data.keyword.BluSoftlayer_full}} public or private virtual server (VSI) if a server failure that causes data or OS loss.

All file system blocks that are backed up are restored, including the OS and any files that weren't excluded from backups. Do not follow this process if you want to restore of a subset of files. To restore only the files, see [http://wiki.r1soft.com/display/CDP/Restoring+Files](http://wiki.r1soft.com/display/CDP/Restoring+Files){:new_window}.

## Preparing the R1Soft Tivoli Continuous Data Protection for Files Server

1. Open a browser window and log in to R1Soft Tivoli Continuous Data Protection for Files server (the IP and admin passwords are available in the [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}).
2. Click **Recovery Points** on the R1Soft Tivoli Continuous Data Protection for Files management portal.
3. Select the **Server** that you want to restore and the **Disk Safe** from which you want to restore.
4. Locate the point from which you want to restore from the recovery points list.
5. Click **Bare Metal Restore** (the shield icon) to start the **Restoration Wizard**.
6. Click **Next** on the **Restoration Wizard**.
7. Select the file systems to be restored and click **Next**.
8. Select the host you want to restore to. It can be the original host or an different host. (Note: the steps within this procedure recover to the same server.)
9. Click **Next**.
10. Choose the storage configuration to use (use what is in place on the server or choose one based on backups).
11. Select the **Partition Tables** you want to use if you elected to choose the file system layout.
12. Map your file systems to the correct block devices (such as C:\ = /dev/sda1) and click **Next**.
13. Select your restore options such as **Reboot after restore**, **Check file system after restore**, and click **Next**.
14. Verify your options and click **Restore** or go back to change your restoration options.

A window appears with the status of the current restoration

## Preparing the device for restoration

1. Open a browser window and access [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}.
2. Click **Devices**, **Device List** and select the device to be restored.
3. Click **Actions** and choose **Boot from image** to display a list of private images.
4. Choose **Public Images** from the menu.
4. Choose the appropriate R1Soft agent boot image for your version of R1Soft server (*r1soft-cdp-bootcd-server-4.0.0.iso*) and click **Boot From This Image**.
5. Click **Actions**, **KVM Console** from the Device Details page for the server you are restoring. After the console is up and the image is started, you see a Debian bootloader screen with some options.
6. Press **Enter** to boot by using the default option.
7. Type netconfig from the r1soft-recovery prompt after the OS is started and press **Enter**.
8. Choose **Yes** to configure networking.
9. Enter the network configuration details from the **Device Details** page.
10. Click **Yes** when prompted to restart networking.
11. **Optional**: Type `passwd root` to set a root password for SSH logins and type `service ssh` start to allow SSH login, which can be useful if your KVM console is slow to respond.
12. Type `service cdp-agent restart`. This command starts the Tivoli Continuous Data Protection for Files agent even if it is not already running.
13. Select **Boot From Image**. A frame appears stating that the device is configured to boot from the *r1soft-cdp-bootcd-agent-4.0.0.iso* image. You are prompted wih a question regarding unloading the image and returning to normal booting.
14. Click **Yes** and the server will reboot from the system disk

The server will run through a chkdsk or fsck process to verify the disk and may restart itself again. After the process completes, your server or VM is operational with data that is restored from your chosen restore point.
