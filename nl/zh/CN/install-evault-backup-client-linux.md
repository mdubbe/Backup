---

copyright:
  years: 1994, 2018
lastupdated: "2018-07-02"

---
{:codeblock: .codeblock}
{:pre: .pre}
{:new_window: target="_blank"}

# 在 Linux 中安装 EVault Backup 客户机 

要在基于 Linux 的操作系统上安装 EVault Backup 客户机，可通过在操作系统的 shell 或终端中运行一系列命令来完成。此过程概述了在以下任何基于 Linux 的操作系统上安装 EVault Backup 客户机所需的步骤：

- RedHat Enterprise Linux
- CentOS
- CloudLinux

完成此过程后，自动进程会自动向 WebCC 注册代理程序服务，然后下载并安装运行该服务所需的文件。

>**注** - 如果在 {{site.data.keyword.slportal}} 中订购服务器时购买了 EVault，那么会自动为您安装该软件。您不需要使用本文档中所述的过程。

如果您在 {{site.data.keyword.slportal}} 中购买了 EVault（作为升级选项），请执行以下步骤来安装软件。

## 登录到目标设备服务器

1. 登录到 [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}，并从主菜单中选择**设备** > **设备列表**以查看可用服务器设备的列表。
2. 找到为其购买 EVault 服务的设备，并记下其公共 IP 地址。 
  - 在以下步骤中，从 Unix 或 Linux 命令行登录到设备时要使用此 IP 地址。在步骤 4 中所示的命令中，将 <publicIpAddress> 替换为实际的公共 IP 地址。 
3. 单击向右箭头以显示有关设备的更多信息，包括用户名和密码。 
  - 如果未显示密码，可通过单击**显示密码**来显示密码。在下一步中，将使用该用户名和密码来登录到测试设备。在下面的命令中，将 `<user name>` 替换为实际的用户名。
4. 通过在 Unix 或 Linux 命令行中输入以下命令，登录到目标设备。
   ```
  ssh <user name>@<publicIpAddress>
  ```
   {: pre}
   
   >**注** - 如果您之前未使用此用户名登录到此服务器，那么系统会向您显示一条有关主机真实性的消息。系统还会询问您是否要继续。请回答**是**以继续。
5. 系统将提示您输入密码，除非您之前设置了用于访问此服务器的 SSH 密钥。

## 更新 Linux 以准备安装 EVault 客户机（仅限 RedHat Linux）
>**注** - 此步骤对于 RedHat Linux 是必需的，但对于其他 Linux 分发版是可选的。

- 在服务器提示符处运行以下命令。
  ```
  yum update
  ```
  {: pre}
   
  在系统提示时，确认下载大小是否正常。更新将继续，并在完成时显示“完成！”消息。

## 获取 EVault 安装脚本

- 在服务器提示符处运行以下命令。
  ```
  wget -N http://downloads.service.softlayer.com/evault/evault_manual.sh
  ```
  {: pre}
   
## 运行 EVault 安装脚本

1. 在服务器提示符处运行以下命令。
   ```
  sh ./evault_manual.sh
  ```
   {: pre}

2. 输入您的 WebCC 用户名和密码。     
   >**注** - 有关查看 EVault backup 用户名和密码的指示信息，请参阅[备份服务入门](/docs/infrastructure/Backup/index.html)一文。
3. 在输入用户名和密码之后，再没有任何需要输入的内容了，即使在安装过程中您会看到一些需要输入内容的屏幕提示，也是如此。您可以安心地忽略这些提示。它们是由 `evault_manual.sh` 脚本所启动的子脚本生成的。`evault_manual.sh` 脚本会提供这些提示的输入内容。
4. 当出现类似以下内容的消息时，表明安装完成：
   ```
  Starting VVAgent: [  OK  ]
  Starting buagent: [  OK  ]
  ```
   {: codeblock}
   
## 验证安装是否成功

1. 验证安装输出中是否显示“已注册到门户网站”消息。可通过在屏幕上查找消息或通过检查以下命令的输出来完成验证：
   ```
  grep 'Registered'  /opt/BUAgent/Install.log
  ```
   {: pre}

2. 运行以下命令并观察输出。
   ```
  service vvagent status
  ```
   {: pre}
   
   这将显示以下消息。
   ```
  VVAgent is running (PID xxxxx).
  buagent is running (PID xxxxx).
  ```
   {: codeblock}
   
  >**注** - 上述由 `xxxxx` 表示的进程标识因各个安装而异。 
  
**后续步骤**

登录到 WebCC 以配置和管理备份代理程序。有关指示信息，请参阅[入门教程](index.html#configuring-evault-agent-in-webcc)。
