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

# Microsoft Windows 更新情報
{: #microsoft-windows-update-information}

IBM は、Microsoft Windows Server 環境用の OS およびソフトウェアの更新サービスを無料で提供しています。

{{site.data.keyword.Bluemix_notm}} のすべての更新サービスでは、以下の機能が共通しています。
* 更新トラフィックはご使用のサーバーから (プライベート VLAN 経由で) プライベート・サービス・ネットワークにルーティングされます。
* 更新トラフィックは無制限のプライベート・ネットワーク帯域幅の一部です。このトラフィックによりパブリック帯域幅割り当てが減ることはありません。
* 更新速度はベンダーから直接更新するよりも高速です (アップグレードされたポート速度はオンデマンドで利用可能です)。
* 世界中で重大な更新日に、更新はすぐに利用可能になります。
* 緊急事態には、パブリック・ポートがシャットダウンされる可能性がありますが、引き続きプライベート・ネットワークで更新が可能です。
* サーバーは、デプロイメント時に自動的に更新するように事前構成されており、オンデマンドで手動での更新も可能です。


{{site.data.keyword.Bluemix_notm}} の更新サーバーは、プライベート・サービス・ネットワーク上にあり、次のロケーション ID を持ちます。

Microsoft, **wsus01.service.softlayer.com**

カーネルまたはサービス・パックのアップグレードは、実動サーバー環境にインストールする前に必ずテストしてください。 IBM によってデプロイされた、特定のハードウェア、OS、およびアプリケーションに関する技術情報は、コントロール・ポータル内の FAQ またはドライバーのセクションにあります。IBM は、継続的にカーネルとサービス・パックのアップグレードをテストして、アップグレード・プロセスに役立つ関連情報 (ドライバーを含む) を投稿しています。


## WSUS Windows Server Update Services
{: #wsus-windows-server-update-services}

多くの場合、Microsoft Windows サーバーは、ローカル Windows Server Update Services (WSUS) サーバーから更新を自動的にプルします。しかし、サーバーが cloud-init 対応イメージを使用してプロビジョンされた場合、デフォルトの Microsoft WSUS (Windows Server Update Services) サーバーではなくローカルの {{site.data.keyword.cloud_notm}} WSUS サーバーを使用するように、手動で Windows レジストリーを更新しなければならない可能性があります。


仮想サーバーを、追加のソフトウェア、プロビジョン後スクリプト、拡張モニタリングなどのアドオンなしで Windows Server オペレーティング・システムとともに注文した場合、サーバーは cloud-init イメージでプロビジョンされる可能性があります。{{site.data.keyword.cloud_notm}} WSUS サーバーを指すようにレジストリーを更新する方法について詳しくは、[ローカル WSUS サーバーを使用するようにインスタンスを更新する](/docs/infrastructure/software?topic=software-updating-an-instance-to-use-a-local-wsus-server)を参照してください。

Microsoft Windows オペレーティング・システムでは、デフォルトで、パッチが使用可能になったらすぐにパッチをダウンロードしてインストールするようにサーバーが構成されます。 再始動が必要な場合、サーバーは自動的に再始動します。重大な脆弱性からサーバーを保護するために更新が行われます。異なる更新スケジュールにしたい場合、コントロール・パネルで **Windows Updates** フィーチャーを使用して更新スケジュールを変更できます。
