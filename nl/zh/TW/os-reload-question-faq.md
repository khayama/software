---
copyright:
  years: 1994, 2017
lastupdated: "2017-09-25"

keywords: OS Reload, Operating System, cpsrvd email

subcollection: software

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}
{:faq: data-hd-content-type='faq'}

# 常見問題
{: #faqs}

## 可以變更裝置上的「作業系統 (OS)」嗎？
{: #can-the-operating-system-os-be-changed-on-the-device-}

重新載入 OS<!--[OS Reload](perform-os-reload-device.html){:new_window}-->，即可變更所安裝的 OS 及軟體。在裝置上選取「OS 重新載入」之後，系統會顯示可讓您更新系統上軟體的頁面鏈結。您可以從這個頁面更新 OS、「控制台」、「防毒套件」及資料庫軟體。

## 您要提供增補 OS 重新載入嗎？
{: #do-you-provide-complimentary-os-reloads-}

自動化 OS 重新載入是免費的，包括自訂的 OS 重新載入（例如，變更作業系統、新增或移除控制台、分割區編輯及其他選項）。如需相關資訊，請開啟「客戶入口網站」。

## 如何追蹤 OS 重新載入的狀態？
{: #how-can-i-track-the-status-of-the-os-reload-}

在「客戶入口網站」的「硬體」下，您的每一部伺服器都會有「附註」區段。「附註」區段包括下列資訊的鏈結：重新載入的現行步驟，以及完成該重新載入部分的估計時間。

## OS 重新載入可以刪除次要磁碟嗎？
{: #can-an-os-reload-erase-secondary-disks-}

OS 重新載入只會格式化系統上的主要磁碟。所有其他磁碟將會保持不變。此運用方式與從映像檔範本重新載入時相同。如果範本包含多個磁碟，則只會格式化主要磁碟。將不會對其他磁碟進行變更。

## 為何我的 cpsrvd 電子郵件會失敗？
{: #why-did-my-cpsrvd-email-fail-}

在大部分情況下，當您收到指出 **cpsrvd 失敗**的電子郵件時，該電子郵件是在重新開機之後立即傳送。chkservd 嘗試驗證 cpsrvd 處理程序時，會發生此錯誤。驗證失敗是因為處理程序尚未啟動。

如果您收到來自 chkservd 服務並指出 cpsrvd 失敗的電子郵件，則大部分情況下都可以忽略訊息。不過，如果您連續收到 5 則以上的訊息，或者在重新啟動之後當天收到 4 則以上的訊息，請開立支援問題單。
