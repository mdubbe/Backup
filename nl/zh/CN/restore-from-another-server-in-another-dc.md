---

copyright:
  years: 1994, 2018
lastupdated: "2018-07-05"

---
{:pre: .pre}
{:new_window: target="_blank"}

# 在不同数据中心内的 VSI 之间创建备份并复原数据

有时，您会希望将数据复原到其他服务器。此过程仅适用于非操作系统文件的文件级别复原。要复原系统映像，请遵循 [Windows BMR](restoring-evault-bmr-system-volume-image.html) 指示信息。

此过程包括在第二个服务器上重新注册 EVault 代理程序以访问第一个服务器的 EVault 位置，以及完成**从其他计算机复原**。

**先决条件**

- Server1 和 Server2 必须具有相同的操作系统。不支持跨平台复原。
- Server1 和 Server2 必须拥有先前已配置的 EVAult 代理程序。要了解如何配置 EVault 代理程序，请单击[此处](index.html#configuring-evault-agent-in-webcc)。
- Server1 的备份作业已在 Server1 EVault 位置生成了备份。

**注**：禁用这两台服务器上的所有调度任务以避免发生任何冲突。 

## 启动 Server2 的 WebCC

>**注** - 请务必启动 {{site.data.keyword.BluVPN}} 连接来访问 {{site.data.keyword.BluSoftlayer_full}} 专用网络，否则 WebCC 链接将不起作用。

1. 登录到 [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}，然后单击主菜单中的**存储** > **备份**，以显示具有 EVault Backup 服务的服务器。 
2. 选择 Server2。单击指向右方的展开箭头以显示 WebCC 链接。
3. 单击 **WebCC 登录**，以在浏览器中启动 WebCC 客户机。

## 重新注册 EVault

1. 单击**所有代理程序**，然后打开要修改的特定代理程序。
2. 单击**编辑**，然后选择**保险库设置**。
3. 单击**重新注册**以将 Server1 连接到 Server2。
4. 在**重新注册保险库**屏幕上，对于**使用保险库概要文件**条目，选择**输入保险库设置**。
5. 输入保险库名称，该名称与 Server1 的 EVault 名称相同。
6. 输入 Server1 的凭证以登录到 Server1 的 EVault。
7. 单击**装入计算机**，此操作将显示与保险库位置连接的服务器。
8. 单击**保存更改**。
9. 在出现提示时，单击**是**以确认重新注册 EVault。

## 在 Server2 上将 Server1 的备份作业作为复原作业运行

1. 单击**所有代理程序**。
   >**注** - 您可能需要刷新页面才能在 Server2 的**作业**选项卡下看到 Server1 上定义为可访问/已同步的作业
2. 将鼠标悬停在**高级**上，然后选择**从其他计算机复原**。
3. 在**从其他计算机复原**屏幕上，单击**添加**。这些字段会使用缺省值自动填充，因此请更改这些字段。
4. 单击“保险库”字段，选择**输入保险库设置**，然后输入 Server1 的保险库的 IP 地址。单击**添加**。
5. 将凭证更新为 Server1 的凭证。
6. 单击**保存更改**。此操作将连接到 Server1 的保险库。
7. 返回到**从其他计算机复原**屏幕，更新“计算机”和“作业”字段。
  - 计算机 - 选择 Server1 作为要从中进行复原的备份计算机。 
  - 作业 - 选择 Server1 中的备份作业。
8. 单击**下一步**以启动复原到其他数据中心内 server2 的过程。
9. 在出现提示时，输入备份密码，然后单击**下一步**。
10. 确认选择的是正确的备份作业，然后单击**下一步**。现在，已在 server2 上配置复原作业。 
11. 选择新配置的作业，然后单击**运行复原**。
12. 选择要复原的文件。 
13. 单击加号以展开文件选择。
14. 单击要从 server1 复原到 server2 的各个文件或文件夹的复选框。然后，单击**包含**。
15. 这些文件将填充右侧的“备份集”窗口。单击**下一步**。 
16. 完成数据选择后，继续选择选项。
    - 选择**复原到原始位置**。
    - 选择**覆盖现有文件**。
17. 单击**运行复原**。“过程详细信息”窗口将提供正在运行的备份作业的状态。完成备份后，单击**关闭**。


## 验证复原

1. 通过 SSH 连接到 Server2 的根目录。
2. 以长格式列出文件和所有目录条目。
  ```
  ls -la
  ```
  {: pre}
  
3. 对比输出。
  
## 恢复正常的备份安排。

1. 复原完成后，除去从中复原数据的 Server1 的注册信息。 
2. 输入当前 Server2 注册信息并启用调度任务。
