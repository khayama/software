---
copyright:
  years: 1994, 2017
lastupdated: "2017-08-23"

subcollection: software
---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}



# RedHat 更新資訊

IBM 免費提供 RedHat 環境的 OS 及軟體更新服務。

IBM 的所有更新服務都共用下列特性：
* 更新資料流量是透過專用 VLAN 從伺服器遞送至專用服務網路
* 更新資料流量是無限制專用網路頻寬的一部分，而且不會減少公用頻寬分配。
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

請一律先測試核心或服務套件升級，再安裝於正式作業伺服器環境上。在客戶「Web 入口網站」的常見問題 (FAQ) 或驅動程式區段中，您可以發現特定硬體、OS 以及所部署的應用程式的相關技術資訊。IBM 會測試核心及服務套件升級，並張貼相關資訊（包括驅動程式），以協助升級處理程序。

## RHN 訂閱

針對 RedHat 作業系統，IBM 提供「RedHat 網路衛星」伺服器來安裝重大及非重大安全更新。

RedHat Network at SoftLayer 包括「RHN 衛星」及 Proxy 伺服器。RedHat 伺服器在佈建時，會使用適當的 Proxy 伺服器自動登錄至「IBM RHN 衛星」伺服器。這項登錄可讓您在伺服器上本端使用 **up2date** 指令，並跨專用服務網路來取回更新。

為了確保企業服務品質，並協助適當的變更管理技術，依預設，會配置 RedHat OS 伺服器來跳過核心更新。若要確保系統穩定性，請在完成回歸測試之後手動執行核心升級。IBM 會使用需要穩定核心版本的尖端硬體技術，以獲得適當的效能。
