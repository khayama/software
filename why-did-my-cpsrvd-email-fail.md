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
# Why did my cpsrvd email fail?

In most cases, when you get an email stating **cpsrvd failed**, it is sent immediately after a reboot. This error occurs when chkservd attempts to validate the cpsrvd process. The validation fails because the process has not started yet.

If you receive an email from the chkservd service, stating that cpsrvd failed, you can ignore the message in most cases. However, if you receive 5 or more of these messages in a row or if you receive more than 4 in a day that follow reboots, open a support ticket.
