---

copyright:
  years: 2017, 2018
lastupdated: "2018-04-08"

keywords: R1Soft

subcollection: software

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}

# 使用 R1Soft Tivoli Continuous Data Protection for Files 還原伺服器

如果伺服器故障導致遺失資料或 OS，請使用此程序來完成將[裸機還原](http://wiki.r1soft.com/display/CDP/Bare-Metal+Restore){:new_window}成 {{site.data.keyword.BluSoftlayer_full}} 公用或專用虛擬伺服器 (VSI)。

所有備份的檔案系統區塊都會被還原，包括 OS 以及未從備份排除的任何檔案。如果您要還原一部分的檔案，請勿執行此程序。若只要還原檔案，請參閱 [http://wiki.r1soft.com/display/CDP/Restoring+Files](http://wiki.r1soft.com/display/CDP/Restoring+Files){:new_window}。

## 準備 R1Soft Tivoli Continuous Data Protection for Files 伺服器

1. 開啟瀏覽器視窗然後登入 R1Soft Tivoli Continuous Data Protection for Files 伺服器（IP 和管理者密碼在 [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window} 中提供）。
2. 按一下 R1Soft Tivoli Continuous Data Protection for Files 管理入口網站上的**回復點**。
3. 選取您要還原的**伺服器**以及您要從其還原的**磁碟安全**。
4. 從回復點清單尋找您要從其進行還原的點。
5. 按一下**裸機還原**（防護圖示）來啟動**還原精靈**。
6. 按一下 **還原精靈**上的**下一步**。
7. 選取要還原的檔案系統，然後按一下**下一步**。
8. 選取還原目的地的主機。可以是原始主機，也可以是不同的主機。（附註：此程序中的步驟會回復至相同伺服器。）
9. 按**下一步**。
10. 選擇要使用的儲存空間配置（請使用伺服器上現有的儲存空間配置，或者根據備份選擇一個）。
11. 如果您選擇檔案系統佈置，請選取您要使用的**分割區表格**。
12. 將您的檔案系統對映至正確的區塊裝置（例如 C:\ = /dev/sda1），然後按**下一步**。
13. 選取還原選項，例如**還原之後重新開機**、**還原之後檢查檔案系統**，然後按**下一步**。
14. 驗證您的選項，然後按一下**還原**，或者返回以變更還原選項。

將會顯示內含現行還原狀態的視窗

## 準備還原的裝置

1. 開啟瀏覽器視窗，然後存取 [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}。
2. 依序按一下**裝置**，**裝置清單**，然後選取要還原的裝置。
3. 按一下**動作**，然後選擇**從映像檔開機**來顯示專用映像檔清單。
4. 從功能表選擇**公用映像檔**。
4. 針對您的 R1Soft 伺服器版本 (*r1soft-cdp-bootcd-server-4.0.0.iso*) 選擇適當的 R1Soft 代理程式開機映像檔，然後按一下**從此映像檔開機**。
5. 從您正在還原的伺服器的「裝置詳細資料」頁面中，依序按一下**動作**，**KVM 主控台**。主控台開啟且映像檔啟動之後，您會看到內含數個選項的 Debian 開機載入器畫面。
6. 按 **Enter** 來使用預設選項開機。
7. OS 啟動之後，從 r1soft-recovery 提示鍵入 netconfig，然後按 **Enter**。
8. 選擇**是**以配置網路。
9. 從**裝置詳細資料**頁面輸入網路配置詳細資料。
10. 出現重新啟動網路的提示時，按一下**是**。
11. **選用**：鍵入 `passwd root` 來設定 SSH 登入的 root 密碼，以及鍵入 `service ssh` start 來容許 SSH 登入，這在您的 KVM 主控台回應速度緩慢時非常有用。
12. 鍵入 `service cdp-agent restart`。這個指令會啟動 Tivoli Continuous Data Protection for Files 代理程式（即使該代理程式尚未執行）。
13. 選取**從映像檔開機**。隨即顯示一個畫面，指示裝置配置成從 *r1soft-cdp-bootcd-agent-4.0.0.iso* 映像檔開機。將會出現提示，詢問您是否要卸載映像檔以及返回至一般開機。
14. 按一下**是**，伺服器將從系統磁碟重新開機

伺服器將會執行 chkdsk 或 fsck 處理程序來驗證磁碟，而且有可能會重新啟動。處理程序完成之後，您的伺服器或 VM 即可使用您從所選擇還原點還原的資料正常作業。
