---
copyright:
  years: 1994, 2017
lastupdated: "2017-09-27"

keywords: Microsoft Windows Update, software update services

subcollection: software

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}

# Microsoft Windows 更新資訊
{: #microsoft-windows-update-information}

IBM 免費提供 Microsoft Windows Server 環境的 OS 及軟體更新服務。

{{site.data.keyword.Bluemix_notm}} 的所有更新服務共用下列特性：
* 更新資料流量是透過專用 VLAN 從伺服器遞送至專用服務網路
* 更新資料流量是無限制專用網路頻寬的一部分。此資料流量不會減少公用頻寬分配。
* 更新速度比直接從供應商更新還要快（依需求提供升級的埠速度）
* 在全球大量重要更新日期間，很容易取得更新。
* 在緊急狀況下，可以關閉公用埠，同時仍然容許透過專用網路進行更新
* 伺服器預先配置成在部署時使用依需求提供的手動更新進行自動更新。


{{site.data.keyword.Bluemix_notm}} 更新伺服器位於具有下列位置 ID 的專用服務網路上。

Microsoft，**wsus01.service.softlayer.com**

請一律先測試核心或服務套件升級，然後再安裝至正式作業伺服器環境。您可以在控制入口網站內的常見問題或驅動程式區段中，尋找特定硬體、OS 以及 IBM 部署的應用程式的相關技術資訊。IBM 會持續測試核心和服務套件升級以及張貼相關資訊（包括驅動程式）來協助升級處理程序。


## WSUS Windows Server 更新服務
{: #wsus-windows-server-update-services}

在許多情況下，Microsoft Windows 伺服器會從本端 Windows Server Update Services (WSUS) 伺服器取回更新。不過，如果您的伺服器已經配備已啟用 cloud-init 的映像檔，您可能需要手動更新 Windows 登錄，改成使用本端 {{site.data.keyword.cloud_notm}} Windows Server Update Services (WSUS) 伺服器，而不是預設 Microsoft WSUS 伺服器。

如果您訂購具有 Windows Server 作業系統但不含任何附加程式（例如，更多軟體、佈建後 Script，或進階監視）的虛擬伺服器，則您的伺服器有可能已佈建有 cloud-init 映像檔。如需更新您的登錄以指向 {{site.data.keyword.cloud_notm}} WSUS 伺服器的相關資訊，請參閱[將實例更新為使用本端 WSUS 伺服器](/docs/infrastructure/software?topic=software-updating-an-instance-to-use-a-local-wsus-server)。

針對 Microsoft Windows 作業系統，依預設，會配置伺服器在修補程式可用時盡快下載並安裝。如果需要重新啟動，伺服器會自動重新啟動。完成這些更新有助於防範伺服器出現嚴重漏洞。如果您偏好以不同的方式排定更新，您可以透過控制台中的 **Windows Updates** 特性來變更更新排程。
