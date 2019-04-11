---

copyright:
  years: 2017, 2018
lastupdated: "2018-04-08"

keywords: R1Soft, restoring OS, restoring bare metal

subcollection: software

---
{:new_window: target="_blank"}
{:shortdesc: .shortdesc}

# R1Soft イメージからのサーバーのリストア
{: #restoring-your-server-from-an-r1soft-image}

この手順に従って、パブリックまたはプライベートの {{site.data.keyword.BluVirtServers_full}} または {{site.data.keyword.BluBareMetServers_full}} へのリストアを実行します。サーバー障害によりデータまたは OS が欠損した場合は、この処理を行ってください。この処理により、バックアップされたすべてのファイル・システム・ブロック (OS と、バックアップから除外されなかったすべてのファイルが含まれます) がリストアされます。

ファイルのサブセットをリストアすることが目的である場合は、この処理を行わないでください。それらのファイルのみをリストアするには、[R1Soft Wiki](http://wiki.r1soft.com/display/CDP/Restoring+Files){:new_window} を参照してください。

## 仮想デバイスのリストア
{: #restoring-your-virtual-device}

1. [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window} で、リストアするデバイスをクリックします。
2. **「アクション」**メニューをクリックし、**「イメージからブート (Boot from image)」**を選択すると、プライベート・イメージのリストが表示されます。
3. メニューから**「パブリック・イメージ」**を選択します。
4. ご使用の R1Soft バージョンに該当する R1Soft エージェント・ブート・イメージ (serverbackup-centos-bootcd-agent.iso) を選択し、右側の**「このイメージからブート (Boot From This Image)」**リンクをクリックします。
5. リストアするサーバーの**「デバイスの詳細」**ページで、**「アクション」** > **「KVM コンソール (KVM Console)」**をクリックします。
6. コンソールが表示されてイメージがブートされると、いくつかのオプションが示された Debian ブート・ローダー画面が表示されます。Enter キーを押して、デフォルト・オプションでブートします。
7. OS がブートされたら、`netconfig` と入力して **Enter** キーを押します。
8. **「はい」**を選択してネットワーキングを構成します。
9. コントロール・ポータルのデバイス詳細でネットワーキング構成の詳細を入力します。
10. プロンプトが出されたら**「はい」**を選択してネットワーキングを再始動します。
11. オプションで、`passed root` と入力して SSH ログインの root パスワードを設定し、service ssh start と入力して SSH ログインを許可します。この手順は、ご使用の KVM コンソールが遅い場合に有効である可能性があります。
12. `service cdp-agent restart` と入力します (Tivoli Continuous Data Protection for Files エージェントがまだ実行されていなければ、このコマンドにより開始されます)。

## ベアメタル・デバイスのリストア
{: #restoring-your-bare-metal-device}

1. [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window} でチケットをオープンし、ご使用のベアメタル・サーバーを **R1Soft ベアメタル・リストア・モード**でブートすることを IBM に依頼してください。
2. リストアするサーバーの**「デバイスの詳細」**ページを使用して、**IPMI KVM コンソール**にログインします。
3. コンソールが表示されてイメージがブートされると、いくつかのオプションが示された Debian ブート・ローダー画面が表示されます。Enter キーを押して、デフォルト・オプションでブートします。
4. OS がブートされたら、`netconfig` と入力して **Enter** キーを押します。
5. **「はい」**を選択してネットワーキングを構成します。
6. コントロール・ポータルのデバイス詳細でネットワーキング構成の詳細を入力します。
7. プロンプトが出されたら**「はい」**を選択してネットワーキングを再始動します。
8. オプションで、`passed root` と入力して SSH ログインの root パスワードを設定し、service ssh start と入力して SSH ログインを許可します。この手順は、ご使用の KVM コンソールが遅い場合に有効である可能性があります。
9. `service cdp-agent restart` と入力します (Tivoli Continuous Data Protection for Files エージェントがまだ実行されていなければ、このコマンドにより開始されます)。

## R1Soft サーバーおよびその他のリストア・パラメーターとオプションの選択
{: #selecting-the-r1soft-server-and-other-restore-parameters-and-options}

R1Soft 資料で[ベアメタル・リストアの実行](http://wiki.r1soft.com/display/ServerBackup/Perform+a+bare-metal+restore)を参照してください。リストアするサーバーを選択し、ファイル・システム、部分表、およびその他のリストア・オプションを選択する必要があります。
