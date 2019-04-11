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

# Red Hat 更新の説明
{: #red-hat-update-instructions}

IBM は、Red Hat 環境用の OS およびソフトウェアの更新サービスを無料で提供しています。

IBM が提供するすべての更新サービスでは、以下の機能が共通しています。
* 更新トラフィックはご使用のサーバーから (プライベート VLAN 経由で) プライベート・サービス・ネットワークにルーティングされます。
* 更新トラフィックは無制限のプライベート・ネットワーク帯域幅の一部です。このトラフィックによりパブリック帯域幅割り当てが減ることはありません。
* 更新速度はベンダーから直接更新するよりも高速です (アップグレードされたポート速度はオンデマンドで利用可能です)。
* 世界中で重大な更新日に、更新はすぐに利用可能になります。
* 緊急事態には、パブリック・ポートがシャットダウンされる可能性がありますが、引き続きプライベート・ネットワークで更新が可能です。
* サーバーは、デプロイメント時に自動的に更新するように事前構成されており、オンデマンドで手動での更新も可能です。

IBM の更新サーバーは、以下のロケーション ID でプライベート・サービス・ネットワーク上にあります。

|データ・センター|サービス・ホスト・アドレス|
|---|---|
|アムステルダム|rhnproxyams0101.service.softlayer.com|
|ダラス|rhnproxy101.service.softlayer.com|
|ヒューストン|rhnproxy421.service.softlayer.com|
|サンノゼ|rhnproxy501.service.softlayer.com|
|シアトル|rhnproxy201.service.softlayer.com|
|シンガポール|rhnproxysng0101.service.softlayer.com|
|ワシントン D.C.|rhnproxy301.service.softlayer.com|

カーネルまたはサービス・パックのアップグレードは、実稼働環境にインストールする前に必ずテストしてください。デプロイされた特定のハードウェア、OS、およびアプリケーションに関する技術情報は、コントロール・ポータル内の FAQ またはドライバーのセクションにあります。

IBM は、カーネルとサービス・パックのアップグレードをテストして、アップグレード・プロセスに役立つ関連情報とドライバーを投稿しています。

## RHN サブスクリプション
{: #rhn-subscription}

Red Hat オペレーティング・システム向けに、IBM は、重要なセキュリティー更新と重要性の低いセキュリティー更新をインストールするための Red Hat Network Satellite サーバーを提供しています。

{{site.data.keyword.Bluemix_notm}} が提供する Red Hat Network には、RHN Satellite サーバーとプロキシー・サーバーが含まれます。Red Hat サーバーは、プロビジョンされると、適切なプロキシー・サーバーを使用して IBM RHN Satellite サーバーに自動的に登録されます。この登録により、**up2date** コマンドをご使用のサーバー上でローカルに使用し、プライベート・サービス・ネットワークを介して更新をプルすることが可能になります。

企業向けのサービス品質を確保して、適切な変更管理技法を容易に使用できるように、Red Hat OS サーバーはデフォルトでカーネル更新をスキップするように構成されています。システムの安定性のため、回帰テストの完了後に、カーネルのアップグレードを手動で実行してください。IBM は、適切なパフォーマンスのために安定したカーネル・エディションを必要とする最先端のハードウェア・テクノロジーを使用しています。
