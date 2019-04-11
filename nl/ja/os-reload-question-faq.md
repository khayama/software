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

# FAQ
{: #faqs}

## デバイス上でオペレーティング・システム (OS) を変更できますか?
{: #can-the-operating-system-os-be-changed-on-the-device-}

OS を再ロードすることによって、インストールした OS およびソフトウェアを変更することができます<!--[OS Reload](perform-os-reload-device.html){:new_window}-->。 デバイス上での OS 再ロードを選択すると、ご使用のシステムにあるソフトウェアを更新できるページへのリンクが表示されます。 このページから、OS、コントロール・パネル、アンチウィルス・パッケージ、およびデータベース・ソフトウェアを更新することができます。

## 無料の OS 再ロードは提供されていますか?
{: #do-you-provide-complimentary-os-reloads-}

自動化された OS 再ロードは無料であり、カスタマイズされた OS 再ロード (オペレーティング・システムの変更、コントロール・パネルの追加や削除、パーティション編集、およびその他のオプション) を含みます。 詳細については、カスタマー・ポータルを開いてください。

## OS 再ロードの状況はどのようにしてトラッキングできますか?
{: #how-can-i-track-the-status-of-the-os-reload-}

カスタマー・ポータルの「ハードウェア」の下に、各サーバーの「注意」セクションがあります。 「注意」セクションに、再ロードの現行ステップと、再ロードのその部分が完了するまでの予測時間に関する情報へのリンクが含まれています。

## OS 再ロードで 2 次ディスクが消去されることはありますか?
{: #can-an-os-reload-erase-secondary-disks-}

OS 再ロードは、システム上の 1 次ディスクのみをフォーマットします。 その他のすべてのディスクは、現状のままになります。 イメージ・テンプレートからの再ロードでも同様です。 テンプレートに複数のディスクが含まれている場合、1 次ディスクのみがフォーマットされます。 他のディスクは変更されません。

## cpsrvd の失敗の E メールの原因は何ですか?
{: #why-did-my-cpsrvd-email-fail-}

**cpsrvd は失敗しました**という E メールを受信した場合、大抵それは再始動の直後に送信されています。chkservd が cpsrvd プロセスを検証しようとしたときに、プロセスが開始していないことが原因で検証が失敗すると、このエラーが起こります。

cpsrvd が失敗したという E メールが chkservd サービスから出されても、ほとんどの場合はこのメッセージを無視できます。 ただし、再始動の後に、5 回以上連続して、または一日に 5 回以上このメッセージが出される場合は、サポート・チケットをオープンしてください。
