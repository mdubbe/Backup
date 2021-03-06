---

copyright:
  years: 1994, 2018
lastupdated: "2018-08-13"

---
{:pre: .pre}
{:new_window: target="_blank"}

# 在 Windows 2016 上配置 EVault

## 安装 EVault Software Agent

1. 在目标服务器上，打开浏览器会话，然后输入以下 URL 来下载可执行文件
   ```
   http://downloads.service.softlayer.com/evault/
   ```
   {:pre}
   >**注**：请安装 V8.30 和更高版本的代理程序。
2. 双击下载的文件，然后在显示的窗口中单击**运行**。
3. 选择用于安装的语言，然后单击**确定**。
4. 单击**下一步**以开始。
5. 阅读条款和条件，然后选择**我接受许可协议中的条款**。然后，单击**下一步**。
6. 对于“安装类型”，选择**典型**。单击**下一步**。
7. 在“向门户网站注册代理程序”屏幕中，选择**跳过注册**。单击**下一步**
8. 在下一个屏幕上，单击**安装**。
9. 安装完成后，单击**完成**。

## 安装 EVault Software CentralControl 8.30

1. 在目标服务器上，打开浏览器会话，然后输入以下 URL 来下载可执行文件。

   ```
   http://downloads.service.softlayer.com/evault/CentralControl/
   ```
   {:pre}

2. 双击下载的文件，然后在显示的窗口中单击**运行**。
3. 执行**典型**安装的安装步骤。
   1. 系统提示您添加桌面快捷方式时，选择**是**。单击**下一步**。
   2. 阅读软件许可协议后，选择**接受**。单击**下一步**。
   3. 保留缺省目标文件夹，然后单击**下一步**。
4. 安装完成后，选中**启动 EVault Software Central Control**。单击**完成**。


## 配置 CentralControl

可通过登录到为 EVault Backup 服务指定的服务器并进行一系列交互操作来完成此任务。

1. 通过 RDP 远程控制您的服务器。
2. 启动 CentralControl。
3. 在工作空间中，右键单击 **MyAgent**，然后选择**代理程序配置**。
4. 在“保险库”选项卡上，单击**新建**。这将显示“保险库配置向导”。单击**下一步**。
5. 选择**注册为新计算机**，然后单击**下一步**。
6. 在“概要文件名称”字段中，输入保险库名称。保险库名称可以在 [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window} 中获取。
6. 输入网络地址（分配的保险库的 IP 地址），然后单击**添加**。然后，单击**下一步**。
7. 输入新的端口值，单击**添加**，然后单击**下一步**。
8. 在“连接设置”屏幕中，输入所需的秒数/分钟数。使**针对与保险库之间的传输启用线上加密**框保持选中。单击**下一步**。
9. 在“认证”屏幕中，输入您的凭证，然后单击**下一步**。
10. “已注册的计算机”窗口会显示您的服务器的主机名。单击**下一步**。
11.	单击**完成**以完成配置。


## 创建 EVault 保留方案

1. 通过 RDP 远程控制您的服务器。
2. 启动 CentralControl。
3. 在工作空间中，右键单击 **MyAgent**，然后选择**代理程序配置**。
4. 单击**保留**选项卡。这将显示“保留向导”，请单击**下一步**。
5. 输入保留名称。单击**下一步**。<br/>
   **注** - 此条目最多可以包含 32 个字母数字字符。不允许使用空格，但可以使用下划线 (`_`) 和短划线 (`-`)。
6. 输入此保留类型的在线保留天数和副本数。然后，单击**下一步**。<br/>
   **注** - 保留天数和副本数的组合用于确保保留最短持续时间和备份数。
7. 选择**我不想创建任何归档备份副本**。单击**下一步**。
8. 单击**完成**以完成保留方案的配置。


## 设置 EVault 作业

1. 通过 RDP 远程控制您的服务器。
2. 启动 CentralControl。
3. 在工作空间中，右键单击 **MyAgent**，然后选择**新建作业**。 
4. 在欢迎屏幕上，单击**下一步**。
5. 选择备份源类型。
6. 对于编码，选择 **Unicode**。单击**下一步**。
7. 选择此作业的目标位置。单击**下一步**。
8. 输入作业的名称及其描述。<br/>
   **注** - 名称长度必须为 1 到 30 个字符。名称可以包含字母、数字、下划线 (`_`)、连字符 (`-`) 和美元符号 (`$`)。
9. 选择数据源。单击**添加**。
10. 指定处理和备份时间选项。选中**快速文件扫描**，并输入希望作为备份时段的小时或分钟。然后，单击**下一步**。
11. 选择加密类型（缺省设置为 AES 256 位），然后输入加密密码。单击**下一步**
12. 选择作业的日志选项。选中**创建日志文件**，然后选择**仅自动清除到期的日志文件**。然后，单击**下一步**
13. 选择**仅从此向导退出**，然后单击**完成**以完成配置。新作业现在显示在 MyAgent 下。


## 运行 EVault 作业

1. 通过 RDP 远程控制您的服务器。
2. 启动 CentralControl。
3. 在工作空间中，右键单击 **MyAgent**，然后选择已创建的代理程序。
4. 在欢迎屏幕上，单击**下一步**。
5. 选择要在其中存储备份作业种子的备份目标或替代位置。单击**下一步**。<br/>
   *提示* - 有关多个保险库的更多信息，请参阅[多保险库技术](multivaulting.html)
6. 选择“快速文件扫描”选项以避免读取未更改的文件。单击**下一步**。
7. 单击**完成**以完成配置并启动备份。这将显示一个过程信息窗口，其中显示备份作业的状态。完成备份作业后，单击**关闭**。
