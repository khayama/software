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

# ソフトウェアについて
{: #about-software}

{{site.data.keyword.BluSoftlayer_full}} は、ベンダーと戦略的な関係を構築することにより、32 ビットおよび 64 ビットの互換ソフトウェアの月次ライセンスを提供しています。  お客様は、デバイスを注文する際に、デバイスのソフトウェアとオペレーティング・システムのタイプを選択します。 {{site.data.keyword.slportal_full}} 内でさらに多くのソフトウェアをデバイスに追加することができ、既存のデバイスで OS を再ロードすることによって
別のオペレーティング・システムに変更することができます。IBM の自動化システムは、安定性と可用性を最大化するため、各ベンダーの最良事例指針を使用してお客様のサーバーへソフトウェアをプロビジョンします。

現在サポートされているソフトウェアのリストについては、[Cloud server software ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")](https://www.ibm.com/cloud-computing/bluemix/node/153){: new_window} を参照してください。

現在はサポートされていないソフトウェアが必要な場合、サーバーへの root アクセス権限を使用して、そのソフトウェアのお客様独自のバージョンをインストールおよび構成してください。  デバイスでサポートされているバージョンに戻すには、OS を再ロードしてください。

{{site.data.keyword.BluSoftlayer_notm}} 環境で製品を使用するための手順と考慮事項は IBM によって組み込まれています。ソフトウェア資料については、そのソフトウェアを作成したベンダーの資料を参照してください。

## IBM Cloud 仮想サーバーでサポートされているオペレーティング・システム
{: #supported-operating-systems-for-ibm-cloud-virtual-servers}

IBM Cloud 仮想サーバーでは、以下のオペレーティング・システムがサポートされています。

- Cent OS 6 (PV)
- Cent OS 7 (HVM)
- Debian 7 (PV)
- Debian 8 (HVM)
- Debian 9 (HVM)
- RHEL 6 (PV)
- RHEL 7 (HVM)
- Ubuntu 14 (PV/HVM) のデフォルトは PV ブート・モードですが、HVM ブート・モードに切り替えることができます
- Ubuntu 16 (PV/HVM) のデフォルトは PV ブート・モードですが、HVM ブート・モードに切り替えることができます
- Windows 2012 (HVM)
- Windows 2012 R2 (HVM)
- Windows 2016 (HVM)

**注:** ブート・ディスクのサイズは、オペレーティング・システムにより以下のように異なります。<br>  
Linux OS は 25 GB と 100 GB をサポートします。
Windows は 100 GB のみサポートします。

PV と HVM の間でのブート・モードの切り替えについて詳しくは、以下のリンクを参照してください。
* [Virtual guest supported boot modes ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")](https://sldn.softlayer.com/reference/services/SoftLayer_Virtual_Guest_Block_Device_Template_Group/getSupportedBootModes){: new_window}
* [Add boot mode option ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")](https://github.com/softlayer/softlayer-python/pull/936/files/09c35a9595651d66f3e117a055efe585745ba2b3){: new_window}
