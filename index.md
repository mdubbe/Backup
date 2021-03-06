---

copyright:
  years: 2014, 2018
lastupdated: "2018-11-15"

---
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:pre: .pre}

# Getting started with backup services

Backups ensure that your data is safely stored outside of your device and protected if it gets lost. EVault backup is an automated agent-based backup system that is managed through the WebCC browser-based management utility. EVault provides users with a method to back up data between servers in one or more data centers on the {{site.data.keyword.BluSoftlayer_full}} Network. Administrators can set backups to follow a daily, weekly, or custom schedule that targets full systems, specific directories, or even individual files. Extra plug-ins ensure compatibility with software like Microsoft Exchange and Microsoft SQL, other types of third-party software, and enable users to complete a Bare Metal Restore, when necessary.

## Ordering EVault

You can purchase EVault backup service in two ways.

- Purchase the service when you Order a Server
- Purchase the service as an Upgrade

For information about pricing, see [EVault on IBM Cloud](https://www.ibm.com/cloud/evault/pricing){:new_window}.

### Purchasing EVault when you order a server

1. Log in to [The IBM Cloud catalog](https://console.bluemix.net/catalog/){:new_window} or the [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}
2. Order a monthly bare metal server. You can learn more about ordering bare metal servers [here](https://console.bluemix.net/docs/bare-metal/baremetal-provision.html){:new_window}.
3. You are redirected to the manage portal to complete the order. <br/>

   EVault backup service isn't available when you're ordering an hourly billed server. However, the service can be added later as an upgrade.
   {:important}
4. Under **Add-ons** section, choose one of the EVault options (other than "None").
6. Scroll down, and click **Add to Order**.
7. Find the Host and Domain Names section, and enter host and domain names. You can choose any host name and domain that you like.
8. On the right, click the **Cloud Service terms** and the **Third-Party Service Agreement** check boxes.
9. Confirm or enter your payment information and click **Submit Order**. You are redirected to a screen with your provisioning order number. You can print the screen because it's also your provisioning order receipt.

You can also save this order without purchasing by clicking **Save as Quote**.
{:tip}

A series of emails is sent to your administrator: Acknowledgment of the provisioning order, Provisioning order approval and processing, and Provisioning complete. The Provisioning complete email includes a link to your *Device Details* page, that you can access after you log in to {{site.data.keyword.cloud_notm}}. You can also log directly in to the {{site.data.keyword.slportal}}.

**Confirming the purchase**
1. In the [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}, select **Devices** > **Device List** from the main menu.
2. Locate the new server that you ordered.
  - If there's clock icon next to the url, you need to wait to continue with the EVault purchase confirmation. You can refresh the page to see an updated status on your new server. When the clock icon is no longer present, you can proceed with the next steps to confirm the EVault service purchase.
  - When the clock icon is no longer showing for your server, click the link (the server's url) to go to the **Device Details** page.
3. Click the **Storage** tab to display the EVault information.
4. Inspect the EVault section, and verify that the size that was selected during the EVault purchase process is displayed next to the EVault link.

### Purchasing EVault as an upgrade

**Select a server on which to install EVault**
1. Log in to [The IBM Cloud catalog](https://console.bluemix.net/catalog/){:new_window} or the [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}
2. Select **Devices** > **Device List** from the main menu. Find the device for which you want to add EVault service.
3. Click the Device name to go to the Device Details page.

**Adding (purchasing) EVault service**
1. Click the **Storage** tab, and scroll down to locate the EVault section.
2. Click the **Add** link.
3. In the window, select a location, and select a size.
4. Select Payment type, and click **Continue**
5. Enter the **Promo Code** if you have one, and click **Recalculate**.
6. Review your order, and click the link to read the terms and conditions.
7. Click the check box if you agree with the terms and conditions.
7. Click **Place Order**.

**Confirming the EVault upgrade purchase**
1. Refresh the **Device Details** page, and ensure that the **Storage** tab is selected.
2. Inspect the EVault section and verify that the size that was selected during the EVault purchase process is displayed next to the EVault link.

If the EVault storage size continues to show a capacity of zero, a second page refresh might be needed.
{:tip}

## Accessing and viewing backup storage details in {{site.data.keyword.slportal}}

The storage details of your EVault backup service can be viewed on the {{site.data.keyword.slportal}} at any time. Details that can be viewed include the password, storage address, and usage that is associated with the selected EVault backup service.

1. To access the **EVault Backup Storage** screen, log in to the [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window} with your unique credentials.
2. Click **Storage**, and select **Backup** from the list.
2. Click anywhere on the row for the EVault backup vault you want to view its storage details. From this view, the Password is not visible. Proceed to the next step to view the password that is associated with your EVault backup service.
3. Click the **Show** check box next to the **Password** field to view the password for the selected EVault backup service.

For many {{site.data.keyword.BluSoftlayer_full}} products and services, the password storage feature within the {{site.data.keyword.slportal}} is used solely for storage or tracking of the password. For those offerings, the changes that are made to them within the {{site.data.keyword.slportal}} aren't applied to the product or service.

It is _not_ the case for EVault backup. Changes that are made to the EVault backup password within the {{site.data.keyword.slportal}} are made to the service itself. When you change your password, keep in mind that it impacts your service directly. To reset your password, follow the steps in [How to Change an EVault backup password in the {{site.data.keyword.slportal}}](change-password-evault-backup-service.html).
{:important}

## Installing the EVault agent

EVault Agent is supported on the following OS:

**Windows**
 - Windows Server 2016
 - Windows Server 2012 R2
 - Windows Server 2012
 - Windows Server 2008 R2
 - Windows Server 2008

**Linux**
 - CentOS 7.x
 - CentOS 6.x
 - Debian GNU/Linux 9.x
 - Debian GNU/Linux 8.x
 - Debian GNU/Linux 7.x
 - Red Hat Enterprise Linux 7.x
 - Red Hat Enterprise Linux 6.x
 - Ubuntu Linux 16.04
 - Ubuntu Linux 14.04

Follow the instructions appropriate for your OS,
- [Installing the backup client in Linux](install-evault-backup-client-linux.html)
- [Installing the backup client in Windows](install-evault-backup-client-windows.html)
- [Installing the backup client for Windows 2016](install-evault-windows2016.html)

## Accessing Web Central Control (WebCC)

Web Central Control (WebCC) is the client that is used to interact with any EVault backup service that is offered by {{site.data.keyword.BluSoftlayer_full}}. WebCC is a browser-based client that runs on the {{site.data.keyword.BluSoftlayer_full}} private network and allows full control of any EVault backup service, including configuration and restores. Follow these steps to access WebCC for EVault backup.

1. Access the Private Network over VPN.<br/>**Note**: WebCC can't be accessed over the public network. A VPN connection must be established first.
2. Access the EVault backup storage screen in the [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}.
3. Click anywhere on the row for the wanted EVault backup to expand the view.
4. Click **WebCC Login** to start the WebCC client in your browser.

## Configuring backup agent in WebCC

After you ordered your EVault service and the agent is installed on the server, you can start creating backups of your data. Follow these steps to configure your agent, retention schedule and start your first backup job.

1. Log in to WebCC.
2. Click **All Agents**> **Unconfigured Agents**.
3. Click **This is a new Agent I would like to configure** link. Step through the process and enter the following information:
   1. Agent configuration - provide agent description, click **Next**.
   2. Job type selection - enter job name, job description, and backup source type, click **Next**.
   3. Selection - select directories and click **Include...**
   4. Options - provide passwords
   5. Schedule - click **Add** to create a schedule, click **Next**.
   6. Select the default vault, click **OK**.
   7. Click **Save**.
4. Create a retention schedule.
   1. Select **Edit** > **Agent Settings**.
   2. Click **Add**.
   3. Complete your retention details.
   4. Click **OK**.
   5. Click **Save**.
   **Note** - Read more about how Retention Schemes work [here](faqs.html)
5. Run the agent and start a backup.
   1. Click **All Agents**, then select the agent that you configured.
   2. Click **Run Backup**.
   3. Confirm Destination and select a retention scheme.
   4. Click **Start Backup**. You can view the backup details while the process is running.
   5. When the backup is complete, click **Close**.

Read more about how you can configure simple File-level backups on Linux [here](configure-simple-file-backup-linux.html).
{:tip}

## Getting online help

WebCC's systems are fully documented and support for the application is accessible within WebCC. Click the white question mark in a blue circle that is located in the upper right for **Help**. Click any article or topic in the navigation bar on the left side to view more information.
