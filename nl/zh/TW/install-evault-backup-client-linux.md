---

copyright:
  years: 1994, 2018
lastupdated: "2018-07-02"

---
{:codeblock: .codeblock}
{:pre: .pre}
{:new_window: target="_blank"}

# 在 Linux 中安裝 EVault 備份用戶端 

在 Linux 型作業系統上安裝 EVault 備份用戶端，可透過作業系統內 Shell 或終端機中的一系列指令來完成。此程序概述在下列任何 Linux 型作業系統上安裝 EVault 備份用戶端所需的步驟：

- RedHat Enterprise Linux
- CentOS
- CloudLinux

在完成此程序之後，自動化處理程序會使用 WebCC 登錄「代理程式」服務，然後下載並安裝執行該服務所需的檔案。

>**附註**：當您在 {{site.data.keyword.slportal}} 中訂購伺服器時，如果您已購買 EVault，則會自動為您安裝軟體。您不需要使用本文件所述的程序。

如果已在 {{site.data.keyword.slportal}} 以升級方式購買了 EVault，請遵循下列步驟來安裝軟體。

## 登入目標裝置伺服器

1. 登入 [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}，並從主功能表中選取**裝置** > **裝置清單**，以查看可用伺服器裝置的清單。
2. 找出您已為其購買 EVault 服務的裝置，並記下其公用 IP 位址。 
  - 從 UNIX 或 Linux 指令行登入裝置時，會在接下來的步驟使用此 IP 位址。在步驟 4 所顯示的指令中，將 <publicIpAddress> 取代為實際公用 IP 位址。 
3. 按一下指向右方的箭頭來顯示裝置的相關資訊，包括使用者名稱和密碼。 
  - 如果未顯示密碼，則按一下**顯示密碼**即可顯示密碼。在下一步中，使用者名稱和密碼會用來登入測試裝置。在後續指令中，將 `<user name>` 取代為實際使用者名稱。
4. 從 UNIX 或 Linux 指令行輸入下列指令，以登入目標裝置。
   ```
  ssh <user name>@<publicIpAddress>
  ```
   {: pre}
   
   >**附註**：如果您之前未使用此使用者名稱登入此伺服器，則會看到關於主機確實性的訊息。系統也會詢問您是否要繼續。回覆**是**以繼續。
5. 除非您先前已設定 SSH 金鑰來存取此伺服器，否則系統會提示您輸入密碼。

## 更新 Linux 以準備安裝 EVault 用戶端（僅限 RedHat Linux）
>**附註**：這對於 RedHat Linux 是必要步驟，但對於其他 Linux 發行套件則為選用步驟。

- 在伺服器提示處執行下列指令。
  ```
  yum update
  ```
  {: pre}
   
  如果系統提示您，請確認下載大小沒問題。更新會繼續，並在完成時顯示「完成！」訊息。

## 取得 EVault 安裝 Script

- 在伺服器提示處執行下列指令。
  ```
  wget -N http://downloads.service.softlayer.com/evault/evault_manual.sh
  ```
  {: pre}
   
## 執行 EVault 安裝 Script

1. 在伺服器提示處執行下列指令。
   ```
  sh ./evault_manual.sh
  ```
   {: pre}

2. 輸入您的 WebCC 使用者名稱和密碼。     
   >**附註**：如需檢視 EVault 備份使用者名稱及密碼的指示，請參閱[開始使用備份服務](/docs/infrastructure/Backup/index.html)一文。
3. 在使用者名稱和密碼之後，不需要任何進一步輸入，即使您在安裝繼續進行時看到部分提示寫入至畫面。您可以安心地忽略這些提示。它們是由 `evault_manual.sh` Script 所啟動的子 Script 所產生。`evault_manual.sh` Script 會提供這些提示的輸入。
4. 當類似如下的訊息出現時，表示安裝已完成：
   ```
  Starting VVAgent: [  OK  ]
  Starting buagent: [  OK  ]
  ```
   {: codeblock}
   
## 驗證安裝成功

1. 驗證 "Registered to The Portal." 訊息是否出現在安裝輸出中。驗證的方式是在畫面上尋找此訊息，或檢查下列指令的輸出：
   ```
  grep 'Registered'  /opt/BUAgent/Install.log
  ```
   {: pre}

2. 執行下列指令並觀察輸出。
   ```
  service vvagent status
  ```
   {: pre}
   
   即會顯示下列訊息。
   ```
  VVAgent is running (PID xxxxx).
  buagent is running (PID xxxxx).
  ```
   {: codeblock}
   
  >**附註**：`xxxxx` 所表示的處理程序 ID 會隨著每個安裝而不同。 
  
**後續步驟**

登入 WebCC，以配置及管理您的備份代理程式。如需指示，請參閱[入門指導教學](index.html#configuring-evault-agent-in-webcc)。
