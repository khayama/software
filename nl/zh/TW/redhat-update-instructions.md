---
copyright:
  years: 1994, 2017
lastupdated: "2017-08-23"

keywords: Red Hat, RedHat

subcollection: software
---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}

# Red Hat 更新指示
{: #red-hat-update-instructions}

IBM 針對 Red Hat 環境提供免費 OS 和 軟體更新服務。

IBM 的所有更新服務都共用下列特性：
* 更新資料流量是透過專用 VLAN 從伺服器遞送至專用服務網路
* 更新資料流量是無限制專用網路頻寬的一部分。此資料流量不會減少公用頻寬分配。
* 更新速度比直接從供應商更新還要快（依需求提供升級的埠速度）
* 在全球大量重要更新日期間，很容易取得更新。
* 在緊急狀況下，可以關閉公用埠，同時仍然容許透過專用網路進行更新
* 伺服器預先配置成在部署時使用依需求提供的手動更新進行自動更新。

IBM 更新伺服器位在具有下列位置 ID 的專用服務網路中。

|資料中心|服務主機位址|
|---|---|
|阿姆斯特丹|rhnproxyams0101.service.softlayer.com|
|達拉斯|rhnproxy101.service.softlayer.com|
|休斯頓|rhnproxy421.service.softlayer.com|
|聖荷西|rhnproxy501.service.softlayer.com|
|西雅圖|rhnproxy201.service.softlayer.com|
|新加坡|rhnproxysng0101.service.softlayer.com|
|華盛頓特區|rhnproxy301.service.softlayer.com|

請一律先測試核心或服務套件升級，然後再安裝至正式作業環境。您可以在控制入口網站內的常見問題或驅動程式區段中，尋找特定硬體、OS 以及部署的應用程式的相關技術資訊。

IBM 會測試核心和服務套件升級以及張貼相關資訊和驅動程式，來協助您升級處理程序。

## RHN 訂閱
{: #rhn-subscription}

對於 Red Hat 作業系統，IBM 提供 Red Hat Network Satellite 伺服器來安裝重大和非重大安全更新。

Red Hat Network at {{site.data.keyword.Bluemix_notm}} 包括 RHN Satellite  和 Proxy 伺服器。在佈建 Red Hat 伺服器時，會使用適當的 Proxy 伺服器自動登錄至 IBM RHN Satellite  伺服器。藉由此登錄，您可以在伺服器上以本端方式使用 **up2date** 指令，以及透過專用服務網路取回更新。

為了確保企業服務品質以及協助適當的變更管理技術，依預設，Red Hat OS 伺服器配置為跳過核心更新。若要確保系統穩定性，請在完成回歸測試之後手動完成核心升級。IBM 會使用需要穩定核心版本的尖端硬體技術，以獲得適當的效能。
