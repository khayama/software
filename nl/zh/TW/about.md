---
copyright:
  years: 2017, 2018
lastupdated: "2018-02-08"

keywords: software

subcollection: software
---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}

# 關於軟體
{: #about-software}

{{site.data.keyword.BluSoftlayer_full}} 具有與供應商的策略關係，可提供 32 位元及 64 位元相容軟體上的月對月授權。當您訂購裝置時，請選取您裝置的作業系統及軟體類型。您可以在 {{site.data.keyword.slportal_full}} 內對裝置新增更多軟體，以及透過在現有裝置上重新載入 OS 來切換至另一個作業系統。IBM 自動化系統會使用每一個供應商的最佳作法準則來確保最大穩定性及可用性，以將軟體佈建至伺服器。

請參閱下列目前支援的軟體清單：[雲端伺服器軟體 ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://www.ibm.com/cloud-computing/bluemix/node/153){: new_window}。

如果您需要目前不支援的軟體，請使用伺服器的 root 存取權，以針對該軟體安裝及配置您自己的版本。若要回到您裝置上受支援的版本，請重新載入 OS。

IBM 已加入在 {{site.data.keyword.BluSoftlayer_notm}} 環境中使用產品的指示或考量。如需軟體文件，請參閱軟體生產供應商的文件。

## IBM Cloud 虛擬伺服器支援的作業系統
{: #supported-operating-systems-for-ibm-cloud-virtual-servers}

IBM Cloud 虛擬伺服器支援下列作業系統。

- Cent OS 6 (PV)
- Cent OS 7 (HVM)
- Debian 7 (PV)
- Debian 8 (HVM)
- Debian 9 (HVM)
- RHEL 6 (PV)
- RHEL 7 (HVM)
- Ubuntu 14 (PV/HVM) 預設為 PV 開機模式，但您可以切換至 HVM 開機模式
- Ubuntu 16 (PV/HVM) 預設為 PV 開機模式，但您可以切換至 HVM 開機模式
- Windows 2012 (HVM)
- Windows 2012 R2 (HVM)
- Windows 2016 (HVM)

**附註：**開機磁碟大小因作業系統而有所不同：<br>  
Linux OS 支援 25 GB 和 100 GB。
Windows 僅支援 100 GB。

如需在 PV 和 HVM 開機模式之間切換的相關資訊，請參閱下列鏈結：
* [虛擬來賓支援的開機模式 ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://sldn.softlayer.com/reference/services/SoftLayer_Virtual_Guest_Block_Device_Template_Group/getSupportedBootModes){: new_window}
* [新增開機模式選項 ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://github.com/softlayer/softlayer-python/pull/936/files/09c35a9595651d66f3e117a055efe585745ba2b3){: new_window}
