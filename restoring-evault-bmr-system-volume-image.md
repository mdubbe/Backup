---

copyright:
  years: 1994, 2018
lastupdated: "2018-11-13"

---
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:pre: .pre}


# Restoring a BMR System Volume Image

If you need to restore a Bare Metal image backup from EVault, you can quickly restore it from the EVault BMR Rescue Kernel system. With EVault BMR, you can restore the system without the need of a bootable operating system. It's useful when the operating system is no longer usable or the drives in the system were replaced.

## Initiating the BMR Rescue Kernel system

You can access the BMR Rescue Kernel system through the {{site.data.keyword.slportal}}.
1. Log in to the [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}
2. Click **Storage** > **Backup**
3. Click the **Arrow** next to the vault.
4. Click **Initiate Bare Metal Restore**. This action starts a transaction that takes a few minutes to complete. Afterward you can access the server by following the steps that are detailed here. You're going to be emailed when the system completes the boot process.


## Restoring from the EVault BMR Rescue Kernel

1. When the EVault BMR Rescue Kernel transaction loads, you can choose to access it in two different ways.
  - A VNC client and the private or public IP address of your server and the password that is listed in the {{site.data.keyword.slportal}}
  - The KVM console of your IPMI card.
  Both of these ways work well.
2. Upon logging in to the BMR Rescue Kernel for the first time, you're greeted with the language selection screen. Select the language of your choice and click **Next**.
<br/>![Figure 1 - BMR Language selection](/images/bmr1.png)<br/> The license agreement for the software is displayed.
3. If you accept the terms, select the check box, and click **Next** to continue. <br/> The main EVault system restore menu is presented.
4. Select **Restore My System**.
<br/>![Figure 2 - BMR Main menu](/images/bmr2.png)
5. The EVault system restore wizard appears. Select **Next** to continue.
<br/>![Figure 3 - BMR Wizard](/images/bmr3.png)
6. Select a backup type to restore from. Select **EVault software** then click **Next** to continue.
7. On the **backup location** screen, select the vault, and enter in the vault address, EVault Account number, the user name, and password. Then, click **Next** to continue.
<br/>![Figure 4 - Choose backup location](/images/bmr4.png)
8. The next screen displays your system in the list. Make sure it is highlighted and click **Next**.
<br/>![Figure 5 - Choose your system](/images/bmr5.png)
9. On the **backup job selection** screen, select the Job that you want to restore from and click **Next**.
<br/>![Figure 6 - Choose your Restore point](/images/bmr6.png)
10. From the **Select Restore Point** menu, select the restore point that you want and click **Next**.
<br/>![Figure 8 - Choose Restore Point](/images/bmr8.png)
11. Select the source and destination volumes. To restore the source to the destination, drag the source volume onto the destination volume.
<br/>![Figure 9 - Select Source and Destination Volumes](/images/bmr9.png)
12. On the format or merge data confirmation box, you can select from two options. Select **Format** for a clean restore that formats the disk. If you want to merge the data on the destination volume, select **Merge**.
<br/>![Figure 10 - Choose Merge](/images/bmr10.png)
13. On the main source and destination volume screen, click **Next**.
14. On the restore plan summary screen, check the box to accept the plan and click **Next**.
<br/>![Figure 11 - Start the restore](/images/bmr11.png)
15. The restore progress screen appears and it shows you the progress of the restoration as it happens.
<br/>![Figure 12 - Restore Progress](/images/bmr12.png)
16. When complete, you receive a notification window that states that the restore was completed successfully. Click **OK**.
17. On the restore progress screen. Click **Next**.
18. On the final screen, check the box for restart system and select **Finish** and the server loads your restored volume image.
  The restoration is now complete. <br/>

  The first time your server loads the restored image, you might see the unexpected shutdown message. It's normal with this restore type and goes away after the first boot.
  {:note}
