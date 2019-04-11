---

copyright:
  years: 2017, 2018
lastupdated: "2018-04-08"

keywords: R1Soft, restoring OS, restoring bare metal

subcollection: software

---
{:new_window: target="_blank"}
{:shortdesc: .shortdesc}

# 從 R1Soft 映像檔還原您的伺服器
{: #restoring-your-server-from-an-r1soft-image}

請使用此程序來完成還原至公用或專用 {{site.data.keyword.BluVirtServers_full}} 或 {{site.data.keyword.BluBareMetServers_full}}。如果伺服器故障導致遺失資料或 OS，請使用此程序。此程序可還原所有備份的檔案系統區塊（包括 OS 以及未從備份排除的任何檔案）。

如果還原目標為一部分的檔案，請勿使用此程序。若只要還原檔案，請參閱 [R1Soft Wiki](http://wiki.r1soft.com/display/CDP/Restoring+Files){:new_window}。

## 還原您的虛擬裝置
{: #restoring-your-virtual-device}

1. 按一下 [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window} 中您要還原的裝置。
2. 按一下**動作**功能表，然後選擇**從映像檔開機**，您會取得專用映像檔清單。
3. 從功能表選擇**公用映像檔**。
4. 針對您的 R1Soft 伺服器版本 (serverbackup-centos-bootcd-agent.iso) 選擇適當的 R1Soft 代理程式開機映像檔，然後按一下右邊的**從此映像檔開機**鏈結。
5. 從您正在還原的伺服器的**裝置詳細資料**頁面中，按一下**動作** > **KVM 主控台**。
6. 主控台開啟且映像檔啟動之後，您會看到內含數個選項的 Debian 開機載入器畫面。請按 Enter 鍵來從預設選項開機。
7. OS 啟動之後，鍵入 `netconfig`，然後按 **Enter**。
8. 選擇**是**來配置網路。
9. 從控制入口網站中的裝置詳細資料輸入網路配置詳細資料。
10. 出現重新啟動網路的提示時，選擇**是**。
11. 選擇性地鍵入 `passed root` 來設定 SSH 登入的 root 密碼，並鍵入 service ssh start 來容許 SSH 登入。如果您的 KVM 主控台速度緩慢，此步驟可很有用。
12. 鍵入 `service cdp-agent restart`（此指令會在 Tivoli Continuous Data Protection for Files 代理程式尚未執行時啟動該代理程式）。

## 還原您的裸機裝置
{: #restoring-your-bare-metal-device}

1. 在 [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window} 中開立問題單，並要求以 **R1Soft 裸機還原模式**啟動裸機伺服器。
2. 使用您正在還原的伺服器的**裝置詳細資料**頁面，登入 **IPMI KVM 主控台**。
3. 主控台開啟且映像檔啟動之後，您會看到內含數個選項的 Debian 開機載入器畫面。請按 Enter 鍵來從預設選項開機。
4. OS 啟動之後，鍵入 `netconfig`，然後按 **Enter**。
5. 選擇**是**來配置網路。
6. 從控制入口網站中的裝置詳細資料輸入網路配置詳細資料。
7. 出現重新啟動網路的提示時，選擇**是**。
8. 選擇性地鍵入 `passed root` 來設定 SSH 登入的 root 密碼，並鍵入 service ssh start 來容許 SSH 登入。如果您的 KVM 主控台速度緩慢，此步驟可很有用。
9. 鍵入 `service cdp-agent restart`（此指令會在 Tivoli Continuous Data Protection for Files 代理程式尚未執行時啟動該代理程式）。

## 選取 R1Soft 伺服器及其他還原參數與選項
{: #selecting-the-r1soft-server-and-other-restore-parameters-and-options}

請參閱 R1Soft 文件來瞭解[執行裸機還原](http://wiki.r1soft.com/display/ServerBackup/Perform+a+bare-metal+restore)。您需要選選取要還原的伺服器，以及選取檔案系統、部分表格，和其他還原選項。
