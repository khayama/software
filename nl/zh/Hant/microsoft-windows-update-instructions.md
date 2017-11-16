---
copyright:
  years: 1994, 2017
lastupdated: "2017-09-27"
---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}

# Microsoft Windows 更新資訊
IBM 免費提供 Microsoft Windows Server 環境的 OS 及軟體更新服務。

SoftLayer 中的所有更新服務都具有下列特性：
* 更新資料流量是透過專用 VLAN 從伺服器遞送至專用服務網路
* 更新資料流量是無限制專用網路頻寬的一部分，而且不會減少公用頻寬分配。
* 更新速度比直接從供應商更新還要快（依需求提供升級的埠速度）
* 在全球大量重要更新日期間，很容易取得更新。
* 在緊急狀況下，可以關閉公用埠，同時仍然容許透過專用網路進行更新
* 伺服器預先配置成在部署時使用依需求提供的手動更新進行自動更新。


SoftLayer 更新伺服器位在具有下列位置 ID 的專用服務網路上。

Microsoft：**wsus01.service.softlayer.com**

請一律先測試核心或服務套件升級，再將它們安裝至正式作業伺服器環境中。在客戶「Web 入口網站」的常見問題 (FAQ) 或驅動程式區段中，您可以發現特定硬體、OS 以及 IBM 所部署應用程式的相關技術資訊。IBM 工程師會持續測試核心及服務套件升級，並張貼相關資訊（包括驅動程式），以協助升級處理程序。


## WSUS - Windows Server 更新服務

Microsoft Windows Server 會自動從本端「Windows Server 更新服務 (WSUS)」伺服器取回更新項目。

針對 Microsoft Windows 作業系統，依預設，會配置伺服器在修補程式可用時盡快下載並安裝。伺服器在需要時會自動重新啟動。進行這些更新，有助於保護伺服器不出現決定性漏洞。如果您偏好以不同的方式排定更新項目，則可以透過「控制台」中的 **Windows Updates** 特性來變更更新排程。
