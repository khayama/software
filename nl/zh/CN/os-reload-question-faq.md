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

# 常见问题
{: #faqs}

## 可以在设备上更改操作系统吗？
{: #can-the-operating-system-os-be-changed-on-the-device-}

可以更改已安装的操作系统和软件，方法是重装操作系统<!--[OS Reload](perform-os-reload-device.html){:new_window}-->。在设备上选择操作系统重装之后，系统会显示一个链接，指向一个可更新系统软件的页面。在此页面中，您可以更新操作系统、控制面板、防病毒程序包以及数据库软件。

## 提供免费操作系统重装吗？
{: #do-you-provide-complimentary-os-reloads-}

自动操作系统重装是免费的，包括定制操作系统重装，如更改操作系统、添加或除去控制面板、分区编辑以及其他选项。有关更多信息，请打开客户门户网站。

## 如何跟踪操作系统重装状态？
{: #how-can-i-track-the-status-of-the-os-reload-}

在客户门户网站的“硬件”下有一个针对每个服务器的“注释”部分。“注释”部分中包含的链接指向有关重新装入当前步骤的信息，以及完成该重新装入部分的估算时间。

## 操作系统重装会擦除辅助磁盘吗？
{: #can-an-os-reload-erase-secondary-disks-}

操作系统重装只会格式化系统主磁盘。其他所有磁盘都不受影响。这跟从映像模板重新装入的方式相同。如果模板中包含超过一个磁盘，那么只会格式化主磁盘。不会对其他磁盘进行任何更改。

## 我的 cpsrvd 电子邮件为什么失败？
{: #why-did-my-cpsrvd-email-fail-}

在大多数情况下，如果您收到电子邮件说 **cpsrvd 失败**，那么该邮件是在重新启动之后立即发送的。如果 chkservd 尝试验证 cpsrvd 过程，就会发生此错误。验证失败是因为该过程未开始。

如果您收到 chkservd 服务发来的电子邮件说 cpsrvd 失败，大多数情况下都可以忽略该消息。但是，如果连续收到 5 个或更多此类消息，或者如果一天中在重新启动后收到超过 4 个此类消息，请开具支持凭单。
