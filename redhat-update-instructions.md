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

# Red Hat Update Instructions
{: #red-hat-update-instructions}

IBM provides OS and software update services for Red Hat environments free of charge.
{:shortdesc}

All update services at IBM share the following features:
* Update traffic is routed from your server (over your private VLAN) to the private service network
* Update traffic is part of your unlimited private network bandwidth. This traffic does not reduce public bandwidth allotments.
* Updates speeds are faster than updating from vendors directly (upgraded ports speeds available on demand)
* Updates are readily available during worldwide heavy critical update days.
* In emergency situations, public ports can be shut down while still allowing updates to occur over the private network
* Servers are pre-configured to update automatically at deployment with manual updates available on demand.

IBM update servers are in the private service network with the following location identifiers:

|Datacenter|Service Host Address|
|---|---|
|Amsterdam|rhnproxyams0101.service.softlayer.com|
|Dallas|rhnproxy101.service.softlayer.com|
|Houston|rhnproxy421.service.softlayer.com|
|San Jose|rhnproxy501.service.softlayer.com|
|Seattle|rhnproxy201.service.softlayer.com|
|Singapore|rhnproxysng0101.service.softlayer.com|
|Washington D.C.|rhnproxy301.service.softlayer.com|

Always test kernel or service pack upgrades before you install them in production environments. You can find technical information for specific hardware, OS, and applications deployed in the FAQ or drivers section inside the control portal.

IBM tests kernel and service pack upgrades and posts related information and drivers to help your upgrade process.

## RHN Subscription
{: #rhn-subscription}

For Red Hat operating systems, IBM provides Red Hat Network Satellite servers to install critical and non-critical security updates.

The Red Hat Network at {{site.data.keyword.Bluemix_notm}} includes RHN Satellite and Proxy servers. When your Red Hat server is provisioned, it is automatically registered to the IBM RHN Satellite server by using the appropriate proxy server. With this registration, you can use **up2date** commands locally on your servers and pull updates across the private service network.

To ensure enterprise quality of service and facilitate proper change management techniques, Red Hat OS servers are configured by default to skip kernel updates. To ensure system stability, complete your kernel upgrades manually after you complete regression testing. IBM uses leading-edge hardware technologies that require stable kernel editions for proper performance.
